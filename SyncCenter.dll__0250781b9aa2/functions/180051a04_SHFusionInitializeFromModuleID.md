# SHFusionInitializeFromModuleID

- ea: `0x180051a04`
- end: `0x180051b09`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ed0`
- `0x180003200`
- `0x1800518a4`

## callees

- `0x180051a04`
- `0x180051ef8`
- `0x180052950`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180051a77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180051a77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051a60`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180051a60`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180051aa9`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180051aa9`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180051ac7`
- `api-ms-win-core-sidebyside-l1-1-0!ReleaseActCtx` at `0x180051ac7`

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
0x180051a04  mov     [rsp-8+arg_10], rbx
0x180051a09  mov     [rsp-8+arg_18], rdi
0x180051a0e  push    rbp
0x180051a0f  lea     rbp, [rsp-180h]
0x180051a17  sub     rsp, 280h
0x180051a1e  mov     rax, cs:__security_cookie
0x180051a25  xor     rax, rsp
0x180051a28  mov     [rbp+180h+var_10], rax
0x180051a2f  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180051a37  mov     rbx, rcx
0x180051a3a  mov     edi, edx
0x180051a3c  jnz     loc_180051AE0
0x180051a42  xorps   xmm0, xmm0
0x180051a45  xor     eax, eax
0x180051a47  mov     [rsp+280h+pActCtx.hModule], rax
0x180051a4c  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180051a51  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x180051a56  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x180051a5b  test    rcx, rcx
0x180051a5e  jnz     short loc_180051A69
0x180051a60  call    cs:__imp_GetModuleHandleW
0x180051a66  mov     rbx, rax
0x180051a69  mov     r8d, 104h; nSize
0x180051a6f  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180051a74  mov     rcx, rbx; hModule
0x180051a77  call    cs:__imp_GetModuleFileNameW
0x180051a7d  movzx   ecx, di
0x180051a80  lea     rax, [rsp+280h+Filename]
0x180051a85  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x180051a8a  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180051a8f  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x180051a97  mov     [rsp+280h+pActCtx.lpSource], rax
0x180051a9c  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180051aa4  mov     [rsp+280h+pActCtx.hModule], rbx
0x180051aa9  call    cs:__imp_CreateActCtxW
0x180051aaf  mov     rcx, rax; hActCtx
0x180051ab2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180051ab6  jz      short loc_180051AD2
0x180051ab8  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051abc  lock cmpxchg cs:g_hActCtx, rcx
0x180051ac5  jz      short loc_180051ACD
0x180051ac7  call    cs:__imp_ReleaseActCtx
0x180051acd  call    DelayLoadCC
0x180051ad2  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x180051ada  jnz     short loc_180051AE0
0x180051adc  xor     eax, eax
0x180051ade  jmp     short loc_180051AE5
0x180051ae0  mov     eax, 1
0x180051ae5  mov     rcx, [rbp+180h+var_10]
0x180051aec  xor     rcx, rsp; StackCookie
0x180051aef  call    __security_check_cookie
0x180051af4  lea     r11, [rsp+280h+var_s0]
0x180051afc  mov     rbx, [r11+20h]
0x180051b00  mov     rdi, [r11+28h]
0x180051b04  mov     rsp, r11
0x180051b07  pop     rbp
0x180051b08  retn
```
