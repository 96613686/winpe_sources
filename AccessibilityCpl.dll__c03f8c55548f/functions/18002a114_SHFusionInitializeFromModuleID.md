# SHFusionInitializeFromModuleID

- ea: `0x18002a114`
- end: `0x18002a219`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003400`
- `0x18002a084`

## callees

- `0x18002a114`
- `0x18002a278`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a170`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002a170`
- `KERNEL32!GetModuleFileNameW` at `0x18002a187`
- `KERNEL32!GetModuleFileNameW` at `0x18002a187`
- `KERNEL32!ReleaseActCtx` at `0x18002a1d7`
- `KERNEL32!ReleaseActCtx` at `0x18002a1d7`
- `KERNEL32!CreateActCtxW` at `0x18002a1b9`
- `KERNEL32!CreateActCtxW` at `0x18002a1b9`

## pseudocode

```c
_BOOL8 __fastcall SHFusionInitializeFromModuleID(HMODULE hModule, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rbx
  HANDLE v4; // rax
  ACTCTXW pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-A0h] BYREF

  ModuleHandleW = hModule;
  if ( g_hActCtx != (HANDLE)-1LL )
    return 1;
  memset(&pActCtx, 0, sizeof(pActCtx));
  if ( !hModule )
    ModuleHandleW = GetModuleHandleW(0);
  GetModuleFileNameW(ModuleHandleW, Filename, 0x104u);
  pActCtx.lpResourceName = (LPCWSTR)a2;
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 136;
  pActCtx.hModule = ModuleHandleW;
  v4 = CreateActCtxW(&pActCtx);
  if ( v4 != (HANDLE)-1LL )
  {
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hActCtx, (signed __int64)v4, -1) != -1 )
      ReleaseActCtx(v4);
    DelayLoadCC();
  }
  return g_hActCtx != (HANDLE)-1LL;
}

```

## disassembly

```asm
0x18002a114  mov     [rsp-8+arg_10], rbx
0x18002a119  mov     [rsp-8+arg_18], rdi
0x18002a11e  push    rbp
0x18002a11f  lea     rbp, [rsp-180h]
0x18002a127  sub     rsp, 280h
0x18002a12e  mov     rax, cs:__security_cookie
0x18002a135  xor     rax, rsp
0x18002a138  mov     [rbp+180h+var_10], rax
0x18002a13f  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002a147  mov     rbx, rcx
0x18002a14a  mov     edi, edx
0x18002a14c  jnz     loc_18002A1F0
0x18002a152  xorps   xmm0, xmm0
0x18002a155  xor     eax, eax
0x18002a157  mov     [rsp+280h+pActCtx.hModule], rax
0x18002a15c  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18002a161  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18002a166  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18002a16b  test    rcx, rcx
0x18002a16e  jnz     short loc_18002A179
0x18002a170  call    cs:__imp_GetModuleHandleW
0x18002a176  mov     rbx, rax
0x18002a179  mov     r8d, 104h; nSize
0x18002a17f  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18002a184  mov     rcx, rbx; hModule
0x18002a187  call    cs:__imp_GetModuleFileNameW
0x18002a18d  movzx   ecx, di
0x18002a190  lea     rax, [rsp+280h+Filename]
0x18002a195  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18002a19a  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18002a19f  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18002a1a7  mov     [rsp+280h+pActCtx.lpSource], rax
0x18002a1ac  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18002a1b4  mov     [rsp+280h+pActCtx.hModule], rbx
0x18002a1b9  call    cs:__imp_CreateActCtxW
0x18002a1bf  mov     rcx, rax; hActCtx
0x18002a1c2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002a1c6  jz      short loc_18002A1E2
0x18002a1c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a1cc  lock cmpxchg cs:g_hActCtx, rcx
0x18002a1d5  jz      short loc_18002A1DD
0x18002a1d7  call    cs:__imp_ReleaseActCtx
0x18002a1dd  call    DelayLoadCC
0x18002a1e2  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18002a1ea  jnz     short loc_18002A1F0
0x18002a1ec  xor     eax, eax
0x18002a1ee  jmp     short loc_18002A1F5
0x18002a1f0  mov     eax, 1
0x18002a1f5  mov     rcx, [rbp+180h+var_10]
0x18002a1fc  xor     rcx, rsp; StackCookie
0x18002a1ff  call    __security_check_cookie
0x18002a204  lea     r11, [rsp+280h+var_s0]
0x18002a20c  mov     rbx, [r11+20h]
0x18002a210  mov     rdi, [r11+28h]
0x18002a214  mov     rsp, r11
0x18002a217  pop     rbp
0x18002a218  retn
```
