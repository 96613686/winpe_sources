# Windows::Usage::RestartAcceptable(uint,std::optional<double>,uchar)

- ea: `0x140244160`
- end: `0x140245353`
- name: `?RestartAcceptable@Usage@Windows@@UEBA?AUDeferReasons@SystemInterface@@IV?$optional@N@std@@E@Z`
- size: `4595`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `service_task, broker_com_uri`

## callees

- `0x140024de0`
- `0x140040184`
- `0x1400413a8`
- `0x140043814`
- `0x140045404`
- `0x140053618`
- `0x140057a20`
- `0x1400722b4`
- `0x1400c695c`
- `0x14012c67c`
- `0x14012d864`
- `0x14018a6dc`
- `0x14018aaec`
- `0x140243d30`
- `0x140244160`
- `0x1402472e0`
- `0x14036f240`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140245145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402451f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140245145`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1402451f7`
- `OLEAUT32!__imp_SysFreeString` at `0x140244b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x140244b8a`
- `OLEAUT32!__imp_SysFreeString` at `0x140244b7a`
- `OLEAUT32!__imp_SysFreeString` at `0x140244b8a`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140245110`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140245110`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1402450ce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140245171`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1402450ce`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x140245171`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140245121`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1402451d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x140245121`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1402451d7`

## string_xrefs

- `0x140245213`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024522c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024524b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140245264`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140245292`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402452ab`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402452c4`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402452dd`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1402452f6`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14024530f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140245328`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140245341`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140244f6e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`
- `0x140245279`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Usage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
char *__fastcall Windows::Usage::RestartAcceptable(__int64 a1, char *a2, int a3, __int64 a4, unsigned __int8 a5)
{
  int v8; // r15d
  int v9; // edi
  __int64 v10; // r14
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rsi
  char v13; // cl
  int v14; // eax
  volatile signed __int32 *v15; // rbx
  _QWORD *v17; // rax
  bool v18; // r12
  volatile signed __int32 *v19; // rsi
  void (__fastcall *v20)(__int64, int *, __int64); // rsi
  int *traits_2_unsigned_short; // rax
  const char *v22; // r9
  __int64 v23; // r11
  __int64 v24; // rax
  volatile signed __int32 *v25; // rsi
  char v26; // r12
  _QWORD *v27; // rax
  volatile signed __int32 *v28; // rsi
  void (__fastcall *v29)(__int64, int *, __int64); // rsi
  wchar_t *v30; // rax
  const char *v31; // r9
  __int64 v32; // r11
  __int64 v33; // rax
  volatile signed __int32 *v34; // rsi
  void (__fastcall *v35)(__int64, int *, __int64); // rsi
  int *v36; // rax
  const char *v37; // r9
  __int64 v38; // r11
  __int64 v39; // rax
  volatile signed __int32 *v40; // rsi
  void (__fastcall *v41)(__int64, int *, __int64); // rsi
  __int16 *v42; // rax
  const char *v43; // r9
  __int64 v44; // r11
  __int64 v45; // rax
  volatile signed __int32 *v46; // rsi
  void (__fastcall *v47)(__int64, int *, __int64); // rsi
  wchar_t *v48; // rax
  const char *v49; // r9
  __int64 v50; // r11
  __int64 v51; // rax
  volatile signed __int32 *v52; // rsi
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // rsi
  __int64 v56; // rsi
  void (__fastcall *v57)(__int64, int *, __int64); // rsi
  __int16 *v58; // rax
  const char *v59; // r9
  __int64 v60; // r11
  __int64 v61; // rax
  volatile signed __int32 *v62; // rsi
  void (__fastcall *v63)(__int64, int *, __int64); // rsi
  int *v64; // rax
  const char *v65; // r9
  __int64 v66; // r11
  __int64 v67; // rax
  volatile signed __int32 *v68; // rsi
  unsigned int UserDisplayState; // eax
  unsigned int v70; // r15d
  void (__fastcall *v71)(__int64, int *, _QWORD); // rsi
  __int16 *v72; // rax
  const char *v73; // r9
  __int64 v74; // r11
  __int64 v75; // rax
  volatile signed __int32 *v76; // rsi
  void (__fastcall *v77)(__int64, int *, __int64); // rsi
  int *v78; // rax
  const char *v79; // r9
  __int64 v80; // r11
  __int64 v81; // rax
  volatile signed __int32 *v82; // rsi
  void (__fastcall *v83)(__int64, int *, __int64); // rsi
  __int16 *v84; // rax
  const char *v85; // r9
  __int64 v86; // r11
  __int64 v87; // rax
  volatile signed __int32 *v88; // rsi
  void (__fastcall *v89)(__int64, int *, __int64); // rsi
  int *v90; // rax
  const char *v91; // r9
  __int64 v92; // r11
  __int64 v93; // rax
  volatile signed __int32 *v94; // rsi
  int v95; // eax
  char *v96; // rdi
  volatile signed __int32 *v97; // rbx
  void (__fastcall *v98)(__int64, int *, __int64); // rbx
  int *v99; // rax
  const char *v100; // r9
  __int64 v101; // r11
  __int64 v102; // rax
  char *v103; // rbx
  LPWSTR v104; // rax
  char *v105; // rbx
  const WCHAR *v106; // rcx
  LPWSTR FileNameW; // rax
  int v108[2]; // [rsp+20h] [rbp-E0h] BYREF
  volatile signed __int32 *v109; // [rsp+28h] [rbp-D8h]
  char v110[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v111; // [rsp+34h] [rbp-CCh]
  __int128 v112; // [rsp+38h] [rbp-C8h] BYREF
  char *v113; // [rsp+48h] [rbp-B8h]
  char v114[8]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v115[14]; // [rsp+58h] [rbp-A8h] BYREF
  char *v116; // [rsp+C8h] [rbp-38h] BYREF
  volatile signed __int32 *v117; // [rsp+D0h] [rbp-30h]
  BSTR bstrString; // [rsp+D8h] [rbp-28h] BYREF
  BSTR v119; // [rsp+E0h] [rbp-20h] BYREF
  LPCWSTR pszPath[2]; // [rsp+E8h] [rbp-18h] BYREF
  __m128i si128; // [rsp+F8h] [rbp-8h]
  __int64 v122; // [rsp+110h] [rbp+10h] BYREF
  __int128 v123; // [rsp+118h] [rbp+18h] BYREF
  __int128 v124; // [rsp+128h] [rbp+28h]
  __int128 v125; // [rsp+138h] [rbp+38h] BYREF
  __int128 v126; // [rsp+148h] [rbp+48h]
  __int128 v127; // [rsp+158h] [rbp+58h] BYREF
  __int64 v128; // [rsp+168h] [rbp+68h]
  __int64 v129; // [rsp+170h] [rbp+70h]
  __int128 v130; // [rsp+178h] [rbp+78h] BYREF
  __int64 v131; // [rsp+188h] [rbp+88h]
  __int64 v132; // [rsp+190h] [rbp+90h]
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v113 = a2;
  v116 = a2;
  v8 = 0;
  v111 = 0;
  v122 = 0;
  v123 = 0;
  *(_QWORD *)&v124 = 0;
  *((_QWORD *)&v124 + 1) = 7;
  LOWORD(v123) = 0;
  v125 = 0;
  *(_QWORD *)&v126 = 0;
  *((_QWORD *)&v126 + 1) = 7;
  LOWORD(v125) = 0;
  v127 = 0;
  v128 = 0;
  v129 = 7;
  LOWORD(v127) = 0;
  v130 = 0;
  v131 = 0;
  v132 = 7;
  LOWORD(v130) = 0;
  v9 = 0;
  v112 = 0;
  SystemInterface::Service::GetSystem(&v112);
  v10 = v112;
  v11 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v112 + 48LL))(v112, v108);
  (*(void (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*v11 + 80LL))(*v11, &bstrString);
  v12 = v109;
  if ( v109 )
  {
    if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = BYTE4(bstrString);
  if ( BYTE4(bstrString) )
  {
    v14 = (int)bstrString;
    if ( ((unsigned __int16)bstrString & 0x400) != 0 )
    {
      std::wstring::operator=(&v130, L"TestOverride_gameModeReason");
      v14 = (int)bstrString;
      v13 = BYTE4(bstrString);
    }
    if ( !v13 )
      goto LABEL_168;
    if ( (v14 & 2) != 0 )
    {
      std::wstring::operator=(&v125, L"TestOverride_displayReason");
      v14 = (int)bstrString;
      v13 = BYTE4(bstrString);
    }
    if ( !v13 )
      goto LABEL_168;
    if ( (v14 & 0x10) != 0 )
    {
      std::wstring::operator=(&v123, L"TestOverride_systemReason");
      v14 = (int)bstrString;
      v13 = BYTE4(bstrString);
    }
    if ( !v13 )
LABEL_168:
      std::_Throw_bad_optional_access();
    LODWORD(v122) = v14 & ~a3;
    SystemInterface::DeferReasons::DeferReasons(a2, &v122);
    v15 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
    if ( *((_QWORD *)&v112 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
    std::wstring::~wstring(&v130);
    std::wstring::~wstring(&v127);
    std::wstring::~wstring(&v125);
    std::wstring::~wstring(&v123);
    return a2;
  }
  else
  {
    v18 = 0;
    if ( (a3 & 4) == 0 )
    {
      v17 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, v108);
      v8 = 2;
      v111 = 2;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v17 + 16LL))(*v17) < a5 )
        v18 = 1;
    }
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      v19 = v109;
      if ( v109 )
      {
        if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
    }
    if ( v18 )
    {
      v9 = 4;
      v20 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v10 + 104LL))(
                                                                            v10,
                                                                            &v116)
                                                           + 256LL);
      traits_2_unsigned_short = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                         L"Defer reason: low battery",
                                         &dword_1404706F4,
                                         0);
      if ( traits_2_unsigned_short == &dword_1404706F4
        || (v24 = ((char *)traits_2_unsigned_short - (char *)L"Defer reason: low battery") >> 1, v24 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v22);
      }
      *(_QWORD *)v108 = L"Defer reason: low battery";
      v109 = (volatile signed __int32 *)v24;
      v20(v23, v108, 1);
      v25 = v117;
      v26 = 0;
      if ( v117 )
      {
        if ( _InterlockedExchangeAdd(v117 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
    }
    else
    {
      v26 = 0;
    }
    if ( (a3 & 0x40) == 0 )
    {
      v27 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v10 + 56LL))(v10, v108);
      v8 |= 4u;
      v111 = v8;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v27 + 40LL))(*v27) )
        v26 = 1;
    }
    if ( (v8 & 4) != 0 )
    {
      v28 = v109;
      if ( v109 )
      {
        if ( _InterlockedExchangeAdd(v109 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
    }
    if ( v26 )
    {
      v9 |= 0x40u;
      v29 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v10 + 104LL))(
                                                                            v10,
                                                                            &v116)
                                                           + 256LL);
      v30 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: not on AC",
                         L"Defer reason: user active",
                         0);
      if ( v30 == L"Defer reason: user active" || (v33 = v30 - L"Defer reason: not on AC", v33 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v31);
      *(_QWORD *)v108 = L"Defer reason: not on AC";
      v109 = (volatile signed __int32 *)v33;
      v29(v32, v108, 1);
      v34 = v117;
      if ( v117 )
      {
        if ( _InterlockedExchangeAdd(v117 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
    }
    if ( (a3 & 1) == 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1) )
    {
      v9 |= 1u;
      v35 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v10 + 104LL))(
                                                                            v10,
                                                                            &v116)
                                                           + 256LL);
      v36 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"Defer reason: user active",
                     &dword_140470684,
                     0);
      if ( v36 == &dword_140470684 || (v39 = ((char *)v36 - (char *)L"Defer reason: user active") >> 1, v39 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v37);
      *(_QWORD *)v108 = L"Defer reason: user active";
      v109 = (volatile signed __int32 *)v39;
      v35(v38, v108, 1);
      v40 = v117;
      if ( v117 )
      {
        if ( _InterlockedExchangeAdd(v117 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
          if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
    }
    if ( (a3 & 0x12) != 0x12 )
    {
      if ( (a3 & 2) == 0 && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0) )
      {
        v9 |= 2u;
        v41 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v10 + 104LL))(
                                                                              v10,
                                                                              &v116)
                                                             + 256LL);
        v42 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Defer reason: display needed",
                           word_1404705E2,
                           0);
        if ( v42 == word_1404705E2 || (v45 = ((char *)v42 - (char *)L"Defer reason: display needed") >> 1, v45 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v43);
        *(_QWORD *)v108 = L"Defer reason: display needed";
        v109 = (volatile signed __int32 *)v45;
        v41(v44, v108, 1);
        v46 = v117;
        if ( v117 )
        {
          if ( !_InterlockedDecrement(v117 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
            if ( !_InterlockedDecrement(v46 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
          }
        }
      }
      if ( (a3 & 0x10) == 0 && (*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a1 + 48LL))(a1, 0) )
      {
        v9 |= 0x10u;
        v47 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, char **))(*(_QWORD *)v10 + 104LL))(
                                                                              v10,
                                                                              &v116)
                                                             + 256LL);
        v48 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Defer reason: system needed",
                           L"Defer reason: not on AC",
                           0);
        if ( v48 == L"Defer reason: not on AC" || (v51 = ((char *)v48 - L"Defer reason: system needed") >> 1, v51 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v49);
        *(_QWORD *)v108 = L"Defer reason: system needed";
        v109 = (volatile signed __int32 *)v51;
        v47(v50, v108, 1);
        v52 = v117;
        if ( v117 )
        {
          if ( !_InterlockedDecrement(v117 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
            if ( !_InterlockedDecrement(v52 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
          }
        }
      }
      if ( (v9 & 0x12) != 0 )
      {
        v116 = 0;
        Windows::DockedHelpers::GetDockedUsage(&v116);
        v119 = 0;
        bstrString = 0;
        v53 = *(_QWORD *)v116;
        bstrString = 0;
        v119 = 0;
        v54 = (*(__int64 (__fastcall **)(char *, BSTR *, BSTR *))(v53 + 56))(v116, &v119, &bstrString);
        if ( v54 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1E8,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
            (const char *)(unsigned int)v54,
            v108[0]);
        v55 = Windows::Strings::to_wstring(pszPath, &v119);
        if ( &v123 != (__int128 *)v55 )
        {
          std::wstring::~wstring(&v123);
          v123 = *(_OWORD *)v55;
          v124 = *(_OWORD *)(v55 + 16);
          *(_QWORD *)(v55 + 16) = 0;
          *(_QWORD *)(v55 + 24) = 7;
          *(_WORD *)v55 = 0;
        }
        std::wstring::~wstring(pszPath);
        v56 = Windows::Strings::to_wstring(pszPath, &bstrString);
        if ( &v125 != (__int128 *)v56 )
        {
          std::wstring::~wstring(&v125);
          v125 = *(_OWORD *)v56;
          v126 = *(_OWORD *)(v56 + 16);
          *(_QWORD *)(v56 + 16) = 0;
          *(_QWORD *)(v56 + 24) = 7;
          *(_WORD *)v56 = 0;
        }
        std::wstring::~wstring(pszPath);
        if ( (v9 & 0x10) != 0 && !(_QWORD)v124 )
        {
          v57 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                                v10,
                                                                                pszPath)
                                                               + 256LL);
          v58 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                             L"Defer reason: ignoring system needed",
                             word_1404708DA,
                             0);
          if ( v58 == word_1404708DA
            || (v61 = ((char *)v58 - (char *)L"Defer reason: ignoring system needed") >> 1, v61 == -1) )
          {
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v59);
          }
          *(_QWORD *)v108 = L"Defer reason: ignoring system needed";
          v109 = (volatile signed __int32 *)v61;
          v57(v60, v108, 1);
          v62 = (volatile signed __int32 *)pszPath[1];
          if ( pszPath[1] )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
              if ( !_InterlockedDecrement(v62 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
            }
          }
          v9 &= ~0x10u;
        }
        if ( (v9 & 2) != 0 && !(_QWORD)v126 )
        {
          v63 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                                v10,
                                                                                pszPath)
                                                               + 256LL);
          v64 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: ignoring display needed",
                         &dword_14047092C,
                         0);
          if ( v64 == &dword_14047092C
            || (v67 = ((char *)v64 - (char *)L"Defer reason: ignoring display needed") >> 1, v67 == -1) )
          {
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v65);
          }
          *(_QWORD *)v108 = L"Defer reason: ignoring display needed";
          v109 = (volatile signed __int32 *)v67;
          v63(v66, v108, 1);
          v68 = (volatile signed __int32 *)pszPath[1];
          if ( pszPath[1] )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
              if ( !_InterlockedDecrement(v68 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
            }
          }
          v9 &= ~2u;
        }
        if ( bstrString )
          SysFreeString(bstrString);
        if ( v119 )
          SysFreeString(v119);
        if ( v116 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v116 + 16LL))(v116);
      }
    }
    if ( (a3 & 0x80) == 0 || (a3 & 0x100) == 0 )
    {
      UserDisplayState = Windows::Usage::GetUserDisplayState();
      v70 = UserDisplayState;
      if ( (a3 & 0x80) == 0 && UserDisplayState == 1 )
      {
        v9 |= 0x80u;
        v71 = *(void (__fastcall **)(__int64, int *, _QWORD))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                             v10,
                                                                             pszPath)
                                                            + 256LL);
        v72 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                           L"Defer reason: presenting",
                           word_14047084A,
                           0);
        if ( v72 == word_14047084A || (v75 = ((char *)v72 - (char *)L"Defer reason: presenting") >> 1, v75 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v73);
        *(_QWORD *)v108 = L"Defer reason: presenting";
        v109 = (volatile signed __int32 *)v75;
        v71(v74, v108, v70);
        v76 = (volatile signed __int32 *)pszPath[1];
        if ( pszPath[1] )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
            if ( !_InterlockedDecrement(v76 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
          }
        }
      }
      if ( (a3 & 0x100) == 0 && v70 - 2 <= 1 )
      {
        v9 |= 0x100u;
        v77 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                              v10,
                                                                              pszPath)
                                                             + 256LL);
        v78 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                       L"Defer reason: full-screen",
                       &dword_140470884,
                       0);
        if ( v78 == &dword_140470884 || (v81 = ((char *)v78 - (char *)L"Defer reason: full-screen") >> 1, v81 == -1) )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xC9,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
            v79);
        *(_QWORD *)v108 = L"Defer reason: full-screen";
        v109 = (volatile signed __int32 *)v81;
        v77(v80, v108, 1);
        v82 = (volatile signed __int32 *)pszPath[1];
        if ( pszPath[1] )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
            if ( !_InterlockedDecrement(v82 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
          }
        }
      }
    }
    if ( (a3 & 8) == 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1) )
    {
      v9 |= 8u;
      v83 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                            v10,
                                                                            pszPath)
                                                           + 256LL);
      v84 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: phone call",
                         word_1404707D2,
                         0);
      if ( v84 == word_1404707D2 || (v87 = ((char *)v84 - (char *)L"Defer reason: phone call") >> 1, v87 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v85);
      *(_QWORD *)v108 = L"Defer reason: phone call";
      v109 = (volatile signed __int32 *)v87;
      v83(v86, v108, 1);
      v88 = (volatile signed __int32 *)pszPath[1];
      if ( pszPath[1] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v88)(v88);
          if ( !_InterlockedDecrement(v88 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v88 + 8LL))(v88);
        }
      }
    }
    if ( (a3 & 0x200) == 0 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 56LL))(a1) )
    {
      v9 |= 0x200u;
      v89 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                            v10,
                                                                            pszPath)
                                                           + 256LL);
      v90 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                     L"Defer reason: block requested",
                     &dword_140470814,
                     0);
      if ( v90 == &dword_140470814 || (v93 = ((char *)v90 - L"Defer reason: block requested") >> 1, v93 == -1) )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v91);
      *(_QWORD *)v108 = L"Defer reason: block requested";
      v109 = (volatile signed __int32 *)v93;
      v89(v92, v108, 1);
      v94 = (volatile signed __int32 *)pszPath[1];
      if ( pszPath[1] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)pszPath[1] + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v94)(v94);
          if ( !_InterlockedDecrement(v94 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v94 + 8LL))(v94);
        }
      }
    }
    if ( (a3 & 0x400) == 0 )
    {
      LODWORD(v119) = 0;
      v110[0] = 0;
      v95 = wil::wnf_query_nothrow<unsigned long>(&WNF_RM_GAME_MODE_ACTIVE, v110, &v119, 0);
      if ( v95 >= 0 )
      {
        if ( (_DWORD)v119 )
        {
          v9 |= 0x400u;
          v98 = *(void (__fastcall **)(__int64, int *, __int64))(**(_QWORD **)(*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v10 + 104LL))(
                                                                                v10,
                                                                                pszPath)
                                                               + 256LL);
          v99 = (int *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                         L"Defer reason: game active",
                         &dword_14047079C,
                         0);
          if ( v99 == &dword_14047079C || (v102 = ((char *)v99 - (char *)L"Defer reason: game active") >> 1, v102 == -1) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v100);
          *(_QWORD *)v108 = L"Defer reason: game active";
          v109 = (volatile signed __int32 *)v102;
          v98(v101, v108, 1);
          std::shared_ptr<Windows::RebootDowntime::InputBuilder>::~shared_ptr<Windows::RebootDowntime::InputBuilder>(pszPath);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl'::`2'::impl) )
          {
            *(_OWORD *)pszPath = 0;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            LOWORD(pszPath[0]) = 0;
            v105 = (char *)OpenProcess(0x400u, 0, (DWORD)v119);
            *(_QWORD *)v108 = v105;
            if ( (unsigned __int64)(v105 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            {
              LODWORD(bstrString) = 0;
              v116 = v105;
              v115[0] = ___7____func_V_lambda_1___1____QueryFullProcessImageNameW_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___0BAA__wil__YAJPEAXKAEAV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___Z___A6AJPEA_W_KPEA_K_Z___function_wistd__6B_;
              v115[1] = &v116;
              v115[2] = &bstrString;
              v115[13] = v115;
              if ( (int)wil::AdaptFixedSizeToAllocatedResult<std::wstring,256>(pszPath, v114) >= 0 )
              {
                v106 = (const WCHAR *)pszPath;
                if ( si128.m128i_i64[1] > 7uLL )
                  v106 = pszPath[0];
                FileNameW = PathFindFileNameW(v106);
                std::wstring::operator=(&v130, FileNameW);
              }
            }
            if ( (unsigned __int64)(v105 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v105);
            std::wstring::~wstring(pszPath);
          }
          else
          {
            v103 = (char *)OpenProcess(0x400u, 0, (DWORD)v119);
            v116 = v103;
            memset(ExeName, 0, 0x208u);
            LODWORD(bstrString) = 260;
            if ( (unsigned __int64)(v103 - 1) <= 0xFFFFFFFFFFFFFFFDuLL
              && QueryFullProcessImageNameW(v103, 0, ExeName, (PDWORD)&bstrString) )
            {
              v104 = PathFindFileNameW(ExeName);
              std::wstring::operator=(&v130, v104);
            }
            if ( (unsigned __int64)(v103 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
              CloseHandle(v103);
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x220,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Usage.cpp",
          (const char *)(unsigned int)v95,
          v108[0]);
      }
    }
    LODWORD(v122) = v9;
    v96 = v113;
    SystemInterface::DeferReasons::DeferReasons(v113, &v122);
    v97 = (volatile signed __int32 *)*((_QWORD *)&v112 + 1);
    if ( *((_QWORD *)&v112 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v112 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v97)(v97);
        if ( _InterlockedExchangeAdd(v97 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v97 + 8LL))(v97);
      }
    }
    std::wstring::~wstring(&v130);
    std::wstring::~wstring(&v127);
    std::wstring::~wstring(&v125);
    std::wstring::~wstring(&v123);
    return v96;
  }
}

```

## disassembly

```asm
0x140244160  mov     [rsp-8+arg_18], rbx
0x140244165  push    rbp
0x140244166  push    rsi
0x140244167  push    rdi
0x140244168  push    r12
0x14024416a  push    r13
0x14024416c  push    r14
0x14024416e  push    r15
0x140244170  lea     rbp, [rsp-2C0h]
0x140244178  sub     rsp, 3C0h
0x14024417f  mov     rax, cs:__security_cookie
0x140244186  xor     rax, rsp
0x140244189  mov     [rbp+2F0h+var_40], rax
0x140244190  mov     ebx, r8d
0x140244193  mov     r12, rdx
0x140244196  mov     [rsp+3F0h+var_3A8], rdx
0x14024419b  mov     r13, rcx
0x14024419e  mov     [rbp+2F0h+var_328], rdx
0x1402441a2  xor     ecx, ecx
0x1402441a4  mov     r15d, ecx
0x1402441a7  mov     [rsp+3F0h+var_3BC], ecx
0x1402441ab  mov     [rbp+2F0h+var_2E0], rcx
0x1402441af  xorps   xmm0, xmm0
0x1402441b2  movups  [rbp+2F0h+var_2D8], xmm0
0x1402441b6  mov     qword ptr [rbp+2F0h+var_2C8], rcx
0x1402441ba  lea     eax, [rcx+7]
0x1402441bd  mov     qword ptr [rbp+2F0h+var_2C8+8], rax
0x1402441c1  mov     word ptr [rbp+2F0h+var_2D8], cx
0x1402441c5  movups  [rbp+2F0h+var_2B8], xmm0
0x1402441c9  mov     qword ptr [rbp+2F0h+var_2A8], rcx
0x1402441cd  mov     qword ptr [rbp+2F0h+var_2A8+8], rax
0x1402441d1  mov     word ptr [rbp+2F0h+var_2B8], cx
0x1402441d5  movups  [rbp+2F0h+var_298], xmm0
0x1402441d9  mov     [rbp+2F0h+var_288], rcx
0x1402441dd  mov     [rbp+2F0h+var_280], rax
0x1402441e1  mov     word ptr [rbp+2F0h+var_298], cx
0x1402441e5  movups  [rbp+2F0h+var_278], xmm0
0x1402441e9  mov     [rbp+2F0h+var_268], rcx
0x1402441f0  mov     [rbp+2F0h+var_260], rax
0x1402441f7  mov     word ptr [rbp+2F0h+var_278], cx
0x1402441fb  mov     edi, ecx
0x1402441fd  movups  [rsp+3F0h+var_3B8], xmm0
0x140244202  lea     rcx, [rsp+3F0h+var_3B8]
0x140244207  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x14024420c  nop
0x14024420d  mov     r14, qword ptr [rsp+3F0h+var_3B8]
0x140244212  mov     rax, [r14]
0x140244215  lea     rdx, [rsp+3F0h+var_3D0]
0x14024421a  mov     rcx, r14
0x14024421d  mov     rax, [rax+30h]
0x140244221  call    _guard_dispatch_icall
0x140244226  nop
0x140244227  mov     rcx, [rax]
0x14024422a  mov     rax, [rcx]
0x14024422d  lea     rdx, [rbp+2F0h+bstrString]
0x140244231  mov     rax, [rax+50h]
0x140244235  call    _guard_dispatch_icall
0x14024423a  nop
0x14024423b  mov     rsi, [rsp+3F0h+var_3C8]
0x140244240  test    rsi, rsi
0x140244243  jz      short loc_14024427C
0x140244245  or      eax, 0FFFFFFFFh
0x140244248  lock xadd [rsi+8], eax
0x14024424d  cmp     eax, 1
0x140244250  jnz     short loc_14024427C
0x140244252  mov     rax, [rsi]
0x140244255  mov     rcx, rsi
0x140244258  mov     rax, [rax]
0x14024425b  call    _guard_dispatch_icall
0x140244260  or      eax, 0FFFFFFFFh
0x140244263  lock xadd [rsi+0Ch], eax
0x140244268  cmp     eax, 1
0x14024426b  jnz     short loc_14024427C
0x14024426d  mov     rax, [rsi]
0x140244270  mov     rcx, rsi
0x140244273  mov     rax, [rax+8]
0x140244277  call    _guard_dispatch_icall
0x14024427c  mov     cl, byte ptr [rbp+2F0h+bstrString+4]
0x14024427f  test    cl, cl
0x140244281  jz      loc_140244378
0x140244287  mov     rax, [rbp+2F0h+bstrString]
0x14024428b  bt      eax, 0Ah
0x14024428f  jnb     short loc_1402442A8
0x140244291  lea     rdx, aTestoverrideGa; "TestOverride_gameModeReason"
0x140244298  lea     rcx, [rbp+2F0h+var_278]; void *
0x14024429c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x1402442a1  mov     rax, [rbp+2F0h+bstrString]
0x1402442a5  mov     cl, byte ptr [rbp+2F0h+bstrString+4]
0x1402442a8  test    cl, cl
0x1402442aa  jz      loc_14024523E
0x1402442b0  test    al, 2
0x1402442b2  jz      short loc_1402442CB
0x1402442b4  lea     rdx, aTestoverrideDi; "TestOverride_displayReason"
0x1402442bb  lea     rcx, [rbp+2F0h+var_2B8]; void *
0x1402442bf  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x1402442c4  mov     rax, [rbp+2F0h+bstrString]
0x1402442c8  mov     cl, byte ptr [rbp+2F0h+bstrString+4]
0x1402442cb  test    cl, cl
0x1402442cd  jz      loc_14024523E
0x1402442d3  test    al, 10h
0x1402442d5  jz      short loc_1402442EE
0x1402442d7  lea     rdx, aTestoverrideSy; "TestOverride_systemReason"
0x1402442de  lea     rcx, [rbp+2F0h+var_2D8]; void *
0x1402442e2  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@QEB_W@Z; std::wstring::operator=(wchar_t const * const)
0x1402442e7  mov     rax, [rbp+2F0h+bstrString]
0x1402442eb  mov     cl, byte ptr [rbp+2F0h+bstrString+4]
0x1402442ee  test    cl, cl
0x1402442f0  jz      loc_14024523E
0x1402442f6  not     ebx
0x1402442f8  and     ebx, eax
0x1402442fa  mov     dword ptr [rbp+2F0h+var_2E0], ebx
0x1402442fd  lea     rdx, [rbp+2F0h+var_2E0]
0x140244301  mov     rcx, r12
0x140244304  call    ??0DeferReasons@SystemInterface@@QEAA@$$QEAU01@@Z; SystemInterface::DeferReasons::DeferReasons(SystemInterface::DeferReasons &&)
0x140244309  nop
0x14024430a  mov     rbx, qword ptr [rsp+3F0h+var_3B8+8]
0x14024430f  test    rbx, rbx
0x140244312  jz      short loc_14024434C
0x140244314  or      eax, 0FFFFFFFFh
0x140244317  lock xadd [rbx+8], eax
0x14024431c  cmp     eax, 1
0x14024431f  jnz     short loc_14024434C
0x140244321  mov     rax, [rbx]
0x140244324  mov     rcx, rbx
0x140244327  mov     rax, [rax]
0x14024432a  call    _guard_dispatch_icall
0x14024432f  or      eax, 0FFFFFFFFh
0x140244332  lock xadd [rbx+0Ch], eax
0x140244337  cmp     eax, 1
0x14024433a  jnz     short loc_14024434C
0x14024433c  mov     rax, [rbx]
0x14024433f  mov     rcx, rbx
0x140244342  mov     rax, [rax+8]
0x140244346  call    _guard_dispatch_icall
0x14024434b  nop
0x14024434c  lea     rcx, [rbp+2F0h+var_278]
0x140244350  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140244355  lea     rcx, [rbp+2F0h+var_298]
0x140244359  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024435e  lea     rcx, [rbp+2F0h+var_2B8]
0x140244362  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140244367  lea     rcx, [rbp+2F0h+var_2D8]
0x14024436b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140244370  mov     rax, r12
0x140244373  jmp     loc_140244FFD
0x140244378  test    bl, 4
0x14024437b  jnz     short loc_1402443B9
0x14024437d  mov     rax, [r14]
0x140244380  lea     rdx, [rsp+3F0h+var_3D0]
0x140244385  mov     rcx, r14
0x140244388  mov     rax, [rax+38h]
0x14024438c  call    _guard_dispatch_icall
0x140244391  nop
0x140244392  mov     r15d, 2
0x140244398  mov     [rsp+3F0h+var_3BC], r15d
0x14024439d  mov     rcx, [rax]
0x1402443a0  mov     rax, [rcx]
0x1402443a3  mov     rax, [rax+10h]
0x1402443a7  call    _guard_dispatch_icall
0x1402443ac  cmp     al, [rbp+2F0h+arg_20]
0x1402443b2  jnb     short loc_1402443B9
0x1402443b4  mov     r12b, 1
0x1402443b7  jmp     short loc_1402443BE
0x1402443b9  xor     ecx, ecx
0x1402443bb  mov     r12b, cl
0x1402443be  test    r15b, 2
0x1402443c2  jz      short loc_140244409
0x1402443c4  and     r15d, 0FFFFFFFDh
0x1402443c8  mov     rsi, [rsp+3F0h+var_3C8]
0x1402443cd  test    rsi, rsi
0x1402443d0  jz      short loc_140244409
0x1402443d2  or      eax, 0FFFFFFFFh
0x1402443d5  lock xadd [rsi+8], eax
0x1402443da  cmp     eax, 1
0x1402443dd  jnz     short loc_140244409
0x1402443df  mov     rax, [rsi]
0x1402443e2  mov     rcx, rsi
0x1402443e5  mov     rax, [rax]
0x1402443e8  call    _guard_dispatch_icall
0x1402443ed  or      eax, 0FFFFFFFFh
0x1402443f0  lock xadd [rsi+0Ch], eax
0x1402443f5  cmp     eax, 1
0x1402443f8  jnz     short loc_140244409
0x1402443fa  mov     rax, [rsi]
0x1402443fd  mov     rcx, rsi
0x140244400  mov     rax, [rax+8]
0x140244404  call    _guard_dispatch_icall
0x140244409  test    r12b, r12b
0x14024440c  jz      loc_1402444D5
0x140244412  mov     edi, 4
0x140244417  mov     rax, [r14]
0x14024441a  lea     rdx, [rbp+2F0h+var_328]
0x14024441e  mov     rcx, r14
0x140244421  mov     rax, [rax+68h]
0x140244425  call    _guard_dispatch_icall
0x14024442a  nop
0x14024442b  mov     r11, [rax]
0x14024442e  mov     rax, [r11]
0x140244431  mov     rsi, [rax+100h]
0x140244438  xor     r8d, r8d
0x14024443b  lea     r12, dword_1404706F4
0x140244442  mov     rdx, r12
0x140244445  lea     rcx, aDeferReasonLow; "Defer reason: low battery"
0x14024444c  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140244451  cmp     rax, r12
0x140244454  jz      loc_140245244
0x14024445a  lea     rcx, aDeferReasonLow; "Defer reason: low battery"
0x140244461  sub     rax, rcx
0x140244464  sar     rax, 1
0x140244467  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14024446b  jz      loc_140245244
0x140244471  mov     qword ptr [rsp+3F0h+var_3D0], rcx
0x140244476  mov     [rsp+3F0h+var_3C8], rax
0x14024447b  lea     r8d, [rdi-3]
0x14024447f  lea     rdx, [rsp+3F0h+var_3D0]
0x140244484  mov     rcx, r11
0x140244487  mov     rax, rsi
0x14024448a  call    _guard_dispatch_icall
0x14024448f  nop
0x140244490  mov     rsi, [rbp+2F0h+var_320]
0x140244494  xor     r12d, r12d
0x140244497  test    rsi, rsi
0x14024449a  jz      short loc_1402444D8
0x14024449c  or      eax, 0FFFFFFFFh
0x14024449f  lock xadd [rsi+8], eax
0x1402444a4  cmp     eax, 1
0x1402444a7  jnz     short loc_1402444D8
0x1402444a9  mov     rax, [rsi]
0x1402444ac  mov     rcx, rsi
0x1402444af  mov     rax, [rax]
0x1402444b2  call    _guard_dispatch_icall
0x1402444b7  or      eax, 0FFFFFFFFh
0x1402444ba  lock xadd [rsi+0Ch], eax
0x1402444bf  cmp     eax, 1
0x1402444c2  jnz     short loc_1402444D8
0x1402444c4  mov     rax, [rsi]
0x1402444c7  mov     rcx, rsi
0x1402444ca  mov     rax, [rax+8]
0x1402444ce  call    _guard_dispatch_icall
0x1402444d3  jmp     short loc_1402444D8
0x1402444d5  xor     r12d, r12d
0x1402444d8  test    bl, 40h
0x1402444db  jnz     short loc_140244511
0x1402444dd  mov     rax, [r14]
0x1402444e0  lea     rdx, [rsp+3F0h+var_3D0]
0x1402444e5  mov     rcx, r14
0x1402444e8  mov     rax, [rax+38h]
0x1402444ec  call    _guard_dispatch_icall
0x1402444f1  nop
0x1402444f2  or      r15d, 4
0x1402444f6  mov     [rsp+3F0h+var_3BC], r15d
0x1402444fb  mov     rcx, [rax]
0x1402444fe  mov     rax, [rcx]
0x140244501  mov     rax, [rax+28h]
0x140244505  call    _guard_dispatch_icall
0x14024450a  test    al, al
0x14024450c  jnz     short loc_140244511
0x14024450e  mov     r12b, 1
0x140244511  test    r15b, 4
0x140244515  jz      short loc_14024455D
0x140244517  mov     rsi, [rsp+3F0h+var_3C8]
0x14024451c  xor     r15d, r15d
0x14024451f  test    rsi, rsi
0x140244522  jz      short loc_140244560
0x140244524  or      eax, 0FFFFFFFFh
0x140244527  lock xadd [rsi+8], eax
0x14024452c  cmp     eax, 1
0x14024452f  jnz     short loc_140244560
0x140244531  mov     rax, [rsi]
0x140244534  mov     rcx, rsi
0x140244537  mov     rax, [rax]
0x14024453a  call    _guard_dispatch_icall
0x14024453f  or      eax, 0FFFFFFFFh
0x140244542  lock xadd [rsi+0Ch], eax
0x140244547  cmp     eax, 1
0x14024454a  jnz     short loc_140244560
0x14024454c  mov     rax, [rsi]
0x14024454f  mov     rcx, rsi
0x140244552  mov     rax, [rax+8]
0x140244556  call    _guard_dispatch_icall
0x14024455b  jmp     short loc_140244560
0x14024455d  xor     r15d, r15d
0x140244560  test    r12b, r12b
0x140244563  jz      loc_140244631
0x140244569  or      edi, 40h
0x14024456c  mov     rax, [r14]
0x14024456f  lea     rdx, [rbp+2F0h+var_328]
0x140244573  mov     rcx, r14
0x140244576  mov     rax, [rax+68h]
0x14024457a  call    _guard_dispatch_icall
0x14024457f  nop
0x140244580  mov     r11, [rax]
0x140244583  mov     rax, [r11]
0x140244586  mov     rsi, [rax+100h]
0x14024458d  xor     r8d, r8d
0x140244590  lea     r15, aDeferReasonUse; "Defer reason: user active"
0x140244597  mov     rdx, r15
0x14024459a  lea     r12, aDeferReasonNot; "Defer reason: not on AC"
0x1402445a1  mov     rcx, r12
0x1402445a4  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
  ... truncated ...
```
