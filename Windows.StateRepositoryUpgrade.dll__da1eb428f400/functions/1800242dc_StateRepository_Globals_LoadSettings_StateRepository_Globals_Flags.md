# StateRepository::Globals::LoadSettings(StateRepository::Globals::Flags)

- ea: `0x1800242dc`
- end: `0x180024736`
- name: `?LoadSettings@Globals@StateRepository@@YAJW4Flags@12@@Z`
- size: `1114`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180023ba8`

## callees

- `0x18000a3c0`
- `0x18000c584`
- `0x18000d9a4`
- `0x180023ac4`
- `0x180023b34`
- `0x180024114`
- `0x18002419c`
- `0x1800242dc`
- `0x18002c304`

## string_xrefs

- `0x180024366`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1800246ce`: `AccessControlFlags`
- `0x18002467a`: `ServiceWaitHintInterval`
- `0x18002464b`: `ServiceIdleTimeout`
- `0x180024614`: `RepairGhostMinimumAgeForDeletion`
- `0x1800244df`: `DatabaseStatisticsUpdateMaxClockDelta`
- `0x1800244b5`: `DatabaseStatisticsUpdateMaintenanceTaskInterval`
- `0x18002448b`: `DatabaseStatisticsUpdateInterval`
- `0x180024434`: `ReindexMaintenanceTaskInterval`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::LoadSettings(char a1)
{
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  int Setting; // eax
  __int64 v6; // rdx
  unsigned int *v8; // [rsp+20h] [rbp-8h]
  unsigned int *v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  HKEY phkResult; // [rsp+58h] [rbp+30h] BYREF

  phkResult = 0;
  v2 = Common::RegistryKey::Open(&phkResult, HKEY_LOCAL_MACHINE, lpSubKey, 0x20119u);
  v4 = v2;
  if ( v2 >= 0 )
  {
    Setting = StateRepository::Globals::GetSetting(
                (StateRepository::Globals *)&phkResult,
                (struct Common::RegistryKey *)L"Options",
                0,
                (unsigned int)&dword_18004B904,
                v8);
    v4 = Setting;
    if ( Setting >= 0 )
    {
      Setting = StateRepository::Globals::GetSetting(
                  (StateRepository::Globals *)&phkResult,
                  (struct Common::RegistryKey *)L"BusyTimeout",
                  (const unsigned __int16 *)0xFA,
                  (unsigned int)&byte_18004B900,
                  v9);
      v4 = Setting;
      if ( Setting >= 0 )
      {
        Setting = StateRepository::Globals::GetSetting(
                    (StateRepository::Globals *)&phkResult,
                    (struct Common::RegistryKey *)L"BusyMaxTimeout",
                    (const unsigned __int16 *)0x493E0,
                    (unsigned __int64)&qword_18004B8F8,
                    (unsigned __int64 *)v9);
        v4 = Setting;
        if ( Setting >= 0 )
        {
          Setting = StateRepository::Globals::GetSetting(
                      (StateRepository::Globals *)&phkResult,
                      (struct Common::RegistryKey *)L"BusyDelayBetweenRetries",
                      0,
                      (unsigned int)&dwMilliseconds,
                      v9);
          v4 = Setting;
          if ( Setting >= 0 )
          {
            Setting = StateRepository::Globals::GetSetting(
                        (StateRepository::Globals *)&phkResult,
                        (struct Common::RegistryKey *)L"ReindexInterval",
                        (const unsigned __int16 *)1,
                        (unsigned __int64)&qword_18004B8F0,
                        (unsigned __int64 *)v9);
            v4 = Setting;
            if ( Setting >= 0 )
            {
              Setting = StateRepository::Globals::GetSetting(
                          (StateRepository::Globals *)&phkResult,
                          (struct Common::RegistryKey *)L"ReindexMaintenanceTaskInterval",
                          (const unsigned __int16 *)0x10E0,
                          (unsigned __int64)&qword_18004B8E8,
                          (unsigned __int64 *)v9);
              v4 = Setting;
              if ( Setting >= 0 )
              {
                Setting = StateRepository::Globals::GetSetting(
                            (StateRepository::Globals *)&phkResult,
                            (struct Common::RegistryKey *)L"ReindexMaxClockDelta",
                            (const unsigned __int16 *)0x10E0,
                            (unsigned int)&qword_18004B8E0,
                            v9);
                v4 = Setting;
                if ( Setting >= 0 )
                {
                  Setting = StateRepository::Globals::GetSetting(
                              (StateRepository::Globals *)&phkResult,
                              (struct Common::RegistryKey *)L"DatabaseStatisticsUpdateInterval",
                              (const unsigned __int16 *)1,
                              (unsigned __int64)&qword_18004B8D8,
                              (unsigned __int64 *)v9);
                  v4 = Setting;
                  if ( Setting >= 0 )
                  {
                    Setting = StateRepository::Globals::GetSetting(
                                (StateRepository::Globals *)&phkResult,
                                (struct Common::RegistryKey *)L"DatabaseStatisticsUpdateMaintenanceTaskInterval",
                                (const unsigned __int16 *)0x10E0,
                                (unsigned __int64)&qword_18004B8D0,
                                (unsigned __int64 *)v9);
                    v4 = Setting;
                    if ( Setting >= 0 )
                    {
                      Setting = StateRepository::Globals::GetSetting(
                                  (StateRepository::Globals *)&phkResult,
                                  (struct Common::RegistryKey *)L"DatabaseStatisticsUpdateMaxClockDelta",
                                  (const unsigned __int16 *)0x10E0,
                                  (unsigned int)&qword_18004B8C8,
                                  v9);
                      v4 = Setting;
                      if ( Setting >= 0 )
                      {
                        Setting = StateRepository::Globals::GetSetting(
                                    (StateRepository::Globals *)&phkResult,
                                    (struct Common::RegistryKey *)L"MaintenanceInterval",
                                    (const unsigned __int16 *)0x5A0,
                                    (unsigned __int64)&qword_18004B8C0,
                                    (unsigned __int64 *)v9);
                        v4 = Setting;
                        if ( Setting >= 0 )
                        {
                          Setting = StateRepository::Globals::GetSetting(
                                      (StateRepository::Globals *)&phkResult,
                                      (struct Common::RegistryKey *)L"MaintenanceMaxClockDelta",
                                      (const unsigned __int16 *)0x10E0,
                                      (unsigned __int64)&qword_18004B8A8,
                                      (unsigned __int64 *)v9);
                          v4 = Setting;
                          if ( Setting >= 0 )
                          {
                            Setting = StateRepository::Globals::GetSetting(
                                        (StateRepository::Globals *)&phkResult,
                                        (struct Common::RegistryKey *)L"GCChangelogsInterval",
                                        (const unsigned __int16 *)0x189C0,
                                        (unsigned __int64)&qword_18004B8B8,
                                        (unsigned __int64 *)v9);
                            v4 = Setting;
                            if ( Setting >= 0 )
                            {
                              Setting = StateRepository::Globals::GetSetting(
                                          (StateRepository::Globals *)&phkResult,
                                          (struct Common::RegistryKey *)L"GCTimeToLiveExpiredInterval",
                                          (const unsigned __int16 *)0xA8C0,
                                          (unsigned __int64)&qword_18004B8B0,
                                          (unsigned __int64 *)v9);
                              v4 = Setting;
                              if ( Setting >= 0 )
                              {
                                Setting = StateRepository::Globals::GetSetting(
                                            (StateRepository::Globals *)&phkResult,
                                            (struct Common::RegistryKey *)L"CheckpointInterval",
                                            (const unsigned __int16 *)0x5A0,
                                            (unsigned __int64)&qword_18004B8A0,
                                            (unsigned __int64 *)v9);
                                v4 = Setting;
                                if ( Setting >= 0 )
                                {
                                  Setting = StateRepository::Globals::GetSetting(
                                              (StateRepository::Globals *)&phkResult,
                                              (struct Common::RegistryKey *)L"CheckpointMaxClockDelta",
                                              (const unsigned __int16 *)0x10E0,
                                              (unsigned __int64)&qword_18004B898,
                                              (unsigned __int64 *)v9);
                                  v4 = Setting;
                                  if ( Setting >= 0 )
                                  {
                                    Setting = StateRepository::Globals::GetSetting(
                                                (StateRepository::Globals *)&phkResult,
                                                (struct Common::RegistryKey *)L"RepairGhostMinimumAgeForDeletion",
                                                (const unsigned __int16 *)0x1D4C0,
                                                (unsigned int)&qword_18004B890,
                                                v9);
                                    v4 = Setting;
                                    if ( Setting >= 0 )
                                    {
                                      if ( (a1 & 1) != 0 )
                                      {
                                        Setting = StateRepository::Globals::GetSetting(
                                                    (StateRepository::Globals *)&phkResult,
                                                    (struct Common::RegistryKey *)L"ServiceIdleTimeout",
                                                    (const unsigned __int16 *)0xEA60,
                                                    (unsigned int)&dword_18004B88C,
                                                    v9);
                                        v4 = Setting;
                                        if ( Setting < 0 )
                                        {
                                          v6 = 265;
                                          goto LABEL_6;
                                        }
                                        Setting = StateRepository::Globals::GetSetting(
                                                    (StateRepository::Globals *)&phkResult,
                                                    (struct Common::RegistryKey *)L"ServiceWaitHintInterval",
                                                    (const unsigned __int16 *)0x1388,
                                                    (unsigned int)&byte_18004B888,
                                                    v9);
                                        v4 = Setting;
                                        if ( Setting < 0 )
                                        {
                                          v6 = 266;
                                          goto LABEL_6;
                                        }
                                        Setting = StateRepository::Globals::GetSetting(
                                                    (StateRepository::Globals *)&phkResult,
                                                    (struct Common::RegistryKey *)L"WaitForRequestsInUseTimeout",
                                                    (const unsigned __int16 *)0x1388,
                                                    (unsigned __int64)&qword_18004B880,
                                                    (unsigned __int64 *)v9);
                                        v4 = Setting;
                                        if ( Setting < 0 )
                                        {
                                          v6 = 267;
                                          goto LABEL_6;
                                        }
                                        Setting = StateRepository::Globals::GetSetting(
                                                    (StateRepository::Globals *)&phkResult,
                                                    (struct Common::RegistryKey *)L"AccessControlFlags",
                                                    0,
                                                    (unsigned int)&qword_18004BF38,
                                                    v9);
                                        v4 = Setting;
                                        if ( Setting < 0 )
                                        {
                                          v6 = 268;
                                          goto LABEL_6;
                                        }
                                      }
                                      Setting = StateRepository::Globals::PartitionSettings::LoadAll((struct Common::RegistryKey *)&phkResult);
                                      v4 = Setting;
                                      if ( Setting >= 0 )
                                      {
                                        Setting = StateRepository::Globals::PolicySettings::LoadAll((struct Common::RegistryKey *)&phkResult);
                                        v4 = Setting;
                                        if ( Setting >= 0 )
                                        {
                                          v4 = 0;
                                          goto LABEL_53;
                                        }
                                        v6 = 273;
                                      }
                                      else
                                      {
                                        v6 = 271;
                                      }
                                      goto LABEL_6;
                                    }
                                    v6 = 261;
                                  }
                                  else
                                  {
                                    v6 = 260;
                                  }
                                }
                                else
                                {
                                  v6 = 259;
                                }
                              }
                              else
                              {
                                v6 = 258;
                              }
                            }
                            else
                            {
                              v6 = 257;
                            }
                          }
                          else
                          {
                            v6 = 256;
                          }
                        }
                        else
                        {
                          v6 = 255;
                        }
                      }
                      else
                      {
                        v6 = 254;
                      }
                    }
                    else
                    {
                      v6 = 253;
                    }
                  }
                  else
                  {
                    v6 = 252;
                  }
                }
                else
                {
                  v6 = 251;
                }
              }
              else
              {
                v6 = 250;
              }
            }
            else
            {
              v6 = 249;
            }
          }
          else
          {
            v6 = 248;
          }
        }
        else
        {
          v6 = 247;
        }
      }
      else
      {
        v6 = 246;
      }
    }
    else
    {
      v6 = 245;
    }
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)Setting,
      (int)v9);
    goto LABEL_53;
  }
  if ( (Microsoft_Windows_StateRepositoryEnableBits & 1) != 0 )
    McTemplateU0dz_EventWriteTransfer(v3, ReadSettingError, (unsigned int)v2, lpSubKey);
LABEL_53:
  Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
  return v4;
}

```

## disassembly

```asm
0x1800242dc  push    rbp
0x1800242de  push    rbx
0x1800242df  push    rsi
0x1800242e0  push    rdi
0x1800242e1  mov     rbp, rsp
0x1800242e4  sub     rsp, 28h
0x1800242e8  mov     r8, cs:lpSubKey; lpSubKey
0x1800242ef  mov     edi, ecx
0x1800242f1  lea     rcx, [rbp+phkResult]; phkResult
0x1800242f5  mov     [rbp+phkResult], 0
0x1800242fd  mov     r9d, 20119h; samDesired
0x180024303  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18002430a  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x18002430f  mov     ebx, eax
0x180024311  test    eax, eax
0x180024313  jns     short loc_18002433D
0x180024315  test    cs:Microsoft_Windows_StateRepositoryEnableBits, 1
0x18002431c  jz      loc_180024722
0x180024322  mov     r9, cs:lpSubKey
0x180024329  lea     rdx, ReadSettingError
0x180024330  mov     r8d, eax
0x180024333  call    McTemplateU0dz_EventWriteTransfer
0x180024338  jmp     loc_180024722
0x18002433d  lea     r9, dword_18004B904; unsigned int
0x180024344  xor     r8d, r8d; unsigned __int16 *
0x180024347  lea     rdx, ?stateRepositoryRegistryNameOptions@StateRepository@@3QBGB; "Options"
0x18002434e  lea     rcx, [rbp+phkResult]; this
0x180024352  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180024357  mov     ebx, eax
0x180024359  test    eax, eax
0x18002435b  jns     short loc_18002437A
0x18002435d  mov     edx, 0F5h; void *
0x180024362  mov     rcx, [rbp+20h]; this
0x180024366  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x18002436d  mov     r9d, eax; char *
0x180024370  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024375  jmp     loc_180024722
0x18002437a  lea     r9, byte_18004B900; unsigned int
0x180024381  mov     r8d, 0FAh; unsigned __int16 *
0x180024387  lea     rdx, ?stateRepositoryRegistryNameBusyTimeout@StateRepository@@3QBGB; "BusyTimeout"
0x18002438e  lea     rcx, [rbp+phkResult]; this
0x180024392  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180024397  mov     ebx, eax
0x180024399  test    eax, eax
0x18002439b  jns     short loc_1800243A4
0x18002439d  mov     edx, 0F6h
0x1800243a2  jmp     short loc_180024362
0x1800243a4  lea     r9, qword_18004B8F8; unsigned __int64
0x1800243ab  mov     r8d, 493E0h; unsigned __int16 *
0x1800243b1  lea     rdx, ?stateRepositoryRegistryNameBusyMaxTimeout@StateRepository@@3QBGB; "BusyMaxTimeout"
0x1800243b8  lea     rcx, [rbp+phkResult]; this
0x1800243bc  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1800243c1  mov     ebx, eax
0x1800243c3  test    eax, eax
0x1800243c5  jns     short loc_1800243CE
0x1800243c7  mov     edx, 0F7h
0x1800243cc  jmp     short loc_180024362
0x1800243ce  lea     r9, dwMilliseconds; unsigned int
0x1800243d5  xor     r8d, r8d; unsigned __int16 *
0x1800243d8  lea     rdx, ?stateRepositoryRegistryNameBusyDelayBetweenRetries@StateRepository@@3QBGB; "BusyDelayBetweenRetries"
0x1800243df  lea     rcx, [rbp+phkResult]; this
0x1800243e3  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x1800243e8  mov     ebx, eax
0x1800243ea  test    eax, eax
0x1800243ec  jns     short loc_1800243F8
0x1800243ee  mov     edx, 0F8h
0x1800243f3  jmp     loc_180024362
0x1800243f8  lea     r9, qword_18004B8F0; unsigned __int64
0x1800243ff  mov     r8d, 1; unsigned __int16 *
0x180024405  lea     rdx, ?stateRepositoryRegistryNameReindexInterval@StateRepository@@3QBGB; "ReindexInterval"
0x18002440c  lea     rcx, [rbp+phkResult]; this
0x180024410  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180024415  mov     ebx, eax
0x180024417  test    eax, eax
0x180024419  jns     short loc_180024425
0x18002441b  mov     edx, 0F9h
0x180024420  jmp     loc_180024362
0x180024425  mov     esi, 10E0h
0x18002442a  lea     r9, qword_18004B8E8; unsigned __int64
0x180024431  mov     r8d, esi; unsigned __int16 *
0x180024434  lea     rdx, ?stateRepositoryRegistryNameReindexMaintenanceTaskInterval@StateRepository@@3QBGB; "ReindexMaintenanceTaskInterval"
0x18002443b  lea     rcx, [rbp+phkResult]; this
0x18002443f  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180024444  mov     ebx, eax
0x180024446  test    eax, eax
0x180024448  jns     short loc_180024454
0x18002444a  mov     edx, 0FAh
0x18002444f  jmp     loc_180024362
0x180024454  lea     r9, qword_18004B8E0; unsigned int
0x18002445b  mov     r8d, esi; unsigned __int16 *
0x18002445e  lea     rdx, ?stateRepositoryRegistryNameReindexMaxClockDelta@StateRepository@@3QBGB; "ReindexMaxClockDelta"
0x180024465  lea     rcx, [rbp+phkResult]; this
0x180024469  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x18002446e  mov     ebx, eax
0x180024470  test    eax, eax
0x180024472  jns     short loc_18002447E
0x180024474  mov     edx, 0FBh
0x180024479  jmp     loc_180024362
0x18002447e  lea     r9, qword_18004B8D8; unsigned __int64
0x180024485  mov     r8d, 1; unsigned __int16 *
0x18002448b  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateInterval@StateRepository@@3QBGB; "DatabaseStatisticsUpdateInterval"
0x180024492  lea     rcx, [rbp+phkResult]; this
0x180024496  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x18002449b  mov     ebx, eax
0x18002449d  test    eax, eax
0x18002449f  jns     short loc_1800244AB
0x1800244a1  mov     edx, 0FCh
0x1800244a6  jmp     loc_180024362
0x1800244ab  lea     r9, qword_18004B8D0; unsigned __int64
0x1800244b2  mov     r8, rsi; unsigned __int16 *
0x1800244b5  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateMaintenanceTaskInterval@StateRepository@@3QBGB; "DatabaseStatisticsUpdateMaintenanceTask"...
0x1800244bc  lea     rcx, [rbp+phkResult]; this
0x1800244c0  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1800244c5  mov     ebx, eax
0x1800244c7  test    eax, eax
0x1800244c9  jns     short loc_1800244D5
0x1800244cb  mov     edx, 0FDh
0x1800244d0  jmp     loc_180024362
0x1800244d5  lea     r9, qword_18004B8C8; unsigned int
0x1800244dc  mov     r8d, esi; unsigned __int16 *
0x1800244df  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateMaxClockDelta@StateRepository@@3QBGB; "DatabaseStatisticsUpdateMaxClockDelta"
0x1800244e6  lea     rcx, [rbp+phkResult]; this
0x1800244ea  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x1800244ef  mov     ebx, eax
0x1800244f1  test    eax, eax
0x1800244f3  jns     short loc_1800244FF
0x1800244f5  mov     edx, 0FEh
0x1800244fa  jmp     loc_180024362
0x1800244ff  lea     r9, qword_18004B8C0; unsigned __int64
0x180024506  mov     r8d, 5A0h; unsigned __int16 *
0x18002450c  lea     rdx, ?stateRepositoryRegistryNameMaintenanceInterval@StateRepository@@3QBGB; "MaintenanceInterval"
0x180024513  lea     rcx, [rbp+phkResult]; this
0x180024517  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x18002451c  mov     ebx, eax
0x18002451e  test    eax, eax
0x180024520  jns     short loc_18002452C
0x180024522  mov     edx, 0FFh
0x180024527  jmp     loc_180024362
0x18002452c  lea     r9, qword_18004B8A8; unsigned __int64
0x180024533  mov     r8, rsi; unsigned __int16 *
0x180024536  lea     rdx, ?stateRepositoryRegistryNameMaintenanceMaxClockDelta@StateRepository@@3QBGB; "MaintenanceMaxClockDelta"
0x18002453d  lea     rcx, [rbp+phkResult]; this
0x180024541  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180024546  mov     ebx, eax
0x180024548  test    eax, eax
0x18002454a  jns     short loc_180024556
0x18002454c  mov     edx, 100h
0x180024551  jmp     loc_180024362
0x180024556  lea     r9, qword_18004B8B8; unsigned __int64
0x18002455d  mov     r8d, 189C0h; unsigned __int16 *
0x180024563  lea     rdx, ?stateRepositoryRegistryNameGCChangelogsInterval@StateRepository@@3QBGB; "GCChangelogsInterval"
0x18002456a  lea     rcx, [rbp+phkResult]; this
0x18002456e  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180024573  mov     ebx, eax
0x180024575  test    eax, eax
0x180024577  jns     short loc_180024583
0x180024579  mov     edx, 101h
0x18002457e  jmp     loc_180024362
0x180024583  lea     r9, qword_18004B8B0; unsigned __int64
0x18002458a  mov     r8d, 0A8C0h; unsigned __int16 *
0x180024590  lea     rdx, ?stateRepositoryRegistryNameGCTimeToLiveExpiredInterval@StateRepository@@3QBGB; "GCTimeToLiveExpiredInterval"
0x180024597  lea     rcx, [rbp+phkResult]; this
0x18002459b  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1800245a0  mov     ebx, eax
0x1800245a2  test    eax, eax
0x1800245a4  jns     short loc_1800245B0
0x1800245a6  mov     edx, 102h
0x1800245ab  jmp     loc_180024362
0x1800245b0  lea     r9, qword_18004B8A0; unsigned __int64
0x1800245b7  mov     r8d, 5A0h; unsigned __int16 *
0x1800245bd  lea     rdx, ?stateRepositoryRegistryNameCheckpointInterval@StateRepository@@3QBGB; "CheckpointInterval"
0x1800245c4  lea     rcx, [rbp+phkResult]; this
0x1800245c8  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1800245cd  mov     ebx, eax
0x1800245cf  test    eax, eax
0x1800245d1  jns     short loc_1800245DD
0x1800245d3  mov     edx, 103h
0x1800245d8  jmp     loc_180024362
0x1800245dd  lea     r9, qword_18004B898; unsigned __int64
0x1800245e4  mov     r8, rsi; unsigned __int16 *
0x1800245e7  lea     rdx, ?stateRepositoryRegistryNameCheckpointMaxClockDelta@StateRepository@@3QBGB; "CheckpointMaxClockDelta"
0x1800245ee  lea     rcx, [rbp+phkResult]; this
0x1800245f2  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1800245f7  mov     ebx, eax
0x1800245f9  test    eax, eax
0x1800245fb  jns     short loc_180024607
0x1800245fd  mov     edx, 104h
0x180024602  jmp     loc_180024362
0x180024607  lea     r9, qword_18004B890; unsigned int
0x18002460e  mov     r8d, 1D4C0h; unsigned __int16 *
0x180024614  lea     rdx, ?stateRepositoryRegistryNameRepairGhostMinimumAgeForDeletion@StateRepository@@3QBGB; "RepairGhostMinimumAgeForDeletion"
0x18002461b  lea     rcx, [rbp+phkResult]; this
0x18002461f  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x180024624  mov     ebx, eax
0x180024626  test    eax, eax
0x180024628  jns     short loc_180024634
0x18002462a  mov     edx, 105h
0x18002462f  jmp     loc_180024362
0x180024634  test    dil, 1
0x180024638  jz      loc_1800246EE
0x18002463e  lea     r9, dword_18004B88C; unsigned int
0x180024645  mov     r8d, 0EA60h; unsigned __int16 *
0x18002464b  lea     rdx, ?stateRepositoryRegistryNameServiceIdleTimeout@StateRepository@@3QBGB; "ServiceIdleTimeout"
0x180024652  lea     rcx, [rbp+phkResult]; this
0x180024656  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x18002465b  mov     ebx, eax
0x18002465d  test    eax, eax
0x18002465f  jns     short loc_18002466B
0x180024661  mov     edx, 109h
0x180024666  jmp     loc_180024362
0x18002466b  mov     edi, 1388h
0x180024670  lea     r9, byte_18004B888; unsigned int
0x180024677  mov     r8d, edi; unsigned __int16 *
0x18002467a  lea     rdx, ?stateRepositoryRegistryNameServiceWaitHintInterval@StateRepository@@3QBGB; "ServiceWaitHintInterval"
0x180024681  lea     rcx, [rbp+phkResult]; this
0x180024685  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x18002468a  mov     ebx, eax
0x18002468c  test    eax, eax
0x18002468e  jns     short loc_18002469A
0x180024690  mov     edx, 10Ah
0x180024695  jmp     loc_180024362
0x18002469a  lea     r9, qword_18004B880; unsigned __int64
0x1800246a1  mov     r8, rdi; unsigned __int16 *
0x1800246a4  lea     rdx, ?stateRepositoryRegistryNameWaitForRequestsInUseTimeout@StateRepository@@3QBGB; "WaitForRequestsInUseTimeout"
0x1800246ab  lea     rcx, [rbp+phkResult]; this
0x1800246af  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1800246b4  mov     ebx, eax
0x1800246b6  test    eax, eax
0x1800246b8  jns     short loc_1800246C4
0x1800246ba  mov     edx, 10Bh
0x1800246bf  jmp     loc_180024362
0x1800246c4  lea     r9, qword_18004BF38; unsigned int
0x1800246cb  xor     r8d, r8d; unsigned __int16 *
0x1800246ce  lea     rdx, ?stateRepositoryRegistryNameAccessControlFlags@StateRepository@@3QBGB; "AccessControlFlags"
0x1800246d5  lea     rcx, [rbp+phkResult]; this
0x1800246d9  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,ushort const *,uint,uint *)
0x1800246de  mov     ebx, eax
0x1800246e0  test    eax, eax
0x1800246e2  jns     short loc_1800246EE
0x1800246e4  mov     edx, 10Ch
0x1800246e9  jmp     loc_180024362
0x1800246ee  lea     rcx, [rbp+phkResult]; struct Common::RegistryKey *
0x1800246f2  call    ?LoadAll@PartitionSettings@Globals@StateRepository@@SAJAEAVRegistryKey@Common@@@Z; StateRepository::Globals::PartitionSettings::LoadAll(Common::RegistryKey &)
0x1800246f7  mov     ebx, eax
0x1800246f9  test    eax, eax
0x1800246fb  jns     short loc_180024707
0x1800246fd  mov     edx, 10Fh
0x180024702  jmp     loc_180024362
0x180024707  lea     rcx, [rbp+phkResult]; struct Common::RegistryKey *
0x18002470b  call    ?LoadAll@PolicySettings@Globals@StateRepository@@SAJAEAVRegistryKey@Common@@@Z; StateRepository::Globals::PolicySettings::LoadAll(Common::RegistryKey &)
0x180024710  mov     ebx, eax
0x180024712  test    eax, eax
0x180024714  jns     short loc_180024720
0x180024716  mov     edx, 111h
0x18002471b  jmp     loc_180024362
0x180024720  xor     ebx, ebx
0x180024722  mov     rcx, [rbp+phkResult]
0x180024726  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18002472b  mov     eax, ebx
0x18002472d  add     rsp, 28h
0x180024731  pop     rdi
0x180024732  pop     rsi
0x180024733  pop     rbx
0x180024734  pop     rbp
0x180024735  retn
```
