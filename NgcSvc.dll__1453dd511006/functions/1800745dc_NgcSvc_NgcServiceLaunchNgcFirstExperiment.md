# NgcSvc::NgcServiceLaunchNgcFirstExperiment

- ea: `0x1800745dc`
- end: `0x18007487d`
- name: `NgcSvc::NgcServiceLaunchNgcFirstExperiment`
- size: `673`
- prototype: `__int64 __fastcall(ULONG SessionId)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007307c`

## callees

- `0x180010990`
- `0x1800281e0`
- `0x1800288a0`
- `0x180028d18`
- `0x18002fb30`
- `0x1800323d0`
- `0x1800334f0`
- `0x180042e40`
- `0x180046d90`
- `0x180048394`
- `0x18005fb04`
- `0x18005fdf0`
- `0x1800745dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800747e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800747e8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180074709`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180074709`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800747de`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x1800747de`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180074625`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180074625`
- `ext-ms-win-session-usertoken-l1-1-0!IsInteractiveUserSession` at `0x1800745e9`
- `ext-ms-win-session-usertoken-l1-1-0!IsInteractiveUserSession` at `0x1800745e9`

## string_xrefs

- `0x18007465f`: `onecore\ds\security\ngc\kspsvc\svc\ngcsvc.cpp`
- `0x180074743`: `onecore\ds\security\ngc\kspsvc\svc\ngcsvc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcSvc::NgcServiceLaunchNgcFirstExperiment(ULONG SessionId)
{
  signed int v2; // eax
  int NgcDefaultCredentialProvider; // ebx
  DWORD v4; // eax
  int UserSidFromToken; // edi
  signed int v6; // eax
  DWORD v7; // eax
  bool v8; // di
  const unsigned __int16 *v9; // rdx
  DWORD LastError; // eax
  int v12; // [rsp+20h] [rbp-30h]
  LPWSTR StringSid; // [rsp+30h] [rbp-20h] BYREF
  PSID Sid[2]; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  ULONG v17; // [rsp+78h] [rbp+28h] BYREF
  DWORD v18; // [rsp+80h] [rbp+30h] BYREF
  void *phToken; // [rsp+88h] [rbp+38h] BYREF

  if ( (unsigned int)IsInteractiveUserSession() && (unsigned __int8)IsWTSQueryUserTokenPresent() )
  {
    StringSid = 0;
    phToken = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &phToken,
      0);
    if ( WTSQueryUserToken(SessionId, &phToken) )
    {
      *(_OWORD *)Sid = 0;
      v15 = 0;
      UserSidFromToken = NgcUtils::GetUserSidFromToken(phToken, (const void **)Sid);
      if ( UserSidFromToken >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &StringSid,
          0);
        if ( ConvertSidToStringSidW(Sid[0], &StringSid) )
        {
          std::vector<unsigned char>::_Tidy(Sid);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
          v8 = 0;
          if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent() )
          {
            LOBYTE(v17) = 0;
            if ( (unsigned __int8)WinStationIsSessionRemoteable(0, SessionId, &v17) )
            {
              v8 = (_BYTE)v17 != 0;
            }
            else
            {
              LastError = GetLastError();
              if ( (unsigned int)dword_180122070 > 3 )
              {
                v18 = LastError;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (__int64)&dword_180122070,
                  (unsigned __int8 *)byte_1801002F7,
                  0,
                  0,
                  (__int64)&v18);
              }
            }
          }
          LOBYTE(v9) = v8;
          NgcDefaultCredentialProvider = NgcFirst::MakeNgcDefaultCredentialProvider(StringSid, v9);
          goto LABEL_31;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v6 = GetLastError();
          NgcDefaultCredentialProvider = v6;
          if ( v6 > 0 )
            NgcDefaultCredentialProvider = (unsigned __int16)v6 | 0x80070000;
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0x3F5,
            (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ngcsvc.cpp",
            (const char *)(unsigned int)NgcDefaultCredentialProvider,
            v12);
        }
        else
        {
          v7 = GetLastError();
          NgcDefaultCredentialProvider = v7;
          if ( (unsigned int)dword_180122070 > 2 )
          {
            v17 = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (__int64)&dword_180122070,
              (unsigned __int8 *)&dword_18010032C,
              0,
              0,
              (__int64)&v17);
          }
          if ( NgcDefaultCredentialProvider > 0 )
            NgcDefaultCredentialProvider = (unsigned __int16)NgcDefaultCredentialProvider | 0x80070000;
        }
        std::vector<unsigned char>::_Tidy(Sid);
      }
      else
      {
        std::vector<unsigned char>::_Tidy(Sid);
        NgcDefaultCredentialProvider = UserSidFromToken;
      }
    }
    else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      v2 = GetLastError();
      NgcDefaultCredentialProvider = v2;
      if ( v2 > 0 )
        NgcDefaultCredentialProvider = (unsigned __int16)v2 | 0x80070000;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x3D5,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\ngcsvc.cpp",
        (const char *)(unsigned int)NgcDefaultCredentialProvider,
        v12);
    }
    else
    {
      v4 = GetLastError();
      NgcDefaultCredentialProvider = v4;
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v17 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180100359,
          0,
          0,
          (__int64)&v17);
      }
      if ( NgcDefaultCredentialProvider > 0 )
        NgcDefaultCredentialProvider = (unsigned __int16)NgcDefaultCredentialProvider | 0x80070000;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&phToken);
LABEL_31:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
    return (unsigned int)NgcDefaultCredentialProvider;
  }
  if ( (unsigned int)dword_180122070 > 4 )
  {
    v17 = SessionId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)word_180100382,
      0,
      0,
      (__int64)&v17);
  }
  return 0;
}

```

## disassembly

```asm
0x1800745dc  push    rbp
0x1800745de  push    rbx
0x1800745df  push    rdi
0x1800745e0  mov     rbp, rsp
0x1800745e3  sub     rsp, 50h
0x1800745e7  mov     ebx, ecx
0x1800745e9  call    cs:__imp_IsInteractiveUserSession
0x1800745ef  test    eax, eax
0x1800745f1  jz      loc_180074843
0x1800745f7  call    IsWTSQueryUserTokenPresent
0x1800745fc  test    al, al
0x1800745fe  jz      loc_180074843
0x180074604  mov     [rbp+StringSid], 0
0x18007460c  mov     [rbp+phToken], 0
0x180074614  xor     edx, edx
0x180074616  lea     rcx, [rbp+phToken]
0x18007461a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007461f  lea     rdx, [rbp+phToken]; phToken
0x180074623  mov     ecx, ebx; SessionId
0x180074625  call    cs:__imp_WTSQueryUserToken
0x18007462b  test    eax, eax
0x18007462d  jnz     loc_1800746C3
0x180074633  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007463a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x18007463f  test    al, al
0x180074641  jz      short loc_180074675
0x180074643  call    cs:__imp_GetLastError
0x180074649  mov     ebx, eax
0x18007464b  test    eax, eax
0x18007464d  jle     short loc_180074658
0x18007464f  movzx   ebx, ax
0x180074652  or      ebx, 80070000h
0x180074658  mov     rcx, [rbp+18h]; this
0x18007465c  mov     r9d, ebx; char *
0x18007465f  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180074666  mov     edx, 3D5h; void *
0x18007466b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180074670  jmp     loc_1800747A5
0x180074675  call    cs:__imp_GetLastError
0x18007467b  mov     ebx, eax
0x18007467d  mov     ecx, cs:dword_180122070
0x180074683  cmp     ecx, 2
0x180074686  jbe     short loc_1800746AD
0x180074688  mov     [rbp+arg_8], eax
0x18007468b  lea     rax, [rbp+arg_8]
0x18007468f  mov     qword ptr [rsp+50h+var_30], rax
0x180074694  xor     r9d, r9d
0x180074697  xor     r8d, r8d
0x18007469a  lea     rdx, byte_180100359
0x1800746a1  lea     rcx, dword_180122070
0x1800746a8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800746ad  test    ebx, ebx
0x1800746af  jle     loc_1800747A5
0x1800746b5  movzx   ebx, bx
0x1800746b8  or      ebx, 80070000h
0x1800746be  jmp     loc_1800747A5
0x1800746c3  xorps   xmm0, xmm0
0x1800746c6  movdqu  xmmword ptr [rbp+Sid], xmm0
0x1800746cb  mov     [rbp+var_8], 0
0x1800746d3  lea     rdx, [rbp+Sid]
0x1800746d7  mov     rcx, [rbp+phToken]; TokenHandle
0x1800746db  call    NgcUtils__GetUserSidFromToken
0x1800746e0  mov     edi, eax
0x1800746e2  test    eax, eax
0x1800746e4  jns     short loc_1800746F6
0x1800746e6  lea     rcx, [rbp+Sid]
0x1800746ea  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800746ef  mov     ebx, edi
0x1800746f1  jmp     loc_1800747A5
0x1800746f6  xor     edx, edx
0x1800746f8  lea     rcx, [rbp+StringSid]
0x1800746fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180074701  lea     rdx, [rbp+StringSid]; StringSid
0x180074705  mov     rcx, [rbp+Sid]; Sid
0x180074709  call    cs:__imp_ConvertSidToStringSidW
0x18007470f  test    eax, eax
0x180074711  jnz     loc_1800747B3
0x180074717  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x18007471e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180074723  test    al, al
0x180074725  jz      short loc_180074756
0x180074727  call    cs:__imp_GetLastError
0x18007472d  mov     ebx, eax
0x18007472f  test    eax, eax
0x180074731  jle     short loc_18007473C
0x180074733  movzx   ebx, ax
0x180074736  or      ebx, 80070000h
0x18007473c  mov     rcx, [rbp+18h]; this
0x180074740  mov     r9d, ebx; char *
0x180074743  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x18007474a  mov     edx, 3F5h; void *
0x18007474f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180074754  jmp     short loc_18007479B
0x180074756  call    cs:__imp_GetLastError
0x18007475c  mov     ebx, eax
0x18007475e  mov     ecx, cs:dword_180122070
0x180074764  cmp     ecx, 2
0x180074767  jbe     short loc_18007478E
0x180074769  mov     [rbp+arg_8], eax
0x18007476c  lea     rax, [rbp+arg_8]
0x180074770  mov     qword ptr [rsp+50h+var_30], rax
0x180074775  xor     r9d, r9d
0x180074778  xor     r8d, r8d
0x18007477b  lea     rdx, dword_18010032C
0x180074782  lea     rcx, dword_180122070
0x180074789  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007478e  test    ebx, ebx
0x180074790  jle     short loc_18007479B
0x180074792  movzx   ebx, bx
0x180074795  or      ebx, 80070000h
0x18007479b  lea     rcx, [rbp+Sid]
0x18007479f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800747a4  nop
0x1800747a5  lea     rcx, [rbp+phToken]
0x1800747a9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800747ae  jmp     loc_180074836
0x1800747b3  lea     rcx, [rbp+Sid]
0x1800747b7  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800747bc  nop
0x1800747bd  lea     rcx, [rbp+phToken]
0x1800747c1  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800747c6  xor     dil, dil
0x1800747c9  call    IsWinStationIsSessionRemoteablePresent
0x1800747ce  test    al, al
0x1800747d0  jz      short loc_180074828
0x1800747d2  mov     byte ptr [rbp+arg_8], dil
0x1800747d6  lea     r8, [rbp+arg_8]
0x1800747da  mov     edx, ebx
0x1800747dc  xor     ecx, ecx
0x1800747de  call    cs:__imp_WinStationIsSessionRemoteable
0x1800747e4  test    al, al
0x1800747e6  jnz     short loc_180074820
0x1800747e8  call    cs:__imp_GetLastError
0x1800747ee  mov     ecx, cs:dword_180122070
0x1800747f4  cmp     ecx, 3
0x1800747f7  jbe     short loc_180074828
0x1800747f9  mov     [rbp+arg_10], eax
0x1800747fc  lea     rax, [rbp+arg_10]
0x180074800  mov     qword ptr [rsp+50h+var_30], rax
0x180074805  xor     r9d, r9d
0x180074808  xor     r8d, r8d
0x18007480b  lea     rdx, byte_1801002F7
0x180074812  lea     rcx, dword_180122070
0x180074819  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18007481e  jmp     short loc_180074828
0x180074820  cmp     byte ptr [rbp+arg_8], dil
0x180074824  setnz   dil
0x180074828  mov     dl, dil; unsigned __int16 *
0x18007482b  mov     rcx, [rbp+StringSid]; this
0x18007482f  call    ?MakeNgcDefaultCredentialProvider@NgcFirst@@YAJPEBG_N@Z; NgcFirst::MakeNgcDefaultCredentialProvider(ushort const *,bool)
0x180074834  mov     ebx, eax
0x180074836  lea     rcx, [rbp+StringSid]; void *
0x18007483a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007483f  mov     eax, ebx
0x180074841  jmp     short loc_180074875
0x180074843  mov     eax, cs:dword_180122070
0x180074849  cmp     eax, 4
0x18007484c  jbe     short loc_180074873
0x18007484e  mov     [rbp+arg_8], ebx
0x180074851  lea     rax, [rbp+arg_8]
0x180074855  mov     qword ptr [rsp+50h+var_30], rax
0x18007485a  xor     r9d, r9d
0x18007485d  xor     r8d, r8d
0x180074860  lea     rdx, word_180100382
0x180074867  lea     rcx, dword_180122070
0x18007486e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180074873  xor     eax, eax
0x180074875  add     rsp, 50h
0x180074879  pop     rdi
0x18007487a  pop     rbx
0x18007487b  pop     rbp
0x18007487c  retn
```
