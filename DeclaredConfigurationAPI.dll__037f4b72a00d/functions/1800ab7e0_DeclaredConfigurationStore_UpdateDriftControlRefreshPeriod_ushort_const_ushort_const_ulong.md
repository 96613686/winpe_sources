# DeclaredConfigurationStore_UpdateDriftControlRefreshPeriod(ushort const *,ushort const *,ulong)

- ea: `0x1800ab7e0`
- end: `0x1800abb4f`
- name: `?DeclaredConfigurationStore_UpdateDriftControlRefreshPeriod@@YAJPEBG0K@Z`
- size: `879`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x18001d0b0`
- `0x18004d1ac`
- `0x1800a212c`
- `0x1800ab7e0`
- `0x1800abdf0`
- `0x1800f5c8c`
- `0x1800f9fe4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ababe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ababe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800aba35`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800aba35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab9cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab9cb`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800ab924`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800ab924`

## string_xrefs

- `0x1800ab83d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab893`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab963`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800aba5c`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\driftcontrol.cpp`
- `0x1800ab931`: `OSData\Software\Microsoft\DeclaredConfiguration\ManagementServiceConfiguration\%s`
- `0x1800ab92a`: `Software\Microsoft\DeclaredConfiguration\ManagementServiceConfiguration\%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeclaredConfigurationStore_UpdateDriftControlRefreshPeriod(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned int a3)
{
  signed int updated; // ebx
  CDeclaredConfigurationLogger *Logger; // rax
  CDeclaredConfigurationLogger *v6; // rax
  char IsStateSeparationEnabled; // al
  const unsigned __int16 *v8; // r8
  int v9; // eax
  CDeclaredConfigurationLogger *v10; // rax
  LSTATUS v11; // eax
  LSTATUS Key; // eax
  CDeclaredConfigurationLogger *v13; // rax
  LSTATUS v14; // eax
  CDeclaredConfigurationLogger *v15; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v21; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey[5]; // [rsp+68h] [rbp-98h] BYREF
  char v23; // [rsp+90h] [rbp-70h]
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]
  unsigned __int16 *v26; // [rsp+2D8h] [rbp+1D8h] BYREF

  v26 = a2;
  v21 = a1;
  *(_DWORD *)Data = a3;
  v19 = 0;
  hKey[0] = 0;
  if ( a1 )
  {
    hKey[1] = (HKEY)&v21;
    hKey[2] = (HKEY)&v26;
    hKey[3] = (HKEY)Data;
    hKey[4] = (HKEY)&v19;
    v23 = 1;
    if ( a2 )
    {
      updated = -2147024846;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
        (const char *)0x80070032LL,
        phkResult);
      Logger = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(
        Logger,
        v21,
        v26,
        *(unsigned int *)Data,
        v19);
    }
    else if ( a3 >= 0x1E )
    {
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
      v8 = L"OSData\\Software\\Microsoft\\DeclaredConfiguration\\ManagementServiceConfiguration\\%s";
      if ( !IsStateSeparationEnabled )
        v8 = L"Software\\Microsoft\\DeclaredConfiguration\\ManagementServiceConfiguration\\%s";
      v9 = StringCchPrintfW(SubKey, 0x104u, v8, a1);
      updated = v9;
      v19 = v9;
      if ( v9 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          hKey,
          0);
        v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x2011Fu, hKey);
        updated = v11;
        if ( v11 > 0 )
          updated = (unsigned __int16)v11 | 0x80070000;
        v19 = updated;
        if ( updated == -2147024894 )
        {
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            hKey,
            0);
          Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2011Fu, 0, hKey, 0);
          updated = Key;
          if ( Key > 0 )
            updated = (unsigned __int16)Key | 0x80070000;
          v19 = updated;
        }
        if ( updated >= 0 )
        {
          v14 = RegSetValueExW(hKey[0], L"RefreshInterval", 0, 4u, Data, 4u);
          updated = v14;
          if ( v14 > 0 )
            updated = (unsigned __int16)v14 | 0x80070000;
          v19 = updated;
          if ( updated >= 0 )
          {
            updated = DeclaredConfigurationStore_UpdateRefreshScheduleTask(v21);
            v19 = updated;
            if ( updated == -2147024894 )
            {
              v19 = 0;
              updated = 0;
            }
          }
          v15 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(
            v15,
            v21,
            v26,
            *(unsigned int *)Data,
            v19);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x181,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
            (const char *)(unsigned int)updated,
            phkResulta);
          v13 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(
            v13,
            v21,
            v26,
            *(unsigned int *)Data,
            v19);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
          (const char *)(unsigned int)v9,
          phkResult);
        v10 = CDeclaredConfigurationLogger::GetLogger();
        CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(
          v10,
          v21,
          v26,
          *(unsigned int *)Data,
          v19);
      }
    }
    else
    {
      if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
        McTemplateU0q_EventWriteTransfer(a1, DcCspRefreshIntervalTooSmall, 30);
      v6 = CDeclaredConfigurationLogger::GetLogger();
      CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(
        v6,
        v21,
        v26,
        *(unsigned int *)Data,
        v19);
      updated = -2147024809;
    }
  }
  else
  {
    updated = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x155,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\driftcontrol.cpp",
      (const char *)0x80070057LL,
      phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800ab7e0  mov     [rsp-8+arg_18], rbx
0x1800ab7e5  mov     [rsp-8+arg_8], rdx
0x1800ab7ea  push    rbp
0x1800ab7eb  lea     rbp, [rsp-1C0h]
0x1800ab7f3  sub     rsp, 2C0h
0x1800ab7fa  mov     rax, cs:__security_cookie
0x1800ab801  xor     rax, rsp
0x1800ab804  mov     [rbp+1C0h+var_10], rax
0x1800ab80b  mov     rbx, rcx
0x1800ab80e  mov     [rsp+2C0h+var_260], rcx
0x1800ab813  mov     dword ptr [rsp+2C0h+Data], r8d
0x1800ab818  mov     [rsp+2C0h+var_270], 0
0x1800ab820  mov     [rsp+2C0h+hKey], 0
0x1800ab829  test    rcx, rcx
0x1800ab82c  jnz     short loc_1800AB853
0x1800ab82e  mov     rcx, [rbp+1C8h]; this
0x1800ab835  mov     ebx, 80070057h
0x1800ab83a  mov     r9d, ebx; char *
0x1800ab83d  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab844  mov     edx, 155h; void *
0x1800ab849  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab84e  jmp     loc_1800ABB23
0x1800ab853  lea     rax, [rsp+2C0h+var_260]
0x1800ab858  mov     [rsp+2C0h+var_250], rax
0x1800ab85d  lea     rax, [rbp+1C0h+arg_8]
0x1800ab864  mov     [rsp+2C0h+var_248], rax
0x1800ab869  lea     rax, [rsp+2C0h+Data]
0x1800ab86e  mov     [rbp+1C0h+var_240], rax
0x1800ab872  lea     rax, [rsp+2C0h+var_270]
0x1800ab877  mov     [rbp+1C0h+var_238], rax
0x1800ab87b  mov     [rbp+1C0h+var_230], 1
0x1800ab87f  test    rdx, rdx
0x1800ab882  jz      short loc_1800AB8D1
0x1800ab884  mov     rcx, [rbp+1C8h]; this
0x1800ab88b  mov     ebx, 80070032h
0x1800ab890  mov     r9d, ebx; char *
0x1800ab893  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab89a  mov     edx, 15Eh; void *
0x1800ab89f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab8a4  nop
0x1800ab8a5  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab8aa  mov     ecx, [rsp+2C0h+var_270]
0x1800ab8ae  mov     dword ptr [rsp+2C0h+phkResult], ecx; int
0x1800ab8b2  mov     r9d, dword ptr [rsp+2C0h+Data]; unsigned int
0x1800ab8b7  mov     r8, [rbp+1C0h+arg_8]; unsigned __int16 *
0x1800ab8be  mov     rdx, [rsp+2C0h+var_260]; unsigned __int16 *
0x1800ab8c3  mov     rcx, rax; this
0x1800ab8c6  call    ?LogOrchestratorUpdateDriftControlRefreshPeriod@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(ushort const *,ushort const *,ulong,long)
0x1800ab8cb  nop
0x1800ab8cc  jmp     loc_1800ABB23
0x1800ab8d1  cmp     r8d, 1Eh
0x1800ab8d5  jnb     short loc_1800AB924
0x1800ab8d7  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x1800ab8de  jz      short loc_1800AB8F3
0x1800ab8e0  mov     r8d, 1Eh
0x1800ab8e6  lea     rdx, DcCspRefreshIntervalTooSmall
0x1800ab8ed  call    McTemplateU0q_EventWriteTransfer
0x1800ab8f2  nop
0x1800ab8f3  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab8f8  mov     ecx, [rsp+2C0h+var_270]
0x1800ab8fc  mov     dword ptr [rsp+2C0h+phkResult], ecx; int
0x1800ab900  mov     r9d, dword ptr [rsp+2C0h+Data]; unsigned int
0x1800ab905  mov     r8, [rbp+1C0h+arg_8]; unsigned __int16 *
0x1800ab90c  mov     rdx, [rsp+2C0h+var_260]; unsigned __int16 *
0x1800ab911  mov     rcx, rax; this
0x1800ab914  call    ?LogOrchestratorUpdateDriftControlRefreshPeriod@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(ushort const *,ushort const *,ulong,long)
0x1800ab919  nop
0x1800ab91a  mov     ebx, 80070057h
0x1800ab91f  jmp     loc_1800ABB23
0x1800ab924  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800ab92a  lea     rcx, aSoftwareMicros_70; "Software\\Microsoft\\DeclaredConfigurat"...
0x1800ab931  lea     r8, aOsdataSoftware_58; "OSData\\Software\\Microsoft\\DeclaredCo"...
0x1800ab938  test    al, al
0x1800ab93a  cmovz   r8, rcx; unsigned __int16 *
0x1800ab93e  mov     r9, rbx
0x1800ab941  mov     edx, 104h; unsigned __int64
0x1800ab946  lea     rcx, [rbp+1C0h+SubKey]; unsigned __int16 *
0x1800ab94a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ab94f  mov     ebx, eax
0x1800ab951  mov     [rsp+2C0h+var_270], eax
0x1800ab955  test    eax, eax
0x1800ab957  jns     short loc_1800AB9A1
0x1800ab959  mov     rcx, [rbp+1C8h]; this
0x1800ab960  mov     r9d, eax; char *
0x1800ab963  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800ab96a  mov     edx, 16Ah; void *
0x1800ab96f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab974  nop
0x1800ab975  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800ab97a  mov     ecx, [rsp+2C0h+var_270]
0x1800ab97e  mov     dword ptr [rsp+2C0h+phkResult], ecx; int
0x1800ab982  mov     r9d, dword ptr [rsp+2C0h+Data]; unsigned int
0x1800ab987  mov     r8, [rbp+1C0h+arg_8]; unsigned __int16 *
0x1800ab98e  mov     rdx, [rsp+2C0h+var_260]; unsigned __int16 *
0x1800ab993  mov     rcx, rax; this
0x1800ab996  call    ?LogOrchestratorUpdateDriftControlRefreshPeriod@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(ushort const *,ushort const *,ulong,long)
0x1800ab99b  nop
0x1800ab99c  jmp     loc_1800ABB23
0x1800ab9a1  xor     edx, edx
0x1800ab9a3  lea     rcx, [rsp+2C0h+hKey]
0x1800ab9a8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ab9ad  lea     rax, [rsp+2C0h+hKey]
0x1800ab9b2  mov     [rsp+2C0h+phkResult], rax; phkResult
0x1800ab9b7  mov     r9d, 2011Fh; samDesired
0x1800ab9bd  xor     r8d, r8d; ulOptions
0x1800ab9c0  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x1800ab9c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab9cb  call    cs:__imp_RegOpenKeyExW
0x1800ab9d1  mov     ebx, eax
0x1800ab9d3  test    eax, eax
0x1800ab9d5  jle     short loc_1800AB9E0
0x1800ab9d7  movzx   ebx, ax
0x1800ab9da  or      ebx, 80070000h
0x1800ab9e0  mov     [rsp+2C0h+var_270], ebx
0x1800ab9e4  cmp     ebx, 80070002h
0x1800ab9ea  jnz     short loc_1800ABA4E
0x1800ab9ec  xor     edx, edx
0x1800ab9ee  lea     rcx, [rsp+2C0h+hKey]
0x1800ab9f3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ab9f8  mov     [rsp+2C0h+lpdwDisposition], 0; lpdwDisposition
0x1800aba01  lea     rax, [rsp+2C0h+hKey]
0x1800aba06  mov     [rsp+2C0h+var_288], rax; phkResult
0x1800aba0b  mov     [rsp+2C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800aba14  mov     [rsp+2C0h+samDesired], 2011Fh; samDesired
0x1800aba1c  mov     dword ptr [rsp+2C0h+phkResult], 0; int
0x1800aba24  xor     r9d, r9d; lpClass
0x1800aba27  xor     r8d, r8d; Reserved
0x1800aba2a  lea     rdx, [rbp+1C0h+SubKey]; lpSubKey
0x1800aba2e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aba35  call    cs:__imp_RegCreateKeyExW
0x1800aba3b  mov     ebx, eax
0x1800aba3d  test    eax, eax
0x1800aba3f  jle     short loc_1800ABA4A
0x1800aba41  movzx   ebx, ax
0x1800aba44  or      ebx, 80070000h
0x1800aba4a  mov     [rsp+2C0h+var_270], ebx
0x1800aba4e  test    ebx, ebx
0x1800aba50  jns     short loc_1800ABA9A
0x1800aba52  mov     rcx, [rbp+1C8h]; this
0x1800aba59  mov     r9d, ebx; char *
0x1800aba5c  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800aba63  mov     edx, 181h; void *
0x1800aba68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aba6d  nop
0x1800aba6e  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800aba73  mov     ecx, [rsp+2C0h+var_270]
0x1800aba77  mov     dword ptr [rsp+2C0h+phkResult], ecx; int
0x1800aba7b  mov     r9d, dword ptr [rsp+2C0h+Data]; unsigned int
0x1800aba80  mov     r8, [rbp+1C0h+arg_8]; unsigned __int16 *
0x1800aba87  mov     rdx, [rsp+2C0h+var_260]; unsigned __int16 *
0x1800aba8c  mov     rcx, rax; this
0x1800aba8f  call    ?LogOrchestratorUpdateDriftControlRefreshPeriod@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(ushort const *,ushort const *,ulong,long)
0x1800aba94  nop
0x1800aba95  jmp     loc_1800ABB23
0x1800aba9a  mov     r9d, 4; dwType
0x1800abaa0  mov     [rsp+2C0h+samDesired], r9d; cbData
0x1800abaa5  lea     rax, [rsp+2C0h+Data]
0x1800abaaa  mov     [rsp+2C0h+phkResult], rax; lpData
0x1800abaaf  xor     r8d, r8d; Reserved
0x1800abab2  lea     rdx, aRefreshinterva; "RefreshInterval"
0x1800abab9  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800ababe  call    cs:__imp_RegSetValueExW
0x1800abac4  mov     ebx, eax
0x1800abac6  test    eax, eax
0x1800abac8  jle     short loc_1800ABAD3
0x1800abaca  movzx   ebx, ax
0x1800abacd  or      ebx, 80070000h
0x1800abad3  mov     [rsp+2C0h+var_270], ebx
0x1800abad7  test    ebx, ebx
0x1800abad9  js      short loc_1800ABAFC
0x1800abadb  mov     rcx, [rsp+2C0h+var_260]; unsigned __int16 *
0x1800abae0  call    ?DeclaredConfigurationStore_UpdateRefreshScheduleTask@@YAJPEBG@Z; DeclaredConfigurationStore_UpdateRefreshScheduleTask(ushort const *)
0x1800abae5  mov     ebx, eax
0x1800abae7  mov     [rsp+2C0h+var_270], eax
0x1800abaeb  cmp     eax, 80070002h
0x1800abaf0  jnz     short loc_1800ABAFC
0x1800abaf2  mov     [rsp+2C0h+var_270], 0
0x1800abafa  xor     ebx, ebx
0x1800abafc  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1800abb01  mov     ecx, [rsp+2C0h+var_270]
0x1800abb05  mov     dword ptr [rsp+2C0h+phkResult], ecx; int
0x1800abb09  mov     r9d, dword ptr [rsp+2C0h+Data]; unsigned int
0x1800abb0e  mov     r8, [rbp+1C0h+arg_8]; unsigned __int16 *
0x1800abb15  mov     rdx, [rsp+2C0h+var_260]; unsigned __int16 *
0x1800abb1a  mov     rcx, rax; this
0x1800abb1d  call    ?LogOrchestratorUpdateDriftControlRefreshPeriod@CDeclaredConfigurationLogger@@QEAAXPEBG0KJ@Z; CDeclaredConfigurationLogger::LogOrchestratorUpdateDriftControlRefreshPeriod(ushort const *,ushort const *,ulong,long)
0x1800abb22  nop
0x1800abb23  lea     rcx, [rsp+2C0h+hKey]
0x1800abb28  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800abb2d  mov     eax, ebx
0x1800abb2f  mov     rcx, [rbp+1C0h+var_10]
0x1800abb36  xor     rcx, rsp; StackCookie
0x1800abb39  call    __security_check_cookie
0x1800abb3e  mov     rbx, [rsp+2C0h+arg_18]
0x1800abb46  add     rsp, 2C0h
0x1800abb4d  pop     rbp
0x1800abb4e  retn
```
