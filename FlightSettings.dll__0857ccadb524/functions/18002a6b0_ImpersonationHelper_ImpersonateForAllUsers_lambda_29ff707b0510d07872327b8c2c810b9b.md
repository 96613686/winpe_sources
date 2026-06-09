# ImpersonationHelper::ImpersonateForAllUsers__lambda_29ff707b0510d07872327b8c2c810b9b__&_

- ea: `0x18002a6b0`
- end: `0x18002a8ef`
- name: `ImpersonationHelper::ImpersonateForAllUsers__lambda_29ff707b0510d07872327b8c2c810b9b__&_`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b8ac`

## callees

- `0x180004b80`
- `0x180006690`
- `0x1800067a8`
- `0x180006938`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180017870`
- `0x18002a594`
- `0x18002a6b0`
- `0x18002a8f8`
- `0x18002aaa0`
- `0x18002b1b0`
- `0x18002b1f4`
- `0x18002b5a0`
- `0x18002b614`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002a800`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18002a800`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18002a7dc`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18002a7dc`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002a87c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18002a87c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18002a82c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18002a82c`

## string_xrefs

- `0x18002a773`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x18002a88b`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ImpersonationHelper::ImpersonateForAllUsers__lambda_29ff707b0510d07872327b8c2c810b9b____(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3)
{
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  unsigned int LastError; // ebx
  __int64 v7; // rdx
  const char *v9; // r9
  __int64 v10; // rdx
  void *v11; // [rsp+20h] [rbp-39h] BYREF
  unsigned int v12; // [rsp+28h] [rbp-31h] BYREF
  unsigned int v13; // [rsp+2Ch] [rbp-2Dh] BYREF
  int v14; // [rsp+30h] [rbp-29h] BYREF
  int SessionActiveShellUserToken; // [rsp+34h] [rbp-25h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-21h] BYREF
  _QWORD *v17; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v18[4]; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v19[2]; // [rsp+68h] [rbp+Fh] BYREF
  int v20; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v17 = a1;
  v16 = a2;
  *a1 = 0;
  *v16 = 0;
  v13 = 0;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( !(unsigned __int8)IsUMgrGetSessionActiveShellUserTokenPresent()
      || !(unsigned __int8)IsQueryActiveSessionPresent()
      || !(unsigned __int8)IsQueryActiveSessionPresent() )
    {
      return v13;
    }
    v12 = 0;
    v11 = 0;
    if ( !(unsigned int)QueryActiveSession(&v12) )
    {
      v10 = 148;
LABEL_25:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v10,
                    (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
                    v9);
      goto LABEL_26;
    }
    v14 = 0;
    RtlGetDeviceFamilyInfoEnum(0, &v14, 0);
    if ( v14 != 5 && (unsigned int)(v14 - 11) > 1 )
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v11,
        0);
      SessionActiveShellUserToken = UMgrGetSessionActiveShellUserToken(v12, &v11);
      if ( SessionActiveShellUserToken >= 0 )
        goto LABEL_27;
      if ( (unsigned __int8)IsUMgrGetSessionActiveShellUserTokenPresent() )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &v11,
          0);
        SessionActiveShellUserToken = ImpersonationHelper::GetActiveUserTokenFromUserManager(&v11);
        if ( SessionActiveShellUserToken >= 0 )
        {
          LastError = 0;
LABEL_26:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
          return LastError;
        }
      }
      FlightSettingsAPITelemetryClass::UMgrGetSessionActiveShellUserTokenFailed<long &>(&SessionActiveShellUserToken);
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v11,
      0);
    if ( !(unsigned int)QueryUserToken(v12, &v11) )
    {
      v10 = 175;
      goto LABEL_25;
    }
LABEL_27:
    *v17 = 1;
    v13 = ImpersonationHelper::ImpersonateForUser__lambda_29ff707b0510d07872327b8c2c810b9b____(v11);
    if ( (v13 & 0x80000000) == 0 )
      *v16 = 1;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
    return v13;
  }
  v20 = 0;
  memset(v19, 0, sizeof(v19));
  v5 = AutoAdjustPrivilege::SetPrivilegeValue((AutoAdjustPrivilege *)v19, v4);
  LastError = v5;
  if ( v5 < 0 )
  {
    v7 = 119;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\flighting\\flightSettings\\broker\\libs\\inc\\ImpersonationHelper.h",
      (const char *)(unsigned int)v5,
      (int)v11);
    AutoAdjustPrivilege::Reset((AutoAdjustPrivilege *)v19);
    return LastError;
  }
  v5 = AutoAdjustPrivilege::Enable((AutoAdjustPrivilege *)v19);
  LastError = v5;
  if ( v5 < 0 )
  {
    v7 = 120;
    goto LABEL_8;
  }
  v18[0] = &v17;
  v18[1] = a3;
  v18[2] = &v16;
  v18[3] = &v13;
  v5 = ImpersonationHelper::EnumSessions__lambda_2d5f8b3289361d52d739f979f3cd1c61___(v18);
  LastError = v5;
  if ( v5 < 0 )
  {
    v7 = 141;
    goto LABEL_8;
  }
  AutoAdjustPrivilege::Reset((AutoAdjustPrivilege *)v19);
  return v13;
}

```

## disassembly

```asm
0x18002a6b0  push    rbp
0x18002a6b2  push    rbx
0x18002a6b3  push    rdi
0x18002a6b4  lea     rbp, [rsp-47h]
0x18002a6b9  sub     rsp, 0A0h
0x18002a6c0  mov     rax, cs:__security_cookie
0x18002a6c7  xor     rax, rsp
0x18002a6ca  mov     [rbp+57h+var_20], rax
0x18002a6ce  mov     rdi, r8
0x18002a6d1  mov     [rbp+57h+var_70], rcx
0x18002a6d5  mov     [rbp+57h+var_78], rdx
0x18002a6d9  mov     qword ptr [rcx], 0
0x18002a6e0  mov     rax, [rbp+57h+var_78]
0x18002a6e4  mov     qword ptr [rax], 0
0x18002a6eb  mov     [rbp+57h+var_84], 0
0x18002a6f2  call    IsWTSEnumerateSessionsWPresent
0x18002a6f7  test    al, al
0x18002a6f9  jz      loc_18002A7A2
0x18002a6ff  mov     [rbp+57h+var_28], 0
0x18002a706  xorps   xmm0, xmm0
0x18002a709  movups  [rbp+57h+var_48], xmm0
0x18002a70d  xorps   xmm1, xmm1
0x18002a710  movups  [rbp+57h+var_38], xmm1
0x18002a714  lea     rcx, [rbp+57h+var_48]; this
0x18002a718  call    ?SetPrivilegeValue@AutoAdjustPrivilege@@QEAAJPEBG@Z; AutoAdjustPrivilege::SetPrivilegeValue(ushort const *)
0x18002a71d  mov     ebx, eax
0x18002a71f  test    eax, eax
0x18002a721  jns     short loc_18002A72A
0x18002a723  mov     edx, 77h ; 'w'
0x18002a728  jmp     short loc_18002A770
0x18002a72a  lea     rcx, [rbp+57h+var_48]; this
0x18002a72e  call    ?Enable@AutoAdjustPrivilege@@QEAAJXZ; AutoAdjustPrivilege::Enable(void)
0x18002a733  mov     ebx, eax
0x18002a735  test    eax, eax
0x18002a737  jns     short loc_18002A740
0x18002a739  mov     edx, 78h ; 'x'
0x18002a73e  jmp     short loc_18002A770
0x18002a740  lea     rax, [rbp+57h+var_70]
0x18002a744  mov     [rbp+57h+var_68], rax
0x18002a748  mov     [rbp+57h+var_60], rdi
0x18002a74c  lea     rax, [rbp+57h+var_78]
0x18002a750  mov     [rbp+57h+var_58], rax
0x18002a754  lea     rax, [rbp+57h+var_84]
0x18002a758  mov     [rbp+57h+var_50], rax
0x18002a75c  lea     rcx, [rbp+57h+var_68]
0x18002a760  call    ImpersonationHelper__EnumSessions__lambda_2d5f8b3289361d52d739f979f3cd1c61___
0x18002a765  mov     ebx, eax
0x18002a767  test    eax, eax
0x18002a769  jns     short loc_18002A794
0x18002a76b  mov     edx, 8Dh; void *
0x18002a770  mov     r9d, eax; char *
0x18002a773  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x18002a77a  mov     rcx, [rbp+5Fh]; this
0x18002a77e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a783  nop
0x18002a784  lea     rcx, [rbp+57h+var_48]; this
0x18002a788  call    ?Reset@AutoAdjustPrivilege@@AEAAJXZ; AutoAdjustPrivilege::Reset(void)
0x18002a78d  mov     eax, ebx
0x18002a78f  jmp     loc_18002A8D8
0x18002a794  lea     rcx, [rbp+57h+var_48]; this
0x18002a798  call    ?Reset@AutoAdjustPrivilege@@AEAAJXZ; AutoAdjustPrivilege::Reset(void)
0x18002a79d  jmp     loc_18002A8D5
0x18002a7a2  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x18002a7a7  test    al, al
0x18002a7a9  jz      loc_18002A8D5
0x18002a7af  call    IsQueryActiveSessionPresent
0x18002a7b4  test    al, al
0x18002a7b6  jz      loc_18002A8D5
0x18002a7bc  call    IsQueryActiveSessionPresent
0x18002a7c1  test    al, al
0x18002a7c3  jz      loc_18002A8D5
0x18002a7c9  mov     [rbp+57h+var_88], 0
0x18002a7d0  mov     [rbp+57h+var_90], 0
0x18002a7d8  lea     rcx, [rbp+57h+var_88]
0x18002a7dc  call    cs:__imp_QueryActiveSession
0x18002a7e2  test    eax, eax
0x18002a7e4  jnz     short loc_18002A7F0
0x18002a7e6  mov     edx, 94h
0x18002a7eb  jmp     loc_18002A88B
0x18002a7f0  mov     [rbp+57h+var_80], 0
0x18002a7f7  xor     r8d, r8d
0x18002a7fa  lea     rdx, [rbp+57h+var_80]
0x18002a7fe  xor     ecx, ecx
0x18002a800  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18002a806  mov     ebx, 1
0x18002a80b  mov     eax, [rbp+57h+var_80]
0x18002a80e  cmp     eax, 5
0x18002a811  jz      short loc_18002A86A
0x18002a813  add     eax, 0FFFFFFF5h
0x18002a816  cmp     eax, ebx
0x18002a818  jbe     short loc_18002A86A
0x18002a81a  xor     edx, edx
0x18002a81c  lea     rcx, [rbp+57h+var_90]
0x18002a820  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002a825  lea     rdx, [rbp+57h+var_90]
0x18002a829  mov     ecx, [rbp+57h+var_88]
0x18002a82c  call    cs:__imp_UMgrGetSessionActiveShellUserToken
0x18002a832  mov     [rbp+57h+var_7C], eax
0x18002a835  test    eax, eax
0x18002a837  jns     short loc_18002A8AB
0x18002a839  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x18002a83e  test    al, al
0x18002a840  jz      short loc_18002A861
0x18002a842  xor     edx, edx
0x18002a844  lea     rcx, [rbp+57h+var_90]
0x18002a848  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002a84d  lea     rcx, [rbp+57h+var_90]; void **
0x18002a851  call    ?GetActiveUserTokenFromUserManager@ImpersonationHelper@@CAJPEAPEAX@Z; ImpersonationHelper::GetActiveUserTokenFromUserManager(void * *)
0x18002a856  mov     [rbp+57h+var_7C], eax
0x18002a859  test    eax, eax
0x18002a85b  js      short loc_18002A861
0x18002a85d  xor     ebx, ebx
0x18002a85f  jmp     short loc_18002A89D
0x18002a861  lea     rcx, [rbp+57h+var_7C]
0x18002a865  call    ??$UMgrGetSessionActiveShellUserTokenFailed@AEAJ@FlightSettingsAPITelemetryClass@@SAXAEAJ@Z; FlightSettingsAPITelemetryClass::UMgrGetSessionActiveShellUserTokenFailed<long &>(long &)
0x18002a86a  xor     edx, edx
0x18002a86c  lea     rcx, [rbp+57h+var_90]
0x18002a870  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002a875  lea     rdx, [rbp+57h+var_90]
0x18002a879  mov     ecx, [rbp+57h+var_88]
0x18002a87c  call    cs:__imp_QueryUserToken
0x18002a882  test    eax, eax
0x18002a884  jnz     short loc_18002A8AB
0x18002a886  mov     edx, 0AFh; void *
0x18002a88b  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x18002a892  mov     rcx, [rbp+5Fh]; this
0x18002a896  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a89b  mov     ebx, eax
0x18002a89d  lea     rcx, [rbp+57h+var_90]
0x18002a8a1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a8a6  jmp     loc_18002A78D
0x18002a8ab  mov     rax, [rbp+57h+var_70]
0x18002a8af  mov     [rax], rbx
0x18002a8b2  mov     rdx, rdi
0x18002a8b5  mov     rcx, [rbp+57h+var_90]; void *
0x18002a8b9  call    ImpersonationHelper__ImpersonateForUser__lambda_29ff707b0510d07872327b8c2c810b9b____
0x18002a8be  mov     [rbp+57h+var_84], eax
0x18002a8c1  test    eax, eax
0x18002a8c3  js      short loc_18002A8CC
0x18002a8c5  mov     rax, [rbp+57h+var_78]
0x18002a8c9  mov     [rax], rbx
0x18002a8cc  lea     rcx, [rbp+57h+var_90]
0x18002a8d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002a8d5  mov     eax, [rbp+57h+var_84]
0x18002a8d8  mov     rcx, [rbp+57h+var_20]
0x18002a8dc  xor     rcx, rsp; StackCookie
0x18002a8df  call    __security_check_cookie
0x18002a8e4  add     rsp, 0A0h
0x18002a8eb  pop     rdi
0x18002a8ec  pop     rbx
0x18002a8ed  pop     rbp
0x18002a8ee  retn
```
