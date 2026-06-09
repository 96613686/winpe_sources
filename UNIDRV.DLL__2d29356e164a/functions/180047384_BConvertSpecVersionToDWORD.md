# BConvertSpecVersionToDWORD

- ea: `0x180047384`
- end: `0x1800475fc`
- name: `BConvertSpecVersionToDWORD`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180047f54`

## callees

- `0x180007220`
- `0x18000aef4`
- `0x18000bf30`
- `0x180024718`
- `0x180033504`
- `0x1800335c8`
- `0x18003f288`
- `0x180047384`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047518`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047536`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047518`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047536`
- `KERNEL32!LocalFree` at `0x1800475b0`
- `KERNEL32!LocalFree` at `0x1800475b0`
- `KERNEL32!LocalAlloc` at `0x1800474ed`
- `KERNEL32!LocalAlloc` at `0x1800474ed`

## string_xrefs

- `0x1800475d1`: `Fatal: unable to alloc memory for pwDLLQualifiedName: %d WCHARs.`

## pseudocode

```c
__int64 __fastcall BConvertSpecVersionToDWORD(const wchar_t *a1, __int64 a2)
{
  __int64 v2; // r15
  unsigned int v5; // esi
  int v6; // edi
  unsigned __int16 v7; // r14
  __int64 v8; // rdx
  __int64 v9; // r15
  __int64 v10; // r13
  wchar_t *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned int v14; // edx
  __int64 v15; // rdi
  wchar_t *v16; // rax
  wchar_t *v17; // r14
  wchar_t *v18; // rcx
  wchar_t *v19; // rax
  wchar_t *v20; // r8
  __int64 result; // rax
  _BYTE v22[8]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v23; // [rsp+38h] [rbp-30h] BYREF
  int v24; // [rsp+40h] [rbp-28h]
  int v25; // [rsp+44h] [rbp-24h]
  _OWORD v26[2]; // [rsp+48h] [rbp-20h] BYREF
  wchar_t *Str; // [rsp+B8h] [rbp+50h] BYREF
  int v29; // [rsp+C0h] [rbp+58h] BYREF
  int v30; // [rsp+C8h] [rbp+60h] BYREF

  v2 = *(_QWORD *)(a2 + 24);
  LODWORD(Str) = 0;
  v25 = 0;
  v5 = 1;
  v30 = 0;
  v29 = 1;
  v6 = 1;
  v26[0] = 0;
  v7 = 0;
  if ( (unsigned int)BReadDataInGlobalNode(v2, &Str, a2) )
  {
    v8 = *(_QWORD *)a2;
    v24 = *(_DWORD *)((unsigned int)Str + *(_QWORD *)a2);
    v23 = v8 + *(unsigned int *)((unsigned int)Str + v8 + 4);
    if ( (unsigned int)BdelimitToken(&v23, ".", v26, v22)
      && (unsigned int)BparseInteger(v26, &v29, 1, a2)
      && (unsigned int)BparseInteger(&v23, &v30, 1, a2) )
    {
      v6 = v29;
      v7 = v30;
    }
    else
    {
      WriteDbgTraceErrorGpd(
        "BConvertSpecVersionToDWORD",
        "BConvertSpecVersionToDWORD: syntax error in *GPDSpecVersion value. unknown version.");
    }
  }
  else
  {
    WriteDbgTraceErrorGpd("BConvertSpecVersionToDWORD", "Missing required keyword: *GPDSpecVersion.");
  }
  *(_DWORD *)(a2 + 776) = v7 | (v6 << 16);
  if ( !(unsigned int)BReadDataInGlobalNode(v2 + 104, &Str, a2) )
    return v5;
  v9 = -1;
  v10 = (unsigned int)Str;
  v11 = (wchar_t *)(*(_QWORD *)a2 + *(unsigned int *)(*(_QWORD *)a2 + (unsigned int)Str + 4LL));
  v12 = -1;
  Str = v11;
  do
    ++v12;
  while ( v11[v12] );
  v13 = -1;
  do
    ++v13;
  while ( a1[v13] );
  v14 = v12 + v13;
  if ( (int)v12 + (int)v13 < (unsigned int)v13 || (v15 = v14 + 1, (unsigned int)v15 < v14) )
  {
    LODWORD(v15) = -1;
  }
  else if ( (unsigned __int64)(2 * v15) <= 0xFFFFFFFF )
  {
    v16 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)(2 * v15));
    v17 = v16;
    if ( v16 )
    {
      StringCchCopyW(v16, (unsigned int)v15, a1);
      v18 = wcsrchr(v17, 0x5Cu);
      if ( v18 )
      {
        v18[1] = 0;
        v19 = wcsrchr(Str, 0x5Cu);
        v20 = v19 + 1;
        if ( !v19 )
          v20 = Str;
        StringCchCatW(v17, (unsigned int)v15, v20);
        do
          ++v9;
        while ( v17[v9] );
        *(_DWORD *)(*(_QWORD *)a2 + v10) = 2 * v9;
        if ( (unsigned int)BwriteToHeap((_DWORD *)(v10 + *(_QWORD *)a2 + 4LL), v17, 2 * (int)v9, 2u, a2) )
          BwriteToHeap(&Str, &qword_18007D1D0, 2u, 1u, a2);
        else
          v5 = 0;
      }
      LocalFree(v17);
      return v5;
    }
  }
  WriteDbgTraceErrorGpd(
    "BConvertSpecVersionToDWORD",
    "Fatal: unable to alloc memory for pwDLLQualifiedName: %d WCHARs.",
    v15);
  result = 0;
  *(_DWORD *)(a2 + 2224) = 2;
  *(_DWORD *)(a2 + 2220) = 3;
  return result;
}

```

## disassembly

```asm
0x180047384  mov     [rsp-40h+pszSrc], rcx
0x180047389  push    rbp
0x18004738a  push    rbx
0x18004738b  push    rsi
0x18004738c  push    rdi
0x18004738d  push    r12
0x18004738f  push    r13
0x180047391  push    r14
0x180047393  push    r15
0x180047395  mov     rbp, rsp
0x180047398  sub     rsp, 68h
0x18004739c  mov     r15, [rdx+18h]
0x1800473a0  xor     r13d, r13d
0x1800473a3  mov     rbx, rdx
0x1800473a6  mov     dword ptr [rbp+Str], r13d
0x1800473aa  mov     r12, rcx
0x1800473ad  mov     [rbp+var_24], r13d
0x1800473b1  mov     esi, 1
0x1800473b6  mov     [rbp+arg_18], r13d
0x1800473ba  mov     r8, rdx
0x1800473bd  mov     [rbp+arg_10], esi
0x1800473c0  xorps   xmm0, xmm0
0x1800473c3  lea     rdx, [rbp+Str]
0x1800473c7  mov     rcx, r15
0x1800473ca  mov     edi, esi
0x1800473cc  movups  [rbp+var_20], xmm0
0x1800473d0  mov     r14d, r13d
0x1800473d3  call    BReadDataInGlobalNode
0x1800473d8  test    eax, eax
0x1800473da  jnz     short loc_1800473E5
0x1800473dc  lea     rdx, aMissingRequire; "Missing required keyword: *GPDSpecVersi"...
0x1800473e3  jmp     short loc_180047456
0x1800473e5  mov     rdx, [rbx]
0x1800473e8  lea     r9, [rbp+var_38]
0x1800473ec  mov     ecx, dword ptr [rbp+Str]
0x1800473ef  lea     r8, [rbp+var_20]
0x1800473f3  mov     eax, [rcx+rdx]
0x1800473f6  mov     [rbp+var_28], eax
0x1800473f9  mov     eax, [rcx+rdx+4]
0x1800473fd  lea     rcx, [rbp+var_30]
0x180047401  add     rax, rdx
0x180047404  lea     rdx, pszSrc; "."
0x18004740b  mov     [rbp+var_30], rax
0x18004740f  call    BdelimitToken
0x180047414  test    eax, eax
0x180047416  jz      short loc_18004744F
0x180047418  mov     r9, rbx
0x18004741b  lea     rdx, [rbp+arg_10]
0x18004741f  mov     r8d, esi
0x180047422  lea     rcx, [rbp+var_20]
0x180047426  call    BparseInteger
0x18004742b  test    eax, eax
0x18004742d  jz      short loc_18004744F
0x18004742f  mov     r9, rbx
0x180047432  lea     rdx, [rbp+arg_18]
0x180047436  mov     r8d, esi
0x180047439  lea     rcx, [rbp+var_30]
0x18004743d  call    BparseInteger
0x180047442  test    eax, eax
0x180047444  jz      short loc_18004744F
0x180047446  mov     edi, [rbp+arg_10]
0x180047449  mov     r14d, [rbp+arg_18]
0x18004744d  jmp     short loc_180047462
0x18004744f  lea     rdx, aBconvertspecve_0; "BConvertSpecVersionToDWORD: syntax erro"...
0x180047456  lea     rcx, aBconvertspecve; "BConvertSpecVersionToDWORD"
0x18004745d  call    WriteDbgTraceErrorGpd
0x180047462  movzx   eax, r14w
0x180047466  lea     rcx, [r15+68h]
0x18004746a  shl     edi, 10h
0x18004746d  lea     rdx, [rbp+Str]
0x180047471  or      edi, eax
0x180047473  mov     r8, rbx
0x180047476  mov     [rbx+308h], edi
0x18004747c  call    BReadDataInGlobalNode
0x180047481  test    eax, eax
0x180047483  jz      loc_1800475B6
0x180047489  mov     rcx, [rbx]
0x18004748c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180047490  mov     r13d, dword ptr [rbp+Str]
0x180047494  mov     eax, [rcx+r13+4]
0x180047499  add     rax, rcx
0x18004749c  mov     rcx, r15
0x18004749f  mov     [rbp+Str], rax
0x1800474a3  xor     edx, edx
0x1800474a5  inc     rcx
0x1800474a8  cmp     [rax+rcx*2], dx
0x1800474ac  jnz     short loc_1800474A5
0x1800474ae  mov     rax, r15
0x1800474b1  inc     rax
0x1800474b4  cmp     [r12+rax*2], dx
0x1800474b9  jnz     short loc_1800474B1
0x1800474bb  lea     edx, [rcx+rax]
0x1800474be  cmp     edx, eax
0x1800474c0  jb      loc_1800475C9
0x1800474c6  lea     edi, [rdx+1]
0x1800474c9  cmp     edi, edx
0x1800474cb  jb      loc_1800475C9
0x1800474d1  lea     rcx, [rdi+rdi]
0x1800474d5  mov     r12d, edi
0x1800474d8  mov     eax, 0FFFFFFFFh
0x1800474dd  cmp     rcx, rax
0x1800474e0  ja      loc_1800475CE
0x1800474e6  mov     edx, ecx; uBytes
0x1800474e8  mov     ecx, 40h ; '@'; uFlags
0x1800474ed  call    cs:__imp_LocalAlloc
0x1800474f3  mov     r14, rax
0x1800474f6  test    rax, rax
0x1800474f9  jz      loc_1800475CE
0x1800474ff  mov     r8, [rbp+pszSrc]; pszSrc
0x180047503  mov     edx, r12d; cchDest
0x180047506  mov     rcx, rax; pszDest
0x180047509  call    StringCchCopyW
0x18004750e  mov     edi, 5Ch ; '\'
0x180047513  mov     rcx, r14; Str
0x180047516  mov     edx, edi; Ch
0x180047518  call    cs:__imp_wcsrchr
0x18004751e  mov     rcx, rax
0x180047521  xor     eax, eax
0x180047523  test    rcx, rcx
0x180047526  jz      loc_1800475AD
0x18004752c  mov     [rcx+2], ax
0x180047530  mov     edx, edi; Ch
0x180047532  mov     rcx, [rbp+Str]; Str
0x180047536  call    cs:__imp_wcsrchr
0x18004753c  mov     edx, r12d; cchDest
0x18004753f  mov     rcx, r14; pszDest
0x180047542  test    rax, rax
0x180047545  lea     r8, [rax+2]
0x180047549  cmovz   r8, [rbp+Str]; pszSrc
0x18004754e  call    StringCchCatW
0x180047553  xor     edi, edi
0x180047555  inc     r15
0x180047558  cmp     [r14+r15*2], di
0x18004755d  jnz     short loc_180047555
0x18004755f  mov     rax, [rbx]
0x180047562  lea     r8d, [r15+r15]
0x180047566  mov     r9d, 2
0x18004756c  mov     [rsp+68h+var_48], rbx
0x180047571  mov     rdx, r14
0x180047574  mov     [rax+r13], r8d
0x180047578  mov     rcx, [rbx]
0x18004757b  add     rcx, 4
0x18004757f  add     rcx, r13
0x180047582  call    BwriteToHeap
0x180047587  test    eax, eax
0x180047589  jz      short loc_1800475AB
0x18004758b  mov     r9d, esi
0x18004758e  mov     [rsp+68h+var_48], rbx
0x180047593  mov     r8d, 2
0x180047599  lea     rdx, qword_18007D1D0
0x1800475a0  lea     rcx, [rbp+Str]
0x1800475a4  call    BwriteToHeap
0x1800475a9  jmp     short loc_1800475AD
0x1800475ab  mov     esi, edi
0x1800475ad  mov     rcx, r14; hMem
0x1800475b0  call    cs:__imp_LocalFree
0x1800475b6  mov     eax, esi
0x1800475b8  add     rsp, 68h
0x1800475bc  pop     r15
0x1800475be  pop     r14
0x1800475c0  pop     r13
0x1800475c2  pop     r12
0x1800475c4  pop     rdi
0x1800475c5  pop     rsi
0x1800475c6  pop     rbx
0x1800475c7  pop     rbp
0x1800475c8  retn
0x1800475c9  mov     edi, 0FFFFFFFFh
0x1800475ce  mov     r8d, edi
0x1800475d1  lea     rdx, aFatalUnableToA_1; "Fatal: unable to alloc memory for pwDLL"...
0x1800475d8  lea     rcx, aBconvertspecve; "BConvertSpecVersionToDWORD"
0x1800475df  call    WriteDbgTraceErrorGpd
0x1800475e4  xor     eax, eax
0x1800475e6  mov     dword ptr [rbx+8B0h], 2
0x1800475f0  mov     dword ptr [rbx+8ACh], 3
0x1800475fa  jmp     short loc_1800475B8
```
