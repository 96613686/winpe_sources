# ConfigurePowerSettingsTask::Execute(void)

- ea: `0x18002a4e0`
- end: `0x18002a786`
- name: `?Execute@ConfigurePowerSettingsTask@@MEAAXXZ`
- size: `678`
- prototype: `void __fastcall(ConfigurePowerSettingsTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180007d5c`
- `0x180022484`
- `0x18002a414`
- `0x18002a4e0`
- `0x180050010`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18002a512`
- `api-ms-win-power-setting-l1-1-0!PowerGetActiveScheme` at `0x18002a512`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002a565`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002a5ee`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002a6ef`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002a565`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002a5ee`
- `api-ms-win-power-setting-l1-1-0!PowerWriteACValueIndex` at `0x18002a6ef`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002a5af`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002a611`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002a683`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002a5af`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002a611`
- `api-ms-win-power-setting-l1-1-0!PowerWriteDCValueIndex` at `0x18002a683`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x18002a718`
- `api-ms-win-power-setting-l1-1-0!PowerSetActiveScheme` at `0x18002a718`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x18002a65a`
- `POWRPROF!PowerReadDCDefaultIndex` at `0x18002a65a`
- `POWRPROF!PowerReadACDefaultIndex` at `0x18002a6c6`
- `POWRPROF!PowerReadACDefaultIndex` at `0x18002a6c6`

## string_xrefs

- `0x18002a523`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`
- `0x18002a576`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`
- `0x18002a5c0`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`
- `0x18002a694`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`
- `0x18002a700`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`
- `0x18002a729`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`
- `0x18002a75f`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`
- `0x18002a774`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\configurepowersettingstask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConfigurePowerSettingsTask::Execute(ConfigurePowerSettingsTask *this)
{
  DWORD ActiveScheme; // eax
  DWORD v3; // eax
  DWORD v4; // eax
  DWORD v5; // eax
  DWORD v6; // eax
  const GUID **v7; // rbx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD active; // eax
  void *v13; // rdx
  GUID *v14; // rcx
  unsigned int AcValueIndex; // [rsp+20h] [rbp-30h]
  unsigned int AcValueIndexa; // [rsp+20h] [rbp-30h]
  unsigned int AcValueIndexb; // [rsp+20h] [rbp-30h]
  unsigned int AcValueIndexc; // [rsp+20h] [rbp-30h]
  unsigned int AcValueIndexd; // [rsp+20h] [rbp-30h]
  unsigned int AcValueIndexe; // [rsp+20h] [rbp-30h]
  unsigned int AcValueIndexf; // [rsp+20h] [rbp-30h]
  GUID **p_SchemeGuid; // [rsp+30h] [rbp-20h] BYREF
  GUID *ActivePolicyGuid; // [rsp+38h] [rbp-18h] BYREF
  char v24; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  DWORD DcDefaultIndex; // [rsp+68h] [rbp+18h] BYREF
  DWORD AcDefaultIndex; // [rsp+70h] [rbp+20h] BYREF
  GUID *SchemeGuid; // [rsp+78h] [rbp+28h] BYREF

  SchemeGuid = 0;
  p_SchemeGuid = &SchemeGuid;
  ActivePolicyGuid = 0;
  v24 = 1;
  ActiveScheme = PowerGetActiveScheme(0, &ActivePolicyGuid);
  if ( ActiveScheme )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x19,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
      (const char *)ActiveScheme,
      AcValueIndex);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<_GUID,wil::process_heap_deleter>>(&p_SchemeGuid);
  v3 = (***((__int64 (__fastcall ****)(_QWORD))this + 10))(*((_QWORD *)this + 10));
  v4 = PowerWriteACValueIndex(
         0,
         SchemeGuid,
         &GUID_ADAPTIVE_POWER_BEHAVIOR_SUBGROUP,
         &GUID_NON_ADAPTIVE_INPUT_TIMEOUT,
         v3);
  if ( v4 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1A,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
      (const char *)v4,
      AcValueIndexa);
  v5 = (***((__int64 (__fastcall ****)(_QWORD))this + 10))(*((_QWORD *)this + 10));
  v6 = PowerWriteDCValueIndex(
         0,
         SchemeGuid,
         &GUID_ADAPTIVE_POWER_BEHAVIOR_SUBGROUP,
         &GUID_NON_ADAPTIVE_INPUT_TIMEOUT,
         v5);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x1B,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
      (const char *)v6,
      AcValueIndexb);
  v7 = (const GUID **)`ConfigurePowerSettingsTask::Execute'::`2'::c_powerSettings;
  do
  {
    v8 = PowerWriteACValueIndex(0, SchemeGuid, *v7, v7[1], 0);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2D,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
        (const char *)v8,
        AcValueIndexc);
    v9 = PowerWriteDCValueIndex(0, SchemeGuid, *v7, v7[1], 0);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2E,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
        (const char *)v9,
        AcValueIndexd);
    v7 += 2;
  }
  while ( v7 != (const GUID **)qword_180054CD0 );
  DcDefaultIndex = 0;
  if ( !PowerReadDCDefaultIndex(
          0,
          SchemeGuid,
          &GUID_VIDEO_SUBGROUP,
          &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS,
          &DcDefaultIndex) )
  {
    DcDefaultIndex = 100;
    v10 = PowerWriteDCValueIndex(0, SchemeGuid, &GUID_VIDEO_SUBGROUP, &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS, 0x64u);
    if ( v10 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x37,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
        (const char *)v10,
        AcValueIndexe);
  }
  AcDefaultIndex = 0;
  if ( !PowerReadACDefaultIndex(
          0,
          SchemeGuid,
          &GUID_VIDEO_SUBGROUP,
          &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS,
          &AcDefaultIndex) )
  {
    AcDefaultIndex = 100;
    v11 = PowerWriteACValueIndex(0, SchemeGuid, &GUID_VIDEO_SUBGROUP, &GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS, 0x64u);
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x3F,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
        (const char *)v11,
        AcValueIndexf);
  }
  active = PowerSetActiveScheme(0, SchemeGuid);
  if ( active )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x42,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\configurepowersettingstask.cpp",
      (const char *)active,
      AcValueIndexf);
  v14 = SchemeGuid;
  SchemeGuid = 0;
  if ( v14 )
    wil::details::FreeProcessHeap((wil::details *)v14, v13);
}

```

## disassembly

```asm
0x18002a4e0  mov     [rsp-8+arg_0], rbx
0x18002a4e5  push    rbp
0x18002a4e6  mov     rbp, rsp
0x18002a4e9  sub     rsp, 50h
0x18002a4ed  mov     rbx, rcx
0x18002a4f0  mov     [rbp+SchemeGuid], 0
0x18002a4f8  lea     rax, [rbp+SchemeGuid]
0x18002a4fc  mov     [rbp+var_20], rax
0x18002a500  mov     [rbp+ActivePolicyGuid], 0
0x18002a508  mov     [rbp+var_10], 1
0x18002a50c  lea     rdx, [rbp+ActivePolicyGuid]; ActivePolicyGuid
0x18002a510  xor     ecx, ecx; UserRootPowerKey
0x18002a512  call    cs:__imp_PowerGetActiveScheme
0x18002a518  mov     rcx, [rbp+8]; this
0x18002a51c  test    eax, eax
0x18002a51e  jz      short loc_18002A535
0x18002a520  mov     r9d, eax; char *
0x18002a523  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a52a  mov     edx, 19h; void *
0x18002a52f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002a535  lea     rcx, [rbp+var_20]
0x18002a539  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@Uprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<_GUID,wil::process_heap_deleter>>(void)
0x18002a53e  mov     rcx, [rbx+50h]
0x18002a542  mov     rax, [rcx]
0x18002a545  mov     rax, [rax]
0x18002a548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a54d  mov     [rsp+50h+AcValueIndex], eax; unsigned int
0x18002a551  lea     r9, GUID_NON_ADAPTIVE_INPUT_TIMEOUT; PowerSettingGuid
0x18002a558  lea     r8, GUID_ADAPTIVE_POWER_BEHAVIOR_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002a55f  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18002a563  xor     ecx, ecx; RootPowerKey
0x18002a565  call    cs:__imp_PowerWriteACValueIndex
0x18002a56b  mov     rcx, [rbp+8]; this
0x18002a56f  test    eax, eax
0x18002a571  jz      short loc_18002A588
0x18002a573  mov     r9d, eax; char *
0x18002a576  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a57d  mov     edx, 1Ah; void *
0x18002a582  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002a588  mov     rcx, [rbx+50h]
0x18002a58c  mov     rax, [rcx]
0x18002a58f  mov     rax, [rax]
0x18002a592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a597  mov     [rsp+50h+AcValueIndex], eax; unsigned int
0x18002a59b  lea     r9, GUID_NON_ADAPTIVE_INPUT_TIMEOUT; PowerSettingGuid
0x18002a5a2  lea     r8, GUID_ADAPTIVE_POWER_BEHAVIOR_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002a5a9  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18002a5ad  xor     ecx, ecx; RootPowerKey
0x18002a5af  call    cs:__imp_PowerWriteDCValueIndex
0x18002a5b5  mov     rcx, [rbp+8]; this
0x18002a5b9  test    eax, eax
0x18002a5bb  jz      short loc_18002A5D2
0x18002a5bd  mov     r9d, eax; char *
0x18002a5c0  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a5c7  mov     edx, 1Bh; void *
0x18002a5cc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002a5d2  lea     rbx, ?c_powerSettings@?1??Execute@ConfigurePowerSettingsTask@@MEAAXXZ@4QBU_unnamed_type_c_powerSettings_@?1??12@MEAAXXZ@B; `ConfigurePowerSettingsTask::Execute(void)'::`2'::_unnamed_type_c_powerSettings_ const near * const `ConfigurePowerSettingsTask::Execute(void)'::`2'::c_powerSettings
0x18002a5d9  mov     [rsp+50h+AcValueIndex], 0; unsigned int
0x18002a5e1  mov     r9, [rbx+8]; PowerSettingGuid
0x18002a5e5  mov     r8, [rbx]; SubGroupOfPowerSettingsGuid
0x18002a5e8  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18002a5ec  xor     ecx, ecx; RootPowerKey
0x18002a5ee  call    cs:__imp_PowerWriteACValueIndex
0x18002a5f4  mov     rcx, [rbp+8]; this
0x18002a5f8  test    eax, eax
0x18002a5fa  jnz     loc_18002A771
0x18002a600  mov     [rsp+50h+AcValueIndex], eax; unsigned int
0x18002a604  mov     r9, [rbx+8]; PowerSettingGuid
0x18002a608  mov     r8, [rbx]; SubGroupOfPowerSettingsGuid
0x18002a60b  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18002a60f  xor     ecx, ecx; RootPowerKey
0x18002a611  call    cs:__imp_PowerWriteDCValueIndex
0x18002a617  mov     rcx, [rbp+8]; this
0x18002a61b  test    eax, eax
0x18002a61d  jnz     loc_18002A75C
0x18002a623  add     rbx, 10h
0x18002a627  lea     rax, qword_180054CD0
0x18002a62e  cmp     rbx, rax
0x18002a631  jnz     short loc_18002A5D9
0x18002a633  mov     [rbp+DcDefaultIndex], 0
0x18002a63a  lea     rax, [rbp+DcDefaultIndex]
0x18002a63e  mov     qword ptr [rsp+50h+AcValueIndex], rax; DcDefaultIndex
0x18002a643  lea     rbx, GUID_DEVICE_POWER_POLICY_VIDEO_BRIGHTNESS
0x18002a64a  mov     r9, rbx; PowerSettingGuid
0x18002a64d  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002a654  mov     rdx, [rbp+SchemeGuid]; SchemePersonalityGuid
0x18002a658  xor     ecx, ecx; RootPowerKey
0x18002a65a  call    cs:__imp_PowerReadDCDefaultIndex
0x18002a660  test    eax, eax
0x18002a662  jnz     short loc_18002A6A6
0x18002a664  mov     [rbp+DcDefaultIndex], 64h ; 'd'
0x18002a66b  mov     [rsp+50h+AcValueIndex], 64h ; 'd'; unsigned int
0x18002a673  mov     r9, rbx; PowerSettingGuid
0x18002a676  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002a67d  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18002a681  xor     ecx, ecx; RootPowerKey
0x18002a683  call    cs:__imp_PowerWriteDCValueIndex
0x18002a689  mov     rcx, [rbp+8]; this
0x18002a68d  test    eax, eax
0x18002a68f  jz      short loc_18002A6A6
0x18002a691  mov     r9d, eax; char *
0x18002a694  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a69b  mov     edx, 37h ; '7'; void *
0x18002a6a0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002a6a6  mov     [rbp+AcDefaultIndex], 0
0x18002a6ad  lea     rax, [rbp+AcDefaultIndex]
0x18002a6b1  mov     qword ptr [rsp+50h+AcValueIndex], rax; unsigned int
0x18002a6b6  mov     r9, rbx; PowerSettingGuid
0x18002a6b9  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002a6c0  mov     rdx, [rbp+SchemeGuid]; SchemePersonalityGuid
0x18002a6c4  xor     ecx, ecx; RootPowerKey
0x18002a6c6  call    cs:__imp_PowerReadACDefaultIndex
0x18002a6cc  test    eax, eax
0x18002a6ce  jnz     short loc_18002A712
0x18002a6d0  mov     [rbp+AcDefaultIndex], 64h ; 'd'
0x18002a6d7  mov     [rsp+50h+AcValueIndex], 64h ; 'd'; unsigned int
0x18002a6df  mov     r9, rbx; PowerSettingGuid
0x18002a6e2  lea     r8, GUID_VIDEO_SUBGROUP; SubGroupOfPowerSettingsGuid
0x18002a6e9  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18002a6ed  xor     ecx, ecx; RootPowerKey
0x18002a6ef  call    cs:__imp_PowerWriteACValueIndex
0x18002a6f5  mov     rcx, [rbp+8]; this
0x18002a6f9  test    eax, eax
0x18002a6fb  jz      short loc_18002A712
0x18002a6fd  mov     r9d, eax; char *
0x18002a700  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a707  mov     edx, 3Fh ; '?'; void *
0x18002a70c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002a712  mov     rdx, [rbp+SchemeGuid]; SchemeGuid
0x18002a716  xor     ecx, ecx; UserRootPowerKey
0x18002a718  call    cs:__imp_PowerSetActiveScheme
0x18002a71e  mov     rcx, [rbp+8]; this
0x18002a722  test    eax, eax
0x18002a724  jz      short loc_18002A73B
0x18002a726  mov     r9d, eax; char *
0x18002a729  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a730  mov     edx, 42h ; 'B'; void *
0x18002a735  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002a73b  mov     rcx, [rbp+SchemeGuid]; this
0x18002a73f  mov     [rbp+SchemeGuid], 0
0x18002a747  test    rcx, rcx
0x18002a74a  jz      short loc_18002A751
0x18002a74c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x18002a751  mov     rbx, [rsp+50h+arg_0]
0x18002a756  add     rsp, 50h
0x18002a75a  pop     rbp
0x18002a75b  retn
0x18002a75c  mov     r9d, eax; char *
0x18002a75f  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a766  mov     edx, 2Eh ; '.'; void *
0x18002a76b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002a771  mov     r9d, eax; char *
0x18002a774  lea     r8, aPcshellShellRe_14; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002a77b  mov     edx, 2Dh ; '-'; void *
0x18002a780  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
