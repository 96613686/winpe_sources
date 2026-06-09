# SHFusionInitializeFromModuleID

- ea: `0x1800106f8`
- end: `0x1800107fd`
- name: `SHFusionInitializeFromModuleID`
- size: `261`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008738`
- `0x1800105f8`

## callees

- `0x1800106f8`
- `0x180010900`
- `0x180016280`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180010754`
- `KERNEL32!GetModuleHandleW` at `0x180010754`
- `KERNEL32!GetModuleFileNameW` at `0x18001076b`
- `KERNEL32!GetModuleFileNameW` at `0x18001076b`
- `KERNEL32!ReleaseActCtx` at `0x1800107bb`
- `KERNEL32!ReleaseActCtx` at `0x1800107bb`
- `KERNEL32!CreateActCtxW` at `0x18001079d`
- `KERNEL32!CreateActCtxW` at `0x18001079d`

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
0x1800106f8  mov     [rsp-8+arg_10], rbx
0x1800106fd  mov     [rsp-8+arg_18], rdi
0x180010702  push    rbp
0x180010703  lea     rbp, [rsp-180h]
0x18001070b  sub     rsp, 280h
0x180010712  mov     rax, cs:__security_cookie
0x180010719  xor     rax, rsp
0x18001071c  mov     [rbp+180h+var_10], rax
0x180010723  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x18001072b  mov     rbx, rcx
0x18001072e  mov     edi, edx
0x180010730  jnz     loc_1800107D4
0x180010736  xorps   xmm0, xmm0
0x180010739  xor     eax, eax
0x18001073b  mov     [rsp+280h+pActCtx.hModule], rax
0x180010740  movups  xmmword ptr [rsp+280h+pActCtx.cbSize], xmm0
0x180010745  movups  xmmword ptr [rsp+280h+pActCtx.wProcessorArchitecture], xmm0
0x18001074a  movups  xmmword ptr [rsp+280h+pActCtx.lpResourceName], xmm0
0x18001074f  test    rcx, rcx
0x180010752  jnz     short loc_18001075D
0x180010754  call    cs:__imp_GetModuleHandleW
0x18001075a  mov     rbx, rax
0x18001075d  mov     r8d, 104h; nSize
0x180010763  lea     rdx, [rsp+280h+Filename]; lpFilename
0x180010768  mov     rcx, rbx; hModule
0x18001076b  call    cs:__imp_GetModuleFileNameW
0x180010771  movzx   ecx, di
0x180010774  lea     rax, [rsp+280h+Filename]
0x180010779  mov     [rsp+280h+pActCtx.lpResourceName], rcx
0x18001077e  lea     rcx, [rsp+280h+pActCtx]; pActCtx
0x180010783  mov     [rsp+280h+pActCtx.cbSize], 38h ; '8'
0x18001078b  mov     [rsp+280h+pActCtx.lpSource], rax
0x180010790  mov     [rsp+280h+pActCtx.dwFlags], 88h
0x180010798  mov     [rsp+280h+pActCtx.hModule], rbx
0x18001079d  call    cs:__imp_CreateActCtxW
0x1800107a3  mov     rcx, rax; hActCtx
0x1800107a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800107aa  jz      short loc_1800107C6
0x1800107ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800107b0  lock cmpxchg cs:g_hActCtx, rcx
0x1800107b9  jz      short loc_1800107C1
0x1800107bb  call    cs:__imp_ReleaseActCtx
0x1800107c1  call    DelayLoadCC
0x1800107c6  cmp     cs:g_hActCtx, 0FFFFFFFFFFFFFFFFh
0x1800107ce  jnz     short loc_1800107D4
0x1800107d0  xor     eax, eax
0x1800107d2  jmp     short loc_1800107D9
0x1800107d4  mov     eax, 1
0x1800107d9  mov     rcx, [rbp+180h+var_10]
0x1800107e0  xor     rcx, rsp; StackCookie
0x1800107e3  call    __security_check_cookie
0x1800107e8  lea     r11, [rsp+280h+var_s0]
0x1800107f0  mov     rbx, [r11+20h]
0x1800107f4  mov     rdi, [r11+28h]
0x1800107f8  mov     rsp, r11
0x1800107fb  pop     rbp
0x1800107fc  retn
```
