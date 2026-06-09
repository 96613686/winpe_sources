# SHFusionInitializeFromModuleID

- ea: `0x18000b0c0`
- end: `0x18000b1c5`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `_BOOL8 __fastcall(HMODULE hModule, unsigned __int16)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004030`
- `0x18000b030`

## callees

- `0x18000b0c0`
- `0x18000b224`
- `0x18000b710`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b11c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b11c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000b133`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000b133`
- `KERNEL32!CreateActCtxW` at `0x18000b165`
- `KERNEL32!CreateActCtxW` at `0x18000b165`
- `KERNEL32!ReleaseActCtx` at `0x18000b183`
- `KERNEL32!ReleaseActCtx` at `0x18000b183`

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
0x18000b0c0  mov     [rsp-8+arg_10], rbx
0x18000b0c5  mov     [rsp-8+arg_18], rdi
0x18000b0ca  push    rbp
0x18000b0cb  lea     rbp, [rsp-180h]
0x18000b0d3  sub     rsp, 280h
0x18000b0da  mov     rax, cs:__security_cookie
0x18000b0e1  xor     rax, rsp
0x18000b0e4  mov     [rbp+180h+var_10], rax
0x18000b0eb  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000b0f3  mov     rbx, rcx
0x18000b0f6  mov     edi, edx
0x18000b0f8  jnz     loc_18000B19C
0x18000b0fe  xorps   xmm0, xmm0
0x18000b101  xor     eax, eax
0x18000b103  mov     [rsp+280h+pActCtx.hModule], rax
0x18000b108  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x18000b10d  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18000b112  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18000b117  test    rcx, rcx
0x18000b11a  jnz     short loc_18000B125
0x18000b11c  call    cs:__imp_GetModuleHandleW
0x18000b122  mov     rbx, rax
0x18000b125  mov     r8d, 104h; nSize
0x18000b12b  lea     rdx, [rsp+280h+Filename]; lpFilename
0x18000b130  mov     rcx, rbx; hModule
0x18000b133  call    cs:__imp_GetModuleFileNameW
0x18000b139  movzx   ecx, di
0x18000b13c  lea     rax, [rsp+280h+Filename]
0x18000b141  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18000b146  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x18000b14b  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18000b153  mov     [rsp+280h+pActCtx.lpSource], rax
0x18000b158  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x18000b160  mov     [rsp+280h+pActCtx.hModule], rbx
0x18000b165  call    cs:__imp_CreateActCtxW
0x18000b16b  mov     rcx, rax; hActCtx
0x18000b16e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b172  jz      short loc_18000B18E
0x18000b174  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b178  lock cmpxchg cs:g_hActCtx, rcx
0x18000b181  jz      short loc_18000B189
0x18000b183  call    cs:__imp_ReleaseActCtx
0x18000b189  call    DelayLoadCC
0x18000b18e  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18000b196  jnz     short loc_18000B19C
0x18000b198  xor     eax, eax
0x18000b19a  jmp     short loc_18000B1A1
0x18000b19c  mov     eax, 1
0x18000b1a1  mov     rcx, [rbp+180h+var_10]
0x18000b1a8  xor     rcx, rsp; StackCookie
0x18000b1ab  call    __security_check_cookie
0x18000b1b0  lea     r11, [rsp+280h+var_s0]
0x18000b1b8  mov     rbx, [r11+20h]
0x18000b1bc  mov     rdi, [r11+28h]
0x18000b1c0  mov     rsp, r11
0x18000b1c3  pop     rbp
0x18000b1c4  retn
```
