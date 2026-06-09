# NgcSvc::NgcServiceVerifyAndFixContainerServiceAppDataDirectoryAcl(void)

- ea: `0x180063b78`
- end: `0x180063f9d`
- name: `?NgcServiceVerifyAndFixContainerServiceAppDataDirectoryAcl@NgcSvc@@YAXXZ`
- size: `1061`
- prototype: `void __fastcall(NgcSvc *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800732e4`

## callees

- `0x18000e960`
- `0x1800281e0`
- `0x180028d18`
- `0x18002c850`
- `0x18002fb30`
- `0x1800323d0`
- `0x180044d64`
- `0x180046d90`
- `0x180047228`
- `0x1800533a4`
- `0x18005cee0`
- `0x18005dd44`
- `0x180063594`
- `0x1800635bc`
- `0x1800635e0`
- `0x1800638f0`
- `0x180063b78`
- `0x180063fa4`
- `0x180064340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063ec9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063c22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063e54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063ec9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180063dbd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180063dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180063daa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180063daa`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180063ea5`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180063ea5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063beb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180063beb`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180063e33`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x180063e33`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180063c82`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180063cb0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180063c82`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180063cb0`

## string_xrefs

- `0x180063c0c`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x180063c9a`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x180063de3`: `onecore\ds\security\ngc\kspsvc\svc\aclfix.cpp`
- `0x180063e2a`: `SeTakeOwnershipPrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall NgcSvc::NgcServiceVerifyAndFixContainerServiceAppDataDirectoryAcl(NgcSvc *this)
{
  const char *v1; // r9
  DWORD v2; // eax
  unsigned __int8 *v3; // rdx
  int v4; // eax
  __int64 v5; // rcx
  HANDLE CurrentProcess; // rax
  const char *v7; // r9
  __int64 v8; // rdx
  unsigned __int8 *v9; // rdx
  int PreviousState; // [rsp+20h] [rbp-E0h]
  _BYTE v11[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD LastError; // [rsp+34h] [rbp-CCh] BYREF
  DWORD v13; // [rsp+38h] [rbp-C8h] BYREF
  PSID Sid; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v15; // [rsp+48h] [rbp-B8h] BYREF
  int BasicProfileFolderPath; // [rsp+4Ch] [rbp-B4h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-B0h] BYREF
  struct _LUID Luid; // [rsp+58h] [rbp-A8h] BYREF
  struct _TOKEN_PRIVILEGES *p_NewState; // [rsp+60h] [rbp-A0h] BYREF
  void **p_TokenHandle; // [rsp+68h] [rbp-98h]
  DWORD *p_LastError; // [rsp+70h] [rbp-90h]
  __int16 v22; // [rsp+78h] [rbp-88h]
  _QWORD v23[3]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v24; // [rsp+98h] [rbp-68h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v26[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[528]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  LastError = 0;
  BasicProfileFolderPath = 0;
  v11[0] = 0;
  v23[0] = &LastError;
  v23[1] = &BasicProfileFolderPath;
  v23[2] = v11;
  v24 = 256;
  Sid = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0);
  if ( !ConvertStringSidToSidW(L"S-1-5-80-2381253463-2694003897-3435975801-3559003598-683041300", &Sid) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
    {
      wil::details::in1diag3::Log_GetLastError(
        retaddr,
        (void *)0x274,
        (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
        v1);
      goto LABEL_37;
    }
    LastError = GetLastError();
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_37;
    v2 = LastError;
    v3 = (unsigned __int8 *)byte_1800FD013;
LABEL_12:
    v13 = v2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      v3,
      0,
      0,
      (__int64)&v13);
    goto LABEL_37;
  }
  memset_0(v27, 0, 0x208u);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(8, L"S-1-5-19", v27, 260);
    if ( BasicProfileFolderPath < 0 )
    {
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_37;
      v2 = BasicProfileFolderPath;
      v3 = (unsigned __int8 *)&unk_1800FCFE8;
      goto LABEL_12;
    }
    p_NewState = (struct _TOKEN_PRIVILEGES *)v27;
    p_TokenHandle = (void **)L"Microsoft";
    p_LastError = (DWORD *)L"Ngc";
    v26[0] = 0;
    v26[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v26[0]) = 0;
    BasicProfileFolderPath = NgcUtils::ComposePath(&p_NewState, 3, v26);
    if ( BasicProfileFolderPath < 0
      || (LastError = NgcSvc::NgcServiceVerifyIndividualAcl(v26, Sid, v11)) != 0
      || !v11[0]
      || (LOBYTE(v5) = 1, (LastError = NgcSvc::NgcServiceReconfigureContainerService(v5)) != 0) )
    {
LABEL_36:
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v26);
      goto LABEL_37;
    }
    *(_WORD *)((char *)&v13 + 1) = 256;
    TokenHandle = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &TokenHandle,
      0);
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
    {
      NewState = 0;
      Luid = 0;
      if ( LookupPrivilegeValueW(0, L"SeTakeOwnershipPrivilege", &Luid) )
      {
        NewState.PrivilegeCount = 1;
        NewState.Privileges[0].Luid = Luid;
        NewState.Privileges[0].Attributes = 2;
        if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0) )
        {
          p_NewState = &NewState;
          p_TokenHandle = &TokenHandle;
          p_LastError = &LastError;
          v22 = 256;
          NgcSvc::NgcServiceVerifyAndFixDirectoryTreeAcl(v26, Sid);
          wil::details::ScopeExitFnGuard__lambda_fa8eee099055e728290ed397db09f5a1___::operator()(&p_NewState);
          goto LABEL_35;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v8 = 773;
          goto LABEL_20;
        }
        LastError = GetLastError();
        if ( (unsigned int)dword_180122070 <= 2 )
          goto LABEL_35;
        v9 = (unsigned __int8 *)byte_1800FCF49;
      }
      else
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
        {
          v8 = 745;
          goto LABEL_20;
        }
        LastError = GetLastError();
        if ( (unsigned int)dword_180122070 <= 2 )
          goto LABEL_35;
        v9 = (unsigned __int8 *)&dword_1800FCF94;
      }
    }
    else
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl'::`2'::impl) )
      {
        v8 = 722;
LABEL_20:
        wil::details::in1diag3::Log_GetLastError(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
          v7);
LABEL_35:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        wil::details::ScopeExitFnGuard__lambda_0232fc221bfe92da797dec691efaf50b___::operator()(&v13);
        goto LABEL_36;
      }
      LastError = GetLastError();
      if ( (unsigned int)dword_180122070 <= 2 )
        goto LABEL_35;
      v9 = (unsigned __int8 *)qword_1800FCFC0;
    }
    v15 = LastError;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      v9,
      0,
      0,
      (__int64)&v15);
    goto LABEL_35;
  }
  v4 = GetBasicProfileFolderPath(8, L"S-1-5-19", v27, 260);
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"onecore\\ds\\security\\ngc\\kspsvc\\svc\\aclfix.cpp",
      (const char *)(unsigned int)v4,
      PreviousState);
LABEL_37:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  wil::details::ScopeExitFnGuard__lambda_7e034dd1942a106d26a3357035704153___::operator()(v23);
}

```

## disassembly

```asm
0x180063b78  mov     [rsp-8+arg_0], rdi
0x180063b7d  push    rbp
0x180063b7e  lea     rbp, [rsp-1F0h]
0x180063b86  sub     rsp, 2F0h
0x180063b8d  mov     rax, cs:__security_cookie
0x180063b94  xor     rax, rsp
0x180063b97  mov     [rbp+1F0h+var_10], rax
0x180063b9e  xor     edi, edi
0x180063ba0  mov     [rsp+2F0h+var_2BC], edi
0x180063ba4  mov     [rsp+2F0h+var_2A4], edi
0x180063ba8  mov     [rsp+2F0h+var_2C0], dil
0x180063bad  lea     rax, [rsp+2F0h+var_2BC]
0x180063bb2  mov     [rbp+1F0h+var_270], rax
0x180063bb6  lea     rax, [rsp+2F0h+var_2A4]
0x180063bbb  mov     [rbp+1F0h+var_268], rax
0x180063bbf  lea     rax, [rsp+2F0h+var_2C0]
0x180063bc4  mov     [rbp+1F0h+var_260], rax
0x180063bc8  mov     [rbp+1F0h+var_258], 100h
0x180063bce  mov     [rsp+2F0h+Sid], rdi
0x180063bd3  xor     edx, edx
0x180063bd5  lea     rcx, [rsp+2F0h+Sid]
0x180063bda  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180063bdf  lea     rdx, [rsp+2F0h+Sid]; Sid
0x180063be4  lea     rcx, StringSid; "S-1-5-80-2381253463-2694003897-34359758"...
0x180063beb  call    cs:__imp_ConvertStringSidToSidW
0x180063bf1  test    eax, eax
0x180063bf3  jnz     short loc_180063C4B
0x180063bf5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063bfc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180063c01  test    al, al
0x180063c03  jz      short loc_180063C22
0x180063c05  mov     rcx, [rbp+1F8h]; this
0x180063c0c  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180063c13  mov     edx, 274h; void *
0x180063c18  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180063c1d  jmp     loc_180063F69
0x180063c22  call    cs:__imp_GetLastError
0x180063c28  mov     [rsp+2F0h+var_2BC], eax
0x180063c2c  mov     eax, cs:dword_180122070
0x180063c32  cmp     eax, 2
0x180063c35  jbe     loc_180063F69
0x180063c3b  mov     eax, [rsp+2F0h+var_2BC]
0x180063c3f  lea     rdx, byte_1800FD013
0x180063c46  jmp     loc_180063CD8
0x180063c4b  xor     edx, edx; Val
0x180063c4d  mov     r8d, 208h; Size
0x180063c53  lea     rcx, [rbp+1F0h+var_220]; void *
0x180063c57  call    memset_0
0x180063c5c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063c63  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180063c68  mov     r9d, 104h
0x180063c6e  lea     r8, [rbp+1F0h+var_220]
0x180063c72  lea     rdx, aS1519; "S-1-5-19"
0x180063c79  mov     ecx, 8
0x180063c7e  test    al, al
0x180063c80  jz      short loc_180063CB0
0x180063c82  call    cs:__imp_GetBasicProfileFolderPath
0x180063c88  mov     rcx, [rbp+1F8h]; this
0x180063c8f  test    eax, eax
0x180063c91  jns     loc_180063F69
0x180063c97  mov     r9d, eax; char *
0x180063c9a  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180063ca1  mov     edx, 289h; void *
0x180063ca6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180063cab  jmp     loc_180063F69
0x180063cb0  call    cs:__imp_GetBasicProfileFolderPath
0x180063cb6  mov     [rsp+2F0h+var_2A4], eax
0x180063cba  test    eax, eax
0x180063cbc  jns     short loc_180063CFD
0x180063cbe  mov     eax, cs:dword_180122070
0x180063cc4  cmp     eax, 2
0x180063cc7  jbe     loc_180063F69
0x180063ccd  mov     eax, [rsp+2F0h+var_2A4]
0x180063cd1  lea     rdx, unk_1800FCFE8
0x180063cd8  mov     [rsp+2F0h+var_2B8], eax
0x180063cdc  lea     rax, [rsp+2F0h+var_2B8]
0x180063ce1  mov     [rsp+2F0h+PreviousState], rax
0x180063ce6  xor     r9d, r9d
0x180063ce9  xor     r8d, r8d
0x180063cec  lea     rcx, dword_180122070
0x180063cf3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180063cf8  jmp     loc_180063F69
0x180063cfd  lea     rax, [rbp+1F0h+var_220]
0x180063d01  mov     [rsp+2F0h+var_290], rax
0x180063d06  mov     rax, cs:off_1800D2C60; "Microsoft"
0x180063d0d  mov     [rsp+2F0h+var_288], rax
0x180063d12  mov     rax, cs:off_1800D2C68; "Ngc"
0x180063d19  mov     [rsp+2F0h+var_280], rax
0x180063d1e  xorps   xmm0, xmm0
0x180063d21  movups  [rbp+1F0h+var_240], xmm0
0x180063d25  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180063d2d  movdqu  [rbp+1F0h+var_230], xmm1
0x180063d32  mov     word ptr [rbp+1F0h+var_240], di
0x180063d36  lea     r8, [rbp+1F0h+var_240]
0x180063d3a  mov     edx, 3
0x180063d3f  lea     rcx, [rsp+2F0h+var_290]
0x180063d44  call    ?ComposePath@NgcUtils@@YAJQEBQEBGKPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::ComposePath(ushort const * const * const,ulong,std::wstring *)
0x180063d49  mov     [rsp+2F0h+var_2A4], eax
0x180063d4d  test    eax, eax
0x180063d4f  js      loc_180063F5F
0x180063d55  lea     r8, [rsp+2F0h+var_2C0]
0x180063d5a  mov     rdx, [rsp+2F0h+Sid]
0x180063d5f  lea     rcx, [rbp+1F0h+var_240]
0x180063d63  call    NgcSvc__NgcServiceVerifyIndividualAcl
0x180063d68  mov     [rsp+2F0h+var_2BC], eax
0x180063d6c  test    eax, eax
0x180063d6e  jnz     loc_180063F5F
0x180063d74  cmp     [rsp+2F0h+var_2C0], dil
0x180063d79  jz      loc_180063F5F
0x180063d7f  mov     cl, 1
0x180063d81  call    NgcSvc__NgcServiceReconfigureContainerService
0x180063d86  mov     [rsp+2F0h+var_2BC], eax
0x180063d8a  test    eax, eax
0x180063d8c  jnz     loc_180063F5F
0x180063d92  mov     word ptr [rsp+2F0h+var_2B8+1], 100h
0x180063d99  mov     [rsp+2F0h+TokenHandle], rdi
0x180063d9e  xor     edx, edx
0x180063da0  lea     rcx, [rsp+2F0h+TokenHandle]
0x180063da5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180063daa  call    cs:__imp_GetCurrentProcess
0x180063db0  lea     r8, [rsp+2F0h+TokenHandle]; TokenHandle
0x180063db5  mov     edx, 20h ; ' '; DesiredAccess
0x180063dba  mov     rcx, rax; ProcessHandle
0x180063dbd  call    cs:__imp_OpenProcessToken
0x180063dc3  test    eax, eax
0x180063dc5  jnz     short loc_180063E19
0x180063dc7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063dce  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180063dd3  test    al, al
0x180063dd5  jz      short loc_180063DF4
0x180063dd7  mov     edx, 2D2h; void *
0x180063ddc  mov     rcx, [rbp+1F8h]; this
0x180063de3  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\ngc\\kspsvc\\svc"...
0x180063dea  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180063def  jmp     loc_180063F49
0x180063df4  call    cs:__imp_GetLastError
0x180063dfa  mov     [rsp+2F0h+var_2BC], eax
0x180063dfe  mov     eax, cs:dword_180122070
0x180063e04  cmp     eax, 2
0x180063e07  jbe     loc_180063F49
0x180063e0d  lea     rdx, qword_1800FCFC0
0x180063e14  jmp     loc_180063EE5
0x180063e19  xorps   xmm0, xmm0
0x180063e1c  movups  xmmword ptr [rbp+1F0h+NewState.PrivilegeCount], xmm0
0x180063e20  mov     qword ptr [rsp+2F0h+Luid.LowPart], rdi
0x180063e25  lea     r8, [rsp+2F0h+Luid]; lpLuid
0x180063e2a  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x180063e31  xor     ecx, ecx; lpSystemName
0x180063e33  call    cs:__imp_LookupPrivilegeValueW
0x180063e39  test    eax, eax
0x180063e3b  jnz     short loc_180063E76
0x180063e3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063e44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180063e49  test    al, al
0x180063e4b  jz      short loc_180063E54
0x180063e4d  mov     edx, 2E9h
0x180063e52  jmp     short loc_180063DDC
0x180063e54  call    cs:__imp_GetLastError
0x180063e5a  mov     [rsp+2F0h+var_2BC], eax
0x180063e5e  mov     eax, cs:dword_180122070
0x180063e64  cmp     eax, 2
0x180063e67  jbe     loc_180063F49
0x180063e6d  lea     rdx, dword_1800FCF94
0x180063e74  jmp     short loc_180063EE5
0x180063e76  mov     [rbp+1F0h+NewState.PrivilegeCount], 1
0x180063e7d  mov     rax, qword ptr [rsp+2F0h+Luid.LowPart]
0x180063e82  mov     qword ptr [rbp+1F0h+NewState.Privileges.Luid.LowPart], rax
0x180063e86  mov     [rbp+1F0h+NewState.Privileges.Attributes], 2
0x180063e8d  mov     [rsp+2F0h+ReturnLength], rdi; ReturnLength
0x180063e92  mov     [rsp+2F0h+PreviousState], rdi; PreviousState
0x180063e97  xor     r9d, r9d; BufferLength
0x180063e9a  lea     r8, [rbp+1F0h+NewState]; NewState
0x180063e9e  xor     edx, edx; DisableAllPrivileges
0x180063ea0  mov     rcx, [rsp+2F0h+TokenHandle]; TokenHandle
0x180063ea5  call    cs:__imp_AdjustTokenPrivileges
0x180063eab  test    eax, eax
0x180063ead  jnz     short loc_180063F0B
0x180063eaf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration> `wil::Feature<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::GetImpl(void)'::`2'::impl
0x180063eb6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_NgcTraceloggingtoWilMigration>::__private_IsEnabled(void)
0x180063ebb  test    al, al
0x180063ebd  jz      short loc_180063EC9
0x180063ebf  mov     edx, 305h
0x180063ec4  jmp     loc_180063DDC
0x180063ec9  call    cs:__imp_GetLastError
0x180063ecf  mov     [rsp+2F0h+var_2BC], eax
0x180063ed3  mov     eax, cs:dword_180122070
0x180063ed9  cmp     eax, 2
0x180063edc  jbe     short loc_180063F49
0x180063ede  lea     rdx, byte_1800FCF49
0x180063ee5  mov     eax, [rsp+2F0h+var_2BC]
0x180063ee9  mov     [rsp+2F0h+var_2A8], eax
0x180063eed  lea     rax, [rsp+2F0h+var_2A8]
0x180063ef2  mov     [rsp+2F0h+PreviousState], rax
0x180063ef7  xor     r9d, r9d
0x180063efa  xor     r8d, r8d
0x180063efd  lea     rcx, dword_180122070
0x180063f04  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180063f09  jmp     short loc_180063F49
0x180063f0b  lea     rax, [rbp+1F0h+NewState]
0x180063f0f  mov     [rsp+2F0h+var_290], rax
0x180063f14  lea     rax, [rsp+2F0h+TokenHandle]
0x180063f19  mov     [rsp+2F0h+var_288], rax
0x180063f1e  lea     rax, [rsp+2F0h+var_2BC]
0x180063f23  mov     [rsp+2F0h+var_280], rax
0x180063f28  mov     [rsp+2F0h+var_278], 100h
0x180063f2f  mov     rdx, [rsp+2F0h+Sid]
0x180063f34  lea     rcx, [rbp+1F0h+var_240]
0x180063f38  call    NgcSvc__NgcServiceVerifyAndFixDirectoryTreeAcl
0x180063f3d  nop
0x180063f3e  lea     rcx, [rsp+2F0h+var_290]
0x180063f43  call    wil__details__ScopeExitFnGuard__lambda_fa8eee099055e728290ed397db09f5a1_____operator__
0x180063f48  nop
0x180063f49  lea     rcx, [rsp+2F0h+TokenHandle]
0x180063f4e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180063f53  nop
0x180063f54  lea     rcx, [rsp+2F0h+var_2B8]
0x180063f59  call    wil__details__ScopeExitFnGuard__lambda_0232fc221bfe92da797dec691efaf50b_____operator__
0x180063f5e  nop
0x180063f5f  lea     rcx, [rbp+1F0h+var_240]
0x180063f63  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180063f68  nop
0x180063f69  lea     rcx, [rsp+2F0h+Sid]; void *
0x180063f6e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180063f73  nop
0x180063f74  lea     rcx, [rbp+1F0h+var_270]
0x180063f78  call    wil__details__ScopeExitFnGuard__lambda_7e034dd1942a106d26a3357035704153_____operator__
0x180063f7d  mov     rcx, [rbp+1F0h+var_10]
0x180063f84  xor     rcx, rsp; StackCookie
0x180063f87  call    __security_check_cookie
0x180063f8c  mov     rdi, [rsp+2F0h+arg_0]
0x180063f94  add     rsp, 2F0h
0x180063f9b  pop     rbp
0x180063f9c  retn
```
