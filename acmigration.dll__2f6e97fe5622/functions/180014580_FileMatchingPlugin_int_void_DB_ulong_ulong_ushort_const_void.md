# FileMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x180014580`
- end: `0x180015240`
- name: `?FileMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `3264`
- prototype: `__int64 __usercall@<rax>(AppCompatUtility *this@<rcx>, void *@<rdx>, struct _DB *@<r8>, unsigned int@<r9d>, unsigned int, const unsigned __int16 *, void *)`
- caller_count: `0`
- callee_count: `26`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002120`
- `0x180002874`
- `0x18000a51c`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000bbbc`
- `0x18000c190`
- `0x18000c3c8`
- `0x18000c534`
- `0x18000dfd8`
- `0x180010718`
- `0x1800118f4`
- `0x180011bcc`
- `0x180012638`
- `0x180014580`
- `0x18001540c`
- `0x180015a60`
- `0x18003f0b0`
- `0x18003fa7c`
- `0x180042ee8`
- `0x180044964`
- `0x1800514a8`
- `0x1800543c0`
- `0x180065120`
- `0x180065150`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180015108`
- `KERNEL32!LocalFree` at `0x180015108`
- `KERNEL32!GetTickCount64` at `0x1800145e7`
- `KERNEL32!GetTickCount64` at `0x18001516e`
- `KERNEL32!GetTickCount64` at `0x1800145e7`
- `KERNEL32!GetTickCount64` at `0x18001516e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180014dbd`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180014dbd`
- `KERNEL32!GetLastError` at `0x18001506b`
- `KERNEL32!GetLastError` at `0x1800150a3`
- `KERNEL32!GetLastError` at `0x18001506b`
- `KERNEL32!GetLastError` at `0x1800150a3`
- `ntdll!RtlFreeHeap` at `0x18001512f`
- `ntdll!RtlFreeHeap` at `0x18001512f`
- `SHELL32!CommandLineToArgvW` at `0x180014b4a`
- `SHELL32!CommandLineToArgvW` at `0x180014b4a`

## string_xrefs

- `0x1800151b6`: `CommandLine is null/empty`
- `0x1800148ee`: `Enter FileMatchingPlugin`
- `0x1800148fb`: `FileMatchingPlugin`
- `0x1800150ea`: `FileMatchingPlugin`
- `0x18001515d`: `FileMatchingPlugin`
- `0x180014921`: `FileMatchingPlugin `
- `0x1800150b6`: `CommandLineToArgvW failed %d, %ws, numArgs=%d`
- `0x180014c47`: `FilePath=%ws`
- `0x180014c6b`: `Empty FilePath.`
- `0x18001519a`: `FileMatchingPlugin Matched = %d, duration = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall FileMatchingPlugin(
        AppCompatUtility *this,
        void *a2,
        struct _DB *a3,
        __int64 a4,
        unsigned int a5,
        const unsigned __int16 *pszSrc,
        void *a7)
{
  AppCompatUtility *v7; // rdi
  _QWORD *v8; // rax
  unsigned int v9; // r9d
  ULONGLONG v10; // r13
  unsigned int v11; // r9d
  LPWSTR *v13; // rax
  unsigned __int16 **v14; // r12
  unsigned int v15; // ebx
  unsigned __int64 v16; // r13
  unsigned __int64 v17; // rdx
  LPCWSTR *v18; // rdi
  __int64 v19; // rbx
  LPCWSTR *v20; // rax
  int i; // eax
  unsigned __int64 v22; // rbx
  int v23; // eax
  const WCHAR *v24; // rcx
  LPCWSTR *v25; // rdi
  LPCWSTR *v26; // rax
  LPCWSTR *v27; // rax
  unsigned __int64 v28; // rbx
  __int64 v29; // rdx
  __int64 v30; // r8
  __int128 *v31; // r9
  __int64 v32; // rax
  __int64 v33; // rbx
  unsigned __int64 v34; // [rsp+20h] [rbp-BD8h]
  DWORD LastError; // [rsp+20h] [rbp-BD8h]
  DWORD v36; // [rsp+20h] [rbp-BD8h]
  int v37; // [rsp+30h] [rbp-BC8h]
  ULONGLONG TickCount64; // [rsp+40h] [rbp-BB8h]
  int pNumArgs; // [rsp+48h] [rbp-BB0h] BYREF
  int v40; // [rsp+4Ch] [rbp-BACh]
  _QWORD v41[2]; // [rsp+50h] [rbp-BA8h] BYREF
  ULONGLONG v42; // [rsp+60h] [rbp-B98h]
  AppCompatUtility *v43; // [rsp+68h] [rbp-B90h]
  LPWSTR *v44; // [rsp+70h] [rbp-B88h]
  AppCompatUtility *v45; // [rsp+78h] [rbp-B80h]
  __int64 v46; // [rsp+80h] [rbp-B78h]
  __int16 v47; // [rsp+90h] [rbp-B68h] BYREF
  char v48; // [rsp+92h] [rbp-B66h]
  __int128 v49; // [rsp+98h] [rbp-B60h]
  __int64 v50; // [rsp+A8h] [rbp-B50h]
  __int64 v51; // [rsp+B0h] [rbp-B48h]
  __int128 v52; // [rsp+B8h] [rbp-B40h]
  __int64 v53; // [rsp+C8h] [rbp-B30h]
  __int64 v54; // [rsp+D0h] [rbp-B28h]
  __int128 v55; // [rsp+D8h] [rbp-B20h]
  __int64 v56; // [rsp+E8h] [rbp-B10h]
  __int64 v57; // [rsp+F0h] [rbp-B08h]
  __int128 v58; // [rsp+F8h] [rbp-B00h]
  __int64 v59; // [rsp+108h] [rbp-AF0h]
  __int64 v60; // [rsp+110h] [rbp-AE8h]
  __int128 v61; // [rsp+118h] [rbp-AE0h]
  __int64 v62; // [rsp+128h] [rbp-AD0h]
  __int64 v63; // [rsp+130h] [rbp-AC8h]
  __int128 v64; // [rsp+138h] [rbp-AC0h]
  __int64 v65; // [rsp+148h] [rbp-AB0h]
  __int64 v66; // [rsp+150h] [rbp-AA8h]
  __int128 v67; // [rsp+158h] [rbp-AA0h]
  __int64 v68; // [rsp+168h] [rbp-A90h]
  __int64 v69; // [rsp+170h] [rbp-A88h]
  __int128 v70; // [rsp+178h] [rbp-A80h]
  __int64 v71; // [rsp+188h] [rbp-A70h]
  __int64 v72; // [rsp+190h] [rbp-A68h]
  __int128 v73; // [rsp+198h] [rbp-A60h]
  __int64 v74; // [rsp+1A8h] [rbp-A50h]
  __int64 v75; // [rsp+1B0h] [rbp-A48h]
  __int128 v76; // [rsp+1B8h] [rbp-A40h]
  __int64 v77; // [rsp+1C8h] [rbp-A30h]
  __int64 v78; // [rsp+1D0h] [rbp-A28h]
  __int128 v79; // [rsp+1D8h] [rbp-A20h]
  __int64 v80; // [rsp+1E8h] [rbp-A10h]
  __int64 v81; // [rsp+1F0h] [rbp-A08h]
  __int128 v82; // [rsp+1F8h] [rbp-A00h]
  __int64 v83; // [rsp+208h] [rbp-9F0h]
  __int64 v84; // [rsp+210h] [rbp-9E8h]
  __int128 v85; // [rsp+218h] [rbp-9E0h]
  __int64 v86; // [rsp+228h] [rbp-9D0h]
  __int64 v87; // [rsp+230h] [rbp-9C8h]
  __int128 v88; // [rsp+238h] [rbp-9C0h]
  __int64 v89; // [rsp+248h] [rbp-9B0h]
  __int64 v90; // [rsp+250h] [rbp-9A8h]
  __int128 v91; // [rsp+258h] [rbp-9A0h]
  __int64 v92; // [rsp+268h] [rbp-990h]
  __int64 v93; // [rsp+270h] [rbp-988h]
  __int128 v94; // [rsp+278h] [rbp-980h]
  __int64 v95; // [rsp+288h] [rbp-970h]
  __int64 v96; // [rsp+290h] [rbp-968h]
  __int128 v97; // [rsp+298h] [rbp-960h]
  __int64 v98; // [rsp+2A8h] [rbp-950h]
  __int64 v99; // [rsp+2B0h] [rbp-948h]
  __int128 v100; // [rsp+2B8h] [rbp-940h]
  __int64 v101; // [rsp+2C8h] [rbp-930h]
  __int64 v102; // [rsp+2D0h] [rbp-928h]
  int v103; // [rsp+2D8h] [rbp-920h]
  PVOID P; // [rsp+2E0h] [rbp-918h] BYREF
  struct AppCompatUtility::_RegexCondition *v105; // [rsp+2E8h] [rbp-910h] BYREF
  LPCWSTR lpSrc[2]; // [rsp+2F0h] [rbp-908h] BYREF
  unsigned __int64 v107; // [rsp+300h] [rbp-8F8h]
  unsigned __int64 v108; // [rsp+308h] [rbp-8F0h]
  __int128 v109; // [rsp+310h] [rbp-8E8h] BYREF
  __int64 v110; // [rsp+320h] [rbp-8D8h]
  __int64 v111; // [rsp+328h] [rbp-8D0h]
  void *Src[2]; // [rsp+330h] [rbp-8C8h] BYREF
  __int128 v113; // [rsp+340h] [rbp-8B8h]
  __int128 v114; // [rsp+350h] [rbp-8A8h] BYREF
  __int64 v115; // [rsp+360h] [rbp-898h]
  unsigned __int64 v116; // [rsp+368h] [rbp-890h]
  __int128 v117; // [rsp+370h] [rbp-888h] BYREF
  __int64 v118; // [rsp+380h] [rbp-878h]
  __int64 v119; // [rsp+388h] [rbp-870h]
  WCHAR Dst[264]; // [rsp+390h] [rbp-868h] BYREF
  int pszDest[392]; // [rsp+5A0h] [rbp-658h] BYREF

  v46 = -2;
  v7 = this;
  v43 = this;
  v45 = this;
  pNumArgs = 0;
  memset_0(pszDest, 0, 0x618u);
  TickCount64 = GetTickCount64();
  v42 = TickCount64;
  memset_0(Dst, 0, 0x208u);
  v114 = 0;
  v115 = 0;
  v116 = 7;
  LOWORD(v114) = 0;
  v117 = 0;
  v118 = 0;
  v119 = 7;
  LOWORD(v117) = 0;
  v41[1] = 0;
  v8 = operator new(0x40u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  v41[0] = v8;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 7;
  LOWORD(v49) = 0;
  v52 = 0;
  v53 = 0;
  v54 = 7;
  LOWORD(v52) = 0;
  v55 = 0;
  v56 = 0;
  v57 = 7;
  LOWORD(v55) = 0;
  v58 = 0;
  v59 = 0;
  v60 = 7;
  LOWORD(v58) = 0;
  v61 = 0;
  v62 = 0;
  v63 = 7;
  LOWORD(v61) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 7;
  LOWORD(v64) = 0;
  v67 = 0;
  v68 = 0;
  v69 = 7;
  LOWORD(v67) = 0;
  v70 = 0;
  v71 = 0;
  v72 = 7;
  LOWORD(v70) = 0;
  v73 = 0;
  v74 = 0;
  v75 = 7;
  LOWORD(v73) = 0;
  v76 = 0;
  v77 = 0;
  v78 = 7;
  LOWORD(v76) = 0;
  v79 = 0;
  v80 = 0;
  v81 = 7;
  LOWORD(v79) = 0;
  v82 = 0;
  v83 = 0;
  v84 = 7;
  LOWORD(v82) = 0;
  v85 = 0;
  v86 = 0;
  v87 = 7;
  LOWORD(v85) = 0;
  v88 = 0;
  v89 = 0;
  v90 = 7;
  LOWORD(v88) = 0;
  v91 = 0;
  v92 = 0;
  v93 = 7;
  LOWORD(v91) = 0;
  v94 = 0;
  v95 = 0;
  v96 = 7;
  LOWORD(v94) = 0;
  v97 = 0;
  v98 = 0;
  v99 = 7;
  LOWORD(v97) = 0;
  v100 = 0;
  v101 = 0;
  v102 = 7;
  LOWORD(v100) = 0;
  v103 = 3;
  P = 0;
  v105 = 0;
  *(_DWORD *)v7 = 0;
  AslLogCallPrintf(3, "FileMatchingPlugin", 2452, "Enter FileMatchingPlugin");
  if ( pszSrc && *pszSrc )
  {
    if ( StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x30Cu, L"FileMatchingPlugin ") < 0 )
    {
      AslLogCallPrintf(1, "FileMatchingPlugin", 2463, "StringCchCatW failed.");
LABEL_5:
      v10 = TickCount64;
LABEL_63:
      v42 = v10;
      if ( P )
      {
        RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
        P = 0;
      }
      try
      {
        AppCompatUtility::AddCacheMatchingPlugin(
          (AppCompatUtility *)*(unsigned int *)v7,
          (int)pszDest,
          (const unsigned __int16 *)a5,
          v9);
      }
      catch ( ... )
      {
        AslLogCallPrintf(1, "FileMatchingPlugin", 2618, "Unhandled exception");
        LODWORD(v10) = v42;
        v7 = v45;
      }
      v33 = (unsigned int)GetTickCount64() - (unsigned int)v10;
      AslTelemetryTrackMetric(::P, "FileMatching_Ms", v33);
      AslLogCallPrintf(
        3,
        "FileMatchingPlugin",
        2624,
        "FileMatchingPlugin Matched = %d, duration = %d",
        *(_DWORD *)v7,
        v33);
      goto LABEL_67;
    }
    v44 = 0;
    if ( StringCchCatW((STRSAFE_LPWSTR)pszDest, 0x30Cu, pszSrc) < 0 )
    {
      AslLogCallPrintf(1, "FileMatchingPlugin", 2470, "StringCchCatW failed; %ws", pszSrc);
      goto LABEL_5;
    }
    *(_OWORD *)lpSrc = 0;
    v107 = 0;
    v108 = 7;
    LOWORD(lpSrc[0]) = 0;
    if ( (unsigned int)AppCompatUtility::CheckCacheMatchingPlugin(v7, pszDest, (const unsigned __int16 *)a5, v11) )
    {
      std::wstring::~wstring(lpSrc);
      _FileAttributesStrs::~_FileAttributesStrs((_FileAttributesStrs *)&v47);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v41);
      std::wstring::~wstring(&v117);
      std::wstring::~wstring(&v114);
      return 1;
    }
    v109 = 0;
    v110 = 0;
    v111 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v109, L"Hash", 4);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v41,
      Src,
      &v109);
    std::wstring::~wstring(&v109);
    v109 = 0;
    v110 = 0;
    v111 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v109, L"MatchingText", 12);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v41,
      Src,
      &v109);
    std::wstring::~wstring(&v109);
    v109 = 0;
    v110 = 0;
    v111 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v109, L"MatchingRegexText", 17);
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      v41,
      Src,
      &v109);
    std::wstring::~wstring(&v109);
    v13 = CommandLineToArgvW(pszSrc, &pNumArgs);
    v14 = v13;
    v44 = v13;
    v15 = pNumArgs;
    if ( v13 && pNumArgs >= 1 )
    {
      Src[0] = *v13;
      if ( !wcscmp_0(L"Features", (const wchar_t *)Src[0]) )
      {
        if ( (unsigned __int8)AppCompatUtility::SupportAllFeatures(v41, v15, v14) )
          *(_DWORD *)v7 = 1;
LABEL_59:
        std::wstring::~wstring(lpSrc);
        v10 = TickCount64;
        goto LABEL_62;
      }
      v16 = -1;
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)Src[0] + v17) );
      if ( v17 > v108 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(lpSrc);
      }
      else
      {
        v18 = lpSrc;
        if ( v108 > 7 )
          v18 = (LPCWSTR *)lpSrc[0];
        v107 = v17;
        v19 = 2 * v17;
        memmove_0(v18, Src[0], 2 * v17);
        *(_WORD *)((char *)v18 + v19) = 0;
        v7 = v43;
      }
      v20 = lpSrc;
      if ( v108 > 7 )
        v20 = (LPCWSTR *)lpSrc[0];
      AslLogCallPrintf(3, "FileMatchingPlugin", 2510, "FilePath=%ws", v20);
      if ( v107 )
      {
        for ( i = 1; ; i = v40 + 2 )
        {
          v40 = i;
          v22 = pNumArgs;
          if ( i >= pNumArgs )
            break;
          Src[0] = (void *)i;
          if ( !wcscmp_0(v14[i], L"-RegexConditions") )
          {
            v23 = AppCompatUtility::ParseRegexConditions(
                    (AppCompatUtility *)&P,
                    &v105,
                    (unsigned __int64 *)&v14[(__int64)Src[0] + 1],
                    (unsigned __int16 **)((int)v22 - v40 - 1),
                    v34);
            if ( v23 )
            {
              AslLogCallPrintf(1, "FileMatchingPlugin", 2537, "Failed to parse RegexConditions. [0x%x]", v23);
              std::wstring::~wstring(lpSrc);
              v10 = TickCount64;
              goto LABEL_62;
            }
            break;
          }
          if ( !ParseArguments((struct _FileAttributesStrs *)&v47, v14, v22, (unsigned __int64)Src[0]) )
          {
            AslLogCallPrintf(1, "FileMatchingPlugin", 2549, "Failed to parse argument.");
            std::wstring::~wstring(lpSrc);
            v10 = TickCount64;
            goto LABEL_62;
          }
        }
        v24 = (const WCHAR *)lpSrc;
        if ( v108 > 7 )
          v24 = lpSrc[0];
        if ( ExpandEnvironmentStringsW(v24, Dst, 0x104u) - 1 > 0x103 )
        {
          LastError = GetLastError();
          AslLogCallPrintf(1, "FileMatchingPlugin", 2560, "ExpandEnvironmentStrings failed, %d", LastError);
          std::wstring::~wstring(lpSrc);
          v10 = TickCount64;
          goto LABEL_62;
        }
        do
          ++v16;
        while ( Dst[v16] );
        if ( v16 > v108 )
        {
          std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(lpSrc);
        }
        else
        {
          v25 = lpSrc;
          if ( v108 > 7 )
            v25 = (LPCWSTR *)lpSrc[0];
          v107 = v16;
          memmove_0(v25, Dst, 2 * v16);
          *((_WORD *)v25 + v16) = 0;
        }
        v26 = lpSrc;
        if ( v108 > 7 )
          v26 = (LPCWSTR *)lpSrc[0];
        if ( *((_WORD *)v26 + v107 - 1) == 92 )
        {
          if ( !v107 )
            std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
          v27 = lpSrc;
          if ( v108 > 7 )
            v27 = (LPCWSTR *)lpSrc[0];
          v28 = v107 - 1;
          memmove_0((char *)v27 + 2 * v107 - 2, (char *)v27 + 2 * v107, 2u);
          v107 = v28;
        }
        v7 = v43;
        if ( (unsigned __int8)GetMatchResult(
                                (unsigned int)lpSrc,
                                (_DWORD)v43,
                                (unsigned int)&v114,
                                (unsigned int)&v117,
                                (__int64)&v47)
          && *(_DWORD *)v7
          && (v92 || v95 || v98) )
        {
          if ( 0x7FFFFFFFFFFFFFFELL == v115 )
            std::_Xlen_string();
          v31 = &v114;
          if ( v116 > 7 )
            v31 = (__int128 *)v114;
          std::wstring::wstring(&v109, v29, v30, v31);
          v32 = std::wstring::append(&v109);
          *(_OWORD *)Src = 0;
          v113 = 0u;
          *(_OWORD *)Src = *(_OWORD *)v32;
          v113 = *(_OWORD *)(v32 + 16);
          *(_QWORD *)(v32 + 16) = 0;
          *(_QWORD *)(v32 + 24) = 7;
          *(_WORD *)v32 = 0;
          CheckDriverStatus((__int64)Src, &v117, v7, (__int64)&v47);
          std::wstring::~wstring(Src);
          std::wstring::~wstring(&v109);
        }
        goto LABEL_59;
      }
      AslLogCallPrintf(1, "FileMatchingPlugin", 2517, "Empty FilePath.");
      std::wstring::~wstring(lpSrc);
      v10 = TickCount64;
    }
    else
    {
      v37 = pNumArgs;
      v36 = GetLastError();
      AslLogCallPrintf(1, "FileMatchingPlugin", 2496, "CommandLineToArgvW failed %d, %ws, numArgs=%d", v36, pszSrc, v37);
      std::wstring::~wstring(lpSrc);
      v10 = TickCount64;
      if ( !v14 )
        goto LABEL_63;
    }
LABEL_62:
    LocalFree(v14);
    goto LABEL_63;
  }
  AslLogCallPrintf(1, "FileMatchingPlugin", 2456, "CommandLine is null/empty");
LABEL_67:
  _FileAttributesStrs::~_FileAttributesStrs((_FileAttributesStrs *)&v47);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v41);
  std::wstring::~wstring(&v117);
  std::wstring::~wstring(&v114);
  return 1;
}

```

## disassembly

```asm
0x180014580  mov     r11, rsp
0x180014583  push    rdi
0x180014584  push    r12
0x180014586  push    r13
0x180014588  push    r14
0x18001458a  push    r15
0x18001458c  sub     rsp, 0BD0h
0x180014593  mov     qword ptr [r11-0B78h], 0FFFFFFFFFFFFFFFEh
0x18001459e  mov     [r11+10h], rbx
0x1800145a2  mov     [r11+18h], rsi
0x1800145a6  mov     rax, cs:__security_cookie
0x1800145ad  xor     rax, rsp
0x1800145b0  mov     [rsp+0BF8h+var_38], rax
0x1800145b8  mov     rdi, rcx
0x1800145bb  mov     [rsp+0BF8h+var_B90], rcx
0x1800145c0  mov     [rsp+0BF8h+var_B80], rcx
0x1800145c5  mov     r13, [rsp+0BF8h+pszSrc]
0x1800145cd  xor     esi, esi
0x1800145cf  mov     [rsp+0BF8h+pNumArgs], esi
0x1800145d3  xor     edx, edx; Val
0x1800145d5  mov     r8d, 618h; Size
0x1800145db  lea     rcx, [r11-658h]; void *
0x1800145e2  call    memset_0
0x1800145e7  call    cs:__imp_GetTickCount64
0x1800145ed  mov     [rsp+0BF8h+var_BB8], rax
0x1800145f2  mov     [rsp+0BF8h+var_B98], rax
0x1800145f7  xor     edx, edx; Val
0x1800145f9  mov     r8d, 208h; Size
0x1800145ff  lea     rcx, [rsp+0BF8h+Dst]; void *
0x180014607  call    memset_0
0x18001460c  xorps   xmm0, xmm0
0x18001460f  movups  [rsp+0BF8h+var_8A8], xmm0
0x180014617  mov     [rsp+0BF8h+var_898], rsi
0x18001461f  lea     ebx, [rsi+7]
0x180014622  mov     [rsp+0BF8h+var_890], rbx
0x18001462a  mov     word ptr [rsp+0BF8h+var_8A8], si
0x180014632  movups  [rsp+0BF8h+var_888], xmm0
0x18001463a  mov     [rsp+0BF8h+var_878], rsi
0x180014642  mov     [rsp+0BF8h+var_870], rbx
0x18001464a  mov     word ptr [rsp+0BF8h+var_888], si
0x180014652  mov     [rsp+0BF8h+var_BA8], rsi
0x180014657  mov     [rsp+0BF8h+var_BA0], rsi
0x18001465c  lea     ecx, [rsi+40h]; Size
0x18001465f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014664  mov     [rax], rax
0x180014667  mov     [rax+8], rax
0x18001466b  mov     [rax+10h], rax
0x18001466f  lea     r14d, [rsi+1]
0x180014673  mov     word ptr [rax+18h], 101h
0x180014679  mov     [rsp+0BF8h+var_BA8], rax
0x18001467e  mov     [rsp+0BF8h+var_B68], si
0x180014686  mov     [rsp+0BF8h+var_B66], sil
0x18001468e  xorps   xmm0, xmm0
0x180014691  movups  [rsp+0BF8h+var_B60], xmm0
0x180014699  mov     [rsp+0BF8h+var_B50], rsi
0x1800146a1  mov     [rsp+0BF8h+var_B48], rbx
0x1800146a9  mov     word ptr [rsp+0BF8h+var_B60], si
0x1800146b1  movups  [rsp+0BF8h+var_B40], xmm0
0x1800146b9  mov     [rsp+0BF8h+var_B30], rsi
0x1800146c1  mov     [rsp+0BF8h+var_B28], rbx
0x1800146c9  mov     word ptr [rsp+0BF8h+var_B40], si
0x1800146d1  movups  [rsp+0BF8h+var_B20], xmm0
0x1800146d9  mov     [rsp+0BF8h+var_B10], rsi
0x1800146e1  mov     [rsp+0BF8h+var_B08], rbx
0x1800146e9  mov     word ptr [rsp+0BF8h+var_B20], si
0x1800146f1  movups  [rsp+0BF8h+var_B00], xmm0
0x1800146f9  mov     [rsp+0BF8h+var_AF0], rsi
0x180014701  mov     [rsp+0BF8h+var_AE8], rbx
0x180014709  mov     word ptr [rsp+0BF8h+var_B00], si
0x180014711  movups  [rsp+0BF8h+var_AE0], xmm0
0x180014719  mov     [rsp+0BF8h+var_AD0], rsi
0x180014721  mov     [rsp+0BF8h+var_AC8], rbx
0x180014729  mov     word ptr [rsp+0BF8h+var_AE0], si
0x180014731  movups  [rsp+0BF8h+var_AC0], xmm0
0x180014739  mov     [rsp+0BF8h+var_AB0], rsi
0x180014741  mov     [rsp+0BF8h+var_AA8], rbx
0x180014749  mov     word ptr [rsp+0BF8h+var_AC0], si
0x180014751  movups  [rsp+0BF8h+var_AA0], xmm0
0x180014759  mov     [rsp+0BF8h+var_A90], rsi
0x180014761  mov     [rsp+0BF8h+var_A88], rbx
0x180014769  mov     word ptr [rsp+0BF8h+var_AA0], si
0x180014771  movups  [rsp+0BF8h+var_A80], xmm0
0x180014779  mov     [rsp+0BF8h+var_A70], rsi
0x180014781  mov     [rsp+0BF8h+var_A68], rbx
0x180014789  mov     word ptr [rsp+0BF8h+var_A80], si
0x180014791  movups  [rsp+0BF8h+var_A60], xmm0
0x180014799  mov     [rsp+0BF8h+var_A50], rsi
0x1800147a1  mov     [rsp+0BF8h+var_A48], rbx
0x1800147a9  mov     word ptr [rsp+0BF8h+var_A60], si
0x1800147b1  movups  [rsp+0BF8h+var_A40], xmm0
0x1800147b9  mov     [rsp+0BF8h+var_A30], rsi
0x1800147c1  mov     [rsp+0BF8h+var_A28], rbx
0x1800147c9  mov     word ptr [rsp+0BF8h+var_A40], si
0x1800147d1  movups  [rsp+0BF8h+var_A20], xmm0
0x1800147d9  mov     [rsp+0BF8h+var_A10], rsi
0x1800147e1  mov     [rsp+0BF8h+var_A08], rbx
0x1800147e9  mov     word ptr [rsp+0BF8h+var_A20], si
0x1800147f1  movups  [rsp+0BF8h+var_A00], xmm0
0x1800147f9  mov     [rsp+0BF8h+var_9F0], rsi
0x180014801  mov     [rsp+0BF8h+var_9E8], rbx
0x180014809  mov     word ptr [rsp+0BF8h+var_A00], si
0x180014811  movups  [rsp+0BF8h+var_9E0], xmm0
0x180014819  mov     [rsp+0BF8h+var_9D0], rsi
0x180014821  mov     [rsp+0BF8h+var_9C8], rbx
0x180014829  mov     word ptr [rsp+0BF8h+var_9E0], si
0x180014831  movups  [rsp+0BF8h+var_9C0], xmm0
0x180014839  mov     [rsp+0BF8h+var_9B0], rsi
0x180014841  mov     [rsp+0BF8h+var_9A8], rbx
0x180014849  mov     word ptr [rsp+0BF8h+var_9C0], si
0x180014851  movups  [rsp+0BF8h+var_9A0], xmm0
0x180014859  mov     [rsp+0BF8h+var_990], rsi
0x180014861  mov     [rsp+0BF8h+var_988], rbx
0x180014869  mov     word ptr [rsp+0BF8h+var_9A0], si
0x180014871  movups  [rsp+0BF8h+var_980], xmm0
0x180014879  mov     [rsp+0BF8h+var_970], rsi
0x180014881  mov     [rsp+0BF8h+var_968], rbx
0x180014889  mov     word ptr [rsp+0BF8h+var_980], si
0x180014891  movups  [rsp+0BF8h+var_960], xmm0
0x180014899  mov     [rsp+0BF8h+var_950], rsi
0x1800148a1  mov     [rsp+0BF8h+var_948], rbx
0x1800148a9  mov     word ptr [rsp+0BF8h+var_960], si
0x1800148b1  movups  [rsp+0BF8h+var_940], xmm0
0x1800148b9  mov     [rsp+0BF8h+var_930], rsi
0x1800148c1  mov     [rsp+0BF8h+var_928], rbx
0x1800148c9  mov     word ptr [rsp+0BF8h+var_940], si
0x1800148d1  mov     [rsp+0BF8h+var_920], 3
0x1800148dc  mov     [rsp+0BF8h+P], rsi
0x1800148e4  mov     [rsp+0BF8h+var_910], rsi
0x1800148ec  mov     [rdi], esi
0x1800148ee  lea     r9, aEnterFilematch; "Enter FileMatchingPlugin"
0x1800148f5  mov     r8d, 994h
0x1800148fb  lea     r15, aFilematchingpl_0; "FileMatchingPlugin"
0x180014902  mov     rdx, r15
0x180014905  lea     ecx, [rsi+3]
0x180014908  call    AslLogCallPrintf
0x18001490d  test    r13, r13
0x180014910  jz      loc_1800151B6
0x180014916  cmp     si, [r13+0]
0x18001491b  jz      loc_1800151B6
0x180014921  lea     r8, aFilematchingpl_1; "FileMatchingPlugin "
0x180014928  mov     r12d, 30Ch
0x18001492e  mov     edx, r12d; cchDest
0x180014931  lea     rcx, [rsp+0BF8h+pszDest]; pszDest
0x180014939  call    StringCchCatW
0x18001493e  test    eax, eax
0x180014940  jns     short loc_180014964
0x180014942  lea     r9, aStringcchcatwF_0; "StringCchCatW failed."
0x180014949  mov     r8d, 99Fh
0x18001494f  mov     rdx, r15
0x180014952  mov     ecx, r14d
0x180014955  call    AslLogCallPrintf
0x18001495a  mov     r13, [rsp+0BF8h+var_BB8]
0x18001495f  jmp     loc_18001510E
0x180014964  mov     [rsp+0BF8h+var_B88], rsi
0x180014969  mov     r8, r13; pszSrc
0x18001496c  mov     rdx, r12; cchDest
0x18001496f  lea     rcx, [rsp+0BF8h+pszDest]; pszDest
0x180014977  call    StringCchCatW
0x18001497c  test    eax, eax
0x18001497e  jns     short loc_18001499F
0x180014980  mov     [rsp+0BF8h+var_BD8], r13
0x180014985  lea     r9, aStringcchcatwF; "StringCchCatW failed; %ws"
0x18001498c  mov     r8d, 9A6h
0x180014992  mov     rdx, r15
0x180014995  mov     ecx, r14d
0x180014998  call    AslLogCallPrintf
0x18001499d  jmp     short loc_18001495A
0x18001499f  xorps   xmm0, xmm0
0x1800149a2  movups  xmmword ptr [rsp+0BF8h+lpSrc], xmm0
0x1800149aa  mov     [rsp+0BF8h+var_8F8], rsi
0x1800149b2  mov     [rsp+0BF8h+var_8F0], rbx
0x1800149ba  mov     word ptr [rsp+0BF8h+lpSrc], si
0x1800149c2  mov     r8d, dword ptr [rsp+0BF8h+arg_20]; unsigned __int16 *
0x1800149ca  lea     rdx, [rsp+0BF8h+pszDest]; int *
0x1800149d2  mov     rcx, rdi; this
0x1800149d5  call    ?CheckCacheMatchingPlugin@AppCompatUtility@@YAHPEAHPEBGK@Z; AppCompatUtility::CheckCacheMatchingPlugin(int *,ushort const *,ulong)
0x1800149da  test    eax, eax
0x1800149dc  jz      short loc_180014A28
0x1800149de  lea     rcx, [rsp+0BF8h+lpSrc]; void *
0x1800149e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800149eb  nop
0x1800149ec  lea     rcx, [rsp+0BF8h+var_B68]; this
0x1800149f4  call    ??1_FileAttributesStrs@@QEAA@XZ; _FileAttributesStrs::~_FileAttributesStrs(void)
0x1800149f9  nop
0x1800149fa  lea     rcx, [rsp+0BF8h+var_BA8]
0x1800149ff  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180014a04  nop
0x180014a05  lea     rcx, [rsp+0BF8h+var_888]; void *
0x180014a0d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014a12  nop
0x180014a13  lea     rcx, [rsp+0BF8h+var_8A8]; void *
0x180014a1b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014a20  mov     eax, r14d
0x180014a23  jmp     loc_180015206
0x180014a28  xorps   xmm0, xmm0
0x180014a2b  movups  [rsp+0BF8h+var_8E8], xmm0
0x180014a33  mov     [rsp+0BF8h+var_8D8], rsi
0x180014a3b  mov     [rsp+0BF8h+var_8D0], rsi
0x180014a43  mov     r8d, 4
0x180014a49  lea     rdx, aHash; "Hash"
0x180014a50  lea     rcx, [rsp+0BF8h+var_8E8]
0x180014a58  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180014a5d  nop
0x180014a5e  lea     r8, [rsp+0BF8h+var_8E8]
0x180014a66  lea     rdx, [rsp+0BF8h+Src]
0x180014a6e  lea     rcx, [rsp+0BF8h+var_BA8]
0x180014a73  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180014a78  nop
0x180014a79  lea     rcx, [rsp+0BF8h+var_8E8]; void *
0x180014a81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014a86  xorps   xmm0, xmm0
0x180014a89  movups  [rsp+0BF8h+var_8E8], xmm0
0x180014a91  mov     [rsp+0BF8h+var_8D8], rsi
0x180014a99  mov     [rsp+0BF8h+var_8D0], rsi
0x180014aa1  mov     r8d, 0Ch
0x180014aa7  lea     rdx, aMatchingtext_0; "MatchingText"
0x180014aae  lea     rcx, [rsp+0BF8h+var_8E8]
0x180014ab6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180014abb  nop
0x180014abc  lea     r8, [rsp+0BF8h+var_8E8]
0x180014ac4  lea     rdx, [rsp+0BF8h+Src]
0x180014acc  lea     rcx, [rsp+0BF8h+var_BA8]
0x180014ad1  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180014ad6  nop
0x180014ad7  lea     rcx, [rsp+0BF8h+var_8E8]; void *
0x180014adf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014ae4  xorps   xmm0, xmm0
0x180014ae7  movups  [rsp+0BF8h+var_8E8], xmm0
0x180014aef  mov     [rsp+0BF8h+var_8D8], rsi
0x180014af7  mov     [rsp+0BF8h+var_8D0], rsi
0x180014aff  mov     r8d, 11h
0x180014b05  lea     rdx, aMatchingregext; "MatchingRegexText"
0x180014b0c  lea     rcx, [rsp+0BF8h+var_8E8]
0x180014b14  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180014b19  nop
0x180014b1a  lea     r8, [rsp+0BF8h+var_8E8]
0x180014b22  lea     rdx, [rsp+0BF8h+Src]
0x180014b2a  lea     rcx, [rsp+0BF8h+var_BA8]
0x180014b2f  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180014b34  nop
0x180014b35  lea     rcx, [rsp+0BF8h+var_8E8]; void *
0x180014b3d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014b42  lea     rdx, [rsp+0BF8h+pNumArgs]; pNumArgs
0x180014b47  mov     rcx, r13; lpCmdLine
0x180014b4a  call    cs:__imp_CommandLineToArgvW
0x180014b50  mov     r12, rax
0x180014b53  mov     [rsp+0BF8h+var_B88], rax
0x180014b58  mov     ebx, [rsp+0BF8h+pNumArgs]
0x180014b5c  test    rax, rax
0x180014b5f  jz      loc_1800150A3
0x180014b65  cmp     ebx, r14d
0x180014b68  jl      loc_1800150A3
0x180014b6e  mov     rdx, [rax]; String2
0x180014b71  mov     [rsp+0BF8h+Src], rdx
0x180014b79  lea     rcx, aFeatures; "Features"
0x180014b80  call    wcscmp_0
0x180014b85  test    eax, eax
0x180014b87  jnz     short loc_180014BB7
0x180014b89  mov     r8, r12
0x180014b8c  mov     edx, ebx
0x180014b8e  lea     rcx, [rsp+0BF8h+var_BA8]
0x180014b93  call    ?SupportAllFeatures@AppCompatUtility@@YA_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@HPEAPEAG@Z; AppCompatUtility::SupportAllFeatures(std::set<std::wstring> const &,int,ushort * *)
0x180014b98  test    al, al
0x180014b9a  jz      short loc_180014B9F
0x180014b9c  mov     [rdi], r14d
0x180014b9f  lea     rcx, [rsp+0BF8h+lpSrc]; void *
0x180014ba7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014bac  nop
0x180014bad  mov     r13, [rsp+0BF8h+var_BB8]
0x180014bb2  jmp     loc_180015105
0x180014bb7  or      r13, 0FFFFFFFFFFFFFFFFh
0x180014bbb  mov     rdx, r13
0x180014bbe  mov     rax, [rsp+0BF8h+Src]
0x180014bc6  inc     rdx
0x180014bc9  cmp     [rax+rdx*2], si
0x180014bcd  jnz     short loc_180014BC6
0x180014bcf  cmp     rdx, [rsp+0BF8h+var_8F0]
0x180014bd7  ja      short loc_180014C18
0x180014bd9  lea     rdi, [rsp+0BF8h+lpSrc]
0x180014be1  cmp     [rsp+0BF8h+var_8F0], 7
0x180014bea  cmova   rdi, [rsp+0BF8h+lpSrc]
0x180014bf3  mov     [rsp+0BF8h+var_8F8], rdx
0x180014bfb  lea     rbx, [rdx+rdx]
0x180014bff  mov     r8, rbx; Size
0x180014c02  mov     rdx, rax; Src
0x180014c05  mov     rcx, rdi; void *
0x180014c08  call    memmove_0
0x180014c0d  mov     [rbx+rdi], si
0x180014c11  mov     rdi, [rsp+0BF8h+var_B90]
0x180014c16  jmp     short loc_180014C28
0x180014c18  mov     r9, rax
0x180014c1b  lea     rcx, [rsp+0BF8h+lpSrc]
0x180014c23  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180014c28  lea     rax, [rsp+0BF8h+lpSrc]
0x180014c30  cmp     [rsp+0BF8h+var_8F0], 7
0x180014c39  cmova   rax, [rsp+0BF8h+lpSrc]
0x180014c42  mov     [rsp+0BF8h+var_BD8], rax; unsigned __int64
0x180014c47  lea     r9, aFilepathWs; "FilePath=%ws"
0x180014c4e  mov     r8d, 9CEh
0x180014c54  mov     rdx, r15
  ... truncated ...
```
