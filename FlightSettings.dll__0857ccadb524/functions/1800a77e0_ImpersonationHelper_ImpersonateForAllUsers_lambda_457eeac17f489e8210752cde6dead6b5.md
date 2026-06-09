# ImpersonationHelper::ImpersonateForAllUsers__lambda_457eeac17f489e8210752cde6dead6b5__&_

- ea: `0x1800a77e0`
- end: `0x1800a7a1f`
- name: `ImpersonationHelper::ImpersonateForAllUsers__lambda_457eeac17f489e8210752cde6dead6b5__&_`
- size: `575`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a7e00`

## callees

- `0x180004b80`
- `0x180006690`
- `0x1800067a8`
- `0x180006938`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180017870`
- `0x18002aaa0`
- `0x18002b1b0`
- `0x18002b1f4`
- `0x18002b5a0`
- `0x18002b614`
- `0x1800a76c4`
- `0x1800a77e0`
- `0x1800a7a28`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800a7930`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800a7930`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1800a790c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1800a790c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800a79ac`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x1800a79ac`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x1800a795c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x1800a795c`

## string_xrefs

- `0x1800a78a3`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`
- `0x1800a79bb`: `onecore\base\flighting\flightSettings\broker\libs\inc\ImpersonationHelper.h`

## pseudocode

```c
__int64 __fastcall ImpersonationHelper::ImpersonateForAllUsers__lambda_457eeac17f489e8210752cde6dead6b5____(
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
    v13 = ImpersonationHelper::ImpersonateForUser__lambda_457eeac17f489e8210752cde6dead6b5____(v11);
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
  v5 = ImpersonationHelper::EnumSessions__lambda_83bf765431e3c1685c22f36bbe9f96c0___(v18);
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
0x1800a77e0  push    rbp
0x1800a77e2  push    rbx
0x1800a77e3  push    rdi
0x1800a77e4  lea     rbp, [rsp-47h]
0x1800a77e9  sub     rsp, 0A0h
0x1800a77f0  mov     rax, cs:__security_cookie
0x1800a77f7  xor     rax, rsp
0x1800a77fa  mov     [rbp+57h+var_20], rax
0x1800a77fe  mov     rdi, r8
0x1800a7801  mov     [rbp+57h+var_70], rcx
0x1800a7805  mov     [rbp+57h+var_78], rdx
0x1800a7809  mov     qword ptr [rcx], 0
0x1800a7810  mov     rax, [rbp+57h+var_78]
0x1800a7814  mov     qword ptr [rax], 0
0x1800a781b  mov     [rbp+57h+var_84], 0
0x1800a7822  call    IsWTSEnumerateSessionsWPresent
0x1800a7827  test    al, al
0x1800a7829  jz      loc_1800A78D2
0x1800a782f  mov     [rbp+57h+var_28], 0
0x1800a7836  xorps   xmm0, xmm0
0x1800a7839  movups  [rbp+57h+var_48], xmm0
0x1800a783d  xorps   xmm1, xmm1
0x1800a7840  movups  [rbp+57h+var_38], xmm1
0x1800a7844  lea     rcx, [rbp+57h+var_48]; this
0x1800a7848  call    ?SetPrivilegeValue@AutoAdjustPrivilege@@QEAAJPEBG@Z; AutoAdjustPrivilege::SetPrivilegeValue(ushort const *)
0x1800a784d  mov     ebx, eax
0x1800a784f  test    eax, eax
0x1800a7851  jns     short loc_1800A785A
0x1800a7853  mov     edx, 77h ; 'w'
0x1800a7858  jmp     short loc_1800A78A0
0x1800a785a  lea     rcx, [rbp+57h+var_48]; this
0x1800a785e  call    ?Enable@AutoAdjustPrivilege@@QEAAJXZ; AutoAdjustPrivilege::Enable(void)
0x1800a7863  mov     ebx, eax
0x1800a7865  test    eax, eax
0x1800a7867  jns     short loc_1800A7870
0x1800a7869  mov     edx, 78h ; 'x'
0x1800a786e  jmp     short loc_1800A78A0
0x1800a7870  lea     rax, [rbp+57h+var_70]
0x1800a7874  mov     [rbp+57h+var_68], rax
0x1800a7878  mov     [rbp+57h+var_60], rdi
0x1800a787c  lea     rax, [rbp+57h+var_78]
0x1800a7880  mov     [rbp+57h+var_58], rax
0x1800a7884  lea     rax, [rbp+57h+var_84]
0x1800a7888  mov     [rbp+57h+var_50], rax
0x1800a788c  lea     rcx, [rbp+57h+var_68]
0x1800a7890  call    ImpersonationHelper__EnumSessions__lambda_83bf765431e3c1685c22f36bbe9f96c0___
0x1800a7895  mov     ebx, eax
0x1800a7897  test    eax, eax
0x1800a7899  jns     short loc_1800A78C4
0x1800a789b  mov     edx, 8Dh; void *
0x1800a78a0  mov     r9d, eax; char *
0x1800a78a3  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x1800a78aa  mov     rcx, [rbp+5Fh]; this
0x1800a78ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a78b3  nop
0x1800a78b4  lea     rcx, [rbp+57h+var_48]; this
0x1800a78b8  call    ?Reset@AutoAdjustPrivilege@@AEAAJXZ; AutoAdjustPrivilege::Reset(void)
0x1800a78bd  mov     eax, ebx
0x1800a78bf  jmp     loc_1800A7A08
0x1800a78c4  lea     rcx, [rbp+57h+var_48]; this
0x1800a78c8  call    ?Reset@AutoAdjustPrivilege@@AEAAJXZ; AutoAdjustPrivilege::Reset(void)
0x1800a78cd  jmp     loc_1800A7A05
0x1800a78d2  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x1800a78d7  test    al, al
0x1800a78d9  jz      loc_1800A7A05
0x1800a78df  call    IsQueryActiveSessionPresent
0x1800a78e4  test    al, al
0x1800a78e6  jz      loc_1800A7A05
0x1800a78ec  call    IsQueryActiveSessionPresent
0x1800a78f1  test    al, al
0x1800a78f3  jz      loc_1800A7A05
0x1800a78f9  mov     [rbp+57h+var_88], 0
0x1800a7900  mov     [rbp+57h+var_90], 0
0x1800a7908  lea     rcx, [rbp+57h+var_88]
0x1800a790c  call    cs:__imp_QueryActiveSession
0x1800a7912  test    eax, eax
0x1800a7914  jnz     short loc_1800A7920
0x1800a7916  mov     edx, 94h
0x1800a791b  jmp     loc_1800A79BB
0x1800a7920  mov     [rbp+57h+var_80], 0
0x1800a7927  xor     r8d, r8d
0x1800a792a  lea     rdx, [rbp+57h+var_80]
0x1800a792e  xor     ecx, ecx
0x1800a7930  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800a7936  mov     ebx, 1
0x1800a793b  mov     eax, [rbp+57h+var_80]
0x1800a793e  cmp     eax, 5
0x1800a7941  jz      short loc_1800A799A
0x1800a7943  add     eax, 0FFFFFFF5h
0x1800a7946  cmp     eax, ebx
0x1800a7948  jbe     short loc_1800A799A
0x1800a794a  xor     edx, edx
0x1800a794c  lea     rcx, [rbp+57h+var_90]
0x1800a7950  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800a7955  lea     rdx, [rbp+57h+var_90]
0x1800a7959  mov     ecx, [rbp+57h+var_88]
0x1800a795c  call    cs:__imp_UMgrGetSessionActiveShellUserToken
0x1800a7962  mov     [rbp+57h+var_7C], eax
0x1800a7965  test    eax, eax
0x1800a7967  jns     short loc_1800A79DB
0x1800a7969  call    IsUMgrGetSessionActiveShellUserTokenPresent
0x1800a796e  test    al, al
0x1800a7970  jz      short loc_1800A7991
0x1800a7972  xor     edx, edx
0x1800a7974  lea     rcx, [rbp+57h+var_90]
0x1800a7978  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800a797d  lea     rcx, [rbp+57h+var_90]; void **
0x1800a7981  call    ?GetActiveUserTokenFromUserManager@ImpersonationHelper@@CAJPEAPEAX@Z; ImpersonationHelper::GetActiveUserTokenFromUserManager(void * *)
0x1800a7986  mov     [rbp+57h+var_7C], eax
0x1800a7989  test    eax, eax
0x1800a798b  js      short loc_1800A7991
0x1800a798d  xor     ebx, ebx
0x1800a798f  jmp     short loc_1800A79CD
0x1800a7991  lea     rcx, [rbp+57h+var_7C]
0x1800a7995  call    ??$UMgrGetSessionActiveShellUserTokenFailed@AEAJ@FlightSettingsAPITelemetryClass@@SAXAEAJ@Z; FlightSettingsAPITelemetryClass::UMgrGetSessionActiveShellUserTokenFailed<long &>(long &)
0x1800a799a  xor     edx, edx
0x1800a799c  lea     rcx, [rbp+57h+var_90]
0x1800a79a0  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800a79a5  lea     rdx, [rbp+57h+var_90]
0x1800a79a9  mov     ecx, [rbp+57h+var_88]
0x1800a79ac  call    cs:__imp_QueryUserToken
0x1800a79b2  test    eax, eax
0x1800a79b4  jnz     short loc_1800A79DB
0x1800a79b6  mov     edx, 0AFh; void *
0x1800a79bb  lea     r8, aOnecoreBaseFli_0; "onecore\\base\\flighting\\flightSetting"...
0x1800a79c2  mov     rcx, [rbp+5Fh]; this
0x1800a79c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a79cb  mov     ebx, eax
0x1800a79cd  lea     rcx, [rbp+57h+var_90]
0x1800a79d1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a79d6  jmp     loc_1800A78BD
0x1800a79db  mov     rax, [rbp+57h+var_70]
0x1800a79df  mov     [rax], rbx
0x1800a79e2  mov     rdx, rdi
0x1800a79e5  mov     rcx, [rbp+57h+var_90]; void *
0x1800a79e9  call    ImpersonationHelper__ImpersonateForUser__lambda_457eeac17f489e8210752cde6dead6b5____
0x1800a79ee  mov     [rbp+57h+var_84], eax
0x1800a79f1  test    eax, eax
0x1800a79f3  js      short loc_1800A79FC
0x1800a79f5  mov     rax, [rbp+57h+var_78]
0x1800a79f9  mov     [rax], rbx
0x1800a79fc  lea     rcx, [rbp+57h+var_90]
0x1800a7a00  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a7a05  mov     eax, [rbp+57h+var_84]
0x1800a7a08  mov     rcx, [rbp+57h+var_20]
0x1800a7a0c  xor     rcx, rsp; StackCookie
0x1800a7a0f  call    __security_check_cookie
0x1800a7a14  add     rsp, 0A0h
0x1800a7a1b  pop     rdi
0x1800a7a1c  pop     rbx
0x1800a7a1d  pop     rbp
0x1800a7a1e  retn
```
