# StateRepository::Globals::LoadSettings(StateRepository::Globals::Flags)

- ea: `0x180203050`
- end: `0x180203754`
- name: `?LoadSettings@Globals@StateRepository@@YAJW4Flags@12@@Z`
- size: `1796`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800934f0`
- `0x1800b2ee0`

## callees

- `0x18001a9e0`
- `0x1800613a8`
- `0x180061560`
- `0x1801a5120`
- `0x180202bd0`
- `0x180202c40`
- `0x180202e88`
- `0x180202f10`
- `0x180203050`

## string_xrefs

- `0x1802030e1`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203129`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203174`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802031bc`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203207`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203254`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18020329c`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802032e7`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18020332f`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203377`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802033c2`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18020340a`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203455`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802034a0`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802034eb`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203533`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18020357e`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802035d3`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203620`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203668`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802036b0`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1802036e7`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x18020371e`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180203693`: `AccessControlFlags`
- `0x180203561`: `RepairGhostMinimumAgeForDeletion`
- `0x1802035b6`: `ServiceIdleTimeout`
- `0x180203603`: `ServiceWaitHintInterval`
- `0x1802032ca`: `DatabaseStatisticsUpdateInterval`
- `0x180203312`: `DatabaseStatisticsUpdateMaintenanceTaskInterval`
- `0x18020335a`: `DatabaseStatisticsUpdateMaxClockDelta`
- `0x180203237`: `ReindexMaintenanceTaskInterval`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateRepository::Globals::LoadSettings(char a1)
{
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  int Setting; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int All; // eax
  int v28; // eax
  unsigned int *v29; // [rsp+20h] [rbp-8h]
  unsigned int *v30; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v31; // [rsp+20h] [rbp-8h]
  unsigned int *v32; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v33; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v34; // [rsp+20h] [rbp-8h]
  unsigned int *v35; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v36; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v37; // [rsp+20h] [rbp-8h]
  unsigned int *v38; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v39; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v40; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v41; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v42; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v43; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v44; // [rsp+20h] [rbp-8h]
  unsigned int *v45; // [rsp+20h] [rbp-8h]
  unsigned int *v46; // [rsp+20h] [rbp-8h]
  unsigned int *v47; // [rsp+20h] [rbp-8h]
  unsigned __int64 *v48; // [rsp+20h] [rbp-8h]
  unsigned int *v49; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  HKEY phkResult; // [rsp+58h] [rbp+30h] BYREF

  phkResult = 0;
  v2 = Common::RegistryKey::Open(&phkResult, HKEY_LOCAL_MACHINE, (LPCWSTR)qword_1804E04E8, 0x20119u);
  v4 = v2;
  if ( v2 < 0 )
  {
    if ( (Microsoft_Windows_StateRepositoryEnableBits & 1) != 0 )
      McTemplateU0dz_EventWriteTransfer(v3, ReadSettingError, (unsigned int)v2, qword_1804E04E8);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  Setting = StateRepository::Globals::GetSetting(
              (StateRepository::Globals *)&phkResult,
              (struct Common::RegistryKey *)L"Options",
              0,
              (unsigned int)&dword_1804DF348,
              v29);
  v4 = Setting;
  if ( Setting < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)Setting,
      (int)v30);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v7 = StateRepository::Globals::GetSetting(
         (StateRepository::Globals *)&phkResult,
         (struct Common::RegistryKey *)L"BusyTimeout",
         (const unsigned __int16 *)0xFA,
         (unsigned int)&dword_1804DF34C,
         v30);
  v4 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v7,
      (int)v31);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v8 = StateRepository::Globals::GetSetting(
         (StateRepository::Globals *)&phkResult,
         (struct Common::RegistryKey *)L"BusyMaxTimeout",
         (const unsigned __int16 *)0x493E0,
         (unsigned __int64)&qword_1804DF330,
         v31);
  v4 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v8,
      (int)v32);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v9 = StateRepository::Globals::GetSetting(
         (StateRepository::Globals *)&phkResult,
         (struct Common::RegistryKey *)L"BusyDelayBetweenRetries",
         0,
         (unsigned int)&dwMilliseconds,
         v32);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v9,
      (int)v33);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v10 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"ReindexInterval",
          (const unsigned __int16 *)1,
          (unsigned __int64)&qword_1804DF338,
          v33);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v10,
      (int)v34);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v11 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"ReindexMaintenanceTaskInterval",
          (const unsigned __int16 *)0x10E0,
          (unsigned __int64)&qword_1804DF340,
          v34);
  v4 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v11,
      (int)v35);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v12 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"ReindexMaxClockDelta",
          (const unsigned __int16 *)0x10E0,
          (unsigned int)&dword_1804DF310,
          v35);
  v4 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v12,
      (int)v36);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v13 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"DatabaseStatisticsUpdateInterval",
          (const unsigned __int16 *)1,
          (unsigned __int64)&qword_1804DF318,
          v36);
  v4 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v13,
      (int)v37);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v14 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"DatabaseStatisticsUpdateMaintenanceTaskInterval",
          (const unsigned __int16 *)0x10E0,
          (unsigned __int64)&qword_1804DF320,
          v37);
  v4 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFD,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v14,
      (int)v38);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v15 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"DatabaseStatisticsUpdateMaxClockDelta",
          (const unsigned __int16 *)0x10E0,
          (unsigned int)&dword_1804DF328,
          v38);
  v4 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFE,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v15,
      (int)v39);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v16 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"MaintenanceInterval",
          (const unsigned __int16 *)0x5A0,
          (unsigned __int64)&qword_1804DF2F0,
          v39);
  v4 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v16,
      (int)v40);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v17 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"MaintenanceMaxClockDelta",
          (const unsigned __int16 *)0x10E0,
          (unsigned __int64)&qword_1804DF308,
          v40);
  v4 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x100,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v17,
      (int)v41);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v18 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"GCChangelogsInterval",
          (const unsigned __int16 *)0x189C0,
          (unsigned __int64)&qword_1804DF2F8,
          v41);
  v4 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v18,
      (int)v42);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v19 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"GCTimeToLiveExpiredInterval",
          (const unsigned __int16 *)0xA8C0,
          (unsigned __int64)&qword_1804DF300,
          v42);
  v4 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v19,
      (int)v43);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v20 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"CheckpointInterval",
          (const unsigned __int16 *)0x5A0,
          (unsigned __int64)&qword_1804DF2D8,
          v43);
  v4 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x103,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v20,
      (int)v44);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v21 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"CheckpointMaxClockDelta",
          (const unsigned __int16 *)0x10E0,
          (unsigned __int64)&qword_1804DF2E0,
          v44);
  v4 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x104,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v21,
      (int)v45);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v22 = StateRepository::Globals::GetSetting(
          (StateRepository::Globals *)&phkResult,
          (struct Common::RegistryKey *)L"RepairGhostMinimumAgeForDeletion",
          (const unsigned __int16 *)0x1D4C0,
          (unsigned int)&dword_1804DF2E8,
          v45);
  v4 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x105,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v22,
      (int)v46);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  if ( (a1 & 1) != 0 )
  {
    v23 = StateRepository::Globals::GetSetting(
            (StateRepository::Globals *)&phkResult,
            (struct Common::RegistryKey *)L"ServiceIdleTimeout",
            (const unsigned __int16 *)0xEA60,
            (unsigned int)&dword_1804DF2D0,
            v46);
    v4 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v23,
        (int)v47);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      return v4;
    }
    v24 = StateRepository::Globals::GetSetting(
            (StateRepository::Globals *)&phkResult,
            (struct Common::RegistryKey *)L"ServiceWaitHintInterval",
            (const unsigned __int16 *)0x1388,
            (unsigned int)&dword_1804DF2C4,
            v47);
    v4 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v24,
        (int)v48);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      return v4;
    }
    v25 = StateRepository::Globals::GetSetting(
            (StateRepository::Globals *)&phkResult,
            (struct Common::RegistryKey *)L"WaitForRequestsInUseTimeout",
            (const unsigned __int16 *)0x1388,
            (unsigned __int64)&qword_1804DF2C8,
            v48);
    v4 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v25,
        (int)v49);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      return v4;
    }
    v26 = StateRepository::Globals::GetSetting(
            (StateRepository::Globals *)&phkResult,
            (struct Common::RegistryKey *)L"AccessControlFlags",
            0,
            (unsigned int)&byte_1804E01B0,
            v49);
    v4 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v26,
        (int)v46);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      return v4;
    }
  }
  All = StateRepository::Globals::PartitionSettings::LoadAll((struct Common::RegistryKey *)&phkResult);
  v4 = All;
  if ( All < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)All,
      (int)v46);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  v28 = StateRepository::Globals::PolicySettings::LoadAll((struct Common::RegistryKey *)&phkResult);
  v4 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v28,
      (int)v46);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    return v4;
  }
  Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
  return 0;
}

```

## disassembly

```asm
0x180203050  push    rbp
0x180203052  push    rbx
0x180203053  push    rsi
0x180203054  push    rdi
0x180203055  mov     rbp, rsp
0x180203058  sub     rsp, 28h
0x18020305c  mov     edi, ecx
0x18020305e  mov     [rbp+phkResult], 0
0x180203066  mov     r9d, 20119h; samDesired
0x18020306c  mov     r8, cs:qword_1804E04E8; lpSubKey
0x180203073  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18020307a  lea     rcx, [rbp+phkResult]; phkResult
0x18020307e  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180203083  mov     ebx, eax
0x180203085  test    eax, eax
0x180203087  jns     short loc_1802030BA
0x180203089  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 1
0x180203090  jz      short loc_1802030A9
0x180203092  mov     r9, cs:qword_1804E04E8
0x180203099  mov     r8d, eax
0x18020309c  lea     rdx, ReadSettingError
0x1802030a3  call    McTemplateU0dz_EventWriteTransfer
0x1802030a8  nop
0x1802030a9  mov     rcx, [rbp+phkResult]
0x1802030ad  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802030b2  nop
0x1802030b3  mov     eax, ebx
0x1802030b5  jmp     loc_18020374B
0x1802030ba  lea     r9, dword_1804DF348; unsigned int
0x1802030c1  xor     r8d, r8d; unsigned __int16 *
0x1802030c4  lea     rdx, ?stateRepositoryRegistryNameOptions@StateRepository@@3QBGB; "Options"
0x1802030cb  lea     rcx, [rbp+phkResult]; this
0x1802030cf  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x1802030d4  mov     ebx, eax
0x1802030d6  test    eax, eax
0x1802030d8  jns     short loc_1802030FF
0x1802030da  mov     rcx, [rbp+20h]; this
0x1802030de  mov     r9d, eax; char *
0x1802030e1  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1802030e8  mov     edx, 0F5h; void *
0x1802030ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802030f2  nop
0x1802030f3  mov     rcx, [rbp+phkResult]
0x1802030f7  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802030fc  nop
0x1802030fd  jmp     short loc_1802030B3
0x1802030ff  lea     r9, dword_1804DF34C; unsigned int
0x180203106  mov     r8d, 0FAh; unsigned __int16 *
0x18020310c  lea     rdx, ?stateRepositoryRegistryNameBusyTimeout@StateRepository@@3QBGB; "BusyTimeout"
0x180203113  lea     rcx, [rbp+phkResult]; this
0x180203117  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x18020311c  mov     ebx, eax
0x18020311e  test    eax, eax
0x180203120  jns     short loc_18020314A
0x180203122  mov     rcx, [rbp+20h]; this
0x180203126  mov     r9d, eax; char *
0x180203129  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x180203130  mov     edx, 0F6h; void *
0x180203135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020313a  nop
0x18020313b  mov     rcx, [rbp+phkResult]
0x18020313f  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180203144  nop
0x180203145  jmp     loc_1802030B3
0x18020314a  lea     r9, qword_1804DF330; unsigned __int64
0x180203151  mov     r8d, 493E0h; unsigned __int16 *
0x180203157  lea     rdx, ?stateRepositoryRegistryNameBusyMaxTimeout@StateRepository@@3QBGB; "BusyMaxTimeout"
0x18020315e  lea     rcx, [rbp+phkResult]; this
0x180203162  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180203167  mov     ebx, eax
0x180203169  test    eax, eax
0x18020316b  jns     short loc_180203195
0x18020316d  mov     rcx, [rbp+20h]; this
0x180203171  mov     r9d, eax; char *
0x180203174  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x18020317b  mov     edx, 0F7h; void *
0x180203180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180203185  nop
0x180203186  mov     rcx, [rbp+phkResult]
0x18020318a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18020318f  nop
0x180203190  jmp     loc_1802030B3
0x180203195  lea     r9, dwMilliseconds; unsigned int
0x18020319c  xor     r8d, r8d; unsigned __int16 *
0x18020319f  lea     rdx, ?stateRepositoryRegistryNameBusyDelayBetweenRetries@StateRepository@@3QBGB; "BusyDelayBetweenRetries"
0x1802031a6  lea     rcx, [rbp+phkResult]; this
0x1802031aa  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x1802031af  mov     ebx, eax
0x1802031b1  test    eax, eax
0x1802031b3  jns     short loc_1802031DD
0x1802031b5  mov     rcx, [rbp+20h]; this
0x1802031b9  mov     r9d, eax; char *
0x1802031bc  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1802031c3  mov     edx, 0F8h; void *
0x1802031c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802031cd  nop
0x1802031ce  mov     rcx, [rbp+phkResult]
0x1802031d2  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802031d7  nop
0x1802031d8  jmp     loc_1802030B3
0x1802031dd  lea     r9, qword_1804DF338; unsigned __int64
0x1802031e4  mov     r8d, 1; unsigned __int16 *
0x1802031ea  lea     rdx, ?stateRepositoryRegistryNameReindexInterval@StateRepository@@3QBGB; "ReindexInterval"
0x1802031f1  lea     rcx, [rbp+phkResult]; this
0x1802031f5  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1802031fa  mov     ebx, eax
0x1802031fc  test    eax, eax
0x1802031fe  jns     short loc_180203228
0x180203200  mov     rcx, [rbp+20h]; this
0x180203204  mov     r9d, eax; char *
0x180203207  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x18020320e  mov     edx, 0F9h; void *
0x180203213  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180203218  nop
0x180203219  mov     rcx, [rbp+phkResult]
0x18020321d  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180203222  nop
0x180203223  jmp     loc_1802030B3
0x180203228  lea     r9, qword_1804DF340; unsigned __int64
0x18020322f  mov     esi, 10E0h
0x180203234  mov     r8d, esi; unsigned __int16 *
0x180203237  lea     rdx, ?stateRepositoryRegistryNameReindexMaintenanceTaskInterval@StateRepository@@3QBGB; "ReindexMaintenanceTaskInterval"
0x18020323e  lea     rcx, [rbp+phkResult]; this
0x180203242  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180203247  mov     ebx, eax
0x180203249  test    eax, eax
0x18020324b  jns     short loc_180203275
0x18020324d  mov     rcx, [rbp+20h]; this
0x180203251  mov     r9d, eax; char *
0x180203254  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x18020325b  mov     edx, 0FAh; void *
0x180203260  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180203265  nop
0x180203266  mov     rcx, [rbp+phkResult]
0x18020326a  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18020326f  nop
0x180203270  jmp     loc_1802030B3
0x180203275  lea     r9, dword_1804DF310; unsigned int
0x18020327c  mov     r8d, esi; unsigned __int16 *
0x18020327f  lea     rdx, ?stateRepositoryRegistryNameReindexMaxClockDelta@StateRepository@@3QBGB; "ReindexMaxClockDelta"
0x180203286  lea     rcx, [rbp+phkResult]; this
0x18020328a  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x18020328f  mov     ebx, eax
0x180203291  test    eax, eax
0x180203293  jns     short loc_1802032BD
0x180203295  mov     rcx, [rbp+20h]; this
0x180203299  mov     r9d, eax; char *
0x18020329c  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1802032a3  mov     edx, 0FBh; void *
0x1802032a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802032ad  nop
0x1802032ae  mov     rcx, [rbp+phkResult]
0x1802032b2  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802032b7  nop
0x1802032b8  jmp     loc_1802030B3
0x1802032bd  lea     r9, qword_1804DF318; unsigned __int64
0x1802032c4  mov     r8d, 1; unsigned __int16 *
0x1802032ca  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateInterval@StateRepository@@3QBGB; "DatabaseStatisticsUpdateInterval"
0x1802032d1  lea     rcx, [rbp+phkResult]; this
0x1802032d5  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1802032da  mov     ebx, eax
0x1802032dc  test    eax, eax
0x1802032de  jns     short loc_180203308
0x1802032e0  mov     rcx, [rbp+20h]; this
0x1802032e4  mov     r9d, eax; char *
0x1802032e7  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1802032ee  mov     edx, 0FCh; void *
0x1802032f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802032f8  nop
0x1802032f9  mov     rcx, [rbp+phkResult]
0x1802032fd  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180203302  nop
0x180203303  jmp     loc_1802030B3
0x180203308  lea     r9, qword_1804DF320; unsigned __int64
0x18020330f  mov     r8, rsi; unsigned __int16 *
0x180203312  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateMaintenanceTaskInterval@StateRepository@@3QBGB; "DatabaseStatisticsUpdateMaintenanceTask"...
0x180203319  lea     rcx, [rbp+phkResult]; this
0x18020331d  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180203322  mov     ebx, eax
0x180203324  test    eax, eax
0x180203326  jns     short loc_180203350
0x180203328  mov     rcx, [rbp+20h]; this
0x18020332c  mov     r9d, eax; char *
0x18020332f  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x180203336  mov     edx, 0FDh; void *
0x18020333b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180203340  nop
0x180203341  mov     rcx, [rbp+phkResult]
0x180203345  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18020334a  nop
0x18020334b  jmp     loc_1802030B3
0x180203350  lea     r9, dword_1804DF328; unsigned int
0x180203357  mov     r8d, esi; unsigned __int16 *
0x18020335a  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateMaxClockDelta@StateRepository@@3QBGB; "DatabaseStatisticsUpdateMaxClockDelta"
0x180203361  lea     rcx, [rbp+phkResult]; this
0x180203365  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x18020336a  mov     ebx, eax
0x18020336c  test    eax, eax
0x18020336e  jns     short loc_180203398
0x180203370  mov     rcx, [rbp+20h]; this
0x180203374  mov     r9d, eax; char *
0x180203377  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x18020337e  mov     edx, 0FEh; void *
0x180203383  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180203388  nop
0x180203389  mov     rcx, [rbp+phkResult]
0x18020338d  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180203392  nop
0x180203393  jmp     loc_1802030B3
0x180203398  lea     r9, qword_1804DF2F0; unsigned __int64
0x18020339f  mov     r8d, 5A0h; unsigned __int16 *
0x1802033a5  lea     rdx, ?stateRepositoryRegistryNameMaintenanceInterval@StateRepository@@3QBGB; "MaintenanceInterval"
0x1802033ac  lea     rcx, [rbp+phkResult]; this
0x1802033b0  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1802033b5  mov     ebx, eax
0x1802033b7  test    eax, eax
0x1802033b9  jns     short loc_1802033E3
0x1802033bb  mov     rcx, [rbp+20h]; this
0x1802033bf  mov     r9d, eax; char *
0x1802033c2  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1802033c9  mov     edx, 0FFh; void *
0x1802033ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802033d3  nop
0x1802033d4  mov     rcx, [rbp+phkResult]
0x1802033d8  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802033dd  nop
0x1802033de  jmp     loc_1802030B3
0x1802033e3  lea     r9, qword_1804DF308; unsigned __int64
0x1802033ea  mov     r8, rsi; unsigned __int16 *
0x1802033ed  lea     rdx, ?stateRepositoryRegistryNameMaintenanceMaxClockDelta@StateRepository@@3QBGB; "MaintenanceMaxClockDelta"
0x1802033f4  lea     rcx, [rbp+phkResult]; this
0x1802033f8  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1802033fd  mov     ebx, eax
0x1802033ff  test    eax, eax
0x180203401  jns     short loc_18020342B
0x180203403  mov     rcx, [rbp+20h]; this
0x180203407  mov     r9d, eax; char *
0x18020340a  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x180203411  mov     edx, 100h; void *
0x180203416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020341b  nop
0x18020341c  mov     rcx, [rbp+phkResult]
0x180203420  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180203425  nop
0x180203426  jmp     loc_1802030B3
0x18020342b  lea     r9, qword_1804DF2F8; unsigned __int64
0x180203432  mov     r8d, 189C0h; unsigned __int16 *
0x180203438  lea     rdx, ?stateRepositoryRegistryNameGCChangelogsInterval@StateRepository@@3QBGB; "GCChangelogsInterval"
0x18020343f  lea     rcx, [rbp+phkResult]; this
0x180203443  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180203448  mov     ebx, eax
0x18020344a  test    eax, eax
0x18020344c  jns     short loc_180203476
0x18020344e  mov     rcx, [rbp+20h]; this
0x180203452  mov     r9d, eax; char *
0x180203455  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x18020345c  mov     edx, 101h; void *
0x180203461  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180203466  nop
0x180203467  mov     rcx, [rbp+phkResult]
0x18020346b  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180203470  nop
0x180203471  jmp     loc_1802030B3
0x180203476  lea     r9, qword_1804DF300; unsigned __int64
0x18020347d  mov     r8d, 0A8C0h; unsigned __int16 *
0x180203483  lea     rdx, ?stateRepositoryRegistryNameGCTimeToLiveExpiredInterval@StateRepository@@3QBGB; "GCTimeToLiveExpiredInterval"
0x18020348a  lea     rcx, [rbp+phkResult]; this
0x18020348e  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180203493  mov     ebx, eax
0x180203495  test    eax, eax
0x180203497  jns     short loc_1802034C1
0x180203499  mov     rcx, [rbp+20h]; this
0x18020349d  mov     r9d, eax; char *
0x1802034a0  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1802034a7  mov     edx, 102h; void *
0x1802034ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802034b1  nop
0x1802034b2  mov     rcx, [rbp+phkResult]
0x1802034b6  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1802034bb  nop
0x1802034bc  jmp     loc_1802030B3
0x1802034c1  lea     r9, qword_1804DF2D8; unsigned __int64
0x1802034c8  mov     r8d, 5A0h; unsigned __int16 *
0x1802034ce  lea     rdx, ?stateRepositoryRegistryNameCheckpointInterval@StateRepository@@3QBGB; "CheckpointInterval"
0x1802034d5  lea     rcx, [rbp+phkResult]; this
0x1802034d9  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1802034de  mov     ebx, eax
0x1802034e0  test    eax, eax
0x1802034e2  jns     short loc_18020350C
0x1802034e4  mov     rcx, [rbp+20h]; this
0x1802034e8  mov     r9d, eax; char *
0x1802034eb  lea     r8, aOnecoreBaseApp_421; "onecore\\base\\appmodel\\staterepositor"...
0x1802034f2  mov     edx, 103h; void *
0x1802034f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802034fc  nop
0x1802034fd  mov     rcx, [rbp+phkResult]
0x180203501  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180203506  nop
0x180203507  jmp     loc_1802030B3
0x18020350c  lea     r9, qword_1804DF2E0; unsigned __int64
  ... truncated ...
```
