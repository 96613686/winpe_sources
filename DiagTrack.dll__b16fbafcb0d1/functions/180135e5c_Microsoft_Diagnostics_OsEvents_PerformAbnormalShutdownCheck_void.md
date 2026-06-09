# Microsoft::Diagnostics::OsEvents::PerformAbnormalShutdownCheck(void)

- ea: `0x180135e5c`
- end: `0x1801368b8`
- name: `?PerformAbnormalShutdownCheck@OsEvents@Diagnostics@Microsoft@@CAJXZ`
- size: `2652`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801436a4`

## callees

- `0x18001fd84`
- `0x180020a4c`
- `0x18002b318`
- `0x18002cae0`
- `0x18002df00`
- `0x180038034`
- `0x18003c66c`
- `0x18005ea74`
- `0x180064e8c`
- `0x180081954`
- `0x18008a51c`
- `0x18008a580`
- `0x18008a5d8`
- `0x1800b47f0`
- `0x180135e5c`
- `0x1801399a8`
- `0x1801cb878`
- `0x1801dc01c`
- `0x1801dc068`
- `0x1801de6fc`
- `0x1801e17c4`
- `0x1801e1c98`
- `0x18020aac0`
- `0x18020aae4`
- `0x18020afa4`
- `0x18020bab8`

## import_xrefs

- `ntdll!RtlCheckSystemBootStatusIntegrity` at `0x180135e95`
- `ntdll!RtlCheckSystemBootStatusIntegrity` at `0x180135e95`
- `ntdll!RtlCreateBootStatusDataFile` at `0x180135ea4`
- `ntdll!RtlCreateBootStatusDataFile` at `0x180135ea4`
- `ntdll!NtPowerInformation` at `0x1801360af`
- `ntdll!NtPowerInformation` at `0x180136429`
- `ntdll!NtPowerInformation` at `0x180136473`
- `ntdll!NtPowerInformation` at `0x1801364b2`
- `ntdll!NtPowerInformation` at `0x180136526`
- `ntdll!NtPowerInformation` at `0x180136566`
- `ntdll!NtPowerInformation` at `0x18013679f`
- `ntdll!NtPowerInformation` at `0x1801360af`
- `ntdll!NtPowerInformation` at `0x180136429`
- `ntdll!NtPowerInformation` at `0x180136473`
- `ntdll!NtPowerInformation` at `0x1801364b2`
- `ntdll!NtPowerInformation` at `0x180136526`
- `ntdll!NtPowerInformation` at `0x180136566`
- `ntdll!NtPowerInformation` at `0x18013679f`
- `ntdll!RtlRestoreSystemBootStatusDefaults` at `0x1801360d6`
- `ntdll!RtlRestoreSystemBootStatusDefaults` at `0x1801360d6`
- `ntdll!RtlGetSystemBootStatus` at `0x1801361e9`
- `ntdll!RtlGetSystemBootStatus` at `0x180136326`
- `ntdll!RtlGetSystemBootStatus` at `0x180136366`
- `ntdll!RtlGetSystemBootStatus` at `0x1801361e9`
- `ntdll!RtlGetSystemBootStatus` at `0x180136326`
- `ntdll!RtlGetSystemBootStatus` at `0x180136366`
- `ntdll!NtQuerySystemTime` at `0x18013623f`
- `ntdll!NtQuerySystemTime` at `0x18013623f`
- `ntdll!RtlComputeCrc32` at `0x180136293`
- `ntdll!RtlComputeCrc32` at `0x180136293`
- `ntdll!RtlSetSystemBootStatus` at `0x1801362b2`
- `ntdll!RtlSetSystemBootStatus` at `0x1801362b2`
- `ntdll!NtQuerySystemInformationEx` at `0x1801365a6`
- `ntdll!NtQuerySystemInformationEx` at `0x1801365e5`
- `ntdll!NtQuerySystemInformationEx` at `0x1801365a6`
- `ntdll!NtQuerySystemInformationEx` at `0x1801365e5`
- `ntdll!NtQuerySystemInformation` at `0x18013660a`
- `ntdll!NtQuerySystemInformation` at `0x18013660a`

## string_xrefs

- `0x180135eb9`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x180135eeb`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x180135f34`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1801360eb`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x18013613f`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x18013618f`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1801361fe`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x180136254`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x1801362c7`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x18013633b`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`
- `0x18013637b`: `onecore\base\telemetry\utc\service\analysis\osevents.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
int Microsoft::Diagnostics::OsEvents::PerformAbnormalShutdownCheck(void)
{
  int v0; // eax
  void *v1; // rcx
  NTSTATUS BootStatusDataFile; // eax
  int BootStatusItem; // eax
  int v5; // ebx
  char v6; // di
  void *v7; // rbx
  AbnormalShutdownData *v8; // rbx
  unsigned int v9; // r13d
  NTSTATUS v10; // eax
  int v11; // eax
  void *v12; // rcx
  int v13; // ebx
  LONG v14; // esi
  int v15; // eax
  void *v16; // rcx
  int v17; // edi
  int v18; // eax
  int v19; // edi
  int v20; // eax
  int v21; // ebx
  NTSTATUS v22; // eax
  int v23; // ebx
  int v24; // eax
  int v25; // ebx
  bool v26; // si
  int SystemBootStatus; // eax
  int v28; // eax
  unsigned int v29; // edi
  void *v30; // rcx
  int v31; // ecx
  void *v32; // rcx
  char v33; // al
  _QWORD *v34; // rdx
  void *v35; // rcx
  int OutputBufferLength; // [rsp+20h] [rbp-5D8h]
  int OutputBufferLengtha; // [rsp+20h] [rbp-5D8h]
  char OutputBuffer; // [rsp+40h] [rbp-5B8h] BYREF
  char v39[3]; // [rsp+41h] [rbp-5B7h] BYREF
  unsigned int v40; // [rsp+44h] [rbp-5B4h] BYREF
  unsigned int v41; // [rsp+48h] [rbp-5B0h] BYREF
  __int64 InputBuffer; // [rsp+50h] [rbp-5A8h] BYREF
  DWORD v43; // [rsp+58h] [rbp-5A0h] BYREF
  int v44[2]; // [rsp+60h] [rbp-598h] BYREF
  __int64 v45; // [rsp+68h] [rbp-590h]
  AbnormalShutdownData *v46; // [rsp+70h] [rbp-588h] BYREF
  unsigned int v47; // [rsp+78h] [rbp-580h] BYREF
  int v48; // [rsp+7Ch] [rbp-57Ch]
  int v49; // [rsp+80h] [rbp-578h]
  _DWORD v50[3]; // [rsp+84h] [rbp-574h] BYREF
  int v51[4]; // [rsp+90h] [rbp-568h] BYREF
  int v52; // [rsp+A0h] [rbp-558h] BYREF
  _QWORD v53[5]; // [rsp+A8h] [rbp-550h] BYREF
  __int128 v54; // [rsp+D0h] [rbp-528h] BYREF
  union _LARGE_INTEGER SystemTime[2]; // [rsp+E0h] [rbp-518h] BYREF
  __int128 v56; // [rsp+F0h] [rbp-508h]
  __int128 v57; // [rsp+100h] [rbp-4F8h]
  _BYTE v58[1128]; // [rsp+110h] [rbp-4E8h] BYREF
  _BYTE v59[56]; // [rsp+578h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5F8h] [rbp+0h]

  v40 = 0;
  v39[0] = 1;
  v0 = RtlCheckSystemBootStatusIntegrity(v39);
  if ( v0 == -1073741772 )
  {
    BootStatusDataFile = RtlCreateBootStatusDataFile();
    if ( BootStatusDataFile < 0 )
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x30B,
               (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
               (const char *)(unsigned int)BootStatusDataFile,
               OutputBufferLength);
    v40 = 1000;
    goto LABEL_13;
  }
  if ( v0 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x313,
             (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
             (const char *)(unsigned int)v0,
             OutputBufferLength);
  if ( !v39[0] )
  {
    v40 = 2000;
LABEL_13:
    v6 = 1;
    goto LABEL_14;
  }
  v41 = 0;
  BootStatusItem = Microsoft::Diagnostics::OsEvents::GetBootStatusItem(v1, RtlBsdItemVersionNumber, &v41);
  v5 = BootStatusItem;
  if ( BootStatusItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
      (const char *)(unsigned int)BootStatusItem,
      OutputBufferLength);
    return v5;
  }
  v6 = 0;
  if ( v41 < 0xC8 )
  {
    v40 = 3000;
    goto LABEL_13;
  }
LABEL_14:
  v7 = operator new(0x148u);
  memset_0(v7, 0, 0x148u);
  v8 = AbnormalShutdownData::AbnormalShutdownData((AbnormalShutdownData *)v7);
  v46 = v8;
  v9 = MEMORY[0x7FFE02C4];
  v41 = MEMORY[0x7FFE02C4];
  if ( !v6 )
  {
    v26 = 0;
    v40 = 0;
    SystemBootStatus = RtlGetSystemBootStatus(11, &v40, 4);
    if ( SystemBootStatus < 0 )
      v26 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x489,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
              (const char *)(unsigned int)SystemBootStatus,
              OutputBufferLength) < 0;
    v41 = 0;
    v28 = RtlGetSystemBootStatus(12, &v41, 4);
    if ( v28 < 0
      && wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x489,
           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
           (const char *)(unsigned int)v28,
           OutputBufferLength) < 0 )
    {
      v26 = 1;
    }
    Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo((__int64)&gs_lifetimeManager, &v52);
    v29 = v41 + 1;
    if ( v40 + 1 >= v41 + 1 )
      v29 = v40 + 1;
    if ( v9 > 0x10 && v29 < v9 - 16 )
      v29 = v9 - 16;
    v49 = 0;
    v48 = 0;
    v50[0] = 0;
    std::wstring::wstring(v53);
    v47 = 0;
    InputBuffer = 0;
    if ( v29 < v9 )
    {
      LODWORD(InputBuffer) = 7;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, v8, 0x20u) < 0 )
      {
        v26 = 1;
        *(_OWORD *)v8 = 0;
        *((_OWORD *)v8 + 1) = 0;
      }
      if ( !*((_QWORD *)v8 + 2) )
        v26 = 1;
      InputBuffer = 42;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v8 + 232, 0x20u) < 0 )
      {
        v26 = 1;
        *(_OWORD *)((char *)v8 + 232) = 0;
        *(_OWORD *)((char *)v8 + 248) = 0;
      }
      LODWORD(InputBuffer) = 22;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v8 + 32, 0x40u) < 0 )
      {
        v26 = 1;
        memset_0(&v54, 0, 0x40u);
        *((_OWORD *)v8 + 2) = v54;
        *((_OWORD *)v8 + 3) = *(_OWORD *)&SystemTime[0].LowPart;
        *((_OWORD *)v8 + 4) = v56;
        *((_OWORD *)v8 + 5) = v57;
      }
      LODWORD(InputBuffer) = 29;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v8 + 184, 0x30u) < 0 )
      {
        *(_OWORD *)((char *)v8 + 184) = 0;
        *(_OWORD *)((char *)v8 + 200) = 0;
        *(_OWORD *)((char *)v8 + 216) = 0;
      }
      LODWORD(InputBuffer) = 86;
      if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, (char *)v8 + 264, 8u) < 0 )
        *((_QWORD *)v8 + 33) = 0;
      *((_DWORD *)v8 + 44) = 7;
      if ( (int)NtQuerySystemInformationEx(72, (char *)v8 + 176, 4, (char *)v8 + 176, 8, 0) >= 0 )
      {
        v49 = *((_DWORD *)v8 + 45);
        if ( v49 )
        {
          *((_DWORD *)v8 + 44) = 8;
          if ( (int)NtQuerySystemInformationEx(72, (char *)v8 + 176, 4, (char *)v8 + 176, 8, 0) >= 0 )
            v48 = *((_DWORD *)v8 + 45);
        }
      }
      if ( NtQuerySystemInformation(SystemBootEnvironmentInformation, (char *)v8 + 144, 0x20u, 0) < 0 )
      {
        *((_OWORD *)v8 + 9) = 0;
        *((_OWORD *)v8 + 10) = 0;
      }
      *(_QWORD *)v44 = L"CrashDumpEnabled";
      v45 = 16;
      *(_QWORD *)v51 = L"System\\CurrentControlSet\\Control\\CrashControl";
      *(_QWORD *)&v51[2] = 45;
      Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, v51, v44, v50);
      v43 = 48;
      *(_QWORD *)v51 = L"Info";
      *(_QWORD *)&v51[2] = std::_WChar_traits<wchar_t>::length(L"Info");
      *(_QWORD *)v44 = L"System\\CurrentControlSet\\Control\\CrashControl\\LastCrashdump";
      v45 = std::_WChar_traits<wchar_t>::length(L"System\\CurrentControlSet\\Control\\CrashControl\\LastCrashdump");
      Microsoft::Diagnostics::Utils::Registry::GetBinary(v31, (int)v44, (int)v51, (_DWORD)v8 + 96, &v43);
      *(_QWORD *)v51 = L"VirtualMachineId";
      *(_QWORD *)&v51[2] = 16;
      *(_QWORD *)v44 = L"SOFTWARE\\Microsoft\\Virtual Machine\\Guest\\Parameters";
      v45 = 51;
      if ( (int)Microsoft::Diagnostics::Utils::Registry::GetString(-2147483646, v44, v51, v53) >= 0 )
        Microsoft::Diagnostics::Utils::String::NormalizeToBracelessUppercaseGuidString(v53);
    }
    if ( (int)Microsoft::Diagnostics::OsEvents::SetBootStatusItem(v30, RtlBsdItemReportedAbnormalShutdownBootId, v9 - 1) >= 0
      && (int)Microsoft::Diagnostics::OsEvents::GetBootStatusItem(v32, RtlBsdItemReportedAbnormalShutdownBootId, &v47) >= 0
      && v9 - 1 == v47 )
    {
      if ( !v26 )
      {
LABEL_69:
        OutputBuffer = 0;
        LODWORD(InputBuffer) = 50;
        if ( NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, &OutputBuffer, 1u) >= 0 )
        {
          v33 = OutputBuffer;
        }
        else
        {
          v33 = 0;
          OutputBuffer = 0;
        }
        if ( v33 && *((_DWORD *)v8 + 27) >= v29 && *((_DWORD *)v8 + 26) )
          OutputBuffer = 0;
        *((_BYTE *)v8 + 320) = v26;
        if ( (_QWORD *)((char *)v8 + 288) != v53 )
        {
          v34 = v53;
          if ( v53[3] > 7u )
            v34 = (_QWORD *)v53[0];
          std::wstring::assign((char *)v8 + 288, v34, v53[2]);
        }
        *((_DWORD *)v8 + 69) = v48;
        *((_DWORD *)v8 + 68) = v49;
        *((_DWORD *)v8 + 70) = v50[0];
        *((_BYTE *)v8 + 321) = OutputBuffer;
        while ( v29 < v9 )
        {
          Microsoft::Diagnostics::OsEvents::SendABSEvent(v29, v9, v40, v8);
          Microsoft::Diagnostics::OsEvents::SetBootStatusItem(v35, RtlBsdItemReportedAbnormalShutdownBootId, v29++);
        }
        std::wstring::_Tidy_deallocate(v53);
        goto LABEL_84;
      }
    }
    else
    {
      v26 = 1;
    }
    if ( v9 - v29 > 1 )
      v29 = v9 - 1;
    goto LABEL_69;
  }
  *(_QWORD *)v44 = L"OsEvents_BootStatReset_0";
  v45 = std::_WChar_traits<wchar_t>::length(L"OsEvents_BootStatReset_0");
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
    (unsigned int)v58,
    (unsigned int)v44,
    16779264,
    0,
    1,
    0,
    0);
  *(_QWORD *)v44 = L"ResetReason";
  v45 = std::_WChar_traits<wchar_t>::length(L"ResetReason");
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v58, v59, v44, &v40);
  *(_QWORD *)v44 = L"BootId";
  v45 = std::_WChar_traits<wchar_t>::length(L"BootId");
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>(v58, v59, v44, &v41);
  *(_OWORD *)v51 = 0;
  Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(&v43, v51);
  Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v58);
  OutputBuffer = 0;
  InputBuffer = 62;
  v10 = NtPowerInformation(SystemPowerStateLogging|0x40, &InputBuffer, 8u, &OutputBuffer, 1u);
  if ( !OutputBuffer && v10 >= 0 )
  {
    *((_BYTE *)v8 + 322) = 1;
    Microsoft::Diagnostics::OsEvents::SendABSEvent(0, 0, 0, v8);
  }
  v11 = RtlRestoreSystemBootStatusDefaults();
  if ( v11 < 0 )
  {
    v13 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x353,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)v11,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v58);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v13;
  }
  v14 = v41;
  v15 = Microsoft::Diagnostics::OsEvents::SetBootStatusItem(v12, RtlBsdItemBootId, v41);
  v17 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x356,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
      (const char *)(unsigned int)v15,
      OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v58);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v17;
  }
  v18 = Microsoft::Diagnostics::OsEvents::SetBootStatusItem(v16, RtlBsdItemShutdownBootId, v14 - 1);
  v19 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x359,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
      (const char *)(unsigned int)v18,
      OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v58);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v19;
  }
  v54 = 0;
  *(_OWORD *)&SystemTime[0].LowPart = 0;
  v20 = RtlGetSystemBootStatus(7, &v54, 32);
  if ( v20 < 0 )
  {
    v21 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x35D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)v20,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v58);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v21;
  }
  SystemTime[1].HighPart = v14;
  v22 = NtQuerySystemTime(SystemTime);
  if ( v22 < 0 )
  {
    v23 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x35F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)v22,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v58);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v23;
  }
  SystemTime[1].LowPart = RtlComputeCrc32(0, (PUCHAR)SystemTime, 8u);
  v24 = RtlSetSystemBootStatus(7, &v54, 32);
  if ( v24 < 0 )
  {
    v25 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x361,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\osevents.cpp",
            (const char *)(unsigned int)v24,
            OutputBufferLengtha);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v58);
    std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(&v46);
    return v25;
  }
  Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v58);
LABEL_84:
  if ( v8 )
  {
    std::wstring::_Tidy_deallocate((char *)v8 + 288);
    operator delete(v8, (const struct std::nothrow_t *)0x148);
  }
  return 0;
}

```

## disassembly

```asm
0x180135e5c  push    rbx
0x180135e5e  push    rsi
0x180135e5f  push    rdi
0x180135e60  push    r13
0x180135e62  push    r14
0x180135e64  push    r15
0x180135e66  sub     rsp, 5C8h
0x180135e6d  mov     rax, cs:__security_cookie
0x180135e74  xor     rax, rsp
0x180135e77  mov     [rsp+5F8h+var_48], rax
0x180135e7f  xor     r15d, r15d
0x180135e82  mov     [rsp+5F8h+var_5B4], r15d
0x180135e87  lea     r14d, [r15+1]
0x180135e8b  mov     [rsp+5F8h+var_5B7], r14b
0x180135e90  lea     rcx, [rsp+5F8h+var_5B7]
0x180135e95  call    cs:__imp_RtlCheckSystemBootStatusIntegrity
0x180135e9b  cmp     eax, 0C0000034h
0x180135ea0  jnz     short loc_180135EDC
0x180135ea2  xor     ecx, ecx
0x180135ea4  call    cs:__imp_RtlCreateBootStatusDataFile
0x180135eaa  test    eax, eax
0x180135eac  jns     short loc_180135ECF
0x180135eae  mov     rcx, [rsp+5F8h]; this
0x180135eb6  mov     r9d, eax; char *
0x180135eb9  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180135ec0  mov     edx, 30Bh; void *
0x180135ec5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180135eca  jmp     loc_180136896
0x180135ecf  mov     [rsp+5F8h+var_5B4], 3E8h
0x180135ed7  jmp     loc_180135F61
0x180135edc  test    eax, eax
0x180135ede  jns     short loc_180135F01
0x180135ee0  mov     rcx, [rsp+5F8h]; this
0x180135ee8  mov     r9d, eax; char *
0x180135eeb  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180135ef2  mov     edx, 313h; void *
0x180135ef7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180135efc  jmp     loc_180136896
0x180135f01  cmp     [rsp+5F8h+var_5B7], r15b
0x180135f06  jnz     short loc_180135F12
0x180135f08  mov     [rsp+5F8h+var_5B4], 7D0h
0x180135f10  jmp     short loc_180135F61
0x180135f12  mov     [rsp+5F8h+var_5B0], r15d
0x180135f17  lea     r8, [rsp+5F8h+var_5B0]; unsigned int *
0x180135f1c  xor     edx, edx; enum RTL_BSD_ITEM_TYPE
0x180135f1e  call    ?GetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@PEAK@Z; Microsoft::Diagnostics::OsEvents::GetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong *)
0x180135f23  mov     ebx, eax
0x180135f25  test    eax, eax
0x180135f27  jns     short loc_180135F4C
0x180135f29  mov     rcx, [rsp+5F8h]; this
0x180135f31  mov     r9d, eax; char *
0x180135f34  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180135f3b  mov     edx, 31Fh; void *
0x180135f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135f45  mov     eax, ebx
0x180135f47  jmp     loc_180136896
0x180135f4c  mov     dil, r15b
0x180135f4f  cmp     [rsp+5F8h+var_5B0], 0C8h
0x180135f57  jnb     short loc_180135F64
0x180135f59  mov     [rsp+5F8h+var_5B4], 0BB8h
0x180135f61  mov     dil, r14b
0x180135f64  mov     esi, 148h
0x180135f69  mov     ecx, esi; Size
0x180135f6b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180135f70  mov     rbx, rax
0x180135f73  mov     r8d, esi; Size
0x180135f76  xor     edx, edx; Val
0x180135f78  mov     rcx, rax; void *
0x180135f7b  call    memset_0
0x180135f80  mov     rcx, rbx; this
0x180135f83  call    ??0AbnormalShutdownData@@QEAA@XZ; AbnormalShutdownData::AbnormalShutdownData(void)
0x180135f88  mov     rbx, rax
0x180135f8b  mov     [rsp+5F8h+var_588], rax
0x180135f90  mov     r13d, ds:7FFE02C4h
0x180135f98  mov     [rsp+5F8h+var_5B0], r13d
0x180135f9d  test    dil, dil
0x180135fa0  jz      loc_18013630B
0x180135fa6  lea     rcx, aOseventsBootst; "OsEvents_BootStatReset_0"
0x180135fad  mov     qword ptr [rsp+5F8h+var_598], rcx
0x180135fb2  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180135fb7  mov     [rsp+5F8h+var_590], rax
0x180135fbc  mov     [rsp+5F8h+var_5C8], r15b
0x180135fc1  mov     byte ptr [rsp+5F8h+var_5D0], r15b
0x180135fc6  mov     byte ptr [rsp+5F8h+OutputBufferLength], r14b
0x180135fcb  mov     r9, 800000000000h
0x180135fd5  mov     r8d, 1000800h
0x180135fdb  lea     rdx, [rsp+5F8h+var_598]
0x180135fe0  lea     rcx, [rsp+5F8h+var_4E8]
0x180135fe8  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x180135fed  nop
0x180135fee  lea     rcx, aResetreason; "ResetReason"
0x180135ff5  mov     qword ptr [rsp+5F8h+var_598], rcx
0x180135ffa  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180135fff  mov     [rsp+5F8h+var_590], rax
0x180136004  lea     r9, [rsp+5F8h+var_5B4]
0x180136009  lea     r8, [rsp+5F8h+var_598]
0x18013600e  lea     rdx, [rsp+5F8h+var_80]
0x180136016  lea     rcx, [rsp+5F8h+var_4E8]
0x18013601e  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x180136023  lea     rcx, aBootid_0; "BootId"
0x18013602a  mov     qword ptr [rsp+5F8h+var_598], rcx
0x18013602f  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180136034  mov     [rsp+5F8h+var_590], rax
0x180136039  lea     r9, [rsp+5F8h+var_5B0]
0x18013603e  lea     r8, [rsp+5F8h+var_598]
0x180136043  lea     rdx, [rsp+5F8h+var_80]
0x18013604b  lea     rcx, [rsp+5F8h+var_4E8]
0x180136053  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x180136058  xorps   xmm0, xmm0
0x18013605b  movdqa  xmmword ptr [rsp+5F8h+var_568], xmm0
0x180136064  lea     rdx, [rsp+5F8h+var_568]
0x18013606c  lea     rcx, [rsp+5F8h+var_5A0]
0x180136071  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x180136076  mov     edx, [rax]
0x180136078  lea     rcx, [rsp+5F8h+var_4E8]; this
0x180136080  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x180136085  mov     [rsp+5F8h+OutputBuffer], r15b
0x18013608a  mov     [rsp+5F8h+InputBuffer], 3Eh ; '>'
0x180136093  mov     [rsp+5F8h+OutputBufferLength], r14d; int
0x180136098  lea     r9, [rsp+5F8h+OutputBuffer]; OutputBuffer
0x18013609d  mov     r14d, 8
0x1801360a3  mov     r8d, r14d; InputBufferLength
0x1801360a6  lea     rdx, [rsp+5F8h+InputBuffer]; InputBuffer
0x1801360ab  lea     ecx, [r14+4Fh]; PowerInformationLevel
0x1801360af  call    cs:__imp_NtPowerInformation
0x1801360b5  cmp     [rsp+5F8h+OutputBuffer], r15b
0x1801360ba  jnz     short loc_1801360D6
0x1801360bc  test    eax, eax
0x1801360be  js      short loc_1801360D6
0x1801360c0  mov     byte ptr [rbx+142h], 1
0x1801360c7  mov     r9, rbx; struct AbnormalShutdownData *
0x1801360ca  xor     r8d, r8d; unsigned int
0x1801360cd  xor     edx, edx; unsigned int
0x1801360cf  xor     ecx, ecx; unsigned int
0x1801360d1  call    ?SendABSEvent@OsEvents@Diagnostics@Microsoft@@CAXKKKPEBUAbnormalShutdownData@@@Z; Microsoft::Diagnostics::OsEvents::SendABSEvent(ulong,ulong,ulong,AbnormalShutdownData const *)
0x1801360d6  call    cs:__imp_RtlRestoreSystemBootStatusDefaults
0x1801360dc  test    eax, eax
0x1801360de  jns     short loc_18013611D
0x1801360e0  mov     rcx, [rsp+5F8h]; this
0x1801360e8  mov     r9d, eax; char *
0x1801360eb  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x1801360f2  mov     edx, 353h; void *
0x1801360f7  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801360fc  mov     ebx, eax
0x1801360fe  lea     rcx, [rsp+5F8h+var_4E8]; this
0x180136106  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18013610b  nop
0x18013610c  lea     rcx, [rsp+5F8h+var_588]
0x180136111  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x180136116  mov     eax, ebx
0x180136118  jmp     loc_180136896
0x18013611d  mov     esi, [rsp+5F8h+var_5B0]
0x180136121  mov     r8d, esi; unsigned int
0x180136124  mov     edx, 0Ah; enum RTL_BSD_ITEM_TYPE
0x180136129  call    ?SetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@K@Z; Microsoft::Diagnostics::OsEvents::SetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong)
0x18013612e  mov     edi, eax
0x180136130  test    eax, eax
0x180136132  jns     short loc_180136170
0x180136134  mov     rcx, [rsp+5F8h]; this
0x18013613c  mov     r9d, eax; char *
0x18013613f  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180136146  mov     edx, 356h; void *
0x18013614b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180136150  nop
0x180136151  lea     rcx, [rsp+5F8h+var_4E8]; this
0x180136159  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18013615e  nop
0x18013615f  lea     rcx, [rsp+5F8h+var_588]
0x180136164  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x180136169  mov     eax, edi
0x18013616b  jmp     loc_180136896
0x180136170  lea     r8d, [rsi-1]; unsigned int
0x180136174  mov     edx, 0Bh; enum RTL_BSD_ITEM_TYPE
0x180136179  call    ?SetBootStatusItem@OsEvents@Diagnostics@Microsoft@@CAJPEAXW4RTL_BSD_ITEM_TYPE@@K@Z; Microsoft::Diagnostics::OsEvents::SetBootStatusItem(void *,RTL_BSD_ITEM_TYPE,ulong)
0x18013617e  mov     edi, eax
0x180136180  test    eax, eax
0x180136182  jns     short loc_1801361C0
0x180136184  mov     rcx, [rsp+5F8h]; this
0x18013618c  mov     r9d, eax; char *
0x18013618f  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180136196  mov     edx, 359h; void *
0x18013619b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801361a0  nop
0x1801361a1  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1801361a9  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1801361ae  nop
0x1801361af  lea     rcx, [rsp+5F8h+var_588]
0x1801361b4  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1801361b9  mov     eax, edi
0x1801361bb  jmp     loc_180136896
0x1801361c0  xorps   xmm0, xmm0
0x1801361c3  movups  [rsp+5F8h+var_528], xmm0
0x1801361cb  movups  xmmword ptr [rsp+5F8h+SystemTime], xmm0
0x1801361d3  xor     r9d, r9d
0x1801361d6  lea     r15d, [r9+20h]
0x1801361da  mov     r8d, r15d
0x1801361dd  lea     rdx, [rsp+5F8h+var_528]
0x1801361e5  lea     ecx, [r9+7]
0x1801361e9  call    cs:__imp_RtlGetSystemBootStatus
0x1801361ef  test    eax, eax
0x1801361f1  jns     short loc_180136230
0x1801361f3  mov     rcx, [rsp+5F8h]; this
0x1801361fb  mov     r9d, eax; char *
0x1801361fe  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180136205  mov     edx, 35Dh; void *
0x18013620a  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18013620f  mov     ebx, eax
0x180136211  lea     rcx, [rsp+5F8h+var_4E8]; this
0x180136219  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18013621e  nop
0x18013621f  lea     rcx, [rsp+5F8h+var_588]
0x180136224  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x180136229  mov     eax, ebx
0x18013622b  jmp     loc_180136896
0x180136230  mov     dword ptr [rsp+5F8h+SystemTime+0Ch], esi
0x180136237  lea     rcx, [rsp+5F8h+SystemTime]; SystemTime
0x18013623f  call    cs:__imp_NtQuerySystemTime
0x180136245  test    eax, eax
0x180136247  jns     short loc_180136286
0x180136249  mov     rcx, [rsp+5F8h]; this
0x180136251  mov     r9d, eax; char *
0x180136254  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x18013625b  mov     edx, 35Fh; void *
0x180136260  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180136265  mov     ebx, eax
0x180136267  lea     rcx, [rsp+5F8h+var_4E8]; this
0x18013626f  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x180136274  nop
0x180136275  lea     rcx, [rsp+5F8h+var_588]
0x18013627a  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x18013627f  mov     eax, ebx
0x180136281  jmp     loc_180136896
0x180136286  mov     r8d, r14d; Length
0x180136289  lea     rdx, [rsp+5F8h+SystemTime]; Buffer
0x180136291  xor     ecx, ecx; InitialCrc
0x180136293  call    cs:__imp_RtlComputeCrc32
0x180136299  mov     dword ptr [rsp+5F8h+SystemTime+8], eax
0x1801362a0  xor     r9d, r9d
0x1801362a3  mov     r8d, r15d
0x1801362a6  lea     rdx, [rsp+5F8h+var_528]
0x1801362ae  lea     ecx, [r9+7]
0x1801362b2  call    cs:__imp_RtlSetSystemBootStatus
0x1801362b8  test    eax, eax
0x1801362ba  jns     short loc_1801362F9
0x1801362bc  mov     rcx, [rsp+5F8h]; this
0x1801362c4  mov     r9d, eax; char *
0x1801362c7  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x1801362ce  mov     edx, 361h; void *
0x1801362d3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1801362d8  mov     ebx, eax
0x1801362da  lea     rcx, [rsp+5F8h+var_4E8]; this
0x1801362e2  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1801362e7  nop
0x1801362e8  lea     rcx, [rsp+5F8h+var_588]
0x1801362ed  call    ??1?$unique_ptr@UAbnormalShutdownData@@U?$default_delete@UAbnormalShutdownData@@@std@@@std@@QEAA@XZ; std::unique_ptr<AbnormalShutdownData>::~unique_ptr<AbnormalShutdownData>(void)
0x1801362f2  mov     eax, ebx
0x1801362f4  jmp     loc_180136896
0x1801362f9  lea     rcx, [rsp+5F8h+var_4E8]; this
0x180136301  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x180136306  jmp     loc_180136870
0x18013630b  movzx   esi, r15b
0x18013630f  mov     [rsp+5F8h+var_5B4], r15d
0x180136314  xor     r9d, r9d
0x180136317  lea     edi, [r9+4]
0x18013631b  mov     r8d, edi
0x18013631e  lea     rdx, [rsp+5F8h+var_5B4]
0x180136323  lea     ecx, [rdi+7]
0x180136326  call    cs:__imp_RtlGetSystemBootStatus
0x18013632c  test    eax, eax
0x18013632e  jns     short loc_180136352
0x180136330  mov     rcx, [rsp+5F8h]; this
0x180136338  mov     r9d, eax; char *
0x18013633b  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180136342  mov     edx, 489h; void *
0x180136347  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18013634c  test    eax, eax
0x18013634e  cmovs   esi, r14d
0x180136352  mov     [rsp+5F8h+var_5B0], r15d
0x180136357  xor     r9d, r9d
0x18013635a  mov     r8d, edi
0x18013635d  lea     rdx, [rsp+5F8h+var_5B0]
0x180136362  lea     ecx, [r9+0Ch]
0x180136366  call    cs:__imp_RtlGetSystemBootStatus
0x18013636c  test    eax, eax
0x18013636e  jns     short loc_180136396
0x180136370  mov     rcx, [rsp+5F8h]; this
0x180136378  mov     r9d, eax; char *
0x18013637b  lea     r8, aOnecoreBaseTel_55; "onecore\\base\\telemetry\\utc\\service"...
0x180136382  mov     edx, 489h; void *
0x180136387  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18013638c  movzx   esi, sil
0x180136390  test    eax, eax
0x180136392  cmovs   esi, r14d
0x180136396  xor     r8d, r8d
0x180136399  lea     rdx, [rsp+5F8h+var_558]
0x1801363a1  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x1801363a8  call    ?GetAuthorizationInfo@LifetimeManager@Diagnostics@Microsoft@@QEAA?AVAuthorizationInfo@23@_N@Z; Microsoft::Diagnostics::LifetimeManager::GetAuthorizationInfo(bool)
0x1801363ad  mov     edi, [rsp+5F8h+var_5B0]
0x1801363b1  inc     edi
0x1801363b3  mov     eax, [rsp+5F8h+var_5B4]
  ... truncated ...
```
