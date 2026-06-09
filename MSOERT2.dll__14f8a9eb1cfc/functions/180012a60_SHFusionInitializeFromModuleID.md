# SHFusionInitializeFromModuleID

- ea: `0x180012a60`
- end: `0x180012b66`
- name: `SHFusionInitializeFromModuleID`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800129d8`

## callees

- `0x180012a60`
- `0x180012c5c`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x180012ac0`
- `KERNEL32!GetModuleHandleA` at `0x180012ac0`
- `KERNEL32!GetModuleFileNameA` at `0x180012ad7`
- `KERNEL32!GetModuleFileNameA` at `0x180012ad7`
- `KERNEL32!CreateActCtxA` at `0x180012b09`
- `KERNEL32!CreateActCtxA` at `0x180012b09`
- `KERNEL32!ReleaseActCtx` at `0x180012b27`
- `KERNEL32!ReleaseActCtx` at `0x180012b27`

## pseudocode

```c
_BOOL8 SHFusionInitializeFromModuleID()
{
  HMODULE ModuleHandleA; // rbx
  unsigned __int16 v1; // di
  HANDLE v2; // rax
  ACTCTXA pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  CHAR Filename[272]; // [rsp+60h] [rbp-A0h] BYREF

  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  ModuleHandleA = hModule;
  v1 = dword_1800209E8;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleA = GetModuleHandleA(0);
  GetModuleFileNameA(ModuleHandleA, Filename, 0x104u);
  pActCtx.lpResourceName = (LPCSTR)v1;
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleA;
  v2 = CreateActCtxA(&pActCtx);
  if ( v2 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v2, -1) != -1 )
      ReleaseActCtx(v2);
    DelayLoadCC();
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x180012a60  mov     [rsp-8+arg_0], rbx
0x180012a65  mov     [rsp-8+arg_8], rdi
0x180012a6a  push    rbp
0x180012a6b  lea     rbp, [rsp-80h]
0x180012a70  sub     rsp, 180h
0x180012a77  mov     rax, cs:__security_cookie
0x180012a7e  xor     rax, rsp
0x180012a81  mov     [rbp+80h+var_10], rax
0x180012a85  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180012a8d  jnz     loc_180012B40
0x180012a93  mov     rbx, cs:hModule
0x180012a9a  xorps   xmm0, xmm0
0x180012a9d  mov     edi, cs:dword_1800209E8
0x180012aa3  xor     eax, eax
0x180012aa5  mov     [rsp+180h+pActCtx.hModule], rax
0x180012aaa  movups  xmmword ptr [rsp+180h+pActCtx.cbSize], xmm0
0x180012aaf  movups  xmmword ptr [rsp+180h+pActCtx.wProcessorArchitecture], xmm0
0x180012ab4  movups  xmmword ptr [rsp+180h+pActCtx.lpResourceName], xmm0
0x180012ab9  test    rbx, rbx
0x180012abc  jnz     short loc_180012AC9
0x180012abe  xor     ecx, ecx; lpModuleName
0x180012ac0  call    cs:__imp_GetModuleHandleA
0x180012ac6  mov     rbx, rax
0x180012ac9  mov     r8d, 104h; nSize
0x180012acf  lea     rdx, [rsp+180h+Filename]; lpFilename
0x180012ad4  mov     rcx, rbx; hModule
0x180012ad7  call    cs:__imp_GetModuleFileNameA
0x180012add  movzx   ecx, di
0x180012ae0  lea     rax, [rsp+180h+Filename]
0x180012ae5  mov     [rsp+180h+pActCtx.lpResourceName], rcx
0x180012aea  lea     rcx, [rsp+180h+pActCtx]; pActCtx
0x180012aef  mov     [rsp+180h+pActCtx.cbSize], 38h ; '8'
0x180012af7  mov     [rsp+180h+pActCtx.lpSource], rax
0x180012afc  mov     [rsp+180h+pActCtx.dwFlags], 88h
0x180012b04  mov     [rsp+180h+pActCtx.hModule], rbx
0x180012b09  call    cs:__imp_CreateActCtxA
0x180012b0f  mov     rcx, rax; hActCtx
0x180012b12  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012b16  jz      short loc_180012B32
0x180012b18  or      rax, 0FFFFFFFFFFFFFFFFh
0x180012b1c  lock cmpxchg cs:g_hActCtx, rcx
0x180012b25  jz      short loc_180012B2D
0x180012b27  call    cs:__imp_ReleaseActCtx
0x180012b2d  call    DelayLoadCC
0x180012b32  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180012b3a  jnz     short loc_180012B40
0x180012b3c  xor     eax, eax
0x180012b3e  jmp     short loc_180012B45
0x180012b40  mov     eax, 1
0x180012b45  mov     rcx, [rbp+80h+var_10]
0x180012b49  xor     rcx, rsp; StackCookie
0x180012b4c  call    __security_check_cookie
0x180012b51  lea     r11, [rsp+180h+var_s0]
0x180012b59  mov     rbx, [r11+10h]
0x180012b5d  mov     rdi, [r11+18h]
0x180012b61  mov     rsp, r11
0x180012b64  pop     rbp
0x180012b65  retn
```
