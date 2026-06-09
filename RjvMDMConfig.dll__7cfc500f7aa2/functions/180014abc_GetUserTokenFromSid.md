# GetUserTokenFromSid

- ea: `0x180014abc`
- end: `0x180014f0d`
- name: `GetUserTokenFromSid`
- size: `1105`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180012a58`

## callees

- `0x180002acc`
- `0x180002c6c`
- `0x1800129e8`
- `0x1800148bc`
- `0x180014974`
- `0x180014abc`
- `0x1800159cc`
- `0x180015a84`
- `0x180017c88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014afc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014d78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014e21`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014afc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014c22`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014d78`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180014e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b6e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ebb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014d90`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014e9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014ebb`
- `ntdll!RtlNtStatusToDosError` at `0x180014e7f`
- `ntdll!RtlNtStatusToDosError` at `0x180014e7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014c0b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014d5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014e06`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014c0b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014d5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014e06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014da3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014dba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ecb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014eda`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014c4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014da3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014dba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014ecb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014eda`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180014b5e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180014b5e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180014bd5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180014bd5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180014eef`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180014eef`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180014cf6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180014cf6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180014cc5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180014cc5`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180014d27`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180014dd0`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180014d27`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x180014dd0`

## pseudocode

```c
__int64 __fastcall GetUserTokenFromSid(__int64 a1, HANDLE *a2, __int64 a3)
{
  PSID v5; // rdi
  signed int CurrentUserToken; // ebx
  signed int LastError; // eax
  int v8; // r14d
  DWORD SessionId; // ecx
  int UserSidFromToken; // eax
  void *v11; // rcx
  NTSTATUS v12; // eax
  signed int v13; // eax
  LPWSTR StringSid; // [rsp+30h] [rbp-20h] BYREF
  PSID Sid; // [rsp+38h] [rbp-18h]
  _QWORD *v17; // [rsp+40h] [rbp-10h] BYREF
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+48h] [rbp-8h] BYREF
  int v19; // [rsp+98h] [rbp+48h] BYREF
  DWORD pCount; // [rsp+A0h] [rbp+50h] BYREF
  int v21; // [rsp+A4h] [rbp+54h]
  void *phToken; // [rsp+A8h] [rbp+58h] BYREF

  v21 = HIDWORD(a3);
  *a2 = 0;
  ppSessionInfo = 0;
  pCount = 0;
  v5 = 0;
  phToken = 0;
  Sid = 0;
  StringSid = 0;
  if ( !(unsigned int)_o__wcsicmp(a1, L"S-1-5-18") )
  {
    CurrentUserToken = GetCurrentUserToken(&phToken);
    if ( CurrentUserToken < 0 )
      goto LABEL_51;
    *a2 = phToken;
    phToken = 0;
    goto LABEL_45;
  }
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
    {
      v19 = 0;
      v17 = 0;
      CurrentUserToken = UMgrEnumerateSessionUsers(&v19, &v17);
      if ( CurrentUserToken < 0 || v19 && (CurrentUserToken = UMgrQueryUserToken(*v17, &phToken), CurrentUserToken < 0) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v17);
        goto LABEL_51;
      }
      wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&void UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(&v17);
    }
    v11 = phToken;
    if ( (((unsigned __int64)phToken + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( !(unsigned int)QueryUserToken(0, &phToken) )
        goto LABEL_7;
      v11 = phToken;
    }
    CurrentUserToken = GetUserSidFromToken(v11);
    if ( CurrentUserToken >= 0 )
    {
      v5 = Sid;
      if ( !ConvertSidToStringSidW(Sid, &StringSid) )
        goto LABEL_7;
      if ( !(unsigned int)_o__wcsicmp(StringSid, a1) )
        goto LABEL_42;
      CloseHandle(phToken);
      phToken = 0;
      LocalFree(v5);
      v5 = 0;
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
        goto LABEL_51;
      }
      CurrentUserToken = GetUserSidFromToken(phToken);
      if ( CurrentUserToken >= 0 )
      {
        v5 = Sid;
        if ( ConvertSidToStringSidW(Sid, &StringSid) )
        {
          if ( (unsigned int)_o__wcsicmp(StringSid, a1) )
          {
            CurrentUserToken = -2102788088;
            goto LABEL_51;
          }
LABEL_42:
          *a2 = phToken;
          phToken = 0;
          goto LABEL_43;
        }
        goto LABEL_7;
      }
    }
    v5 = Sid;
    goto LABEL_51;
  }
  if ( !WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount) )
    goto LABEL_7;
  CurrentUserToken = 0;
  v8 = 0;
  if ( !pCount )
    goto LABEL_22;
  while ( 1 )
  {
    SessionId = ppSessionInfo[v8].SessionId;
    if ( !SessionId
      || (ppSessionInfo[v8].State & 0xFFFFFFFA) != 0
      || ppSessionInfo[v8].State == WTSIdle
      || !WTSQueryUserToken(SessionId, &phToken) )
    {
      goto LABEL_19;
    }
    UserSidFromToken = GetUserSidFromToken(phToken);
    v5 = Sid;
    CurrentUserToken = UserSidFromToken;
    if ( UserSidFromToken < 0 )
      goto LABEL_51;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
      break;
LABEL_18:
    LocalFree(StringSid);
    StringSid = 0;
    LocalFree(v5);
    v5 = 0;
    Sid = 0;
    CloseHandle(phToken);
    phToken = 0;
LABEL_19:
    if ( ++v8 >= pCount )
      goto LABEL_22;
  }
  if ( (unsigned int)_o__wcsicmp(StringSid, a1) )
  {
    CurrentUserToken = -2102788088;
    goto LABEL_18;
  }
  *a2 = phToken;
  phToken = 0;
LABEL_22:
  if ( v8 == pCount )
  {
    CurrentUserToken = -2147023888;
    goto LABEL_51;
  }
LABEL_43:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl'::`2'::impl)
    || (CurrentUserToken = SetUserTokenEnterpriseExempt(*a2), CurrentUserToken >= 0) )
  {
LABEL_45:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl'::`2'::impl) )
    {
      v12 = SrpSetTokenEnterpriseExempt(*a2);
      if ( v12 < 0 )
      {
        v13 = RtlNtStatusToDosError(v12);
        CurrentUserToken = v13;
        if ( v13 > 0 )
          CurrentUserToken = (unsigned __int16)v13 | 0x80070000;
        CloseHandle(*a2);
        *a2 = 0;
      }
    }
  }
LABEL_51:
  if ( phToken )
    CloseHandle(phToken);
  LocalFree(StringSid);
  LocalFree(v5);
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return (unsigned int)CurrentUserToken;
}

```

## disassembly

```asm
0x180014abc  mov     qword ptr [rsp-38h+arg_10], r8
0x180014ac1  push    rbp
0x180014ac2  push    rbx
0x180014ac3  push    rsi
0x180014ac4  push    rdi
0x180014ac5  push    r12
0x180014ac7  push    r14
0x180014ac9  push    r15
0x180014acb  mov     rbp, rsp
0x180014ace  sub     rsp, 50h
0x180014ad2  xor     r12d, r12d
0x180014ad5  mov     rsi, rdx
0x180014ad8  mov     [rdx], r12
0x180014adb  mov     r15, rcx
0x180014ade  lea     rdx, aS1518; "S-1-5-18"
0x180014ae5  mov     [rbp+ppSessionInfo], r12
0x180014ae9  mov     [rbp+arg_10], r12d
0x180014aed  mov     edi, r12d
0x180014af0  mov     [rbp+phToken], r12
0x180014af4  mov     [rbp+Sid], r12
0x180014af8  mov     [rbp+StringSid], r12
0x180014afc  call    cs:__imp__o__wcsicmp
0x180014b03  nop     dword ptr [rax+rax+00h]
0x180014b08  test    eax, eax
0x180014b0a  jnz     short loc_180014B2F
0x180014b0c  lea     rcx, [rbp+phToken]; TokenHandle
0x180014b10  call    GetCurrentUserToken
0x180014b15  mov     ebx, eax
0x180014b17  test    eax, eax
0x180014b19  js      loc_180014EB2
0x180014b1f  mov     rcx, [rbp+phToken]
0x180014b23  mov     [rsi], rcx
0x180014b26  mov     [rbp+phToken], r12
0x180014b2a  jmp     loc_180014E61
0x180014b2f  call    IsWTSEnumerateSessionsWPresent
0x180014b34  test    al, al
0x180014b36  jz      loc_180014CA3
0x180014b3c  call    IsWTSEnumerateSessionsWPresent
0x180014b41  test    al, al
0x180014b43  jz      loc_180014CA3
0x180014b49  xor     edx, edx; Reserved
0x180014b4b  lea     rax, [rbp+arg_10]
0x180014b4f  lea     r9, [rbp+ppSessionInfo]; ppSessionInfo
0x180014b53  mov     [rsp+50h+pCount], rax; pCount
0x180014b58  xor     ecx, ecx; hServer
0x180014b5a  lea     r8d, [rdx+1]; Version
0x180014b5e  call    cs:__imp_WTSEnumerateSessionsW
0x180014b65  nop     dword ptr [rax+rax+00h]
0x180014b6a  test    eax, eax
0x180014b6c  jnz     short loc_180014B92
0x180014b6e  call    cs:__imp_GetLastError
0x180014b75  nop     dword ptr [rax+rax+00h]
0x180014b7a  mov     ebx, eax
0x180014b7c  test    eax, eax
0x180014b7e  jle     loc_180014EB2
0x180014b84  movzx   ebx, ax
0x180014b87  or      ebx, 80070000h
0x180014b8d  jmp     loc_180014EB2
0x180014b92  mov     ebx, r12d
0x180014b95  mov     r14d, r12d
0x180014b98  cmp     [rbp+arg_10], r12d
0x180014b9c  jbe     loc_180014C8F
0x180014ba2  mov     eax, r14d
0x180014ba5  lea     rdx, [rax+rax*2]
0x180014ba9  mov     rax, [rbp+ppSessionInfo]
0x180014bad  mov     ecx, [rax+rdx*8]; SessionId
0x180014bb0  test    ecx, ecx
0x180014bb2  jz      loc_180014C75
0x180014bb8  test    dword ptr [rax+rdx*8+10h], 0FFFFFFFAh
0x180014bc0  jnz     loc_180014C75
0x180014bc6  cmp     dword ptr [rax+rdx*8+10h], 5
0x180014bcb  jz      loc_180014C75
0x180014bd1  lea     rdx, [rbp+phToken]; phToken
0x180014bd5  call    cs:__imp_WTSQueryUserToken
0x180014bdc  nop     dword ptr [rax+rax+00h]
0x180014be1  test    eax, eax
0x180014be3  jz      loc_180014C75
0x180014be9  mov     rcx, [rbp+phToken]; TokenHandle
0x180014bed  lea     rdx, [rbp+Sid]
0x180014bf1  call    GetUserSidFromToken
0x180014bf6  mov     rdi, [rbp+Sid]
0x180014bfa  mov     ebx, eax
0x180014bfc  test    eax, eax
0x180014bfe  js      loc_180014EB2
0x180014c04  lea     rdx, [rbp+StringSid]; StringSid
0x180014c08  mov     rcx, rdi; Sid
0x180014c0b  call    cs:__imp_ConvertSidToStringSidW
0x180014c12  nop     dword ptr [rax+rax+00h]
0x180014c17  test    eax, eax
0x180014c19  jz      short loc_180014C37
0x180014c1b  mov     rcx, [rbp+StringSid]
0x180014c1f  mov     rdx, r15
0x180014c22  call    cs:__imp__o__wcsicmp
0x180014c29  nop     dword ptr [rax+rax+00h]
0x180014c2e  test    eax, eax
0x180014c30  jz      short loc_180014C84
0x180014c32  mov     ebx, 82AA0008h
0x180014c37  mov     rcx, [rbp+StringSid]; hMem
0x180014c3b  call    cs:__imp_LocalFree
0x180014c42  nop     dword ptr [rax+rax+00h]
0x180014c47  mov     rcx, rdi; hMem
0x180014c4a  mov     [rbp+StringSid], r12
0x180014c4e  call    cs:__imp_LocalFree
0x180014c55  nop     dword ptr [rax+rax+00h]
0x180014c5a  mov     rcx, [rbp+phToken]; hObject
0x180014c5e  mov     rdi, r12
0x180014c61  mov     [rbp+Sid], r12
0x180014c65  call    cs:__imp_CloseHandle
0x180014c6c  nop     dword ptr [rax+rax+00h]
0x180014c71  mov     [rbp+phToken], r12
0x180014c75  inc     r14d
0x180014c78  cmp     r14d, [rbp+arg_10]
0x180014c7c  jb      loc_180014BA2
0x180014c82  jmp     short loc_180014C8F
0x180014c84  mov     rax, [rbp+phToken]
0x180014c88  mov     [rsi], rax
0x180014c8b  mov     [rbp+phToken], r12
0x180014c8f  cmp     r14d, [rbp+arg_10]
0x180014c93  jnz     loc_180014E43
0x180014c99  mov     ebx, 800703F0h
0x180014c9e  jmp     loc_180014EB2
0x180014ca3  call    IsUMgrEnumerateSessionUsersPresent
0x180014ca8  test    al, al
0x180014caa  jz      short loc_180014D11
0x180014cac  call    IsUMgrEnumerateSessionUsersPresent
0x180014cb1  test    al, al
0x180014cb3  jz      short loc_180014D11
0x180014cb5  lea     rdx, [rbp+var_10]
0x180014cb9  mov     [rbp+arg_8], r12d
0x180014cbd  lea     rcx, [rbp+arg_8]
0x180014cc1  mov     [rbp+var_10], r12
0x180014cc5  call    cs:__imp_UMgrEnumerateSessionUsers
0x180014ccc  nop     dword ptr [rax+rax+00h]
0x180014cd1  mov     ebx, eax
0x180014cd3  test    eax, eax
0x180014cd5  jns     short loc_180014CE5
0x180014cd7  lea     rcx, [rbp+var_10]
0x180014cdb  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180014ce0  jmp     loc_180014EB2
0x180014ce5  cmp     [rbp+arg_8], r12d
0x180014ce9  jbe     short loc_180014D08
0x180014ceb  mov     rcx, [rbp+var_10]
0x180014cef  lea     rdx, [rbp+phToken]
0x180014cf3  mov     rcx, [rcx]
0x180014cf6  call    cs:__imp_UMgrQueryUserToken
0x180014cfd  nop     dword ptr [rax+rax+00h]
0x180014d02  mov     ebx, eax
0x180014d04  test    eax, eax
0x180014d06  js      short loc_180014CD7
0x180014d08  lea     rcx, [rbp+var_10]
0x180014d0c  call    ??1?$unique_storage@U?$resource_policy@PEAU_SESSION_USER_CONTEXT@@P6AXPEAU1@@Z$1?UMgrFreeSessionUsers@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SESSION_USER_CONTEXT *,void (*)(_SESSION_USER_CONTEXT *),&UMgrFreeSessionUsers(_SESSION_USER_CONTEXT *),wistd::integral_constant<unsigned __int64,0>,_SESSION_USER_CONTEXT *,_SESSION_USER_CONTEXT *,0,std::nullptr_t>>(void)
0x180014d11  mov     rcx, [rbp+phToken]
0x180014d15  lea     rax, [rcx+1]
0x180014d19  test    rax, 0FFFFFFFFFFFFFFFEh
0x180014d1f  jnz     short loc_180014D3F
0x180014d21  lea     rdx, [rbp+phToken]
0x180014d25  xor     ecx, ecx
0x180014d27  call    cs:__imp_QueryUserToken
0x180014d2e  nop     dword ptr [rax+rax+00h]
0x180014d33  test    eax, eax
0x180014d35  jz      loc_180014B6E
0x180014d3b  mov     rcx, [rbp+phToken]; TokenHandle
0x180014d3f  lea     rdx, [rbp+Sid]
0x180014d43  call    GetUserSidFromToken
0x180014d48  mov     ebx, eax
0x180014d4a  test    eax, eax
0x180014d4c  js      loc_180014EAE
0x180014d52  mov     rdi, [rbp+Sid]
0x180014d56  lea     rdx, [rbp+StringSid]; StringSid
0x180014d5a  mov     rcx, rdi; Sid
0x180014d5d  call    cs:__imp_ConvertSidToStringSidW
0x180014d64  nop     dword ptr [rax+rax+00h]
0x180014d69  test    eax, eax
0x180014d6b  jz      loc_180014B6E
0x180014d71  mov     rcx, [rbp+StringSid]
0x180014d75  mov     rdx, r15
0x180014d78  call    cs:__imp__o__wcsicmp
0x180014d7f  nop     dword ptr [rax+rax+00h]
0x180014d84  test    eax, eax
0x180014d86  jz      loc_180014E38
0x180014d8c  mov     rcx, [rbp+phToken]; hObject
0x180014d90  call    cs:__imp_CloseHandle
0x180014d97  nop     dword ptr [rax+rax+00h]
0x180014d9c  mov     rcx, rdi; hMem
0x180014d9f  mov     [rbp+phToken], r12
0x180014da3  call    cs:__imp_LocalFree
0x180014daa  nop     dword ptr [rax+rax+00h]
0x180014daf  mov     rcx, [rbp+StringSid]; hMem
0x180014db3  mov     rdi, r12
0x180014db6  mov     [rbp+Sid], r12
0x180014dba  call    cs:__imp_LocalFree
0x180014dc1  nop     dword ptr [rax+rax+00h]
0x180014dc6  lea     rdx, [rbp+phToken]
0x180014dca  mov     [rbp+StringSid], r12
0x180014dce  xor     ecx, ecx
0x180014dd0  call    cs:__imp_QueryUserToken
0x180014dd7  nop     dword ptr [rax+rax+00h]
0x180014ddc  test    eax, eax
0x180014dde  jz      loc_180014B6E
0x180014de4  mov     rcx, [rbp+phToken]; TokenHandle
0x180014de8  lea     rdx, [rbp+Sid]
0x180014dec  call    GetUserSidFromToken
0x180014df1  mov     ebx, eax
0x180014df3  test    eax, eax
0x180014df5  js      loc_180014EAE
0x180014dfb  mov     rdi, [rbp+Sid]
0x180014dff  lea     rdx, [rbp+StringSid]; StringSid
0x180014e03  mov     rcx, rdi; Sid
0x180014e06  call    cs:__imp_ConvertSidToStringSidW
0x180014e0d  nop     dword ptr [rax+rax+00h]
0x180014e12  test    eax, eax
0x180014e14  jz      loc_180014B6E
0x180014e1a  mov     rcx, [rbp+StringSid]
0x180014e1e  mov     rdx, r15
0x180014e21  call    cs:__imp__o__wcsicmp
0x180014e28  nop     dword ptr [rax+rax+00h]
0x180014e2d  test    eax, eax
0x180014e2f  jz      short loc_180014E38
0x180014e31  mov     ebx, 82AA0008h
0x180014e36  jmp     short loc_180014EB2
0x180014e38  mov     rax, [rbp+phToken]
0x180014e3c  mov     [rsi], rax
0x180014e3f  mov     [rbp+phToken], r12
0x180014e43  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59345096@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096> `wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl(void)'::`2'::impl
0x180014e4a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(void)
0x180014e4f  test    al, al
0x180014e51  jnz     short loc_180014E61
0x180014e53  mov     rcx, [rsi]; TokenHandle
0x180014e56  call    SetUserTokenEnterpriseExempt
0x180014e5b  mov     ebx, eax
0x180014e5d  test    eax, eax
0x180014e5f  js      short loc_180014EB2
0x180014e61  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59345096@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096> `wil::Feature<__WilFeatureTraits_Feature_59345096>::GetImpl(void)'::`2'::impl
0x180014e68  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59345096@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59345096>::__private_IsEnabled(void)
0x180014e6d  test    al, al
0x180014e6f  jz      short loc_180014EB2
0x180014e71  mov     rcx, [rsi]; TokenHandle
0x180014e74  call    SrpSetTokenEnterpriseExempt
0x180014e79  test    eax, eax
0x180014e7b  jns     short loc_180014EB2
0x180014e7d  mov     ecx, eax; Status
0x180014e7f  call    cs:__imp_RtlNtStatusToDosError
0x180014e86  nop     dword ptr [rax+rax+00h]
0x180014e8b  mov     ebx, eax
0x180014e8d  test    eax, eax
0x180014e8f  jle     short loc_180014E9A
0x180014e91  movzx   ebx, ax
0x180014e94  or      ebx, 80070000h
0x180014e9a  mov     rcx, [rsi]; hObject
0x180014e9d  call    cs:__imp_CloseHandle
0x180014ea4  nop     dword ptr [rax+rax+00h]
0x180014ea9  mov     [rsi], r12
0x180014eac  jmp     short loc_180014EB2
0x180014eae  mov     rdi, [rbp+Sid]
0x180014eb2  mov     rcx, [rbp+phToken]; hObject
0x180014eb6  test    rcx, rcx
0x180014eb9  jz      short loc_180014EC7
0x180014ebb  call    cs:__imp_CloseHandle
0x180014ec2  nop     dword ptr [rax+rax+00h]
0x180014ec7  mov     rcx, [rbp+StringSid]; hMem
0x180014ecb  call    cs:__imp_LocalFree
0x180014ed2  nop     dword ptr [rax+rax+00h]
0x180014ed7  mov     rcx, rdi; hMem
0x180014eda  call    cs:__imp_LocalFree
0x180014ee1  nop     dword ptr [rax+rax+00h]
0x180014ee6  mov     rcx, [rbp+ppSessionInfo]; pMemory
0x180014eea  test    rcx, rcx
0x180014eed  jz      short loc_180014EFB
0x180014eef  call    cs:__imp_WTSFreeMemory
0x180014ef6  nop     dword ptr [rax+rax+00h]
0x180014efb  mov     eax, ebx
0x180014efd  add     rsp, 50h
0x180014f01  pop     r15
0x180014f03  pop     r14
0x180014f05  pop     r12
0x180014f07  pop     rdi
0x180014f08  pop     rsi
0x180014f09  pop     rbx
0x180014f0a  pop     rbp
0x180014f0b  retn
```
