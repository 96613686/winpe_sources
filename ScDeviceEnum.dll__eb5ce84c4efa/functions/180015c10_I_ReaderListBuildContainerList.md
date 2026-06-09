# I_ReaderListBuildContainerList

- ea: `0x180015c10`
- end: `0x1800160bf`
- name: `I_ReaderListBuildContainerList`
- size: `1199`
- prototype: `__int64 __fastcall(__int64 *, const void **)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180017954`

## callees

- `0x180001f26`
- `0x180007178`
- `0x1800071d4`
- `0x180015c10`
- `0x18001cb0c`
- `0x18001cb98`
- `0x18001cc6c`
- `0x18001dd7c`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001609a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fc3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001609a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015edc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015f90`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015c78`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015edc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180015f90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001604b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001604b`
- `CRYPTSP!CryptReleaseContext` at `0x180016083`
- `CRYPTSP!CryptReleaseContext` at `0x180016083`
- `CRYPTSP!CryptGetProvParam` at `0x180015d90`
- `CRYPTSP!CryptGetProvParam` at `0x180015f5e`
- `CRYPTSP!CryptGetProvParam` at `0x180015d90`
- `CRYPTSP!CryptGetProvParam` at `0x180015f5e`
- `CRYPTSP!CryptAcquireContextW` at `0x180015d0a`
- `CRYPTSP!CryptAcquireContextW` at `0x180015d0a`

## pseudocode

```c
__int64 __fastcall I_ReaderListBuildContainerList(__int64 *a1, const void **a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  size_t v6; // rdi
  DWORD LastError; // esi
  wchar_t *v8; // rax
  __int64 v9; // rcx
  WCHAR *v10; // r14
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  int v13; // edx
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  DWORD *p_pdwDataLen; // r14
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  void *v19; // rsp
  void *v20; // rsp
  DWORD *v21; // rax
  DWORD v22; // r12d
  const void *v23; // rax
  __int64 v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  DWORD dwFlags; // r13d
  size_t i; // r15
  BOOL ProvParam; // eax
  size_t v30; // rdx
  _BYTE *v31; // rax
  __int64 v32; // rcx
  _BYTE *v33; // rbx
  void **v34; // r13
  void *v35; // r8
  HANDLE v36; // rcx
  size_t v37; // rbx
  DWORD v38; // eax
  __int64 v40; // [rsp+0h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+30h] [rbp+0h] BYREF
  DWORD v42; // [rsp+34h] [rbp+4h] BYREF
  WCHAR *v43; // [rsp+38h] [rbp+8h] BYREF
  HCRYPTPROV phProv; // [rsp+40h] [rbp+10h] BYREF
  size_t pcchLength; // [rsp+48h] [rbp+18h] BYREF
  const void **v46; // [rsp+50h] [rbp+20h]

  v46 = a2;
  phProv = 0;
  v3 = *a1;
  v4 = -1;
  pdwDataLen = 0;
  v42 = 0;
  pcchLength = 0;
  do
    ++v4;
  while ( *(_WORD *)(v3 + 2 * v4) );
  v6 = v4 + 6;
  LastError = 8;
  v8 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * (v4 + 6));
  v43 = v8;
  v10 = v8;
  if ( !v8 )
  {
    WppTraceIndent(v9, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    }
    goto LABEL_60;
  }
  StringCchPrintfW(v8, v6, L"\\\\.\\%s\\", *a1);
  if ( !CryptAcquireContextW(&phProv, v10, (LPCWSTR)a1[10], *((_DWORD *)a1 + 30), 0xF0000000) )
  {
    LastError = GetLastError();
    WppTraceIndent(v11, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_60;
    }
    v13 = 87;
    goto LABEL_13;
  }
  if ( !CryptGetProvParam(phProv, 2u, 0, &pdwDataLen, 1u) )
  {
    LastError = GetLastError();
    WppTraceIndent(v14, 2);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_60;
    }
    v13 = 88;
LABEL_13:
    WPP_SF_sd(v12[2], v13, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, LastError);
    goto LABEL_60;
  }
  v15 = pdwDataLen;
  p_pdwDataLen = 0;
  if ( !pdwDataLen
    || pdwDataLen > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)pdwDataLen + g_ulAdditionalProbeSize + 8 < pdwDataLen
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_27;
  }
  v17 = v15 + 23;
  if ( v15 + 23 <= v15 + 8 )
    v17 = 0xFFFFFFFFFFFFFF0LL;
  v18 = v17 & 0xFFFFFFFFFFFFFFF0uLL;
  v19 = alloca(v18);
  v20 = alloca(v18);
  p_pdwDataLen = &pdwDataLen;
  if ( &v40 == (__int64 *)-48LL || (pdwDataLen = 1801679955, (p_pdwDataLen = (DWORD *)&v43) == 0) )
  {
LABEL_27:
    v18 = v15 + 8;
    if ( v15 + 8 >= v15 )
    {
      v21 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_pdwDataLen = v21;
      if ( v21 )
      {
        *v21 = 1885431112;
        p_pdwDataLen = v21 + 2;
      }
    }
  }
  if ( !p_pdwDataLen )
  {
    WppTraceIndent(v18, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 89, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    }
    goto LABEL_59;
  }
  v22 = 2 * pdwDataLen + 3;
  v23 = HeapAlloc(hHeap, 8u, v22);
  *a2 = v23;
  if ( !v23 )
  {
    WppTraceIndent(v24, 2);
    v25 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v26 = 90;
LABEL_40:
      WPP_SF_s(v25[2], v26, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    }
    goto LABEL_57;
  }
  dwFlags = 1;
  for ( i = 0; ; i += v37 )
  {
    v42 = pdwDataLen;
    ProvParam = CryptGetProvParam(phProv, 2u, (BYTE *)p_pdwDataLen, &v42, dwFlags);
    dwFlags = 0;
    if ( !ProvParam )
    {
      v38 = GetLastError();
      if ( v38 == 259 )
        v38 = 0;
      LastError = v38;
      goto LABEL_57;
    }
    v30 = v42;
    if ( i + v42 + 1LL > v22 )
      break;
LABEL_46:
    if ( v30 > 0x7FFFFFFF || StringLengthWorkerA((STRSAFE_PCNZCH)p_pdwDataLen, v30, &pcchLength) < 0 )
    {
      LastError = 14;
      goto LABEL_57;
    }
    v37 = ++pcchLength;
    memcpy_0((char *)*v46 + i, p_pdwDataLen, pcchLength);
  }
  v22 *= 2;
  v31 = HeapAlloc(hHeap, 8u, v22);
  v33 = v31;
  if ( v31 )
  {
    v34 = (void **)v46;
    memcpy_0(v31, *v46, i);
    v35 = *v34;
    v36 = hHeap;
    v33[i] = 0;
    HeapFree(v36, 0, v35);
    v30 = v42;
    *v34 = v33;
    dwFlags = 0;
    goto LABEL_46;
  }
  WppTraceIndent(v32, 2);
  v25 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = 91;
    goto LABEL_40;
  }
LABEL_57:
  if ( *(p_pdwDataLen - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
LABEL_59:
  v10 = v43;
LABEL_60:
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  if ( v10 )
    HeapFree(hHeap, 0, v10);
  return LastError;
}

```

## disassembly

```asm
0x180015c10  push    rbp
0x180015c12  push    rbx
0x180015c13  push    rsi
0x180015c14  push    rdi
0x180015c15  push    r12
0x180015c17  push    r13
0x180015c19  push    r14
0x180015c1b  push    r15
0x180015c1d  sub     rsp, 78h
0x180015c21  lea     rbp, [rsp+30h]
0x180015c26  mov     rax, cs:__security_cookie
0x180015c2d  xor     rax, rbp
0x180015c30  mov     [rbp+80h+var_50], rax
0x180015c34  xor     r13d, r13d
0x180015c37  mov     [rbp+80h+var_60], rdx
0x180015c3b  mov     rbx, rcx
0x180015c3e  mov     [rbp+80h+phProv], r13
0x180015c42  mov     rcx, [rcx]
0x180015c45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015c49  mov     [rbp+80h+pdwDataLen], r13d
0x180015c4d  mov     r15, rdx
0x180015c50  mov     [rbp+80h+var_7C], r13d
0x180015c54  mov     [rbp+80h+pcchLength], r13
0x180015c58  inc     rax
0x180015c5b  cmp     [rcx+rax*2], r13w
0x180015c60  jnz     short loc_180015C58
0x180015c62  mov     rcx, cs:hHeap; hHeap
0x180015c69  lea     rdi, [rax+6]
0x180015c6d  mov     esi, 8
0x180015c72  lea     r8, [rdi+rdi]; dwBytes
0x180015c76  mov     edx, esi; dwFlags
0x180015c78  call    cs:__imp_HeapAlloc
0x180015c7e  mov     [rbp+80h+var_78], rax
0x180015c82  mov     r14, rax
0x180015c85  test    rax, rax
0x180015c88  jnz     short loc_180015CDE
0x180015c8a  lea     edi, [rsi-6]
0x180015c8d  mov     edx, edi
0x180015c8f  call    WppTraceIndent
0x180015c94  mov     rcx, cs:WPP_GLOBAL_Control
0x180015c9b  lea     rax, WPP_GLOBAL_Control
0x180015ca2  cmp     rcx, rax
0x180015ca5  jz      loc_180016078
0x180015cab  test    byte ptr [rcx+1Ch], 1
0x180015caf  jz      loc_180016078
0x180015cb5  cmp     [rcx+19h], dil
0x180015cb9  jb      loc_180016078
0x180015cbf  mov     r9, cs:WPP_pszIndent
0x180015cc6  lea     edx, [rsi+4Eh]
0x180015cc9  mov     rcx, [rcx+10h]
0x180015ccd  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015cd4  call    WPP_SF_s
0x180015cd9  jmp     loc_180016078
0x180015cde  mov     r9, [rbx]
0x180015ce1  lea     r8, aS; "\\\\.\\%s\\"
0x180015ce8  mov     rdx, rdi; cchDest
0x180015ceb  mov     rcx, r14; pszDest
0x180015cee  call    StringCchPrintfW
0x180015cf3  mov     r9d, [rbx+78h]; dwProvType
0x180015cf7  lea     rcx, [rbp+80h+phProv]; phProv
0x180015cfb  mov     r8, [rbx+50h]; szProvider
0x180015cff  mov     rdx, r14; szContainer
0x180015d02  mov     [rsp+0B0h+dwFlags], 0F0000000h; dwFlags
0x180015d0a  call    cs:__imp_CryptAcquireContextW
0x180015d10  cmp     eax, 1
0x180015d13  jz      short loc_180015D77
0x180015d15  call    cs:__imp_GetLastError
0x180015d1b  mov     edi, 2
0x180015d20  mov     esi, eax
0x180015d22  mov     edx, edi
0x180015d24  call    WppTraceIndent
0x180015d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d30  lea     rax, WPP_GLOBAL_Control
0x180015d37  cmp     rcx, rax
0x180015d3a  jz      loc_180016078
0x180015d40  test    byte ptr [rcx+1Ch], 1
0x180015d44  jz      loc_180016078
0x180015d4a  cmp     [rcx+19h], dil
0x180015d4e  jb      loc_180016078
0x180015d54  lea     edx, [rdi+55h]
0x180015d57  mov     r9, cs:WPP_pszIndent
0x180015d5e  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015d65  mov     rcx, [rcx+10h]
0x180015d69  mov     [rsp+0B0h+dwFlags], esi
0x180015d6d  call    WPP_SF_sd
0x180015d72  jmp     loc_180016078
0x180015d77  mov     rcx, [rbp+80h+phProv]; hProv
0x180015d7b  lea     r9, [rbp+80h+pdwDataLen]; pdwDataLen
0x180015d7f  xor     r8d, r8d; pbData
0x180015d82  mov     [rsp+0B0h+dwFlags], 1; dwFlags
0x180015d8a  lea     edi, [r8+2]
0x180015d8e  mov     edx, edi; dwParam
0x180015d90  call    cs:__imp_CryptGetProvParam
0x180015d96  cmp     eax, 1
0x180015d99  jz      short loc_180015DDD
0x180015d9b  call    cs:__imp_GetLastError
0x180015da1  mov     edx, edi
0x180015da3  mov     esi, eax
0x180015da5  call    WppTraceIndent
0x180015daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180015db1  lea     rax, WPP_GLOBAL_Control
0x180015db8  cmp     rcx, rax
0x180015dbb  jz      loc_180016078
0x180015dc1  test    byte ptr [rcx+1Ch], 1
0x180015dc5  jz      loc_180016078
0x180015dcb  cmp     [rcx+19h], dil
0x180015dcf  jb      loc_180016078
0x180015dd5  lea     edx, [rdi+56h]
0x180015dd8  jmp     loc_180015D57
0x180015ddd  mov     ebx, [rbp+80h+pdwDataLen]
0x180015de0  mov     r14, r13
0x180015de3  test    rbx, rbx
0x180015de6  jz      short loc_180015E48
0x180015de8  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180015def  ja      short loc_180015E48
0x180015df1  mov     rcx, cs:g_ulAdditionalProbeSize
0x180015df8  add     rcx, rsi
0x180015dfb  add     rcx, rbx
0x180015dfe  cmp     rcx, rbx
0x180015e01  jb      short loc_180015E48
0x180015e03  call    VerifyStackAvailable
0x180015e08  test    eax, eax
0x180015e0a  jz      short loc_180015E48
0x180015e0c  lea     rax, [rbx+8]
0x180015e10  lea     rcx, [rax+0Fh]
0x180015e14  cmp     rcx, rax
0x180015e17  ja      short loc_180015E23
0x180015e19  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180015e23  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180015e27  mov     rax, rcx
0x180015e2a  call    _alloca_probe
0x180015e2f  sub     rsp, rcx
0x180015e32  lea     r14, [rsp+0B0h+pdwDataLen]
0x180015e37  test    r14, r14
0x180015e3a  jz      short loc_180015E48
0x180015e3c  mov     dword ptr [r14], 6B637453h
0x180015e43  add     r14, rsi
0x180015e46  jnz     short loc_180015E6E
0x180015e48  lea     rcx, [rbx+8]
0x180015e4c  cmp     rcx, rbx
0x180015e4f  jb      short loc_180015E6E
0x180015e51  mov     rax, cs:g_pfnAllocate
0x180015e58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e5d  mov     r14, rax
0x180015e60  test    rax, rax
0x180015e63  jz      short loc_180015E6E
0x180015e65  mov     dword ptr [rax], 70616548h
0x180015e6b  add     r14, rsi
0x180015e6e  test    r14, r14
0x180015e71  jnz     short loc_180015EC5
0x180015e73  mov     edx, edi
0x180015e75  call    WppTraceIndent
0x180015e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015e81  lea     rax, WPP_GLOBAL_Control
0x180015e88  cmp     rcx, rax
0x180015e8b  jz      loc_180016074
0x180015e91  test    byte ptr [rcx+1Ch], 1
0x180015e95  jz      loc_180016074
0x180015e9b  cmp     [rcx+19h], dil
0x180015e9f  jb      loc_180016074
0x180015ea5  mov     r9, cs:WPP_pszIndent
0x180015eac  lea     edx, [r14+59h]
0x180015eb0  mov     rcx, [rcx+10h]
0x180015eb4  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015ebb  call    WPP_SF_s
0x180015ec0  jmp     loc_180016074
0x180015ec5  mov     eax, [rbp+80h+pdwDataLen]
0x180015ec8  mov     edx, esi; dwFlags
0x180015eca  mov     rcx, cs:hHeap; hHeap
0x180015ed1  lea     r12d, ds:3[rax*2]
0x180015ed9  mov     r8d, r12d; dwBytes
0x180015edc  call    cs:__imp_HeapAlloc
0x180015ee2  mov     [r15], rax
0x180015ee5  test    rax, rax
0x180015ee8  jnz     short loc_180015F3D
0x180015eea  mov     edx, edi
0x180015eec  call    WppTraceIndent
0x180015ef1  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ef8  lea     rax, WPP_GLOBAL_Control
0x180015eff  cmp     rcx, rax
0x180015f02  jz      loc_18001605C
0x180015f08  test    byte ptr [rcx+1Ch], 1
0x180015f0c  jz      loc_18001605C
0x180015f12  cmp     [rcx+19h], dil
0x180015f16  jb      loc_18001605C
0x180015f1c  mov     edx, 5Ah ; 'Z'
0x180015f21  mov     r9, cs:WPP_pszIndent
0x180015f28  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180015f2f  mov     rcx, [rcx+10h]
0x180015f33  call    WPP_SF_s
0x180015f38  jmp     loc_18001605C
0x180015f3d  mov     r13d, 1
0x180015f43  xor     r15d, r15d
0x180015f46  mov     eax, [rbp+80h+pdwDataLen]
0x180015f49  lea     r9, [rbp+80h+var_7C]; pdwDataLen
0x180015f4d  mov     rcx, [rbp+80h+phProv]; hProv
0x180015f51  mov     r8, r14; pbData
0x180015f54  mov     edx, edi; dwParam
0x180015f56  mov     [rbp+80h+var_7C], eax
0x180015f59  mov     [rsp+0B0h+dwFlags], r13d; dwFlags
0x180015f5e  call    cs:__imp_CryptGetProvParam
0x180015f64  xor     r13d, r13d
0x180015f67  test    eax, eax
0x180015f69  jz      loc_18001604B
0x180015f6f  mov     edx, [rbp+80h+var_7C]
0x180015f72  mov     eax, r12d
0x180015f75  lea     rcx, [rdx+1]
0x180015f79  add     rcx, r15
0x180015f7c  cmp     rcx, rax
0x180015f7f  jbe     short loc_180015FD3
0x180015f81  mov     rcx, cs:hHeap; hHeap
0x180015f88  add     r12d, r12d
0x180015f8b  mov     r8d, r12d; dwBytes
0x180015f8e  mov     edx, esi; dwFlags
0x180015f90  call    cs:__imp_HeapAlloc
0x180015f96  mov     rbx, rax
0x180015f99  test    rax, rax
0x180015f9c  jz      short loc_180016014
0x180015f9e  mov     r13, [rbp+80h+var_60]
0x180015fa2  mov     r8, r15; Size
0x180015fa5  mov     rcx, rax; void *
0x180015fa8  mov     rdx, [r13+0]; Src
0x180015fac  call    memcpy_0
0x180015fb1  mov     r8, [r13+0]; lpMem
0x180015fb5  xor     edx, edx; dwFlags
0x180015fb7  mov     rcx, cs:hHeap; hHeap
0x180015fbe  mov     byte ptr [rbx+r15], 0
0x180015fc3  call    cs:__imp_HeapFree
0x180015fc9  mov     edx, [rbp+80h+var_7C]; cchMax
0x180015fcc  mov     [r13+0], rbx
0x180015fd0  xor     r13d, r13d
0x180015fd3  cmp     rdx, 7FFFFFFFh
0x180015fda  ja      short loc_180016044
0x180015fdc  lea     r8, [rbp+80h+pcchLength]; pcchLength
0x180015fe0  mov     rcx, r14; psz
0x180015fe3  call    StringLengthWorkerA
0x180015fe8  test    eax, eax
0x180015fea  js      short loc_180016044
0x180015fec  mov     rax, [rbp+80h+var_60]
0x180015ff0  mov     rdx, r14; Src
0x180015ff3  mov     rbx, [rbp+80h+pcchLength]
0x180015ff7  inc     rbx
0x180015ffa  mov     r8, rbx; Size
0x180015ffd  mov     [rbp+80h+pcchLength], rbx
0x180016001  mov     rcx, [rax]
0x180016004  add     rcx, r15; void *
0x180016007  call    memcpy_0
0x18001600c  add     r15, rbx
0x18001600f  jmp     loc_180015F46
0x180016014  mov     edx, edi
0x180016016  call    WppTraceIndent
0x18001601b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016022  lea     rax, WPP_GLOBAL_Control
0x180016029  cmp     rcx, rax
0x18001602c  jz      short loc_18001605C
0x18001602e  test    byte ptr [rcx+1Ch], 1
0x180016032  jz      short loc_18001605C
0x180016034  cmp     [rcx+19h], dil
0x180016038  jb      short loc_18001605C
0x18001603a  mov     edx, 5Bh ; '['
0x18001603f  jmp     loc_180015F21
0x180016044  mov     esi, 0Eh
0x180016049  jmp     short loc_18001605C
0x18001604b  call    cs:__imp_GetLastError
0x180016051  cmp     eax, 103h
0x180016056  cmovz   eax, r13d
0x18001605a  mov     esi, eax
0x18001605c  lea     rcx, [r14-8]
0x180016060  cmp     dword ptr [rcx], 70616548h
0x180016066  jnz     short loc_180016074
0x180016068  mov     rax, cs:g_pfnFree
0x18001606f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016074  mov     r14, [rbp+80h+var_78]
0x180016078  mov     rcx, [rbp+80h+phProv]; hProv
0x18001607c  test    rcx, rcx
0x18001607f  jz      short loc_180016089
0x180016081  xor     edx, edx; dwFlags
0x180016083  call    cs:__imp_CryptReleaseContext
0x180016089  test    r14, r14
0x18001608c  jz      short loc_1800160A0
0x18001608e  mov     rcx, cs:hHeap; hHeap
0x180016095  mov     r8, r14; lpMem
0x180016098  xor     edx, edx; dwFlags
0x18001609a  call    cs:__imp_HeapFree
0x1800160a0  mov     eax, esi
0x1800160a2  mov     rcx, [rbp+80h+var_50]
0x1800160a6  xor     rcx, rbp; StackCookie
0x1800160a9  call    __security_check_cookie
0x1800160ae  lea     rsp, [rbp+48h]
0x1800160b2  pop     r15
0x1800160b4  pop     r14
0x1800160b6  pop     r13
0x1800160b8  pop     r12
0x1800160ba  pop     rdi
0x1800160bb  pop     rsi
0x1800160bc  pop     rbx
0x1800160bd  pop     rbp
0x1800160be  retn
```
