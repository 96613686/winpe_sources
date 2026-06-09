# UserHelpers::Impersonator::Initialize(Windows::System::IUser *)

- ea: `0x18004e9fc`
- end: `0x18004ef32`
- name: `?Initialize@Impersonator@UserHelpers@@AEAAXPEAUIUser@System@Windows@@@Z`
- size: `1334`
- prototype: `void __fastcall(UserHelpers::Impersonator *__hidden this, struct Windows::System::IUser *)`
- caller_count: `2`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004d638`
- `0x18004d744`

## callees

- `0x18001dac0`
- `0x18004e9c4`
- `0x18004e9fc`
- `0x18004ef38`
- `0x18004ef8c`
- `0x18004f024`
- `0x18004f114`
- `0x18004f5d0`
- `0x18012eb38`
- `0x1801593b0`
- `0x18015ae78`
- `0x180201e50`
- `0x180204c10`
- `0x18022cc70`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ec7d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ec7d`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004eb57`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18004eb57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004eb4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004eb4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ea3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004ea3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ef07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ef27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ef07`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ef27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ea7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ea7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ea9b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004ea9b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004ebf2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004ee20`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004ebf2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18004ee20`
- `ntdll!RtlIsMultiSessionSku` at `0x18004eb69`
- `ntdll!RtlIsMultiSessionSku` at `0x18004eb69`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18004eb77`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18004eb77`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x18004edd1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQuerySessionUserToken` at `0x18004edd1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x18004ee5f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetImpersonationTokenForContext` at `0x18004ee5f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18004ed5f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetConstrainedUserToken` at `0x18004ed5f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004eba1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18004eba1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18004eaf0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18004ecf3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18004eaf0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18004ecf3`

## string_xrefs

- `0x18004ec87`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ec9c`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ecb1`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ecc6`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ecdb`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ed04`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ed70`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ed82`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ee70`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ee82`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ee9a`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004eeac`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004eee3`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004eef5`: `shellcommon\shell\Common\Helpers\UserHelpers.h`
- `0x18004ef12`: `shellcommon\shell\Common\Helpers\UserHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall UserHelpers::Impersonator::Initialize(
        UserHelpers::Impersonator *this,
        struct Windows::System::IUser *a2)
{
  HANDLE CurrentProcess; // rax
  bool *v5; // r8
  int IsProcessAppContainer; // eax
  wil::details::in1diag3 *v7; // rcx
  HRESULT v8; // eax
  int ActivationFactory; // eax
  _QWORD *v10; // rsi
  int v11; // eax
  void *v12; // rdx
  char *v13; // rdi
  int v14; // eax
  _QWORD *v15; // rbx
  DWORD CurrentProcessId; // eax
  const char *v17; // r9
  int UserToken; // eax
  const char *v19; // r9
  int UserContext; // eax
  const char *v21; // r9
  int ConstrainedUserToken; // eax
  const char *v23; // r9
  int SessionUserToken; // eax
  const char *v25; // r9
  const char *v26; // r9
  int ImpersonationTokenForContext; // eax
  TOKEN_TYPE TokenType; // [rsp+20h] [rbp-60h]
  TOKEN_TYPE TokenTypea; // [rsp+20h] [rbp-60h]
  _BYTE v30[4]; // [rsp+30h] [rbp-50h] BYREF
  DWORD pSessionId; // [rsp+34h] [rbp-4Ch] BYREF
  HANDLE hExistingToken; // [rsp+38h] [rbp-48h] BYREF
  HANDLE v33; // [rsp+40h] [rbp-40h] BYREF
  __int64 v34; // [rsp+48h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  HSTRING string; // [rsp+70h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::operator=();
  if ( a2 )
  {
    v30[0] = 0;
    CurrentProcess = GetCurrentProcess();
    IsProcessAppContainer = CallerIdentity::IsProcessAppContainer(CurrentProcess, v30, v5);
    v7 = retaddr;
    if ( IsProcessAppContainer >= 0 )
    {
      wil::open_current_access_token(&hObject);
      v34 = 0;
      string = 0;
      v8 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
      if ( v8 >= 0 )
      {
        ActivationFactory = RoGetActivationFactory(string, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v34);
        if ( ActivationFactory < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x112,
            (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
            (const char *)(unsigned int)ActivationFactory,
            TokenType);
        v10 = (_QWORD *)((char *)this + 16);
        v11 = (*(__int64 (__fastcall **)(__int64, struct Windows::System::IUser *, char *))(*(_QWORD *)v34 + 136LL))(
                v34,
                a2,
                (char *)this + 16);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x113,
            (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
            (const char *)(unsigned int)v11,
            TokenType);
        v13 = (char *)hObject;
        if ( !UserHelpers::IsSystemAccount((UserHelpers *)hObject, v12) )
        {
          v33 = 0;
          v14 = UMgrQueryUserContext(0, &v33);
          if ( v14 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x11B,
              (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
              (const char *)(unsigned int)v14,
              TokenType);
          if ( v33 == (HANDLE)*v10 && (HANDLE *)((char *)this + 8) != &hObject )
          {
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              (char *)this + 8,
              v13);
            v13 = 0;
            hObject = 0;
          }
        }
        v15 = (_QWORD *)((char *)this + 8);
        if ( ((*v15 + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        {
          if ( v30[0] )
          {
            if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x126,
                (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                v21);
            *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v15;
            hstringHeader.Reserved.Reserved2[16] = 1;
            ConstrainedUserToken = UMgrGetConstrainedUserToken(0, *v10, 0, &hstringHeader.Reserved.Reserved2[8]);
            if ( ConstrainedUserToken < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x127,
                (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                (const char *)(unsigned int)ConstrainedUserToken,
                TokenType);
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
          }
          else
          {
            pSessionId = 0;
            CurrentProcessId = GetCurrentProcessId();
            if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
              wil::details::in1diag3::_Throw_GetLastError(
                retaddr,
                (void *)0x12D,
                (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                v17);
            if ( (unsigned __int8)RtlIsMultiSessionSku(retaddr)
              && pSessionId == (unsigned int)RtlGetCurrentServiceSessionId() )
            {
              hExistingToken = 0;
              hstringHeader.Reserved.Reserved1 = &hExistingToken;
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
              hstringHeader.Reserved.Reserved2[16] = 1;
              UserToken = UMgrQueryUserToken(*v10, &hstringHeader.Reserved.Reserved2[8]);
              if ( UserToken < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x134,
                  (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                  (const char *)(unsigned int)UserToken,
                  TokenType);
              if ( hstringHeader.Reserved.Reserved2[16] )
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  hstringHeader.Reserved.Reserved1,
                  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]);
              *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v15;
              hstringHeader.Reserved.Reserved2[16] = 1;
              if ( !DuplicateTokenEx(
                      hExistingToken,
                      0x2000000u,
                      0,
                      SecurityImpersonation,
                      TokenImpersonation,
                      (PHANDLE)&hstringHeader.Reserved.Reserved2[8]) )
                wil::details::in1diag3::_Throw_GetLastError(
                  retaddr,
                  (void *)0x135,
                  (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                  v19);
              if ( hstringHeader.Reserved.Reserved2[16] )
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                  hstringHeader.Reserved.Reserved1,
                  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]);
              if ( (char *)hExistingToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                CloseHandle(hExistingToken);
            }
            else
            {
              v33 = 0;
              if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x141,
                  (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                  v23);
              hstringHeader.Reserved.Reserved1 = &v33;
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
              hstringHeader.Reserved.Reserved2[16] = 1;
              SessionUserToken = UMgrQuerySessionUserToken(pSessionId, &hstringHeader.Reserved.Reserved2[8]);
              if ( SessionUserToken < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x142,
                  (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                  (const char *)(unsigned int)SessionUserToken,
                  TokenType);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
              hExistingToken = 0;
              hstringHeader.Reserved.Reserved1 = &hExistingToken;
              *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
              hstringHeader.Reserved.Reserved2[16] = 1;
              if ( !DuplicateTokenEx(
                      v33,
                      0x2000000u,
                      0,
                      SecurityImpersonation,
                      TokenImpersonation,
                      (PHANDLE)&hstringHeader.Reserved.Reserved2[8]) )
                wil::details::in1diag3::_Throw_GetLastError(
                  retaddr,
                  (void *)0x145,
                  (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                  v25);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
              if ( !(unsigned __int8)IsUMgrGetImpersonationTokenForContextPresent() )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x146,
                  (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                  v26);
              *(_OWORD *)&hstringHeader.Reserved.Reserved1 = (unsigned __int64)v15;
              hstringHeader.Reserved.Reserved2[16] = 1;
              ImpersonationTokenForContext = UMgrGetImpersonationTokenForContext(
                                               hExistingToken,
                                               *v10,
                                               &hstringHeader.Reserved.Reserved2[8]);
              if ( ImpersonationTokenForContext < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x147,
                  (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
                  (const char *)(unsigned int)ImpersonationTokenForContext,
                  TokenTypea);
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&hstringHeader);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
            }
          }
        }
        if ( v34 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          CloseHandle(v13);
        return;
      }
      RaiseException(v8, 1u, 0, 0);
    }
    wil::details::in1diag3::Throw_Hr(
      v7,
      (void *)0x10E,
      (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
      (const char *)(unsigned int)IsProcessAppContainer,
      TokenType);
  }
  UserContext = UMgrQueryUserContext(0, (char *)this + 16);
  if ( UserContext < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x108,
      (unsigned int)"shellcommon\\shell\\Common\\Helpers\\UserHelpers.h",
      (const char *)(unsigned int)UserContext,
      TokenType);
  wil::open_current_access_token(&v34);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    (char *)this + 8,
    &v34);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v34);
}

```

## disassembly

```asm
0x18004e9fc  mov     [rsp-28h+arg_10], rbx
0x18004ea01  push    rbp
0x18004ea02  push    rsi
0x18004ea03  push    rdi
0x18004ea04  push    r14
0x18004ea06  push    r15
0x18004ea08  mov     rbp, rsp
0x18004ea0b  sub     rsp, 80h
0x18004ea12  mov     rax, cs:__security_cookie
0x18004ea19  xor     rax, rsp
0x18004ea1c  mov     [rbp+var_8], rax
0x18004ea20  mov     rdi, rdx
0x18004ea23  mov     rbx, rcx
0x18004ea26  xor     r15d, r15d
0x18004ea29  call    ??4?$com_ptr_t@UIUser@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEAV01@PEAUIUser@System@Windows@@@Z; wil::com_ptr_t<Windows::System::IUser,wil::err_exception_policy>::operator=(Windows::System::IUser *)
0x18004ea2e  test    rdi, rdi
0x18004ea31  jz      loc_18004ECED
0x18004ea37  mov     [rbp+var_50], r15b
0x18004ea3b  call    cs:__imp_GetCurrentProcess
0x18004ea41  mov     rcx, rax; ProcessHandle
0x18004ea44  lea     rdx, [rbp+var_50]; void *
0x18004ea48  call    ?IsProcessAppContainer@CallerIdentity@@YAJPEAXPEA_N@Z; CallerIdentity::IsProcessAppContainer(void *,bool *)
0x18004ea4d  mov     rcx, [rbp+28h]
0x18004ea51  test    eax, eax
0x18004ea53  js      loc_18004EC84
0x18004ea59  lea     rcx, [rbp+hObject]
0x18004ea5d  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x18004ea62  nop
0x18004ea63  mov     [rbp+var_38], r15
0x18004ea67  mov     [rbp+string], r15
0x18004ea6b  lea     r9, [rbp+string]; string
0x18004ea6f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004ea73  lea     edx, [r15+23h]; length
0x18004ea77  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x18004ea7e  call    cs:__imp_WindowsCreateStringReference
0x18004ea84  test    eax, eax
0x18004ea86  js      loc_18004EC71
0x18004ea8c  lea     r8, [rbp+var_38]
0x18004ea90  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x18004ea97  mov     rcx, [rbp+string]
0x18004ea9b  call    cs:__imp_RoGetActivationFactory
0x18004eaa1  mov     rcx, [rbp+28h]; this
0x18004eaa5  test    eax, eax
0x18004eaa7  js      loc_18004EC99
0x18004eaad  mov     rcx, [rbp+var_38]
0x18004eab1  lea     rsi, [rbx+10h]
0x18004eab5  mov     rax, [rcx]
0x18004eab8  mov     r8, rsi
0x18004eabb  mov     rdx, rdi
0x18004eabe  mov     rax, [rax+88h]
0x18004eac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eaca  mov     rcx, [rbp+28h]; this
0x18004eace  test    eax, eax
0x18004ead0  js      loc_18004ECAE
0x18004ead6  mov     rdi, [rbp+hObject]
0x18004eada  mov     rcx, rdi; this
0x18004eadd  call    ?IsSystemAccount@UserHelpers@@YA_NPEAX@Z; UserHelpers::IsSystemAccount(void *)
0x18004eae2  test    al, al
0x18004eae4  jnz     short loc_18004EB27
0x18004eae6  mov     [rbp+var_40], r15
0x18004eaea  lea     rdx, [rbp+var_40]
0x18004eaee  xor     ecx, ecx
0x18004eaf0  call    cs:__imp_UMgrQueryUserContext
0x18004eaf6  mov     rcx, [rbp+28h]; this
0x18004eafa  test    eax, eax
0x18004eafc  js      loc_18004ECC3
0x18004eb02  mov     rax, [rsi]
0x18004eb05  cmp     [rbp+var_40], rax
0x18004eb09  jnz     short loc_18004EB27
0x18004eb0b  lea     rcx, [rbx+8]
0x18004eb0f  lea     rax, [rbp+hObject]
0x18004eb13  cmp     rcx, rax
0x18004eb16  jz      short loc_18004EB27
0x18004eb18  mov     rdx, rdi
0x18004eb1b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004eb20  mov     edi, r15d
0x18004eb23  mov     [rbp+hObject], r15
0x18004eb27  add     rbx, 8
0x18004eb2b  mov     rax, [rbx]
0x18004eb2e  inc     rax
0x18004eb31  test    rax, 0FFFFFFFFFFFFFFFEh
0x18004eb37  jnz     loc_18004EC2A
0x18004eb3d  cmp     [rbp+var_50], r15b
0x18004eb41  jnz     loc_18004ED3A
0x18004eb47  mov     [rbp+pSessionId], r15d
0x18004eb4b  call    cs:__imp_GetCurrentProcessId
0x18004eb51  mov     ecx, eax; dwProcessId
0x18004eb53  lea     rdx, [rbp+pSessionId]; pSessionId
0x18004eb57  call    cs:__imp_ProcessIdToSessionId
0x18004eb5d  mov     rcx, [rbp+28h]; this
0x18004eb61  test    eax, eax
0x18004eb63  jz      loc_18004EEE3
0x18004eb69  call    cs:__imp_RtlIsMultiSessionSku
0x18004eb6f  test    al, al
0x18004eb71  jz      loc_18004EDA5
0x18004eb77  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18004eb7d  cmp     [rbp+pSessionId], eax
0x18004eb80  jnz     loc_18004EDA5
0x18004eb86  mov     [rbp+hExistingToken], r15
0x18004eb8a  lea     rax, [rbp+hExistingToken]
0x18004eb8e  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18004eb92  mov     qword ptr [rbp+hstringHeader.Reserved+8], r15
0x18004eb96  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18004eb9a  lea     rdx, [rbp+hstringHeader.Reserved+8]
0x18004eb9e  mov     rcx, [rsi]
0x18004eba1  call    cs:__imp_UMgrQueryUserToken
0x18004eba7  mov     rcx, [rbp+28h]; this
0x18004ebab  test    eax, eax
0x18004ebad  js      loc_18004ECD8
0x18004ebb3  cmp     byte ptr [rbp+hstringHeader.Reserved+10h], r15b
0x18004ebb7  jz      short loc_18004EBC6
0x18004ebb9  mov     rdx, qword ptr [rbp+hstringHeader.Reserved+8]
0x18004ebbd  mov     rcx, qword ptr [rbp+hstringHeader.Reserved]
0x18004ebc1  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004ebc6  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x18004ebca  mov     qword ptr [rbp+hstringHeader.Reserved+8], r15
0x18004ebce  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18004ebd2  lea     rax, [rbp+hstringHeader.Reserved+8]
0x18004ebd6  mov     [rsp+80h+phNewToken], rax; phNewToken
0x18004ebdb  mov     r9d, 2; ImpersonationLevel
0x18004ebe1  mov     [rsp+80h+TokenType], r9d; TokenType
0x18004ebe6  xor     r8d, r8d; lpTokenAttributes
0x18004ebe9  mov     edx, 2000000h; dwDesiredAccess
0x18004ebee  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x18004ebf2  call    cs:__imp_DuplicateTokenEx
0x18004ebf8  mov     rcx, [rbp+28h]; this
0x18004ebfc  test    eax, eax
0x18004ebfe  jz      loc_18004EEF5
0x18004ec04  cmp     byte ptr [rbp+hstringHeader.Reserved+10h], r15b
0x18004ec08  jz      short loc_18004EC18
0x18004ec0a  mov     rdx, qword ptr [rbp+hstringHeader.Reserved+8]
0x18004ec0e  mov     rcx, qword ptr [rbp+hstringHeader.Reserved]
0x18004ec12  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18004ec17  nop
0x18004ec18  mov     rcx, [rbp+hExistingToken]; hObject
0x18004ec1c  lea     rax, [rcx-1]
0x18004ec20  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004ec24  jbe     loc_18004EF07
0x18004ec2a  mov     rcx, [rbp+var_38]
0x18004ec2e  test    rcx, rcx
0x18004ec31  jz      short loc_18004EC40
0x18004ec33  mov     rax, [rcx]
0x18004ec36  mov     rax, [rax+10h]
0x18004ec3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ec3f  nop
0x18004ec40  lea     rax, [rdi-1]
0x18004ec44  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004ec48  jbe     loc_18004EF24
0x18004ec4e  mov     rcx, [rbp+var_8]
0x18004ec52  xor     rcx, rsp; StackCookie
0x18004ec55  call    __security_check_cookie
0x18004ec5a  mov     rbx, [rsp+80h+arg_10]
0x18004ec62  add     rsp, 80h
0x18004ec69  pop     r15
0x18004ec6b  pop     r14
0x18004ec6d  pop     rdi
0x18004ec6e  pop     rsi
0x18004ec6f  pop     rbp
0x18004ec70  retn
0x18004ec71  xor     r9d, r9d; lpArguments
0x18004ec74  xor     r8d, r8d; nNumberOfArguments
0x18004ec77  lea     edx, [r9+1]; dwExceptionFlags
0x18004ec7b  mov     ecx, eax; dwExceptionCode
0x18004ec7d  call    cs:__imp_RaiseException
0x18004ec83  nop
0x18004ec84  mov     r9d, eax; char *
0x18004ec87  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ec8e  mov     edx, 10Eh; void *
0x18004ec93  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ec99  mov     r9d, eax; char *
0x18004ec9c  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004eca3  mov     edx, 112h; void *
0x18004eca8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ecae  mov     r9d, eax; char *
0x18004ecb1  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ecb8  mov     edx, 113h; void *
0x18004ecbd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ecc3  mov     r9d, eax; char *
0x18004ecc6  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004eccd  mov     edx, 11Bh; void *
0x18004ecd2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ecd8  mov     r9d, eax; char *
0x18004ecdb  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ece2  mov     edx, 134h; void *
0x18004ece7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eced  lea     rdx, [rbx+10h]
0x18004ecf1  xor     ecx, ecx
0x18004ecf3  call    cs:__imp_UMgrQueryUserContext
0x18004ecf9  test    eax, eax
0x18004ecfb  jns     short loc_18004ED16
0x18004ecfd  mov     rcx, [rbp+28h]; this
0x18004ed01  mov     r9d, eax; char *
0x18004ed04  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ed0b  mov     edx, 108h; void *
0x18004ed10  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ed16  lea     rcx, [rbp+var_38]
0x18004ed1a  call    ?open_current_access_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@KW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token(ulong,wil::OpenThreadTokenAs)
0x18004ed1f  lea     rcx, [rbx+8]
0x18004ed23  lea     rdx, [rbp+var_38]
0x18004ed27  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18004ed2c  lea     rcx, [rbp+var_38]
0x18004ed30  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004ed35  jmp     loc_18004EC4E
0x18004ed3a  mov     r14, [rbp+28h]
0x18004ed3e  call    IsUMgrGetImpersonationTokenForContextPresent
0x18004ed43  test    al, al
0x18004ed45  jz      short loc_18004ED82
0x18004ed47  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x18004ed4b  mov     qword ptr [rbp+hstringHeader.Reserved+8], r15
0x18004ed4f  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18004ed53  lea     r9, [rbp+hstringHeader.Reserved+8]
0x18004ed57  xor     r8d, r8d
0x18004ed5a  mov     rdx, [rsi]
0x18004ed5d  xor     ecx, ecx
0x18004ed5f  call    cs:__imp_UMgrGetConstrainedUserToken
0x18004ed65  mov     rcx, [rbp+28h]; this
0x18004ed69  test    eax, eax
0x18004ed6b  jns     short loc_18004ED97
0x18004ed6d  mov     r9d, eax; char *
0x18004ed70  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ed77  mov     edx, 127h; void *
0x18004ed7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ed82  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ed89  mov     edx, 126h; void *
0x18004ed8e  mov     rcx, r14; this
0x18004ed91  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004ed97  lea     rcx, [rbp+hstringHeader]
0x18004ed9b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004eda0  jmp     loc_18004EC2A
0x18004eda5  mov     [rbp+var_40], r15
0x18004eda9  mov     r14, [rbp+28h]
0x18004edad  call    IsUMgrGetImpersonationTokenForContextPresent
0x18004edb2  test    al, al
0x18004edb4  jz      loc_18004EE82
0x18004edba  lea     rax, [rbp+var_40]
0x18004edbe  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18004edc2  mov     qword ptr [rbp+hstringHeader.Reserved+8], r15
0x18004edc6  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18004edca  lea     rdx, [rbp+hstringHeader.Reserved+8]
0x18004edce  mov     ecx, [rbp+pSessionId]
0x18004edd1  call    cs:__imp_UMgrQuerySessionUserToken
0x18004edd7  mov     rcx, [rbp+28h]; this
0x18004eddb  test    eax, eax
0x18004eddd  js      loc_18004EE97
0x18004ede3  lea     rcx, [rbp+hstringHeader]
0x18004ede7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004edec  mov     [rbp+hExistingToken], r15
0x18004edf0  lea     rax, [rbp+hExistingToken]
0x18004edf4  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18004edf8  mov     qword ptr [rbp+hstringHeader.Reserved+8], r15
0x18004edfc  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18004ee00  lea     rax, [rbp+hstringHeader.Reserved+8]
0x18004ee04  mov     [rsp+80h+phNewToken], rax; phNewToken
0x18004ee09  mov     r9d, 2; ImpersonationLevel
0x18004ee0f  mov     [rsp+80h+TokenType], r9d; int
0x18004ee14  xor     r8d, r8d; lpTokenAttributes
0x18004ee17  mov     edx, 2000000h; dwDesiredAccess
0x18004ee1c  mov     rcx, [rbp+var_40]; hExistingToken
0x18004ee20  call    cs:__imp_DuplicateTokenEx
0x18004ee26  mov     rcx, [rbp+28h]; this
0x18004ee2a  test    eax, eax
0x18004ee2c  jz      loc_18004EF12
0x18004ee32  lea     rcx, [rbp+hstringHeader]
0x18004ee36  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004ee3b  mov     r14, [rbp+28h]
0x18004ee3f  call    IsUMgrGetImpersonationTokenForContextPresent
0x18004ee44  test    al, al
0x18004ee46  jz      short loc_18004EEAC
0x18004ee48  mov     qword ptr [rbp+hstringHeader.Reserved], rbx
0x18004ee4c  mov     qword ptr [rbp+hstringHeader.Reserved+8], r15
0x18004ee50  mov     byte ptr [rbp+hstringHeader.Reserved+10h], 1
0x18004ee54  lea     r8, [rbp+hstringHeader.Reserved+8]
0x18004ee58  mov     rdx, [rsi]
0x18004ee5b  mov     rcx, [rbp+hExistingToken]
0x18004ee5f  call    cs:__imp_UMgrGetImpersonationTokenForContext
0x18004ee65  mov     rcx, [rbp+28h]; this
0x18004ee69  test    eax, eax
0x18004ee6b  jns     short loc_18004EEC1
0x18004ee6d  mov     r9d, eax; char *
0x18004ee70  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ee77  mov     edx, 147h; void *
0x18004ee7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004ee82  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004ee89  mov     edx, 141h; void *
0x18004ee8e  mov     rcx, r14; this
0x18004ee91  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004ee97  mov     r9d, eax; char *
0x18004ee9a  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004eea1  mov     edx, 142h; void *
0x18004eea6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004eeac  lea     r8, aShellcommonShe_191; "shellcommon\\shell\\Common\\Helpers\\Us"...
0x18004eeb3  mov     edx, 146h; void *
0x18004eeb8  mov     rcx, r14; this
0x18004eebb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004eec1  lea     rcx, [rbp+hstringHeader]
0x18004eec5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004eeca  nop
0x18004eecb  lea     rcx, [rbp+hExistingToken]
0x18004eecf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004eed4  nop
  ... truncated ...
```
