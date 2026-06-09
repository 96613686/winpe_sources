# _ModernDeployment::Autopilot::Core::FwtDeviceIdentityCollector::Collect_::_25_::_lambda_1_::operator()

- ea: `0x1800e710c`
- end: `0x1800e744d`
- name: `_ModernDeployment::Autopilot::Core::FwtDeviceIdentityCollector::Collect_::_25_::_lambda_1_::operator()`
- size: `833`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e7780`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180081e80`
- `0x1800e40bc`
- `0x1800e416c`
- `0x1800e710c`
- `0x18019cd1c`
- `0x18019cd64`
- `0x18019cdac`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e72a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e72a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e7282`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e7282`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800e7395`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x1800e7395`

## string_xrefs

- `0x1800e720d`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceidentitycollector.cpp`
- `0x1800e7360`: `onecoreuap\admin\moderndeployment\autopilot\service\fastwindowstelemetry\fwtdeviceidentitycollector.cpp`
- `0x1800e727b`: `powrprof.dll`

## pseudocode

```c
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
0x1800e710c  push    rbp
0x1800e710e  push    rbx
0x1800e710f  push    rsi
0x1800e7110  push    rdi
0x1800e7111  lea     rbp, [rsp-3Fh]
0x1800e7116  sub     rsp, 0C8h
0x1800e711d  mov     rax, cs:__security_cookie
0x1800e7124  xor     rax, rsp
0x1800e7127  mov     [rbp+57h+var_30], rax
0x1800e712b  mov     rdi, rdx
0x1800e712e  xorps   xmm0, xmm0
0x1800e7131  movups  [rbp+57h+var_50], xmm0
0x1800e7135  xor     esi, esi
0x1800e7137  mov     [rbp+57h+var_40], rsi
0x1800e713b  lea     ecx, [rsi+7]
0x1800e713e  mov     [rbp+57h+var_38], rcx
0x1800e7142  mov     word ptr [rbp+57h+var_50], si
0x1800e7146  movups  [rbp+57h+var_70], xmm0
0x1800e714a  mov     [rbp+57h+var_60], rsi
0x1800e714e  mov     [rbp+57h+var_58], rcx
0x1800e7152  mov     word ptr [rbp+57h+var_70], si
0x1800e7156  movups  [rbp+57h+var_90], xmm0
0x1800e715a  mov     [rbp+57h+var_80], rsi
0x1800e715e  mov     [rbp+57h+var_78], rcx
0x1800e7162  mov     word ptr [rbp+57h+var_90], si
0x1800e7166  lea     rcx, [rbp+57h+var_50]
0x1800e716a  call    ?GetSmBiosSystemInfoManufacturer@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoManufacturer(std::wstring &)
0x1800e716f  test    eax, eax
0x1800e7171  js      short loc_1800E71B6
0x1800e7173  mov     rbx, [rbp+57h+var_40]
0x1800e7177  test    rbx, rbx
0x1800e717a  jz      short loc_1800E71B6
0x1800e717c  lea     rcx, [rbp+57h+var_50]
0x1800e7180  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e7185  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e7189  mov     qword ptr [rbp+57h+SystemPowerStatus+8], rbx
0x1800e718d  lea     rax, aMake; "Make"
0x1800e7194  mov     [rbp+57h+var_C0], rax
0x1800e7198  mov     [rbp+57h+var_B8], 4
0x1800e71a0  lea     r8, [rbp+57h+SystemPowerStatus]
0x1800e71a4  lea     rdx, [rbp+57h+var_C0]
0x1800e71a8  mov     rcx, rdi
0x1800e71ab  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e71b0  mov     ebx, eax
0x1800e71b2  test    eax, eax
0x1800e71b4  js      short loc_1800E7206
0x1800e71b6  lea     rcx, [rbp+57h+var_70]
0x1800e71ba  call    ?GetSmBiosSystemInfoModel@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoModel(std::wstring &)
0x1800e71bf  test    eax, eax
0x1800e71c1  js      short loc_1800E7223
0x1800e71c3  mov     rbx, [rbp+57h+var_60]
0x1800e71c7  test    rbx, rbx
0x1800e71ca  jz      short loc_1800E7223
0x1800e71cc  lea     rcx, [rbp+57h+var_70]
0x1800e71d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e71d5  mov     [rbp+57h+var_C0], rax
0x1800e71d9  mov     [rbp+57h+var_B8], rbx
0x1800e71dd  lea     rax, aModel; "Model"
0x1800e71e4  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e71e8  mov     qword ptr [rbp+57h+SystemPowerStatus+8], 5
0x1800e71f0  lea     r8, [rbp+57h+var_C0]
0x1800e71f4  lea     rdx, [rbp+57h+SystemPowerStatus]
0x1800e71f8  mov     rcx, rdi
0x1800e71fb  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e7200  mov     ebx, eax
0x1800e7202  test    eax, eax
0x1800e7204  jns     short loc_1800E7223
0x1800e7206  mov     rcx, [rbp+5Fh]; this
0x1800e720a  mov     r9d, eax; char *
0x1800e720d  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e7214  mov     edx, 9Eh; void *
0x1800e7219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e721e  jmp     loc_1800E7417
0x1800e7223  lea     rcx, [rbp+57h+var_90]
0x1800e7227  call    ?GetSmBiosSystemInfoSerialNumber@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::GetSmBiosSystemInfoSerialNumber(std::wstring &)
0x1800e722c  test    eax, eax
0x1800e722e  js      short loc_1800E7273
0x1800e7230  mov     rbx, [rbp+57h+var_80]
0x1800e7234  test    rbx, rbx
0x1800e7237  jz      short loc_1800E7273
0x1800e7239  lea     rcx, [rbp+57h+var_90]
0x1800e723d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e7242  mov     [rbp+57h+var_C0], rax
0x1800e7246  mov     [rbp+57h+var_B8], rbx
0x1800e724a  lea     rax, aDeviceserialnu; "DeviceSerialNumber"
0x1800e7251  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e7255  mov     qword ptr [rbp+57h+SystemPowerStatus+8], 12h
0x1800e725d  lea     r8, [rbp+57h+var_C0]
0x1800e7261  lea     rdx, [rbp+57h+SystemPowerStatus]
0x1800e7265  mov     rcx, rdi
0x1800e7268  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e726d  mov     ebx, eax
0x1800e726f  test    eax, eax
0x1800e7271  js      short loc_1800E7206
0x1800e7273  xor     edx, edx; hFile
0x1800e7275  mov     r8d, 800h; dwFlags
0x1800e727b  lea     rcx, LibFileName; "powrprof.dll"
0x1800e7282  call    cs:__imp_LoadLibraryExW
0x1800e7289  nop     dword ptr [rax+rax+00h]
0x1800e728e  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e7292  test    rax, rax
0x1800e7295  jz      loc_1800E737F
0x1800e729b  lea     rdx, aPowerdetermine; "PowerDeterminePlatformRoleEx"
0x1800e72a2  mov     rcx, rax; hModule
0x1800e72a5  call    cs:__imp_GetProcAddress
0x1800e72ac  nop     dword ptr [rax+rax+00h]
0x1800e72b1  test    rax, rax
0x1800e72b4  jz      loc_1800E737F
0x1800e72ba  mov     ecx, 2
0x1800e72bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e72c4  sub     eax, 1
0x1800e72c7  jz      short loc_1800E7314
0x1800e72c9  sub     eax, 1
0x1800e72cc  jz      short loc_1800E730B
0x1800e72ce  sub     eax, 1
0x1800e72d1  jz      short loc_1800E7302
0x1800e72d3  sub     eax, 1
0x1800e72d6  jz      short loc_1800E72F9
0x1800e72d8  sub     eax, 1
0x1800e72db  jz      short loc_1800E72F9
0x1800e72dd  sub     eax, 2
0x1800e72e0  jz      short loc_1800E72F9
0x1800e72e2  cmp     eax, 1
0x1800e72e5  jz      short loc_1800E72F0
0x1800e72e7  lea     rax, ?ChassisTypeUnknown@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Unknown"
0x1800e72ee  jmp     short loc_1800E731B
0x1800e72f0  lea     rax, ?ChassisTypeTablet@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Tablet"
0x1800e72f7  jmp     short loc_1800E731B
0x1800e72f9  lea     rax, ?ChassisTypeServer@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Server"
0x1800e7300  jmp     short loc_1800E731B
0x1800e7302  lea     rax, ?ChassisTypeWorkstation@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Workstation"
0x1800e7309  jmp     short loc_1800E731B
0x1800e730b  lea     rax, ?ChassisTypeLaptop@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Laptop"
0x1800e7312  jmp     short loc_1800E731B
0x1800e7314  lea     rax, ?ChassisTypeDesktop@FwtTelemetryValueStrings@Core@Autopilot@ModernDeployment@@3QBGB; "Desktop"
0x1800e731b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800e731f  inc     rcx
0x1800e7322  cmp     [rax+rcx*2], si
0x1800e7326  jnz     short loc_1800E731F
0x1800e7328  mov     [rbp+57h+var_C0], rax
0x1800e732c  mov     [rbp+57h+var_B8], rcx
0x1800e7330  lea     rax, aChassistype; "ChassisType"
0x1800e7337  mov     [rbp+57h+var_B0], rax
0x1800e733b  mov     [rbp+57h+var_A8], 0Bh
0x1800e7343  lea     r8, [rbp+57h+var_C0]
0x1800e7347  lea     rdx, [rbp+57h+var_B0]
0x1800e734b  mov     rcx, rdi
0x1800e734e  call    ?SetString@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; ModernDeployment::Autopilot::Core::MachineContext::SetString(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x1800e7353  mov     ebx, eax
0x1800e7355  test    eax, eax
0x1800e7357  jns     short loc_1800E737F
0x1800e7359  mov     rcx, [rbp+5Fh]; this
0x1800e735d  mov     r9d, eax; char *
0x1800e7360  lea     r8, aOnecoreuapAdmi_19; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800e7367  mov     edx, 9Eh; void *
0x1800e736c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7371  lea     rcx, [rbp+57h+SystemPowerStatus]
0x1800e7375  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800e737a  jmp     loc_1800E7417
0x1800e737f  lea     rcx, [rbp+57h+SystemPowerStatus]
0x1800e7383  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1800e7388  xor     eax, eax
0x1800e738a  mov     qword ptr [rbp+57h+SystemPowerStatus], rax
0x1800e738e  mov     dword ptr [rbp+57h+SystemPowerStatus+8], eax
0x1800e7391  lea     rcx, [rbp+57h+SystemPowerStatus]; lpSystemPowerStatus
0x1800e7395  call    cs:__imp_GetSystemPowerStatus
0x1800e739c  nop     dword ptr [rax+rax+00h]
0x1800e73a1  test    eax, eax
0x1800e73a3  jz      short loc_1800E7415
0x1800e73a5  mov     al, byte ptr [rbp+57h+SystemPowerStatus+1]
0x1800e73a8  cmp     al, 80h
0x1800e73aa  jz      short loc_1800E73B3
0x1800e73ac  cmp     al, 0FFh
0x1800e73ae  mov     r8b, 1
0x1800e73b1  jnz     short loc_1800E73B6
0x1800e73b3  mov     r8b, sil
0x1800e73b6  lea     rax, aBatterypresent; "BatteryPresent"
0x1800e73bd  mov     [rbp+57h+var_B0], rax
0x1800e73c1  mov     [rbp+57h+var_A8], 0Eh
0x1800e73c9  lea     rdx, [rbp+57h+var_B0]
0x1800e73cd  mov     rcx, rdi
0x1800e73d0  call    ?SetBool@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@_N@Z; ModernDeployment::Autopilot::Core::MachineContext::SetBool(std::basic_string_view<ushort>,bool)
0x1800e73d5  mov     ebx, eax
0x1800e73d7  test    eax, eax
0x1800e73d9  js      loc_1800E7206
0x1800e73df  mov     al, byte ptr [rbp+57h+SystemPowerStatus]
0x1800e73e2  cmp     al, 0FFh
0x1800e73e4  jz      short loc_1800E7415
0x1800e73e6  cmp     al, 1
0x1800e73e8  setz    r8b
0x1800e73ec  lea     rax, aAcpowerconnect; "ACPowerConnected"
0x1800e73f3  mov     [rbp+57h+var_B0], rax
0x1800e73f7  mov     [rbp+57h+var_A8], 10h
0x1800e73ff  lea     rdx, [rbp+57h+var_B0]
0x1800e7403  mov     rcx, rdi
0x1800e7406  call    ?SetBool@MachineContext@Core@Autopilot@ModernDeployment@@QEAAJV?$basic_string_view@GU?$char_traits@G@std@@@std@@_N@Z; ModernDeployment::Autopilot::Core::MachineContext::SetBool(std::basic_string_view<ushort>,bool)
0x1800e740b  mov     ebx, eax
0x1800e740d  test    eax, eax
0x1800e740f  js      loc_1800E7206
0x1800e7415  mov     ebx, esi
0x1800e7417  lea     rcx, [rbp+57h+var_90]
0x1800e741b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e7420  lea     rcx, [rbp+57h+var_70]
0x1800e7424  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e7429  lea     rcx, [rbp+57h+var_50]
0x1800e742d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e7432  mov     eax, ebx
0x1800e7434  mov     rcx, [rbp+57h+var_30]
0x1800e7438  xor     rcx, rsp; StackCookie
0x1800e743b  call    __security_check_cookie
0x1800e7440  add     rsp, 0C8h
0x1800e7447  pop     rdi
0x1800e7448  pop     rsi
0x1800e7449  pop     rbx
0x1800e744a  pop     rbp
0x1800e744b  retn
```
