# WmiQueryMatchingPluginHelper(int *,ushort const *,ulong)

- ea: `0x18000c974`
- end: `0x18000dd88`
- name: `?WmiQueryMatchingPluginHelper@@YAXPEAHPEBGK@Z`
- size: `5140`
- prototype: `void __fastcall(AppCompatUtility *this, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c8d0`

## callees

- `0x180001cf0`
- `0x180002120`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000c3c8`
- `0x18000c534`
- `0x18000c5d0`
- `0x18000c5fc`
- `0x18000c974`
- `0x18000dfd8`
- `0x18000e064`
- `0x18000e0e4`
- `0x18003f0b0`
- `0x18003fa7c`
- `0x1800425fc`
- `0x1800426a8`
- `0x180044964`
- `0x1800514a8`
- `0x1800543c0`
- `0x180065120`
- `0x180065150`
- `0x18006a010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18000db28`
- `KERNEL32!LocalFree` at `0x18000db28`
- `KERNEL32!MultiByteToWideChar` at `0x18000d6c0`
- `KERNEL32!MultiByteToWideChar` at `0x18000d6f6`
- `KERNEL32!MultiByteToWideChar` at `0x18000d6c0`
- `KERNEL32!MultiByteToWideChar` at `0x18000d6f6`
- `KERNEL32!GetTickCount64` at `0x18000cad3`
- `KERNEL32!GetTickCount64` at `0x18000db58`
- `KERNEL32!GetTickCount64` at `0x18000cad3`
- `KERNEL32!GetTickCount64` at `0x18000db58`
- `ole32!CoCreateInstance` at `0x18000d42d`
- `ole32!CoCreateInstance` at `0x18000d42d`
- `ole32!CoSetProxyBlanket` at `0x18000d632`
- `ole32!CoSetProxyBlanket` at `0x18000d632`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d477`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d715`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d477`
- `OLEAUT32!__imp_SysAllocString` at `0x18000d715`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d6cd`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18000d6cd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc54`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d70c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d76d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dcf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd6e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000cc54`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d4c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d70c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000d76d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc1d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dcf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd6e`
- `OLEAUT32!__imp_VariantInit` at `0x18000cac8`
- `OLEAUT32!__imp_VariantInit` at `0x18000cac8`
- `OLEAUT32!__imp_VariantClear` at `0x18000cbe2`
- `OLEAUT32!__imp_VariantClear` at `0x18000dbaa`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc80`
- `OLEAUT32!__imp_VariantClear` at `0x18000cbe2`
- `OLEAUT32!__imp_VariantClear` at `0x18000dbaa`
- `OLEAUT32!__imp_VariantClear` at `0x18000dc80`
- `SHLWAPI!StrToInt64ExW` at `0x18000d30d`
- `SHLWAPI!StrToInt64ExW` at `0x18000d30d`
- `SHLWAPI!StrToIntExW` at `0x18000ce28`
- `SHLWAPI!StrToIntExW` at `0x18000d241`
- `SHLWAPI!StrToIntExW` at `0x18000ce28`
- `SHLWAPI!StrToIntExW` at `0x18000d241`
- `SHELL32!CommandLineToArgvW` at `0x18000cd8a`
- `SHELL32!CommandLineToArgvW` at `0x18000cd8a`

## string_xrefs

- `0x18000cb11`: `Enter WmiQueryMatchingPlugin`
- `0x18000cb1e`: `WmiQueryMatchingPluginHelper`
- `0x18000ce03`: `WmiQueryMatchingPluginHelper`
- `0x18000ce4a`: `WmiQueryMatchingPluginHelper`
- `0x18000d1c6`: `WmiQueryMatchingPluginHelper`
- `0x18000d3fa`: `WmiQueryMatchingPluginHelper`
- `0x18000d5f5`: `WmiQueryMatchingPluginHelper`
- `0x18000d64d`: `WmiQueryMatchingPluginHelper`
- `0x18000d79f`: `WmiQueryMatchingPluginHelper`
- `0x18000d9a4`: `WmiQueryMatchingPluginHelper`
- `0x18000da56`: `WmiQueryMatchingPluginHelper`
- `0x18000daed`: `WmiQueryMatchingPluginHelper`
- `0x18000db8a`: `WmiQueryMatchingPluginHelper`
- `0x18000dc62`: `WmiQueryMatchingPluginHelper`
- `0x18000dc55`: `CommandLine is null/empty`
- `0x18000cb6f`: `WmiQueryMatchingPlugin `
- `0x18000cb89`: `WmiQueryMatchingPlugin `
- `0x18000dae0`: `CommandLineToArgvW failed, %ws, numArgs=%d`
- `0x18000daae`: `0x%08x CoCreateInstance failed`
- `0x18000db7d`: `WmiQueryMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=23
void __fastcall WmiQueryMatchingPluginHelper(AppCompatUtility *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v3; // r15d
  unsigned int v6; // r13d
  OLECHAR *v7; // rsi
  _QWORD *v8; // rax
  unsigned int v9; // r14d
  _WORD *v10; // rbx
  unsigned int v11; // r9d
  int *v12; // rdx
  const wchar_t **v13; // rax
  const wchar_t **v14; // r15
  int v15; // ebx
  unsigned int v16; // r9d
  const char *v17; // r9
  __int64 v18; // r8
  const wchar_t *v19; // r9
  unsigned __int64 v20; // rdx
  OLECHAR *v21; // rdi
  __int64 v22; // rbx
  const wchar_t *v23; // r9
  unsigned __int64 v24; // rdx
  void **v25; // rdi
  __int64 v26; // rbx
  const wchar_t *v27; // r9
  unsigned __int64 v28; // rdx
  wchar_t **v29; // rdi
  __int64 v30; // rbx
  const wchar_t *v31; // r9
  unsigned __int64 v32; // rdx
  void **v33; // rdi
  __int64 v34; // rbx
  const wchar_t *v35; // r9
  unsigned __int64 v36; // rdx
  wchar_t **v37; // rdi
  __int64 v38; // rbx
  const wchar_t *v39; // r9
  unsigned __int64 v40; // rdx
  PCWSTR *v41; // rdi
  __int64 v42; // rbx
  const wchar_t *v43; // r9
  unsigned __int64 v44; // rdx
  wchar_t **v45; // rdi
  __int64 v46; // rbx
  wchar_t **v47; // rbx
  PCWSTR *v48; // r10
  wchar_t **v49; // r9
  void **v50; // r8
  wchar_t **v51; // rdx
  void **v52; // rcx
  OLECHAR *v53; // rax
  unsigned __int64 v54; // rbx
  const wchar_t *v55; // rcx
  size_t v56; // r8
  const unsigned __int16 *v57; // rdx
  const WCHAR *v58; // rcx
  wchar_t *v59; // rcx
  const unsigned __int16 *v60; // rdx
  wchar_t *v61; // rcx
  unsigned __int64 v62; // rbx
  const wchar_t *v63; // rcx
  size_t v64; // r8
  const WCHAR *v65; // rcx
  unsigned __int64 v66; // rbx
  const wchar_t *v67; // rcx
  size_t v68; // r8
  unsigned __int64 v69; // rbx
  const wchar_t *v70; // rcx
  size_t v71; // r8
  unsigned __int64 v72; // rbx
  const wchar_t *v73; // rcx
  size_t v74; // r8
  wchar_t **v75; // rax
  HRESULT v76; // eax
  LPVOID v77; // rdi
  __int64 v78; // r12
  OLECHAR *v79; // rcx
  OLECHAR *v80; // rbx
  BSTR v81; // rdx
  BSTR v82; // rax
  int v83; // ecx
  int v84; // edi
  OLECHAR **v85; // rbx
  void **v86; // rdx
  __int64 v87; // rbx
  OLECHAR **v88; // rax
  HRESULT v89; // eax
  const OLECHAR *v90; // rbx
  IUnknown *v91; // r12
  struct IUnknownVtbl *lpVtbl; // r13
  int v93; // edi
  WCHAR *v94; // rax
  OLECHAR *v95; // rbx
  int v96; // ecx
  int v97; // ecx
  int v98; // edi
  __int64 v99; // rcx
  int v100; // eax
  void **v101; // rdx
  int v102; // ecx
  void **v103; // rax
  AppCompatUtility *v104; // rbx
  int v105; // eax
  int v106; // eax
  void **v107; // rdx
  int v108; // eax
  void **v109; // rcx
  OLECHAR **v110; // rax
  OLECHAR *v111; // rax
  __int64 v112; // r8
  void **v113; // rdx
  int v114; // eax
  LPVOID *ppv; // [rsp+28h] [rbp-E0h]
  LPVOID *ppva; // [rsp+28h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+28h] [rbp-E0h]
  LPVOID *ppvc; // [rsp+28h] [rbp-E0h]
  LPVOID *ppvd; // [rsp+28h] [rbp-E0h]
  LPVOID *ppve; // [rsp+28h] [rbp-E0h]
  DWORD dwImpLevel[2]; // [rsp+30h] [rbp-D8h]
  char v122; // [rsp+68h] [rbp-A0h]
  int pNumArgs; // [rsp+78h] [rbp-90h] BYREF
  int piRet; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v126; // [rsp+80h] [rbp-88h] BYREF
  int v127; // [rsp+84h] [rbp-84h] BYREF
  __int64 v128; // [rsp+88h] [rbp-80h] BYREF
  IUnknown *pProxy; // [rsp+90h] [rbp-78h] BYREF
  __int64 v130; // [rsp+98h] [rbp-70h] BYREF
  LPVOID v131; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v132[2]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int16 *v133; // [rsp+B8h] [rbp-50h]
  LONGLONG pllRet; // [rsp+C0h] [rbp-48h] BYREF
  _QWORD v135[2]; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+D8h] [rbp-30h] BYREF
  OLECHAR *v137; // [rsp+F0h] [rbp-18h]
  ULONGLONG TickCount64; // [rsp+F8h] [rbp-10h]
  __int64 v139; // [rsp+100h] [rbp-8h]
  OLECHAR *Src[2]; // [rsp+108h] [rbp+0h] BYREF
  __int64 v141; // [rsp+118h] [rbp+10h]
  unsigned __int64 v142; // [rsp+120h] [rbp+18h]
  wchar_t *String1[2]; // [rsp+128h] [rbp+20h] BYREF
  unsigned __int64 v144; // [rsp+138h] [rbp+30h]
  unsigned __int64 v145; // [rsp+140h] [rbp+38h]
  void *v146[2]; // [rsp+148h] [rbp+40h] BYREF
  unsigned __int64 v147; // [rsp+158h] [rbp+50h]
  unsigned __int64 v148; // [rsp+160h] [rbp+58h]
  wchar_t *v149[2]; // [rsp+168h] [rbp+60h] BYREF
  unsigned __int64 v150; // [rsp+178h] [rbp+70h]
  unsigned __int64 v151; // [rsp+180h] [rbp+78h]
  OLECHAR psz[8]; // [rsp+188h] [rbp+80h] BYREF
  unsigned __int64 v153; // [rsp+198h] [rbp+90h]
  unsigned __int64 v154; // [rsp+1A0h] [rbp+98h]
  wchar_t *S1[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  unsigned __int64 v156; // [rsp+1B8h] [rbp+B0h]
  unsigned __int64 v157; // [rsp+1C0h] [rbp+B8h]
  void *v158[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  __int64 v159; // [rsp+1D8h] [rbp+D0h]
  unsigned __int64 v160; // [rsp+1E0h] [rbp+D8h]
  PCWSTR pszString[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  unsigned __int64 v162; // [rsp+1F8h] [rbp+F0h]
  unsigned __int64 v163; // [rsp+200h] [rbp+F8h]
  __int128 v164; // [rsp+208h] [rbp+100h] BYREF
  __int64 v165; // [rsp+218h] [rbp+110h]
  __int64 v166; // [rsp+220h] [rbp+118h]
  void *v167[2]; // [rsp+228h] [rbp+120h] BYREF
  unsigned __int64 v168; // [rsp+238h] [rbp+130h]
  unsigned __int64 v169; // [rsp+240h] [rbp+138h]

  v139 = -2;
  v3 = (unsigned int)a3;
  LODWORD(v133) = (_DWORD)a3;
  v6 = 0;
  v130 = 0;
  v128 = 0;
  v131 = 0;
  pProxy = 0;
  v7 = 0;
  v137 = 0;
  pNumArgs = 0;
  *(_OWORD *)psz = 0;
  v153 = 0;
  v154 = 7;
  psz[0] = 0;
  *(_OWORD *)v167 = 0;
  v168 = 0;
  v169 = 7;
  LOWORD(v167[0]) = 0;
  *(_OWORD *)S1 = 0;
  v156 = 0;
  v157 = 7;
  LOWORD(S1[0]) = 0;
  *(_OWORD *)v146 = 0;
  v147 = 0;
  v148 = 7;
  LOWORD(v146[0]) = 0;
  *(_OWORD *)v149 = 0;
  v150 = 0;
  v151 = 7;
  LOWORD(v149[0]) = 0;
  *(_OWORD *)pszString = 0;
  v162 = 0;
  v163 = 7;
  LOWORD(pszString[0]) = 0;
  *(_OWORD *)String1 = 0;
  v144 = 0;
  v145 = 7;
  LOWORD(String1[0]) = 0;
  *(_OWORD *)Src = 0;
  v141 = 0;
  v142 = 7;
  LOWORD(Src[0]) = 0;
  *(_OWORD *)v158 = 0;
  v159 = 0;
  v160 = 7;
  LOWORD(v158[0]) = 0;
  v126 = 0;
  v127 = 0;
  VariantInit(&pvarg);
  pllRet = 0;
  TickCount64 = GetTickCount64();
  v132[1] = 0;
  v8 = operator new(0x40u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  v9 = 1;
  *((_WORD *)v8 + 12) = 257;
  v132[0] = v8;
  piRet = 6000;
  *(_DWORD *)this = 0;
  AslLogCallPrintf(3, "WmiQueryMatchingPluginHelper", 154, "Enter WmiQueryMatchingPlugin");
  if ( a2 && *a2 )
  {
    if ( v160 < 0x17 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v158);
    }
    else
    {
      v10 = v158[0];
      v159 = 23;
      memmove_0(v158[0], L"WmiQueryMatchingPlugin ", 0x2Eu);
      v10[23] = 0;
    }
    std::wstring::append(v158, a2);
    v12 = (int *)v158;
    if ( v160 > 7 )
      v12 = (int *)v158[0];
    if ( (unsigned int)AppCompatUtility::CheckCacheMatchingPlugin(this, v12, (const unsigned __int16 *)v3, v11) )
    {
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v132);
      VariantClear(&pvarg);
      std::wstring::~wstring(v158);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(String1);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(v149);
      std::wstring::~wstring(v146);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v167);
      std::wstring::~wstring(psz);
      SysFreeString(0);
      if ( pProxy )
        ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
      if ( v131 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v131 + 16LL))(v131);
      goto LABEL_241;
    }
    v164 = 0;
    v165 = 0;
    v166 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v164, L"FreeFormWhereClause", 19);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v132,
      v135,
      &v164);
    std::wstring::~wstring(&v164);
    v164 = 0;
    v165 = 0;
    v166 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v164, L"WildIndex", 9);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v132,
      v135,
      &v164);
    std::wstring::~wstring(&v164);
    v164 = 0;
    v165 = 0;
    v166 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v164, L"Timeout", 7);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v132,
      v135,
      &v164);
    std::wstring::~wstring(&v164);
    v13 = (const wchar_t **)CommandLineToArgvW(a2, &pNumArgs);
    v14 = v13;
    v15 = pNumArgs;
    if ( !v13 || pNumArgs < 1 )
    {
      AslLogCallPrintf(
        1,
        "WmiQueryMatchingPluginHelper",
        180,
        "CommandLineToArgvW failed, %ws, numArgs=%d",
        a2,
        pNumArgs);
      goto LABEL_223;
    }
    if ( !wcscmp_0(L"Features", *v13) )
    {
      if ( (unsigned __int8)AppCompatUtility::SupportAllFeatures(v132, (unsigned int)v15, v14) )
        *(_DWORD *)this = 1;
      goto LABEL_223;
    }
    if ( !wcscmp_0(L"-Timeout", *v14) )
    {
      if ( v15 < 9 )
      {
        LODWORD(ppv) = v15;
        v17 = "Wrong arguments number: %d";
        v18 = 198;
LABEL_22:
        AslLogCallPrintf(v9, "WmiQueryMatchingPluginHelper", v18, v17, ppv);
        goto LABEL_223;
      }
      v6 = 2;
      if ( !StrToIntExW(v14[1], 0, &piRet) )
      {
        AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 204, "StrToIntEx failed %ws", v14[1]);
        goto LABEL_223;
      }
    }
    else if ( v15 < 7 )
    {
      AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 210, "Wrong arguments number: %d", v15);
      goto LABEL_223;
    }
    v19 = v14[v6];
    v20 = -1;
    do
      ++v20;
    while ( v19[v20] );
    if ( v20 > v154 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(psz);
    }
    else
    {
      v21 = psz;
      if ( v154 > 7 )
        v21 = *(OLECHAR **)psz;
      v153 = v20;
      v22 = v20;
      memmove_0(v21, v19, 2 * v20);
      v21[v22] = 0;
    }
    v23 = v14[v6 + 1];
    v24 = -1;
    do
      ++v24;
    while ( v23[v24] );
    if ( v24 > v169 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v167);
    }
    else
    {
      v25 = v167;
      if ( v169 > 7 )
        v25 = (void **)v167[0];
      v168 = v24;
      v26 = 2 * v24;
      memmove_0(v25, v23, 2 * v24);
      *(_WORD *)((char *)v25 + v26) = 0;
    }
    v27 = v14[v6 + 2];
    v28 = -1;
    do
      ++v28;
    while ( v27[v28] );
    if ( v28 > v157 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(S1);
    }
    else
    {
      v29 = S1;
      if ( v157 > 7 )
        v29 = (wchar_t **)S1[0];
      v156 = v28;
      v30 = 2 * v28;
      memmove_0(v29, v27, 2 * v28);
      *(_WORD *)((char *)v29 + v30) = 0;
    }
    v31 = v14[v6 + 3];
    v32 = -1;
    do
      ++v32;
    while ( v31[v32] );
    if ( v32 > v148 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v146);
    }
    else
    {
      v33 = v146;
      if ( v148 > 7 )
        v33 = (void **)v146[0];
      v147 = v32;
      v34 = 2 * v32;
      memmove_0(v33, v31, 2 * v32);
      *(_WORD *)((char *)v33 + v34) = 0;
    }
    v35 = v14[v6 + 4];
    v36 = -1;
    do
      ++v36;
    while ( v35[v36] );
    if ( v36 > v151 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v149);
    }
    else
    {
      v37 = v149;
      if ( v151 > 7 )
        v37 = (wchar_t **)v149[0];
      v150 = v36;
      v38 = 2 * v36;
      memmove_0(v37, v35, 2 * v36);
      *(_WORD *)((char *)v37 + v38) = 0;
    }
    v39 = v14[v6 + 5];
    v40 = -1;
    do
      ++v40;
    while ( v39[v40] );
    if ( v40 > v163 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(pszString);
    }
    else
    {
      v41 = pszString;
      if ( v163 > 7 )
        v41 = (PCWSTR *)pszString[0];
      v162 = v40;
      v42 = 2 * v40;
      memmove_0(v41, v39, 2 * v40);
      *(_WORD *)((char *)v41 + v42) = 0;
    }
    v43 = v14[v6 + 6];
    v44 = -1;
    do
      ++v44;
    while ( v43[v44] );
    if ( v44 > v145 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(String1);
    }
    else
    {
      v45 = String1;
      if ( v145 > 7 )
        v45 = (wchar_t **)String1[0];
      v144 = v44;
      v46 = 2 * v44;
      memmove_0(v45, v43, 2 * v44);
      *(_WORD *)((char *)v45 + v46) = 0;
    }
    v47 = String1;
    if ( v145 > 7 )
      v47 = (wchar_t **)String1[0];
    v48 = pszString;
    if ( v163 > 7 )
      v48 = (PCWSTR *)pszString[0];
    v49 = v149;
    if ( v151 > 7 )
      v49 = (wchar_t **)v149[0];
    v50 = v146;
    if ( v148 > 7 )
      v50 = (void **)v146[0];
    v51 = S1;
    if ( v157 > 7 )
      v51 = (wchar_t **)S1[0];
    v52 = v167;
    if ( v169 > 7 )
      v52 = (void **)v167[0];
    v53 = psz;
    if ( v154 > 7 )
      v53 = *(OLECHAR **)psz;
    AslLogCallPrintf(
      3,
      "WmiQueryMatchingPluginHelper",
      224,
      "Provider=%ws;Class=%ws;Index=%ws;Name=%ws;Type=%ws;Expected=%ws;Operation=%ws;Timeout=%d",
      v53,
      v52,
      v51,
      v50,
      v49,
      v48,
      v47,
      piRet);
    v54 = v156;
    v55 = (const wchar_t *)S1;
    if ( v157 > 7 )
      v55 = S1[0];
    v56 = v156;
    if ( v156 > 1 )
      v56 = 1;
    if ( !wmemcmp(v55, L"*", v56) && v54 == 1 )
    {
      v122 = 1;
    }
    else
    {
      v58 = (const WCHAR *)S1;
      if ( v157 > 7 )
        v58 = S1[0];
      if ( !StrToIntExW(v58, 1, &v126) || (v122 = 0, v126 < 0) )
      {
        AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 233, "Convert WmiObjectIndex failed, %ws", a2);
        goto LABEL_223;
      }
    }
    v59 = (wchar_t *)v149;
    if ( v151 > 7 )
      v59 = v149[0];
    if ( !AppCompatUtility::IsValidVariableType(v59, v57) )
    {
      AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 239, "Variable type not supported, %ws", a2);
      goto LABEL_223;
    }
    v61 = (wchar_t *)String1;
    if ( v145 > 7 )
      v61 = String1[0];
    if ( !AppCompatUtility::IsValidComparisonOperation(v61, v60) )
    {
      AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 245, "Operation type not supported, %ws", a2);
      goto LABEL_223;
    }
    v62 = v150;
    v63 = (const wchar_t *)v149;
    if ( v151 > 7 )
      v63 = v149[0];
    v64 = v150;
    if ( v150 > 3 )
      v64 = 3;
    if ( !wmemcmp(v63, L"int", v64) && v62 == 3 )
    {
      v65 = (const WCHAR *)pszString;
      if ( v163 > 7 )
        v65 = pszString[0];
      if ( !StrToInt64ExW(v65, 1, &pllRet) )
      {
        AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 253, "Convert ExpectedValue integer failed, %ws", a2);
        goto LABEL_223;
      }
    }
    v66 = v150;
    v67 = (const wchar_t *)v149;
    if ( v151 > 7 )
      v67 = v149[0];
    v68 = v150;
    if ( v150 > 7 )
      v68 = 7;
    if ( !wmemcmp(v67, L"wstring", v68) && v66 == 7 )
    {
      v69 = v144;
      v70 = (const wchar_t *)String1;
      if ( v145 > 7 )
        v70 = String1[0];
      v71 = v144;
      if ( v144 > 2 )
        v71 = 2;
      if ( wmemcmp(v70, L"eq", v71) || v69 != 2 )
      {
        v72 = v144;
        v73 = (const wchar_t *)String1;
        if ( v145 > 7 )
          v73 = String1[0];
        v74 = v144;
        if ( v144 > 2 )
          v74 = 2;
        if ( wmemcmp(v73, L"ne", v74) || v72 != 2 )
        {
          v75 = String1;
          if ( v145 > 7 )
            v75 = (wchar_t **)String1[0];
          AslLogCallPrintf(
            1,
            "WmiQueryMatchingPluginHelper",
            261,
            "Operation type not supported for string variable, %ws",
            v75);
          goto LABEL_223;
        }
      }
    }
    v76 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &v131);
    if ( v76 < 0 || (v77 = v131) == 0 )
    {
      LODWORD(ppva) = v76;
      AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 268, "0x%08x CoCreateInstance failed", ppva);
      goto LABEL_223;
    }
    v78 = *(_QWORD *)v131;
    if ( v154 <= 7 )
    {
      v79 = psz;
    }
    else
    {
      v79 = *(OLECHAR **)psz;
      if ( !*(_QWORD *)psz )
      {
        v80 = 0;
        v135[0] = 0;
        v81 = 0;
        goto LABEL_148;
      }
    }
    v82 = SysAllocString(v79);
    v80 = v82;
    v135[0] = v82;
    if ( !v82 )
      ATL::AtlThrowImpl(v83);
    v81 = v82;
LABEL_148:
    v84 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(v78 + 24))(
            v77,
            v81,
            0,
            0,
            0,
            0,
            0,
            0,
            &pProxy);
    SysFreeString(v80);
    if ( v84 < 0 || !pProxy )
    {
      v111 = psz;
      if ( v84 == -2147217394 )
      {
        v9 = 3;
        v112 = 281;
        v84 = -2147217394;
      }
      else
      {
        v112 = 277;
      }
      if ( v154 > 7 )
        v111 = *(OLECHAR **)psz;
      LODWORD(ppvb) = v84;
      AslLogCallPrintf(v9, "WmiQueryMatchingPluginHelper", v112, "0x%08x ConnectServer failed, %ws", ppvb, v111);
      goto LABEL_223;
    }
    if ( v142 < 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
    }
    else
    {
      v85 = Src;
      if ( v142 > 7 )
        v85 = (OLECHAR **)Src[0];
      v141 = 7;
      memmove_0(v85, L"SELECT ", 0xEu);
      *((_WORD *)v85 + 7) = 0;
    }
    v86 = v146;
    if ( v148 > 7 )
      v86 = (void **)v146[0];
    std::wstring::append(Src, v86);
    std::wstring::append(Src, L" FROM ");
    std::wstring::append(Src);
    if ( pNumArgs >= (int)(v6 + 9) )
    {
      v87 = v6 + 7;
      if ( !wcscmp_0(v14[v87], L"WHERE") )
      {
        while ( (int)v87 < pNumArgs )
        {
          std::wstring::append(Src, (void *)L" ");
          std::wstring::append(Src, (void *)v14[(int)v87]);
          LODWORD(v87) = v87 + 1;
        }
      }
      else
      {
        std::wstring::append(Src, L" WHERE ");
        std::wstring::append(Src, (void *)v14[v87]);
        std::wstring::append(Src, L" = \"");
        std::wstring::append(Src, (void *)v14[v6 + 8]);
        std::wstring::append(Src, (void *)L"\"");
      }
    }
    v88 = Src;
    if ( v142 > 7 )
      v88 = (OLECHAR **)Src[0];
    AslLogCallPrintf(3, "WmiQueryMatchingPluginHelper", 311, "Wql Query=%ws", v88);
    v89 = CoSetProxyBlanket(
            pProxy,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            0,
            3u,
            (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
            0x800u);
    if ( v89 < 0 )
    {
      AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 326, "0x%08x CoSetProxyBlanket failed", v89);
      goto LABEL_223;
    }
    if ( v142 <= 7 )
    {
      v90 = (const OLECHAR *)Src;
    }
    else
    {
      v90 = Src[0];
      if ( !Src[0] )
        goto LABEL_169;
    }
    SysFreeString(0);
    v7 = SysAllocString(v90);
    v137 = v7;
    if ( !v7 )
      ATL::AtlThrowImpl(v97);
LABEL_169:
    v91 = pProxy;
    lpVtbl = pProxy->lpVtbl;
    v93 = MultiByteToWideChar(3u, 0, "WQL", -1, 0, 0);
    v94 = SysAllocStringLen(0, v93 - 1);
    v95 = v94;
    v96 = 0;
    if ( v94 )
    {
      if ( MultiByteToWideChar(3u, 0, "WQL", -1, v94, v93) != v93 )
      {
        SysFreeString(v95);
        v135[0] = 0;
        goto LABEL_246;
      }
      v96 = 0;
    }
    v135[0] = v95;
    if ( v95 )
    {
      v98 = ((__int64 (__fastcall *)(IUnknown *, OLECHAR *, OLECHAR *, __int64, _QWORD, __int64 *))lpVtbl[6].Release)(
              v91,
              v95,
              v7,
              48,
              0,
              &v130);
      SysFreeString(v95);
      if ( v98 < 0 || (v99 = v130) == 0 )
      {
        v110 = Src;
        if ( v142 > 7 )
          v110 = (OLECHAR **)Src[0];
        LODWORD(ppvc) = v98;
        AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 338, "0x%08x ExecQuery failed, query:%ws", ppvc, v110);
        goto LABEL_223;
      }
      if ( v122 )
      {
        while ( 1 )
        {
          v100 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *, int *))(*(_QWORD *)v99 + 32LL))(
                   v99,
                   (unsigned int)piRet,
                   1,
                   &v128,
                   &v127);
          if ( v100 == 1 )
            goto LABEL_223;
          if ( v100 < 0 || !v127 )
            break;
          AslLogCallPrintf(3, "WmiQueryMatchingPluginHelper", 352, "Got a wmi object");
          v101 = v146;
          if ( v148 > 7 )
            v101 = (void **)v146[0];
          v102 = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v128 + 32LL))(
                   v128,
                   v101,
                   0,
                   &pvarg,
                   0,
                   0);
          if ( v102 < 0 )
          {
            v103 = v146;
            if ( v148 > 7 )
              v103 = (void **)v146[0];
            LODWORD(ppvd) = v102;
            AslLogCallPrintf(
              1,
              "WmiQueryMatchingPluginHelper",
              357,
              "0x%08x Failed to get the variable %ws",
              ppvd,
              v103);
            goto LABEL_193;
          }
          CompareResult(this, v149, &pvarg, pszString, pllRet, String1);
          if ( v128 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
            v128 = 0;
          }
          if ( *(_DWORD *)this )
            goto LABEL_193;
          v99 = v130;
        }
        AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 348, "0x%08x Failed to get the wmi object", v100);
LABEL_193:
        v104 = this;
        goto LABEL_224;
      }
      if ( v126 > 0 )
      {
        v105 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v130 + 56LL))(v130, (unsigned int)piRet);
        if ( v105 < 0 )
        {
          dwImpLevel[0] = v126;
          LODWORD(ppvc) = v105;
          AslLogCallPrintf(
            1,
            "WmiQueryMatchingPluginHelper",
            385,
            "0x%08x Failed to advance to the wmi object position %d",
            ppvc,
            *(_QWORD *)dwImpLevel);
          goto LABEL_223;
        }
        v99 = v130;
      }
      v106 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *, int *))(*(_QWORD *)v99 + 32LL))(
               v99,
               (unsigned int)piRet,
               1,
               &v128,
               &v127);
      if ( v106 )
      {
        if ( v106 != 1 )
        {
          v18 = 398;
          v17 = "0x%08x Failed to get the wmi object";
LABEL_210:
          LODWORD(ppv) = v106;
          goto LABEL_22;
        }
      }
      else if ( v127 )
      {
        v107 = v146;
        if ( v148 > 7 )
          v107 = (void **)v146[0];
        v108 = (*(__int64 (__fastcall **)(__int64, void **, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v128 + 32LL))(
                 v128,
                 v107,
                 0,
                 &pvarg,
                 0,
                 0);
        if ( v108 >= 0 )
        {
          v104 = this;
          CompareResult(this, v149, &pvarg, pszString, pllRet, String1);
LABEL_224:
          if ( v128 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
            v128 = 0;
          }
          if ( v14 )
            LocalFree(v14);
          if ( v159 )
          {
            v113 = v158;
            if ( v160 > 7 )
              LODWORD(v113) = v158[0];
            AppCompatUtility::AddCacheMatchingPlugin(
              (AppCompatUtility *)*(unsigned int *)v104,
              (int)v113,
              (const unsigned __int16 *)(unsigned int)v133,
              v16);
          }
          v114 = GetTickCount64();
          AslTelemetryTrackMetric(P, "WmiMatching_Ms", (unsigned int)(v114 - TickCount64));
          AslLogCallPrintf(
            3,
            "WmiQueryMatchingPluginHelper",
            439,
            "WmiQueryMatchingPlugin Matched = %d",
            *(_DWORD *)v104);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v132);
          VariantClear(&pvarg);
          std::wstring::~wstring(v158);
          std::wstring::~wstring(Src);
          std::wstring::~wstring(String1);
          std::wstring::~wstring(pszString);
          std::wstring::~wstring(v149);
          std::wstring::~wstring(v146);
          std::wstring::~wstring(S1);
          std::wstring::~wstring(v167);
          std::wstring::~wstring(psz);
          SysFreeString(v7);
          if ( pProxy )
            ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
          if ( v131 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v131 + 16LL))(v131);
          goto LABEL_241;
        }
        v109 = v146;
        if ( v148 > 7 )
          v109 = (void **)v146[0];
        LODWORD(ppve) = v108;
        AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 410, "0x%08x Failed to get the variable %ws", ppve, v109);
LABEL_223:
        v104 = this;
        goto LABEL_224;
      }
      v9 = 3;
      v18 = 402;
      v17 = "0x%08x No wmi object";
      goto LABEL_210;
    }
LABEL_246:
    ATL::AtlThrowImpl(v96);
  }
  AslLogCallPrintf(1, "WmiQueryMatchingPluginHelper", 158, "CommandLine is null/empty");
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v132);
  VariantClear(&pvarg);
  std::wstring::~wstring(v158);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(String1);
  std::wstring::~wstring(pszString);
  std::wstring::~wstring(v149);
  std::wstring::~wstring(v146);
  std::wstring::~wstring(S1);
  std::wstring::~wstring(v167);
  std::wstring::~wstring(psz);
  SysFreeString(0);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  if ( v131 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v131 + 16LL))(v131);
LABEL_241:
  if ( v130 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v130 + 16LL))(v130);
}

```

## disassembly

```asm
0x18000c974  mov     rax, rsp
0x18000c977  push    rbp
0x18000c978  push    rsi
0x18000c979  push    rdi
0x18000c97a  push    r12
0x18000c97c  push    r13
0x18000c97e  push    r14
0x18000c980  push    r15
0x18000c982  lea     rbp, [rax-188h]
0x18000c989  sub     rsp, 250h
0x18000c990  mov     [rbp+180h+var_188], 0FFFFFFFFFFFFFFFEh
0x18000c998  mov     [rax+18h], rbx
0x18000c99c  mov     rax, cs:__security_cookie
0x18000c9a3  xor     rax, rsp
0x18000c9a6  mov     [rbp+180h+var_40], rax
0x18000c9ad  mov     r15d, r8d
0x18000c9b0  mov     dword ptr [rbp+180h+var_1D0], r8d
0x18000c9b4  mov     r12, rdx
0x18000c9b7  mov     rdi, rcx
0x18000c9ba  mov     qword ptr [rsp+280h+var_218], rcx
0x18000c9bf  xor     r13d, r13d
0x18000c9c2  mov     [rbp+180h+var_1F0], r13
0x18000c9c6  mov     [rbp+180h+var_200], r13
0x18000c9ca  mov     [rbp+180h+var_1E8], r13
0x18000c9ce  mov     [rbp+180h+pProxy], r13
0x18000c9d2  mov     esi, r13d
0x18000c9d5  mov     [rbp+180h+var_198], r13
0x18000c9d9  mov     [rsp+280h+pNumArgs], r13d
0x18000c9de  xorps   xmm0, xmm0
0x18000c9e1  movups  xmmword ptr [rbp+180h+psz], xmm0
0x18000c9e8  mov     [rbp+180h+var_F0], r13
0x18000c9ef  lea     ebx, [r13+7]
0x18000c9f3  mov     [rbp+180h+var_E8], rbx
0x18000c9fa  mov     [rbp+180h+psz], r13w
0x18000ca02  movups  xmmword ptr [rbp+180h+var_60], xmm0
0x18000ca09  mov     [rbp+180h+var_50], r13
0x18000ca10  mov     [rbp+180h+var_48], rbx
0x18000ca17  mov     word ptr [rbp+180h+var_60], r13w
0x18000ca1f  movups  xmmword ptr [rbp+180h+S1], xmm0
0x18000ca26  mov     [rbp+180h+var_D0], r13
0x18000ca2d  mov     [rbp+180h+var_C8], rbx
0x18000ca34  mov     word ptr [rbp+180h+S1], r13w
0x18000ca3c  movups  xmmword ptr [rbp+180h+var_140], xmm0
0x18000ca40  mov     [rbp+180h+var_130], r13
0x18000ca44  mov     [rbp+180h+var_128], rbx
0x18000ca48  mov     word ptr [rbp+180h+var_140], r13w
0x18000ca4d  movups  xmmword ptr [rbp+180h+var_120], xmm0
0x18000ca51  mov     [rbp+180h+var_110], r13
0x18000ca55  mov     [rbp+180h+var_108], rbx
0x18000ca59  mov     word ptr [rbp+180h+var_120], r13w
0x18000ca5e  movups  xmmword ptr [rbp+180h+pszString], xmm0
0x18000ca65  mov     [rbp+180h+var_90], r13
0x18000ca6c  mov     [rbp+180h+var_88], rbx
0x18000ca73  mov     word ptr [rbp+180h+pszString], r13w
0x18000ca7b  movups  xmmword ptr [rbp+180h+String1], xmm0
0x18000ca7f  mov     [rbp+180h+var_150], r13
0x18000ca83  mov     [rbp+180h+var_148], rbx
0x18000ca87  mov     word ptr [rbp+180h+String1], r13w
0x18000ca8c  movups  xmmword ptr [rbp+180h+Src], xmm0
0x18000ca90  mov     [rbp+180h+var_170], r13
0x18000ca94  mov     [rbp+180h+var_168], rbx
0x18000ca98  mov     word ptr [rbp+180h+Src], r13w
0x18000ca9d  movups  xmmword ptr [rbp+180h+var_C0], xmm0
0x18000caa4  mov     [rbp+180h+var_B0], r13
0x18000caab  mov     [rbp+180h+var_A8], rbx
0x18000cab2  mov     word ptr [rbp+180h+var_C0], r13w
0x18000caba  mov     [rsp+280h+var_208], r13d
0x18000cabf  mov     [rsp+280h+var_204], r13d
0x18000cac4  lea     rcx, [rbp+180h+pvarg]; pvarg
0x18000cac8  call    cs:__imp_VariantInit
0x18000cace  nop
0x18000cacf  mov     [rbp+180h+pllRet], r13
0x18000cad3  call    cs:__imp_GetTickCount64
0x18000cad9  mov     [rbp+180h+var_190], rax
0x18000cadd  mov     [rbp+180h+var_1E0], r13
0x18000cae1  mov     [rbp+180h+var_1D8], r13
0x18000cae5  lea     ecx, [rbx+39h]; Size
0x18000cae8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000caed  mov     [rax], rax
0x18000caf0  mov     [rax+8], rax
0x18000caf4  mov     [rax+10h], rax
0x18000caf8  lea     r14d, [r13+1]
0x18000cafc  mov     word ptr [rax+18h], 101h
0x18000cb02  mov     [rbp+180h+var_1E0], rax
0x18000cb06  mov     [rsp+280h+piRet], 1770h
0x18000cb0e  mov     [rdi], r13d
0x18000cb11  lea     r9, aEnterWmiquerym; "Enter WmiQueryMatchingPlugin"
0x18000cb18  mov     r8d, 9Ah
0x18000cb1e  lea     rdx, aWmiquerymatchi_3; "WmiQueryMatchingPluginHelper"
0x18000cb25  lea     ecx, [rbx-4]
0x18000cb28  call    AslLogCallPrintf
0x18000cb2d  test    r12, r12
0x18000cb30  jz      loc_18000DC55
0x18000cb36  cmp     r13w, [r12]
0x18000cb3b  jz      loc_18000DC55
0x18000cb41  lea     edx, [rbx+10h]
0x18000cb44  cmp     [rbp+180h+var_A8], rdx
0x18000cb4b  jb      short loc_18000CB89
0x18000cb4d  lea     rbx, [rbp+180h+var_C0]
0x18000cb54  cmp     [rbp+180h+var_A8], 7
0x18000cb5c  cmova   rbx, [rbp+180h+var_C0]
0x18000cb64  mov     [rbp+180h+var_B0], rdx
0x18000cb6b  lea     r8d, [r13+2Eh]; Size
0x18000cb6f  lea     rdx, aWmiquerymatchi_2; "WmiQueryMatchingPlugin "
0x18000cb76  mov     rcx, rbx; void *
0x18000cb79  call    memmove_0
0x18000cb7e  mov     [rbx+2Eh], r13w
0x18000cb83  lea     ebx, [r13+7]
0x18000cb87  jmp     short loc_18000CB9C
0x18000cb89  lea     r9, aWmiquerymatchi_2; "WmiQueryMatchingPlugin "
0x18000cb90  lea     rcx, [rbp+180h+var_C0]
0x18000cb97  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000cb9c  mov     rdx, r12; void *
0x18000cb9f  lea     rcx, [rbp+180h+var_C0]; Src
0x18000cba6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000cbab  lea     rdx, [rbp+180h+var_C0]
0x18000cbb2  cmp     [rbp+180h+var_A8], rbx
0x18000cbb9  cmova   rdx, [rbp+180h+var_C0]; int *
0x18000cbc1  mov     r8d, r15d; unsigned __int16 *
0x18000cbc4  mov     rcx, rdi; this
0x18000cbc7  call    ?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z; AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)
0x18000cbcc  test    eax, eax
0x18000cbce  jz      loc_18000CC8C
0x18000cbd4  lea     rcx, [rbp+180h+var_1E0]
0x18000cbd8  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000cbdd  nop
0x18000cbde  lea     rcx, [rbp+180h+pvarg]; pvarg
0x18000cbe2  call    cs:__imp_VariantClear
0x18000cbe8  nop
0x18000cbe9  lea     rcx, [rbp+180h+var_C0]; void *
0x18000cbf0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cbf5  nop
0x18000cbf6  lea     rcx, [rbp+180h+Src]; void *
0x18000cbfa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cbff  nop
0x18000cc00  lea     rcx, [rbp+180h+String1]; void *
0x18000cc04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc09  nop
0x18000cc0a  lea     rcx, [rbp+180h+pszString]; void *
0x18000cc11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc16  nop
0x18000cc17  lea     rcx, [rbp+180h+var_120]; void *
0x18000cc1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc20  nop
0x18000cc21  lea     rcx, [rbp+180h+var_140]; void *
0x18000cc25  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc2a  nop
0x18000cc2b  lea     rcx, [rbp+180h+S1]; void *
0x18000cc32  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc37  nop
0x18000cc38  lea     rcx, [rbp+180h+var_60]; void *
0x18000cc3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc44  nop
0x18000cc45  lea     rcx, [rbp+180h+psz]; void *
0x18000cc4c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cc51  nop
0x18000cc52  xor     ecx, ecx; bstrString
0x18000cc54  call    cs:__imp_SysFreeString
0x18000cc5a  nop
0x18000cc5b  mov     rcx, [rbp+180h+pProxy]
0x18000cc5f  test    rcx, rcx
0x18000cc62  jz      short loc_18000CC71
0x18000cc64  mov     rax, [rcx]
0x18000cc67  mov     rax, [rax+10h]
0x18000cc6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc70  nop
0x18000cc71  mov     rcx, [rbp+180h+var_1E8]
0x18000cc75  test    rcx, rcx
0x18000cc78  jz      short loc_18000CC87
0x18000cc7a  mov     rax, [rcx]
0x18000cc7d  mov     rax, [rax+10h]
0x18000cc81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc86  nop
0x18000cc87  jmp     loc_18000DD25
0x18000cc8c  xorps   xmm0, xmm0
0x18000cc8f  movups  [rbp+180h+var_80], xmm0
0x18000cc96  mov     [rbp+180h+var_70], r13
0x18000cc9d  mov     [rbp+180h+var_68], r13
0x18000cca4  mov     r8d, 13h
0x18000ccaa  lea     rdx, aFreeformwherec; "FreeFormWhereClause"
0x18000ccb1  lea     rcx, [rbp+180h+var_80]
0x18000ccb8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ccbd  nop
0x18000ccbe  lea     r8, [rbp+180h+var_80]
0x18000ccc5  lea     rdx, [rbp+180h+var_1C0]
0x18000ccc9  lea     rcx, [rbp+180h+var_1E0]
0x18000cccd  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18000ccd2  nop
0x18000ccd3  lea     rcx, [rbp+180h+var_80]; void *
0x18000ccda  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ccdf  xorps   xmm0, xmm0
0x18000cce2  movups  [rbp+180h+var_80], xmm0
0x18000cce9  mov     [rbp+180h+var_70], r13
0x18000ccf0  mov     [rbp+180h+var_68], r13
0x18000ccf7  mov     r8d, 9
0x18000ccfd  lea     rdx, aWildindex; "WildIndex"
0x18000cd04  lea     rcx, [rbp+180h+var_80]
0x18000cd0b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cd10  nop
0x18000cd11  lea     r8, [rbp+180h+var_80]
0x18000cd18  lea     rdx, [rbp+180h+var_1C0]
0x18000cd1c  lea     rcx, [rbp+180h+var_1E0]
0x18000cd20  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18000cd25  nop
0x18000cd26  lea     rcx, [rbp+180h+var_80]; void *
0x18000cd2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cd32  xorps   xmm0, xmm0
0x18000cd35  movups  [rbp+180h+var_80], xmm0
0x18000cd3c  mov     [rbp+180h+var_70], r13
0x18000cd43  mov     [rbp+180h+var_68], r13
0x18000cd4a  mov     r8, rbx
0x18000cd4d  lea     rdx, aTimeout_1; "Timeout"
0x18000cd54  lea     rcx, [rbp+180h+var_80]
0x18000cd5b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000cd60  nop
0x18000cd61  lea     r8, [rbp+180h+var_80]
0x18000cd68  lea     rdx, [rbp+180h+var_1C0]
0x18000cd6c  lea     rcx, [rbp+180h+var_1E0]
0x18000cd70  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18000cd75  nop
0x18000cd76  lea     rcx, [rbp+180h+var_80]; void *
0x18000cd7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000cd82  lea     rdx, [rsp+280h+pNumArgs]; pNumArgs
0x18000cd87  mov     rcx, r12; lpCmdLine
0x18000cd8a  call    cs:__imp_CommandLineToArgvW
0x18000cd90  mov     r15, rax
0x18000cd93  mov     ebx, [rsp+280h+pNumArgs]
0x18000cd97  test    rax, rax
0x18000cd9a  jz      loc_18000DAD7
0x18000cda0  cmp     ebx, r14d
0x18000cda3  jl      loc_18000DAD7
0x18000cda9  mov     rdx, [rax]; String2
0x18000cdac  lea     rcx, aFeatures; "Features"
0x18000cdb3  call    wcscmp_0
0x18000cdb8  test    eax, eax
0x18000cdba  jnz     short loc_18000CDDA
0x18000cdbc  mov     r8, r15
0x18000cdbf  mov     edx, ebx
0x18000cdc1  lea     rcx, [rbp+180h+var_1E0]
0x18000cdc5  call    ?SupportAllFeatures@AppCompatUtility@@YA_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@HPEAPEAG@Z; AppCompatUtility::SupportAllFeatures(std::set<std::wstring> const &,int,ushort * *)
0x18000cdca  test    al, al
0x18000cdcc  jz      loc_18000DAFC
0x18000cdd2  mov     [rdi], r14d
0x18000cdd5  jmp     loc_18000DAFC
0x18000cdda  mov     rdx, [r15]; String2
0x18000cddd  lea     rcx, aTimeout_0; "-Timeout"
0x18000cde4  call    wcscmp_0
0x18000cde9  test    eax, eax
0x18000cdeb  jnz     short loc_18000CE61
0x18000cded  cmp     ebx, 9
0x18000cdf0  jge     short loc_18000CE17
0x18000cdf2  mov     dword ptr [rsp+280h+ppv], ebx
0x18000cdf6  lea     r9, aWrongArguments; "Wrong arguments number: %d"
0x18000cdfd  mov     r8d, 0C6h
0x18000ce03  lea     rdx, aWmiquerymatchi_3; "WmiQueryMatchingPluginHelper"
0x18000ce0a  mov     ecx, r14d
0x18000ce0d  call    AslLogCallPrintf
0x18000ce12  jmp     loc_18000DAFC
0x18000ce17  mov     r13d, 2
0x18000ce1d  lea     r8, [rsp+280h+piRet]; piRet
0x18000ce22  xor     edx, edx; dwFlags
0x18000ce24  mov     rcx, [r15+8]; pszString
0x18000ce28  call    cs:__imp_StrToIntExW
0x18000ce2e  xor     edi, edi
0x18000ce30  test    eax, eax
0x18000ce32  jnz     short loc_18000CE7B
0x18000ce34  mov     rax, [r15+8]
0x18000ce38  mov     [rsp+280h+ppv], rax
0x18000ce3d  lea     r9, aStrtointexFail_0; "StrToIntEx failed %ws"
0x18000ce44  mov     r8d, 0CCh
0x18000ce4a  lea     rdx, aWmiquerymatchi_3; "WmiQueryMatchingPluginHelper"
0x18000ce51  mov     ecx, r14d
0x18000ce54  call    AslLogCallPrintf
0x18000ce59  xor     r13d, r13d
0x18000ce5c  jmp     loc_18000DAFC
0x18000ce61  cmp     ebx, 7
0x18000ce64  jge     short loc_18000CE79
0x18000ce66  mov     dword ptr [rsp+280h+ppv], ebx
0x18000ce6a  lea     r9, aWrongArguments; "Wrong arguments number: %d"
0x18000ce71  mov     r8d, 0D2h
0x18000ce77  jmp     short loc_18000CE4A
0x18000ce79  xor     edi, edi
0x18000ce7b  mov     eax, r13d
0x18000ce7e  mov     r9, [r15+rax*8]
0x18000ce82  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000ce86  inc     rdx
0x18000ce89  cmp     [r9+rdx*2], di
0x18000ce8e  jnz     short loc_18000CE86
0x18000ce90  cmp     rdx, [rbp+180h+var_E8]
0x18000ce97  ja      short loc_18000CED3
0x18000ce99  lea     rdi, [rbp+180h+psz]
0x18000cea0  cmp     [rbp+180h+var_E8], 7
0x18000cea8  cmova   rdi, qword ptr [rbp+180h+psz]
0x18000ceb0  mov     [rbp+180h+var_F0], rdx
0x18000ceb7  lea     rbx, [rdx+rdx]
0x18000cebb  mov     r8, rbx; Size
0x18000cebe  mov     rdx, r9; Src
0x18000cec1  mov     rcx, rdi; void *
0x18000cec4  call    memmove_0
0x18000cec9  xor     eax, eax
  ... truncated ...
```
