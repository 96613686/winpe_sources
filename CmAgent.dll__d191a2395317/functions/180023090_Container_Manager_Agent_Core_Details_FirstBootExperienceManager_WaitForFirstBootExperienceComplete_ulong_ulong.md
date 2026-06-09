# Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForFirstBootExperienceComplete(ulong,ulong,bool &)

- ea: `0x180023090`
- end: `0x180023570`
- name: `?WaitForFirstBootExperienceComplete@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@QEAAJKKAEA_N@Z`
- size: `1248`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core::Details::FirstBootExperienceManager *__hidden this, unsigned int, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800052f0`

## callees

- `0x1800045e4`
- `0x18000892c`
- `0x18000b5b0`
- `0x18000b820`
- `0x18000b894`
- `0x180011ea4`
- `0x180020308`
- `0x180023090`
- `0x180023578`
- `0x180024080`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800230bf`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800230bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800231e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002321f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023289`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800232ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023550`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800231e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002321f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023289`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800232ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023352`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800233f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023432`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023447`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023550`

## string_xrefs

- `0x180023524`: `DisableAppInstallsOnFirstLogon`
- `0x18002323a`: `SYSTEM\ControlSet001\Control\Winlogon\Notifications\Components\CmAgent`
- `0x180023307`: `SYSTEM\ControlSet001\Services\sppsvc`
- `0x18002336d`: `SYSTEM\ControlSet001\Services\edgeupdate`
- `0x1800233be`: `SYSTEM\ControlSet001\Services\edgeupdatem`
- `0x1800230e7`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x180023128`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x1800231c9`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`
- `0x1800233d9`: `onecore\base\gendrv\silos\clem\agent\core\lib\firstbootexperience.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForFirstBootExperienceComplete(
        Container::Manager::Agent::Core::Details::FirstBootExperienceManager *this,
        unsigned int a2,
        int a3,
        bool *a4)
{
  _DWORD *v5; // rcx
  int v7; // ebx
  __int64 v8; // rdx
  int v10; // eax
  unsigned int *v11; // rdx
  __int64 v12; // rcx
  bool v13; // di
  __int64 v14; // rdx
  HKEY v15; // rcx
  HKEY v16; // rcx
  HKEY v17; // rcx
  HKEY v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  const unsigned __int16 *v21; // rdx
  bool *v22; // r9
  Csl *v23; // rcx
  __int64 v24; // rcx
  HKEY v25; // rcx
  HKEY v26; // rcx
  HKEY v27[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF
  unsigned int v30; // [rsp+68h] [rbp+38h] BYREF
  int v31; // [rsp+70h] [rbp+40h] BYREF

  v31 = a3;
  v30 = a2;
  v5 = (_DWORD *)((char *)this + 32);
  *v5 = 1;
  WakeByAddressAll(v5);
  v7 = Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(
         (char *)this + 20,
         &v30);
  if ( v7 < 0 )
  {
    v8 = 196;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v7);
    return (unsigned int)v7;
  }
  v7 = *((_DWORD *)this + 4);
  if ( v7 < 0 )
  {
    v8 = 197;
    goto LABEL_3;
  }
  v10 = Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForWnf(
          this,
          &WNF_SHEL_LOGON_COMPLETE,
          &v30);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v10);
    v8 = 200;
    goto LABEL_3;
  }
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
    (char *)this + 40,
    0);
  v7 = Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForWnf(
         this,
         &WNF_SHEL_OOBE_USER_LOGON_COMPLETE,
         &v30);
  if ( v7 < 0 )
  {
    v8 = 203;
    goto LABEL_3;
  }
  v7 = Container::Manager::Agent::Core::WaitForSystemQuiesce((Container::Manager::Agent::Core *)&v31, v11);
  if ( v7 == -2147023436 )
  {
    v13 = 1;
  }
  else
  {
    if ( v7 < 0 )
    {
      v8 = 217;
      goto LABEL_3;
    }
    v13 = 0;
  }
  hKey = 0;
  v7 = Csl::OpenRegistryKey(v12, L"SYSTEM\\ControlSet001\\Control\\Containers", 0x2001Fu, (char *)&hKey);
  if ( v7 < 0 )
  {
    v14 = 229;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v7);
LABEL_19:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v7;
  }
  v7 = Csl::RegistryKey::SetDwordValue(&hKey, L"FirstBootExperienceEnabled", 0);
  if ( v7 < 0 )
  {
    v14 = 231;
    goto LABEL_18;
  }
  v15 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v7 = Csl::OpenRegistryKey(
         (__int64)v15,
         L"SYSTEM\\ControlSet001\\Control\\Winlogon\\Notifications\\Components\\CmAgent",
         0x2001Fu,
         (char *)&hKey);
  if ( v7 < 0 )
  {
    v14 = 241;
    goto LABEL_18;
  }
  v7 = Csl::RegistryKey::SetStringValue(&hKey, L"Events", (const BYTE *)&qword_18003F6C0, 1);
  if ( v7 < 0 )
  {
    v14 = 243;
    goto LABEL_18;
  }
  v16 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v7 = Csl::OpenRegistryKey((__int64)v16, L"SYSTEM\\ControlSet001\\Control\\Session Manager", 0x2001Fu, (char *)&hKey);
  if ( v7 < 0 )
  {
    v14 = 252;
    goto LABEL_18;
  }
  v7 = Csl::RegistryKey::SetDwordValue(&hKey, L"NumberOfInitialSessions", 1);
  if ( v7 < 0 )
  {
    v14 = 254;
    goto LABEL_18;
  }
  v17 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v7 = Csl::OpenRegistryKey((__int64)v17, L"SYSTEM\\ControlSet001\\Services\\sppsvc", 0x2001Fu, (char *)&hKey);
  if ( v7 < 0 )
  {
    v14 = 266;
    goto LABEL_18;
  }
  v7 = Csl::RegistryKey::SetDwordValue(&hKey, L"Start", 4);
  if ( v7 < 0 )
  {
    v14 = 268;
    goto LABEL_18;
  }
  v18 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v7 = Csl::OpenRegistryKey((__int64)v18, L"SYSTEM\\ControlSet001\\Services\\edgeupdate", 0x2001Fu, (char *)&hKey);
  if ( v7 < 0 )
  {
    v14 = 279;
    goto LABEL_18;
  }
  v7 = Csl::RegistryKey::SetDwordValue(&hKey, L"Start", 4);
  if ( v7 < 0 )
  {
    v14 = 281;
    goto LABEL_18;
  }
  v27[0] = 0;
  v7 = Csl::OpenRegistryKey(v19, L"SYSTEM\\ControlSet001\\Services\\edgeupdatem", 0x2001Fu, (char *)v27);
  if ( v7 < 0 )
  {
    v20 = 287;
    goto LABEL_49;
  }
  v7 = Csl::RegistryKey::SetDwordValue(v27, L"Start", 4);
  if ( v7 < 0 )
  {
    v20 = 289;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\firstbootexperience.cpp",
      (const char *)(unsigned int)v7);
    if ( v27[0] )
      RegCloseKey(v27[0]);
    goto LABEL_19;
  }
  if ( v27[0] )
    RegCloseKey(v27[0]);
  v23 = (Csl *)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  LOBYTE(hKey) = 0;
  v7 = Csl::RemoveUserFromGroup(v23, v21, (unsigned __int16 *)&hKey, v22);
  if ( v7 < 0 )
  {
    v8 = 298;
    goto LABEL_3;
  }
  hKey = 0;
  v7 = Csl::OpenRegistryKey(v24, L"SYSTEM\\ControlSet001\\Control\\Hvsi", 0x2001Fu, (char *)&hKey);
  if ( v7 < 0 )
  {
    v14 = 310;
    goto LABEL_18;
  }
  v7 = Csl::RegistryKey::SetDwordValue(&hKey, L"IsHvsiLogon", 1);
  if ( v7 < 0 )
  {
    v14 = 311;
    goto LABEL_18;
  }
  v25 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  v7 = Csl::OpenRegistryKey(
         (__int64)v25,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Explorer",
         0x2001Fu,
         (char *)&hKey);
  if ( v7 < 0 )
  {
    v14 = 322;
    goto LABEL_18;
  }
  v7 = Csl::RegistryKey::SetDwordValue(&hKey, L"ActiveSetupDisabled", 1);
  if ( v7 < 0 )
  {
    v14 = 324;
    goto LABEL_18;
  }
  v7 = Csl::RegistryKey::SetDwordValue(&hKey, L"DisableAppInstallsOnFirstLogon", 1);
  if ( v7 < 0 )
  {
    v14 = 325;
    goto LABEL_18;
  }
  v26 = hKey;
  *a4 = v13;
  if ( v26 )
    RegCloseKey(v26);
  return 0;
}

```

## disassembly

```asm
0x180023090  mov     [rsp-28h+arg_18], rbx
0x180023095  mov     [rsp-28h+arg_10], r8d
0x18002309a  mov     [rsp-28h+arg_8], edx
0x18002309e  push    rbp
0x18002309f  push    rsi
0x1800230a0  push    rdi
0x1800230a1  push    r12
0x1800230a3  push    r15
0x1800230a5  mov     rbp, rsp
0x1800230a8  sub     rsp, 30h
0x1800230ac  mov     rdi, rcx
0x1800230af  mov     r12d, 1
0x1800230b5  add     rcx, 20h ; ' '; Address
0x1800230b9  mov     rsi, r9
0x1800230bc  mov     [rcx], r12d
0x1800230bf  call    cs:__imp_WakeByAddressAll
0x1800230c6  nop     dword ptr [rax+rax+00h]
0x1800230cb  lea     rcx, [rdi+14h]; Address
0x1800230cf  lea     rdx, [rbp+arg_8]
0x1800230d3  call    ??$WaitOnEventAndUpdateTimeout@V?$slim_event_t@$00@wil@@@Details@Core@Agent@Manager@Container@@YAJAEAV?$slim_event_t@$00@wil@@AEAK@Z; Container::Manager::Agent::Core::Details::WaitOnEventAndUpdateTimeout<wil::slim_event_t<1>>(wil::slim_event_t<1> &,ulong &)
0x1800230d8  mov     ebx, eax
0x1800230da  test    eax, eax
0x1800230dc  jns     short loc_1800230FD
0x1800230de  mov     edx, 0C4h; void *
0x1800230e3  mov     rcx, [rbp+28h]; this
0x1800230e7  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800230ee  mov     r9d, ebx; char *
0x1800230f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800230f6  mov     eax, ebx
0x1800230f8  jmp     loc_18002355E
0x1800230fd  mov     ebx, [rdi+10h]
0x180023100  test    ebx, ebx
0x180023102  jns     short loc_18002310B
0x180023104  mov     edx, 0C5h
0x180023109  jmp     short loc_1800230E3
0x18002310b  lea     r8, [rbp+arg_8]; unsigned int *
0x18002310f  mov     rcx, rdi; this
0x180023112  lea     rdx, WNF_SHEL_LOGON_COMPLETE; struct _WNF_STATE_NAME *
0x180023119  call    ?WaitForWnf@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@AEAAJAEBU_WNF_STATE_NAME@@AEAK@Z; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForWnf(_WNF_STATE_NAME const &,ulong &)
0x18002311e  mov     ebx, eax
0x180023120  test    eax, eax
0x180023122  jns     short loc_180023143
0x180023124  mov     rcx, [rbp+28h]; this
0x180023128  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18002312f  mov     r9d, eax; char *
0x180023132  mov     edx, 165h; void *
0x180023137  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002313c  mov     edx, 0C8h
0x180023141  jmp     short loc_1800230E3
0x180023143  lea     rcx, [rdi+28h]
0x180023147  xor     edx, edx
0x180023149  call    ?Stop@?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002314e  lea     r8, [rbp+arg_8]; unsigned int *
0x180023152  mov     rcx, rdi; this
0x180023155  lea     rdx, WNF_SHEL_OOBE_USER_LOGON_COMPLETE; struct _WNF_STATE_NAME *
0x18002315c  call    ?WaitForWnf@FirstBootExperienceManager@Details@Core@Agent@Manager@Container@@AEAAJAEBU_WNF_STATE_NAME@@AEAK@Z; Container::Manager::Agent::Core::Details::FirstBootExperienceManager::WaitForWnf(_WNF_STATE_NAME const &,ulong &)
0x180023161  mov     ebx, eax
0x180023163  test    eax, eax
0x180023165  jns     short loc_180023171
0x180023167  mov     edx, 0CBh
0x18002316c  jmp     loc_1800230E3
0x180023171  lea     rcx, [rbp+arg_10]; this
0x180023175  call    ?WaitForSystemQuiesce@Core@Agent@Manager@Container@@YAJAEAK@Z; Container::Manager::Agent::Core::WaitForSystemQuiesce(ulong &)
0x18002317a  mov     ebx, eax
0x18002317c  cmp     eax, 800705B4h
0x180023181  jnz     short loc_180023188
0x180023183  mov     dil, r12b
0x180023186  jmp     short loc_180023199
0x180023188  test    ebx, ebx
0x18002318a  jns     short loc_180023196
0x18002318c  mov     edx, 0D9h
0x180023191  jmp     loc_1800230E3
0x180023196  xor     dil, dil
0x180023199  mov     r15d, 2001Fh
0x18002319f  mov     [rbp+hKey], 0
0x1800231a7  mov     r8d, r15d
0x1800231aa  lea     r9, [rbp+hKey]
0x1800231ae  lea     rdx, aSystemControls_4; "SYSTEM\\ControlSet001\\Control\\Contain"...
0x1800231b5  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800231ba  mov     ebx, eax
0x1800231bc  test    eax, eax
0x1800231be  jns     short loc_1800231F6
0x1800231c0  mov     edx, 0E5h; void *
0x1800231c5  mov     rcx, [rbp+28h]; this
0x1800231c9  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800231d0  mov     r9d, ebx; char *
0x1800231d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800231d8  mov     rcx, [rbp+hKey]; hKey
0x1800231dc  test    rcx, rcx
0x1800231df  jz      loc_1800230F6
0x1800231e5  call    cs:__imp_RegCloseKey
0x1800231ec  nop     dword ptr [rax+rax+00h]
0x1800231f1  jmp     loc_1800230F6
0x1800231f6  xor     r8d, r8d; unsigned int
0x1800231f9  lea     rdx, aFirstbootexper; "FirstBootExperienceEnabled"
0x180023200  lea     rcx, [rbp+hKey]; this
0x180023204  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180023209  mov     ebx, eax
0x18002320b  test    eax, eax
0x18002320d  jns     short loc_180023216
0x18002320f  mov     edx, 0E7h
0x180023214  jmp     short loc_1800231C5
0x180023216  mov     rcx, [rbp+hKey]; hKey
0x18002321a  test    rcx, rcx
0x18002321d  jz      short loc_18002322B
0x18002321f  call    cs:__imp_RegCloseKey
0x180023226  nop     dword ptr [rax+rax+00h]
0x18002322b  lea     r9, [rbp+hKey]
0x18002322f  mov     [rbp+hKey], 0
0x180023237  mov     r8d, r15d
0x18002323a  lea     rdx, aSystemControls_0; "SYSTEM\\ControlSet001\\Control\\Winlogo"...
0x180023241  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180023246  mov     ebx, eax
0x180023248  test    eax, eax
0x18002324a  jns     short loc_180023256
0x18002324c  mov     edx, 0F1h
0x180023251  jmp     loc_1800231C5
0x180023256  mov     r9d, r12d; unsigned int
0x180023259  lea     r8, qword_18003F6C0; unsigned __int16 *
0x180023260  lea     rdx, aEvents; "Events"
0x180023267  lea     rcx, [rbp+hKey]; this
0x18002326b  call    ?SetStringValue@RegistryKey@Csl@@QEAAJPEBG0K@Z; Csl::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x180023270  mov     ebx, eax
0x180023272  test    eax, eax
0x180023274  jns     short loc_180023280
0x180023276  mov     edx, 0F3h
0x18002327b  jmp     loc_1800231C5
0x180023280  mov     rcx, [rbp+hKey]; hKey
0x180023284  test    rcx, rcx
0x180023287  jz      short loc_180023295
0x180023289  call    cs:__imp_RegCloseKey
0x180023290  nop     dword ptr [rax+rax+00h]
0x180023295  lea     r9, [rbp+hKey]
0x180023299  mov     [rbp+hKey], 0
0x1800232a1  mov     r8d, r15d
0x1800232a4  lea     rdx, aSystemControls; "SYSTEM\\ControlSet001\\Control\\Session"...
0x1800232ab  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800232b0  mov     ebx, eax
0x1800232b2  test    eax, eax
0x1800232b4  jns     short loc_1800232C0
0x1800232b6  mov     edx, 0FCh
0x1800232bb  jmp     loc_1800231C5
0x1800232c0  mov     r8d, r12d; unsigned int
0x1800232c3  lea     rdx, aNumberofinitia; "NumberOfInitialSessions"
0x1800232ca  lea     rcx, [rbp+hKey]; this
0x1800232ce  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x1800232d3  mov     ebx, eax
0x1800232d5  test    eax, eax
0x1800232d7  jns     short loc_1800232E3
0x1800232d9  mov     edx, 0FEh
0x1800232de  jmp     loc_1800231C5
0x1800232e3  mov     rcx, [rbp+hKey]; hKey
0x1800232e7  test    rcx, rcx
0x1800232ea  jz      short loc_1800232F8
0x1800232ec  call    cs:__imp_RegCloseKey
0x1800232f3  nop     dword ptr [rax+rax+00h]
0x1800232f8  lea     r9, [rbp+hKey]
0x1800232fc  mov     [rbp+hKey], 0
0x180023304  mov     r8d, r15d
0x180023307  lea     rdx, aSystemControls_1; "SYSTEM\\ControlSet001\\Services\\sppsvc"
0x18002330e  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180023313  mov     ebx, eax
0x180023315  test    eax, eax
0x180023317  jns     short loc_180023323
0x180023319  mov     edx, 10Ah
0x18002331e  jmp     loc_1800231C5
0x180023323  mov     r8d, 4; unsigned int
0x180023329  lea     rdx, aStart; "Start"
0x180023330  lea     rcx, [rbp+hKey]; this
0x180023334  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180023339  mov     ebx, eax
0x18002333b  test    eax, eax
0x18002333d  jns     short loc_180023349
0x18002333f  mov     edx, 10Ch
0x180023344  jmp     loc_1800231C5
0x180023349  mov     rcx, [rbp+hKey]; hKey
0x18002334d  test    rcx, rcx
0x180023350  jz      short loc_18002335E
0x180023352  call    cs:__imp_RegCloseKey
0x180023359  nop     dword ptr [rax+rax+00h]
0x18002335e  lea     r9, [rbp+hKey]
0x180023362  mov     [rbp+hKey], 0
0x18002336a  mov     r8d, r15d
0x18002336d  lea     rdx, aSystemControls_3; "SYSTEM\\ControlSet001\\Services\\edgeup"...
0x180023374  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x180023379  mov     ebx, eax
0x18002337b  test    eax, eax
0x18002337d  jns     short loc_180023389
0x18002337f  mov     edx, 117h
0x180023384  jmp     loc_1800231C5
0x180023389  mov     r8d, 4; unsigned int
0x18002338f  lea     rdx, aStart; "Start"
0x180023396  lea     rcx, [rbp+hKey]; this
0x18002339a  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x18002339f  mov     ebx, eax
0x1800233a1  test    eax, eax
0x1800233a3  jns     short loc_1800233AF
0x1800233a5  mov     edx, 119h
0x1800233aa  jmp     loc_1800231C5
0x1800233af  lea     r9, [rbp+var_10]
0x1800233b3  mov     [rbp+var_10], 0
0x1800233bb  mov     r8d, r15d
0x1800233be  lea     rdx, aSystemControls_5; "SYSTEM\\ControlSet001\\Services\\edgeup"...
0x1800233c5  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800233ca  mov     ebx, eax
0x1800233cc  test    eax, eax
0x1800233ce  jns     short loc_180023406
0x1800233d0  mov     edx, 11Fh; void *
0x1800233d5  mov     rcx, [rbp+28h]; this
0x1800233d9  lea     r8, aOnecoreBaseGen_10; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x1800233e0  mov     r9d, ebx; char *
0x1800233e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800233e8  mov     rcx, [rbp+var_10]; hKey
0x1800233ec  test    rcx, rcx
0x1800233ef  jz      loc_1800231D8
0x1800233f5  call    cs:__imp_RegCloseKey
0x1800233fc  nop     dword ptr [rax+rax+00h]
0x180023401  jmp     loc_1800231D8
0x180023406  mov     r8d, 4; unsigned int
0x18002340c  lea     rdx, aStart; "Start"
0x180023413  lea     rcx, [rbp+var_10]; this
0x180023417  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x18002341c  mov     ebx, eax
0x18002341e  test    eax, eax
0x180023420  jns     short loc_180023429
0x180023422  mov     edx, 121h
0x180023427  jmp     short loc_1800233D5
0x180023429  mov     rcx, [rbp+var_10]; hKey
0x18002342d  test    rcx, rcx
0x180023430  jz      short loc_18002343E
0x180023432  call    cs:__imp_RegCloseKey
0x180023439  nop     dword ptr [rax+rax+00h]
0x18002343e  mov     rcx, [rbp+hKey]; hKey
0x180023442  test    rcx, rcx
0x180023445  jz      short loc_180023453
0x180023447  call    cs:__imp_RegCloseKey
0x18002344e  nop     dword ptr [rax+rax+00h]
0x180023453  lea     r8, [rbp+hKey]; unsigned __int16 *
0x180023457  mov     byte ptr [rbp+hKey], 0
0x18002345b  call    ?RemoveUserFromGroup@Csl@@YAJPEBG0PEA_N@Z; Csl::RemoveUserFromGroup(ushort const *,ushort const *,bool *)
0x180023460  mov     ebx, eax
0x180023462  test    eax, eax
0x180023464  jns     short loc_180023470
0x180023466  mov     edx, 12Ah
0x18002346b  jmp     loc_1800230E3
0x180023470  lea     r9, [rbp+hKey]
0x180023474  mov     [rbp+hKey], 0
0x18002347c  mov     r8d, r15d
0x18002347f  lea     rdx, aSystemControls_2; "SYSTEM\\ControlSet001\\Control\\Hvsi"
0x180023486  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x18002348b  mov     ebx, eax
0x18002348d  test    eax, eax
0x18002348f  jns     short loc_18002349B
0x180023491  mov     edx, 136h
0x180023496  jmp     loc_1800231C5
0x18002349b  mov     r8d, r12d; unsigned int
0x18002349e  lea     rdx, aIshvsilogon; "IsHvsiLogon"
0x1800234a5  lea     rcx, [rbp+hKey]; this
0x1800234a9  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x1800234ae  mov     ebx, eax
0x1800234b0  test    eax, eax
0x1800234b2  jns     short loc_1800234BE
0x1800234b4  mov     edx, 137h
0x1800234b9  jmp     loc_1800231C5
0x1800234be  mov     rcx, [rbp+hKey]; hKey
0x1800234c2  test    rcx, rcx
0x1800234c5  jz      short loc_1800234D3
0x1800234c7  call    cs:__imp_RegCloseKey
0x1800234ce  nop     dword ptr [rax+rax+00h]
0x1800234d3  lea     r9, [rbp+hKey]
0x1800234d7  mov     [rbp+hKey], 0
0x1800234df  mov     r8d, r15d
0x1800234e2  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800234e9  call    ?OpenRegistryKey@Csl@@YAJPEAUHKEY__@@PEBGW4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryKey(HKEY__ *,ushort const *,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800234ee  mov     ebx, eax
0x1800234f0  test    eax, eax
0x1800234f2  jns     short loc_1800234FE
0x1800234f4  mov     edx, 142h
0x1800234f9  jmp     loc_1800231C5
0x1800234fe  mov     r8d, r12d; unsigned int
0x180023501  lea     rdx, aActivesetupdis; "ActiveSetupDisabled"
0x180023508  lea     rcx, [rbp+hKey]; this
0x18002350c  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180023511  mov     ebx, eax
0x180023513  test    eax, eax
0x180023515  jns     short loc_180023521
0x180023517  mov     edx, 144h
0x18002351c  jmp     loc_1800231C5
0x180023521  mov     r8d, r12d; unsigned int
0x180023524  lea     rdx, aDisableappinst; "DisableAppInstallsOnFirstLogon"
0x18002352b  lea     rcx, [rbp+hKey]; this
0x18002352f  call    ?SetDwordValue@RegistryKey@Csl@@QEAAJPEBGK@Z; Csl::RegistryKey::SetDwordValue(ushort const *,ulong)
0x180023534  mov     ebx, eax
0x180023536  test    eax, eax
0x180023538  jns     short loc_180023544
0x18002353a  mov     edx, 145h
0x18002353f  jmp     loc_1800231C5
0x180023544  mov     rcx, [rbp+hKey]; hKey
0x180023548  mov     [rsi], dil
0x18002354b  test    rcx, rcx
  ... truncated ...
```
