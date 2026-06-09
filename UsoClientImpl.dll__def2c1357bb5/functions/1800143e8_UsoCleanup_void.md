# UsoCleanup(void)

- ea: `0x1800143e8`
- end: `0x180014dd3`
- name: `?UsoCleanup@@YAJXZ`
- size: `2539`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180007804`
- `0x180009380`
- `0x18000c9e0`
- `0x1800143e8`
- `0x180018cd0`
- `0x180019208`
- `0x18001aae4`
- `0x18002f2f0`
- `0x18002f454`
- `0x18002f478`
- `0x1800338a4`
- `0x1800344b8`
- `0x180056500`
- `0x180056568`
- `0x18005c5e0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001492d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800149a3`
- `OLEAUT32!__imp_SysAllocString` at `0x180014a19`
- `OLEAUT32!__imp_SysAllocString` at `0x180014a8f`
- `OLEAUT32!__imp_SysAllocString` at `0x180014b05`
- `OLEAUT32!__imp_SysAllocString` at `0x180014b7b`
- `OLEAUT32!__imp_SysAllocString` at `0x18001492d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800149a3`
- `OLEAUT32!__imp_SysAllocString` at `0x180014a19`
- `OLEAUT32!__imp_SysAllocString` at `0x180014a8f`
- `OLEAUT32!__imp_SysAllocString` at `0x180014b05`
- `OLEAUT32!__imp_SysAllocString` at `0x180014b7b`
- `OLEAUT32!__imp_SysFreeString` at `0x180014995`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180014af7`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014be0`
- `OLEAUT32!__imp_SysFreeString` at `0x180014995`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a0b`
- `OLEAUT32!__imp_SysFreeString` at `0x180014a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180014af7`
- `OLEAUT32!__imp_SysFreeString` at `0x180014b6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014be0`

## string_xrefs

- `0x180014d67`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180014d79`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180014d8b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180014d9d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180014daf`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180014dc1`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1800145c6`: `ServiceIsLoggingForWorker`
- `0x180014794`: `SmartSchedulerValidationTask`
- `0x1800148af`: `\Microsoft\Windows\UpdateOrchestrator`
- `0x180014926`: `Maintenance Install`
- `0x180014a12`: `Policy Install`
- `0x180014a88`: `AC Power Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 UsoCleanup(void)
{
  int v0; // edi
  BSTR v1; // r14
  BSTR v2; // rsi
  unsigned __int128 v3; // kr10_16
  __m128i si128; // xmm6
  __int64 v5; // r8
  OLECHAR *v6; // rcx
  __int64 v7; // rax
  const char *v8; // r9
  BSTR v9; // rsi
  BSTR v10; // r14
  __int64 v11; // r10
  OLECHAR *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rcx
  const char *v15; // r9
  __int64 bstr; // rax
  int TaskSchedulerFolder; // eax
  unsigned int v18; // esi
  OLECHAR *v19; // rax
  const char *v20; // r9
  int v21; // edi
  OLECHAR *v22; // rcx
  unsigned int v23; // edi
  OLECHAR *v24; // rax
  const char *v25; // r9
  int v26; // edi
  OLECHAR *v27; // rcx
  unsigned int v28; // edi
  OLECHAR *v29; // rax
  const char *v30; // r9
  int v31; // edi
  OLECHAR *v32; // rcx
  unsigned int v33; // edi
  OLECHAR *v34; // rax
  const char *v35; // r9
  int v36; // edi
  OLECHAR *v37; // rcx
  unsigned int v38; // edi
  OLECHAR *v39; // rax
  const char *v40; // r9
  int v41; // edi
  OLECHAR *v42; // rcx
  unsigned int v43; // edi
  OLECHAR *v44; // rax
  const char *v45; // r9
  OLECHAR *v46; // rcx
  _QWORD *i; // rdi
  _QWORD *v48; // r14
  __int64 v49; // rax
  int v50; // eax
  BSTR bstrString[2]; // [rsp+20h] [rbp-278h] BYREF
  BSTR v53; // [rsp+30h] [rbp-268h] BYREF
  __int64 *v54; // [rsp+38h] [rbp-260h]
  BSTR v55[2]; // [rsp+40h] [rbp-258h] BYREF
  BSTR v56; // [rsp+50h] [rbp-248h] BYREF
  __int64 v57; // [rsp+58h] [rbp-240h]
  BSTR v58; // [rsp+60h] [rbp-238h] BYREF
  __int64 v59; // [rsp+68h] [rbp-230h]
  BSTR v60; // [rsp+70h] [rbp-228h] BYREF
  __int64 v61; // [rsp+78h] [rbp-220h]
  _OWORD v62[2]; // [rsp+80h] [rbp-218h] BYREF
  _OWORD v63[2]; // [rsp+A0h] [rbp-1F8h] BYREF
  _OWORD v64[2]; // [rsp+C0h] [rbp-1D8h] BYREF
  _OWORD v65[2]; // [rsp+E0h] [rbp-1B8h] BYREF
  _OWORD v66[2]; // [rsp+100h] [rbp-198h] BYREF
  _OWORD v67[2]; // [rsp+120h] [rbp-178h] BYREF
  _OWORD v68[2]; // [rsp+140h] [rbp-158h] BYREF
  _OWORD v69[2]; // [rsp+160h] [rbp-138h] BYREF
  _OWORD v70[2]; // [rsp+180h] [rbp-118h] BYREF
  _OWORD v71[2]; // [rsp+1A0h] [rbp-F8h] BYREF
  _OWORD v72[2]; // [rsp+1C0h] [rbp-D8h] BYREF
  _OWORD v73[2]; // [rsp+1E0h] [rbp-B8h] BYREF
  _OWORD v74[2]; // [rsp+200h] [rbp-98h] BYREF
  __int64 v75; // [rsp+220h] [rbp-78h] BYREF
  __int128 v76; // [rsp+228h] [rbp-70h] BYREF
  __int64 v77; // [rsp+238h] [rbp-60h]
  __int64 *v78; // [rsp+240h] [rbp-58h] BYREF
  int v79[4]; // [rsp+248h] [rbp-50h] BYREF
  __int64 v80; // [rsp+258h] [rbp-40h]
  unsigned __int128 v81; // [rsp+260h] [rbp-38h] BYREF
  __int64 v82; // [rsp+270h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v0 = 0;
  LODWORD(v75) = 0;
  v81 = 0;
  v82 = 0;
  memset(v66, 0, sizeof(v66));
  std::wstring::_Construct<1,wchar_t const *>(v66);
  memset(v67, 0, sizeof(v67));
  std::wstring::_Construct<1,wchar_t const *>(v67);
  memset(v68, 0, sizeof(v68));
  std::wstring::_Construct<1,wchar_t const *>(v68);
  memset(v69, 0, sizeof(v69));
  std::wstring::_Construct<1,wchar_t const *>(v69);
  memset(v70, 0, sizeof(v70));
  std::wstring::_Construct<1,wchar_t const *>(v70);
  memset(v71, 0, sizeof(v71));
  std::wstring::_Construct<1,wchar_t const *>(v71);
  memset(v72, 0, sizeof(v72));
  std::wstring::_Construct<1,wchar_t const *>(v72);
  memset(v73, 0, sizeof(v73));
  std::wstring::_Construct<1,wchar_t const *>(v73);
  memset(v74, 0, sizeof(v74));
  std::wstring::_Construct<1,wchar_t const *>(v74);
  v53 = (BSTR)v66;
  v54 = &v75;
  std::vector<std::wstring>::vector<std::wstring>(&v81, &v53);
  `eh vector destructor iterator'(v66, 0x20u, 9u, std::wstring::~wstring);
  v1 = (BSTR)*((_QWORD *)&v81 + 1);
  v3 = v81;
  v53 = (BSTR)(v3 >> 64);
  v2 = (BSTR)v3;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    bstrString[0] = v2;
    if ( v2 == v1 )
      break;
    v5 = *((_QWORD *)v2 + 2);
    v6 = v2;
    if ( *((_QWORD *)v2 + 3) > 7u )
      v6 = *(OLECHAR **)v2;
    v62[0] = 0;
    v62[1] = si128;
    LOWORD(v62[0]) = 0;
    v7 = -1;
    do
      ++v7;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v7] );
    try
    {
      v60 = v6;
      v61 = v5;
      v58 = (BSTR)v62;
      v59 = 0;
      v56 = (BSTR)SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v57 = v7;
      Windows::Registry::DeleteSystemValue(v55, &v56, &v58, &v60);
      std::wstring::~wstring(v62);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x4F7,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
        v8);
      v2 = bstrString[0];
      v1 = v53;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v0 = v75;
    }
    v2 += 16;
  }
  *(_OWORD *)v79 = 0;
  v80 = 0;
  memset(v63, 0, sizeof(v63));
  std::wstring::_Construct<1,wchar_t const *>(v63);
  memset(v64, 0, sizeof(v64));
  std::wstring::_Construct<1,wchar_t const *>(v64);
  memset(v65, 0, sizeof(v65));
  std::wstring::_Construct<1,wchar_t const *>(v65);
  v53 = (BSTR)v63;
  v54 = (__int64 *)v66;
  std::vector<std::wstring>::vector<std::wstring>(v79, &v53);
  `eh vector destructor iterator'(v63, 0x20u, 3u, std::wstring::~wstring);
  v9 = *(BSTR *)v79;
  v10 = *(BSTR *)&v79[2];
  v53 = *(BSTR *)&v79[2];
  while ( 1 )
  {
    bstrString[0] = v9;
    if ( v9 == v10 )
      break;
    v11 = *((_QWORD *)v9 + 2);
    v12 = v9;
    if ( *((_QWORD *)v9 + 3) > 7u )
      v12 = *(OLECHAR **)v9;
    v13 = -1;
    do
      ++v13;
    while ( SystemInterface::Registry::USO_SCHEDULER_ROOT[v13] );
    v14 = -1;
    do
      ++v14;
    while ( SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID[v14] );
    try
    {
      v60 = v12;
      v61 = v11;
      v58 = (BSTR)SystemInterface::Registry::USO_SCHEDULER_ROOT;
      v59 = v13;
      v56 = (BSTR)SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID;
      v57 = v14;
      Windows::Registry::DeleteSystemValue(v55, &v56, &v58, &v60);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x507,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
        v15);
      v9 = bstrString[0];
      v10 = v53;
      v0 = v75;
    }
    v9 += 16;
  }
  v78 = 0;
  bstr = wil::make_bstr(&v53, L"\\Microsoft\\Windows\\UpdateOrchestrator");
  TaskSchedulerFolder = GetTaskSchedulerFolder(bstr, &v78);
  v18 = TaskSchedulerFolder;
  if ( TaskSchedulerFolder >= 0 )
  {
    v76 = 0;
    v77 = 0;
    v19 = SysAllocString(L"Maintenance Install");
    bstrString[0] = v19;
    v21 = v0 | 0x10;
    LODWORD(v75) = v21;
    if ( !v19 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v20);
    if ( *((_QWORD *)&v76 + 1) == v77 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v76,
        *((_QWORD *)&v76 + 1),
        bstrString);
      v22 = bstrString[0];
    }
    else
    {
      **((_QWORD **)&v76 + 1) = v19;
      v22 = 0;
      *((_QWORD *)&v76 + 1) += 8LL;
    }
    v23 = v21 & 0xFFFFFFEF;
    if ( v22 )
      SysFreeString(v22);
    v24 = SysAllocString(L"Universal Orchestrator Start");
    v56 = v24;
    v26 = v23 | 0x20;
    LODWORD(v75) = v26;
    if ( !v24 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    if ( *((_QWORD *)&v76 + 1) == v77 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v76,
        *((_QWORD *)&v76 + 1),
        &v56);
      v27 = v56;
    }
    else
    {
      **((_QWORD **)&v76 + 1) = v24;
      v27 = 0;
      *((_QWORD *)&v76 + 1) += 8LL;
    }
    v28 = v26 & 0xFFFFFFDF;
    if ( v27 )
      SysFreeString(v27);
    v29 = SysAllocString(L"Policy Install");
    v58 = v29;
    v31 = v28 | 0x40;
    LODWORD(v75) = v31;
    if ( !v29 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v30);
    if ( *((_QWORD *)&v76 + 1) == v77 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v76,
        *((_QWORD *)&v76 + 1),
        &v58);
      v32 = v58;
    }
    else
    {
      **((_QWORD **)&v76 + 1) = v29;
      v32 = 0;
      *((_QWORD *)&v76 + 1) += 8LL;
    }
    v33 = v31 & 0xFFFFFFBF;
    if ( v32 )
      SysFreeString(v32);
    v34 = SysAllocString(L"AC Power Install");
    v60 = v34;
    v36 = v33 | 2;
    LODWORD(v75) = v36;
    if ( !v34 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v35);
    if ( *((_QWORD *)&v76 + 1) == v77 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v76,
        *((_QWORD *)&v76 + 1),
        &v60);
      v37 = v60;
    }
    else
    {
      **((_QWORD **)&v76 + 1) = v34;
      v37 = 0;
      *((_QWORD *)&v76 + 1) += 8LL;
    }
    v38 = v36 & 0xFFFFFFFD;
    if ( v37 )
      SysFreeString(v37);
    v39 = SysAllocString(L"AC Power Download");
    v55[0] = v39;
    v41 = v38 | 4;
    LODWORD(v75) = v41;
    if ( !v39 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v40);
    if ( *((_QWORD *)&v76 + 1) == v77 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v76,
        *((_QWORD *)&v76 + 1),
        v55);
      v42 = v55[0];
    }
    else
    {
      **((_QWORD **)&v76 + 1) = v39;
      v42 = 0;
      *((_QWORD *)&v76 + 1) += 8LL;
    }
    v43 = v41 & 0xFFFFFFFB;
    if ( v42 )
      SysFreeString(v42);
    v44 = SysAllocString(L"Backup Scan");
    v53 = v44;
    LODWORD(v75) = v43 | 8;
    if ( !v44 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v45);
    if ( *((_QWORD *)&v76 + 1) == v77 )
    {
      std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        &v76,
        *((_QWORD *)&v76 + 1),
        &v53);
      v46 = v53;
    }
    else
    {
      **((_QWORD **)&v76 + 1) = v44;
      v46 = 0;
      *((_QWORD *)&v76 + 1) += 8LL;
    }
    if ( v46 )
      SysFreeString(v46);
    v48 = (_QWORD *)*((_QWORD *)&v76 + 1);
    for ( i = (_QWORD *)v76; ; ++i )
    {
      if ( i == v48 )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v76);
        if ( v78 )
          (*(void (__fastcall **)(__int64 *))(*v78 + 16))(v78);
        std::vector<std::wstring>::_Tidy(v79);
        std::vector<std::wstring>::_Tidy(&v81);
        return 0;
      }
      v75 = 0;
      v49 = *v78;
      v75 = 0;
      if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64 *))(v49 + 104))(v78, *i, &v75) >= 0 )
      {
        v50 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD))(*v78 + 120))(v78, *i, 0);
        v18 = v50;
        if ( v50 < 0 )
          break;
      }
      if ( v75 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)v50,
      (int)bstrString[0]);
    if ( v75 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
    std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(&v76);
    if ( v78 )
      (*(void (__fastcall **)(__int64 *))(*v78 + 16))(v78);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x50B,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)TaskSchedulerFolder,
      (int)bstrString[0]);
    if ( v78 )
      (*(void (__fastcall **)(__int64 *))(*v78 + 16))(v78);
  }
  std::vector<std::wstring>::_Tidy(v79);
  std::vector<std::wstring>::_Tidy(&v81);
  return v18;
}

```

## disassembly

```asm
0x1800143e8  mov     r11, rsp
0x1800143eb  mov     [r11+8], rbx
0x1800143ef  mov     [r11+10h], rsi
0x1800143f3  mov     [r11+18h], rdi
0x1800143f7  push    r14
0x1800143f9  sub     rsp, 290h
0x180014400  movaps  xmmword ptr [r11-18h], xmm6
0x180014405  mov     rax, cs:__security_cookie
0x18001440c  xor     rax, rsp
0x18001440f  mov     [rsp+298h+var_20], rax
0x180014417  xor     ebx, ebx
0x180014419  mov     edi, ebx
0x18001441b  mov     [r11-78h], ebx
0x18001441f  xorps   xmm0, xmm0
0x180014422  xor     eax, eax
0x180014424  movups  xmmword ptr [r11-38h], xmm0
0x180014429  mov     [r11-28h], rax
0x18001442d  movups  [rsp+298h+var_198], xmm0
0x180014435  xorps   xmm1, xmm1
0x180014438  movdqa  [rsp+298h+var_188], xmm1
0x180014441  lea     r8d, [rbx+7]
0x180014445  lea     rdx, aMostack; "MoStack"
0x18001444c  lea     rcx, [r11-198h]
0x180014453  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014458  nop
0x180014459  xorps   xmm0, xmm0
0x18001445c  movups  [rsp+298h+var_178], xmm0
0x180014464  xorps   xmm1, xmm1
0x180014467  movdqa  [rsp+298h+var_168], xmm1
0x180014470  lea     esi, [rbx+0Eh]
0x180014473  mov     r8d, esi
0x180014476  lea     rdx, aMostackenabled; "MoStackEnabled"
0x18001447d  lea     rcx, [rsp+298h+var_178]
0x180014485  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001448a  nop
0x18001448b  xorps   xmm0, xmm0
0x18001448e  movups  [rsp+298h+var_158], xmm0
0x180014496  xorps   xmm1, xmm1
0x180014499  movdqa  [rsp+298h+var_148], xmm1
0x1800144a2  lea     r8d, [rbx+0Ah]
0x1800144a6  lea     rdx, aPolicyhash; "PolicyHash"
0x1800144ad  lea     rcx, [rsp+298h+var_158]
0x1800144b5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800144ba  nop
0x1800144bb  xorps   xmm0, xmm0
0x1800144be  movups  [rsp+298h+var_138], xmm0
0x1800144c6  xorps   xmm1, xmm1
0x1800144c9  movdqa  [rsp+298h+var_128], xmm1
0x1800144d2  lea     r8d, [rbx+0Fh]
0x1800144d6  lea     rdx, aPolicytimestam; "PolicyTimeStamp"
0x1800144dd  lea     rcx, [rsp+298h+var_138]
0x1800144e5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800144ea  nop
0x1800144eb  xorps   xmm0, xmm0
0x1800144ee  movups  [rsp+298h+var_118], xmm0
0x1800144f6  xorps   xmm1, xmm1
0x1800144f9  movdqa  [rsp+298h+var_108], xmm1
0x180014502  lea     r8d, [rbx+0Ch]
0x180014506  lea     rdx, aReservereset; "ReserveReset"
0x18001450d  lea     rcx, [rsp+298h+var_118]
0x180014515  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001451a  nop
0x18001451b  xorps   xmm0, xmm0
0x18001451e  movups  [rsp+298h+var_F8], xmm0
0x180014526  xorps   xmm1, xmm1
0x180014529  movdqa  [rsp+298h+var_E8], xmm1
0x180014532  mov     r8d, esi
0x180014535  lea     rdx, aUsodiagnostics; "USODiagnostics"
0x18001453c  lea     rcx, [rsp+298h+var_F8]
0x180014544  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014549  nop
0x18001454a  xorps   xmm0, xmm0
0x18001454d  movups  [rsp+298h+var_D8], xmm0
0x180014555  xorps   xmm1, xmm1
0x180014558  movdqa  [rsp+298h+var_C8], xmm1
0x180014561  lea     r8d, [rbx+1Ah]
0x180014565  lea     rdx, aOsswapdetectio; "OSSwapDetectionInitialized"
0x18001456c  lea     rcx, [rsp+298h+var_D8]
0x180014574  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014579  nop
0x18001457a  xorps   xmm0, xmm0
0x18001457d  movups  [rsp+298h+var_B8], xmm0
0x180014585  xorps   xmm1, xmm1
0x180014588  movdqa  [rsp+298h+var_A8], xmm1
0x180014591  lea     esi, [rbx+19h]
0x180014594  mov     r8d, esi
0x180014597  lea     rdx, aWorkercansurre; "WorkerCanSurrenderLogging"
0x18001459e  lea     rcx, [rsp+298h+var_B8]
0x1800145a6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800145ab  nop
0x1800145ac  xorps   xmm0, xmm0
0x1800145af  movups  [rsp+298h+var_98], xmm0
0x1800145b7  xorps   xmm1, xmm1
0x1800145ba  movdqa  [rsp+298h+var_88], xmm1
0x1800145c3  mov     r8d, esi
0x1800145c6  lea     rdx, aServiceisloggi; "ServiceIsLoggingForWorker"
0x1800145cd  lea     rcx, [rsp+298h+var_98]
0x1800145d5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800145da  nop
0x1800145db  lea     rax, [rsp+298h+var_198]
0x1800145e3  mov     [rsp+298h+var_268], rax
0x1800145e8  lea     rax, [rsp+298h+var_78]
0x1800145f0  mov     [rsp+298h+var_260], rax
0x1800145f5  lea     rdx, [rsp+298h+var_268]
0x1800145fa  lea     rcx, [rsp+298h+var_38]
0x180014602  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@AEBV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x180014607  nop
0x180014608  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; void (*)(void *)
0x18001460f  lea     edx, [rbx+20h]; unsigned __int64
0x180014612  lea     r8d, [rbx+9]; unsigned __int64
0x180014616  lea     rcx, [rsp+298h+var_198]; void *
0x18001461e  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180014623  mov     rsi, [rsp+298h+var_38]
0x18001462b  mov     r14, [rsp+298h+var_30]
0x180014633  mov     [rsp+298h+var_268], r14
0x180014638  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180014640  mov     [rsp+298h+bstrString], rsi
0x180014645  cmp     rsi, r14
0x180014648  jz      loc_180014703
0x18001464e  mov     r8, [rsi+10h]
0x180014652  mov     rcx, rsi
0x180014655  cmp     qword ptr [rsi+18h], 7
0x18001465a  jbe     short loc_18001465F
0x18001465c  mov     rcx, [rsi]
0x18001465f  xorps   xmm0, xmm0
0x180014662  movups  [rsp+298h+var_218], xmm0
0x18001466a  movdqu  [rsp+298h+var_208], xmm6
0x180014673  mov     word ptr [rsp+298h+var_218], bx
0x18001467b  mov     rdx, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180014682  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014686  inc     rax
0x180014689  cmp     [rdx+rax*2], bx
0x18001468d  jnz     short loc_180014686
0x18001468f  mov     [rsp+298h+var_228], rcx
0x180014694  mov     [rsp+298h+var_220], r8
0x180014699  lea     rcx, [rsp+298h+var_218]
0x1800146a1  mov     [rsp+298h+var_238], rcx
0x1800146a6  mov     [rsp+298h+var_230], rbx
0x1800146ab  mov     [rsp+298h+var_248], rdx
0x1800146b0  mov     [rsp+298h+var_240], rax
0x1800146b5  lea     r9, [rsp+298h+var_228]
0x1800146ba  lea     r8, [rsp+298h+var_238]
0x1800146bf  lea     rdx, [rsp+298h+var_248]
0x1800146c4  lea     rcx, [rsp+298h+var_258]
0x1800146c9  call    ?DeleteSystemValue@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@00@Z; Windows::Registry::DeleteSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x1800146ce  nop
0x1800146cf  lea     rcx, [rsp+298h+var_218]; void *
0x1800146d7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800146dc  nop
0x1800146dd  jmp     short loc_1800146FA
0x1800146df  xor     ebx, ebx
0x1800146e1  mov     rsi, [rsp+298h+bstrString]
0x1800146e6  mov     r14, [rsp+298h+var_268]
0x1800146eb  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1800146f3  mov     edi, dword ptr [rsp+298h+var_78]
0x1800146fa  add     rsi, 20h ; ' '
0x1800146fe  jmp     loc_180014640
0x180014703  xorps   xmm0, xmm0
0x180014706  xor     eax, eax
0x180014708  movups  xmmword ptr [rsp+298h+var_50], xmm0
0x180014710  mov     [rsp+298h+var_40], rax
0x180014718  movups  [rsp+298h+var_1F8], xmm0
0x180014720  xorps   xmm1, xmm1
0x180014723  movdqa  [rsp+298h+var_1E8], xmm1
0x18001472c  lea     r8d, [rax+2Fh]
0x180014730  lea     rdx, aCheckingToSeeI; "Checking to see if mostack override has"...
0x180014737  lea     rcx, [rsp+298h+var_1F8]
0x18001473f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014744  nop
0x180014745  xorps   xmm0, xmm0
0x180014748  movups  [rsp+298h+var_1D8], xmm0
0x180014750  xorps   xmm1, xmm1
0x180014753  movdqa  [rsp+298h+var_1C8], xmm1
0x18001475c  mov     r8d, 18h
0x180014762  lea     rdx, aCleanupusocore; "CleanupUsoCoreWorkerLogs"
0x180014769  lea     rcx, [rsp+298h+var_1D8]
0x180014771  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180014776  nop
0x180014777  xorps   xmm0, xmm0
0x18001477a  movups  [rsp+298h+var_1B8], xmm0
0x180014782  xorps   xmm1, xmm1
0x180014785  movdqa  [rsp+298h+var_1A8], xmm1
0x18001478e  mov     r8d, 1Ch
0x180014794  lea     rdx, aSmartscheduler; "SmartSchedulerValidationTask"
0x18001479b  lea     rcx, [rsp+298h+var_1B8]
0x1800147a3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800147a8  nop
0x1800147a9  lea     rax, [rsp+298h+var_1F8]
0x1800147b1  mov     [rsp+298h+var_268], rax
0x1800147b6  lea     rax, [rsp+298h+var_198]
0x1800147be  mov     [rsp+298h+var_260], rax
0x1800147c3  lea     rdx, [rsp+298h+var_268]
0x1800147c8  lea     rcx, [rsp+298h+var_50]
0x1800147d0  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@V?$initializer_list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@AEBV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@1@@Z; std::vector<std::wstring>::vector<std::wstring>(std::initializer_list<std::wstring>,std::allocator<std::wstring> const &)
0x1800147d5  nop
0x1800147d6  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; void (*)(void *)
0x1800147dd  mov     edx, 20h ; ' '; unsigned __int64
0x1800147e2  lea     r8d, [rdx-1Dh]; unsigned __int64
0x1800147e6  lea     rcx, [rsp+298h+var_1F8]; void *
0x1800147ee  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800147f3  mov     rsi, qword ptr [rsp+298h+var_50]
0x1800147fb  mov     r14, qword ptr [rsp+298h+var_50+8]
0x180014803  mov     [rsp+298h+var_268], r14
0x180014808  mov     [rsp+298h+bstrString], rsi; int
0x18001480d  cmp     rsi, r14
0x180014810  jz      loc_1800148A7
0x180014816  mov     r10, [rsi+10h]
0x18001481a  mov     rdx, rsi
0x18001481d  cmp     qword ptr [rsi+18h], 7
0x180014822  jbe     short loc_180014827
0x180014824  mov     rdx, [rsi]
0x180014827  mov     r9, cs:?USO_SCHEDULER_ROOT@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USO_SCHEDULER_ROOT
0x18001482e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014832  inc     rax
0x180014835  cmp     [r9+rax*2], bx
0x18001483a  jnz     short loc_180014832
0x18001483c  mov     r8, cs:?USOCURRENTVERSIONROOT_REDIRECTION_ID@Registry@SystemInterface@@2QEB_WEB; wchar_t const * const SystemInterface::Registry::USOCURRENTVERSIONROOT_REDIRECTION_ID
0x180014843  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180014847  inc     rcx
0x18001484a  cmp     [r8+rcx*2], bx
0x18001484f  jnz     short loc_180014847
0x180014851  mov     [rsp+298h+var_228], rdx
0x180014856  mov     [rsp+298h+var_220], r10
0x18001485b  mov     [rsp+298h+var_238], r9
0x180014860  mov     [rsp+298h+var_230], rax
0x180014865  mov     [rsp+298h+var_248], r8
0x18001486a  mov     [rsp+298h+var_240], rcx
0x18001486f  lea     r9, [rsp+298h+var_228]
0x180014874  lea     r8, [rsp+298h+var_238]
0x180014879  lea     rdx, [rsp+298h+var_248]
0x18001487e  lea     rcx, [rsp+298h+var_258]
0x180014883  call    ?DeleteSystemValue@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@00@Z; Windows::Registry::DeleteSystemValue(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180014888  nop
0x180014889  jmp     short loc_18001489E
0x18001488b  xor     ebx, ebx
0x18001488d  mov     rsi, [rsp+298h+bstrString]
0x180014892  mov     r14, [rsp+298h+var_268]
0x180014897  mov     edi, dword ptr [rsp+298h+var_78]
0x18001489e  add     rsi, 20h ; ' '
0x1800148a2  jmp     loc_180014808
0x1800148a7  mov     [rsp+298h+var_58], rbx
0x1800148af  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\UpdateOrchestrato"...
0x1800148b6  lea     rcx, [rsp+298h+var_268]
0x1800148bb  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1800148c0  lea     rdx, [rsp+298h+var_58]
0x1800148c8  mov     rcx, rax
0x1800148cb  call    ?GetTaskSchedulerFolder@@YAJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UITaskFolder@@Uerr_returncode_policy@wil@@@2@@Z; GetTaskSchedulerFolder(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,wil::com_ptr_t<ITaskFolder,wil::err_returncode_policy> &)
0x1800148d0  mov     esi, eax
0x1800148d2  test    eax, eax
0x1800148d4  jns     short loc_180014912
0x1800148d6  mov     rcx, [rsp+298h]; this
0x1800148de  mov     r9d, eax; char *
0x1800148e1  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x1800148e8  mov     edx, 50Bh; void *
0x1800148ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800148f2  nop
0x1800148f3  mov     rcx, [rsp+298h+var_58]
0x1800148fb  test    rcx, rcx
0x1800148fe  jz      short loc_18001490D
0x180014900  mov     rax, [rcx]
0x180014903  mov     rax, [rax+10h]
0x180014907  call    _guard_dispatch_icall
0x18001490c  nop
0x18001490d  jmp     loc_180014D45
0x180014912  xorps   xmm1, xmm1
0x180014915  movdqu  [rsp+298h+var_70], xmm1
0x18001491e  mov     [rsp+298h+var_60], rbx
0x180014926  lea     rcx, psz; "Maintenance Install"
0x18001492d  call    cs:__imp_SysAllocString
0x180014933  mov     [rsp+298h+bstrString], rax
0x180014938  or      edi, 10h
0x18001493b  mov     dword ptr [rsp+298h+var_78], edi
0x180014942  mov     rcx, [rsp+298h]; this
0x18001494a  test    rax, rax
0x18001494d  jz      loc_180014D67
0x180014953  mov     rdx, qword ptr [rsp+298h+var_70+8]
0x18001495b  cmp     rdx, [rsp+298h+var_60]
0x180014963  jz      short loc_180014976
0x180014965  mov     [rdx], rax
0x180014968  mov     rcx, rbx
0x18001496b  add     qword ptr [rsp+298h+var_70+8], 8
0x180014974  jmp     short loc_18001498D
0x180014976  lea     r8, [rsp+298h+bstrString]
0x18001497b  lea     rcx, [rsp+298h+var_70]
0x180014983  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x180014988  mov     rcx, [rsp+298h+bstrString]; bstrString
0x18001498d  and     edi, 0FFFFFFEFh
0x180014990  test    rcx, rcx
0x180014993  jz      short loc_18001499C
0x180014995  call    cs:__imp_SysFreeString
0x18001499b  nop
0x18001499c  lea     rcx, aUniversalOrche; "Universal Orchestrator Start"
0x1800149a3  call    cs:__imp_SysAllocString
0x1800149a9  mov     [rsp+298h+var_248], rax
0x1800149ae  or      edi, 20h
0x1800149b1  mov     dword ptr [rsp+298h+var_78], edi
0x1800149b8  mov     rcx, [rsp+298h]; this
0x1800149c0  test    rax, rax
0x1800149c3  jz      loc_180014D79
0x1800149c9  mov     rdx, qword ptr [rsp+298h+var_70+8]
  ... truncated ...
```
