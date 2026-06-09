# _ModernDeployment::Autopilot::Core::FwtDeviceIdentityCollector::Collect_::_25_::_lambda_1_::operator()

- ea: `0x1800e4764`
- end: `0x1800e4a92`
- name: `_ModernDeployment::Autopilot::Core::FwtDeviceIdentityCollector::Collect_::_25_::_lambda_1_::operator()`
- size: `814`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e4dc0`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x1800813fc`
- `0x1800e17d0`
- `0x1800e1880`
- `0x1800e4764`
- `0x180197b1c`
- `0x180197b60`
- `0x180197ba4`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e48f7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e48f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e48da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e48da`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800e49e1`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800e49e1`

## string_xrefs

- `0x1800e48d3`: `powrprof.dll`
- `0x1800e4865`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceidentitycollector.cpp`
- `0x1800e49ac`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceidentitycollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::FwtDeviceIdentityCollector::Collect_::_25_::_lambda_1_::operator()(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  const unsigned __int16 *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // r8
  __int64 v20; // r8
  const wchar_t *v22; // [rsp+20h] [rbp-69h] BYREF
  __int64 v23; // [rsp+28h] [rbp-61h]
  const wchar_t *v24; // [rsp+30h] [rbp-59h] BYREF
  __int64 v25; // [rsp+38h] [rbp-51h]
  const wchar_t *SystemPowerStatus; // [rsp+40h] [rbp-49h] BYREF
  __int64 SystemPowerStatus_8; // [rsp+48h] [rbp-41h]
  __int128 v28; // [rsp+50h] [rbp-39h] BYREF
  __int64 v29; // [rsp+60h] [rbp-29h]
  __int64 v30; // [rsp+68h] [rbp-21h]
  __int128 v31; // [rsp+70h] [rbp-19h] BYREF
  __int64 v32; // [rsp+80h] [rbp-9h]
  __int64 v33; // [rsp+88h] [rbp-1h]
  __int128 v34; // [rsp+90h] [rbp+7h] BYREF
  __int64 v35; // [rsp+A0h] [rbp+17h]
  __int64 v36; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v34 = 0;
  v35 = 0;
  v36 = 7;
  LOWORD(v34) = 0;
  v31 = 0;
  v32 = 0;
  v33 = 7;
  LOWORD(v31) = 0;
  v28 = 0;
  v29 = 0;
  v30 = 7;
  LOWORD(v28) = 0;
  if ( (int)Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoManufacturer(&v34) < 0
    || (v3 = v35) == 0
    || (SystemPowerStatus = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v34),
        SystemPowerStatus_8 = v3,
        v22 = L"Make",
        v23 = 4,
        v4 = ModernDeployment::Autopilot::Core::MachineContext::SetString(a2, &v22, &SystemPowerStatus),
        v5 = v4,
        v4 >= 0) )
  {
    if ( (int)Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoModel(&v31) < 0
      || (v6 = v32) == 0
      || (v22 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v31),
          v23 = v6,
          SystemPowerStatus = L"Model",
          SystemPowerStatus_8 = 5,
          v4 = ModernDeployment::Autopilot::Core::MachineContext::SetString(a2, &SystemPowerStatus, &v22),
          v5 = v4,
          v4 >= 0) )
    {
      if ( (int)Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoSerialNumber(&v28) < 0
        || (v7 = v29) == 0
        || (v22 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v28),
            v23 = v7,
            SystemPowerStatus = L"DeviceSerialNumber",
            SystemPowerStatus_8 = 18,
            v4 = ModernDeployment::Autopilot::Core::MachineContext::SetString(a2, &SystemPowerStatus, &v22),
            v5 = v4,
            v4 >= 0) )
      {
        Library = LoadLibraryExW(L"powrprof.dll", 0, 0x800u);
        SystemPowerStatus = (const wchar_t *)Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "PowerDeterminePlatformRoleEx");
          if ( ProcAddress )
          {
            v10 = ((__int64 (__fastcall *)(__int64))ProcAddress)(2) - 1;
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                v12 = v11 - 1;
                if ( v12 )
                {
                  v13 = v12 - 1;
                  if ( v13 && (v14 = v13 - 1) != 0 && (v15 = v14 - 2) != 0 )
                    v16 = v15 == 1 ? L"Tablet" : L"Unknown";
                  else
                    v16 = L"Server";
                }
                else
                {
                  v16 = L"Workstation";
                }
              }
              else
              {
                v16 = L"Laptop";
              }
            }
            else
            {
              v16 = L"Desktop";
            }
            v17 = -1;
            do
              ++v17;
            while ( v16[v17] );
            v22 = v16;
            v23 = v17;
            v24 = L"ChassisType";
            v25 = 11;
            v18 = ModernDeployment::Autopilot::Core::MachineContext::SetString(a2, &v24, &v22);
            v5 = v18;
            if ( v18 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x9E,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtdeviceid"
                              "entitycollector.cpp",
                (const char *)(unsigned int)v18,
                (int)v22);
              wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&SystemPowerStatus);
              goto LABEL_38;
            }
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&SystemPowerStatus);
        SystemPowerStatus = 0;
        LODWORD(SystemPowerStatus_8) = 0;
        if ( !GetSystemPowerStatus((LPSYSTEM_POWER_STATUS)&SystemPowerStatus) )
          goto LABEL_37;
        if ( BYTE1(SystemPowerStatus) == 0x80 || (LOBYTE(v19) = 1, BYTE1(SystemPowerStatus) == 0xFF) )
          LOBYTE(v19) = 0;
        v24 = L"BatteryPresent";
        v25 = 14;
        v4 = ModernDeployment::Autopilot::Core::MachineContext::SetBool(a2, &v24, v19);
        v5 = v4;
        if ( v4 >= 0 )
        {
          if ( (_BYTE)SystemPowerStatus == 0xFF
            || (LOBYTE(v20) = (_BYTE)SystemPowerStatus == 1,
                v24 = L"ACPowerConnected",
                v25 = 16,
                v4 = ModernDeployment::Autopilot::Core::MachineContext::SetBool(a2, &v24, v20),
                v5 = v4,
                v4 >= 0) )
          {
LABEL_37:
            v5 = 0;
            goto LABEL_38;
          }
        }
      }
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9E,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\fastwindowstelemetry\\fwtdeviceidentitycollector.cpp",
    (const char *)(unsigned int)v4,
    (int)v22);
LABEL_38:
  std::wstring::_Tidy_deallocate(&v28);
  std::wstring::_Tidy_deallocate(&v31);
  std::wstring::_Tidy_deallocate(&v34);
  return v5;
}

```

## disassembly

```asm
0x1800e4764  push    rbp
0x1800e4766  push    rbx
0x1800e4767  push    rsi
0x1800e4768  push    rdi
0x1800e4769  lea     rbp, [rsp-3Fh]
0x1800e476e  sub     rsp, 0C8h
0x1800e4775  mov     rax, cs:__security_cookie
0x1800e477c  xor     rax, rsp
0x1800e477f  mov     [rbp+57h+var_30], rax
0x1800e4783  mov     rdi, rdx
0x1800e4786  xorps   xmm0, xmm0
0x1800e4789  movups  [rbp+57h+var_50], xmm0
0x1800e478d  xor     esi, esi
0x1800e478f  mov     [rbp+57h+var_40], rsi
0x1800e4793  lea     ecx, [rsi+7]
0x1800e4796  mov     [rbp+57h+var_38], rcx
0x1800e479a  mov     word ptr [rbp+57h+var_50], si
0x1800e479e  movups  [rbp+57h+var_70], xmm0
0x1800e47a2  mov     [rbp+57h+var_60], rsi
0x1800e47a6  mov     [rbp+57h+var_58], rcx
0x1800e47aa  mov     word ptr [rbp+57h+var_70], si
0x1800e47ae  movups  [rbp+57h+var_90], xmm0
0x1800e47b2  mov     [rbp+57h+var_80], rsi
0x1800e47b6  mov     [rbp+57h+var_78], rcx
0x1800e47ba  mov     word ptr [rbp+57h+var_90], si
0x1800e47be  lea     rcx, [rbp+57h+var_50]
0x1800e47c2  call    ?GetSmBiosSystemInfoManufacturer@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoManufacturer(std::wstring &)
0x1800e47c7  test    eax, eax
0x1800e47c9  js      short loc_1800E480E
0x1800e47cb  mov     rbx, [rbp+57h+var_40]
0x1800e47cf  test    rbx, rbx
0x1800e47d2  jz      short loc_1800E480E
0x1800e47d4  lea     rcx, [rbp+57h+var_50]
0x1800e47d8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e47dd  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e47e1  mov     qword ptr [rbp+57h+SystemPowerStatus+8], rbx
0x1800e47e5  lea     rax, aMake; "Make"
0x1800e47ec  mov     [rbp+57h+var_C0], rax
0x1800e47f0  mov     [rbp+57h+var_B8], 4
0x1800e47f8  lea     r8, [rbp+57h+SystemPowerStatus]
0x1800e47fc  lea     rdx, [rbp+57h+var_C0]
0x1800e4800  mov     rcx, rdi
0x1800e4803  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e4808  mov     ebx, eax
0x1800e480a  test    eax, eax
0x1800e480c  js      short loc_1800E485E
0x1800e480e  lea     rcx, [rbp+57h+var_70]
0x1800e4812  call    ?GetSmBiosSystemInfoModel@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoModel(std::wstring &)
0x1800e4817  test    eax, eax
0x1800e4819  js      short loc_1800E487B
0x1800e481b  mov     rbx, [rbp+57h+var_60]
0x1800e481f  test    rbx, rbx
0x1800e4822  jz      short loc_1800E487B
0x1800e4824  lea     rcx, [rbp+57h+var_70]
0x1800e4828  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e482d  mov     [rbp+57h+var_C0], rax
0x1800e4831  mov     [rbp+57h+var_B8], rbx
0x1800e4835  lea     rax, aModel; "Model"
0x1800e483c  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e4840  mov     qword ptr [rbp+57h+SystemPowerStatus+8], 5
0x1800e4848  lea     r8, [rbp+57h+var_C0]
0x1800e484c  lea     rdx, [rbp+57h+SystemPowerStatus]
0x1800e4850  mov     rcx, rdi
0x1800e4853  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e4858  mov     ebx, eax
0x1800e485a  test    eax, eax
0x1800e485c  jns     short loc_1800E487B
0x1800e485e  mov     rcx, [rbp+5Fh]; this
0x1800e4862  mov     r9d, eax; char *
0x1800e4865  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e486c  mov     edx, 9Eh; void *
0x1800e4871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4876  jmp     loc_1800E4A5D
0x1800e487b  lea     rcx, [rbp+57h+var_90]
0x1800e487f  call    ?GetSmBiosSystemInfoSerialNumber@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoSerialNumber(std::wstring &)
0x1800e4884  test    eax, eax
0x1800e4886  js      short loc_1800E48CB
0x1800e4888  mov     rbx, [rbp+57h+var_80]
0x1800e488c  test    rbx, rbx
0x1800e488f  jz      short loc_1800E48CB
0x1800e4891  lea     rcx, [rbp+57h+var_90]
0x1800e4895  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e489a  mov     [rbp+57h+var_C0], rax
0x1800e489e  mov     [rbp+57h+var_B8], rbx
0x1800e48a2  lea     rax, aDeviceserialnu; "DeviceSerialNumber"
0x1800e48a9  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e48ad  mov     qword ptr [rbp+57h+SystemPowerStatus+8], 12h
0x1800e48b5  lea     r8, [rbp+57h+var_C0]
0x1800e48b9  lea     rdx, [rbp+57h+SystemPowerStatus]
0x1800e48bd  mov     rcx, rdi
0x1800e48c0  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e48c5  mov     ebx, eax
0x1800e48c7  test    eax, eax
0x1800e48c9  js      short loc_1800E485E
0x1800e48cb  xor     edx, edx; hFile
0x1800e48cd  mov     r8d, 800h; dwFlags
0x1800e48d3  lea     rcx, LibFileName; "powrprof.dll"
0x1800e48da  call    cs:__imp_LoadLibraryExW
0x1800e48e0  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e48e4  test    rax, rax
0x1800e48e7  jz      loc_1800E49CB
0x1800e48ed  lea     rdx, aPowerdetermine; "PowerDeterminePlatformRoleEx"
0x1800e48f4  mov     rcx, rax; hModule
0x1800e48f7  call    cs:__imp_GetProcAddress
0x1800e48fd  test    rax, rax
0x1800e4900  jz      loc_1800E49CB
0x1800e4906  mov     ecx, 2
0x1800e490b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4910  sub     eax, 1
0x1800e4913  jz      short loc_1800E4960
0x1800e4915  sub     eax, 1
0x1800e4918  jz      short loc_1800E4957
0x1800e491a  sub     eax, 1
0x1800e491d  jz      short loc_1800E494E
0x1800e491f  sub     eax, 1
0x1800e4922  jz      short loc_1800E4945
0x1800e4924  sub     eax, 1
0x1800e4927  jz      short loc_1800E4945
0x1800e4929  sub     eax, 2
0x1800e492c  jz      short loc_1800E4945
0x1800e492e  cmp     eax, 1
0x1800e4931  jz      short loc_1800E493C
0x1800e4933  lea     rax, ?ChassisTypeUnknown@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Unknown"
0x1800e493a  jmp     short loc_1800E4967
0x1800e493c  lea     rax, ?ChassisTypeTablet@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Tablet"
0x1800e4943  jmp     short loc_1800E4967
0x1800e4945  lea     rax, ?ChassisTypeServer@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Server"
0x1800e494c  jmp     short loc_1800E4967
0x1800e494e  lea     rax, ?ChassisTypeWorkstation@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Workstation"
0x1800e4955  jmp     short loc_1800E4967
0x1800e4957  lea     rax, ?ChassisTypeLaptop@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Laptop"
0x1800e495e  jmp     short loc_1800E4967
0x1800e4960  lea     rax, ?ChassisTypeDesktop@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Desktop"
0x1800e4967  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800e496b  inc     rcx
0x1800e496e  cmp     [rax+rcx*2], si
0x1800e4972  jnz     short loc_1800E496B
0x1800e4974  mov     [rbp+57h+var_C0], rax
0x1800e4978  mov     [rbp+57h+var_B8], rcx
0x1800e497c  lea     rax, aChassistype; "ChassisType"
0x1800e4983  mov     [rbp+57h+var_B0], rax
0x1800e4987  mov     [rbp+57h+var_A8], 0Bh
0x1800e498f  lea     r8, [rbp+57h+var_C0]
0x1800e4993  lea     rdx, [rbp+57h+var_B0]
0x1800e4997  mov     rcx, rdi
0x1800e499a  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e499f  mov     ebx, eax
0x1800e49a1  test    eax, eax
0x1800e49a3  jns     short loc_1800E49CB
0x1800e49a5  mov     rcx, [rbp+5Fh]; this
0x1800e49a9  mov     r9d, eax; char *
0x1800e49ac  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e49b3  mov     edx, 9Eh; void *
0x1800e49b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e49bd  lea     rcx, [rbp+57h+SystemPowerStatus]
0x1800e49c1  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800e49c6  jmp     loc_1800E4A5D
0x1800e49cb  lea     rcx, [rbp+57h+SystemPowerStatus]
0x1800e49cf  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800e49d4  xor     eax, eax
0x1800e49d6  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e49da  mov     dword ptr [rbp+57h+SystemPowerStatus+8], eax
0x1800e49dd  lea     rcx, [rbp+57h+SystemPowerStatus]; lpSystemPowerStatus
0x1800e49e1  call    cs:__imp_GetSystemPowerStatus
0x1800e49e7  test    eax, eax
0x1800e49e9  jz      short loc_1800E4A5B
0x1800e49eb  mov     al, byte ptr [rbp+57h+SystemPowerStatus+1]
0x1800e49ee  cmp     al, 80h
0x1800e49f0  jz      short loc_1800E49F9
0x1800e49f2  cmp     al, 0FFh
0x1800e49f4  mov     r8b, 1
0x1800e49f7  jnz     short loc_1800E49FC
0x1800e49f9  mov     r8b, sil
0x1800e49fc  lea     rax, aBatterypresent; "BatteryPresent"
0x1800e4a03  mov     [rbp+57h+var_B0], rax
0x1800e4a07  mov     [rbp+57h+var_A8], 0Eh
0x1800e4a0f  lea     rdx, [rbp+57h+var_B0]
0x1800e4a13  mov     rcx, rdi
0x1800e4a16  call    ?SetBool@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@_N@Z; ModernDeployment::Autopilot::Core::MachineContext::SetBool(std::basic_string_view<ushort>,bool)
0x1800e4a1b  mov     ebx, eax
0x1800e4a1d  test    eax, eax
0x1800e4a1f  js      loc_1800E485E
0x1800e4a25  mov     al, byte ptr [rbp+57h+SystemPowerStatus]
0x1800e4a28  cmp     al, 0FFh
0x1800e4a2a  jz      short loc_1800E4A5B
0x1800e4a2c  cmp     al, 1
0x1800e4a2e  setz    r8b
0x1800e4a32  lea     rax, aAcpowerconnect; "ACPowerConnected"
0x1800e4a39  mov     [rbp+57h+var_B0], rax
0x1800e4a3d  mov     [rbp+57h+var_A8], 10h
0x1800e4a45  lea     rdx, [rbp+57h+var_B0]
0x1800e4a49  mov     rcx, rdi
0x1800e4a4c  call    ?SetBool@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@_N@Z; ModernDeployment::Autopilot::Core::MachineContext::SetBool(std::basic_string_view<ushort>,bool)
0x1800e4a51  mov     ebx, eax
0x1800e4a53  test    eax, eax
0x1800e4a55  js      loc_1800E485E
0x1800e4a5b  mov     ebx, esi
0x1800e4a5d  lea     rcx, [rbp+57h+var_90]
0x1800e4a61  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4a66  lea     rcx, [rbp+57h+var_70]
0x1800e4a6a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4a6f  lea     rcx, [rbp+57h+var_50]
0x1800e4a73  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e4a78  mov     eax, ebx
0x1800e4a7a  mov     rcx, [rbp+57h+var_30]
0x1800e4a7e  xor     rcx, rsp; StackCookie
0x1800e4a81  call    __security_check_cookie
0x1800e4a86  add     rsp, 0C8h
0x1800e4a8d  pop     rdi
0x1800e4a8e  pop     rsi
0x1800e4a8f  pop     rbx
0x1800e4a90  pop     rbp
0x1800e4a91  retn
```
