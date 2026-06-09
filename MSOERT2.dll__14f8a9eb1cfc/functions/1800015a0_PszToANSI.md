# PszToANSI

- ea: `0x1800015a0`
- end: `0x18000169f`
- name: `PszToANSI`
- size: `255`
- prototype: `CHAR *__fastcall(UINT CodePage, LPCWCH lpWideCharStr)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003110`
- `0x1800061d0`
- `0x18000a9f0`

## callees

- `0x1800015a0`
- `0x180014010`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1800015fb`
- `KERNEL32!WideCharToMultiByte` at `0x180001654`
- `KERNEL32!WideCharToMultiByte` at `0x1800015fb`
- `KERNEL32!WideCharToMultiByte` at `0x180001654`

## pseudocode

```c
CHAR *__fastcall PszToANSI(UINT CodePage, LPCWCH lpWideCharStr)
{
  __int64 v4; // rax
  int v6; // ebp
  int v7; // eax
  CHAR *lpMultiByteStr; // rdi
  int cbMultiByte; // esi

  if ( !lpWideCharStr )
    return 0;
  v4 = -1;
  while ( lpWideCharStr[++v4] != 0 )
    ;
  v6 = v4 + 1;
  v7 = WideCharToMultiByte(CodePage, 0, lpWideCharStr, v4 + 1, 0, 0, 0, 0);
  if ( !v7 )
    return 0;
  lpMultiByteStr = 0;
  cbMultiByte = v7 + 1;
  if ( v7 != -1 )
    lpMultiByteStr = (CHAR *)((__int64 (__fastcall *)(LPMALLOC, _QWORD))g_pMalloc->lpVtbl->Alloc)(
                               g_pMalloc,
                               (unsigned int)(v7 + 2));
  if ( !lpMultiByteStr || WideCharToMultiByte(CodePage, 0, lpWideCharStr, v6, lpMultiByteStr, cbMultiByte, 0, 0) )
    return lpMultiByteStr;
  ((void (__fastcall *)(LPMALLOC, CHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, lpMultiByteStr);
  return 0;
}

```

## disassembly

```asm
0x1800015a0  mov     [rsp+arg_10], rbx
0x1800015a5  push    rdi
0x1800015a6  push    r14
0x1800015a8  push    r15
0x1800015aa  sub     rsp, 40h
0x1800015ae  xor     r15d, r15d
0x1800015b1  mov     rbx, rdx
0x1800015b4  mov     r14d, ecx
0x1800015b7  test    rdx, rdx
0x1800015ba  jz      loc_18000169A
0x1800015c0  mov     [rsp+58h+arg_0], rbp
0x1800015c5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800015cc  nop     dword ptr [rax+00h]
0x1800015d0  cmp     [rdx+rax*2+2], r15w
0x1800015d6  lea     rax, [rax+1]
0x1800015da  jnz     short loc_1800015D0
0x1800015dc  mov     [rsp+58h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800015e1  lea     ebp, [rax+1]
0x1800015e4  mov     [rsp+58h+lpDefaultChar], r15; lpDefaultChar
0x1800015e9  mov     r9d, ebp; cchWideChar
0x1800015ec  mov     [rsp+58h+cbMultiByte], r15d; cbMultiByte
0x1800015f1  mov     r8, rbx; lpWideCharStr
0x1800015f4  xor     edx, edx; dwFlags
0x1800015f6  mov     [rsp+58h+lpMultiByteStr], r15; lpMultiByteStr
0x1800015fb  call    cs:__imp_WideCharToMultiByte
0x180001601  test    eax, eax
0x180001603  jz      loc_180001695
0x180001609  mov     [rsp+58h+arg_8], rsi
0x18000160e  mov     rdi, r15
0x180001611  lea     esi, [rax+1]
0x180001614  test    esi, esi
0x180001616  jz      short loc_180001631
0x180001618  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18000161f  lea     edx, [rsi+1]
0x180001622  mov     r8, [rcx]
0x180001625  mov     rax, [r8+18h]
0x180001629  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000162e  mov     rdi, rax
0x180001631  test    rdi, rdi
0x180001634  jz      short loc_180001690
0x180001636  mov     [rsp+58h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x18000163b  mov     r9d, ebp; cchWideChar
0x18000163e  mov     [rsp+58h+lpDefaultChar], r15; lpDefaultChar
0x180001643  mov     r8, rbx; lpWideCharStr
0x180001646  mov     [rsp+58h+cbMultiByte], esi; cbMultiByte
0x18000164a  xor     edx, edx; dwFlags
0x18000164c  mov     ecx, r14d; CodePage
0x18000164f  mov     [rsp+58h+lpMultiByteStr], rdi; lpMultiByteStr
0x180001654  call    cs:__imp_WideCharToMultiByte
0x18000165a  test    eax, eax
0x18000165c  jnz     short loc_180001690
0x18000165e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180001665  mov     rdx, rdi
0x180001668  mov     rax, [rcx]
0x18000166b  mov     rax, [rax+28h]
0x18000166f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001674  mov     rax, r15
0x180001677  mov     rsi, [rsp+58h+arg_8]
0x18000167c  mov     rbp, [rsp+58h+arg_0]
0x180001681  mov     rbx, [rsp+58h+arg_10]
0x180001686  add     rsp, 40h
0x18000168a  pop     r15
0x18000168c  pop     r14
0x18000168e  pop     rdi
0x18000168f  retn
0x180001690  mov     rax, rdi
0x180001693  jmp     short loc_180001677
0x180001695  mov     rax, r15
0x180001698  jmp     short loc_18000167C
0x18000169a  mov     rax, r15
0x18000169d  jmp     short loc_180001681
```
