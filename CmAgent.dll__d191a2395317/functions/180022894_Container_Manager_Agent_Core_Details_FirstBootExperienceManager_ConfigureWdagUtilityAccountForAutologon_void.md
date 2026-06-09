# Container::Manager::Agent::Core::Details::FirstBootExperienceManager::ConfigureWdagUtilityAccountForAutologon(void)

- ea: `0x180022894`
- end: `0x180022c0a`
- name: `?ConfigureWdagUtilityAccountForAutologon@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@AEAAJXZ`
- size: `886`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core::Details::FirstBootExperienceManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022d50`

## callees

- `0x180003ce4`
- `0x1800045e4`
- `0x180007b4c`
- `0x18000b5b0`
- `0x18000b820`
- `0x18000b894`
- `0x180022894`
- `0x180023844`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022a77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022bc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022a77`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022bc2`
- `samcli!NetUserSetInfo` at `0x18002290b`
- `samcli!NetUserSetInfo` at `0x180022a17`
- `samcli!NetUserSetInfo` at `0x18002290b`
- `samcli!NetUserSetInfo` at `0x180022a17`
- `samcli!NetUserGetInfo` at `0x1800228c7`
- `samcli!NetUserGetInfo` at `0x18002299b`
- `samcli!NetUserGetInfo` at `0x1800228c7`
- `samcli!NetUserGetInfo` at `0x18002299b`
- `netutils!NetApiBufferFree` at `0x18002293e`
- `netutils!NetApiBufferFree` at `0x180022976`
- `netutils!NetApiBufferFree` at `0x1800229ce`
- `netutils!NetApiBufferFree` at `0x180022bd7`
- `netutils!NetApiBufferFree` at `0x18002293e`
- `netutils!NetApiBufferFree` at `0x180022976`
- `netutils!NetApiBufferFree` at `0x1800229ce`
- `netutils!NetApiBufferFree` at `0x180022bd7`

## string_xrefs

- `0x180022952`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x1800229b4`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x180022a5b`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x180022bf8`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x180022924`: `onecore\base\gendrv\silos\csl\lib\cslsecurity.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::Details::FirstBootExperienceManager::ConfigureWdagUtilityAccountForAutologon(
        Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this)
{
  DWORD Info; // eax
  __int64 v2; // rdx
  LPBYTE v3; // rcx
  int v4; // eax
  int v5; // ebx
  DWORD v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  Csl *v11; // rcx
  bool *v12; // r9
  Csl *v13; // rcx
  bool *v14; // r9
  Csl *v15; // rcx
  bool *v16; // r9
  const char *v17; // r9
  unsigned int parm_err; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  Container::Manager::Agent::Core::Details::FirstBootExperienceManager *buf; // [rsp+50h] [rbp+20h] BYREF
  LPBYTE v21; // [rsp+58h] [rbp+28h] BYREF
  LPBYTE bufptr; // [rsp+60h] [rbp+30h] BYREF

  buf = this;
  bufptr = 0;
  Info = NetUserGetInfo(0, L"WDAGUtilityAccount", 0x17u, &bufptr);
  if ( Info )
  {
    v2 = 1343;
    goto LABEL_6;
  }
  v3 = bufptr;
  v4 = *((_DWORD *)bufptr + 6);
  if ( (v4 & 2) == 0 )
  {
LABEL_12:
    if ( v3 )
      NetApiBufferFree(v3);
    goto LABEL_14;
  }
  LODWORD(buf) = v4 & 0xFFFFFFFD;
  Info = NetUserSetInfo(0, L"WDAGUtilityAccount", 0x3F0u, (LPBYTE)&buf, 0);
  if ( !Info )
  {
    v3 = bufptr;
    goto LABEL_12;
  }
  v2 = 1358;
LABEL_6:
  v5 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v2,
         (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslsecurity.cpp",
         (const char *)Info,
         parm_err);
  if ( bufptr )
    NetApiBufferFree(bufptr);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v5,
      parm_err);
    return (unsigned int)v5;
  }
LABEL_14:
  v21 = 0;
  v7 = NetUserGetInfo(0, L"WDAGUtilityAccount", 3u, &v21);
  if ( v7 )
  {
    v8 = 545;
LABEL_16:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v8,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
           (const char *)v7,
           parm_err);
LABEL_17:
    if ( v21 )
      NetApiBufferFree(v21);
    return (unsigned int)v5;
  }
  *((_QWORD *)v21 + 1) = L"Password!";
  *((_DWORD *)v21 + 10) |= 0x10000u;
  *((_DWORD *)v21 + 44) = 0;
  v7 = NetUserSetInfo(0, L"WDAGUtilityAccount", 3u, v21, 0);
  if ( v7 )
  {
    v8 = 556;
    goto LABEL_16;
  }
  bufptr = 0;
  v5 = Csl::OpenRegistryKey(v9, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 131103, &bufptr);
  if ( v5 < 0 )
  {
    v10 = 564;
    goto LABEL_23;
  }
  v5 = Csl::RegistryKey::SetStringValue((Csl::RegistryKey *)&bufptr, L"DefaultDomainName", L"MINWINPC", 9u);
  if ( v5 < 0 )
  {
    v10 = 566;
    goto LABEL_23;
  }
  v5 = Csl::RegistryKey::SetStringValue((Csl::RegistryKey *)&bufptr, L"DefaultUserName", L"WDAGUtilityAccount", 0x13u);
  if ( v5 < 0 )
  {
    v10 = 567;
    goto LABEL_23;
  }
  v5 = Csl::RegistryKey::SetStringValue((Csl::RegistryKey *)&bufptr, L"DefaultPassword", L"Password!", 0xAu);
  if ( v5 < 0 )
  {
    v10 = 569;
    goto LABEL_23;
  }
  v5 = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&bufptr, L"ForceDefaultUserName", 1u);
  if ( v5 < 0 )
  {
    v10 = 571;
    goto LABEL_23;
  }
  v5 = Csl::RegistryKey::SetDwordValue((Csl::RegistryKey *)&bufptr, L"ForceAutologon", 1u);
  if ( v5 < 0 )
  {
    v10 = 572;
    goto LABEL_23;
  }
  LOBYTE(buf) = 0;
  v5 = Csl::AddUserToGroup(v11, L"S-1-5-32-545", (unsigned __int16 *)&buf, v12);
  if ( v5 < 0 )
  {
    v10 = 579;
    goto LABEL_23;
  }
  v5 = Csl::AddUserToGroup(v13, L"S-1-5-32-555", (unsigned __int16 *)&buf, v14);
  if ( v5 < 0 )
  {
    v10 = 582;
    goto LABEL_23;
  }
  v5 = Csl::AddUserToGroup(v15, L"S-1-5-32-544", (unsigned __int16 *)&buf, v16);
  if ( v5 < 0 )
  {
    v10 = 589;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v5,
      parm_err);
    if ( bufptr )
      RegCloseKey((HKEY)bufptr);
    goto LABEL_17;
  }
  if ( (_BYTE)buf )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x250,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      v17);
  if ( bufptr )
    RegCloseKey((HKEY)bufptr);
  if ( v21 )
    NetApiBufferFree(v21);
  return 0;
}

```

## disassembly

```asm
0x180022894  mov     [rsp-18h+arg_18], rbx
0x180022899  mov     [rsp-18h+buf], rcx
0x18002289e  push    rbp
0x18002289f  push    rsi
0x1800228a0  push    r14
0x1800228a2  mov     rbp, rsp
0x1800228a5  sub     rsp, 30h
0x1800228a9  lea     rsi, AccountName; "WDAGUtilityAccount"
0x1800228b0  mov     [rbp+bufptr], 0
0x1800228b8  mov     rdx, rsi; username
0x1800228bb  lea     r9, [rbp+bufptr]; bufptr
0x1800228bf  mov     r8d, 17h; level
0x1800228c5  xor     ecx, ecx; servername
0x1800228c7  call    cs:__imp_NetUserGetInfo
0x1800228ce  nop     dword ptr [rax+rax+00h]
0x1800228d3  test    eax, eax
0x1800228d5  jz      short loc_1800228DE
0x1800228d7  mov     edx, 53Fh
0x1800228dc  jmp     short loc_180022920
0x1800228de  mov     rcx, [rbp+bufptr]
0x1800228e2  mov     eax, [rcx+18h]
0x1800228e5  test    al, 2
0x1800228e7  jz      loc_180022971
0x1800228ed  and     eax, 0FFFFFFFDh
0x1800228f0  mov     qword ptr [rsp+30h+parm_err], 0; unsigned int
0x1800228f9  lea     r9, [rbp+buf]; buf
0x1800228fd  mov     dword ptr [rbp+buf], eax
0x180022900  mov     r8d, 3F0h; level
0x180022906  mov     rdx, rsi; username
0x180022909  xor     ecx, ecx; servername
0x18002290b  call    cs:__imp_NetUserSetInfo
0x180022912  nop     dword ptr [rax+rax+00h]
0x180022917  test    eax, eax
0x180022919  jz      short loc_18002296D
0x18002291b  mov     edx, 54Eh; void *
0x180022920  mov     rcx, [rbp+18h]; this
0x180022924  lea     r8, aOnecoreBaseGen_11; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18002292b  mov     r9d, eax; char *
0x18002292e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180022933  mov     rcx, [rbp+bufptr]; Buffer
0x180022937  mov     ebx, eax
0x180022939  test    rcx, rcx
0x18002293c  jz      short loc_18002294A
0x18002293e  call    cs:__imp_NetApiBufferFree
0x180022945  nop     dword ptr [rax+rax+00h]
0x18002294a  test    ebx, ebx
0x18002294c  jns     short loc_180022982
0x18002294e  mov     rcx, [rbp+18h]; this
0x180022952  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180022959  mov     r9d, ebx; char *
0x18002295c  mov     edx, 21Ah; void *
0x180022961  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022966  mov     eax, ebx
0x180022968  jmp     loc_180022BE5
0x18002296d  mov     rcx, [rbp+bufptr]; Buffer
0x180022971  test    rcx, rcx
0x180022974  jz      short loc_180022982
0x180022976  call    cs:__imp_NetApiBufferFree
0x18002297d  nop     dword ptr [rax+rax+00h]
0x180022982  mov     ebx, 3
0x180022987  mov     [rbp+arg_8], 0
0x18002298f  mov     r8d, ebx; level
0x180022992  lea     r9, [rbp+arg_8]; bufptr
0x180022996  mov     rdx, rsi; username
0x180022999  xor     ecx, ecx; servername
0x18002299b  call    cs:__imp_NetUserGetInfo
0x1800229a2  nop     dword ptr [rax+rax+00h]
0x1800229a7  test    eax, eax
0x1800229a9  jz      short loc_1800229DC
0x1800229ab  mov     edx, 221h; void *
0x1800229b0  mov     rcx, [rbp+18h]; this
0x1800229b4  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800229bb  mov     r9d, eax; char *
0x1800229be  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800229c3  mov     ebx, eax
0x1800229c5  mov     rcx, [rbp+arg_8]; Buffer
0x1800229c9  test    rcx, rcx
0x1800229cc  jz      short loc_180022966
0x1800229ce  call    cs:__imp_NetApiBufferFree
0x1800229d5  nop     dword ptr [rax+rax+00h]
0x1800229da  jmp     short loc_180022966
0x1800229dc  mov     rax, [rbp+arg_8]
0x1800229e0  lea     r14, aPassword; "Password!"
0x1800229e7  mov     r8d, ebx; level
0x1800229ea  mov     qword ptr [rsp+30h+parm_err], 0; int
0x1800229f3  mov     rdx, rsi; username
0x1800229f6  xor     ecx, ecx; servername
0x1800229f8  mov     [rax+8], r14
0x1800229fc  mov     rax, [rbp+arg_8]
0x180022a00  bts     dword ptr [rax+28h], 10h
0x180022a05  mov     rax, [rbp+arg_8]
0x180022a09  mov     dword ptr [rax+0B0h], 0
0x180022a13  mov     r9, [rbp+arg_8]; buf
0x180022a17  call    cs:__imp_NetUserSetInfo
0x180022a1e  nop     dword ptr [rax+rax+00h]
0x180022a23  test    eax, eax
0x180022a25  jz      short loc_180022A2E
0x180022a27  mov     edx, 22Ch
0x180022a2c  jmp     short loc_1800229B0
0x180022a2e  lea     r9, [rbp+bufptr]
0x180022a32  mov     [rbp+bufptr], 0
0x180022a3a  mov     r8d, 2001Fh
0x180022a40  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180022a47  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180022a4c  mov     ebx, eax
0x180022a4e  test    eax, eax
0x180022a50  jns     short loc_180022A88
0x180022a52  mov     edx, 234h; void *
0x180022a57  mov     rcx, [rbp+18h]; this
0x180022a5b  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180022a62  mov     r9d, ebx; char *
0x180022a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a6a  mov     rcx, [rbp+bufptr]; hKey
0x180022a6e  test    rcx, rcx
0x180022a71  jz      loc_1800229C5
0x180022a77  call    cs:__imp_RegCloseKey
0x180022a7e  nop     dword ptr [rax+rax+00h]
0x180022a83  jmp     loc_1800229C5
0x180022a88  mov     r9d, 9; unsigned int
0x180022a8e  lea     r8, aMinwinpc; "MINWINPC"
0x180022a95  lea     rdx, aDefaultdomainn; "DefaultDomainName"
0x180022a9c  lea     rcx, [rbp+bufptr]; this
0x180022aa0  call    ?SetStringValue@RegistryKey@Csl@@QEAAJPEBG0K@Z; Csl::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180022aa5  mov     ebx, eax
0x180022aa7  test    eax, eax
0x180022aa9  jns     short loc_180022AB2
0x180022aab  mov     edx, 236h
0x180022ab0  jmp     short loc_180022A57
0x180022ab2  mov     r9d, 13h; unsigned int
0x180022ab8  lea     rdx, aDefaultusernam; "DefaultUserName"
0x180022abf  mov     r8, rsi; unsigned __int16 *
0x180022ac2  lea     rcx, [rbp+bufptr]; this
0x180022ac6  call    ?SetStringValue@RegistryKey@Csl@@QEAAJPEBG0K@Z; Csl::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180022acb  mov     ebx, eax
0x180022acd  test    eax, eax
0x180022acf  jns     short loc_180022ADB
0x180022ad1  mov     edx, 237h
0x180022ad6  jmp     loc_180022A57
0x180022adb  mov     r9d, 0Ah; unsigned int
0x180022ae1  lea     rdx, aDefaultpasswor; "DefaultPassword"
0x180022ae8  mov     r8, r14; unsigned __int16 *
0x180022aeb  lea     rcx, [rbp+bufptr]; this
0x180022aef  call    ?SetStringValue@RegistryKey@Csl@@QEAAJPEBG0K@Z; Csl::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180022af4  mov     ebx, eax
0x180022af6  test    eax, eax
0x180022af8  jns     short loc_180022B04
0x180022afa  mov     edx, 239h
0x180022aff  jmp     loc_180022A57
0x180022b04  mov     esi, 1
0x180022b09  lea     rdx, aForcedefaultus; "ForceDefaultUserName"
0x180022b10  mov     r8d, esi; unsigned int
0x180022b13  lea     rcx, [rbp+bufptr]; this
0x180022b17  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180022b1c  mov     ebx, eax
0x180022b1e  test    eax, eax
0x180022b20  jns     short loc_180022B2C
0x180022b22  mov     edx, 23Bh
0x180022b27  jmp     loc_180022A57
0x180022b2c  mov     r8d, esi; unsigned int
0x180022b2f  lea     rdx, aForceautologon; "ForceAutologon"
0x180022b36  lea     rcx, [rbp+bufptr]; this
0x180022b3a  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180022b3f  mov     ebx, eax
0x180022b41  test    eax, eax
0x180022b43  jns     short loc_180022B4F
0x180022b45  mov     edx, 23Ch
0x180022b4a  jmp     loc_180022A57
0x180022b4f  lea     r8, [rbp+buf]; unsigned __int16 *
0x180022b53  mov     byte ptr [rbp+buf], 0
0x180022b57  lea     rdx, aS1532545; "S-1-5-32-545"
0x180022b5e  call    ?AddUserToGroup@Csl@@YAJPEBG0PEA_N@Z; Csl::AddUserToGroup(ushort const *,ushort const *,bool *)
0x180022b63  mov     ebx, eax
0x180022b65  test    eax, eax
0x180022b67  jns     short loc_180022B73
0x180022b69  mov     edx, 243h
0x180022b6e  jmp     loc_180022A57
0x180022b73  lea     r8, [rbp+buf]; unsigned __int16 *
0x180022b77  lea     rdx, aS1532555; "S-1-5-32-555"
0x180022b7e  call    ?AddUserToGroup@Csl@@YAJPEBG0PEA_N@Z; Csl::AddUserToGroup(ushort const *,ushort const *,bool *)
0x180022b83  mov     ebx, eax
0x180022b85  test    eax, eax
0x180022b87  jns     short loc_180022B93
0x180022b89  mov     edx, 246h
0x180022b8e  jmp     loc_180022A57
0x180022b93  lea     r8, [rbp+buf]; unsigned __int16 *
0x180022b97  lea     rdx, aS1532544; "S-1-5-32-544"
0x180022b9e  call    ?AddUserToGroup@Csl@@YAJPEBG0PEA_N@Z; Csl::AddUserToGroup(ushort const *,ushort const *,bool *)
0x180022ba3  mov     ebx, eax
0x180022ba5  test    eax, eax
0x180022ba7  jns     short loc_180022BB3
0x180022ba9  mov     edx, 24Dh
0x180022bae  jmp     loc_180022A57
0x180022bb3  cmp     byte ptr [rbp+buf], 0
0x180022bb7  jnz     short loc_180022BF4
0x180022bb9  mov     rcx, [rbp+bufptr]; hKey
0x180022bbd  test    rcx, rcx
0x180022bc0  jz      short loc_180022BCE
0x180022bc2  call    cs:__imp_RegCloseKey
0x180022bc9  nop     dword ptr [rax+rax+00h]
0x180022bce  mov     rcx, [rbp+arg_8]; Buffer
0x180022bd2  test    rcx, rcx
0x180022bd5  jz      short loc_180022BE3
0x180022bd7  call    cs:__imp_NetApiBufferFree
0x180022bde  nop     dword ptr [rax+rax+00h]
0x180022be3  xor     eax, eax
0x180022be5  mov     rbx, [rsp+30h+arg_18]
0x180022bea  add     rsp, 30h
0x180022bee  pop     r14
0x180022bf0  pop     rsi
0x180022bf1  pop     rbp
0x180022bf2  retn
0x180022bf4  mov     rcx, [rbp+18h]; this
0x180022bf8  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x180022bff  mov     edx, 250h; void *
0x180022c04  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
