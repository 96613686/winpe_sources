# UserOOBEController::s_ShutdownUserOobe(bool)

- ea: `0x18002abbc`
- end: `0x18002ada4`
- name: `?s_ShutdownUserOobe@UserOOBEController@@CAJ_N@Z`
- size: `488`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800268e0`
- `0x180026bc0`

## callees

- `0x180007114`
- `0x180007134`
- `0x18000a5e8`
- `0x180013688`
- `0x1800169b0`
- `0x18001f6c4`
- `0x18002197c`
- `0x180021a84`
- `0x1800279b8`
- `0x180028298`
- `0x18002849c`
- `0x18002abbc`
- `0x18002d838`

## import_xrefs

- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002acf1`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x18002acf1`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18002ad31`
- `api-ms-win-core-shutdown-l1-1-0!InitiateSystemShutdownExW` at `0x18002ad31`

## string_xrefs

- `0x18002abee`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002ac3e`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002acac`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002ad02`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x18002ad3f`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall UserOOBEController::s_ShutdownUserOobe(const unsigned __int16 *a1)
{
  int v1; // esi
  unsigned int v2; // eax
  DWORD v4; // edi
  int DefaultAccountSid; // eax
  int LastError; // ebx
  const unsigned __int16 *v7; // rcx
  int v8; // eax
  const unsigned __int16 *v9; // rcx
  unsigned int v10; // eax
  const char *v11; // r9
  const unsigned __int16 *v12; // rcx
  const unsigned __int16 *v13; // rcx
  BOOL bRebootAfterShutdown; // [rsp+20h] [rbp-30h]
  LPCWSTR pszSubKey[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  unsigned __int16 *v17; // [rsp+78h] [rbp+28h] BYREF
  int v18; // [rsp+80h] [rbp+30h]
  char v19; // [rsp+84h] [rbp+34h]

  v1 = (unsigned __int8)a1;
  LODWORD(v17) = 0;
  v2 = SetPrivilegeAttribute(a1, 2u, (unsigned int *)&v17);
  if ( v2 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x3DB,
             (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
             (const char *)v2,
             bRebootAfterShutdown);
  v4 = (unsigned int)v17;
  v18 = (int)v17;
  v19 = 1;
  if ( (_BYTE)v1 )
    OOBE::Health::details::OOBEHealthTracker::HandleEvent<7,bool>();
  else
    OOBE::Health::details::OOBEHealthTracker::HandleEvent<9,bool>();
  v17 = 0;
  DefaultAccountSid = UserOOBEController::s_GetDefaultAccountSid(&v17);
  LastError = DefaultAccountSid;
  if ( DefaultAccountSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F2,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)DefaultAccountSid,
      bRebootAfterShutdown);
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&v17);
    SetPrivilegeAttribute(v7, v4, 0);
    return LastError;
  }
  memset(pszSubKey, 0, 24);
  v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
         pszSubKey,
         L"%s\\%s",
         v17,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\UserOOBE");
  LastError = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F4,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)(unsigned int)v8,
      bRebootAfterShutdown);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszSubKey);
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&v17);
    SetPrivilegeAttribute(v9, v4, 0);
    return LastError;
  }
  v10 = SHDeleteValueW(HKEY_USERS, pszSubKey[0], L"ExplorerStartCount");
  if ( v10 )
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)0x3F5,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v10,
      bRebootAfterShutdown);
  UserOOBEController::s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny();
  if ( !InitiateSystemShutdownExW(0, 0, 0, 1, v1, 0x20004u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x401,
                  (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
                  v11);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszSubKey);
    wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&v17);
    SetPrivilegeAttribute(v12, v4, 0);
    return LastError;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(pszSubKey);
  wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(&v17);
  SetPrivilegeAttribute(v13, v4, 0);
  return 0;
}

```

## disassembly

```asm
0x18002abbc  mov     [rsp-18h+arg_0], rbx
0x18002abc1  push    rbp
0x18002abc2  push    rsi
0x18002abc3  push    rdi
0x18002abc4  mov     rbp, rsp
0x18002abc7  sub     rsp, 50h
0x18002abcb  movzx   esi, cl
0x18002abce  mov     dword ptr [rbp+arg_8], 0
0x18002abd5  lea     r8, [rbp+arg_8]; unsigned int *
0x18002abd9  mov     edx, 2; unsigned int
0x18002abde  call    ?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z; SetPrivilegeAttribute(ushort const *,ulong,ulong *)
0x18002abe3  test    eax, eax
0x18002abe5  jz      short loc_18002AC04
0x18002abe7  mov     rcx, [rbp+18h]; this
0x18002abeb  mov     r9d, eax; char *
0x18002abee  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002abf5  mov     edx, 3DBh; void *
0x18002abfa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002abff  jmp     loc_18002AD97
0x18002ac04  mov     edi, dword ptr [rbp+arg_8]
0x18002ac07  mov     [rbp+arg_10], edi
0x18002ac0a  mov     [rbp+arg_14], 1
0x18002ac0e  test    sil, sil
0x18002ac11  jz      short loc_18002AC1A
0x18002ac13  call    ??$HandleEvent@$06_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<7,bool>(bool)
0x18002ac18  jmp     short loc_18002AC20
0x18002ac1a  call    ??$HandleEvent@$08_N@OOBEHealthTracker@details@Health@OOBE@@SAX_N@Z; OOBE::Health::details::OOBEHealthTracker::HandleEvent<9,bool>(bool)
0x18002ac1f  nop
0x18002ac20  mov     [rbp+arg_8], 0
0x18002ac28  lea     rcx, [rbp+arg_8]; unsigned __int16 **
0x18002ac2c  call    ?s_GetDefaultAccountSid@UserOOBEController@@CAJPEAPEAG@Z; UserOOBEController::s_GetDefaultAccountSid(ushort * *)
0x18002ac31  mov     ebx, eax
0x18002ac33  test    eax, eax
0x18002ac35  jns     short loc_18002AC6C
0x18002ac37  mov     rcx, [rbp+18h]; this
0x18002ac3b  mov     r9d, eax; char *
0x18002ac3e  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002ac45  mov     edx, 3F2h; void *
0x18002ac4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ac4f  nop
0x18002ac50  lea     rcx, [rbp+arg_8]
0x18002ac54  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18002ac59  nop
0x18002ac5a  xor     r8d, r8d; unsigned int *
0x18002ac5d  mov     edx, edi; unsigned int
0x18002ac5f  call    ?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z; SetPrivilegeAttribute(ushort const *,ulong,ulong *)
0x18002ac64  nop
0x18002ac65  mov     eax, ebx
0x18002ac67  jmp     loc_18002AD97
0x18002ac6c  mov     [rbp+pszSubKey], 0
0x18002ac74  mov     [rbp+var_18], 0
0x18002ac7c  mov     [rbp+var_10], 0
0x18002ac84  lea     r9, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002ac8b  mov     r8, [rbp+arg_8]
0x18002ac8f  lea     rdx, aSS_0; "%s\\%s"
0x18002ac96  lea     rcx, [rbp+pszSubKey]
0x18002ac9a  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002ac9f  mov     ebx, eax
0x18002aca1  test    eax, eax
0x18002aca3  jns     short loc_18002ACDF
0x18002aca5  mov     rcx, [rbp+18h]; this
0x18002aca9  mov     r9d, eax; char *
0x18002acac  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002acb3  mov     edx, 3F4h; void *
0x18002acb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002acbd  nop
0x18002acbe  lea     rcx, [rbp+pszSubKey]
0x18002acc2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002acc7  nop
0x18002acc8  lea     rcx, [rbp+arg_8]
0x18002accc  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18002acd1  nop
0x18002acd2  xor     r8d, r8d; unsigned int *
0x18002acd5  mov     edx, edi; unsigned int
0x18002acd7  call    ?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z; SetPrivilegeAttribute(ushort const *,ulong,ulong *)
0x18002acdc  nop
0x18002acdd  jmp     short loc_18002AC65
0x18002acdf  lea     r8, aExplorerstartc; "ExplorerStartCount"
0x18002ace6  mov     rdx, [rbp+pszSubKey]; pszSubKey
0x18002acea  mov     rcx, 0FFFFFFFF80000003h; hkey
0x18002acf1  call    cs:__imp_SHDeleteValueW
0x18002acf7  mov     rcx, [rbp+18h]; this
0x18002acfb  test    eax, eax
0x18002acfd  jz      short loc_18002AD13
0x18002acff  mov     r9d, eax; char *
0x18002ad02  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002ad09  mov     edx, 3F5h; void *
0x18002ad0e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002ad13  call    ?s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny@UserOOBEController@@CAJXZ; UserOOBEController::s_EnsureDefaultAccountAutoLogonAndCacheProvisioningCredentialIfAny(void)
0x18002ad18  mov     [rsp+50h+dwReason], 20004h; dwReason
0x18002ad20  mov     [rsp+50h+bRebootAfterShutdown], esi; bRebootAfterShutdown
0x18002ad24  mov     r9d, 1; bForceAppsClosed
0x18002ad2a  xor     r8d, r8d; dwTimeout
0x18002ad2d  xor     edx, edx; lpMessage
0x18002ad2f  xor     ecx, ecx; lpMachineName
0x18002ad31  call    cs:__imp_InitiateSystemShutdownExW
0x18002ad37  test    eax, eax
0x18002ad39  jnz     short loc_18002AD76
0x18002ad3b  mov     rcx, [rbp+18h]; this
0x18002ad3f  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002ad46  mov     edx, 401h; void *
0x18002ad4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002ad50  mov     ebx, eax
0x18002ad52  lea     rcx, [rbp+pszSubKey]
0x18002ad56  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002ad5b  nop
0x18002ad5c  lea     rcx, [rbp+arg_8]
0x18002ad60  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18002ad65  nop
0x18002ad66  xor     r8d, r8d; unsigned int *
0x18002ad69  mov     edx, edi; unsigned int
0x18002ad6b  call    ?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z; SetPrivilegeAttribute(ushort const *,ulong,ulong *)
0x18002ad70  nop
0x18002ad71  jmp     loc_18002AC65
0x18002ad76  lea     rcx, [rbp+pszSubKey]
0x18002ad7a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002ad7f  nop
0x18002ad80  lea     rcx, [rbp+arg_8]
0x18002ad84  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x18002ad89  nop
0x18002ad8a  xor     r8d, r8d; unsigned int *
0x18002ad8d  mov     edx, edi; unsigned int
0x18002ad8f  call    ?SetPrivilegeAttribute@@YAKPEBGKPEAK@Z; SetPrivilegeAttribute(ushort const *,ulong,ulong *)
0x18002ad94  nop
0x18002ad95  xor     eax, eax
0x18002ad97  mov     rbx, [rsp+50h+arg_0]
0x18002ad9c  add     rsp, 50h
0x18002ada0  pop     rdi
0x18002ada1  pop     rsi
0x18002ada2  pop     rbp
0x18002ada3  retn
```
