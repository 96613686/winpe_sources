# DeviceCensusMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x1800108d0`
- end: `0x180011584`
- name: `?DeviceCensusMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `3252`
- prototype: `__int64 __usercall@<rax>(AppCompatUtility *this@<rcx>, void *@<rdx>, struct _DB *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000dfd8`
- `0x18000e0e4`
- `0x1800108d0`
- `0x18003f0b0`
- `0x18003fa7c`
- `0x18003ffb4`
- `0x180040148`
- `0x180040e64`
- `0x1800425fc`
- `0x1800543c0`
- `0x180065150`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800114d4`
- `KERNEL32!LocalFree` at `0x1800114d4`
- `KERNEL32!GetLastError` at `0x180011444`
- `KERNEL32!GetLastError` at `0x180011444`
- `SHLWAPI!StrToInt64ExW` at `0x180010f44`
- `SHLWAPI!StrToInt64ExW` at `0x1800112f4`
- `SHLWAPI!StrToInt64ExW` at `0x180010f44`
- `SHLWAPI!StrToInt64ExW` at `0x1800112f4`
- `SHELL32!CommandLineToArgvW` at `0x180010b15`
- `SHELL32!CommandLineToArgvW` at `0x180010b15`

## string_xrefs

- `0x18001152b`: `CommandLine is null/empty`
- `0x18001096c`: `Enter DeviceCensusMatchingPlugin`
- `0x180010977`: `DeviceCensusMatchingPlugin`
- `0x1800114b0`: `DeviceCensusMatchingPlugin`
- `0x1800114f9`: `DeviceCensusMatchingPlugin`
- `0x18001099f`: `DeviceCensusMatchingPlugin `
- `0x180011457`: `CommandLineToArgvW failed, code:%d;  %ws; numArgs=%d`
- `0x180011511`: `DeviceCensusMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall DeviceCensusMatchingPlugin(
        AppCompatUtility *this,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *pszSrc,
        void *a7)
{
  AppCompatUtility *v7; // rbx
  unsigned int v8; // r9d
  unsigned int v9; // r9d
  LPWSTR *v11; // rax
  LPWSTR *v12; // r13
  LPWSTR v13; // r9
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // rdx
  void **v16; // rdi
  __int64 v17; // rbx
  LPWSTR v18; // r9
  unsigned __int64 v19; // rdx
  wchar_t **v20; // rdi
  __int64 v21; // rbx
  LPWSTR v22; // r9
  unsigned __int64 v23; // rdx
  PCWSTR *v24; // rdi
  __int64 v25; // rbx
  LPWSTR v26; // r9
  wchar_t **v27; // rdi
  wchar_t **v28; // r8
  PCWSTR *v29; // rdx
  wchar_t **v30; // rcx
  void **v31; // rax
  unsigned __int64 v32; // rbx
  const wchar_t *v33; // rcx
  size_t v34; // r8
  const unsigned __int16 *v35; // rdx
  unsigned __int64 v36; // rbx
  const wchar_t *v37; // rcx
  size_t v38; // r8
  wchar_t *v39; // rcx
  wchar_t **v40; // rax
  unsigned __int64 v41; // rbx
  const wchar_t *v42; // rcx
  size_t v43; // r8
  const WCHAR *v44; // rcx
  unsigned __int64 v45; // rbx
  const wchar_t *v46; // rcx
  size_t v47; // r8
  unsigned __int64 v48; // rdi
  const wchar_t *v49; // rcx
  size_t v50; // r8
  unsigned __int64 v51; // rdi
  const wchar_t *v52; // rcx
  size_t v53; // r8
  wchar_t **v54; // rax
  __int64 v55; // rax
  int CtacClientAttribute; // ebx
  PCWSTR *v57; // rax
  unsigned __int64 v58; // rbx
  const wchar_t *v59; // rcx
  size_t v60; // r8
  int v61; // eax
  unsigned __int64 v62; // rbx
  const wchar_t *v63; // rcx
  size_t v64; // r8
  const WCHAR *v65; // rcx
  wchar_t **v66; // rax
  DWORD LastError; // [rsp+20h] [rbp-588h]
  int v68; // [rsp+30h] [rbp-578h]
  int pNumArgs; // [rsp+40h] [rbp-568h] BYREF
  AppCompatUtility *v70; // [rsp+48h] [rbp-560h]
  LONGLONG v71; // [rsp+50h] [rbp-558h] BYREF
  LONGLONG pllRet; // [rsp+58h] [rbp-550h] BYREF
  LPWSTR *v73; // [rsp+60h] [rbp-548h]
  AppCompatUtility *v74; // [rsp+68h] [rbp-540h]
  const unsigned __int16 *v75; // [rsp+70h] [rbp-538h]
  __int128 v76; // [rsp+78h] [rbp-530h] BYREF
  __int128 v77; // [rsp+88h] [rbp-520h]
  __int64 v78; // [rsp+98h] [rbp-510h]
  wchar_t *S1[2]; // [rsp+A0h] [rbp-508h] BYREF
  unsigned __int64 v80; // [rsp+B0h] [rbp-4F8h]
  unsigned __int64 v81; // [rsp+B8h] [rbp-4F0h]
  wchar_t *String1[2]; // [rsp+C0h] [rbp-4E8h] BYREF
  unsigned __int64 v83; // [rsp+D0h] [rbp-4D8h]
  unsigned __int64 v84; // [rsp+D8h] [rbp-4D0h]
  PCWSTR pszString[2]; // [rsp+E0h] [rbp-4C8h] BYREF
  unsigned __int64 v86; // [rsp+F0h] [rbp-4B8h]
  unsigned __int64 v87; // [rsp+F8h] [rbp-4B0h]
  void *v88[2]; // [rsp+100h] [rbp-4A8h] BYREF
  unsigned __int64 v89; // [rsp+110h] [rbp-498h]
  unsigned __int64 v90; // [rsp+118h] [rbp-490h]
  PCWSTR v91[2]; // [rsp+120h] [rbp-488h] BYREF
  __m128i si128; // [rsp+130h] [rbp-478h]
  _OWORD Src[2]; // [rsp+140h] [rbp-468h] BYREF
  int pszDest[260]; // [rsp+160h] [rbp-448h] BYREF

  v78 = -2;
  v7 = this;
  v70 = this;
  v74 = this;
  v75 = pszSrc;
  pNumArgs = 0;
  pllRet = 0;
  memset_0(pszDest, 0, sizeof(pszDest));
  *(_OWORD *)v91 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v91[0]) = 0;
  v71 = 0;
  *(_DWORD *)v7 = 0;
  AslLogCallPrintf(3, "DeviceCensusMatchingPlugin", 84, "Enter DeviceCensusMatchingPlugin");
  if ( pszSrc && *pszSrc )
  {
    if ( StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x208u, L"DeviceCensusMatchingPlugin ") < 0 )
    {
      AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 95, "StringCchCatW failed.");
LABEL_130:
      try
      {
        AppCompatUtility::AddCacheMatchingPlugin(
          (AppCompatUtility *)*(unsigned int *)v7,
          (int)pszDest,
          (const unsigned __int16 *)a5,
          v8);
      }
      catch ( ... )
      {
        AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 228, "Unhandled exception");
        v7 = v74;
      }
      AslLogCallPrintf(3, "DeviceCensusMatchingPlugin", 231, "DeviceCensusMatchingPlugin Matched = %d", *(_DWORD *)v7);
      goto LABEL_129;
    }
    v73 = 0;
    if ( StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x208u, pszSrc) < 0 )
    {
      AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 102, "StringCchCatW failed; %ws", pszSrc);
      goto LABEL_130;
    }
    *(_OWORD *)v88 = 0;
    v89 = 0;
    v90 = 7;
    LOWORD(v88[0]) = 0;
    *(_OWORD *)S1 = 0;
    v80 = 0;
    v81 = 7;
    LOWORD(S1[0]) = 0;
    *(_OWORD *)pszString = 0;
    v86 = 0;
    v87 = 7;
    LOWORD(pszString[0]) = 0;
    *(_OWORD *)String1 = 0;
    v83 = 0;
    v84 = 7;
    LOWORD(String1[0]) = 0;
    if ( (unsigned int)AppCompatUtility::CheckCacheMatchingPlugin(v7, pszDest, (const unsigned __int16 *)a5, v9) )
    {
      std::wstring::~wstring(String1);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v88);
      std::wstring::~wstring(v91);
      return 1;
    }
    v11 = CommandLineToArgvW(pszSrc, &pNumArgs);
    v12 = v11;
    v73 = v11;
    if ( !v11 || pNumArgs != 4 )
    {
      v68 = pNumArgs;
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "DeviceCensusMatchingPlugin",
        125,
        "CommandLineToArgvW failed, code:%d;  %ws; numArgs=%d",
        LastError,
        pszSrc,
        v68);
      std::wstring::~wstring(String1);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v88);
      v7 = v70;
      if ( !v12 )
        goto LABEL_130;
LABEL_126:
      LocalFree(v12);
      v7 = v70;
      goto LABEL_130;
    }
    v13 = *v11;
    v14 = -1;
    v15 = -1;
    do
      ++v15;
    while ( v13[v15] );
    if ( v15 > v90 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v88);
    }
    else
    {
      v16 = v88;
      if ( v90 > 7 )
        v16 = (void **)v88[0];
      v89 = v15;
      v17 = 2 * v15;
      memmove_0(v16, v13, 2 * v15);
      *(_WORD *)((char *)v16 + v17) = 0;
    }
    v18 = v12[1];
    v19 = -1;
    do
      ++v19;
    while ( v18[v19] );
    if ( v19 > v81 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(S1);
    }
    else
    {
      v20 = S1;
      if ( v81 > 7 )
        v20 = (wchar_t **)S1[0];
      v80 = v19;
      v21 = 2 * v19;
      memmove_0(v20, v18, 2 * v19);
      *(_WORD *)((char *)v20 + v21) = 0;
    }
    v22 = v12[2];
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    if ( v23 > v87 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(pszString);
    }
    else
    {
      v24 = pszString;
      if ( v87 > 7 )
        v24 = (PCWSTR *)pszString[0];
      v86 = v23;
      v25 = 2 * v23;
      memmove_0(v24, v22, 2 * v23);
      *(_WORD *)((char *)v24 + v25) = 0;
    }
    v26 = v12[3];
    do
      ++v14;
    while ( v26[v14] );
    if ( v14 > v84 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(String1);
    }
    else
    {
      v27 = String1;
      if ( v84 > 7 )
        v27 = (wchar_t **)String1[0];
      v83 = v14;
      memmove_0(v27, v26, 2 * v14);
      *((_WORD *)v27 + v14) = 0;
    }
    v28 = String1;
    if ( v84 > 7 )
      v28 = (wchar_t **)String1[0];
    v29 = pszString;
    if ( v87 > 7 )
      v29 = (PCWSTR *)pszString[0];
    v30 = S1;
    if ( v81 > 7 )
      v30 = (wchar_t **)S1[0];
    v31 = v88;
    if ( v90 > 7 )
      v31 = (void **)v88[0];
    AslLogCallPrintf(
      3,
      "DeviceCensusMatchingPlugin",
      135,
      "PropertyName=%ws;PropertyType=%ws;ExpectedValue=%ws;Operation=%ws",
      v31,
      v30,
      v29,
      v28);
    if ( !v89 )
    {
      AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 143, "Empty PropertyName.");
      std::wstring::~wstring(String1);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v88);
      goto LABEL_126;
    }
    v32 = v80;
    v33 = (const wchar_t *)S1;
    if ( v81 > 7 )
      v33 = S1[0];
    v34 = v80;
    if ( v80 > 3 )
      v34 = 3;
    if ( wmemcmp(v33, L"int", v34) || v32 != 3 )
    {
      v36 = v80;
      v37 = (const wchar_t *)S1;
      if ( v81 > 7 )
        v37 = S1[0];
      v38 = v80;
      if ( v80 > 7 )
        v38 = 7;
      if ( wmemcmp(v37, L"wstring", v38) || v36 != 7 )
      {
        v66 = S1;
        if ( v81 > 7 )
          v66 = (wchar_t **)S1[0];
        AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 149, "Wrong PropertyType: %ws", v66);
        std::wstring::~wstring(String1);
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v88);
        goto LABEL_126;
      }
    }
    v39 = (wchar_t *)String1;
    if ( v84 > 7 )
      v39 = String1[0];
    if ( !AppCompatUtility::IsValidComparisonOperation(v39, v35) )
    {
      v40 = String1;
      if ( v84 > 7 )
        v40 = (wchar_t **)String1[0];
      AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 155, "Operation type not supported, %ws", v40);
      std::wstring::~wstring(String1);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v88);
      goto LABEL_126;
    }
    v41 = v80;
    v42 = (const wchar_t *)S1;
    if ( v81 > 7 )
      v42 = S1[0];
    v43 = v80;
    if ( v80 > 3 )
      v43 = 3;
    if ( !wmemcmp(v42, L"int", v43) && v41 == 3 )
    {
      v44 = (const WCHAR *)pszString;
      if ( v87 > 7 )
        v44 = pszString[0];
      if ( !StrToInt64ExW(v44, 1, &pllRet) )
      {
        AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 163, "Convert ExpectedValue to integer failed, %ws", v75);
        std::wstring::~wstring(String1);
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v88);
        goto LABEL_126;
      }
    }
    v45 = v80;
    v46 = (const wchar_t *)S1;
    if ( v81 > 7 )
      v46 = S1[0];
    v47 = v80;
    if ( v80 > 7 )
      v47 = 7;
    if ( !wmemcmp(v46, L"wstring", v47) && v45 == 7 )
    {
      v48 = v83;
      v49 = (const wchar_t *)String1;
      if ( v84 > 7 )
        v49 = String1[0];
      v50 = v83;
      if ( v83 > 2 )
        v50 = 2;
      if ( wmemcmp(v49, L"eq", v50) || v48 != 2 )
      {
        v51 = v83;
        v52 = (const wchar_t *)String1;
        if ( v84 > 7 )
          v52 = String1[0];
        v53 = v83;
        if ( v83 > 2 )
          v53 = 2;
        if ( wmemcmp(v52, L"ne", v53) || v51 != 2 )
        {
          v54 = String1;
          if ( v84 > 7 )
            v54 = (wchar_t **)String1[0];
          AslLogCallPrintf(
            1,
            "DeviceCensusMatchingPlugin",
            171,
            "Operation type not supported for string variable, %ws",
            v54);
          std::wstring::~wstring(String1);
          std::wstring::~wstring(pszString);
          std::wstring::~wstring(S1);
          std::wstring::~wstring(v88);
          goto LABEL_126;
        }
      }
    }
    memset(Src, 0, sizeof(Src));
    std::wstring::_Construct<1,unsigned short const *>(Src, L"c:", 2);
    v55 = std::wstring::append(Src);
    v76 = 0;
    v77 = 0u;
    v76 = *(_OWORD *)v55;
    v77 = *(_OWORD *)(v55 + 16);
    *(_QWORD *)(v55 + 16) = 0;
    *(_QWORD *)(v55 + 24) = 7;
    *(_WORD *)v55 = 0;
    CtacClientAttribute = AppCompatUtility::GetCtacClientAttribute(v91, &v76);
    std::wstring::~wstring(Src);
    if ( CtacClientAttribute < 0 )
    {
      AslLogCallPrintf(
        1,
        "DeviceCensusMatchingPlugin",
        182,
        "GetCtacClientAttribute failed. [0x%x]",
        CtacClientAttribute);
      std::wstring::~wstring(String1);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v88);
      goto LABEL_126;
    }
    v57 = v91;
    if ( si128.m128i_i64[1] > 7uLL )
      v57 = (PCWSTR *)v91[0];
    AslLogCallPrintf(3, "DeviceCensusMatchingPlugin", 186, "Census result value: %ws", v57);
    v58 = v80;
    v59 = (const wchar_t *)S1;
    if ( v81 > 7 )
      v59 = S1[0];
    v60 = v80;
    if ( v80 > 7 )
      v60 = 7;
    if ( !wmemcmp(v59, L"wstring", v60) && v58 == 7 )
    {
      v61 = AppCompatUtility::CompareStr(v91, pszString, String1);
    }
    else
    {
      v62 = v80;
      v63 = (const wchar_t *)S1;
      if ( v81 > 7 )
        v63 = S1[0];
      v64 = v80;
      if ( v80 > 3 )
        v64 = 3;
      if ( wmemcmp(v63, L"int", v64) || v62 != 3 )
        goto LABEL_121;
      v65 = (const WCHAR *)v91;
      if ( si128.m128i_i64[1] > 7uLL )
        v65 = v91[0];
      if ( !StrToInt64ExW(v65, 1, &v71) )
      {
        AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 200, "Convert Census result to integer failed");
        std::wstring::~wstring(String1);
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v88);
        goto LABEL_126;
      }
      AslLogCallPrintf(3, "DeviceCensusMatchingPlugin", 204, "Census result value int64 = %lld", v71);
      v61 = AppCompatUtility::CompareInt(v71, pllRet, String1);
    }
    *(_DWORD *)v70 = v61;
LABEL_121:
    std::wstring::~wstring(String1);
    std::wstring::~wstring(pszString);
    std::wstring::~wstring(S1);
    std::wstring::~wstring(v88);
    goto LABEL_126;
  }
  AslLogCallPrintf(1, "DeviceCensusMatchingPlugin", 88, "CommandLine is null/empty");
LABEL_129:
  std::wstring::~wstring(v91);
  return 1;
}

```

## disassembly

```asm
0x1800108d0  mov     r11, rsp
0x1800108d3  push    rdi
0x1800108d4  push    r12
0x1800108d6  push    r13
0x1800108d8  push    r14
0x1800108da  push    r15
0x1800108dc  sub     rsp, 580h
0x1800108e3  mov     qword ptr [r11-510h], 0FFFFFFFFFFFFFFFEh
0x1800108ee  mov     [r11+10h], rbx
0x1800108f2  mov     [r11+18h], rsi
0x1800108f6  mov     rax, cs:__security_cookie
0x1800108fd  xor     rax, rsp
0x180010900  mov     [rsp+5A8h+var_38], rax
0x180010908  mov     rbx, rcx
0x18001090b  mov     [rsp+5A8h+var_560], rcx
0x180010910  mov     [rsp+5A8h+var_540], rcx
0x180010915  mov     rdi, [rsp+5A8h+pszSrc]
0x18001091d  mov     [rsp+5A8h+var_538], rdi
0x180010922  xor     esi, esi
0x180010924  mov     [rsp+5A8h+pNumArgs], esi
0x180010928  mov     [rsp+5A8h+pllRet], rsi
0x18001092d  xor     edx, edx; Val
0x18001092f  mov     r8d, 410h; Size
0x180010935  lea     rcx, [r11-448h]; void *
0x18001093c  call    memset_0
0x180010941  xorps   xmm0, xmm0
0x180010944  movups  xmmword ptr [rsp+5A8h+var_488], xmm0
0x18001094c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180010954  movdqu  [rsp+5A8h+var_478], xmm1
0x18001095d  mov     word ptr [rsp+5A8h+var_488], si
0x180010965  mov     [rsp+5A8h+var_558], rsi
0x18001096a  mov     [rbx], esi
0x18001096c  lea     r9, aEnterDevicecen; "Enter DeviceCensusMatchingPlugin"
0x180010973  lea     r8d, [rsi+54h]
0x180010977  lea     r14, aDevicecensusma_2; "DeviceCensusMatchingPlugin"
0x18001097e  mov     rdx, r14
0x180010981  lea     r12d, [rsi+3]
0x180010985  mov     ecx, r12d
0x180010988  call    AslLogCallPrintf
0x18001098d  test    rdi, rdi
0x180010990  jz      loc_18001152B
0x180010996  cmp     si, [rdi]
0x180010999  jz      loc_18001152B
0x18001099f  lea     r8, aDevicecensusma_1; "DeviceCensusMatchingPlugin "
0x1800109a6  mov     r15d, 208h
0x1800109ac  mov     edx, r15d; cchDest
0x1800109af  lea     rcx, [rsp+5A8h+pszDest]; pszDest
0x1800109b7  call    StringCchCatW
0x1800109bc  test    eax, eax
0x1800109be  jns     short loc_1800109DB
0x1800109c0  lea     r9, aStringcchcatwF_0; "StringCchCatW failed."
0x1800109c7  lea     r8d, [rsi+5Fh]
0x1800109cb  mov     rdx, r14
0x1800109ce  lea     ecx, [rsi+1]
0x1800109d1  call    AslLogCallPrintf
0x1800109d6  jmp     loc_1800114DF
0x1800109db  mov     [rsp+5A8h+var_548], rsi
0x1800109e0  mov     r8, rdi; pszSrc
0x1800109e3  mov     rdx, r15; cchDest
0x1800109e6  lea     rcx, [rsp+5A8h+pszDest]; pszDest
0x1800109ee  call    StringCchCatW
0x1800109f3  test    eax, eax
0x1800109f5  jns     short loc_180010A1A
0x1800109f7  mov     [rsp+5A8h+var_588], rdi
0x1800109fc  lea     r9, aStringcchcatwF; "StringCchCatW failed; %ws"
0x180010a03  mov     r8d, 66h ; 'f'
0x180010a09  mov     rdx, r14
0x180010a0c  lea     ecx, [r8-65h]
0x180010a10  call    AslLogCallPrintf
0x180010a15  jmp     loc_1800114DF
0x180010a1a  xorps   xmm0, xmm0
0x180010a1d  movups  xmmword ptr [rsp+5A8h+var_4A8], xmm0
0x180010a25  mov     [rsp+5A8h+var_498], rsi
0x180010a2d  mov     eax, 7
0x180010a32  mov     [rsp+5A8h+var_490], rax
0x180010a3a  mov     word ptr [rsp+5A8h+var_4A8], si
0x180010a42  movups  xmmword ptr [rsp+5A8h+S1], xmm0
0x180010a4a  mov     [rsp+5A8h+var_4F8], rsi
0x180010a52  mov     [rsp+5A8h+var_4F0], rax
0x180010a5a  mov     word ptr [rsp+5A8h+S1], si
0x180010a62  movups  xmmword ptr [rsp+5A8h+pszString], xmm0
0x180010a6a  mov     [rsp+5A8h+var_4B8], rsi
0x180010a72  mov     [rsp+5A8h+var_4B0], rax
0x180010a7a  mov     word ptr [rsp+5A8h+pszString], si
0x180010a82  movups  xmmword ptr [rsp+5A8h+String1], xmm0
0x180010a8a  mov     [rsp+5A8h+var_4D8], rsi
0x180010a92  mov     [rsp+5A8h+var_4D0], rax
0x180010a9a  mov     word ptr [rsp+5A8h+String1], si
0x180010aa2  mov     r8d, dword ptr [rsp+5A8h+arg_20]; unsigned __int16 *
0x180010aaa  lea     rdx, [rsp+5A8h+pszDest]; int *
0x180010ab2  mov     rcx, rbx; this
0x180010ab5  call    ?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z; AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)
0x180010aba  test    eax, eax
0x180010abc  jz      short loc_180010B0D
0x180010abe  lea     rcx, [rsp+5A8h+String1]; void *
0x180010ac6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010acb  nop
0x180010acc  lea     rcx, [rsp+5A8h+pszString]; void *
0x180010ad4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ad9  nop
0x180010ada  lea     rcx, [rsp+5A8h+S1]; void *
0x180010ae2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ae7  nop
0x180010ae8  lea     rcx, [rsp+5A8h+var_4A8]; void *
0x180010af0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010af5  nop
0x180010af6  lea     rcx, [rsp+5A8h+var_488]; void *
0x180010afe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010b03  mov     eax, 1
0x180010b08  jmp     loc_180011557
0x180010b0d  lea     rdx, [rsp+5A8h+pNumArgs]; pNumArgs
0x180010b12  mov     rcx, rdi; lpCmdLine
0x180010b15  call    cs:__imp_CommandLineToArgvW
0x180010b1b  mov     r13, rax
0x180010b1e  mov     [rsp+5A8h+var_548], rax
0x180010b23  mov     ebx, [rsp+5A8h+pNumArgs]
0x180010b27  test    rax, rax
0x180010b2a  jz      loc_180011444
0x180010b30  cmp     ebx, 4
0x180010b33  jnz     loc_180011444
0x180010b39  mov     r9, [rax]
0x180010b3c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180010b40  mov     rdx, r15
0x180010b43  inc     rdx
0x180010b46  cmp     [r9+rdx*2], si
0x180010b4b  jnz     short loc_180010B43
0x180010b4d  cmp     rdx, [rsp+5A8h+var_490]
0x180010b55  ja      short loc_180010B91
0x180010b57  lea     rdi, [rsp+5A8h+var_4A8]
0x180010b5f  cmp     [rsp+5A8h+var_490], 7
0x180010b68  cmova   rdi, [rsp+5A8h+var_4A8]
0x180010b71  mov     [rsp+5A8h+var_498], rdx
0x180010b79  lea     rbx, [rdx+rdx]
0x180010b7d  mov     r8, rbx; Size
0x180010b80  mov     rdx, r9; Src
0x180010b83  mov     rcx, rdi; void *
0x180010b86  call    memmove_0
0x180010b8b  mov     [rdi+rbx], si
0x180010b8f  jmp     short loc_180010B9E
0x180010b91  lea     rcx, [rsp+5A8h+var_4A8]
0x180010b99  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180010b9e  mov     r9, [r13+8]
0x180010ba2  mov     rdx, r15
0x180010ba5  inc     rdx
0x180010ba8  cmp     [r9+rdx*2], si
0x180010bad  jnz     short loc_180010BA5
0x180010baf  cmp     rdx, [rsp+5A8h+var_4F0]
0x180010bb7  ja      short loc_180010BF3
0x180010bb9  lea     rdi, [rsp+5A8h+S1]
0x180010bc1  cmp     [rsp+5A8h+var_4F0], 7
0x180010bca  cmova   rdi, [rsp+5A8h+S1]
0x180010bd3  mov     [rsp+5A8h+var_4F8], rdx
0x180010bdb  lea     rbx, [rdx+rdx]
0x180010bdf  mov     r8, rbx; Size
0x180010be2  mov     rdx, r9; Src
0x180010be5  mov     rcx, rdi; void *
0x180010be8  call    memmove_0
0x180010bed  mov     [rdi+rbx], si
0x180010bf1  jmp     short loc_180010C00
0x180010bf3  lea     rcx, [rsp+5A8h+S1]
0x180010bfb  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180010c00  mov     r9, [r13+10h]
0x180010c04  mov     rdx, r15
0x180010c07  inc     rdx
0x180010c0a  cmp     [r9+rdx*2], si
0x180010c0f  jnz     short loc_180010C07
0x180010c11  cmp     rdx, [rsp+5A8h+var_4B0]
0x180010c19  ja      short loc_180010C55
0x180010c1b  lea     rdi, [rsp+5A8h+pszString]
0x180010c23  cmp     [rsp+5A8h+var_4B0], 7
0x180010c2c  cmova   rdi, [rsp+5A8h+pszString]
0x180010c35  mov     [rsp+5A8h+var_4B8], rdx
0x180010c3d  lea     rbx, [rdx+rdx]
0x180010c41  mov     r8, rbx; Size
0x180010c44  mov     rdx, r9; Src
0x180010c47  mov     rcx, rdi; void *
0x180010c4a  call    memmove_0
0x180010c4f  mov     [rdi+rbx], si
0x180010c53  jmp     short loc_180010C62
0x180010c55  lea     rcx, [rsp+5A8h+pszString]
0x180010c5d  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180010c62  mov     r9, [r13+18h]
0x180010c66  inc     r15
0x180010c69  cmp     [r9+r15*2], si
0x180010c6e  jnz     short loc_180010C66
0x180010c70  cmp     r15, [rsp+5A8h+var_4D0]
0x180010c78  ja      short loc_180010CB4
0x180010c7a  lea     rdi, [rsp+5A8h+String1]
0x180010c82  cmp     [rsp+5A8h+var_4D0], 7
0x180010c8b  cmova   rdi, [rsp+5A8h+String1]
0x180010c94  mov     [rsp+5A8h+var_4D8], r15
0x180010c9c  lea     rbx, [r15+r15]
0x180010ca0  mov     r8, rbx; Size
0x180010ca3  mov     rdx, r9; Src
0x180010ca6  mov     rcx, rdi; void *
0x180010ca9  call    memmove_0
0x180010cae  mov     [rdi+rbx], si
0x180010cb2  jmp     short loc_180010CC4
0x180010cb4  mov     rdx, r15
0x180010cb7  lea     rcx, [rsp+5A8h+String1]
0x180010cbf  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180010cc4  lea     r8, [rsp+5A8h+String1]
0x180010ccc  mov     r15d, 7
0x180010cd2  cmp     [rsp+5A8h+var_4D0], r15
0x180010cda  cmova   r8, [rsp+5A8h+String1]
0x180010ce3  lea     rdx, [rsp+5A8h+pszString]
0x180010ceb  cmp     [rsp+5A8h+var_4B0], r15
0x180010cf3  cmova   rdx, [rsp+5A8h+pszString]
0x180010cfc  lea     rcx, [rsp+5A8h+S1]
0x180010d04  cmp     [rsp+5A8h+var_4F0], r15
0x180010d0c  cmova   rcx, [rsp+5A8h+S1]
0x180010d15  lea     rax, [rsp+5A8h+var_4A8]
0x180010d1d  cmp     [rsp+5A8h+var_490], r15
0x180010d25  cmova   rax, [rsp+5A8h+var_4A8]
0x180010d2e  mov     [rsp+5A8h+var_570], r8
0x180010d33  mov     [rsp+5A8h+var_578], rdx
0x180010d38  mov     [rsp+5A8h+var_580], rcx
0x180010d3d  mov     [rsp+5A8h+var_588], rax
0x180010d42  lea     r9, aPropertynameWs; "PropertyName=%ws;PropertyType=%ws;Expec"...
0x180010d49  mov     r8d, 87h
0x180010d4f  mov     rdx, r14
0x180010d52  mov     ecx, r12d
0x180010d55  call    AslLogCallPrintf
0x180010d5a  cmp     [rsp+5A8h+var_498], rsi
0x180010d62  jnz     short loc_180010DBB
0x180010d64  lea     r9, aEmptyPropertyn; "Empty PropertyName."
0x180010d6b  mov     r8d, 8Fh
0x180010d71  mov     rdx, r14
0x180010d74  lea     ecx, [r15-6]
0x180010d78  call    AslLogCallPrintf
0x180010d7d  nop
0x180010d7e  lea     rcx, [rsp+5A8h+String1]; void *
0x180010d86  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010d8b  nop
0x180010d8c  lea     rcx, [rsp+5A8h+pszString]; void *
0x180010d94  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010d99  nop
0x180010d9a  lea     rcx, [rsp+5A8h+S1]; void *
0x180010da2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010da7  nop
0x180010da8  lea     rcx, [rsp+5A8h+var_4A8]; void *
0x180010db0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010db5  nop
0x180010db6  jmp     loc_1800114D1
0x180010dbb  mov     rbx, [rsp+5A8h+var_4F8]
0x180010dc3  lea     rcx, [rsp+5A8h+S1]
0x180010dcb  cmp     [rsp+5A8h+var_4F0], r15
0x180010dd3  cmova   rcx, [rsp+5A8h+S1]; S1
0x180010ddc  mov     r8, rbx
0x180010ddf  cmp     rbx, r12
0x180010de2  cmova   r8, r12; N
0x180010de6  lea     rdx, aInt; "int"
0x180010ded  call    wmemcmp
0x180010df2  test    eax, eax
0x180010df4  jnz     short loc_180010DFB
0x180010df6  cmp     rbx, r12
0x180010df9  jz      short loc_180010E43
0x180010dfb  mov     rbx, [rsp+5A8h+var_4F8]
0x180010e03  lea     rcx, [rsp+5A8h+S1]
0x180010e0b  cmp     [rsp+5A8h+var_4F0], r15
0x180010e13  cmova   rcx, [rsp+5A8h+S1]; S1
0x180010e1c  mov     r8, rbx
0x180010e1f  cmp     rbx, r15
0x180010e22  cmova   r8, r15; N
0x180010e26  lea     rdx, aWstring; "wstring"
0x180010e2d  call    wmemcmp
0x180010e32  test    eax, eax
0x180010e34  jnz     loc_1800113CE
0x180010e3a  cmp     rbx, r15
0x180010e3d  jnz     loc_1800113CE
0x180010e43  lea     rcx, [rsp+5A8h+String1]
0x180010e4b  cmp     [rsp+5A8h+var_4D0], r15
0x180010e53  cmova   rcx, [rsp+5A8h+String1]; String1
0x180010e5c  call    ?IsValidComparisonOperation@AppCompatUtility@@YA_NPEBG@Z; AppCompatUtility::IsValidComparisonOperation(ushort const *)
0x180010e61  test    al, al
0x180010e63  jnz     short loc_180010EDB
0x180010e65  lea     rax, [rsp+5A8h+String1]
0x180010e6d  cmp     [rsp+5A8h+var_4D0], r15
0x180010e75  cmova   rax, [rsp+5A8h+String1]
0x180010e7e  mov     [rsp+5A8h+var_588], rax
0x180010e83  lea     r9, aOperationTypeN; "Operation type not supported, %ws"
0x180010e8a  mov     r8d, 9Bh
0x180010e90  mov     rdx, r14
0x180010e93  mov     ecx, 1
0x180010e98  call    AslLogCallPrintf
0x180010e9d  nop
0x180010e9e  lea     rcx, [rsp+5A8h+String1]; void *
0x180010ea6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010eab  nop
0x180010eac  lea     rcx, [rsp+5A8h+pszString]; void *
0x180010eb4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010eb9  nop
0x180010eba  lea     rcx, [rsp+5A8h+S1]; void *
0x180010ec2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ec7  nop
0x180010ec8  lea     rcx, [rsp+5A8h+var_4A8]; void *
0x180010ed0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010ed5  nop
0x180010ed6  jmp     loc_1800114D1
0x180010edb  mov     rbx, [rsp+5A8h+var_4F8]
  ... truncated ...
```
