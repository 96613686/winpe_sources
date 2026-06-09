# SystemSettings::WorkAccess::CEnrollmentProfileSetting::SyncManagement(ushort const *)

- ea: `0x18003f978`
- end: `0x18003fd8f`
- name: `?SyncManagement@CEnrollmentProfileSetting@WorkAccess@SystemSettings@@SAJPEBG@Z`
- size: `1047`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040230`

## callees

- `0x1800096ec`
- `0x18001ed10`
- `0x18003f978`
- `0x18004d550`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003fc2e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18003fc2e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fa63`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003fa63`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fc1f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18003fc1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f9aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003fbf4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003fc3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003f9aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003fbf4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003fc3a`
- `omadmapi!__imp_OmaDmInitiateSessionEx` at `0x18003f9e0`
- `omadmapi!__imp_OmaDmInitiateSessionEx` at `0x18003f9e0`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x18003fbc0`
- `omadmapi!__imp_OmaDmGetInitiationInfo` at `0x18003fbc0`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18003fbe4`
- `omadmapi!__imp_OmaDmFreeInitiationInfo` at `0x18003fbe4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003faec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003faec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fb3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fcc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd5d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fb3d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fc6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fcc2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003fd5d`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003fb78`
- `api-ms-win-core-registry-l1-1-0!RegNotifyChangeKeyValue` at `0x18003fb78`

## string_xrefs

- `0x18003f9f9`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003fa30`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003fa87`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003fb12`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003fc97`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003fce6`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`
- `0x18003fd32`: `shellcommon\shell\settingshandlers\workaccess\lib\enrollmentprofilesettings.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::WorkAccess::CEnrollmentProfileSetting::SyncManagement(const unsigned __int16 *a1)
{
  ULONGLONG TickCount64; // rsi
  int v3; // eax
  unsigned int v4; // ebx
  HANDLE EventW; // rbx
  HKEY v7; // rcx
  LSTATUS v8; // eax
  unsigned int v9; // edi
  HKEY v10; // rcx
  LSTATUS v11; // eax
  int InitiationInfo; // eax
  BOOL v13; // edi
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdx
  HKEY v16; // rcx
  HKEY v17; // rcx
  HKEY v18; // rcx
  HKEY v19; // rcx
  int phkResult; // [rsp+20h] [rbp-60h]
  int phkResulta; // [rsp+20h] [rbp-60h]
  __int64 v22; // [rsp+40h] [rbp-40h] BYREF
  __int128 v23; // [rsp+48h] [rbp-38h]
  __int128 v24; // [rsp+58h] [rbp-28h]
  __int128 v25; // [rsp+68h] [rbp-18h]
  __int64 v26; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  HKEY hKey; // [rsp+B8h] [rbp+38h] BYREF
  HANDLE v29; // [rsp+C0h] [rbp+40h] BYREF
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+48h]

  SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
    (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
    1);
  lpSubKey = 0;
  TickCount64 = GetTickCount64();
  v3 = OmaDmInitiateSessionEx(a1, 1, 2);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)(unsigned int)v3,
      0);
    SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
      (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
      0);
    return v4;
  }
  if ( !lpSubKey )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)0x80070057LL,
      0);
    SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
      (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
      0);
    return v4;
  }
  hKey = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v29 = EventW;
  if ( !EventW )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F8,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)0x8007000ELL,
      0);
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v29);
    v7 = hKey;
    hKey = 0;
    if ( v7 )
      RegCloseKey(v7);
    SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
      (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
      0);
    return v4;
  }
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v9 = v8;
  if ( v8 > 0 )
    v9 = (unsigned __int16)v8 | 0x80070000;
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
      (const char *)v9,
      phkResult);
    CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v29);
    v10 = hKey;
    hKey = 0;
    if ( v10 )
      RegCloseKey(v10);
    SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
      (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
      0);
    return v9;
  }
  while ( 1 )
  {
    v11 = RegNotifyChangeKeyValue(hKey, 1, 5u, EventW, 1);
    v9 = v11;
    if ( v11 > 0 )
      v9 = (unsigned __int16)v11 | 0x80070000;
    if ( (v9 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)v9,
        phkResulta);
      CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v29);
      v19 = hKey;
      hKey = 0;
      if ( v19 )
        RegCloseKey(v19);
      goto LABEL_36;
    }
    v22 = 64;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    InitiationInfo = OmaDmGetInitiationInfo(lpSubKey, &v22);
    v9 = InitiationInfo;
    if ( InitiationInfo < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x200,
        (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
        (const char *)(unsigned int)InitiationInfo,
        phkResulta);
      CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v29);
      v18 = hKey;
      hKey = 0;
      if ( v18 )
        RegCloseKey(v18);
LABEL_36:
      SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
        (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
        0);
      return v9;
    }
    v13 = HIDWORD(v23) == 5;
    OmaDmFreeInitiationInfo(&v22);
    if ( v13 )
      goto LABEL_25;
    v14 = GetTickCount64() - TickCount64;
    v15 = 180000 - v14;
    if ( v14 > 0x2BF20 )
      v15 = 0;
    if ( v15 > 0xFFFFFFFF )
      break;
    WaitForSingleObject(EventW, v15);
    ResetEvent(EventW);
    if ( GetTickCount64() - TickCount64 >= 0x2BF20 )
    {
LABEL_25:
      CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v29);
      v16 = hKey;
      hKey = 0;
      if ( v16 )
        RegCloseKey(v16);
      SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
        (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
        0);
      return 0;
    }
  }
  v4 = -2147024362;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20B,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\enrollmentprofilesettings.cpp",
    (const char *)0x80070216LL,
    phkResulta);
  CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(&v29);
  v17 = hKey;
  hKey = 0;
  if ( v17 )
    RegCloseKey(v17);
  SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(
    (SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance *)&SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance,
    0);
  return v4;
}

```

## disassembly

```asm
0x18003f978  mov     [rsp-28h+arg_0], rbx
0x18003f97d  push    rbp
0x18003f97e  push    rsi
0x18003f97f  push    rdi
0x18003f980  push    r13
0x18003f982  push    r15
0x18003f984  mov     rbp, rsp
0x18003f987  sub     rsp, 80h
0x18003f98e  mov     rbx, rcx
0x18003f991  mov     dl, 1; bool
0x18003f993  lea     r15, ?_corpDeviceNotificationInstance@CCorpDeviceNotificationSingleton@DataModel@SystemSettings@@1VCCorpDeviceNotificationSingletonInstance@23@A; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance SystemSettings::DataModel::CCorpDeviceNotificationSingleton::_corpDeviceNotificationInstance
0x18003f99a  mov     rcx, r15; this
0x18003f99d  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003f9a2  mov     [rbp+lpSubKey], 0
0x18003f9aa  call    cs:__imp_GetTickCount64
0x18003f9b1  nop     dword ptr [rax+rax+00h]
0x18003f9b6  mov     rsi, rax
0x18003f9b9  mov     [rsp+80h+var_50], 14h
0x18003f9c1  lea     rax, [rbp+lpSubKey]
0x18003f9c5  mov     [rsp+80h+var_58], rax
0x18003f9ca  mov     dword ptr [rsp+80h+phkResult], 0; int
0x18003f9d2  xor     r9d, r9d
0x18003f9d5  lea     edx, [r9+1]
0x18003f9d9  lea     r8d, [r9+2]
0x18003f9dd  mov     rcx, rbx
0x18003f9e0  call    cs:__imp_OmaDmInitiateSessionEx
0x18003f9e7  nop     dword ptr [rax+rax+00h]
0x18003f9ec  mov     ebx, eax
0x18003f9ee  test    eax, eax
0x18003f9f0  jns     short loc_18003FA1D
0x18003f9f2  mov     rcx, [rbp+28h]; this
0x18003f9f6  mov     r9d, eax; char *
0x18003f9f9  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003fa00  mov     edx, 1F4h; void *
0x18003fa05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa0a  nop
0x18003fa0b  xor     edx, edx; bool
0x18003fa0d  mov     rcx, r15; this
0x18003fa10  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fa15  nop
0x18003fa16  mov     eax, ebx
0x18003fa18  jmp     loc_18003FD77
0x18003fa1d  cmp     [rbp+lpSubKey], 0
0x18003fa22  jnz     short loc_18003FA4F
0x18003fa24  mov     rcx, [rbp+28h]; this
0x18003fa28  mov     ebx, 80070057h
0x18003fa2d  mov     r9d, ebx; char *
0x18003fa30  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003fa37  mov     edx, 1F5h; void *
0x18003fa3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa41  nop
0x18003fa42  xor     edx, edx; bool
0x18003fa44  mov     rcx, r15; this
0x18003fa47  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fa4c  nop
0x18003fa4d  jmp     short loc_18003FA16
0x18003fa4f  mov     [rbp+hKey], 0
0x18003fa57  xor     r9d, r9d; lpName
0x18003fa5a  xor     r8d, r8d; bInitialState
0x18003fa5d  lea     edx, [r9+1]; bManualReset
0x18003fa61  xor     ecx, ecx; lpEventAttributes
0x18003fa63  call    cs:__imp_CreateEventW
0x18003fa6a  nop     dword ptr [rax+rax+00h]
0x18003fa6f  mov     rbx, rax
0x18003fa72  mov     [rbp+arg_10], rax
0x18003fa76  test    rax, rax
0x18003fa79  jnz     short loc_18003FACF
0x18003fa7b  mov     rcx, [rbp+28h]; this
0x18003fa7f  mov     ebx, 8007000Eh
0x18003fa84  mov     r9d, ebx; char *
0x18003fa87  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003fa8e  mov     edx, 1F8h; void *
0x18003fa93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa98  lea     rcx, [rbp+arg_10]
0x18003fa9c  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003faa1  mov     rcx, [rbp+hKey]; hKey
0x18003faa5  mov     [rbp+hKey], 0
0x18003faad  test    rcx, rcx
0x18003fab0  jz      short loc_18003FABF
0x18003fab2  call    cs:__imp_RegCloseKey
0x18003fab9  nop     dword ptr [rax+rax+00h]
0x18003fabe  nop
0x18003fabf  xor     edx, edx; bool
0x18003fac1  mov     rcx, r15; this
0x18003fac4  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fac9  nop
0x18003faca  jmp     loc_18003FA16
0x18003facf  lea     rax, [rbp+hKey]
0x18003fad3  mov     [rsp+80h+phkResult], rax; int
0x18003fad8  mov     r9d, 20019h; samDesired
0x18003fade  xor     r8d, r8d; ulOptions
0x18003fae1  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18003fae5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003faec  call    cs:__imp_RegOpenKeyExW
0x18003faf3  nop     dword ptr [rax+rax+00h]
0x18003faf8  mov     edi, eax
0x18003fafa  test    eax, eax
0x18003fafc  jle     short loc_18003FB07
0x18003fafe  movzx   edi, ax
0x18003fb01  or      edi, 80070000h
0x18003fb07  test    edi, edi
0x18003fb09  jns     short loc_18003FB5A
0x18003fb0b  mov     rcx, [rbp+28h]; this
0x18003fb0f  mov     r9d, edi; char *
0x18003fb12  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003fb19  mov     edx, 1F9h; void *
0x18003fb1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fb23  lea     rcx, [rbp+arg_10]
0x18003fb27  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003fb2c  mov     rcx, [rbp+hKey]; hKey
0x18003fb30  mov     [rbp+hKey], 0
0x18003fb38  test    rcx, rcx
0x18003fb3b  jz      short loc_18003FB4A
0x18003fb3d  call    cs:__imp_RegCloseKey
0x18003fb44  nop     dword ptr [rax+rax+00h]
0x18003fb49  nop
0x18003fb4a  xor     edx, edx; bool
0x18003fb4c  mov     rcx, r15; this
0x18003fb4f  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fb54  nop
0x18003fb55  jmp     loc_18003FD75
0x18003fb5a  mov     r13d, 2BF20h
0x18003fb60  mov     dword ptr [rsp+80h+phkResult], 1; int
0x18003fb68  mov     r9, rbx; hEvent
0x18003fb6b  mov     edx, 1; bWatchSubtree
0x18003fb70  lea     r8d, [rdx+4]; dwNotifyFilter
0x18003fb74  mov     rcx, [rbp+hKey]; hKey
0x18003fb78  call    cs:__imp_RegNotifyChangeKeyValue
0x18003fb7f  nop     dword ptr [rax+rax+00h]
0x18003fb84  mov     edi, eax
0x18003fb86  test    eax, eax
0x18003fb88  jle     short loc_18003FB93
0x18003fb8a  movzx   edi, ax
0x18003fb8d  or      edi, 80070000h
0x18003fb93  test    edi, edi
0x18003fb95  js      loc_18003FD2B
0x18003fb9b  mov     [rbp+var_40], 40h ; '@'
0x18003fba3  xorps   xmm0, xmm0
0x18003fba6  xor     eax, eax
0x18003fba8  movups  [rbp+var_38], xmm0
0x18003fbac  movups  [rbp+var_28], xmm0
0x18003fbb0  movups  [rbp+var_18], xmm0
0x18003fbb4  mov     [rbp+var_8], rax
0x18003fbb8  lea     rdx, [rbp+var_40]
0x18003fbbc  mov     rcx, [rbp+lpSubKey]
0x18003fbc0  call    cs:__imp_OmaDmGetInitiationInfo
0x18003fbc7  nop     dword ptr [rax+rax+00h]
0x18003fbcc  mov     edi, eax
0x18003fbce  test    eax, eax
0x18003fbd0  js      loc_18003FCDF
0x18003fbd6  xor     edi, edi
0x18003fbd8  cmp     dword ptr [rbp+var_38+0Ch], 5
0x18003fbdc  setz    dil
0x18003fbe0  lea     rcx, [rbp+var_40]
0x18003fbe4  call    cs:__imp_OmaDmFreeInitiationInfo
0x18003fbeb  nop     dword ptr [rax+rax+00h]
0x18003fbf0  test    edi, edi
0x18003fbf2  jnz     short loc_18003FC52
0x18003fbf4  call    cs:__imp_GetTickCount64
0x18003fbfb  nop     dword ptr [rax+rax+00h]
0x18003fc00  sub     rax, rsi
0x18003fc03  mov     rdx, r13
0x18003fc06  sub     rdx, rax
0x18003fc09  xor     ecx, ecx
0x18003fc0b  cmp     rax, r13
0x18003fc0e  cmova   rdx, rcx; dwMilliseconds
0x18003fc12  mov     eax, 0FFFFFFFFh
0x18003fc17  cmp     rdx, rax
0x18003fc1a  ja      short loc_18003FC8B
0x18003fc1c  mov     rcx, rbx; hHandle
0x18003fc1f  call    cs:__imp_WaitForSingleObject
0x18003fc26  nop     dword ptr [rax+rax+00h]
0x18003fc2b  mov     rcx, rbx; hEvent
0x18003fc2e  call    cs:__imp_ResetEvent
0x18003fc35  nop     dword ptr [rax+rax+00h]
0x18003fc3a  call    cs:__imp_GetTickCount64
0x18003fc41  nop     dword ptr [rax+rax+00h]
0x18003fc46  sub     rax, rsi
0x18003fc49  cmp     rax, r13
0x18003fc4c  jb      loc_18003FB60
0x18003fc52  lea     rcx, [rbp+arg_10]
0x18003fc56  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003fc5b  mov     rcx, [rbp+hKey]; hKey
0x18003fc5f  mov     [rbp+hKey], 0
0x18003fc67  test    rcx, rcx
0x18003fc6a  jz      short loc_18003FC79
0x18003fc6c  call    cs:__imp_RegCloseKey
0x18003fc73  nop     dword ptr [rax+rax+00h]
0x18003fc78  nop
0x18003fc79  xor     edx, edx; bool
0x18003fc7b  mov     rcx, r15; this
0x18003fc7e  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fc83  nop
0x18003fc84  xor     eax, eax
0x18003fc86  jmp     loc_18003FD77
0x18003fc8b  mov     rcx, [rbp+28h]; this
0x18003fc8f  mov     ebx, 80070216h
0x18003fc94  mov     r9d, ebx; char *
0x18003fc97  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003fc9e  mov     edx, 20Bh; void *
0x18003fca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fca8  lea     rcx, [rbp+arg_10]
0x18003fcac  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003fcb1  mov     rcx, [rbp+hKey]; hKey
0x18003fcb5  mov     [rbp+hKey], 0
0x18003fcbd  test    rcx, rcx
0x18003fcc0  jz      short loc_18003FCCF
0x18003fcc2  call    cs:__imp_RegCloseKey
0x18003fcc9  nop     dword ptr [rax+rax+00h]
0x18003fcce  nop
0x18003fccf  xor     edx, edx; bool
0x18003fcd1  mov     rcx, r15; this
0x18003fcd4  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fcd9  nop
0x18003fcda  jmp     loc_18003FA16
0x18003fcdf  mov     rcx, [rbp+28h]; this
0x18003fce3  mov     r9d, edi; char *
0x18003fce6  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003fced  mov     edx, 200h; void *
0x18003fcf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fcf7  lea     rcx, [rbp+arg_10]
0x18003fcfb  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003fd00  mov     rcx, [rbp+hKey]; hKey
0x18003fd04  mov     [rbp+hKey], 0
0x18003fd0c  test    rcx, rcx
0x18003fd0f  jz      short loc_18003FD1E
0x18003fd11  call    cs:__imp_RegCloseKey
0x18003fd18  nop     dword ptr [rax+rax+00h]
0x18003fd1d  nop
0x18003fd1e  xor     edx, edx; bool
0x18003fd20  mov     rcx, r15; this
0x18003fd23  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fd28  nop
0x18003fd29  jmp     short loc_18003FD75
0x18003fd2b  mov     rcx, [rbp+28h]; this
0x18003fd2f  mov     r9d, edi; char *
0x18003fd32  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\settingshandlers\\w"...
0x18003fd39  mov     edx, 1FCh; void *
0x18003fd3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fd43  lea     rcx, [rbp+arg_10]
0x18003fd47  call    ?Release@?$CTSmartObj@PEAXV?$CAutoHandle_Policy@PEAX@@@@QEAAXXZ; CTSmartObj<void *,CAutoHandle_Policy<void *>>::Release(void)
0x18003fd4c  mov     rcx, [rbp+hKey]; hKey
0x18003fd50  mov     [rbp+hKey], 0
0x18003fd58  test    rcx, rcx
0x18003fd5b  jz      short loc_18003FD6A
0x18003fd5d  call    cs:__imp_RegCloseKey
0x18003fd64  nop     dword ptr [rax+rax+00h]
0x18003fd69  nop
0x18003fd6a  xor     edx, edx; bool
0x18003fd6c  mov     rcx, r15; this
0x18003fd6f  call    ?NotifyBusyState@CCorpDeviceNotificationSingletonInstance@DataModel@SystemSettings@@QEAAX_N@Z; SystemSettings::DataModel::CCorpDeviceNotificationSingletonInstance::NotifyBusyState(bool)
0x18003fd74  nop
0x18003fd75  mov     eax, edi
0x18003fd77  mov     rbx, [rsp+80h+arg_0]
0x18003fd7f  add     rsp, 80h
0x18003fd86  pop     r15
0x18003fd88  pop     r13
0x18003fd8a  pop     rdi
0x18003fd8b  pop     rsi
0x18003fd8c  pop     rbp
0x18003fd8d  retn
```
