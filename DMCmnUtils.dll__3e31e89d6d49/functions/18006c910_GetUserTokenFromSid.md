# GetUserTokenFromSid

- ea: `0x18006c910`
- end: `0x18006cdcc`
- name: `GetUserTokenFromSid`
- size: `1212`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006a730`
- `0x18006a860`

## callees

- `0x1800527b4`
- `0x180052ac4`
- `0x180069ae8`
- `0x18006c710`
- `0x18006c7c8`
- `0x18006c910`
- `0x18006d88c`
- `0x18006d924`
- `0x1800b2244`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c960`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006caaf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006cc23`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006cccc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006c960`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006caaf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006cc23`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006cccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c9a9`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006c999`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18006c999`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c988`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006c988`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006caf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cc3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006caf5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cc3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd53`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cc4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cd81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cd90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cac8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cade`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cc4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cc65`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cd81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006cd90`
- `ntdll!RtlNtStatusToDosError` at `0x18006cd35`
- `ntdll!RtlNtStatusToDosError` at `0x18006cd35`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006ca98`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006cc08`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006ccb1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006ca98`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006cc08`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006ccb1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006cda5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18006cda5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18006ca62`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18006ca62`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18006ca0c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18006ca0c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18006cbd2`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18006cc7b`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18006cbd2`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18006cc7b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006cba1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18006cba1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006cb70`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18006cb70`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromSid(__int64 a1, HANDLE *a2, DWORD *a3)
{
  PSID v6; // rdi
  signed int CurrentUserToken; // ebx
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  int v10; // r15d
  ULONG SessionId; // ecx
  int UserSidFromToken; // eax
  void *v13; // rcx
  NTSTATUS v14; // eax
  signed int v15; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-20h] BYREF
  PSID Sid; // [rsp+38h] [rbp-18h]
  _QWORD *v19; // [rsp+40h] [rbp-10h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+48h] [rbp-8h] BYREF
  DWORD pCount; // [rsp+98h] [rbp+48h] BYREF
  int v22; // [rsp+A0h] [rbp+50h] BYREF
  void *phToken; // [rsp+A8h] [rbp+58h] BYREF

  ppSessionInfo = 0;
  pCount = 0;
  phToken = 0;
  v6 = 0;
  Sid = 0;
  StringSid = 0;
  *a2 = 0;
  if ( a3 )
    *a3 = -1;
  if ( !(unsigned int)_o__wcsicmp(a1, L"S-1-5-18") )
  {
    CurrentUserToken = GetCurrentUserToken(&phToken);
    if ( CurrentUserToken < 0 )
      goto LABEL_57;
    if ( !a3 || (CurrentProcessId = GetCurrentProcessId(), ProcessIdToSessionId(CurrentProcessId, a3)) )
    {
      *a2 = phToken;
      phToken = 0;
      goto LABEL_51;
    }
    goto LABEL_7;
  }
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
    {
      v22 = 0;
      v19 = 0;
      CurrentUserToken = UMgrEnumerateSessionUsers(&v22, &v19);
      if ( CurrentUserToken < 0 || v22 && (CurrentUserToken = UMgrQueryUserToken(*v19, &phToken), CurrentUserToken < 0) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v19);
        goto LABEL_57;
      }
      wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v19);
    }
    v13 = phToken;
    if ( (((unsigned __int64)phToken + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( !(unsigned int)QueryUserToken(0, &phToken) )
        goto LABEL_7;
      v13 = phToken;
    }
    CurrentUserToken = GetUserSidFromToken(v13);
    if ( CurrentUserToken >= 0 )
    {
      v6 = Sid;
      if ( !ConvertSidToStringSidW(Sid, &StringSid) )
        goto LABEL_7;
      if ( !(unsigned int)_o__wcsicmp(StringSid, a1) )
        goto LABEL_47;
      CloseHandle(phToken);
      phToken = 0;
      LocalFree(v6);
      v6 = 0;
      Sid = 0;
      LocalFree(StringSid);
      StringSid = 0;
      if ( !(unsigned int)QueryUserToken(0, &phToken) )
      {
LABEL_7:
        LastError = GetLastError();
        CurrentUserToken = LastError;
        if ( LastError > 0 )
          CurrentUserToken = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_57;
      }
      CurrentUserToken = GetUserSidFromToken(phToken);
      if ( CurrentUserToken >= 0 )
      {
        v6 = Sid;
        if ( ConvertSidToStringSidW(Sid, &StringSid) )
        {
          if ( (unsigned int)_o__wcsicmp(StringSid, a1) )
          {
            CurrentUserToken = -2102788088;
            goto LABEL_57;
          }
LABEL_47:
          *a2 = phToken;
          phToken = 0;
          if ( a3 )
            *a3 = 0;
          goto LABEL_49;
        }
        goto LABEL_7;
      }
    }
    v6 = Sid;
    goto LABEL_57;
  }
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    goto LABEL_7;
  CurrentUserToken = 0;
  v10 = 0;
  if ( !pCount )
    goto LABEL_27;
  while ( 1 )
  {
    SessionId = ppSessionInfo[v10].SessionId;
    if ( !SessionId
      || (ppSessionInfo[v10].State & 0xFFFFFFFA) != 0
      || ppSessionInfo[v10].State == WTSIdle
      || !WTSQueryUserToken(SessionId, &phToken) )
    {
      goto LABEL_23;
    }
    UserSidFromToken = GetUserSidFromToken(phToken);
    v6 = Sid;
    CurrentUserToken = UserSidFromToken;
    if ( UserSidFromToken < 0 )
      goto LABEL_57;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
      break;
LABEL_22:
    LocalFree(StringSid);
    StringSid = 0;
    LocalFree(v6);
    v6 = 0;
    Sid = 0;
    CloseHandle(phToken);
    phToken = 0;
LABEL_23:
    if ( ++v10 >= pCount )
      goto LABEL_27;
  }
  if ( (unsigned int)_o__wcsicmp(StringSid, a1) )
  {
    CurrentUserToken = -2102788088;
    goto LABEL_22;
  }
  *a2 = phToken;
  phToken = 0;
  if ( a3 )
    *a3 = ppSessionInfo[v10].SessionId;
LABEL_27:
  if ( v10 == pCount )
  {
    CurrentUserToken = -2147023888;
    goto LABEL_57;
  }
LABEL_49:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl'::`2'::impl)
    || (CurrentUserToken = SetUserTokenEnterpriseExempt(*a2), CurrentUserToken >= 0) )
  {
LABEL_51:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl'::`2'::impl) )
    {
      v14 = SrpSetTokenEnterpriseExempt(*a2);
      if ( v14 < 0 )
      {
        v15 = RtlNtStatusToDosError(v14);
        CurrentUserToken = v15;
        if ( v15 > 0 )
          CurrentUserToken = (unsigned __int16)v15 | 0x80070000;
        CloseHandle(*a2);
        *a2 = 0;
      }
    }
  }
LABEL_57:
  if ( phToken )
    CloseHandle(phToken);
  LocalFree(StringSid);
  LocalFree(v6);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return (unsigned int)CurrentUserToken;
}

```

## disassembly

```asm
0x18006c910  mov     [rsp-38h+arg_0], rbx
0x18006c915  push    rbp
0x18006c916  push    rsi
0x18006c917  push    rdi
0x18006c918  push    r12
0x18006c91a  push    r13
0x18006c91c  push    r14
0x18006c91e  push    r15
0x18006c920  mov     rbp, rsp
0x18006c923  sub     rsp, 50h
0x18006c927  xor     r12d, r12d
0x18006c92a  mov     rsi, r8
0x18006c92d  mov     [rbp+ppSessionInfo], r12
0x18006c931  mov     r14, rdx
0x18006c934  mov     [rbp+arg_8], r12d
0x18006c938  mov     r13, rcx
0x18006c93b  mov     [rbp+phToken], r12
0x18006c93f  mov     edi, r12d
0x18006c942  mov     [rbp+Sid], r12
0x18006c946  mov     [rbp+StringSid], r12
0x18006c94a  mov     [rdx], r12
0x18006c94d  test    r8, r8
0x18006c950  jz      short loc_18006C959
0x18006c952  mov     dword ptr [r8], 0FFFFFFFFh
0x18006c959  lea     rdx, aS1518; "S-1-5-18"
0x18006c960  call    cs:__imp__o__wcsicmp
0x18006c967  nop     dword ptr [rax+rax+00h]
0x18006c96c  test    eax, eax
0x18006c96e  jnz     short loc_18006C9DD
0x18006c970  lea     rcx, [rbp+phToken]; TokenHandle
0x18006c974  call    GetCurrentUserToken
0x18006c979  mov     ebx, eax
0x18006c97b  test    eax, eax
0x18006c97d  js      loc_18006CD68
0x18006c983  test    rsi, rsi
0x18006c986  jz      short loc_18006C9CD
0x18006c988  call    cs:__imp_GetCurrentProcessId
0x18006c98f  nop     dword ptr [rax+rax+00h]
0x18006c994  mov     ecx, eax; dwProcessId
0x18006c996  mov     rdx, rsi; pSessionId
0x18006c999  call    cs:__imp_ProcessIdToSessionId
0x18006c9a0  nop     dword ptr [rax+rax+00h]
0x18006c9a5  test    eax, eax
0x18006c9a7  jnz     short loc_18006C9CD
0x18006c9a9  call    cs:__imp_GetLastError
0x18006c9b0  nop     dword ptr [rax+rax+00h]
0x18006c9b5  mov     ebx, eax
0x18006c9b7  test    eax, eax
0x18006c9b9  jle     loc_18006CD68
0x18006c9bf  movzx   ebx, ax
0x18006c9c2  or      ebx, 80070000h
0x18006c9c8  jmp     loc_18006CD68
0x18006c9cd  mov     rax, [rbp+phToken]
0x18006c9d1  mov     [r14], rax
0x18006c9d4  mov     [rbp+phToken], r12
0x18006c9d8  jmp     loc_18006CD17
0x18006c9dd  call    IsWTSEnumerateSessionsWPresent
0x18006c9e2  test    al, al
0x18006c9e4  jz      loc_18006CB4E
0x18006c9ea  call    IsWTSEnumerateSessionsWPresent
0x18006c9ef  test    al, al
0x18006c9f1  jz      loc_18006CB4E
0x18006c9f7  xor     edx, edx; Reserved
0x18006c9f9  lea     rax, [rbp+arg_8]
0x18006c9fd  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x18006ca01  mov     [rsp+50h+pCount], rax; pCount
0x18006ca06  xor     ecx, ecx; hServer
0x18006ca08  lea     r8d, [rdx+1]; Version
0x18006ca0c  call    cs:__imp_WTSEnumerateSessionsW
0x18006ca13  nop     dword ptr [rax+rax+00h]
0x18006ca18  test    eax, eax
0x18006ca1a  jz      short loc_18006C9A9
0x18006ca1c  mov     ebx, r12d
0x18006ca1f  mov     r15d, r12d
0x18006ca22  cmp     [rbp+arg_8], r12d
0x18006ca26  jbe     loc_18006CB3A
0x18006ca2c  mov     eax, r15d
0x18006ca2f  lea     r12, [rax+rax*2]
0x18006ca33  mov     rax, [rbp+ppSessionInfo]
0x18006ca37  mov     ecx, [rax+r12*8]; SessionId
0x18006ca3b  test    ecx, ecx
0x18006ca3d  jz      loc_18006CB07
0x18006ca43  test    dword ptr [rax+r12*8+10h], 0FFFFFFFAh
0x18006ca4c  jnz     loc_18006CB07
0x18006ca52  cmp     dword ptr [rax+r12*8+10h], 5
0x18006ca58  jz      loc_18006CB07
0x18006ca5e  lea     rdx, [rbp+phToken]; phToken
0x18006ca62  call    cs:__imp_WTSQueryUserToken
0x18006ca69  nop     dword ptr [rax+rax+00h]
0x18006ca6e  test    eax, eax
0x18006ca70  jz      loc_18006CB07
0x18006ca76  mov     rcx, [rbp+phToken]; TokenHandle
0x18006ca7a  lea     rdx, [rbp+Sid]
0x18006ca7e  call    GetUserSidFromToken
0x18006ca83  mov     rdi, [rbp+Sid]
0x18006ca87  mov     ebx, eax
0x18006ca89  test    eax, eax
0x18006ca8b  js      loc_18006CD68
0x18006ca91  lea     rdx, [rbp+StringSid]; StringSid
0x18006ca95  mov     rcx, rdi; Sid
0x18006ca98  call    cs:__imp_ConvertSidToStringSidW
0x18006ca9f  nop     dword ptr [rax+rax+00h]
0x18006caa4  test    eax, eax
0x18006caa6  jz      short loc_18006CAC4
0x18006caa8  mov     rcx, [rbp+StringSid]
0x18006caac  mov     rdx, r13
0x18006caaf  call    cs:__imp__o__wcsicmp
0x18006cab6  nop     dword ptr [rax+rax+00h]
0x18006cabb  test    eax, eax
0x18006cabd  jz      short loc_18006CB19
0x18006cabf  mov     ebx, 82AA0008h
0x18006cac4  mov     rcx, [rbp+StringSid]; hMem
0x18006cac8  call    cs:__imp_LocalFree
0x18006cacf  nop     dword ptr [rax+rax+00h]
0x18006cad4  xor     r12d, r12d
0x18006cad7  mov     rcx, rdi; hMem
0x18006cada  mov     [rbp+StringSid], r12
0x18006cade  call    cs:__imp_LocalFree
0x18006cae5  nop     dword ptr [rax+rax+00h]
0x18006caea  mov     rcx, [rbp+phToken]; hObject
0x18006caee  mov     edi, r12d
0x18006caf1  mov     [rbp+Sid], r12
0x18006caf5  call    cs:__imp_CloseHandle
0x18006cafc  nop     dword ptr [rax+rax+00h]
0x18006cb01  mov     [rbp+phToken], r12
0x18006cb05  jmp     short loc_18006CB0A
0x18006cb07  xor     r12d, r12d
0x18006cb0a  inc     r15d
0x18006cb0d  cmp     r15d, [rbp+arg_8]
0x18006cb11  jb      loc_18006CA2C
0x18006cb17  jmp     short loc_18006CB3A
0x18006cb19  mov     rax, [rbp+phToken]
0x18006cb1d  mov     [r14], rax
0x18006cb20  mov     [rbp+phToken], 0
0x18006cb28  test    rsi, rsi
0x18006cb2b  jz      short loc_18006CB37
0x18006cb2d  mov     rax, [rbp+ppSessionInfo]
0x18006cb31  mov     ecx, [rax+r12*8]
0x18006cb35  mov     [rsi], ecx
0x18006cb37  xor     r12d, r12d
0x18006cb3a  cmp     r15d, [rbp+arg_8]
0x18006cb3e  jnz     loc_18006CCF9
0x18006cb44  mov     ebx, 800703F0h
0x18006cb49  jmp     loc_18006CD68
0x18006cb4e  call    IsUMgrEnumerateSessionUsersPresent
0x18006cb53  test    al, al
0x18006cb55  jz      short loc_18006CBBC
0x18006cb57  call    IsUMgrEnumerateSessionUsersPresent
0x18006cb5c  test    al, al
0x18006cb5e  jz      short loc_18006CBBC
0x18006cb60  lea     rdx, [rbp+var_10]
0x18006cb64  mov     [rbp+arg_10], r12d
0x18006cb68  lea     rcx, [rbp+arg_10]
0x18006cb6c  mov     [rbp+var_10], r12
0x18006cb70  call    cs:__imp_UMgrEnumerateSessionUsers
0x18006cb77  nop     dword ptr [rax+rax+00h]
0x18006cb7c  mov     ebx, eax
0x18006cb7e  test    eax, eax
0x18006cb80  jns     short loc_18006CB90
0x18006cb82  lea     rcx, [rbp+var_10]
0x18006cb86  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18006cb8b  jmp     loc_18006CD68
0x18006cb90  cmp     [rbp+arg_10], r12d
0x18006cb94  jbe     short loc_18006CBB3
0x18006cb96  mov     rcx, [rbp+var_10]
0x18006cb9a  lea     rdx, [rbp+phToken]
0x18006cb9e  mov     rcx, [rcx]
0x18006cba1  call    cs:__imp_UMgrQueryUserToken
0x18006cba8  nop     dword ptr [rax+rax+00h]
0x18006cbad  mov     ebx, eax
0x18006cbaf  test    eax, eax
0x18006cbb1  js      short loc_18006CB82
0x18006cbb3  lea     rcx, [rbp+var_10]
0x18006cbb7  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x18006cbbc  mov     rcx, [rbp+phToken]
0x18006cbc0  lea     rax, [rcx+1]
0x18006cbc4  test    rax, 0FFFFFFFFFFFFFFFEh
0x18006cbca  jnz     short loc_18006CBEA
0x18006cbcc  lea     rdx, [rbp+phToken]
0x18006cbd0  xor     ecx, ecx
0x18006cbd2  call    cs:__imp_QueryUserToken
0x18006cbd9  nop     dword ptr [rax+rax+00h]
0x18006cbde  test    eax, eax
0x18006cbe0  jz      loc_18006C9A9
0x18006cbe6  mov     rcx, [rbp+phToken]; TokenHandle
0x18006cbea  lea     rdx, [rbp+Sid]
0x18006cbee  call    GetUserSidFromToken
0x18006cbf3  mov     ebx, eax
0x18006cbf5  test    eax, eax
0x18006cbf7  js      loc_18006CD64
0x18006cbfd  mov     rdi, [rbp+Sid]
0x18006cc01  lea     rdx, [rbp+StringSid]; StringSid
0x18006cc05  mov     rcx, rdi; Sid
0x18006cc08  call    cs:__imp_ConvertSidToStringSidW
0x18006cc0f  nop     dword ptr [rax+rax+00h]
0x18006cc14  test    eax, eax
0x18006cc16  jz      loc_18006C9A9
0x18006cc1c  mov     rcx, [rbp+StringSid]
0x18006cc20  mov     rdx, r13
0x18006cc23  call    cs:__imp__o__wcsicmp
0x18006cc2a  nop     dword ptr [rax+rax+00h]
0x18006cc2f  test    eax, eax
0x18006cc31  jz      loc_18006CCE6
0x18006cc37  mov     rcx, [rbp+phToken]; hObject
0x18006cc3b  call    cs:__imp_CloseHandle
0x18006cc42  nop     dword ptr [rax+rax+00h]
0x18006cc47  mov     rcx, rdi; hMem
0x18006cc4a  mov     [rbp+phToken], r12
0x18006cc4e  call    cs:__imp_LocalFree
0x18006cc55  nop     dword ptr [rax+rax+00h]
0x18006cc5a  mov     rcx, [rbp+StringSid]; hMem
0x18006cc5e  mov     rdi, r12
0x18006cc61  mov     [rbp+Sid], r12
0x18006cc65  call    cs:__imp_LocalFree
0x18006cc6c  nop     dword ptr [rax+rax+00h]
0x18006cc71  lea     rdx, [rbp+phToken]
0x18006cc75  mov     [rbp+StringSid], r12
0x18006cc79  xor     ecx, ecx
0x18006cc7b  call    cs:__imp_QueryUserToken
0x18006cc82  nop     dword ptr [rax+rax+00h]
0x18006cc87  test    eax, eax
0x18006cc89  jz      loc_18006C9A9
0x18006cc8f  mov     rcx, [rbp+phToken]; TokenHandle
0x18006cc93  lea     rdx, [rbp+Sid]
0x18006cc97  call    GetUserSidFromToken
0x18006cc9c  mov     ebx, eax
0x18006cc9e  test    eax, eax
0x18006cca0  js      loc_18006CD64
0x18006cca6  mov     rdi, [rbp+Sid]
0x18006ccaa  lea     rdx, [rbp+StringSid]; StringSid
0x18006ccae  mov     rcx, rdi; Sid
0x18006ccb1  call    cs:__imp_ConvertSidToStringSidW
0x18006ccb8  nop     dword ptr [rax+rax+00h]
0x18006ccbd  test    eax, eax
0x18006ccbf  jz      loc_18006C9A9
0x18006ccc5  mov     rcx, [rbp+StringSid]
0x18006ccc9  mov     rdx, r13
0x18006cccc  call    cs:__imp__o__wcsicmp
0x18006ccd3  nop     dword ptr [rax+rax+00h]
0x18006ccd8  test    eax, eax
0x18006ccda  jz      short loc_18006CCE6
0x18006ccdc  mov     ebx, 82AA0008h
0x18006cce1  jmp     loc_18006CD68
0x18006cce6  mov     rax, [rbp+phToken]
0x18006ccea  mov     [r14], rax
0x18006cced  mov     [rbp+phToken], r12
0x18006ccf1  test    rsi, rsi
0x18006ccf4  jz      short loc_18006CCF9
0x18006ccf6  mov     [rsi], r12d
0x18006ccf9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59345096@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096> `wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl(void)'::`2'::impl
0x18006cd00  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(void)
0x18006cd05  test    al, al
0x18006cd07  jnz     short loc_18006CD17
0x18006cd09  mov     rcx, [r14]; TokenHandle
0x18006cd0c  call    SetUserTokenEnterpriseExempt
0x18006cd11  mov     ebx, eax
0x18006cd13  test    eax, eax
0x18006cd15  js      short loc_18006CD68
0x18006cd17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59345096@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096> `wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl(void)'::`2'::impl
0x18006cd1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(void)
0x18006cd23  test    al, al
0x18006cd25  jz      short loc_18006CD68
0x18006cd27  mov     rcx, [r14]; TokenHandle
0x18006cd2a  call    SrpSetTokenEnterpriseExempt
0x18006cd2f  test    eax, eax
0x18006cd31  jns     short loc_18006CD68
0x18006cd33  mov     ecx, eax; Status
0x18006cd35  call    cs:__imp_RtlNtStatusToDosError
0x18006cd3c  nop     dword ptr [rax+rax+00h]
0x18006cd41  mov     ebx, eax
0x18006cd43  test    eax, eax
0x18006cd45  jle     short loc_18006CD50
0x18006cd47  movzx   ebx, ax
0x18006cd4a  or      ebx, 80070000h
0x18006cd50  mov     rcx, [r14]; hObject
0x18006cd53  call    cs:__imp_CloseHandle
0x18006cd5a  nop     dword ptr [rax+rax+00h]
0x18006cd5f  mov     [r14], r12
0x18006cd62  jmp     short loc_18006CD68
0x18006cd64  mov     rdi, [rbp+Sid]
0x18006cd68  mov     rcx, [rbp+phToken]; hObject
0x18006cd6c  test    rcx, rcx
0x18006cd6f  jz      short loc_18006CD7D
0x18006cd71  call    cs:__imp_CloseHandle
0x18006cd78  nop     dword ptr [rax+rax+00h]
0x18006cd7d  mov     rcx, [rbp+StringSid]; hMem
0x18006cd81  call    cs:__imp_LocalFree
0x18006cd88  nop     dword ptr [rax+rax+00h]
0x18006cd8d  mov     rcx, rdi; hMem
0x18006cd90  call    cs:__imp_LocalFree
0x18006cd97  nop     dword ptr [rax+rax+00h]
0x18006cd9c  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x18006cda0  test    rcx, rcx
0x18006cda3  jz      short loc_18006CDB1
0x18006cda5  call    cs:__imp_WTSFreeMemory
0x18006cdac  nop     dword ptr [rax+rax+00h]
0x18006cdb1  mov     eax, ebx
0x18006cdb3  mov     rbx, [rsp+50h+arg_0]
0x18006cdbb  add     rsp, 50h
0x18006cdbf  pop     r15
  ... truncated ...
```
