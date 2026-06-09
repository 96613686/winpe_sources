# RegistryMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18000ef90`
- end: `0x180010673`
- name: `?RegistryMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `5859`
- prototype: `__int64 __usercall@<rax>(AppCompatUtility *this@<rcx>, void *@<rdx>, struct _DB *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x1800020c0`
- `0x180002120`
- `0x180002874`
- `0x18000a51c`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c190`
- `0x18000c3c8`
- `0x18000c534`
- `0x18000e0e4`
- `0x18000e5a4`
- `0x18000e7dc`
- `0x18000ef90`
- `0x18001067c`
- `0x18003f0b0`
- `0x18003fa7c`
- `0x180040854`
- `0x1800425fc`
- `0x180042ee8`
- `0x180044964`
- `0x1800514a8`
- `0x1800543c0`
- `0x180065120`
- `0x180065150`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fe03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001008d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000fe03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001008d`
- `KERNEL32!LocalFree` at `0x180010579`
- `KERNEL32!LocalFree` at `0x180010579`
- `KERNEL32!GetTickCount64` at `0x18000f013`
- `KERNEL32!GetTickCount64` at `0x1800105dd`
- `KERNEL32!GetTickCount64` at `0x18000f013`
- `KERNEL32!GetTickCount64` at `0x1800105dd`
- `ntdll!RtlFreeHeap` at `0x18001059e`
- `ntdll!RtlFreeHeap` at `0x18001059e`
- `SHLWAPI!StrToInt64ExW` at `0x18000fc55`
- `SHLWAPI!StrToInt64ExW` at `0x18000fc55`
- `SHELL32!CommandLineToArgvW` at `0x18000f32b`
- `SHELL32!CommandLineToArgvW` at `0x18000f32b`

## string_xrefs

- `0x180010624`: `CommandLine is null/empty`
- `0x1800104d0`: `CommandLineToArgvW failed, %ws, numArgs=%d`
- `0x18000f035`: `Enter RegistryMatchingPlugin`
- `0x18000f042`: `RegistryMatchingPlugin`
- `0x18001054a`: `RegistryMatchingPlugin`
- `0x1800105c8`: `RegistryMatchingPlugin`
- `0x18000f068`: `RegistryMatchingPlugin `
- `0x1800105ed`: `RegistryMatching_Ms`
- `0x180010608`: `RegistryMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall RegistryMatchingPlugin(
        AppCompatUtility *this,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *pszSrc,
        void *a7)
{
  AppCompatUtility *v7; // r13
  unsigned int v8; // r9d
  _QWORD *v9; // rax
  unsigned int v10; // r9d
  const wchar_t **v12; // rax
  const wchar_t **v13; // rdi
  int v14; // ebx
  const wchar_t *v15; // r13
  const wchar_t **v16; // r12
  unsigned __int64 v17; // r12
  unsigned __int64 v18; // rdx
  void **v19; // rdi
  __int64 v20; // rbx
  const wchar_t *v21; // r9
  unsigned __int64 v22; // rdx
  wchar_t **v23; // rdi
  __int64 v24; // rbx
  const wchar_t *v25; // r9
  unsigned __int64 v26; // rdx
  void **v27; // rdi
  __int64 v28; // rbx
  const wchar_t *v29; // r9
  unsigned __int64 v30; // rdx
  wchar_t **v31; // rdi
  __int64 v32; // rbx
  const wchar_t *v33; // r9
  unsigned __int64 v34; // rdx
  PCWSTR *v35; // rdi
  __int64 v36; // rbx
  const wchar_t *v37; // r9
  wchar_t **v38; // rdi
  PCWSTR *v39; // rdx
  void **v40; // rcx
  void **v41; // rax
  wchar_t **v42; // rdx
  wchar_t **v43; // rcx
  wchar_t **v44; // rax
  unsigned __int64 v45; // rbx
  const wchar_t *v46; // rcx
  size_t v47; // r8
  char v48; // r13
  unsigned __int64 v49; // rbx
  const wchar_t *v50; // rcx
  size_t v51; // r8
  wchar_t **v52; // rbx
  wchar_t *v53; // rdi
  unsigned __int64 v54; // r12
  const unsigned __int16 *v55; // rdx
  wchar_t **v56; // rax
  wchar_t *v57; // rcx
  unsigned __int64 v58; // rbx
  const wchar_t *v59; // rcx
  size_t v60; // r8
  wchar_t **v61; // rax
  unsigned __int64 v62; // rbx
  wchar_t **v63; // rcx
  size_t v64; // r8
  unsigned __int64 v65; // rbx
  const wchar_t *v66; // rcx
  size_t v67; // r8
  unsigned __int64 v68; // rbx
  const wchar_t *v69; // rcx
  size_t v70; // r8
  const WCHAR *v71; // rcx
  unsigned __int64 v72; // rbx
  const wchar_t *v73; // rcx
  size_t v74; // r8
  wchar_t **v75; // rax
  int v76; // edi
  unsigned __int64 v77; // rbx
  const wchar_t *v78; // rcx
  size_t v79; // r8
  unsigned __int64 v80; // rbx
  const wchar_t *v81; // rcx
  size_t v82; // r8
  unsigned __int64 v83; // rbx
  const wchar_t *v84; // rcx
  size_t v85; // r8
  unsigned __int64 v86; // rbx
  const wchar_t *v87; // rcx
  size_t v88; // r8
  wchar_t **v89; // rax
  wchar_t **v90; // rax
  int v91; // eax
  __int64 v92; // rcx
  void *AllSubkeys; // rbx
  __int64 v94; // r8
  unsigned __int64 v95; // [rsp+20h] [rbp-7F8h]
  char v96; // [rsp+60h] [rbp-7B8h]
  const wchar_t **hMem; // [rsp+68h] [rbp-7B0h]
  int pNumArgs; // [rsp+70h] [rbp-7A8h] BYREF
  _QWORD v99[2]; // [rsp+78h] [rbp-7A0h] BYREF
  AppCompatUtility *v100; // [rsp+88h] [rbp-790h]
  __int64 v101; // [rsp+90h] [rbp-788h] BYREF
  PVOID P; // [rsp+98h] [rbp-780h] BYREF
  struct AppCompatUtility::_RegexCondition *v103; // [rsp+A0h] [rbp-778h] BYREF
  LONGLONG pllRet; // [rsp+A8h] [rbp-770h] BYREF
  AppCompatUtility *v105; // [rsp+B0h] [rbp-768h]
  const unsigned __int16 *v106; // [rsp+B8h] [rbp-760h]
  ULONGLONG TickCount64; // [rsp+C0h] [rbp-758h]
  __int64 v108; // [rsp+C8h] [rbp-750h]
  _BYTE v109[16]; // [rsp+D0h] [rbp-748h] BYREF
  wchar_t *v110[2]; // [rsp+E0h] [rbp-738h] BYREF
  unsigned __int64 v111; // [rsp+F0h] [rbp-728h]
  unsigned __int64 v112; // [rsp+F8h] [rbp-720h]
  wchar_t *String1[2]; // [rsp+100h] [rbp-718h] BYREF
  unsigned __int64 v114; // [rsp+110h] [rbp-708h]
  unsigned __int64 v115; // [rsp+118h] [rbp-700h]
  wchar_t *S1[2]; // [rsp+120h] [rbp-6F8h] BYREF
  unsigned __int64 v117; // [rsp+130h] [rbp-6E8h]
  unsigned __int64 v118; // [rsp+138h] [rbp-6E0h]
  PCWSTR pszString[2]; // [rsp+140h] [rbp-6D8h] BYREF
  unsigned __int64 v120; // [rsp+150h] [rbp-6C8h]
  unsigned __int64 v121; // [rsp+158h] [rbp-6C0h]
  void *v122[2]; // [rsp+160h] [rbp-6B8h] BYREF
  unsigned __int64 v123; // [rsp+170h] [rbp-6A8h]
  unsigned __int64 v124; // [rsp+178h] [rbp-6A0h]
  void *v125[2]; // [rsp+180h] [rbp-698h] BYREF
  unsigned __int64 v126; // [rsp+190h] [rbp-688h]
  unsigned __int64 v127; // [rsp+198h] [rbp-680h]
  __int128 v128; // [rsp+1A0h] [rbp-678h] BYREF
  __int64 v129; // [rsp+1B0h] [rbp-668h]
  __int64 v130; // [rsp+1B8h] [rbp-660h]
  int pszDest[392]; // [rsp+1C0h] [rbp-658h] BYREF

  v108 = -2;
  v7 = this;
  v100 = this;
  v105 = this;
  v106 = pszSrc;
  pNumArgs = 0;
  pllRet = 0;
  v101 = 0;
  memset_0(pszDest, 0, 0x618u);
  TickCount64 = GetTickCount64();
  P = 0;
  v103 = 0;
  *(_DWORD *)v7 = 0;
  AslLogCallPrintf(3, "RegistryMatchingPlugin", 515, "Enter RegistryMatchingPlugin");
  if ( pszSrc && *pszSrc )
  {
    if ( StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x30Cu, L"RegistryMatchingPlugin ") < 0 )
    {
      AslLogCallPrintf(1, "RegistryMatchingPlugin", 526, "StringCchCatW failed.");
LABEL_198:
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
        AslLogCallPrintf(1, "RegistryMatchingPlugin", 734, "Unhandled exception");
        v7 = v105;
      }
      v94 = (unsigned int)GetTickCount64() - (unsigned int)TickCount64;
      AslTelemetryTrackMetric(::P, "RegistryMatching_Ms", v94);
      AslLogCallPrintf(3, "RegistryMatchingPlugin", 740, "RegistryMatchingPlugin Matched = %d", *(_DWORD *)v7);
      return 1;
    }
    v96 = 0;
    if ( StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x30Cu, pszSrc) < 0 )
    {
      AslLogCallPrintf(1, "RegistryMatchingPlugin", 533, "StringCchCatW failed; %ws", pszSrc);
      goto LABEL_198;
    }
    *(_OWORD *)v122 = 0;
    v123 = 0;
    v124 = 7;
    LOWORD(v122[0]) = 0;
    *(_OWORD *)v125 = 0;
    v126 = 0;
    v127 = 7;
    LOWORD(v125[0]) = 0;
    *(_OWORD *)String1 = 0;
    v114 = 0;
    v115 = 7;
    LOWORD(String1[0]) = 0;
    *(_OWORD *)pszString = 0;
    v120 = 0;
    v121 = 7;
    LOWORD(pszString[0]) = 0;
    *(_OWORD *)v110 = 0;
    v111 = 0;
    v112 = 7;
    LOWORD(v110[0]) = 0;
    *(_OWORD *)S1 = 0;
    v117 = 0;
    v118 = 7;
    LOWORD(S1[0]) = 0;
    v99[1] = 0;
    v9 = operator new(0x40u);
    *v9 = v9;
    v9[1] = v9;
    v9[2] = v9;
    *((_WORD *)v9 + 12) = 257;
    v99[0] = v9;
    if ( (unsigned int)AppCompatUtility::CheckCacheMatchingPlugin(v7, pszDest, (const unsigned __int16 *)a5, v10) )
    {
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v110);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(String1);
      std::wstring::~wstring(v125);
      std::wstring::~wstring(v122);
      return 1;
    }
    v128 = 0;
    v129 = 0;
    v130 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v128, L"MultiSz", 7);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v99,
      v109,
      &v128);
    std::wstring::~wstring(&v128);
    v128 = 0;
    v129 = 0;
    v130 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v128, L"RegexExpectedData", 17);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v99,
      v109,
      &v128);
    std::wstring::~wstring(&v128);
    v12 = (const wchar_t **)CommandLineToArgvW(pszSrc, &pNumArgs);
    v13 = v12;
    hMem = v12;
    v14 = pNumArgs;
    if ( v12 && pNumArgs >= 1 )
    {
      v15 = *v12;
      if ( !wcscmp_0(L"Features", *v12) )
      {
        if ( (unsigned __int8)AppCompatUtility::SupportAllFeatures(v99, (unsigned int)v14, v13) )
          *(_DWORD *)v100 = 1;
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v110);
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(String1);
        std::wstring::~wstring(v125);
        std::wstring::~wstring(v122);
        v16 = hMem;
        goto LABEL_191;
      }
      if ( v14 >= 6 )
      {
        v17 = -1;
        v18 = -1;
        do
          ++v18;
        while ( v15[v18] );
        if ( v18 > v124 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v122);
        }
        else
        {
          v19 = v122;
          if ( v124 > 7 )
            v19 = (void **)v122[0];
          v123 = v18;
          v20 = 2 * v18;
          memmove_0(v19, v15, 2 * v18);
          *(_WORD *)((char *)v19 + v20) = 0;
          v13 = hMem;
        }
        v21 = v13[1];
        v22 = -1;
        do
          ++v22;
        while ( v21[v22] );
        if ( v22 > v118 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(S1);
        }
        else
        {
          v23 = S1;
          if ( v118 > 7 )
            v23 = (wchar_t **)S1[0];
          v117 = v22;
          v24 = 2 * v22;
          memmove_0(v23, v21, 2 * v22);
          *(_WORD *)((char *)v23 + v24) = 0;
          v13 = hMem;
        }
        v25 = v13[2];
        v26 = -1;
        do
          ++v26;
        while ( v25[v26] );
        if ( v26 > v127 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v125);
        }
        else
        {
          v27 = v125;
          if ( v127 > 7 )
            v27 = (void **)v125[0];
          v126 = v26;
          v28 = 2 * v26;
          memmove_0(v27, v25, 2 * v26);
          *(_WORD *)((char *)v27 + v28) = 0;
          v13 = hMem;
        }
        v29 = v13[3];
        v30 = -1;
        do
          ++v30;
        while ( v29[v30] );
        if ( v30 > v112 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v110);
        }
        else
        {
          v31 = v110;
          if ( v112 > 7 )
            v31 = (wchar_t **)v110[0];
          v111 = v30;
          v32 = 2 * v30;
          memmove_0(v31, v29, 2 * v30);
          *(_WORD *)((char *)v31 + v32) = 0;
          v13 = hMem;
        }
        v33 = v13[4];
        v34 = -1;
        do
          ++v34;
        while ( v33[v34] );
        if ( v34 > v121 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(pszString);
        }
        else
        {
          v35 = pszString;
          if ( v121 > 7 )
            v35 = (PCWSTR *)pszString[0];
          v120 = v34;
          v36 = 2 * v34;
          memmove_0(v35, v33, 2 * v34);
          *(_WORD *)((char *)v35 + v36) = 0;
          v13 = hMem;
        }
        v37 = v13[5];
        do
          ++v17;
        while ( v37[v17] );
        if ( v17 > v115 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(String1);
        }
        else
        {
          v38 = String1;
          if ( v115 > 7 )
            v38 = (wchar_t **)String1[0];
          v114 = v17;
          memmove_0(v38, v37, 2 * v17);
          *((_WORD *)v38 + v17) = 0;
        }
        v39 = pszString;
        if ( v121 > 7 )
          v39 = (PCWSTR *)pszString[0];
        v40 = v125;
        if ( v127 > 7 )
          v40 = (void **)v125[0];
        v41 = v122;
        if ( v124 > 7 )
          v41 = (void **)v122[0];
        AslLogCallPrintf(3, "RegistryMatchingPlugin", 585, "RegKey=%ws;RegValueName=%ws;Expected=%ws", v41, v40, v39);
        v42 = v110;
        if ( v112 > 7 )
          v42 = (wchar_t **)v110[0];
        v43 = String1;
        if ( v115 > 7 )
          v43 = (wchar_t **)String1[0];
        v44 = S1;
        if ( v118 > 7 )
          v44 = (wchar_t **)S1[0];
        AslLogCallPrintf(
          3,
          "RegistryMatchingPlugin",
          586,
          "KeyOrValue=%ws;RegValueType=%ws;Operation=%ws",
          v44,
          v43,
          v42);
        if ( v123 )
        {
          v45 = v117;
          v46 = (const wchar_t *)S1;
          if ( v118 > 7 )
            v46 = S1[0];
          v47 = v117;
          if ( v117 > 9 )
            v47 = 9;
          if ( !wmemcmp(v46, L"KeySearch", v47) && v45 == 9 )
          {
            v48 = 1;
          }
          else
          {
            v49 = v117;
            v50 = (const wchar_t *)S1;
            if ( v118 > 7 )
              v50 = S1[0];
            v51 = v117;
            if ( v117 > 0xB )
              v51 = 11;
            if ( wmemcmp(v50, L"ValueSearch", v51) || v49 != 11 )
            {
              AslLogCallPrintf(1, "RegistryMatchingPlugin", 608, "Missing KeySearch or ValueSearch");
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
              std::wstring::~wstring(S1);
              std::wstring::~wstring(v110);
              std::wstring::~wstring(pszString);
              std::wstring::~wstring(String1);
              std::wstring::~wstring(v125);
              std::wstring::~wstring(v122);
              v16 = hMem;
              goto LABEL_191;
            }
            v48 = 0;
          }
          v52 = String1;
          v53 = String1[0];
          v54 = v115;
          if ( v115 > 7 )
            v52 = (wchar_t **)String1[0];
          if ( !wcscmp_0((const wchar_t *)v52, L"REG_DWORD")
            || !wcscmp_0((const wchar_t *)v52, L"REG_QWORD")
            || !wcscmp_0((const wchar_t *)v52, L"REG_SZ")
            || !wcscmp_0((const wchar_t *)v52, L"REG_EXPAND_SZ")
            || !wcscmp_0((const wchar_t *)v52, L"REG_MULTI_SZ")
            || *(_WORD *)v52 == 78 && *((_WORD *)v52 + 1) == 65 && !*((_WORD *)v52 + 2) )
          {
            v57 = (wchar_t *)v110;
            if ( v112 > 7 )
              v57 = v110[0];
            if ( !AppCompatUtility::IsValidComparisonOperation(v57, v55) )
            {
              v58 = v111;
              v59 = (const wchar_t *)v110;
              if ( v112 > 7 )
                v59 = v110[0];
              v60 = v111;
              if ( v111 > 9 )
                v60 = 9;
              if ( wmemcmp(v59, L"count_gte", v60) || v58 != 9 )
              {
                v61 = v110;
                if ( v112 > 7 )
                  v61 = (wchar_t **)v110[0];
                AslLogCallPrintf(1, "RegistryMatchingPlugin", 620, "Operation type not supported, %ws", v61);
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
                std::wstring::~wstring(S1);
                std::wstring::~wstring(v110);
                std::wstring::~wstring(pszString);
                std::wstring::~wstring(String1);
                std::wstring::~wstring(v125);
                std::wstring::~wstring(v122);
                v16 = hMem;
                goto LABEL_191;
              }
              v54 = v115;
              v53 = String1[0];
            }
            v62 = v114;
            v63 = String1;
            if ( v54 > 7 )
              v63 = (wchar_t **)v53;
            v64 = v114;
            if ( v114 > 9 )
              v64 = 9;
            if ( wmemcmp((const wchar_t *)v63, L"REG_DWORD", v64) || v62 != 9 )
            {
              v65 = v114;
              v66 = (const wchar_t *)String1;
              if ( v115 > 7 )
                v66 = String1[0];
              v67 = v114;
              if ( v114 > 9 )
                v67 = 9;
              if ( wmemcmp(v66, L"REG_QWORD", v67) || v65 != 9 )
              {
                v68 = v111;
                v69 = (const wchar_t *)v110;
                if ( v112 > 7 )
                  v69 = v110[0];
                v70 = v111;
                if ( v111 > 9 )
                  v70 = 9;
                if ( wmemcmp(v69, L"count_gte", v70) || v68 != 9 )
                  goto LABEL_141;
              }
            }
            v71 = (const WCHAR *)pszString;
            if ( v121 > 7 )
              v71 = pszString[0];
            if ( !StrToInt64ExW(v71, 1, &pllRet) )
            {
              AslLogCallPrintf(1, "RegistryMatchingPlugin", 629, "Convert ExpectedData integer failed, %ws", v106);
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
              std::wstring::~wstring(S1);
              std::wstring::~wstring(v110);
              std::wstring::~wstring(pszString);
              std::wstring::~wstring(String1);
              std::wstring::~wstring(v125);
              std::wstring::~wstring(v122);
              v16 = hMem;
            }
            else
            {
LABEL_141:
              if ( !v48 )
                goto LABEL_145;
              v72 = v111;
              v73 = (const wchar_t *)v110;
              if ( v112 > 7 )
                v73 = v110[0];
              v74 = v111;
              if ( v111 > 9 )
                v74 = 9;
              if ( !wmemcmp(v73, L"count_gte", v74) && v72 == 9 )
              {
LABEL_145:
                v76 = 6;
                v16 = hMem;
                while ( v76 < pNumArgs )
                {
                  if ( (unsigned int)_o__wcsicmp(L"-ExpectedDataIsRegex", hMem[v76]) )
                  {
                    if ( (unsigned int)_o__wcsicmp(L"-RegexConditions", hMem[v76]) )
                    {
                      AslLogCallPrintf(1, "RegistryMatchingPlugin", 682, "Unexpected argument: %ws", hMem[v76]);
                      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
                      std::wstring::~wstring(S1);
                      std::wstring::~wstring(v110);
                      std::wstring::~wstring(pszString);
                      std::wstring::~wstring(String1);
                      std::wstring::~wstring(v125);
                      std::wstring::~wstring(v122);
                      goto LABEL_191;
                    }
                    v91 = AppCompatUtility::ParseRegexConditions(
                            (AppCompatUtility *)&P,
                            &v103,
                            (unsigned __int64 *)&hMem[v76 + 1],
                            (unsigned __int16 **)(pNumArgs - v76 - 1),
                            v95);
                    if ( v91 )
                    {
                      AslLogCallPrintf(1, "RegistryMatchingPlugin", 671, "Failed to parse RegexConditions. [0x%x]", v91);
                      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
                      std::wstring::~wstring(S1);
                      std::wstring::~wstring(v110);
                      std::wstring::~wstring(pszString);
                      std::wstring::~wstring(String1);
                      std::wstring::~wstring(v125);
                      std::wstring::~wstring(v122);
                      goto LABEL_191;
                    }
                    break;
                  }
                  v77 = v111;
                  v78 = (const wchar_t *)v110;
                  if ( v112 > 7 )
                    v78 = v110[0];
                  v79 = v111;
                  if ( v111 > 2 )
                    v79 = 2;
                  if ( wmemcmp(v78, L"eq", v79) || v77 != 2 )
                  {
                    v90 = v110;
                    if ( v112 > 7 )
                      v90 = (wchar_t **)v110[0];
                    AslLogCallPrintf(
                      1,
                      "RegistryMatchingPlugin",
                      649,
                      "Operation type not supported when using -ExpectedDataIsRegex, '%ws'. Must be 'eq'.",
                      v90);
                    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
                    std::wstring::~wstring(S1);
                    std::wstring::~wstring(v110);
                    std::wstring::~wstring(pszString);
                    std::wstring::~wstring(String1);
                    std::wstring::~wstring(v125);
                    std::wstring::~wstring(v122);
                    goto LABEL_191;
                  }
                  v80 = v114;
                  v81 = (const wchar_t *)String1;
                  if ( v115 > 7 )
                    v81 = String1[0];
                  v82 = v114;
                  if ( v114 > 6 )
                    v82 = 6;
                  if ( wmemcmp(v81, L"REG_SZ", v82) || v80 != 6 )
                  {
                    v83 = v114;
                    v84 = (const wchar_t *)String1;
                    if ( v115 > 7 )
                      v84 = String1[0];
                    v85 = v114;
                    if ( v114 > 0xD )
                      v85 = 13;
                    if ( wmemcmp(v84, L"REG_EXPAND_SZ", v85) || v83 != 13 )
                    {
                      v86 = v114;
                      v87 = (const wchar_t *)String1;
                      if ( v115 > 7 )
                        v87 = String1[0];
                      v88 = v114;
                      if ( v114 > 0xC )
                        v88 = 12;
                      if ( wmemcmp(v87, L"REG_MULTI_SZ", v88) || v86 != 12 )
                      {
                        v89 = v110;
                        if ( v112 > 7 )
                          v89 = (wchar_t **)v110[0];
                        AslLogCallPrintf(
                          1,
                          "RegistryMatchingPlugin",
                          656,
                          "Value type not supported when using -ExpectedDataIsRegex, '%ws'. Must be 'REG_SZ', 'REG_EXPAND"
                          "_SZ or 'REG_MULTI_SZ''.",
                          v89);
                        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
                        std::wstring::~wstring(S1);
                        std::wstring::~wstring(v110);
                        std::wstring::~wstring(pszString);
                        std::wstring::~wstring(String1);
                        std::wstring::~wstring(v125);
                        std::wstring::~wstring(v122);
                        goto LABEL_191;
                      }
                    }
                  }
                  v96 = 1;
                  ++v76;
                }
                if ( (unsigned __int8)GetRootKey(v122, &v101) )
                {
                  AllSubkeys = (void *)AppCompatUtility::GetAllSubkeys(v122, v101);
                  if ( AllSubkeys )
                  {
                    LOBYTE(v92) = v48;
                    GetMatchResult(v92, v101, AllSubkeys, v110, v125, String1, pszString, pllRet, v96, P, v103, v100);
                    std::vector<std::wstring>::_Tidy(AllSubkeys);
                    operator delete(AllSubkeys);
                  }
                }
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
                std::wstring::~wstring(S1);
                std::wstring::~wstring(v110);
                std::wstring::~wstring(pszString);
                std::wstring::~wstring(String1);
                std::wstring::~wstring(v125);
                std::wstring::~wstring(v122);
              }
              else
              {
                v75 = v110;
                if ( v112 > 7 )
                  v75 = (wchar_t **)v110[0];
                AslLogCallPrintf(
                  1,
                  "RegistryMatchingPlugin",
                  636,
                  "For key search, the only operation should be count_gte, %ws",
                  v75);
                std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
                std::wstring::~wstring(S1);
                std::wstring::~wstring(v110);
                std::wstring::~wstring(pszString);
                std::wstring::~wstring(String1);
                std::wstring::~wstring(v125);
                std::wstring::~wstring(v122);
                v16 = hMem;
              }
            }
            goto LABEL_191;
          }
          v56 = String1;
          if ( v54 > 7 )
            v56 = (wchar_t **)v53;
          AslLogCallPrintf(1, "RegistryMatchingPlugin", 614, "Reg value type not supported, %ws", v56);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
          std::wstring::~wstring(S1);
          std::wstring::~wstring(v110);
          std::wstring::~wstring(pszString);
          std::wstring::~wstring(String1);
          std::wstring::~wstring(v125);
          std::wstring::~wstring(v122);
          v16 = hMem;
        }
        else
        {
          AslLogCallPrintf(1, "RegistryMatchingPlugin", 594, "Empty RegKey.");
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
          std::wstring::~wstring(S1);
          std::wstring::~wstring(v110);
          std::wstring::~wstring(pszString);
          std::wstring::~wstring(String1);
          std::wstring::~wstring(v125);
          std::wstring::~wstring(v122);
          v16 = hMem;
        }
      }
      else
      {
        AslLogCallPrintf(1, "RegistryMatchingPlugin", 574, "Wrong arguments number: %d", v14);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
        std::wstring::~wstring(S1);
        std::wstring::~wstring(v110);
        std::wstring::~wstring(pszString);
        std::wstring::~wstring(String1);
        std::wstring::~wstring(v125);
        std::wstring::~wstring(v122);
        v16 = hMem;
      }
    }
    else
    {
      AslLogCallPrintf(1, "RegistryMatchingPlugin", 560, "CommandLineToArgvW failed, %ws, numArgs=%d", pszSrc, pNumArgs);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v99);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v110);
      std::wstring::~wstring(pszString);
      std::wstring::~wstring(String1);
      std::wstring::~wstring(v125);
      std::wstring::~wstring(v122);
      if ( !v13 )
      {
LABEL_192:
        if ( P )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        v7 = v100;
        goto LABEL_198;
      }
      v16 = hMem;
    }
LABEL_191:
    LocalFree(v16);
    goto LABEL_192;
  }
  AslLogCallPrintf(1, "RegistryMatchingPlugin", 519, "CommandLine is null/empty");
  return 1;
}

```

## disassembly

```asm
0x18000ef90  mov     r11, rsp
0x18000ef93  push    rdi
0x18000ef94  push    r12
0x18000ef96  push    r13
0x18000ef98  push    r14
0x18000ef9a  push    r15
0x18000ef9c  sub     rsp, 7F0h
0x18000efa3  mov     qword ptr [r11-750h], 0FFFFFFFFFFFFFFFEh
0x18000efae  mov     [r11+10h], rbx
0x18000efb2  mov     [r11+18h], rsi
0x18000efb6  mov     rax, cs:__security_cookie
0x18000efbd  xor     rax, rsp
0x18000efc0  mov     [rsp+818h+var_38], rax
0x18000efc8  mov     r13, rcx
0x18000efcb  mov     [rsp+818h+var_790], rcx
0x18000efd3  mov     [rsp+818h+var_768], rcx
0x18000efdb  mov     r12, [rsp+818h+pszSrc]
0x18000efe3  mov     [rsp+818h+var_760], r12
0x18000efeb  xor     esi, esi
0x18000efed  mov     [rsp+818h+pNumArgs], esi
0x18000eff1  mov     [r11-770h], rsi
0x18000eff8  mov     [r11-788h], rsi
0x18000efff  xor     edx, edx; Val
0x18000f001  mov     r8d, 618h; Size
0x18000f007  lea     rcx, [r11-658h]; void *
0x18000f00e  call    memset_0
0x18000f013  call    cs:__imp_GetTickCount64
0x18000f019  mov     [rsp+818h+var_758], rax
0x18000f021  mov     [rsp+818h+P], rsi
0x18000f029  mov     [rsp+818h+var_778], rsi
0x18000f031  mov     [r13+0], esi
0x18000f035  lea     r9, aEnterRegistrym_0; "Enter RegistryMatchingPlugin"
0x18000f03c  mov     r8d, 203h
0x18000f042  lea     r15, aRegistrymatchi_1; "RegistryMatchingPlugin"
0x18000f049  mov     rdx, r15
0x18000f04c  lea     ecx, [rsi+3]
0x18000f04f  call    AslLogCallPrintf
0x18000f054  test    r12, r12
0x18000f057  jz      loc_180010624
0x18000f05d  cmp     si, [r12]
0x18000f062  jz      loc_180010624
0x18000f068  lea     r8, aRegistrymatchi; "RegistryMatchingPlugin "
0x18000f06f  mov     ebx, 30Ch
0x18000f074  mov     edx, ebx; cchDest
0x18000f076  lea     rcx, [rsp+818h+pszDest]; pszDest
0x18000f07e  call    StringCchCatW
0x18000f083  test    eax, eax
0x18000f085  jns     short loc_18000F0A8
0x18000f087  lea     r9, aStringcchcatwF_0; "StringCchCatW failed."
0x18000f08e  mov     r8d, 20Eh
0x18000f094  mov     rdx, r15
0x18000f097  lea     r14d, [rsi+1]
0x18000f09b  mov     ecx, r14d
0x18000f09e  call    AslLogCallPrintf
0x18000f0a3  jmp     loc_1800105AC
0x18000f0a8  mov     [rsp+818h+hMem], rsi
0x18000f0ad  mov     [rsp+818h+var_7B8], sil
0x18000f0b2  mov     r8, r12; pszSrc
0x18000f0b5  mov     rdx, rbx; cchDest
0x18000f0b8  lea     rcx, [rsp+818h+pszDest]; pszDest
0x18000f0c0  call    StringCchCatW
0x18000f0c5  test    eax, eax
0x18000f0c7  jns     short loc_18000F0F1
0x18000f0c9  mov     [rsp+818h+var_7F8], r12
0x18000f0ce  lea     r9, aStringcchcatwF; "StringCchCatW failed; %ws"
0x18000f0d5  mov     r8d, 215h
0x18000f0db  mov     rdx, r15
0x18000f0de  mov     r14d, 1
0x18000f0e4  mov     ecx, r14d
0x18000f0e7  call    AslLogCallPrintf
0x18000f0ec  jmp     loc_1800105AC
0x18000f0f1  xorps   xmm0, xmm0
0x18000f0f4  movups  xmmword ptr [rsp+818h+var_6B8], xmm0
0x18000f0fc  mov     [rsp+818h+var_6A8], rsi
0x18000f104  mov     ebx, 7
0x18000f109  mov     [rsp+818h+var_6A0], rbx
0x18000f111  mov     word ptr [rsp+818h+var_6B8], si
0x18000f119  movups  xmmword ptr [rsp+818h+var_698], xmm0
0x18000f121  mov     [rsp+818h+var_688], rsi
0x18000f129  mov     [rsp+818h+var_680], rbx
0x18000f131  mov     word ptr [rsp+818h+var_698], si
0x18000f139  movups  xmmword ptr [rsp+818h+String1], xmm0
0x18000f141  mov     [rsp+818h+var_708], rsi
0x18000f149  mov     [rsp+818h+var_700], rbx
0x18000f151  mov     word ptr [rsp+818h+String1], si
0x18000f159  movups  xmmword ptr [rsp+818h+pszString], xmm0
0x18000f161  mov     [rsp+818h+var_6C8], rsi
0x18000f169  mov     [rsp+818h+var_6C0], rbx
0x18000f171  mov     word ptr [rsp+818h+pszString], si
0x18000f179  movups  xmmword ptr [rsp+818h+var_738], xmm0
0x18000f181  mov     [rsp+818h+var_728], rsi
0x18000f189  mov     [rsp+818h+var_720], rbx
0x18000f191  mov     word ptr [rsp+818h+var_738], si
0x18000f199  movups  xmmword ptr [rsp+818h+S1], xmm0
0x18000f1a1  mov     [rsp+818h+var_6E8], rsi
0x18000f1a9  mov     [rsp+818h+var_6E0], rbx
0x18000f1b1  mov     word ptr [rsp+818h+S1], si
0x18000f1b9  mov     [rsp+818h+var_7A0], rsi
0x18000f1be  mov     [rsp+818h+var_798], rsi
0x18000f1c6  lea     ecx, [rbx+39h]; Size
0x18000f1c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f1ce  mov     [rax], rax
0x18000f1d1  mov     [rax+8], rax
0x18000f1d5  mov     [rax+10h], rax
0x18000f1d9  lea     r14d, [rbx-6]
0x18000f1dd  mov     word ptr [rax+18h], 101h
0x18000f1e3  mov     [rsp+818h+var_7A0], rax
0x18000f1e8  mov     r8d, dword ptr [rsp+818h+arg_20]; unsigned __int16 *
0x18000f1f0  lea     rdx, [rsp+818h+pszDest]; int *
0x18000f1f8  mov     rcx, r13; this
0x18000f1fb  call    ?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z; AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)
0x18000f200  test    eax, eax
0x18000f202  jz      short loc_18000F26A
0x18000f204  lea     rcx, [rsp+818h+var_7A0]
0x18000f209  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000f20e  nop
0x18000f20f  lea     rcx, [rsp+818h+S1]; void *
0x18000f217  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f21c  nop
0x18000f21d  lea     rcx, [rsp+818h+var_738]; void *
0x18000f225  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f22a  nop
0x18000f22b  lea     rcx, [rsp+818h+pszString]; void *
0x18000f233  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f238  nop
0x18000f239  lea     rcx, [rsp+818h+String1]; void *
0x18000f241  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f246  nop
0x18000f247  lea     rcx, [rsp+818h+var_698]; void *
0x18000f24f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f254  nop
0x18000f255  lea     rcx, [rsp+818h+var_6B8]; void *
0x18000f25d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f262  mov     eax, r14d
0x18000f265  jmp     loc_180010645
0x18000f26a  xorps   xmm0, xmm0
0x18000f26d  movups  [rsp+818h+var_678], xmm0
0x18000f275  mov     [rsp+818h+var_668], rsi
0x18000f27d  mov     [rsp+818h+var_660], rsi
0x18000f285  mov     r8, rbx
0x18000f288  lea     rdx, aMultisz; "MultiSz"
0x18000f28f  lea     rcx, [rsp+818h+var_678]
0x18000f297  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f29c  nop
0x18000f29d  lea     r8, [rsp+818h+var_678]
0x18000f2a5  lea     rdx, [rsp+818h+var_748]
0x18000f2ad  lea     rcx, [rsp+818h+var_7A0]
0x18000f2b2  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18000f2b7  nop
0x18000f2b8  lea     rcx, [rsp+818h+var_678]; void *
0x18000f2c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f2c5  xorps   xmm0, xmm0
0x18000f2c8  movups  [rsp+818h+var_678], xmm0
0x18000f2d0  mov     [rsp+818h+var_668], rsi
0x18000f2d8  mov     [rsp+818h+var_660], rsi
0x18000f2e0  mov     r8d, 11h
0x18000f2e6  lea     rdx, aRegexexpectedd; "RegexExpectedData"
0x18000f2ed  lea     rcx, [rsp+818h+var_678]
0x18000f2f5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000f2fa  nop
0x18000f2fb  lea     r8, [rsp+818h+var_678]
0x18000f303  lea     rdx, [rsp+818h+var_748]
0x18000f30b  lea     rcx, [rsp+818h+var_7A0]
0x18000f310  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18000f315  nop
0x18000f316  lea     rcx, [rsp+818h+var_678]; void *
0x18000f31e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f323  lea     rdx, [rsp+818h+pNumArgs]; pNumArgs
0x18000f328  mov     rcx, r12; lpCmdLine
0x18000f32b  call    cs:__imp_CommandLineToArgvW
0x18000f331  mov     rdi, rax
0x18000f334  mov     [rsp+818h+hMem], rax
0x18000f339  mov     ebx, [rsp+818h+pNumArgs]
0x18000f33d  test    rax, rax
0x18000f340  jz      loc_1800104C7
0x18000f346  cmp     ebx, r14d
0x18000f349  jl      loc_1800104C7
0x18000f34f  mov     r13, [rax]
0x18000f352  mov     rdx, r13; String2
0x18000f355  lea     rcx, aFeatures; "Features"
0x18000f35c  call    wcscmp_0
0x18000f361  test    eax, eax
0x18000f363  jnz     loc_18000F3F0
0x18000f369  mov     r8, rdi
0x18000f36c  mov     edx, ebx
0x18000f36e  lea     rcx, [rsp+818h+var_7A0]
0x18000f373  call    ?SupportAllFeatures@AppCompatUtility@@YA_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@HPEAPEAG@Z; AppCompatUtility::SupportAllFeatures(std::set<std::wstring> const &,int,ushort * *)
0x18000f378  test    al, al
0x18000f37a  jz      short loc_18000F387
0x18000f37c  mov     rax, [rsp+818h+var_790]
0x18000f384  mov     [rax], r14d
0x18000f387  lea     rcx, [rsp+818h+var_7A0]
0x18000f38c  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000f391  nop
0x18000f392  lea     rcx, [rsp+818h+S1]; void *
0x18000f39a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f39f  nop
0x18000f3a0  lea     rcx, [rsp+818h+var_738]; void *
0x18000f3a8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f3ad  nop
0x18000f3ae  lea     rcx, [rsp+818h+pszString]; void *
0x18000f3b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f3bb  nop
0x18000f3bc  lea     rcx, [rsp+818h+String1]; void *
0x18000f3c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f3c9  nop
0x18000f3ca  lea     rcx, [rsp+818h+var_698]; void *
0x18000f3d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f3d7  nop
0x18000f3d8  lea     rcx, [rsp+818h+var_6B8]; void *
0x18000f3e0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f3e5  nop
0x18000f3e6  mov     r12, [rsp+818h+hMem]
0x18000f3eb  jmp     loc_180010576
0x18000f3f0  cmp     ebx, 6
0x18000f3f3  jge     loc_18000F47F
0x18000f3f9  mov     dword ptr [rsp+818h+var_7F8], ebx
0x18000f3fd  lea     r9, aWrongArguments; "Wrong arguments number: %d"
0x18000f404  mov     r8d, 23Eh
0x18000f40a  mov     rdx, r15
0x18000f40d  mov     ecx, r14d
0x18000f410  call    AslLogCallPrintf
0x18000f415  nop
0x18000f416  lea     rcx, [rsp+818h+var_7A0]
0x18000f41b  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x18000f420  nop
0x18000f421  lea     rcx, [rsp+818h+S1]; void *
0x18000f429  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f42e  nop
0x18000f42f  lea     rcx, [rsp+818h+var_738]; void *
0x18000f437  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f43c  nop
0x18000f43d  lea     rcx, [rsp+818h+pszString]; void *
0x18000f445  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f44a  nop
0x18000f44b  lea     rcx, [rsp+818h+String1]; void *
0x18000f453  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f458  nop
0x18000f459  lea     rcx, [rsp+818h+var_698]; void *
0x18000f461  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f466  nop
0x18000f467  lea     rcx, [rsp+818h+var_6B8]; void *
0x18000f46f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f474  nop
0x18000f475  mov     r12, [rsp+818h+hMem]
0x18000f47a  jmp     loc_180010576
0x18000f47f  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000f483  mov     rdx, r12
0x18000f486  inc     rdx
0x18000f489  cmp     [r13+rdx*2+0], si
0x18000f48f  jnz     short loc_18000F486
0x18000f491  cmp     rdx, [rsp+818h+var_6A0]
0x18000f499  ja      short loc_18000F4DA
0x18000f49b  lea     rdi, [rsp+818h+var_6B8]
0x18000f4a3  cmp     [rsp+818h+var_6A0], 7
0x18000f4ac  cmova   rdi, [rsp+818h+var_6B8]
0x18000f4b5  mov     [rsp+818h+var_6A8], rdx
0x18000f4bd  lea     rbx, [rdx+rdx]
0x18000f4c1  mov     r8, rbx; Size
0x18000f4c4  mov     rdx, r13; Src
0x18000f4c7  mov     rcx, rdi; void *
0x18000f4ca  call    memmove_0
0x18000f4cf  mov     [rbx+rdi], si
0x18000f4d3  mov     rdi, [rsp+818h+hMem]
0x18000f4d8  jmp     short loc_18000F4EA
0x18000f4da  mov     r9, r13
0x18000f4dd  lea     rcx, [rsp+818h+var_6B8]
0x18000f4e5  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000f4ea  mov     r9, [rdi+8]
0x18000f4ee  mov     rdx, r12
0x18000f4f1  inc     rdx
0x18000f4f4  cmp     [r9+rdx*2], si
0x18000f4f9  jnz     short loc_18000F4F1
0x18000f4fb  cmp     rdx, [rsp+818h+var_6E0]
0x18000f503  ja      short loc_18000F544
0x18000f505  lea     rdi, [rsp+818h+S1]
0x18000f50d  cmp     [rsp+818h+var_6E0], 7
0x18000f516  cmova   rdi, [rsp+818h+S1]
0x18000f51f  mov     [rsp+818h+var_6E8], rdx
0x18000f527  lea     rbx, [rdx+rdx]
0x18000f52b  mov     r8, rbx; Size
0x18000f52e  mov     rdx, r9; Src
0x18000f531  mov     rcx, rdi; void *
0x18000f534  call    memmove_0
0x18000f539  mov     [rbx+rdi], si
0x18000f53d  mov     rdi, [rsp+818h+hMem]
0x18000f542  jmp     short loc_18000F551
0x18000f544  lea     rcx, [rsp+818h+S1]
0x18000f54c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000f551  mov     r9, [rdi+10h]
0x18000f555  mov     rdx, r12
0x18000f558  inc     rdx
0x18000f55b  cmp     [r9+rdx*2], si
0x18000f560  jnz     short loc_18000F558
0x18000f562  cmp     rdx, [rsp+818h+var_680]
0x18000f56a  ja      short loc_18000F5AB
0x18000f56c  lea     rdi, [rsp+818h+var_698]
0x18000f574  cmp     [rsp+818h+var_680], 7
0x18000f57d  cmova   rdi, [rsp+818h+var_698]
0x18000f586  mov     [rsp+818h+var_688], rdx
  ... truncated ...
```
