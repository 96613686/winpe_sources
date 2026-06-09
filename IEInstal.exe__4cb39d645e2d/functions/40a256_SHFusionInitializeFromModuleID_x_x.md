# SHFusionInitializeFromModuleID(x,x)

- ea: `0x40a256`
- end: `0x40a329`
- name: `_SHFusionInitializeFromModuleID@8`
- size: `211`
- prototype: `BOOL __fastcall(HMODULE hModule, unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x409212`
- `0x40a1f1`

## callees

- `0x40a256`
- `0x40a372`
- `0x40cb60`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x40a292`
- `KERNEL32!GetModuleHandleW` at `0x40a292`
- `KERNEL32!CreateActCtxW` at `0x40a2e3`
- `KERNEL32!CreateActCtxW` at `0x40a2e3`
- `KERNEL32!ReleaseActCtx` at `0x40a304`
- `KERNEL32!ReleaseActCtx` at `0x40a304`
- `KERNEL32!GetModuleFileNameW` at `0x40a2a7`
- `KERNEL32!GetModuleFileNameW` at `0x40a2a7`

## pseudocode

```c
BOOL __fastcall SHFusionInitializeFromModuleID(HMODULE hModule, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // esi
  HANDLE v4; // eax
  ACTCTXW pActCtx; // [esp+8h] [ebp-22Ch] BYREF
  WCHAR Filename[260]; // [esp+28h] [ebp-20Ch] BYREF

  ModuleHandleW = hModule;
  if ( g_hActCtx == (HANDLE)-1 )
  {
    memset(&pActCtx, 0, sizeof(pActCtx));
    if ( !hModule )
      ModuleHandleW = GetModuleHandleW(0);
    GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
    pActCtx.cbSize = 32;
    pActCtx.lpSource = Filename;
    pActCtx.lpResourceName = (LPCWSTR)a2;
    pActCtx.dwFlags = 136;
    pActCtx.hModule = ModuleHandleW;
    v4 = CreateActCtxW(&pActCtx);
    if ( v4 != (HANDLE)-1 )
    {
      if ( _InterlockedCompareExchange((volatile signed __int32 *)&g_hActCtx, (signed __int32)v4, -1) != -1 )
        ReleaseActCtx(v4);
      DelayLoadCC();
    }
  }
  return (char *)g_hActCtx + 1 != 0;
}

```

## disassembly

```asm
0x40a256  mov     edi, edi
0x40a258  push    ebp
0x40a259  mov     ebp, esp
0x40a25b  sub     esp, 22Ch
0x40a261  mov     eax, ___security_cookie
0x40a266  xor     eax, ebp
0x40a268  mov     [ebp+var_4], eax
0x40a26b  cmp     _g_hActCtx, 0FFFFFFFFh
0x40a272  push    ebx
0x40a273  push    esi
0x40a274  mov     ebx, edx
0x40a276  mov     esi, ecx
0x40a278  jnz     loc_40A30F
0x40a27e  push    edi
0x40a27f  push    8
0x40a281  pop     ecx
0x40a282  xor     eax, eax
0x40a284  lea     edi, [ebp+pActCtx]
0x40a28a  rep stosd
0x40a28c  pop     edi
0x40a28d  test    esi, esi
0x40a28f  jnz     short loc_40A29A
0x40a291  push    eax; lpModuleName
0x40a292  call    ds:__imp__GetModuleHandleW@4; GetModuleHandleW(x)
0x40a298  mov     esi, eax
0x40a29a  push    104h; nSize
0x40a29f  lea     eax, [ebp+Filename]
0x40a2a5  push    eax; lpFilename
0x40a2a6  push    esi; hModule
0x40a2a7  call    ds:__imp__GetModuleFileNameW@12; GetModuleFileNameW(x,x,x)
0x40a2ad  lea     eax, [ebp+Filename]
0x40a2b3  mov     [ebp+pActCtx.cbSize], 20h ; ' '
0x40a2bd  mov     [ebp+pActCtx.lpSource], eax
0x40a2c3  movzx   eax, bx
0x40a2c6  mov     [ebp+pActCtx.lpResourceName], eax
0x40a2cc  lea     eax, [ebp+pActCtx]
0x40a2d2  push    eax; pActCtx
0x40a2d3  mov     [ebp+pActCtx.dwFlags], 88h
0x40a2dd  mov     [ebp+pActCtx.hModule], esi
0x40a2e3  call    ds:__imp__CreateActCtxW@4; CreateActCtxW(x)
0x40a2e9  mov     edx, eax
0x40a2eb  cmp     edx, 0FFFFFFFFh
0x40a2ee  jz      short loc_40A30F
0x40a2f0  mov     ecx, edx
0x40a2f2  mov     esi, offset _g_hActCtx
0x40a2f7  or      eax, 0FFFFFFFFh
0x40a2fa  lock cmpxchg [esi], ecx
0x40a2fe  cmp     eax, 0FFFFFFFFh
0x40a301  jz      short loc_40A30A
0x40a303  push    edx; hActCtx
0x40a304  call    ds:__imp__ReleaseActCtx@4; ReleaseActCtx(x)
0x40a30a  call    _DelayLoadCC@0; DelayLoadCC()
0x40a30f  mov     ecx, [ebp+var_4]
0x40a312  xor     eax, eax
0x40a314  cmp     _g_hActCtx, 0FFFFFFFFh
0x40a31b  pop     esi
0x40a31c  setnz   al
0x40a31f  xor     ecx, ebp; StackCookie
0x40a321  pop     ebx
0x40a322  call    @__security_check_cookie@4; __security_check_cookie(x)
0x40a327  leave
0x40a328  retn
```
