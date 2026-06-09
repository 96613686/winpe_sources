# Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(HSTRING__ *,Windows::Internal::Security::Authentication::Web::CallerContext &,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)

- ea: `0x1800228e0`
- end: `0x180023078`
- name: `?GetFromId@CWamProviderRegistrationInternal@Web@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@AEAVCallerContext@23456@PEAPEAUIWamProviderRegistrationInformation@23456@@Z`
- size: `1944`
- prototype: `__int64 __fastcall(HSTRING, struct Windows::Internal::Security::Authentication::Web::CallerContext *this, struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **)`
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180020d90`
- `0x1800262f0`
- `0x18006e4c4`
- `0x1800dae5c`
- `0x1800db234`

## callees

- `0x18000a7b0`
- `0x18000bd40`
- `0x180011400`
- `0x180011f94`
- `0x180012624`
- `0x180013804`
- `0x1800228e0`
- `0x1800323a0`
- `0x180040790`
- `0x180040980`
- `0x1800455a4`
- `0x18007c0f0`
- `0x18008e690`
- `0x18011b010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022a89`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180022a89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800229b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800229b0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022a54`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022b06`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022a54`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180022b06`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800229c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800229c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002293c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18002293c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022a7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022b2b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022bf1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022f94`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022bf1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180022f94`

## string_xrefs

- `0x180022a18`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x180023041`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x180023053`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x180023065`: `onecore\ds\security\tokenbroker\inc\WamCallerContext.h`
- `0x180022921`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180022954`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x18002298e`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180022a34`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180022aca`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180022d3a`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`
- `0x180022e0a`: `onecore\ds\security\tokenbroker\broker\lib\wamproviderregistration.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Windows::Internal::Security::Authentication::Web::CWamProviderRegistrationInternal::GetFromId(
        HSTRING a1,
        struct Windows::Internal::Security::Authentication::Web::CallerContext *this,
        struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **a3)
{
  int v7; // eax
  unsigned int v8; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v11; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  const char *v14; // r9
  int RegistrationInfomationWithId; // eax
  unsigned int v16; // ebx
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v17; // rcx
  const char *v18; // r9
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v19; // rax
  const struct _tlgProvider_t *v20; // rax
  int Extension; // eax
  unsigned int v22; // ebx
  const struct _tlgProvider_t *v23; // rbx
  int v24; // r9d
  struct Windows::Internal::StateRepository::IApplicationExtension *v25; // rcx
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v26; // rcx
  struct Windows::Internal::StateRepository::IApplicationExtension *v27; // rcx
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v28; // rcx
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v29; // rcx
  int ProviderRegistrationInformationFromExtension; // eax
  struct Windows::Internal::StateRepository::IApplicationExtension *v31; // rcx
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v32; // rcx
  ULONGLONG Keyword; // rbx
  int v34; // edi
  const struct _tlgProvider_t *v35; // rax
  ULONGLONG v36; // rcx
  struct Windows::Internal::StateRepository::IApplicationExtension *v37; // rcx
  int UserDataCount; // [rsp+20h] [rbp-F8h]
  int UserDataCounta; // [rsp+20h] [rbp-F8h]
  struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *v40; // [rsp+30h] [rbp-E8h] BYREF
  struct Windows::Internal::StateRepository::IApplicationExtension *v41; // [rsp+38h] [rbp-E0h] BYREF
  unsigned int v42; // [rsp+40h] [rbp-D8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+48h] [rbp-D0h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-C8h] BYREF
  char v45; // [rsp+58h] [rbp-C0h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+60h] [rbp-B8h] BYREF
  ULONGLONG v47; // [rsp+70h] [rbp-A8h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-A0h] BYREF
  char *v49; // [rsp+88h] [rbp-90h]
  int v50; // [rsp+90h] [rbp-88h]
  int v51; // [rsp+94h] [rbp-84h]
  struct _EVENT_DATA_DESCRIPTOR v52; // [rsp+98h] [rbp-80h] BYREF
  char *v53; // [rsp+A8h] [rbp-70h]
  int v54; // [rsp+B0h] [rbp-68h]
  int v55; // [rsp+B4h] [rbp-64h]
  unsigned int *v56; // [rsp+B8h] [rbp-60h]
  __int64 v57; // [rsp+C0h] [rbp-58h]
  struct _EVENT_DATA_DESCRIPTOR *v58; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)0x80004003LL,
      UserDataCount);
    return 2147500035LL;
  }
  if ( WindowsIsStringEmpty(a1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)0x80070057LL,
      UserDataCount);
    return 2147942487LL;
  }
  *a3 = 0;
  v7 = Windows::Internal::Security::Authentication::Web::CallerContext::CaptureSessionUserInformation(this);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A8,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)v7,
      UserDataCount);
    return v8;
  }
  v45 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xF01FFu, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147023888 )
    {
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      if ( (v12 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E5,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
          (const char *)v12,
          UserDataCount);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3AB,
          (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
          (const char *)v12,
          UserDataCounta);
        if ( v45 && !SetThreadToken(0, TokenHandle) )
          wil::details::in1diag3::_FailFast_GetLastError(
            retaddr,
            (void *)0x1DE,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
            v13);
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
          CloseHandle(TokenHandle);
        return v12;
      }
    }
  }
  if ( !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
      v14);
  v45 = 1;
  v40 = 0;
  RegistrationInfomationWithId = Windows::Internal::Security::Authentication::Web::ProviderRegistrationCache::FindRegistrationInfomationWithId(
                                   a1,
                                   *((_DWORD *)this + 6),
                                   &v40);
  v16 = RegistrationInfomationWithId;
  if ( RegistrationInfomationWithId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B1,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
      (const char *)(unsigned int)RegistrationInfomationWithId,
      UserDataCount);
    v17 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( v45 && !SetThreadToken(0, TokenHandle) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\inc\\WamCallerContext.h",
        v18);
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(TokenHandle);
    return v16;
  }
  v19 = v40;
  if ( v40 )
    goto LABEL_80;
  v20 = TbLogProvider::Provider();
  if ( *(_DWORD *)v20 > 5u )
  {
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 5;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = *((_QWORD *)v20 + 1);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v49 = byte_180146825;
    v50 = 48;
    v51 = 1;
    v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*((_QWORD *)v20 + 4), &EventDescriptor, 0, 0, 2u, &UserData);
  }
  v41 = 0;
  EventDescriptor = 0;
  v52.Ptr = (ULONGLONG)&std::_Func_impl_no_alloc<_lambda_8db1653d5e5b1978f9d2fa3b5818f431_,bool,Windows::Internal::StateRepository::IApplicationExtension *>::`vftable';
  *(_QWORD *)&v52.Size = a1;
  v58 = &v52;
  Extension = ExtensionRegistrationResolver::_FindExtension(&EventDescriptor, &v52, this, &v41);
  v22 = Extension;
  if ( Extension != -2146893805 )
  {
    if ( Extension < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CA,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)Extension,
        UserDataCount);
      if ( EventDescriptor.Keyword )
        (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)EventDescriptor.Keyword + 16LL))(EventDescriptor.Keyword);
      if ( *(_QWORD *)&EventDescriptor.Id )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&EventDescriptor.Id + 16LL))(*(_QWORD *)&EventDescriptor.Id);
      v27 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v28 + 16LL))(v28);
      }
LABEL_53:
      Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
      return v22;
    }
    v29 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    ProviderRegistrationInformationFromExtension = _GetProviderRegistrationInformationFromExtension(
                                                     v41,
                                                     *((void **)this + 36),
                                                     &v40);
    v22 = ProviderRegistrationInformationFromExtension;
    if ( ProviderRegistrationInformationFromExtension < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3CD,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\broker\\lib\\wamproviderregistration.cpp",
        (const char *)(unsigned int)ProviderRegistrationInformationFromExtension,
        UserDataCount);
      if ( EventDescriptor.Keyword )
        (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)EventDescriptor.Keyword + 16LL))(EventDescriptor.Keyword);
      if ( *(_QWORD *)&EventDescriptor.Id )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&EventDescriptor.Id + 16LL))(*(_QWORD *)&EventDescriptor.Id);
      v31 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      v32 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v32 + 16LL))(v32);
      }
      goto LABEL_53;
    }
    v47 = 0;
    Keyword = EventDescriptor.Keyword;
    if ( EventDescriptor.Keyword )
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)EventDescriptor.Keyword + 8LL))(EventDescriptor.Keyword);
    v47 = Keyword;
    v34 = Windows::Internal::Security::Authentication::Web::ProviderRegistrationCache::Refresh(
            Keyword,
            *((unsigned int *)this + 6),
            *((_QWORD *)this + 36));
    if ( v34 < 0 )
    {
      v35 = TbLogProvider::Provider();
      if ( *(_DWORD *)v35 > 3u )
      {
        v42 = v34;
        v56 = &v42;
        v57 = 4;
        UserData.Ptr = 0x30B000000LL;
        *(_QWORD *)&UserData.Size = 0;
        v52.Ptr = *((_QWORD *)v35 + 1);
        v52.Size = *(unsigned __int16 *)v52.Ptr;
        v52.Reserved = 2;
        v53 = byte_1801467AD;
        v54 = 57;
        v55 = 1;
        LODWORD(StringRawBuffer) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*((_QWORD *)v35 + 4), (PCEVENT_DESCRIPTOR)&UserData, 0, 0, 3u, &v52);
      }
    }
    v36 = v47;
    if ( v47 )
    {
      v47 = 0;
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v36 + 16LL))(v36);
    }
    if ( Keyword )
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)Keyword + 16LL))(Keyword);
    if ( *(_QWORD *)&EventDescriptor.Id )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&EventDescriptor.Id + 16LL))(*(_QWORD *)&EventDescriptor.Id);
    v37 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v19 = v40;
LABEL_80:
    v40 = 0;
    *a3 = v19;
    Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
    return 0;
  }
  if ( (unsigned int)Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(
                       a1,
                       0) )
  {
    v23 = TbLogProvider::Provider();
    if ( *(_DWORD *)v23 > 2u )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(a1, 0);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        (_DWORD)v23,
        (unsigned int)&byte_1801467E7,
        0,
        v24,
        (__int64)&StringRawBuffer);
    }
  }
  if ( EventDescriptor.Keyword )
    (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)EventDescriptor.Keyword + 16LL))(EventDescriptor.Keyword);
  if ( *(_QWORD *)&EventDescriptor.Id )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&EventDescriptor.Id + 16LL))(*(_QWORD *)&EventDescriptor.Id);
  v25 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = v40;
  if ( v40 )
  {
    v40 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation *))(*(_QWORD *)v26 + 16LL))(v26);
  }
  Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope((Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope *)&TokenHandle);
  return 2148073491LL;
}

```

## disassembly

```asm
0x1800228e0  push    rbx
0x1800228e2  push    rsi
0x1800228e3  push    rdi
0x1800228e4  push    r12
0x1800228e6  push    r13
0x1800228e8  push    r14
0x1800228ea  push    r15
0x1800228ec  sub     rsp, 0E0h
0x1800228f3  mov     rax, cs:__security_cookie
0x1800228fa  xor     rax, rsp
0x1800228fd  mov     [rsp+118h+var_40], rax
0x180022905  mov     r14, r8
0x180022908  mov     rsi, rdx
0x18002290b  mov     rdi, rcx
0x18002290e  test    r8, r8
0x180022911  jnz     short loc_18002293C
0x180022913  mov     rcx, [rsp+118h]; this
0x18002291b  mov     r9d, 80004003h; char *
0x180022921  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180022928  mov     edx, 3A4h; void *
0x18002292d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022932  mov     eax, 80004003h
0x180022937  jmp     loc_18002301E
0x18002293c  call    cs:__imp_WindowsIsStringEmpty
0x180022942  test    eax, eax
0x180022944  jz      short loc_18002296F
0x180022946  mov     rcx, [rsp+118h]; this
0x18002294e  mov     r9d, 80070057h; char *
0x180022954  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x18002295b  mov     edx, 3A5h; void *
0x180022960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022965  mov     eax, 80070057h
0x18002296a  jmp     loc_18002301E
0x18002296f  xor     r13d, r13d
0x180022972  mov     [r14], r13
0x180022975  mov     rcx, rsi; this
0x180022978  call    ?CaptureSessionUserInformation@CallerContext@Web@Authentication@Security@Internal@Windows@@QEAAJXZ; Windows::Internal::Security::Authentication::Web::CallerContext::CaptureSessionUserInformation(void)
0x18002297d  mov     ebx, eax
0x18002297f  test    eax, eax
0x180022981  jns     short loc_1800229A6
0x180022983  mov     rcx, [rsp+118h]; this
0x18002298b  mov     r9d, eax; char *
0x18002298e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180022995  mov     edx, 3A8h; void *
0x18002299a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002299f  mov     eax, ebx
0x1800229a1  jmp     loc_18002301E
0x1800229a6  mov     [rsp+118h+var_C0], r13b
0x1800229ab  mov     [rsp+118h+TokenHandle], r13
0x1800229b0  call    cs:__imp_GetCurrentThread
0x1800229b6  mov     rcx, rax; ThreadHandle
0x1800229b9  lea     r9, [rsp+118h+TokenHandle]; TokenHandle
0x1800229be  mov     edx, 0F01FFh; DesiredAccess
0x1800229c3  mov     r8d, 1; OpenAsSelf
0x1800229c9  call    cs:__imp_OpenThreadToken
0x1800229cf  test    eax, eax
0x1800229d1  jnz     loc_180022A89
0x1800229d7  call    cs:__imp_GetLastError
0x1800229dd  test    eax, eax
0x1800229df  jle     short loc_1800229E9
0x1800229e1  movzx   eax, ax
0x1800229e4  or      eax, 80070000h
0x1800229e9  cmp     eax, 800703F0h
0x1800229ee  jz      loc_180022A89
0x1800229f4  call    cs:__imp_GetLastError
0x1800229fa  mov     ebx, eax
0x1800229fc  test    eax, eax
0x1800229fe  jle     short loc_180022A09
0x180022a00  movzx   ebx, ax
0x180022a03  or      ebx, 80070000h
0x180022a09  test    ebx, ebx
0x180022a0b  jns     short loc_180022A89
0x180022a0d  mov     rcx, [rsp+118h]; this
0x180022a15  mov     r9d, ebx; char *
0x180022a18  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\tokenbroker\\inc"...
0x180022a1f  mov     edx, 1E5h; void *
0x180022a24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a29  mov     rcx, [rsp+118h]; this
0x180022a31  mov     r9d, ebx; char *
0x180022a34  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180022a3b  mov     edx, 3ABh; void *
0x180022a40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a45  nop
0x180022a46  cmp     [rsp+118h+var_C0], 0
0x180022a4b  jz      short loc_180022A6A
0x180022a4d  mov     rdx, [rsp+118h+TokenHandle]; Token
0x180022a52  xor     ecx, ecx; Thread
0x180022a54  call    cs:__imp_SetThreadToken
0x180022a5a  mov     rcx, [rsp+118h]; this
0x180022a62  test    eax, eax
0x180022a64  jz      loc_180023041
0x180022a6a  mov     rax, [rsp+118h+TokenHandle]
0x180022a6f  lea     rcx, [rax-1]
0x180022a73  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180022a77  ja      short loc_180022A82
0x180022a79  mov     rcx, rax; hObject
0x180022a7c  call    cs:__imp_CloseHandle
0x180022a82  mov     eax, ebx
0x180022a84  jmp     loc_18002301E
0x180022a89  call    cs:__imp_RevertToSelf
0x180022a8f  mov     rcx, [rsp+118h]; this
0x180022a97  test    eax, eax
0x180022a99  jz      loc_180023053
0x180022a9f  mov     [rsp+118h+var_C0], 1
0x180022aa4  mov     [rsp+118h+var_E8], r13
0x180022aa9  lea     r8, [rsp+118h+var_E8]; struct Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation **
0x180022aae  mov     edx, [rsi+18h]; unsigned int
0x180022ab1  mov     rcx, rdi; HSTRING
0x180022ab4  call    ?FindRegistrationInfomationWithId@ProviderRegistrationCache@Web@Authentication@Security@Internal@Windows@@SAJPEAUHSTRING__@@KPEAPEAUIWamProviderRegistrationInformation@23456@@Z; Windows::Internal::Security::Authentication::Web::ProviderRegistrationCache::FindRegistrationInfomationWithId(HSTRING__ *,ulong,Windows::Internal::Security::Authentication::Web::IWamProviderRegistrationInformation * *)
0x180022ab9  mov     ebx, eax
0x180022abb  test    eax, eax
0x180022abd  jns     short loc_180022B38
0x180022abf  mov     rcx, [rsp+118h]; this
0x180022ac7  mov     r9d, eax; char *
0x180022aca  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180022ad1  mov     edx, 3B1h; void *
0x180022ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022adb  nop
0x180022adc  mov     rcx, [rsp+118h+var_E8]
0x180022ae1  test    rcx, rcx
0x180022ae4  jz      short loc_180022AF8
0x180022ae6  mov     [rsp+118h+var_E8], r13
0x180022aeb  mov     rax, [rcx]
0x180022aee  mov     rax, [rax+10h]
0x180022af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022af7  nop
0x180022af8  cmp     [rsp+118h+var_C0], 0
0x180022afd  jz      short loc_180022B1C
0x180022aff  mov     rdx, [rsp+118h+TokenHandle]; Token
0x180022b04  xor     ecx, ecx; Thread
0x180022b06  call    cs:__imp_SetThreadToken
0x180022b0c  mov     rcx, [rsp+118h]; this
0x180022b14  test    eax, eax
0x180022b16  jz      loc_180023065
0x180022b1c  mov     rcx, [rsp+118h+TokenHandle]; hObject
0x180022b21  lea     rax, [rcx-1]
0x180022b25  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022b29  ja      short loc_180022B31
0x180022b2b  call    cs:__imp_CloseHandle
0x180022b31  mov     eax, ebx
0x180022b33  jmp     loc_18002301E
0x180022b38  mov     rax, [rsp+118h+var_E8]
0x180022b3d  test    rax, rax
0x180022b40  jnz     loc_180023004
0x180022b46  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x180022b4b  mov     r10, rax
0x180022b4e  mov     ecx, [rax]
0x180022b50  cmp     ecx, 5
0x180022b53  jbe     loc_180022BF9
0x180022b59  mov     dword ptr [rsp+118h+EventDescriptor.Id], 0B000000h
0x180022b61  movzx   ecx, cs:word_18014681B
0x180022b68  mov     dword ptr [rsp+118h+EventDescriptor.Level], ecx
0x180022b6c  mov     [rsp+118h+EventDescriptor.Keyword], r13
0x180022b71  mov     rcx, [rax+8]
0x180022b75  mov     [rsp+118h+var_A0.Ptr], rcx
0x180022b7a  movzx   eax, word ptr [rcx]
0x180022b7d  mov     [rsp+118h+var_A0.Size], eax
0x180022b84  mov     dword ptr [rsp+118h+var_A0.0Ch], 2
0x180022b8f  lea     rax, byte_180146825
0x180022b96  mov     [rsp+118h+var_90], rax
0x180022b9e  mov     [rsp+118h+var_88], 30h ; '0'
0x180022ba9  mov     [rsp+118h+var_84], 1
0x180022bb4  lea     r15, _TraceLoggingMetadataEnd
0x180022bbb  mov     rax, r15
0x180022bbe  lea     r12, _TraceLoggingMetadata
0x180022bc5  sub     eax, r12d
0x180022bc8  mov     [rsp+118h+var_D8], eax
0x180022bcc  mov     eax, [rsp+118h+var_D8]
0x180022bd0  lea     rax, [rsp+118h+var_A0]
0x180022bd5  mov     [rsp+118h+UserData], rax; UserData
0x180022bda  mov     [rsp+118h+UserDataCount], 2; UserDataCount
0x180022be2  xor     r9d, r9d; RelatedActivityId
0x180022be5  xor     r8d, r8d; ActivityId
0x180022be8  lea     rdx, [rsp+118h+EventDescriptor]; EventDescriptor
0x180022bed  mov     rcx, [r10+20h]; RegHandle
0x180022bf1  call    cs:__imp_EventWriteTransfer
0x180022bf7  jmp     short loc_180022C07
0x180022bf9  lea     r15, _TraceLoggingMetadataEnd
0x180022c00  lea     r12, _TraceLoggingMetadata
0x180022c07  mov     [rsp+118h+var_E0], r13
0x180022c0c  xorps   xmm0, xmm0
0x180022c0f  movdqu  xmmword ptr [rsp+118h+EventDescriptor.Id], xmm0
0x180022c15  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_8db1653d5e5b1978f9d2fa3b5818f431_@@_NPEAUIApplicationExtension@StateRepository@Internal@Windows@@@std@@6B@; const std::_Func_impl_no_alloc<_lambda_8db1653d5e5b1978f9d2fa3b5818f431_,bool,Windows::Internal::StateRepository::IApplicationExtension *>::`vftable'
0x180022c1c  mov     [rsp+118h+var_80.Ptr], rax
0x180022c24  mov     qword ptr [rsp+118h+var_80.Size], rdi
0x180022c2c  lea     rax, [rsp+118h+var_80]
0x180022c34  mov     [rsp+118h+var_48], rax
0x180022c3c  lea     r9, [rsp+118h+var_E0]
0x180022c41  mov     r8, rsi
0x180022c44  lea     rdx, [rsp+118h+var_80]
0x180022c4c  lea     rcx, [rsp+118h+EventDescriptor]
0x180022c51  call    ?_FindExtension@ExtensionRegistrationResolver@@AEAAJV?$function@$$A6A_NPEAUIApplicationExtension@StateRepository@Internal@Windows@@@Z@std@@AEBVCallerContext@Web@Authentication@Security@Internal@Windows@@PEAPEAUIApplicationExtension@StateRepository@89@@Z; ExtensionRegistrationResolver::_FindExtension(std::function<bool (Windows::Internal::StateRepository::IApplicationExtension *)>,Windows::Internal::Security::Authentication::Web::CallerContext const &,Windows::Internal::StateRepository::IApplicationExtension * *)
0x180022c56  mov     ebx, eax
0x180022c58  cmp     eax, 80090013h
0x180022c5d  jnz     loc_180022D27
0x180022c63  xor     edx, edx
0x180022c65  mov     rcx, rdi
0x180022c68  call    ?GetBuiltInProviderType@PluginManager@TokenBroker@Authentication@Security@Internal@Windows@@SA?AW4BuiltInProviderType@23456@PEAUHSTRING__@@0@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginManager::GetBuiltInProviderType(HSTRING__ *,HSTRING__ *)
0x180022c6d  test    eax, eax
0x180022c6f  jz      short loc_180022CAD
0x180022c71  call    ?Provider@TbLogProvider@@SAPEBU_tlgProvider_t@@XZ; TbLogProvider::Provider(void)
0x180022c76  mov     rbx, rax
0x180022c79  mov     edx, [rax]
0x180022c7b  cmp     edx, 2
0x180022c7e  jbe     short loc_180022CAD
0x180022c80  xor     edx, edx; length
0x180022c82  mov     rcx, rdi; string
0x180022c85  call    cs:__imp_WindowsGetStringRawBuffer
0x180022c8b  mov     [rsp+118h+var_D0], rax
0x180022c90  lea     rax, [rsp+118h+var_D0]
0x180022c95  mov     qword ptr [rsp+118h+UserDataCount], rax
0x180022c9a  xor     r8d, r8d
0x180022c9d  lea     rdx, byte_1801467E7
0x180022ca4  mov     rcx, rbx
0x180022ca7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180022cac  nop
0x180022cad  mov     rcx, [rsp+118h+EventDescriptor.Keyword]
0x180022cb2  test    rcx, rcx
0x180022cb5  jz      short loc_180022CC4
0x180022cb7  mov     rax, [rcx]
0x180022cba  mov     rax, [rax+10h]
0x180022cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cc3  nop
0x180022cc4  mov     rcx, qword ptr [rsp+118h+EventDescriptor.Id]
0x180022cc9  test    rcx, rcx
0x180022ccc  jz      short loc_180022CDB
0x180022cce  mov     rax, [rcx]
0x180022cd1  mov     rax, [rax+10h]
0x180022cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cda  nop
0x180022cdb  mov     rcx, [rsp+118h+var_E0]
0x180022ce0  test    rcx, rcx
0x180022ce3  jz      short loc_180022CF7
0x180022ce5  mov     [rsp+118h+var_E0], r13
0x180022cea  mov     rax, [rcx]
0x180022ced  mov     rax, [rax+10h]
0x180022cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cf6  nop
0x180022cf7  mov     rcx, [rsp+118h+var_E8]
0x180022cfc  test    rcx, rcx
0x180022cff  jz      short loc_180022D13
0x180022d01  mov     [rsp+118h+var_E8], r13
0x180022d06  mov     rdx, [rcx]
0x180022d09  mov     rax, [rdx+10h]
0x180022d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d12  nop
0x180022d13  lea     rcx, [rsp+118h+TokenHandle]; this
0x180022d18  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x180022d1d  mov     eax, 80090013h
0x180022d22  jmp     loc_18002301E
0x180022d27  test    ebx, ebx
0x180022d29  jns     loc_180022DC3
0x180022d2f  mov     rcx, [rsp+118h]; this
0x180022d37  mov     r9d, ebx; char *
0x180022d3a  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\tokenbroker\\bro"...
0x180022d41  mov     edx, 3CAh; void *
0x180022d46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022d4b  nop
0x180022d4c  mov     rcx, [rsp+118h+EventDescriptor.Keyword]
0x180022d51  test    rcx, rcx
0x180022d54  jz      short loc_180022D63
0x180022d56  mov     rax, [rcx]
0x180022d59  mov     rax, [rax+10h]
0x180022d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d62  nop
0x180022d63  mov     rcx, qword ptr [rsp+118h+EventDescriptor.Id]
0x180022d68  test    rcx, rcx
0x180022d6b  jz      short loc_180022D7A
0x180022d6d  mov     rax, [rcx]
0x180022d70  mov     rax, [rax+10h]
0x180022d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d79  nop
0x180022d7a  mov     rcx, [rsp+118h+var_E0]
0x180022d7f  test    rcx, rcx
0x180022d82  jz      short loc_180022D96
0x180022d84  mov     [rsp+118h+var_E0], r13
0x180022d89  mov     rax, [rcx]
0x180022d8c  mov     rax, [rax+10h]
0x180022d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d95  nop
0x180022d96  mov     rcx, [rsp+118h+var_E8]
0x180022d9b  test    rcx, rcx
0x180022d9e  jz      short loc_180022DB2
0x180022da0  mov     [rsp+118h+var_E8], r13
0x180022da5  mov     rax, [rcx]
0x180022da8  mov     rax, [rax+10h]
0x180022dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022db1  nop
0x180022db2  lea     rcx, [rsp+118h+TokenHandle]; this
0x180022db7  call    ??1SuspendImpersonationScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x180022dbc  mov     eax, ebx
0x180022dbe  jmp     loc_18002301E
0x180022dc3  mov     rcx, [rsp+118h+var_E8]
0x180022dc8  test    rcx, rcx
0x180022dcb  jz      short loc_180022DDF
0x180022dcd  mov     [rsp+118h+var_E8], r13
0x180022dd2  mov     rax, [rcx]
0x180022dd5  mov     rax, [rax+10h]
0x180022dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dde  nop
  ... truncated ...
```
