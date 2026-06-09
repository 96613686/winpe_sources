# inverted::GetTextKey(inverted::TEXTKEY_FLAGS,ulong,unsigned __int64,wchar_t const *,uint,uchar *,uint *)

- ea: `0x180052b10`
- end: `0x180053abc`
- name: `?GetTextKey@inverted@@YAXW4TEXTKEY_FLAGS@1@K_KPEB_WIPEAEPEAI@Z`
- size: `4012`
- prototype: `void __high(enum inverted::TEXTKEY_FLAGS, unsigned int, unsigned __int64, const wchar_t *, unsigned int, unsigned __int8 *, unsigned int *)`
- caller_count: `4`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800517e0`
- `0x180089e58`
- `0x1800ab000`
- `0x18017ae68`

## callees

- `0x180038f08`
- `0x180052b10`
- `0x180053ac4`
- `0x180054178`
- `0x18005492c`
- `0x180055618`
- `0x18008a284`
- `0x1800bd230`
- `0x1800bd388`
- `0x1800d99b4`
- `0x1800d9e90`
- `0x1801134cc`
- `0x180147154`
- `0x18015708c`
- `0x18015eee4`
- `0x180188d74`
- `0x180188d90`
- `0x180189260`
- `0x180189280`
- `0x18018940c`
- `0x180189474`
- `0x1801895b0`
- `0x180189cce`
- `0x18018a0e1`
- `0x18018a123`
- `0x18018e778`
- `0x18018e8cb`

## import_xrefs

- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180053046`
- `msvcp_win!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180053046`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800535d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800535d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053646`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180053646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005377b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005377b`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x180053473`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x1800536ec`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x180053473`
- `api-ms-win-core-localization-l1-2-0!GetNLSVersionEx` at `0x1800536ec`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180052c15`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180053546`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18005357d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180052c15`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180053546`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18005357d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053165`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053769`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800539ca`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053165`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x180053769`
- `api-ms-win-core-localization-l1-2-0!LCMapStringEx` at `0x1800539ca`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180053117`
- `api-ms-win-core-localization-l1-2-0!IsValidLocaleName` at `0x180053117`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180052f76`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x180052f76`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530e8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530c9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800530e8`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180052b93`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180053098`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18005369e`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180052b93`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x180053098`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18005369e`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x180052fab`
- `ext-ms-win-els-elscore-l1-1-0!MappingFreePropertyBag` at `0x180052fab`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180052f37`
- `ext-ms-win-els-elscore-l1-1-0!MappingRecognizeText` at `0x180052f37`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18005361f`
- `ext-ms-win-els-elscore-l1-1-0!MappingGetServices` at `0x18005361f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall inverted::GetTextKey(
        char a1,
        LCID a2,
        unsigned __int64 a3,
        const WCHAR *a4,
        unsigned int Size,
        WCHAR *a6,
        unsigned int *a7)
{
  unsigned __int64 v7; // r13
  __int64 result; // rax
  char v10; // r12
  char v11; // si
  char v12; // r14
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // edi
  WCHAR *v17; // rbx
  int v18; // eax
  int v19; // esi
  DWORD v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned int *v24; // rax
  unsigned int *v25; // rsi
  DWORD v26; // eax
  unsigned __int64 v27; // rsi
  _WORD *v28; // rax
  WCHAR *v29; // rcx
  __int64 v30; // r9
  LPCWSTR v31; // rax
  WCHAR v32; // dx
  unsigned __int64 v33; // rsi
  int v34; // edx
  const WCHAR *v35; // r10
  int v36; // eax
  int v37; // ecx
  unsigned __int64 v38; // rcx
  LPCWSTR v39; // rdx
  WCHAR *v40; // r8
  __int64 v41; // r9
  __int64 v42; // r11
  WCHAR v43; // ax
  __int64 v44; // r11
  bool v45; // cf
  bool v46; // zf
  HRESULT Services; // esi
  __int64 v48; // r8
  int v49; // ecx
  int v50; // r14d
  bool v51; // zf
  PWSTR v52; // rax
  int v53; // esi
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rsi
  const WCHAR *v56; // r12
  LCID v57; // r14d
  const WCHAR *v58; // rsi
  const unsigned __int16 *v59; // r8
  unsigned int v60; // r13d
  const WCHAR *v61; // r13
  WCHAR *v62; // rdx
  int Error; // ecx
  unsigned int v64; // eax
  unsigned int v65; // r8d
  LPWSTR v66; // r9
  unsigned int v67; // ecx
  int v68; // r11d
  char v69; // r12
  char v70; // dl
  int v71; // edx
  unsigned int v72; // r10d
  unsigned int j; // ecx
  LPWSTR v74; // r11
  unsigned int v75; // r9d
  unsigned int v76; // edx
  unsigned int v77; // r13d
  char v78; // cl
  char v79; // r12
  int v80; // r10d
  signed int v81; // r12d
  void *v82; // rcx
  void *v83; // rdi
  __int64 v84; // rcx
  int v85; // r10d
  char v86; // cl
  const char *v87; // r9
  unsigned int v88; // eax
  const char *v89; // r9
  unsigned int v90; // eax
  const char *v91; // r9
  unsigned int v92; // ecx
  const char *v93; // r9
  const WCHAR *v94; // r12
  unsigned int v95; // eax
  signed int LastError; // eax
  int v97; // edx
  int v98; // r9d
  __int64 v99; // rcx
  unsigned int v100; // r14d
  int v101; // esi
  char v102; // dl
  char v103; // al
  inverted::CLocaleNameCache *v104; // rax
  const WCHAR *LocaleName; // rax
  int SearchKey; // eax
  unsigned __int8 *v107; // r12
  unsigned int v108; // edi
  inverted::CLocaleNameCache *v109; // rax
  const WCHAR *v110; // rax
  int v111; // eax
  unsigned int v112; // eax
  WCHAR *v113; // rdx
  WCHAR *v114; // rax
  int v115; // ecx
  LPWSTR v116; // r13
  signed __int32 v117[8]; // [rsp+0h] [rbp-100h] BYREF
  LPWSTR lpDestStr; // [rsp+20h] [rbp-E0h]
  char v119; // [rsp+50h] [rbp-B0h]
  int v120; // [rsp+54h] [rbp-ACh]
  char v121; // [rsp+58h] [rbp-A8h]
  LPCWSTR pszText; // [rsp+60h] [rbp-A0h] BYREF
  int SearchKeyFlags; // [rsp+68h] [rbp-98h]
  int v124; // [rsp+6Ch] [rbp-94h]
  LCID Locale; // [rsp+70h] [rbp-90h]
  unsigned int v126; // [rsp+74h] [rbp-8Ch]
  LPCWSTR v127; // [rsp+78h] [rbp-88h]
  DWORD dwMapFlags; // [rsp+80h] [rbp-80h]
  LPCWSTR lpSrcStr; // [rsp+88h] [rbp-78h]
  LPVOID pv; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v131; // [rsp+98h] [rbp-68h]
  unsigned __int64 v132; // [rsp+A0h] [rbp-60h]
  LPCWSTR v133; // [rsp+A8h] [rbp-58h]
  _MAPPING_ENUM_OPTIONS pOptions; // [rsp+B0h] [rbp-50h] BYREF
  _MAPPING_PROPERTY_BAG pbag; // [rsp+100h] [rbp+0h] BYREF
  int cchDest[2]; // [rsp+140h] [rbp+40h]
  LPWSTR v137; // [rsp+148h] [rbp+48h]
  _BYTE v138[576]; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3D8h] [rbp+2D8h]

  lpSrcStr = a4;
  v7 = a3;
  Locale = a2;
  result = (__int64)a7;
  v131 = a7;
  if ( !a3 )
  {
    *a7 = 0;
    return result;
  }
  v10 = a1 & 1;
  if ( (a1 & 2) != 0 )
  {
    v11 = 1;
    v12 = 0;
  }
  else
  {
    v11 = 0;
    v12 = 1;
  }
  v119 = v12;
  v121 = v11;
  if ( LCIDToLocaleName(a2, 0, 0, 0) <= 0 && a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v14, v13, v15);
  v16 = 0;
  v17 = 0;
  v133 = 0;
  if ( !v11 )
    goto LABEL_262;
  if ( Locale == 1042 )
  {
    v132 = (unsigned int)v7;
    v33 = (unsigned int)v7 + 1LL;
    if ( v33 >= (unsigned int)v7 )
    {
      pbag.Size = 0;
      if ( is_mul_ok(v33, 2u) )
      {
        v35 = (const WCHAR *)WINRT_IMPL_CoTaskMemAlloc(2 * v33);
        pszText = v35;
        v36 = 0;
        v37 = -2147024882;
        if ( !v35 )
          v36 = -2147024882;
        LODWORD(v127) = v36;
        if ( v36 < 0 )
        {
          pszText = v35;
          v46 = v36 == 0;
        }
        else
        {
          if ( (v35 || (unsigned int)v7 == -1) && v33 <= 0x7FFFFFFF )
          {
            if ( v132 >= 0x7FFFFFFF )
            {
              pszText = v35;
              if ( (unsigned int)v7 != -1 )
                *v35 = 0;
            }
            else
            {
              v38 = v132;
              v39 = lpSrcStr;
              if ( !lpSrcStr )
              {
                v39 = &psz;
                v38 = 0;
              }
              pszText = v35;
              if ( (unsigned int)v7 != -1 )
              {
                v40 = (WCHAR *)v35;
                v41 = 0;
                v42 = (unsigned int)v7 + 1LL;
                while ( v38 )
                {
                  v43 = *v39;
                  if ( !*v39 )
                  {
                    if ( !v33 )
                    {
LABEL_64:
                      *(v40 - 1) = 0;
                      goto LABEL_70;
                    }
                    break;
                  }
                  ++v39;
                  *v40++ = v43;
                  --v38;
                  ++v41;
                  if ( !--v33 )
                    goto LABEL_64;
                }
                *v40 = 0;
                v45 = v42 == v41;
                v44 = v42 - v41;
                if ( !v45 && v44 != 1 && (unsigned __int64)(2 * v44) > 2 )
                  memset_0((void *)&v35[v41 + 1], 0, 2 * v44 - 2);
              }
            }
          }
          else
          {
            *v35 = 0;
            pszText = v35;
          }
LABEL_70:
          *(_OWORD *)&pbag.Size = xmmword_1802DD280;
          Services = 0;
          if ( !byte_18036932C )
          {
            AcquireSRWLockExclusive(&s_srwElsServiceLock);
            if ( !byte_18036932C )
            {
              memset(&pOptions.pszCategory, 0, 56);
              *((_QWORD *)&pOptions + 9) = 0;
              pOptions.Size = 80;
              pOptions.pGuid = (GUID *)&pbag;
              Services = MappingGetServices(&pOptions, &g_scriptAutoDetection, &pdwServicesCount);
              if ( Services >= 0 )
              {
                if ( pdwServicesCount )
                  byte_18036932C = 1;
                else
                  Services = -2147467259;
              }
            }
            ReleaseSRWLockExclusive(&s_srwElsServiceLock);
          }
          if ( Services >= 0 )
          {
            memset(&pbag.prgResultRanges, 0, 56);
            pbag.Size = 64;
            v48 = -1;
            do
              ++v48;
            while ( pszText[v48] );
            Services = MappingRecognizeText(g_scriptAutoDetection, pszText, v48, 0, 0, &pbag);
            if ( Services >= 0 )
            {
              LOBYTE(v49) = 0;
              v126 = v49;
              LODWORD(v127) = 0;
              if ( !pbag.dwRangesCount )
                goto LABEL_83;
              v50 = 0;
              while ( 1 )
              {
                v51 = (_BYTE)v49 == 0;
                if ( (_BYTE)v49 )
                  break;
                v52 = StrStrIW(L"Hang", (PCWSTR)pbag.prgResultRanges[v50].pData);
                v49 = (unsigned __int8)v126;
                if ( v52 )
                  v49 = 1;
                v126 = v49;
                if ( ++v50 >= pbag.dwRangesCount )
                {
                  v51 = (_BYTE)v49 == 0;
                  break;
                }
              }
              v12 = v119;
              if ( v51 )
LABEL_83:
                Services = 1;
              MappingFreePropertyBag(&pbag);
            }
          }
          CoTaskMemFree_0((LPVOID)pszText);
          v46 = Services == 0;
        }
        if ( v46 )
        {
          pszText = 0;
          pv = 0;
          if ( (int)_AllocStringWorker<CTCoAllocPolicy>(
                      v37,
                      v34,
                      (_DWORD)lpSrcStr,
                      v132,
                      (_DWORD)lpDestStr,
                      (__int64)&pv) >= 0 )
          {
            v53 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
                    (PMAPPING_SERVICE_INFO *)g_koreanDecomposition,
                    (LPCWSTR)pv,
                    (wchar_t **)&pszText);
            CoTaskMemFree_0(pv);
            if ( v53 >= 0 )
            {
              lpSrcStr = pszText;
              v17 = (WCHAR *)pszText;
              v133 = pszText;
              v7 = -1;
              do
                ++v7;
              while ( pszText[v7] );
            }
            v12 = v119;
          }
        }
      }
    }
  }
  if ( !v10 )
  {
LABEL_262:
    if ( !`IsIcuSortingDefaultEnabled'::`2'::checked )
    {
      memset(&pbag, 0, 32);
      LODWORD(pbag.Size) = 32;
      if ( GetNLSVersionEx(0x8001u, 0, (LPNLSVERSIONINFOEX)&pbag) )
      {
        if ( (HIDWORD(pbag.Size) & 0xFF000000) == 0x1000000 )
        {
          `IsIcuSortingDefaultEnabled'::`2'::usingICU = 1;
          _InterlockedOr(v117, 0);
        }
        `IsIcuSortingDefaultEnabled'::`2'::checked = 1;
      }
    }
    if ( `IsIcuSortingDefaultEnabled'::`2'::usingICU )
    {
      v20 = 134415363;
    }
    else
    {
      if ( v12 )
      {
        v18 = 1032;
        v19 = 134414337;
      }
      else
      {
        v18 = 1024;
        v19 = 134414339;
      }
      v20 = v18 | v19;
    }
    v22 = (unsigned int)LCMapStringW(Locale, v20, lpSrcStr, v7, a6, Size);
    v24 = v131;
    *v131 = v22;
    if ( (_DWORD)v22 )
    {
      v25 = v24;
    }
    else
    {
      if ( GetLastError() != 122 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x405,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
          v87);
      v88 = LCMapStringW(Locale, v20, lpSrcStr, v7, 0, 0);
      LODWORD(pszText) = v88;
      if ( !v88 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x40C,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
          v89);
      pbag.Size = (size_t)operator new[](v88);
      v90 = LCMapStringW(Locale, v20, lpSrcStr, v7, (LPWSTR)pbag.Size, (int)pszText);
      v92 = v90;
      if ( !v90 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x419,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
          v91);
      if ( Size < v90 )
        v92 = Size;
      v25 = v131;
      *v131 = v92;
      memcpy_0(a6, (const void *)pbag.Size, v92);
      operator delete((void *)pbag.Size);
      v22 = *v25;
    }
    if ( v12 && (_DWORD)v22 )
    {
      v21 = (unsigned int)(v22 - 1);
      if ( *((_BYTE *)a6 + v21) )
        v21 = (unsigned int)v22;
      else
        *v25 = v21;
      for ( ; (_DWORD)v21; *v25 = v21 )
      {
        v21 = (unsigned int)(v21 - 1);
        if ( *((_BYTE *)a6 + v21) != 1 )
          break;
      }
    }
    if ( v121 )
    {
      if ( v10 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v22, v21, v23);
      v22 = *v25;
      while ( v16 < (unsigned int)v22 )
      {
        if ( *((_BYTE *)a6 + v16) == 1 )
        {
          *v25 = v16;
          goto LABEL_26;
        }
        ++v16;
      }
    }
    goto LABEL_26;
  }
  if ( dword_180369330 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_180369330);
    if ( dword_180369330 == -1 )
    {
      TPUtils::combinable<inverted::CLocaleNameCache>::combinable<inverted::CLocaleNameCache>();
      atexit(inverted::GetTextKey_::_19_::_dynamic_atexit_destructor_for__s_localeNameCache__);
      Init_thread_footer(&dword_180369330);
    }
  }
  if ( !`IsIcuSortingDefaultEnabled'::`2'::checked )
  {
    memset(&pbag, 0, 32);
    LODWORD(pbag.Size) = 32;
    if ( GetNLSVersionEx(0x8001u, 0, (LPNLSVERSIONINFOEX)&pbag) )
    {
      if ( (HIDWORD(pbag.Size) & 0xFF000000) == 0x1000000 )
      {
        `IsIcuSortingDefaultEnabled'::`2'::usingICU = 1;
        _InterlockedOr(v117, 0);
      }
      `IsIcuSortingDefaultEnabled'::`2'::checked = 1;
    }
  }
  v26 = 134415361;
  if ( `IsIcuSortingDefaultEnabled'::`2'::usingICU )
    v26 = 134415363;
  dwMapFlags = v26;
  v27 = v7 + 1;
  v28 = operator new[](saturated_mul(v7 + 1, 2u));
  pv = v28;
  if ( v7 == -1 )
  {
    v30 = 2147942487LL;
  }
  else if ( v7 > 0x7FFFFFFE || v27 > 0x7FFFFFFF )
  {
    v30 = 2147942487LL;
    *v28 = 0;
  }
  else
  {
    v29 = v28;
    v30 = 0;
    v31 = lpSrcStr;
    while ( v7 )
    {
      v32 = *v31;
      if ( !*v31 )
      {
        if ( !v27 )
        {
LABEL_44:
          --v29;
          v30 = 2147942522LL;
          break;
        }
        break;
      }
      ++v31;
      *v29++ = v32;
      --v7;
      if ( !--v27 )
        goto LABEL_44;
    }
    *v29 = 0;
  }
  if ( (int)v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
      (const char *)v30,
      (int)lpDestStr);
  CurrentThreadId = (unsigned int)Concurrency::details::platform::GetCurrentThreadId(retaddr);
  for ( i = *(_QWORD *)(qword_180369340 + 8 * (CurrentThreadId % qword_180369348)); i; i = *(_QWORD *)(i + 184) )
  {
    if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      goto LABEL_96;
  }
  i = TPUtils::combinable<inverted::CLocaleNameCache>::_AddLocalItem(
        qword_180369340,
        (unsigned int)CurrentThreadId,
        CurrentThreadId % qword_180369348);
LABEL_96:
  v56 = (const WCHAR *)(i + 8);
  v57 = Locale;
  if ( Locale != *(_DWORD *)(i + 4) )
  {
    if ( !LCIDToLocaleName(Locale, (LPWSTR)(i + 8), 85, 0x8000000u)
      && !LCIDToLocaleName(0, (LPWSTR)(i + 8), 85, 0x8000000u) )
    {
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xD17,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\tquery\\include\\indexdefinition.h",
        v93);
    }
    *(_DWORD *)(i + 4) = v57;
  }
  v58 = (const WCHAR *)pv;
  v127 = (LPCWSTR)pv;
  pbag.Size = 0;
  pszText = 0;
  v60 = Size;
  if ( (!StrCmpIW(v56, L"ko") || !StrCmpIW(v56, L"ko-KR"))
    && !(unsigned int)CScriptAutoDetection::HasScript(&g_scriptAutoDetection, v58, v59) )
  {
    v120 = CKoreanDecomposition::DecomposeKoreanForPrefixMatch(
             (PMAPPING_SERVICE_INFO *)g_koreanDecomposition,
             v58,
             (unsigned __int16 **)&pszText);
    if ( v120 < 0 )
    {
      v82 = (void *)pszText;
      v25 = v131;
      v81 = v120;
      goto LABEL_148;
    }
    pbag.Size = (size_t)pszText;
    v127 = pszText;
  }
  SearchKeyFlags = GetSearchKeyFlags(v56);
  *(_QWORD *)cchDest = 576;
  v137 = 0;
  v25 = v131;
  *v131 = 0;
  v61 = &psz;
  if ( IsValidLocaleName(v56) )
    v61 = v56;
  v62 = (WCHAR *)v138;
  if ( v137 )
    v62 = v137;
  if ( LCMapStringEx(v61, dwMapFlags, v127, -1, v62, cchDest[0], 0, 0, 0) )
  {
    v120 = 0;
    goto LABEL_110;
  }
  Error = ResultFromKnownLastError();
  v120 = Error;
  if ( Error != -2147024774 )
  {
LABEL_108:
    if ( Error >= 0 )
    {
      v64 = 0;
      v116 = v137;
LABEL_145:
      v81 = v120;
LABEL_146:
      *v25 = v64;
      goto LABEL_147;
    }
    v81 = v120;
    goto LABEL_213;
  }
  v94 = v127;
  v95 = LCMapStringEx(v61, dwMapFlags, v127, -1, 0, 0, 0, 0, 0);
  LODWORD(v127) = v95;
  if ( v95 )
  {
    if ( v95 < 0x240uLL )
    {
      v113 = v137;
      v115 = cchDest[0];
    }
    else
    {
      v113 = (WCHAR *)operator new[](v95, (const struct std::nothrow_t *)&std::nothrow);
      v132 = (unsigned __int64)v113;
      v137 = v113;
      if ( !v113 )
      {
        v81 = -2147024882;
        v116 = 0;
        goto LABEL_147;
      }
      v115 = (int)v127;
      *(_QWORD *)cchDest = (unsigned int)v127;
    }
    v114 = (WCHAR *)v138;
    if ( v113 )
      v114 = v113;
    if ( LCMapStringEx(v61, dwMapFlags, v94, -1, v114, v115, 0, 0, 0) )
    {
      v120 = 0;
LABEL_110:
      v65 = cchDest[0];
      v66 = (LPWSTR)v138;
      v116 = v137;
      v132 = (unsigned __int64)v137;
      if ( v137 )
        v66 = v137;
      v67 = 0;
      v68 = 0;
      v69 = SearchKeyFlags;
      while ( v67 < cchDest[0] )
      {
        v70 = *((_BYTE *)v66 + v67);
        if ( v70 == 1 )
        {
          v72 = v67 + 1;
          LODWORD(lpSrcStr) = v67 + 1;
          for ( j = v67 + 1; j < cchDest[0]; ++j )
          {
            if ( *((_BYTE *)v66 + j) == 1 )
            {
              v64 = v68 + 1;
              v126 = v68 + 1;
              if ( v68 != -1 && Size )
              {
                if ( v64 > Size )
                {
                  v64 = 0;
                  v81 = -2147024774;
                  goto LABEL_146;
                }
                LODWORD(v127) = j - 1;
                v74 = (LPWSTR)v138;
                if ( v137 )
                  v74 = v137;
                v124 = 0;
                v75 = 0;
                v76 = 0;
                LODWORD(pszText) = v72;
                v77 = v64;
                do
                {
                  if ( v72 >= v65 )
                    break;
                  if ( v76 >= v65 )
                    break;
                  v78 = *((_BYTE *)v74 + v76);
                  if ( v78 == 1 )
                    break;
                  if ( (unsigned __int8)(v78 + 87) <= 6u || (v69 & 2) != 0 && (unsigned __int8)(v78 + 64) <= 0x39u )
                  {
                    v79 = 0;
                    v80 = 3;
                  }
                  else
                  {
                    v79 = 1;
                    ++v124;
                    v80 = 2;
                  }
                  for ( ; v75 < v64; --v80 )
                  {
                    if ( v76 >= v65 )
                      break;
                    if ( !v80 )
                      break;
                    *((_BYTE *)a6 + v75++) = *((_BYTE *)v74 + v76++);
                  }
                  if ( (SearchKeyFlags & 4) != 0 )
                  {
                    v46 = v79 == 0;
                    v69 = SearchKeyFlags;
                    if ( !v46 )
                    {
                      if ( v75 >= v64 )
                        goto LABEL_143;
                      if ( (SearchKeyFlags & 1) == 0 )
                      {
                        v85 = (int)lpSrcStr;
                        v86 = *((_BYTE *)v74 + (unsigned int)lpSrcStr);
                        if ( v86 == 1 )
                        {
                          *((_BYTE *)a6 + v75) = 2;
                        }
                        else
                        {
                          *((_BYTE *)a6 + v75) = v86;
                          LODWORD(lpSrcStr) = v85 + 1;
                        }
                      }
                      ++v75;
                    }
                  }
                  else
                  {
                    v69 = SearchKeyFlags;
                  }
                  v72 = (unsigned int)lpSrcStr;
                }
                while ( v75 < v64 );
                if ( (v69 & 4) == 0 )
                  goto LABEL_144;
LABEL_143:
                if ( (v69 & 1) != 0 )
                {
                  v97 = v124;
                  v98 = v124 - (_DWORD)v127 + (_DWORD)pszText - 1;
                  LODWORD(v99) = 0;
                  if ( v64 )
                  {
                    v100 = (unsigned int)v127;
                    v101 = v120;
                    do
                    {
                      if ( v100 >= v65 || !v97 )
                        break;
                      v102 = *((_BYTE *)a6 + (unsigned int)v99);
                      if ( (unsigned __int8)(v102 + 87) <= 6u || (v69 & 2) != 0 && (unsigned __int8)(v102 + 64) <= 0x39u )
                      {
                        LODWORD(v99) = v99 + 3;
                        v97 = v124;
                      }
                      else
                      {
                        v99 = (unsigned int)(v99 + 2);
                        if ( (unsigned int)v99 < v77 )
                        {
                          if ( v98 )
                          {
                            --v98;
                            v103 = 2;
                          }
                          else
                          {
                            v103 = *((_BYTE *)v74 + v100--);
                          }
                          *((_BYTE *)a6 + v99) = v103;
                          LODWORD(v99) = v99 + 1;
                        }
                        v97 = --v124;
                      }
                    }
                    while ( (unsigned int)v99 < v77 );
                    v120 = v101;
                    v126 = v77;
                    v25 = v131;
                    v57 = Locale;
                  }
                }
LABEL_144:
                *((_BYTE *)a6 + v77 - 1) = 0;
                v64 = v126;
                v116 = (LPWSTR)v132;
              }
              goto LABEL_145;
            }
          }
          break;
        }
        if ( (unsigned __int8)(v70 + 87) <= 6u || (SearchKeyFlags & 2) != 0 && (unsigned __int8)(v70 + 64) <= 0x39u )
          v71 = 3;
        else
          v71 = 2;
        v67 += v71;
        if ( v71 + (unsigned int)((SearchKeyFlags & 4) != 0) > 3 )
          v68 += 3;
        else
          v68 += v71 + ((SearchKeyFlags & 4) != 0);
      }
      v64 = 0;
      goto LABEL_145;
    }
    Error = ResultFromKnownLastError();
    v120 = Error;
    goto LABEL_108;
  }
  LastError = GetLastError();
  v81 = LastError;
  if ( LastError > 0 )
    v81 = (unsigned __int16)LastError | 0x80070000;
  if ( v81 >= 0 )
    v81 = -2147467259;
LABEL_213:
  v116 = v137;
LABEL_147:
  operator delete(v116);
  v82 = (void *)pbag.Size;
  v60 = Size;
LABEL_148:
  CoTaskMemFree_0(v82);
  if ( v81 < 0 )
  {
    if ( v81 != -2147024774 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3CB,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
        (const char *)(unsigned int)v81,
        (int)lpDestStr);
    v104 = (inverted::CLocaleNameCache *)TPUtils::combinable<inverted::CLocaleNameCache>::local();
    LocaleName = inverted::CLocaleNameCache::GetLocaleName(v104, v57);
    SearchKey = CreateSearchKey(LocaleName, dwMapFlags, (const unsigned __int16 *)pv, 0, 0, v25);
    if ( SearchKey < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
        (const char *)(unsigned int)SearchKey,
        (int)lpDestStr);
    v107 = (unsigned __int8 *)operator new[](*v25);
    pbag.Size = (size_t)v107;
    v108 = *v25;
    v109 = (inverted::CLocaleNameCache *)TPUtils::combinable<inverted::CLocaleNameCache>::local();
    v110 = inverted::CLocaleNameCache::GetLocaleName(v109, v57);
    LODWORD(lpDestStr) = v108;
    v83 = pv;
    v111 = CreateSearchKey(v110, dwMapFlags, (const unsigned __int16 *)pv, v107, (unsigned int)lpDestStr, v25);
    if ( v111 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3DB,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\inverted\\invertedutils.cpp",
        (const char *)(unsigned int)v111,
        (int)lpDestStr);
    v112 = *v25;
    if ( v60 < *v25 )
      v112 = v60;
    *v25 = v112;
    memcpy_0(a6, v107, v112);
    operator delete(v107);
  }
  else
  {
    v83 = pv;
  }
  if ( *v25 )
  {
    v84 = *v25 - 1;
    if ( !*((_BYTE *)a6 + v84) )
      *v25 = v84;
  }
  operator delete(v83);
LABEL_26:
  if ( v17 )
    CoTaskMemFree_0(v17);
  result = *v25;
  if ( (_DWORD)result )
  {
    result = (unsigned int)(result - 1);
    if ( *((_BYTE *)a6 + result) == 1 )
      return MicrosoftTelemetryAssertTriggeredNoArgs(v22, v21, v23);
  }
  return result;
}

```

## disassembly

```asm
0x180052b10  mov     [rsp-8+arg_0], rbx
0x180052b15  push    rbp
0x180052b16  push    rsi
0x180052b17  push    rdi
0x180052b18  push    r12
0x180052b1a  push    r13
0x180052b1c  push    r14
0x180052b1e  push    r15
0x180052b20  lea     rbp, [rsp-2A0h]
0x180052b28  sub     rsp, 3A0h
0x180052b2f  mov     rax, cs:__security_cookie
0x180052b36  xor     rax, rsp
0x180052b39  mov     [rbp+2D0h+var_40], rax
0x180052b40  mov     [rbp+2D0h+lpSrcStr], r9
0x180052b44  mov     r13, r8
0x180052b47  mov     ebx, edx
0x180052b49  mov     [rsp+3D0h+Locale], edx
0x180052b4d  mov     r15, [rbp+2D0h+arg_28]
0x180052b54  mov     rax, [rbp+2D0h+arg_30]
0x180052b5b  mov     [rbp+2D0h+var_338], rax
0x180052b5f  test    r8, r8
0x180052b62  jz      loc_1800535C1
0x180052b68  movzx   r12d, cl
0x180052b6c  and     r12b, 1
0x180052b70  test    cl, 2
0x180052b73  jz      loc_18005303B
0x180052b79  mov     sil, 1
0x180052b7c  xor     r14b, r14b
0x180052b7f  mov     [rsp+3D0h+var_380], r14b
0x180052b84  mov     byte ptr [rsp+3D0h+var_37C+4], sil
0x180052b89  xor     r9d, r9d; dwFlags
0x180052b8c  xor     r8d, r8d; cchName
0x180052b8f  xor     edx, edx; lpName
0x180052b91  mov     ecx, ebx; Locale
0x180052b93  call    cs:__imp_LCIDToLocaleName
0x180052b99  test    eax, eax
0x180052b9b  jg      short loc_180052BA6
0x180052b9d  test    ebx, ebx
0x180052b9f  jz      short loc_180052BA6
0x180052ba1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180052ba6  xor     edi, edi
0x180052ba8  mov     ebx, edi
0x180052baa  mov     [rbp+2D0h+var_328], rbx
0x180052bae  test    sil, sil
0x180052bb1  jz      short loc_180052BCA
0x180052bb3  cmp     [rsp+3D0h+Locale], 412h
0x180052bbb  jz      loc_180052DB8
0x180052bc1  test    r12b, r12b
0x180052bc4  jnz     loc_180052CC6
0x180052bca  cmp     cs:?checked@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::checked
0x180052bd1  jz      loc_180053456
0x180052bd7  cmp     cs:?usingICU@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::usingICU
0x180052bde  jnz     loc_180052CBC
0x180052be4  test    r14b, r14b
0x180052be7  jz      loc_180052CAD
0x180052bed  mov     eax, 408h
0x180052bf2  mov     esi, 8030001h
0x180052bf7  or      esi, eax
0x180052bf9  mov     eax, dword ptr [rbp+2D0h+Size]
0x180052bff  mov     [rsp+3D0h+cchDest], eax; cchDest
0x180052c03  mov     [rsp+3D0h+lpDestStr], r15; lpDestStr
0x180052c08  mov     r9d, r13d; cchSrc
0x180052c0b  mov     r8, [rbp+2D0h+lpSrcStr]; lpSrcStr
0x180052c0f  mov     edx, esi; dwMapFlags
0x180052c11  mov     ecx, [rsp+3D0h+Locale]; Locale
0x180052c15  call    cs:__imp_LCMapStringW
0x180052c1b  mov     ecx, eax
0x180052c1d  mov     rax, [rbp+2D0h+var_338]
0x180052c21  mov     [rax], ecx
0x180052c23  test    ecx, ecx
0x180052c25  jz      loc_180053521
0x180052c2b  mov     rsi, rax
0x180052c2e  test    r14b, r14b
0x180052c31  jnz     loc_1800534B5
0x180052c37  cmp     byte ptr [rsp+3D0h+var_37C+4], 0
0x180052c3c  jz      short loc_180052C63
0x180052c3e  test    r12b, r12b
0x180052c41  jnz     loc_180053950
0x180052c47  mov     ecx, [rsi]
0x180052c49  nop     dword ptr [rax+00000000h]
0x180052c50  cmp     edi, ecx
0x180052c52  jnb     short loc_180052C63
0x180052c54  mov     eax, edi
0x180052c56  cmp     byte ptr [rax+r15], 1
0x180052c5b  jz      short loc_180052C61
0x180052c5d  inc     edi
0x180052c5f  jmp     short loc_180052C50
0x180052c61  mov     [rsi], edi
0x180052c63  test    rbx, rbx
0x180052c66  jz      short loc_180052C70
0x180052c68  mov     rcx, rbx; pv
0x180052c6b  call    CoTaskMemFree_0
0x180052c70  mov     eax, [rsi]
0x180052c72  test    eax, eax
0x180052c74  jz      short loc_180052C83
0x180052c76  dec     eax
0x180052c78  cmp     byte ptr [rax+r15], 1
0x180052c7d  jz      loc_180053AB2
0x180052c83  mov     rcx, [rbp+2D0h+var_40]
0x180052c8a  xor     rcx, rsp; StackCookie
0x180052c8d  call    __security_check_cookie
0x180052c92  mov     rbx, [rsp+3D0h+arg_0]
0x180052c9a  add     rsp, 3A0h
0x180052ca1  pop     r15
0x180052ca3  pop     r14
0x180052ca5  pop     r13
0x180052ca7  pop     r12
0x180052ca9  pop     rdi
0x180052caa  pop     rsi
0x180052cab  pop     rbp
0x180052cac  retn
0x180052cad  mov     eax, 400h
0x180052cb2  mov     esi, 8030003h
0x180052cb7  jmp     loc_180052BF7
0x180052cbc  mov     esi, 8030403h
0x180052cc1  jmp     loc_180052BF9
0x180052cc6  mov     ecx, cs:_tls_index
0x180052ccc  mov     rax, gs:58h
0x180052cd5  mov     edx, 10h
0x180052cda  mov     rax, [rax+rcx*8]
0x180052cde  mov     ecx, [rdx+rax]
0x180052ce1  cmp     cs:dword_180369330, ecx
0x180052ce7  jg      loc_180053651
0x180052ced  cmp     cs:?checked@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::checked
0x180052cf4  jz      loc_1800536CF
0x180052cfa  mov     eax, 8030401h
0x180052cff  mov     esi, 8030403h
0x180052d04  cmp     cs:?usingICU@?1??IsIcuSortingDefaultEnabled@@9@4HA, 0; int `IsIcuSortingDefaultEnabled'::`2'::usingICU
0x180052d0b  cmovnz  eax, esi
0x180052d0e  mov     [rbp+2D0h+dwMapFlags], eax
0x180052d11  lea     rsi, [r13+1]
0x180052d15  mov     eax, 2
0x180052d1a  mul     rsi
0x180052d1d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180052d24  cmovb   rax, rcx
0x180052d28  mov     rcx, rax; unsigned __int64
0x180052d2b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180052d30  mov     [rbp+2D0h+pv], rax
0x180052d34  test    rsi, rsi
0x180052d37  jz      loc_1800539E4
0x180052d3d  cmp     r13, 7FFFFFFEh
0x180052d44  ja      loc_1800537A8
0x180052d4a  cmp     rsi, 7FFFFFFFh
0x180052d51  ja      loc_1800537A8
0x180052d57  mov     rcx, rax
0x180052d5a  mov     r9d, edi; char *
0x180052d5d  mov     rax, [rbp+2D0h+lpSrcStr]
0x180052d61  test    r13, r13
0x180052d64  jz      short loc_180052D93
0x180052d66  movzx   edx, word ptr [rax]
0x180052d69  test    dx, dx
0x180052d6c  jz      short loc_180052D8E
0x180052d6e  add     rax, 2
0x180052d72  mov     [rcx], dx
0x180052d75  add     rcx, 2
0x180052d79  dec     r13
0x180052d7c  sub     rsi, 1
0x180052d80  jnz     short loc_180052D61
0x180052d82  sub     rcx, 2
0x180052d86  mov     r9d, 8007007Ah
0x180052d8c  jmp     short loc_180052D93
0x180052d8e  test    rsi, rsi
0x180052d91  jz      short loc_180052D82
0x180052d93  mov     [rcx], di
0x180052d96  mov     rcx, [rbp+2D8h]; this
0x180052d9d  test    r9d, r9d
0x180052da0  jns     loc_180053046
0x180052da6  lea     r8, aOnecoreuapBase_301; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180052dad  mov     edx, 3BDh; void *
0x180052db2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052db8  mov     eax, r13d
0x180052dbb  mov     [rbp+2D0h+var_330], rax
0x180052dbf  lea     rsi, [rax+1]
0x180052dc3  cmp     rsi, rax
0x180052dc6  jb      loc_180052BC1
0x180052dcc  mov     [rbp+2D0h+pbag.Size], rdi
0x180052dd0  mov     eax, 2
0x180052dd5  mul     rsi
0x180052dd8  test    rdx, rdx
0x180052ddb  jnz     loc_180052BC1
0x180052de1  mov     rcx, rax; cb
0x180052de4  call    WINRT_IMPL_CoTaskMemAlloc
0x180052de9  mov     r10, rax
0x180052dec  mov     [rsp+3D0h+pszText], rax
0x180052df1  mov     eax, edi
0x180052df3  test    r10, r10
0x180052df6  mov     ecx, 8007000Eh
0x180052dfb  cmovz   eax, ecx
0x180052dfe  mov     dword ptr [rsp+3D0h+var_358], eax
0x180052e02  test    eax, eax
0x180052e04  js      loc_180052EB3
0x180052e0a  test    r10, r10
0x180052e0d  jz      loc_180053A0F
0x180052e13  cmp     rsi, 7FFFFFFFh
0x180052e1a  ja      loc_180053A18
0x180052e20  mov     rax, [rbp+2D0h+var_330]
0x180052e24  cmp     rax, 7FFFFFFFh
0x180052e2a  jnb     loc_1800539F8
0x180052e30  mov     rcx, rax
0x180052e33  mov     rax, [rbp+2D0h+lpSrcStr]
0x180052e37  mov     rdx, rax
0x180052e3a  test    rax, rax
0x180052e3d  jz      loc_180053A26
0x180052e43  mov     [rsp+3D0h+pszText], r10
0x180052e48  test    rsi, rsi
0x180052e4b  jz      short loc_180052EC2
0x180052e4d  mov     r8, r10
0x180052e50  mov     r9, rdi
0x180052e53  mov     r11, rsi
0x180052e56  test    rcx, rcx
0x180052e59  jz      short loc_180052E87
0x180052e5b  movzx   eax, word ptr [rdx]
0x180052e5e  test    ax, ax
0x180052e61  jz      short loc_180052E82
0x180052e63  add     rdx, 2
0x180052e67  mov     [r8], ax
0x180052e6b  add     r8, 2
0x180052e6f  dec     rcx
0x180052e72  inc     r9
0x180052e75  sub     rsi, 1
0x180052e79  jnz     short loc_180052E56
0x180052e7b  mov     [r8-2], di
0x180052e80  jmp     short loc_180052EC2
0x180052e82  test    rsi, rsi
0x180052e85  jz      short loc_180052E7B
0x180052e87  mov     [r8], di
0x180052e8b  sub     r11, r9
0x180052e8e  cmp     r11, 1
0x180052e92  jbe     short loc_180052EC2
0x180052e94  lea     r8, [r11+r11]
0x180052e98  cmp     r8, 2
0x180052e9c  jbe     short loc_180052EC2
0x180052e9e  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180052ea2  add     r10, 2
0x180052ea6  lea     rcx, [r10+r9*2]; void *
0x180052eaa  xor     edx, edx; Val
0x180052eac  call    memset_0
0x180052eb1  jmp     short loc_180052EC2
0x180052eb3  mov     [rsp+3D0h+pszText], r10
0x180052eb8  mov     esi, eax
0x180052eba  test    eax, eax
0x180052ebc  js      loc_180052FBD
0x180052ec2  movups  xmm0, cs:xmmword_1802DD280
0x180052ec9  movaps  xmmword ptr [rbp+2D0h+pbag.Size], xmm0
0x180052ecd  mov     esi, edi
0x180052ecf  cmp     cs:byte_18036932C, sil
0x180052ed6  jz      loc_1800535CA
0x180052edc  test    esi, esi
0x180052ede  js      loc_180052FB1
0x180052ee4  mov     [rbp+2D0h+pbag.prgResultRanges], rdi
0x180052ee8  xorps   xmm0, xmm0
0x180052eeb  movdqa  xmmword ptr [rbp+2D0h+pbag.dwRangesCount], xmm0
0x180052ef0  xorps   xmm1, xmm1
0x180052ef3  movdqa  xmmword ptr [rbp+2D0h+pbag.dwServiceDataSize], xmm1
0x180052ef8  movdqa  xmmword ptr [rbp+2D0h+pbag.dwCallerDataSize], xmm0
0x180052efd  mov     [rbp+2D0h+pbag.Size], 40h ; '@'
0x180052f05  mov     r8, 0FFFFFFFFFFFFFFFFh
0x180052f0c  mov     rax, [rsp+3D0h+pszText]
0x180052f11  inc     r8; dwLength
0x180052f14  cmp     word ptr [rax+r8*2], 0
0x180052f1a  jnz     short loc_180052F11
0x180052f1c  lea     rcx, [rbp+2D0h+pbag]
0x180052f20  mov     qword ptr [rsp+3D0h+cchDest], rcx; pbag
0x180052f25  mov     [rsp+3D0h+lpDestStr], rdi; pOptions
0x180052f2a  xor     r9d, r9d; dwIndex
0x180052f2d  mov     rdx, rax; pszText
0x180052f30  mov     rcx, cs:?g_scriptAutoDetection@@3VCScriptAutoDetection@@A; pServiceInfo
0x180052f37  call    cs:__imp_MappingRecognizeText
0x180052f3d  mov     esi, eax
0x180052f3f  test    eax, eax
0x180052f41  js      short loc_180052FB1
0x180052f43  xor     cl, cl
0x180052f45  mov     [rsp+3D0h+var_35C], ecx
0x180052f49  mov     dword ptr [rsp+3D0h+var_358], edi
0x180052f4d  mov     eax, 1
0x180052f52  cmp     [rbp+2D0h+pbag.dwRangesCount], 0
0x180052f56  jbe     short loc_180052FA5
0x180052f58  mov     r14d, edi
0x180052f5b  test    cl, cl
0x180052f5d  jnz     short loc_180052F9D
0x180052f5f  mov     eax, r14d
0x180052f62  lea     rcx, [rax+rax*8]
0x180052f66  mov     rdx, [rbp+2D0h+pbag.prgResultRanges]
0x180052f6a  mov     rdx, [rdx+rcx*8+18h]; pszSrch
0x180052f6f  lea     rcx, pszFirst; "Hang"
0x180052f76  call    cs:__imp_StrStrIW
0x180052f7c  mov     ecx, [rsp+3D0h+var_35C]
0x180052f80  movzx   ecx, cl
0x180052f83  test    rax, rax
0x180052f86  mov     eax, 1
0x180052f8b  cmovnz  ecx, eax
0x180052f8e  mov     [rsp+3D0h+var_35C], ecx
0x180052f92  inc     r14d
0x180052f95  cmp     r14d, [rbp+2D0h+pbag.dwRangesCount]
0x180052f99  jb      short loc_180052F5B
0x180052f9b  test    cl, cl
0x180052f9d  movzx   r14d, [rsp+3D0h+var_380]
0x180052fa3  jnz     short loc_180052FA7
0x180052fa5  mov     esi, eax
0x180052fa7  lea     rcx, [rbp+2D0h+pbag]; pBag
  ... truncated ...
```
