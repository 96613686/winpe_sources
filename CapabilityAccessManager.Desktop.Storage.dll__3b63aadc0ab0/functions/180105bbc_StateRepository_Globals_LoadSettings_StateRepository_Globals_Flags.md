# StateRepository::Globals::LoadSettings(StateRepository::Globals::Flags)

- ea: `0x180105bbc`
- end: `0x180106002`
- name: `?LoadSettings@Globals@StateRepository@@YAJW4Flags@12@@Z`
- size: `1094`
- prototype: `__int64 __fastcall(char, HKEY, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180104fbc`

## callees

- `0x1800eabf4`
- `0x180104ec4`
- `0x180104f40`
- `0x1801056f0`
- `0x180105a7c`
- `0x180105bbc`
- `0x18010968c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180105bf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180105ff1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180105bf6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180105ff1`

## string_xrefs

- `0x180105ed7`: `RepairGhostMinimumAgeForDeletion`
- `0x180105cf7`: `ReindexMaintenanceTaskInterval`
- `0x180105d4e`: `DatabaseStatisticsUpdateInterval`
- `0x180105f91`: `AccessControlFlags`
- `0x180105f0e`: `ServiceIdleTimeout`
- `0x180105f3d`: `ServiceWaitHintInterval`
- `0x180105d78`: `DatabaseStatisticsUpdateMaintenanceTaskInterval`
- `0x180105da2`: `DatabaseStatisticsUpdateMaxClockDelta`
- `0x180105c2c`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::Globals::LoadSettings(char a1, HKEY a2, __int64 a3, unsigned int a4)
{
  int Setting; // ebx
  __int64 v7; // rdx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+20h]
  HKEY hKey; // [rsp+58h] [rbp+30h] BYREF

  hKey = 0;
  Setting = Common::RegistryKey::Open(&hKey, a2, (const unsigned __int16 *)qword_180140658, a4);
  if ( Setting < 0 )
  {
LABEL_2:
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    return (unsigned int)Setting;
  }
  Setting = StateRepository::Globals::GetSetting(&hKey, L"Options", 0, &dword_18013F948);
  if ( Setting < 0 )
  {
    v7 = 245;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)Setting,
      v8);
    goto LABEL_2;
  }
  Setting = StateRepository::Globals::GetSetting(&hKey, L"BusyTimeout", (const wchar_t *)0xFA, &dword_18013F938);
  if ( Setting < 0 )
  {
    v7 = 246;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(&hKey, L"BusyMaxTimeout", (const wchar_t *)0x493E0, &qword_18013F940);
  if ( Setting < 0 )
  {
    v7 = 247;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(&hKey, L"BusyDelayBetweenRetries", 0, &dwMilliseconds);
  if ( Setting < 0 )
  {
    v7 = 248;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(&hKey, L"ReindexInterval", (const wchar_t *)1, &qword_18013F930);
  if ( Setting < 0 )
  {
    v7 = 249;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"ReindexMaintenanceTaskInterval",
              (const wchar_t *)0x10E0,
              &qword_18013F920);
  if ( Setting < 0 )
  {
    v7 = 250;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"ReindexMaxClockDelta",
              (const wchar_t *)0x10E0,
              &qword_18013F928);
  if ( Setting < 0 )
  {
    v7 = 251;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"DatabaseStatisticsUpdateInterval",
              (const wchar_t *)1,
              &qword_18013F910);
  if ( Setting < 0 )
  {
    v7 = 252;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"DatabaseStatisticsUpdateMaintenanceTaskInterval",
              (const wchar_t *)0x10E0,
              &qword_18013F918);
  if ( Setting < 0 )
  {
    v7 = 253;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"DatabaseStatisticsUpdateMaxClockDelta",
              (const wchar_t *)0x10E0,
              &qword_18013F900);
  if ( Setting < 0 )
  {
    v7 = 254;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"MaintenanceInterval",
              (const wchar_t *)0x5A0,
              &qword_18013F908);
  if ( Setting < 0 )
  {
    v7 = 255;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"MaintenanceMaxClockDelta",
              (const wchar_t *)0x10E0,
              &qword_18013F8E0);
  if ( Setting < 0 )
  {
    v7 = 256;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"GCChangelogsInterval",
              (const wchar_t *)0x189C0,
              &qword_18013F8F0);
  if ( Setting < 0 )
  {
    v7 = 257;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"GCTimeToLiveExpiredInterval",
              (const wchar_t *)0xA8C0,
              &qword_18013F8F8);
  if ( Setting < 0 )
  {
    v7 = 258;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(&hKey, L"CheckpointInterval", (const wchar_t *)0x5A0, &qword_18013F8E8);
  if ( Setting < 0 )
  {
    v7 = 259;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"CheckpointMaxClockDelta",
              (const wchar_t *)0x10E0,
              &qword_18013F8D8);
  if ( Setting < 0 )
  {
    v7 = 260;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::GetSetting(
              &hKey,
              L"RepairGhostMinimumAgeForDeletion",
              (const wchar_t *)0x1D4C0,
              &qword_18013F8D0);
  if ( Setting < 0 )
  {
    v7 = 261;
    goto LABEL_7;
  }
  if ( (a1 & 1) != 0 )
  {
    Setting = StateRepository::Globals::GetSetting(
                &hKey,
                L"ServiceIdleTimeout",
                (const wchar_t *)0xEA60,
                &byte_18013F8C8);
    if ( Setting < 0 )
    {
      v7 = 265;
      goto LABEL_7;
    }
    Setting = StateRepository::Globals::GetSetting(
                &hKey,
                L"ServiceWaitHintInterval",
                (const wchar_t *)0x1388,
                &dword_18013F8CC);
    if ( Setting < 0 )
    {
      v7 = 266;
      goto LABEL_7;
    }
    Setting = StateRepository::Globals::GetSetting(
                &hKey,
                L"WaitForRequestsInUseTimeout",
                (const wchar_t *)0x1388,
                &qword_18013F8C0);
    if ( Setting < 0 )
    {
      v7 = 267;
      goto LABEL_7;
    }
    Setting = StateRepository::Globals::GetSetting(&hKey, L"AccessControlFlags", 0, &qword_180140480);
    if ( Setting < 0 )
    {
      v7 = 268;
      goto LABEL_7;
    }
  }
  Setting = StateRepository::Globals::PartitionSettings::LoadAll((struct Common::RegistryKey *)&hKey);
  if ( Setting < 0 )
  {
    v7 = 271;
    goto LABEL_7;
  }
  Setting = StateRepository::Globals::PolicySettings::LoadAll(&hKey);
  if ( Setting < 0 )
  {
    v7 = 273;
    goto LABEL_7;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180105bbc  push    rbp
0x180105bbe  push    rbx
0x180105bbf  push    rsi
0x180105bc0  push    rdi
0x180105bc1  mov     rbp, rsp
0x180105bc4  sub     rsp, 28h
0x180105bc8  mov     r8, cs:qword_180140658; unsigned __int16 *
0x180105bcf  mov     edi, ecx
0x180105bd1  lea     rcx, [rbp+hKey]; phkResult
0x180105bd5  mov     [rbp+hKey], 0
0x180105bdd  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x180105be2  mov     ebx, eax
0x180105be4  test    eax, eax
0x180105be6  jns     short loc_180105C03
0x180105be8  mov     rcx, [rbp+hKey]; hKey
0x180105bec  lea     rdx, [rcx-1]
0x180105bf0  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180105bf4  ja      short loc_180105BFC
0x180105bf6  call    cs:__imp_RegCloseKey
0x180105bfc  mov     eax, ebx
0x180105bfe  jmp     loc_180105FF9
0x180105c03  lea     r9, dword_18013F948; unsigned int
0x180105c0a  xor     r8d, r8d; wchar_t *
0x180105c0d  lea     rdx, ?stateRepositoryRegistryNameOptions@StateRepository@@3QB_WB; "Options"
0x180105c14  lea     rcx, [rbp+hKey]; this
0x180105c18  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105c1d  mov     ebx, eax
0x180105c1f  test    eax, eax
0x180105c21  jns     short loc_180105C3D
0x180105c23  mov     edx, 0F5h; void *
0x180105c28  mov     rcx, [rbp+20h]; this
0x180105c2c  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x180105c33  mov     r9d, ebx; char *
0x180105c36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105c3b  jmp     short loc_180105BE8
0x180105c3d  lea     r9, dword_18013F938; unsigned int
0x180105c44  mov     r8d, 0FAh; wchar_t *
0x180105c4a  lea     rdx, ?stateRepositoryRegistryNameBusyTimeout@StateRepository@@3QB_WB; "BusyTimeout"
0x180105c51  lea     rcx, [rbp+hKey]; this
0x180105c55  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105c5a  mov     ebx, eax
0x180105c5c  test    eax, eax
0x180105c5e  jns     short loc_180105C67
0x180105c60  mov     edx, 0F6h
0x180105c65  jmp     short loc_180105C28
0x180105c67  lea     r9, qword_18013F940; unsigned __int64
0x180105c6e  mov     r8d, 493E0h; wchar_t *
0x180105c74  lea     rdx, ?stateRepositoryRegistryNameBusyMaxTimeout@StateRepository@@3QB_WB; "BusyMaxTimeout"
0x180105c7b  lea     rcx, [rbp+hKey]; this
0x180105c7f  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105c84  mov     ebx, eax
0x180105c86  test    eax, eax
0x180105c88  jns     short loc_180105C91
0x180105c8a  mov     edx, 0F7h
0x180105c8f  jmp     short loc_180105C28
0x180105c91  lea     r9, dwMilliseconds; unsigned int
0x180105c98  xor     r8d, r8d; wchar_t *
0x180105c9b  lea     rdx, ?stateRepositoryRegistryNameBusyDelayBetweenRetries@StateRepository@@3QB_WB; "BusyDelayBetweenRetries"
0x180105ca2  lea     rcx, [rbp+hKey]; this
0x180105ca6  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105cab  mov     ebx, eax
0x180105cad  test    eax, eax
0x180105caf  jns     short loc_180105CBB
0x180105cb1  mov     edx, 0F8h
0x180105cb6  jmp     loc_180105C28
0x180105cbb  lea     r9, qword_18013F930; unsigned __int64
0x180105cc2  mov     r8d, 1; wchar_t *
0x180105cc8  lea     rdx, ?stateRepositoryRegistryNameReindexInterval@StateRepository@@3QB_WB; "ReindexInterval"
0x180105ccf  lea     rcx, [rbp+hKey]; this
0x180105cd3  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105cd8  mov     ebx, eax
0x180105cda  test    eax, eax
0x180105cdc  jns     short loc_180105CE8
0x180105cde  mov     edx, 0F9h
0x180105ce3  jmp     loc_180105C28
0x180105ce8  mov     esi, 10E0h
0x180105ced  lea     r9, qword_18013F920; unsigned __int64
0x180105cf4  mov     r8d, esi; wchar_t *
0x180105cf7  lea     rdx, ?stateRepositoryRegistryNameReindexMaintenanceTaskInterval@StateRepository@@3QB_WB; "ReindexMaintenanceTaskInterval"
0x180105cfe  lea     rcx, [rbp+hKey]; this
0x180105d02  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105d07  mov     ebx, eax
0x180105d09  test    eax, eax
0x180105d0b  jns     short loc_180105D17
0x180105d0d  mov     edx, 0FAh
0x180105d12  jmp     loc_180105C28
0x180105d17  lea     r9, qword_18013F928; unsigned int
0x180105d1e  mov     r8d, esi; wchar_t *
0x180105d21  lea     rdx, ?stateRepositoryRegistryNameReindexMaxClockDelta@StateRepository@@3QB_WB; "ReindexMaxClockDelta"
0x180105d28  lea     rcx, [rbp+hKey]; this
0x180105d2c  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105d31  mov     ebx, eax
0x180105d33  test    eax, eax
0x180105d35  jns     short loc_180105D41
0x180105d37  mov     edx, 0FBh
0x180105d3c  jmp     loc_180105C28
0x180105d41  lea     r9, qword_18013F910; unsigned __int64
0x180105d48  mov     r8d, 1; wchar_t *
0x180105d4e  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateInterval@StateRepository@@3QB_WB; "DatabaseStatisticsUpdateInterval"
0x180105d55  lea     rcx, [rbp+hKey]; this
0x180105d59  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105d5e  mov     ebx, eax
0x180105d60  test    eax, eax
0x180105d62  jns     short loc_180105D6E
0x180105d64  mov     edx, 0FCh
0x180105d69  jmp     loc_180105C28
0x180105d6e  lea     r9, qword_18013F918; unsigned __int64
0x180105d75  mov     r8, rsi; wchar_t *
0x180105d78  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateMaintenanceTaskInterval@StateRepository@@3QB_WB; "DatabaseStatisticsUpdateMaintenanceTask"...
0x180105d7f  lea     rcx, [rbp+hKey]; this
0x180105d83  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105d88  mov     ebx, eax
0x180105d8a  test    eax, eax
0x180105d8c  jns     short loc_180105D98
0x180105d8e  mov     edx, 0FDh
0x180105d93  jmp     loc_180105C28
0x180105d98  lea     r9, qword_18013F900; unsigned int
0x180105d9f  mov     r8d, esi; wchar_t *
0x180105da2  lea     rdx, ?stateRepositoryRegistryNameDatabaseStatisticsUpdateMaxClockDelta@StateRepository@@3QB_WB; "DatabaseStatisticsUpdateMaxClockDelta"
0x180105da9  lea     rcx, [rbp+hKey]; this
0x180105dad  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105db2  mov     ebx, eax
0x180105db4  test    eax, eax
0x180105db6  jns     short loc_180105DC2
0x180105db8  mov     edx, 0FEh
0x180105dbd  jmp     loc_180105C28
0x180105dc2  lea     r9, qword_18013F908; unsigned __int64
0x180105dc9  mov     r8d, 5A0h; wchar_t *
0x180105dcf  lea     rdx, ?stateRepositoryRegistryNameMaintenanceInterval@StateRepository@@3QB_WB; "MaintenanceInterval"
0x180105dd6  lea     rcx, [rbp+hKey]; this
0x180105dda  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105ddf  mov     ebx, eax
0x180105de1  test    eax, eax
0x180105de3  jns     short loc_180105DEF
0x180105de5  mov     edx, 0FFh
0x180105dea  jmp     loc_180105C28
0x180105def  lea     r9, qword_18013F8E0; unsigned __int64
0x180105df6  mov     r8, rsi; wchar_t *
0x180105df9  lea     rdx, ?stateRepositoryRegistryNameMaintenanceMaxClockDelta@StateRepository@@3QB_WB; "MaintenanceMaxClockDelta"
0x180105e00  lea     rcx, [rbp+hKey]; this
0x180105e04  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105e09  mov     ebx, eax
0x180105e0b  test    eax, eax
0x180105e0d  jns     short loc_180105E19
0x180105e0f  mov     edx, 100h
0x180105e14  jmp     loc_180105C28
0x180105e19  lea     r9, qword_18013F8F0; unsigned __int64
0x180105e20  mov     r8d, 189C0h; wchar_t *
0x180105e26  lea     rdx, ?stateRepositoryRegistryNameGCChangelogsInterval@StateRepository@@3QB_WB; "GCChangelogsInterval"
0x180105e2d  lea     rcx, [rbp+hKey]; this
0x180105e31  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105e36  mov     ebx, eax
0x180105e38  test    eax, eax
0x180105e3a  jns     short loc_180105E46
0x180105e3c  mov     edx, 101h
0x180105e41  jmp     loc_180105C28
0x180105e46  lea     r9, qword_18013F8F8; unsigned __int64
0x180105e4d  mov     r8d, 0A8C0h; wchar_t *
0x180105e53  lea     rdx, ?stateRepositoryRegistryNameGCTimeToLiveExpiredInterval@StateRepository@@3QB_WB; "GCTimeToLiveExpiredInterval"
0x180105e5a  lea     rcx, [rbp+hKey]; this
0x180105e5e  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105e63  mov     ebx, eax
0x180105e65  test    eax, eax
0x180105e67  jns     short loc_180105E73
0x180105e69  mov     edx, 102h
0x180105e6e  jmp     loc_180105C28
0x180105e73  lea     r9, qword_18013F8E8; unsigned __int64
0x180105e7a  mov     r8d, 5A0h; wchar_t *
0x180105e80  lea     rdx, ?stateRepositoryRegistryNameCheckpointInterval@StateRepository@@3QB_WB; "CheckpointInterval"
0x180105e87  lea     rcx, [rbp+hKey]; this
0x180105e8b  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105e90  mov     ebx, eax
0x180105e92  test    eax, eax
0x180105e94  jns     short loc_180105EA0
0x180105e96  mov     edx, 103h
0x180105e9b  jmp     loc_180105C28
0x180105ea0  lea     r9, qword_18013F8D8; unsigned __int64
0x180105ea7  mov     r8, rsi; wchar_t *
0x180105eaa  lea     rdx, ?stateRepositoryRegistryNameCheckpointMaxClockDelta@StateRepository@@3QB_WB; "CheckpointMaxClockDelta"
0x180105eb1  lea     rcx, [rbp+hKey]; this
0x180105eb5  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105eba  mov     ebx, eax
0x180105ebc  test    eax, eax
0x180105ebe  jns     short loc_180105ECA
0x180105ec0  mov     edx, 104h
0x180105ec5  jmp     loc_180105C28
0x180105eca  lea     r9, qword_18013F8D0; unsigned int
0x180105ed1  mov     r8d, 1D4C0h; wchar_t *
0x180105ed7  lea     rdx, ?stateRepositoryRegistryNameRepairGhostMinimumAgeForDeletion@StateRepository@@3QB_WB; "RepairGhostMinimumAgeForDeletion"
0x180105ede  lea     rcx, [rbp+hKey]; this
0x180105ee2  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105ee7  mov     ebx, eax
0x180105ee9  test    eax, eax
0x180105eeb  jns     short loc_180105EF7
0x180105eed  mov     edx, 105h
0x180105ef2  jmp     loc_180105C28
0x180105ef7  test    dil, 1
0x180105efb  jz      loc_180105FB1
0x180105f01  lea     r9, byte_18013F8C8; unsigned int
0x180105f08  mov     r8d, 0EA60h; wchar_t *
0x180105f0e  lea     rdx, ?stateRepositoryRegistryNameServiceIdleTimeout@StateRepository@@3QB_WB; "ServiceIdleTimeout"
0x180105f15  lea     rcx, [rbp+hKey]; this
0x180105f19  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105f1e  mov     ebx, eax
0x180105f20  test    eax, eax
0x180105f22  jns     short loc_180105F2E
0x180105f24  mov     edx, 109h
0x180105f29  jmp     loc_180105C28
0x180105f2e  mov     edi, 1388h
0x180105f33  lea     r9, dword_18013F8CC; unsigned int
0x180105f3a  mov     r8d, edi; wchar_t *
0x180105f3d  lea     rdx, ?stateRepositoryRegistryNameServiceWaitHintInterval@StateRepository@@3QB_WB; "ServiceWaitHintInterval"
0x180105f44  lea     rcx, [rbp+hKey]; this
0x180105f48  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105f4d  mov     ebx, eax
0x180105f4f  test    eax, eax
0x180105f51  jns     short loc_180105F5D
0x180105f53  mov     edx, 10Ah
0x180105f58  jmp     loc_180105C28
0x180105f5d  lea     r9, qword_18013F8C0; unsigned __int64
0x180105f64  mov     r8, rdi; wchar_t *
0x180105f67  lea     rdx, ?stateRepositoryRegistryNameWaitForRequestsInUseTimeout@StateRepository@@3QB_WB; "WaitForRequestsInUseTimeout"
0x180105f6e  lea     rcx, [rbp+hKey]; this
0x180105f72  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_W_KPEA_K@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,unsigned __int64,unsigned __int64 *)
0x180105f77  mov     ebx, eax
0x180105f79  test    eax, eax
0x180105f7b  jns     short loc_180105F87
0x180105f7d  mov     edx, 10Bh
0x180105f82  jmp     loc_180105C28
0x180105f87  lea     r9, qword_180140480; unsigned int
0x180105f8e  xor     r8d, r8d; wchar_t *
0x180105f91  lea     rdx, ?stateRepositoryRegistryNameAccessControlFlags@StateRepository@@3QB_WB; "AccessControlFlags"
0x180105f98  lea     rcx, [rbp+hKey]; this
0x180105f9c  call    ?GetSetting@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEB_WIPEAI@Z; StateRepository::Globals::GetSetting(Common::RegistryKey &,wchar_t const *,uint,uint *)
0x180105fa1  mov     ebx, eax
0x180105fa3  test    eax, eax
0x180105fa5  jns     short loc_180105FB1
0x180105fa7  mov     edx, 10Ch
0x180105fac  jmp     loc_180105C28
0x180105fb1  lea     rcx, [rbp+hKey]; struct Common::RegistryKey *
0x180105fb5  call    ?LoadAll@PartitionSettings@Globals@StateRepository@@SAJAEAVRegistryKey@Common@@@Z; StateRepository::Globals::PartitionSettings::LoadAll(Common::RegistryKey &)
0x180105fba  mov     ebx, eax
0x180105fbc  test    eax, eax
0x180105fbe  jns     short loc_180105FCA
0x180105fc0  mov     edx, 10Fh
0x180105fc5  jmp     loc_180105C28
0x180105fca  lea     rcx, [rbp+hKey]; struct Common::RegistryKey *
0x180105fce  call    ?LoadAll@PolicySettings@Globals@StateRepository@@SAJAEAVRegistryKey@Common@@@Z; StateRepository::Globals::PolicySettings::LoadAll(Common::RegistryKey &)
0x180105fd3  mov     ebx, eax
0x180105fd5  test    eax, eax
0x180105fd7  jns     short loc_180105FE3
0x180105fd9  mov     edx, 111h
0x180105fde  jmp     loc_180105C28
0x180105fe3  mov     rcx, [rbp+hKey]; hKey
0x180105fe7  lea     rax, [rcx-1]
0x180105feb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180105fef  ja      short loc_180105FF7
0x180105ff1  call    cs:__imp_RegCloseKey
0x180105ff7  xor     eax, eax
0x180105ff9  add     rsp, 28h
0x180105ffd  pop     rdi
0x180105ffe  pop     rsi
0x180105fff  pop     rbx
0x180106000  pop     rbp
0x180106001  retn
```
