# NgcKspServer::CheckContainerForLogonKey(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,NgcTransportContainerInfo const &,bool *)

- ea: `0x180038988`
- end: `0x180038ed6`
- name: `?CheckContainerForLogonKey@NgcKspServer@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBUNgcTransportContainerInfo@@PEA_N@Z`
- size: `1358`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006d918`

## callees

- `0x18000782c`
- `0x180020a0c`
- `0x180028d18`
- `0x18002c9d8`
- `0x180034cf8`
- `0x180038988`
- `0x180039080`
- `0x18004566c`
- `0x180046d90`
- `0x180048394`
- `0x18004aa08`
- `0x18004f1dc`
- `0x18005f6a8`
- `0x1800ab228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038ca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038eb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038b10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038ca8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038eb6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800389cd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800389cd`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalFindCredential` at `0x180038ada`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalFindCredential` at `0x180038b72`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalFindCredential` at `0x180038ada`
- `ext-ms-win-security-ngc-local-l1-1-0!NgcLocalFindCredential` at `0x180038b72`

## string_xrefs

- `0x180038a01`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x180038a8f`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x180038af1`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x180038be9`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x180038c89`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x180038d62`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x180038e0f`: `onecore\ds\security\ngc\kspsvc\svc\mgmtsrv.cpp`
- `0x180038e89`: `login.live.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NgcKspServer::CheckContainerForLogonKey(_QWORD *a1, __int64 a2, bool *a3)
{
  _QWORD *v4; // rdi
  BOOL v5; // ebx
  signed int LastError; // ebx
  enum NgcUserAccountType *v7; // r8
  int UserAccountType; // eax
  int Credential; // eax
  unsigned int v10; // edi
  HLOCAL v11; // rcx
  char *v13; // rdx
  int v14; // edx
  bool v15; // di
  __int64 v16; // rdx
  __int64 v17; // rcx
  int v18; // eax
  unsigned int v19; // r14d
  HLOCAL v20; // rcx
  int IsJoined; // eax
  char IsEnabled; // al
  __int64 v23; // rcx
  int JoinInfo; // eax
  int v25; // eax
  HLOCAL v26; // rcx
  bool v27; // zf
  HLOCAL v28; // rcx
  unsigned int v29; // [rsp+20h] [rbp-40h]
  __int64 v30; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-20h] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h] BYREF
  char v34; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  int v36; // [rsp+A0h] [rbp+40h] BYREF
  int v37; // [rsp+B8h] [rbp+58h] BYREF

  v4 = a1;
  hMem = 0;
  p_hMem = &hMem;
  Sid = 0;
  v34 = 1;
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v5 = ConvertStringSidToSidW((LPCWSTR)a1, &Sid);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_Win32(
        retaddr,
        (void *)0xB8,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)LastError,
        v29);
    }
    else if ( (unsigned int)dword_180122070 > 2 )
    {
      v36 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_1800FFE07,
        0,
        0,
        (__int64)&v36);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_77;
  }
  LODWORD(v30) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    UserAccountType = NgcUtils::GetUserAccountType((NgcUtils *)hMem, &v30, v7);
    LastError = UserAccountType;
    if ( UserAccountType < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
        (const char *)(unsigned int)UserAccountType,
        v29);
LABEL_77:
      v28 = hMem;
      hMem = 0;
      if ( v28 )
        LocalFree(v28);
      return (unsigned int)LastError;
    }
    LastError = 0;
  }
  else
  {
    LastError = NgcUtils::GetUserAccountType((NgcUtils *)hMem, &v30, v7);
    if ( LastError < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_77;
      v13 = &byte_1800FFDD7;
      goto LABEL_25;
    }
  }
  v37 = 0;
  if ( (unsigned __int8)IsNgcLocalFindCredentialPresent() )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      if ( v4[3] > 7u )
        v4 = (_QWORD *)*v4;
      Credential = NgcLocalFindCredential(v4, &v37);
      v10 = Credential;
      if ( Credential < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE3,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)(unsigned int)Credential,
          v29);
        v11 = hMem;
        hMem = 0;
        if ( v11 )
          LocalFree(v11);
        return v10;
      }
    }
    else
    {
      if ( v4[3] > 7u )
        v4 = (_QWORD *)*v4;
      LastError = NgcLocalFindCredential(v4, &v37);
      if ( LastError < 0 )
      {
        if ( (unsigned int)dword_180122070 <= 2 )
          goto LABEL_77;
        v13 = byte_1800FFDA3;
        goto LABEL_25;
      }
    }
    v14 = v37;
    if ( v37 )
    {
      *a3 = 1;
      goto LABEL_77;
    }
  }
  else
  {
    v14 = v37;
  }
  v15 = 0;
  LOBYTE(v36) = 0;
  if ( (_DWORD)v30 == 1 )
  {
    v15 = v14 != 0;
    goto LABEL_76;
  }
  if ( (_DWORD)v30 == 2 )
  {
    LastError = FindLogonKeyWithDomainAndTenant((wchar_t *)L"login.live.com", (wchar_t *)&sourceString);
    if ( LastError < 0 )
      goto LABEL_77;
LABEL_64:
    v15 = v36;
LABEL_76:
    *a3 = v15;
    goto LABEL_77;
  }
  if ( (_DWORD)v30 != 3 )
  {
    if ( (_DWORD)v30 != 4 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x171,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)0x8000FFFFLL,
          v29);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v36 = -2147418113;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1800FFC9B,
          0,
          0,
          (__int64)&v36);
      }
LABEL_70:
      v26 = hMem;
      v27 = hMem == 0;
      hMem = 0;
      if ( !v27 )
        LocalFree(v26);
      return 2147549183LL;
    }
LABEL_53:
    v30 = 0;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl);
    v30 = 0;
    if ( IsEnabled )
    {
      JoinInfo = DsrGetJoinInfo(v23, &v30);
      LastError = JoinInfo;
      if ( JoinInfo < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13F,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)(unsigned int)JoinInfo,
          v29);
        goto LABEL_56;
      }
    }
    else
    {
      v25 = DsrGetJoinInfo(v23, &v30);
      LastError = v25;
      if ( v25 < 0 )
      {
        if ( (unsigned int)dword_180122070 > 2 )
        {
          v36 = v25;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_1800FFCF3,
            0,
            0,
            (__int64)&v36);
        }
        goto LABEL_56;
      }
    }
    if ( !v30 || *(_DWORD *)v30 != 1 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
          (const char *)0x8000FFFFLL,
          v29);
      }
      else if ( (unsigned int)dword_180122070 > 2 )
      {
        v36 = -2147418113;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)&unk_1800FFCC8,
          0,
          0,
          (__int64)&v36);
      }
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v30);
      goto LABEL_70;
    }
    LastError = FindLogonKeyWithDomainAndTenant(*(wchar_t **)(v30 + 24), *(wchar_t **)(v30 + 32));
    if ( LastError < 0 )
    {
LABEL_56:
      wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v30);
      goto LABEL_77;
    }
    wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&void DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(&v30);
    goto LABEL_64;
  }
  LODWORD(v30) = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    IsJoined = DeviceRegistrationStateApi::IsJoined(v17, v16, &v30);
    LastError = IsJoined;
    if ( IsJoined >= 0 )
    {
LABEL_50:
      if ( !(_DWORD)v30 )
      {
        if ( (unsigned int)dword_180122070 > 3 )
        {
          v36 = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)byte_1800FFD1F,
            0,
            0,
            (__int64)&v36);
        }
        goto LABEL_76;
      }
      goto LABEL_53;
    }
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DsrIsDeviceJoinedEx",
      L"DeviceRegistrationStateApi::IsJoined",
      (unsigned int)IsJoined);
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_77;
    v13 = (char *)&dword_1800FFD74;
LABEL_25:
    v36 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)v13,
      0,
      0,
      (__int64)&v36);
    goto LABEL_77;
  }
  v18 = DeviceRegistrationStateApi::IsJoined(v17, v16, &v30);
  v19 = v18;
  if ( v18 >= 0 )
    goto LABEL_50;
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"DsrIsDeviceJoinedEx",
    L"DeviceRegistrationStateApi::IsJoined",
    (unsigned int)v18);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11B,
    (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\mgmtsrv.cpp",
    (const char *)v19,
    v29);
  v20 = hMem;
  hMem = 0;
  if ( v20 )
    LocalFree(v20);
  return v19;
}

```

## disassembly

```asm
0x180038988  mov     [rsp-38h+arg_8], rbx
0x18003898d  push    rbp
0x18003898e  push    rsi
0x18003898f  push    rdi
0x180038990  push    r12
0x180038992  push    r13
0x180038994  push    r14
0x180038996  push    r15
0x180038998  mov     rbp, rsp
0x18003899b  sub     rsp, 60h
0x18003899f  mov     r15, r8
0x1800389a2  mov     r12, rdx
0x1800389a5  mov     rdi, rcx
0x1800389a8  xor     r13d, r13d
0x1800389ab  mov     [rbp+hMem], r13
0x1800389af  lea     rax, [rbp+hMem]
0x1800389b3  mov     [rbp+var_20], rax
0x1800389b7  mov     [rbp+Sid], r13
0x1800389bb  mov     [rbp+var_10], 1
0x1800389bf  cmp     qword ptr [rcx+18h], 7
0x1800389c4  jbe     short loc_1800389C9
0x1800389c6  mov     rcx, [rcx]; StringSid
0x1800389c9  lea     rdx, [rbp+Sid]; Sid
0x1800389cd  call    cs:__imp_ConvertStringSidToSidW
0x1800389d3  mov     ebx, eax
0x1800389d5  lea     rcx, [rbp+var_20]
0x1800389d9  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800389de  test    ebx, ebx
0x1800389e0  jnz     short loc_180038A5A
0x1800389e2  call    cs:__imp_GetLastError
0x1800389e8  mov     ebx, eax
0x1800389ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x1800389f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x1800389f6  test    al, al
0x1800389f8  jz      short loc_180038A14
0x1800389fa  mov     rcx, [rbp+38h]; this
0x1800389fe  mov     r9d, ebx; char *
0x180038a01  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180038a08  mov     edx, 0B8h; void *
0x180038a0d  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180038a12  jmp     short loc_180038A44
0x180038a14  mov     eax, cs:dword_180122070
0x180038a1a  cmp     eax, 2
0x180038a1d  jbe     short loc_180038A44
0x180038a1f  mov     [rbp+arg_0], ebx
0x180038a22  lea     rax, [rbp+arg_0]
0x180038a26  mov     [rsp+60h+var_40], rax
0x180038a2b  xor     r9d, r9d
0x180038a2e  xor     r8d, r8d
0x180038a31  lea     rdx, byte_1800FFE07
0x180038a38  lea     rcx, dword_180122070
0x180038a3f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180038a44  test    ebx, ebx
0x180038a46  jle     loc_180038EA9
0x180038a4c  movzx   ebx, bx
0x180038a4f  or      ebx, 80070000h
0x180038a55  jmp     loc_180038EA9
0x180038a5a  mov     dword ptr [rbp+var_30], r13d
0x180038a5e  lea     rsi, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180038a65  mov     rcx, rsi
0x180038a68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180038a6d  lea     rdx, [rbp+var_30]; void *
0x180038a71  mov     rcx, [rbp+hMem]; this
0x180038a75  test    al, al
0x180038a77  jz      loc_180038B1D
0x180038a7d  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x180038a82  mov     ebx, eax
0x180038a84  test    eax, eax
0x180038a86  jns     short loc_180038AA5
0x180038a88  mov     rcx, [rbp+38h]; this
0x180038a8c  mov     r9d, eax; char *
0x180038a8f  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180038a96  mov     edx, 0CAh; void *
0x180038a9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038aa0  jmp     loc_180038EA9
0x180038aa5  mov     ebx, r13d
0x180038aa8  mov     [rbp+arg_18], r13d
0x180038aac  call    IsNgcLocalFindCredentialPresent
0x180038ab1  test    al, al
0x180038ab3  jz      loc_180038BA6
0x180038ab9  mov     rcx, rsi
0x180038abc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180038ac1  test    al, al
0x180038ac3  jz      loc_180038B61
0x180038ac9  cmp     qword ptr [rdi+18h], 7
0x180038ace  jbe     short loc_180038AD3
0x180038ad0  mov     rdi, [rdi]
0x180038ad3  lea     rdx, [rbp+arg_18]
0x180038ad7  mov     rcx, rdi
0x180038ada  call    cs:__imp_NgcLocalFindCredential
0x180038ae0  mov     edi, eax
0x180038ae2  test    eax, eax
0x180038ae4  jns     loc_180038B96
0x180038aea  mov     rcx, [rbp+38h]; this
0x180038aee  mov     r9d, eax; char *
0x180038af1  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180038af8  mov     edx, 0E3h; void *
0x180038afd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b02  nop
0x180038b03  mov     rcx, [rbp+hMem]; hMem
0x180038b07  mov     [rbp+hMem], r13
0x180038b0b  test    rcx, rcx
0x180038b0e  jz      short loc_180038B16
0x180038b10  call    cs:__imp_LocalFree
0x180038b16  mov     eax, edi
0x180038b18  jmp     loc_180038EBE
0x180038b1d  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x180038b22  mov     ebx, eax
0x180038b24  test    eax, eax
0x180038b26  jns     short loc_180038AA8
0x180038b28  mov     ecx, cs:dword_180122070
0x180038b2e  cmp     ecx, 2
0x180038b31  jbe     loc_180038EA9
0x180038b37  lea     rdx, byte_1800FFDD7
0x180038b3e  lea     rax, [rbp+arg_0]
0x180038b42  xor     r9d, r9d
0x180038b45  mov     [rsp+60h+var_40], rax
0x180038b4a  xor     r8d, r8d
0x180038b4d  mov     [rbp+arg_0], ebx
0x180038b50  lea     rcx, dword_180122070
0x180038b57  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180038b5c  jmp     loc_180038EA9
0x180038b61  cmp     qword ptr [rdi+18h], 7
0x180038b66  jbe     short loc_180038B6B
0x180038b68  mov     rdi, [rdi]
0x180038b6b  lea     rdx, [rbp+arg_18]
0x180038b6f  mov     rcx, rdi
0x180038b72  call    cs:__imp_NgcLocalFindCredential
0x180038b78  mov     ebx, eax
0x180038b7a  test    eax, eax
0x180038b7c  jns     short loc_180038B96
0x180038b7e  mov     eax, cs:dword_180122070
0x180038b84  cmp     eax, 2
0x180038b87  jbe     loc_180038EA9
0x180038b8d  lea     rdx, byte_1800FFDA3
0x180038b94  jmp     short loc_180038B3E
0x180038b96  mov     edx, [rbp+arg_18]
0x180038b99  test    edx, edx
0x180038b9b  jz      short loc_180038BA9
0x180038b9d  mov     byte ptr [r15], 1
0x180038ba1  jmp     loc_180038EA9
0x180038ba6  mov     edx, [rbp+arg_18]
0x180038ba9  mov     dil, r13b
0x180038bac  mov     byte ptr [rbp+arg_0], r13b
0x180038bb0  mov     ecx, dword ptr [rbp+var_30]
0x180038bb3  sub     ecx, 1
0x180038bb6  jz      loc_180038EA0
0x180038bbc  sub     ecx, 1
0x180038bbf  jz      loc_180038E7B
0x180038bc5  sub     ecx, 1
0x180038bc8  jz      short loc_180038C3C
0x180038bca  cmp     ecx, 1
0x180038bcd  jz      loc_180038D38
0x180038bd3  mov     rcx, rsi
0x180038bd6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180038bdb  test    al, al
0x180038bdd  jz      short loc_180038BFF
0x180038bdf  mov     rcx, [rbp+38h]; this
0x180038be3  mov     r9d, 8000FFFFh; char *
0x180038be9  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180038bf0  mov     edx, 171h; void *
0x180038bf5  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180038bfa  jmp     loc_180038E61
0x180038bff  mov     eax, cs:dword_180122070
0x180038c05  cmp     eax, 2
0x180038c08  jbe     loc_180038E61
0x180038c0e  mov     [rbp+arg_0], 8000FFFFh
0x180038c15  lea     rax, [rbp+arg_0]
0x180038c19  mov     [rsp+60h+var_40], rax
0x180038c1e  xor     r9d, r9d
0x180038c21  xor     r8d, r8d
0x180038c24  lea     rdx, byte_1800FFC9B
0x180038c2b  lea     rcx, dword_180122070
0x180038c32  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180038c37  jmp     loc_180038E61
0x180038c3c  mov     dword ptr [rbp+var_30], r13d
0x180038c40  mov     rcx, rsi
0x180038c43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180038c48  mov     [rsp+60h+var_38], r13
0x180038c4d  lea     r8, [rbp+var_30]
0x180038c51  test    al, al
0x180038c53  jz      short loc_180038CB6
0x180038c55  call    ?IsJoined@DeviceRegistrationStateApi@@SAJPEBGW4_JOIN_TYPE@@PEAH2PEAPEBU_CERT_CONTEXT@@2@Z; DeviceRegistrationStateApi::IsJoined(ushort const *,_JOIN_TYPE,int *,int *,_CERT_CONTEXT const * *,int *)
0x180038c5a  mov     r14d, eax
0x180038c5d  test    eax, eax
0x180038c5f  jns     loc_180038CF9
0x180038c65  mov     r9d, eax
0x180038c68  lea     r8, aDeviceregistra_1; "DeviceRegistrationStateApi::IsJoined"
0x180038c6f  lea     rdx, aDsrisdevicejoi; "DsrIsDeviceJoinedEx"
0x180038c76  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180038c7d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180038c82  mov     rcx, [rbp+38h]; this
0x180038c86  mov     r9d, r14d; char *
0x180038c89  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180038c90  mov     edx, 11Bh; void *
0x180038c95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038c9a  nop
0x180038c9b  mov     rcx, [rbp+hMem]; hMem
0x180038c9f  mov     [rbp+hMem], r13
0x180038ca3  test    rcx, rcx
0x180038ca6  jz      short loc_180038CAE
0x180038ca8  call    cs:__imp_LocalFree
0x180038cae  mov     eax, r14d
0x180038cb1  jmp     loc_180038EBE
0x180038cb6  call    ?IsJoined@DeviceRegistrationStateApi@@SAJPEBGW4_JOIN_TYPE@@PEAH2PEAPEBU_CERT_CONTEXT@@2@Z; DeviceRegistrationStateApi::IsJoined(ushort const *,_JOIN_TYPE,int *,int *,_CERT_CONTEXT const * *,int *)
0x180038cbb  mov     ebx, eax
0x180038cbd  test    eax, eax
0x180038cbf  jns     short loc_180038CF9
0x180038cc1  mov     r9d, eax
0x180038cc4  lea     r8, aDeviceregistra_1; "DeviceRegistrationStateApi::IsJoined"
0x180038ccb  lea     rdx, aDsrisdevicejoi; "DsrIsDeviceJoinedEx"
0x180038cd2  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180038cd9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180038cde  mov     eax, cs:dword_180122070
0x180038ce4  cmp     eax, 2
0x180038ce7  jbe     loc_180038EA9
0x180038ced  lea     rdx, dword_1800FFD74
0x180038cf4  jmp     loc_180038B3E
0x180038cf9  cmp     dword ptr [rbp+var_30], r13d
0x180038cfd  jnz     short loc_180038D38
0x180038cff  mov     eax, cs:dword_180122070
0x180038d05  cmp     eax, 3
0x180038d08  jbe     loc_180038EA6
0x180038d0e  mov     [rbp+arg_0], ebx
0x180038d11  lea     rax, [rbp+arg_0]
0x180038d15  mov     [rsp+60h+var_40], rax
0x180038d1a  xor     r9d, r9d
0x180038d1d  xor     r8d, r8d
0x180038d20  lea     rdx, byte_1800FFD1F
0x180038d27  lea     rcx, dword_180122070
0x180038d2e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180038d33  jmp     loc_180038EA6
0x180038d38  mov     [rbp+var_30], r13
0x180038d3c  mov     rcx, rsi
0x180038d3f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180038d44  mov     [rbp+var_30], r13
0x180038d48  lea     rdx, [rbp+var_30]
0x180038d4c  test    al, al
0x180038d4e  jz      short loc_180038D82
0x180038d50  call    DsrGetJoinInfo
0x180038d55  mov     ebx, eax
0x180038d57  test    eax, eax
0x180038d59  jns     short loc_180038DBF
0x180038d5b  mov     rcx, [rbp+38h]; this
0x180038d5f  mov     r9d, eax; char *
0x180038d62  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180038d69  mov     edx, 13Fh; void *
0x180038d6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038d73  nop
0x180038d74  lea     rcx, [rbp+var_30]
0x180038d78  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x180038d7d  jmp     loc_180038EA9
0x180038d82  call    DsrGetJoinInfo
0x180038d87  mov     ebx, eax
0x180038d89  test    eax, eax
0x180038d8b  jns     short loc_180038DBF
0x180038d8d  mov     ecx, cs:dword_180122070
0x180038d93  cmp     ecx, 2
0x180038d96  jbe     short loc_180038D74
0x180038d98  mov     [rbp+arg_0], eax
0x180038d9b  lea     rax, [rbp+arg_0]
0x180038d9f  mov     [rsp+60h+var_40], rax
0x180038da4  xor     r9d, r9d
0x180038da7  xor     r8d, r8d
0x180038daa  lea     rdx, byte_1800FFCF3
0x180038db1  lea     rcx, dword_180122070
0x180038db8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180038dbd  jmp     short loc_180038D74
0x180038dbf  mov     rcx, [rbp+var_30]
0x180038dc3  test    rcx, rcx
0x180038dc6  jz      short loc_180038DF9
0x180038dc8  cmp     dword ptr [rcx], 1
0x180038dcb  jnz     short loc_180038DF9
0x180038dcd  lea     r9, [rbp+arg_0]
0x180038dd1  mov     r8, r12
0x180038dd4  mov     rdx, [rcx+20h]; wchar_t *
0x180038dd8  mov     rcx, [rcx+18h]; S2
0x180038ddc  call    FindLogonKeyWithDomainAndTenant
0x180038de1  mov     ebx, eax
0x180038de3  lea     rcx, [rbp+var_30]
0x180038de7  test    eax, eax
0x180038de9  js      short loc_180038D78
0x180038deb  call    ??1?$unique_storage@U?$resource_policy@PEAU_DSREG_JOIN_INFO@@P6AXPEAU1@@Z$1?DsrFreeJoinInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_DSREG_JOIN_INFO *,void (*)(_DSREG_JOIN_INFO *),&DsrFreeJoinInfo(_DSREG_JOIN_INFO *),wistd::integral_constant<unsigned __int64,0>,_DSREG_JOIN_INFO *,_DSREG_JOIN_INFO *,0,std::nullptr_t>>(void)
0x180038df0  mov     dil, byte ptr [rbp+arg_0]
0x180038df4  jmp     loc_180038EA6
0x180038df9  mov     rcx, rsi
0x180038dfc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180038e01  test    al, al
0x180038e03  jz      short loc_180038E22
0x180038e05  mov     rcx, [rbp+38h]; this
0x180038e09  mov     r9d, 8000FFFFh; char *
0x180038e0f  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180038e16  mov     edx, 155h; void *
0x180038e1b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180038e20  jmp     short loc_180038E57
0x180038e22  mov     eax, cs:dword_180122070
0x180038e28  cmp     eax, 2
0x180038e2b  jbe     short loc_180038E57
0x180038e2d  mov     [rbp+arg_0], 8000FFFFh
0x180038e34  lea     rax, [rbp+arg_0]
  ... truncated ...
```
