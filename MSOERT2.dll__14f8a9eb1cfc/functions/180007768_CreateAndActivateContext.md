# CreateAndActivateContext

- ea: `0x180007768`
- end: `0x180007839`
- name: `CreateAndActivateContext`
- size: `209`
- prototype: `__int64 __fastcall(ULONG_PTR *lpCookie)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007ba8`

## callees

- `0x180007768`
- `0x180012f8e`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x1800077cc`
- `KERNEL32!GetModuleFileNameA` at `0x1800077cc`
- `KERNEL32!CreateActCtxA` at `0x1800077fa`
- `KERNEL32!CreateActCtxA` at `0x1800077fa`
- `KERNEL32!ActivateActCtx` at `0x18000780f`
- `KERNEL32!ActivateActCtx` at `0x18000780f`

## pseudocode

```c
HANDLE __fastcall CreateAndActivateContext(ULONG_PTR *lpCookie)
{
  HANDLE v2; // rax
  HANDLE v3; // rbx
  ACTCTXA pActCtx; // [rsp+20h] [rbp-E0h] BYREF
  CHAR Filename[272]; // [rsp+60h] [rbp-A0h] BYREF

  memset(&pActCtx.wProcessorArchitecture, 0, 40);
  memset_0(Filename, 0, 0x104u);
  GetModuleFileNameA(g_hInst, Filename, 0x104u);
  pActCtx.cbSize = 56;
  pActCtx.lpSource = Filename;
  pActCtx.dwFlags = 8;
  pActCtx.lpResourceName = (LPCSTR)123;
  v2 = CreateActCtxA(&pActCtx);
  v3 = v2;
  if ( v2 != (HANDLE)-1LL )
    ActivateActCtx(v2, lpCookie);
  return v3;
}

```

## disassembly

```asm
0x180007768  mov     [rsp-8+arg_8], rbx
0x18000776d  mov     [rsp-8+arg_10], rdi
0x180007772  push    rbp
0x180007773  lea     rbp, [rsp-80h]
0x180007778  sub     rsp, 180h
0x18000777f  mov     rax, cs:__security_cookie
0x180007786  xor     rax, rsp
0x180007789  mov     [rbp+80h+var_10], rax
0x18000778d  xorps   xmm0, xmm0
0x180007790  mov     rdi, rcx
0x180007793  xor     eax, eax
0x180007795  lea     rcx, [rsp+180h+Filename]; void *
0x18000779a  mov     ebx, 104h
0x18000779f  mov     [rsp+180h+pActCtx.hModule], rax
0x1800077a4  mov     r8d, ebx; Size
0x1800077a7  xor     edx, edx; Val
0x1800077a9  movups  xmmword ptr [rsp+180h+pActCtx.cbSize], xmm0
0x1800077ae  movups  xmmword ptr [rsp+180h+pActCtx.wProcessorArchitecture], xmm0
0x1800077b3  movups  xmmword ptr [rsp+180h+pActCtx.lpResourceName], xmm0
0x1800077b8  call    memset_0
0x1800077bd  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hModule
0x1800077c4  lea     rdx, [rsp+180h+Filename]; lpFilename
0x1800077c9  mov     r8d, ebx; nSize
0x1800077cc  call    cs:__imp_GetModuleFileNameA
0x1800077d2  lea     rax, [rsp+180h+Filename]
0x1800077d7  mov     [rsp+180h+pActCtx.cbSize], 38h ; '8'
0x1800077df  lea     rcx, [rsp+180h+pActCtx]; pActCtx
0x1800077e4  mov     [rsp+180h+pActCtx.lpSource], rax
0x1800077e9  mov     [rsp+180h+pActCtx.dwFlags], 8
0x1800077f1  mov     [rsp+180h+pActCtx.lpResourceName], 7Bh ; '{'
0x1800077fa  call    cs:__imp_CreateActCtxA
0x180007800  mov     rbx, rax
0x180007803  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007807  jz      short loc_180007815
0x180007809  mov     rdx, rdi; lpCookie
0x18000780c  mov     rcx, rax; hActCtx
0x18000780f  call    cs:__imp_ActivateActCtx
0x180007815  mov     rax, rbx
0x180007818  mov     rcx, [rbp+80h+var_10]
0x18000781c  xor     rcx, rsp; StackCookie
0x18000781f  call    __security_check_cookie
0x180007824  lea     r11, [rsp+180h+var_s0]
0x18000782c  mov     rbx, [r11+18h]
0x180007830  mov     rdi, [r11+20h]
0x180007834  mov     rsp, r11
0x180007837  pop     rbp
0x180007838  retn
```
