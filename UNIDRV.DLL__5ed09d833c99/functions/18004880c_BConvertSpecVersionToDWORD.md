# BConvertSpecVersionToDWORD

- ea: `0x18004880c`
- end: `0x180048a9d`
- name: `BConvertSpecVersionToDWORD`
- size: `657`
- prototype: `__int64 __fastcall(const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180049418`

## callees

- `0x180007150`
- `0x18000af00`
- `0x18000bf20`
- `0x180024c98`
- `0x180033e78`
- `0x180033f3c`
- `0x180040318`
- `0x18004880c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800489a6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800489ca`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800489a6`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800489ca`
- `KERNEL32!LocalFree` at `0x180048a4a`
- `KERNEL32!LocalFree` at `0x180048a4a`
- `KERNEL32!LocalAlloc` at `0x180048975`
- `KERNEL32!LocalAlloc` at `0x180048975`

## string_xrefs

- `0x180048a72`: `Fatal: unable to alloc memory for pwDLLQualifiedName: %d WCHARs.`

## pseudocode

```c
__int64 __fastcall BConvertSpecVersionToDWORD(const wchar_t *a1, __int64 a2)
{
  unsigned int *v2; // r15
  unsigned int v5; // esi
  unsigned int v6; // edi
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
  int v22; // [rsp+30h] [rbp-38h] BYREF
  __int64 v23; // [rsp+38h] [rbp-30h] BYREF
  int v24; // [rsp+40h] [rbp-28h]
  int v25; // [rsp+44h] [rbp-24h]
  _OWORD v26[2]; // [rsp+48h] [rbp-20h] BYREF
  wchar_t *Str; // [rsp+B8h] [rbp+50h] BYREF
  unsigned int v29; // [rsp+C0h] [rbp+58h] BYREF
  unsigned int v30; // [rsp+C8h] [rbp+60h] BYREF

  v2 = *(unsigned int **)(a2 + 24);
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
    if ( (unsigned int)BdelimitToken((__int64)&v23, (__int64)".", (__int64)v26, &v22)
      && (unsigned int)BparseInteger((__int64)v26, &v29, 1)
      && (unsigned int)BparseInteger((__int64)&v23, &v30, 1) )
    {
      v6 = v29;
      v7 = v30;
    }
    else
    {
      WriteDbgTraceErrorGpd(
        (__int64)"BConvertSpecVersionToDWORD",
        "BConvertSpecVersionToDWORD: syntax error in *GPDSpecVersion value. unknown version.");
    }
  }
  else
  {
    WriteDbgTraceErrorGpd((__int64)"BConvertSpecVersionToDWORD", "Missing required keyword: *GPDSpecVersion.");
  }
  *(_DWORD *)(a2 + 776) = v7 | (v6 << 16);
  if ( !(unsigned int)BReadDataInGlobalNode(v2 + 26, &Str, a2) )
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
          BwriteToHeap(&Str, &qword_18007F1D0, 2u, 1u, a2);
        else
          v5 = 0;
      }
      LocalFree(v17);
      return v5;
    }
  }
  WriteDbgTraceErrorGpd(
    (__int64)"BConvertSpecVersionToDWORD",
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
0x18004880c  mov     [rsp-40h+pszSrc], rcx
0x180048811  push    rbp
0x180048812  push    rbx
0x180048813  push    rsi
0x180048814  push    rdi
0x180048815  push    r12
0x180048817  push    r13
0x180048819  push    r14
0x18004881b  push    r15
0x18004881d  mov     rbp, rsp
0x180048820  sub     rsp, 68h
0x180048824  mov     r15, [rdx+18h]
0x180048828  xor     r13d, r13d
0x18004882b  mov     rbx, rdx
0x18004882e  mov     dword ptr [rbp+Str], r13d
0x180048832  mov     r12, rcx
0x180048835  mov     [rbp+var_24], r13d
0x180048839  mov     esi, 1
0x18004883e  mov     [rbp+arg_18], r13d
0x180048842  mov     r8, rdx
0x180048845  mov     [rbp+arg_10], esi
0x180048848  xorps   xmm0, xmm0
0x18004884b  lea     rdx, [rbp+Str]
0x18004884f  mov     rcx, r15
0x180048852  mov     edi, esi
0x180048854  movups  [rbp+var_20], xmm0
0x180048858  mov     r14d, r13d
0x18004885b  call    BReadDataInGlobalNode
0x180048860  test    eax, eax
0x180048862  jnz     short loc_18004886D
0x180048864  lea     rdx, aMissingRequire; "Missing required keyword: *GPDSpecVersi"...
0x18004886b  jmp     short loc_1800488DE
0x18004886d  mov     rdx, [rbx]
0x180048870  lea     r9, [rbp+var_38]
0x180048874  mov     ecx, dword ptr [rbp+Str]
0x180048877  lea     r8, [rbp+var_20]
0x18004887b  mov     eax, [rcx+rdx]
0x18004887e  mov     [rbp+var_28], eax
0x180048881  mov     eax, [rcx+rdx+4]
0x180048885  lea     rcx, [rbp+var_30]
0x180048889  add     rax, rdx
0x18004888c  lea     rdx, pszSrc; "."
0x180048893  mov     [rbp+var_30], rax
0x180048897  call    BdelimitToken
0x18004889c  test    eax, eax
0x18004889e  jz      short loc_1800488D7
0x1800488a0  mov     r9, rbx
0x1800488a3  lea     rdx, [rbp+arg_10]
0x1800488a7  mov     r8d, esi
0x1800488aa  lea     rcx, [rbp+var_20]
0x1800488ae  call    BparseInteger
0x1800488b3  test    eax, eax
0x1800488b5  jz      short loc_1800488D7
0x1800488b7  mov     r9, rbx
0x1800488ba  lea     rdx, [rbp+arg_18]
0x1800488be  mov     r8d, esi
0x1800488c1  lea     rcx, [rbp+var_30]
0x1800488c5  call    BparseInteger
0x1800488ca  test    eax, eax
0x1800488cc  jz      short loc_1800488D7
0x1800488ce  mov     edi, [rbp+arg_10]
0x1800488d1  mov     r14d, [rbp+arg_18]
0x1800488d5  jmp     short loc_1800488EA
0x1800488d7  lea     rdx, aBconvertspecve_0; "BConvertSpecVersionToDWORD: syntax erro"...
0x1800488de  lea     rcx, aBconvertspecve; "BConvertSpecVersionToDWORD"
0x1800488e5  call    WriteDbgTraceErrorGpd
0x1800488ea  movzx   eax, r14w
0x1800488ee  lea     rcx, [r15+68h]
0x1800488f2  shl     edi, 10h
0x1800488f5  lea     rdx, [rbp+Str]
0x1800488f9  or      edi, eax
0x1800488fb  mov     r8, rbx
0x1800488fe  mov     [rbx+308h], edi
0x180048904  call    BReadDataInGlobalNode
0x180048909  test    eax, eax
0x18004890b  jz      loc_180048A56
0x180048911  mov     rcx, [rbx]
0x180048914  or      r15, 0FFFFFFFFFFFFFFFFh
0x180048918  mov     r13d, dword ptr [rbp+Str]
0x18004891c  mov     eax, [rcx+r13+4]
0x180048921  add     rax, rcx
0x180048924  mov     rcx, r15
0x180048927  mov     [rbp+Str], rax
0x18004892b  xor     edx, edx
0x18004892d  inc     rcx
0x180048930  cmp     [rax+rcx*2], dx
0x180048934  jnz     short loc_18004892D
0x180048936  mov     rax, r15
0x180048939  inc     rax
0x18004893c  cmp     [r12+rax*2], dx
0x180048941  jnz     short loc_180048939
0x180048943  lea     edx, [rcx+rax]
0x180048946  cmp     edx, eax
0x180048948  jb      loc_180048A6A
0x18004894e  lea     edi, [rdx+1]
0x180048951  cmp     edi, edx
0x180048953  jb      loc_180048A6A
0x180048959  lea     rcx, [rdi+rdi]
0x18004895d  mov     r12d, edi
0x180048960  mov     eax, 0FFFFFFFFh
0x180048965  cmp     rcx, rax
0x180048968  ja      loc_180048A6F
0x18004896e  mov     edx, ecx; uBytes
0x180048970  mov     ecx, 40h ; '@'; uFlags
0x180048975  call    cs:__imp_LocalAlloc
0x18004897c  nop     dword ptr [rax+rax+00h]
0x180048981  mov     r14, rax
0x180048984  test    rax, rax
0x180048987  jz      loc_180048A6F
0x18004898d  mov     r8, [rbp+pszSrc]; pszSrc
0x180048991  mov     edx, r12d; cchDest
0x180048994  mov     rcx, rax; pszDest
0x180048997  call    StringCchCopyW
0x18004899c  mov     edi, 5Ch ; '\'
0x1800489a1  mov     rcx, r14; Str
0x1800489a4  mov     edx, edi; Ch
0x1800489a6  call    cs:__imp_wcsrchr
0x1800489ad  nop     dword ptr [rax+rax+00h]
0x1800489b2  mov     rcx, rax
0x1800489b5  xor     eax, eax
0x1800489b7  test    rcx, rcx
0x1800489ba  jz      loc_180048A47
0x1800489c0  mov     [rcx+2], ax
0x1800489c4  mov     edx, edi; Ch
0x1800489c6  mov     rcx, [rbp+Str]; Str
0x1800489ca  call    cs:__imp_wcsrchr
0x1800489d1  nop     dword ptr [rax+rax+00h]
0x1800489d6  mov     edx, r12d; cchDest
0x1800489d9  mov     rcx, r14; pszDest
0x1800489dc  test    rax, rax
0x1800489df  lea     r8, [rax+2]
0x1800489e3  cmovz   r8, [rbp+Str]; pszSrc
0x1800489e8  call    StringCchCatW
0x1800489ed  xor     edi, edi
0x1800489ef  inc     r15
0x1800489f2  cmp     [r14+r15*2], di
0x1800489f7  jnz     short loc_1800489EF
0x1800489f9  mov     rax, [rbx]
0x1800489fc  lea     r8d, [r15+r15]
0x180048a00  mov     r9d, 2
0x180048a06  mov     [rsp+68h+var_48], rbx
0x180048a0b  mov     rdx, r14
0x180048a0e  mov     [rax+r13], r8d
0x180048a12  mov     rcx, [rbx]
0x180048a15  add     rcx, 4
0x180048a19  add     rcx, r13
0x180048a1c  call    BwriteToHeap
0x180048a21  test    eax, eax
0x180048a23  jz      short loc_180048A45
0x180048a25  mov     r9d, esi
0x180048a28  mov     [rsp+68h+var_48], rbx
0x180048a2d  mov     r8d, 2
0x180048a33  lea     rdx, qword_18007F1D0
0x180048a3a  lea     rcx, [rbp+Str]
0x180048a3e  call    BwriteToHeap
0x180048a43  jmp     short loc_180048A47
0x180048a45  mov     esi, edi
0x180048a47  mov     rcx, r14; hMem
0x180048a4a  call    cs:__imp_LocalFree
0x180048a51  nop     dword ptr [rax+rax+00h]
0x180048a56  mov     eax, esi
0x180048a58  add     rsp, 68h
0x180048a5c  pop     r15
0x180048a5e  pop     r14
0x180048a60  pop     r13
0x180048a62  pop     r12
0x180048a64  pop     rdi
0x180048a65  pop     rsi
0x180048a66  pop     rbx
0x180048a67  pop     rbp
0x180048a68  retn
0x180048a6a  mov     edi, 0FFFFFFFFh
0x180048a6f  mov     r8d, edi
0x180048a72  lea     rdx, aFatalUnableToA_1; "Fatal: unable to alloc memory for pwDLL"...
0x180048a79  lea     rcx, aBconvertspecve; "BConvertSpecVersionToDWORD"
0x180048a80  call    WriteDbgTraceErrorGpd
0x180048a85  xor     eax, eax
0x180048a87  mov     dword ptr [rbx+8B0h], 2
0x180048a91  mov     dword ptr [rbx+8ACh], 3
0x180048a9b  jmp     short loc_180048A58
```
