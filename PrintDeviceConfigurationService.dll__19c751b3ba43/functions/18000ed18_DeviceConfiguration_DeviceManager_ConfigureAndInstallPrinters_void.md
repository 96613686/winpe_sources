# DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters(void)

- ea: `0x18000ed18`
- end: `0x18000f0ee`
- name: `?ConfigureAndInstallPrinters@DeviceManager@DeviceConfiguration@@QEAAJXZ`
- size: `982`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000de10`

## callees

- `0x1800020c0`
- `0x180004e44`
- `0x180004e64`
- `0x18000ac9c`
- `0x18000ae04`
- `0x18000aeac`
- `0x18000afcc`
- `0x18000b838`
- `0x18000c06c`
- `0x18000dcfc`
- `0x18000e83c`
- `0x18000ece4`
- `0x18000ed18`
- `0x18000f510`
- `0x18000f9b4`
- `0x18000fa2c`
- `0x18000fad4`
- `0x18000fbe0`
- `0x180010ca4`
- `0x180011550`
- `0x1800115a0`
- `0x180014658`
- `0x18001467c`
- `0x1800146a0`
- `0x180014a70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed5b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ed5b`

## string_xrefs

- `0x18000ee10`: `Updating the install state of device %ws to Installing`
- `0x18000ee17`: `DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters`
- `0x18000ee4d`: `DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters`
- `0x18000ee7a`: `DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters`
- `0x18000ef28`: `DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters`
- `0x18000f075`: `DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters`
- `0x18000f099`: `DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters`
- `0x18000ee46`: `SetDeviceInstallationState (Installing) failed with hr: 0x%x`
- `0x18000eede`: `printscan\print\spooler\configuration\deviceconfigurationservice\lib\devicemanager.cpp`
- `0x18000ef21`: `Starting installation for device %ws (device type: %ws)`
- `0x18000f06e`: `_InstallDevice failed with hr: 0x%x`
- `0x18000f092`: `_ConfigureDevice failed with hr: 0x%x`
- `0x18000ee73`: `No devices were discovered that needed to be configured!`

## pseudocode

```c
__int64 __fastcall DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rsi
  struct _GUID ***v2; // rdi
  struct _GUID **v3; // rbx
  struct _GUID **v4; // r14
  unsigned int v5; // edi
  struct _GUID **i; // rsi
  _QWORD *DeviceId; // rax
  int v8; // eax
  char v9; // al
  __int64 v10; // rdi
  __int64 v11; // r8
  _QWORD *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rax
  int v17; // esi
  struct _GUID v18; // xmm6
  __int64 v19; // rax
  const unsigned __int16 *v20; // r13
  __int64 v21; // r8
  __int64 PortName; // rax
  __int64 PrinterName; // rax
  unsigned __int64 v24; // rdx
  unsigned __int8 v25; // cl
  const unsigned __int16 *v26; // r12
  __int64 v27; // rcx
  DeviceConfigurationTelemetry *v28; // rcx
  const char *v30; // [rsp+30h] [rbp-148h]
  unsigned __int16 *v32; // [rsp+48h] [rbp-130h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-128h]
  struct _GUID **v34; // [rsp+58h] [rbp-120h] BYREF
  struct _GUID **v35; // [rsp+60h] [rbp-118h]
  struct _GUID **v36; // [rsp+68h] [rbp-110h]
  char v37[8]; // [rsp+70h] [rbp-108h] BYREF
  char v38[16]; // [rsp+78h] [rbp-100h] BYREF
  char v39[24]; // [rsp+88h] [rbp-F0h] BYREF
  struct _GUID v40; // [rsp+A0h] [rbp-D8h] BYREF
  _BYTE v41[32]; // [rsp+C0h] [rbp-B8h] BYREF
  _BYTE v42[32]; // [rsp+E0h] [rbp-98h] BYREF
  _BYTE v43[32]; // [rsp+100h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v1 = this;
  std::vector<std::shared_ptr<DeviceConfiguration::Device>>::vector<std::shared_ptr<DeviceConfiguration::Device>>(&v34);
  AcquireSRWLockExclusive(v1 + 1);
  v32 = (unsigned __int16 *)&v1[1];
  v2 = (struct _GUID ***)DeviceConfiguration::DeviceManager::_DiscoverDevices(v1, &v40);
  if ( &v34 == v2 )
  {
    v4 = v35;
    v3 = v34;
  }
  else
  {
    std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Tidy(&v34);
    v3 = *v2;
    v34 = *v2;
    v4 = v2[1];
    v35 = v4;
    v36 = v2[2];
    *v2 = 0;
    v2[1] = 0;
    v2[2] = 0;
  }
  v5 = 0;
  std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Tidy(&v40);
  if ( v3 != v4 )
  {
    for ( i = v3; i != v4; i += 2 )
    {
      if ( !*(_DWORD *)&(*i)[15].Data4[4] )
      {
        DeviceId = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(*i, &v40);
        if ( DeviceId[3] > 7u )
          DeviceId = (_QWORD *)*DeviceId;
        DeviceConfigurationTelemetry::WriteDbgTraceInfo(
          "DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters",
          L"Updating the install state of device %ws to Installing",
          DeviceId);
        std::wstring::_Tidy_deallocate(&v40);
        v8 = DeviceConfiguration::Device::SetDeviceInstallationState(*i, 1);
        v5 = v8;
        if ( v8 < 0 )
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters",
            L"SetDeviceInstallationState (Installing) failed with hr: 0x%x",
            (unsigned int)v8);
      }
    }
    v1 = this;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v32);
  if ( v3 == v4 )
  {
    DeviceConfigurationTelemetry::WriteDbgTraceError(
      "DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters",
      L"No devices were discovered that needed to be configured!");
    v5 = -2147023728;
  }
  else
  {
    DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(g_printDeviceConfigurationService);
    DeviceConfiguration::PrintDeviceConfigurationService::AcquireSpoolerLock(g_printDeviceConfigurationService, v37);
    while ( v3 != v4 )
    {
      v9 = std::_Atomic_storage<bool,1>::load(&v1[2]);
      wil::details::in1diag3::Throw_Win32IfMsg(
        retaddr,
        (void *)0x57,
        (unsigned int)"printscan\\print\\spooler\\configuration\\deviceconfigurationservice\\lib\\devicemanager.cpp",
        (const char *)0x45B,
        v9,
        (bool)"Shutdown in progress!",
        v30);
      v10 = DeviceConfiguration::StringifyDeviceType(*(unsigned int *)&(*v3)[15].Data2);
      v12 = (_QWORD *)DeviceConfiguration::Device::GetDeviceId(v11, v41);
      if ( v12[3] > 7u )
        v12 = (_QWORD *)*v12;
      DeviceConfigurationTelemetry::WriteDbgTraceInfo(
        "DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters",
        L"Starting installation for device %ws (device type: %ws)",
        v12,
        v10);
      std::wstring::_Tidy_deallocate(v41);
      v13 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(v38, v3);
      v15 = DeviceConfiguration::DeviceManager::_ConfigureDevice(v14, v13);
      v5 = v15;
      if ( v15 < 0 )
      {
        DeviceConfigurationTelemetry::WriteDbgTraceError(
          "DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters",
          L"_ConfigureDevice failed with hr: 0x%x",
          (unsigned int)v15);
      }
      else
      {
        v16 = std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(
                v39,
                v3);
        v17 = DeviceConfiguration::DeviceManager::_InstallDevice(v1, v16);
        v18 = (*v3)[14];
        v19 = DeviceConfiguration::Device::GetDeviceId(*v3, v43);
        v20 = (const unsigned __int16 *)v19;
        if ( *(_QWORD *)(v19 + 24) > 7u )
          v20 = *(const unsigned __int16 **)v19;
        v33 = (unsigned __int16 *)DeviceConfiguration::StringifyDeviceType(*(unsigned int *)&(*v3)[15].Data2);
        PortName = DeviceConfiguration::Device::GetPortName(v21, v42);
        v32 = (unsigned __int16 *)PortName;
        if ( *(_QWORD *)(PortName + 24) > 7u )
          v32 = *(unsigned __int16 **)PortName;
        PrinterName = DeviceConfiguration::Device::GetPrinterName(*v3, v41);
        v26 = (const unsigned __int16 *)PrinterName;
        v5 = v17;
        if ( *(_QWORD *)(PrinterName + 24) > 7u )
          v26 = *(const unsigned __int16 **)PrinterName;
        if ( DeviceConfigurationTelemetry::IsEnabled(v25, v24) )
        {
          wil::details::static_lazy<DeviceConfigurationTelemetry>::get(
            v27,
            _lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_);
          v40 = v18;
          DeviceConfigurationTelemetry::PnpDevice_(v28, v26, v32, v33, v20, &v40, v17);
        }
        std::wstring::_Tidy_deallocate(v41);
        std::wstring::_Tidy_deallocate(v42);
        std::wstring::_Tidy_deallocate(v43);
        if ( v17 < 0 )
          DeviceConfigurationTelemetry::WriteDbgTraceError(
            "DeviceConfiguration::DeviceManager::ConfigureAndInstallPrinters",
            L"_InstallDevice failed with hr: 0x%x",
            (unsigned int)v17);
        v1 = this;
      }
      v3 += 2;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v37);
  }
  std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Tidy(&v34);
  return v5;
}

```

## disassembly

```asm
0x18000ed18  mov     rax, rsp
0x18000ed1b  push    rbx
0x18000ed1c  push    rsi
0x18000ed1d  push    rdi
0x18000ed1e  push    r12
0x18000ed20  push    r13
0x18000ed22  push    r14
0x18000ed24  sub     rsp, 148h
0x18000ed2b  movaps  xmmword ptr [rax-48h], xmm6
0x18000ed2f  mov     rax, cs:__security_cookie
0x18000ed36  xor     rax, rsp
0x18000ed39  mov     [rsp+178h+var_58], rax
0x18000ed41  mov     rsi, rcx
0x18000ed44  mov     [rsp+178h+var_138], rcx
0x18000ed49  lea     rcx, [rsp+178h+var_120]
0x18000ed4e  call    ??0?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DeviceConfiguration::Device>>::vector<std::shared_ptr<DeviceConfiguration::Device>>(void)
0x18000ed53  nop
0x18000ed54  lea     rbx, [rsi+8]
0x18000ed58  mov     rcx, rbx; SRWLock
0x18000ed5b  call    cs:__imp_AcquireSRWLockExclusive
0x18000ed61  mov     [rsp+178h+var_130], rbx
0x18000ed66  lea     rdx, [rsp+178h+var_D8]
0x18000ed6e  mov     rcx, rsi
0x18000ed71  call    ?_DiscoverDevices@DeviceManager@DeviceConfiguration@@AEAA?AV?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@XZ; DeviceConfiguration::DeviceManager::_DiscoverDevices(void)
0x18000ed76  mov     rdi, rax
0x18000ed79  lea     rax, [rsp+178h+var_120]
0x18000ed7e  cmp     rax, rdi
0x18000ed81  jz      short loc_18000EDC0
0x18000ed83  lea     rcx, [rsp+178h+var_120]
0x18000ed88  call    ?_Tidy@?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Tidy(void)
0x18000ed8d  mov     rbx, [rdi]
0x18000ed90  mov     [rsp+178h+var_120], rbx
0x18000ed95  mov     r14, [rdi+8]
0x18000ed99  mov     [rsp+178h+var_118], r14
0x18000ed9e  mov     rax, [rdi+10h]
0x18000eda2  mov     [rsp+178h+var_110], rax
0x18000eda7  mov     qword ptr [rdi], 0
0x18000edae  mov     qword ptr [rdi+8], 0
0x18000edb6  mov     qword ptr [rdi+10h], 0
0x18000edbe  jmp     short loc_18000EDCA
0x18000edc0  mov     r14, [rsp+178h+var_118]
0x18000edc5  mov     rbx, [rsp+178h+var_120]
0x18000edca  xor     edi, edi
0x18000edcc  lea     rcx, [rsp+178h+var_D8]
0x18000edd4  call    ?_Tidy@?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Tidy(void)
0x18000edd9  cmp     rbx, r14
0x18000eddc  jz      loc_18000EE64
0x18000ede2  mov     rsi, rbx
0x18000ede5  cmp     rsi, r14
0x18000ede8  jz      short loc_18000EE5F
0x18000edea  mov     rcx, [rsi]
0x18000eded  cmp     dword ptr [rcx+0FCh], 0
0x18000edf4  jnz     short loc_18000EE59
0x18000edf6  lea     rdx, [rsp+178h+var_D8]
0x18000edfe  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x18000ee03  cmp     qword ptr [rax+18h], 7
0x18000ee08  jbe     short loc_18000EE0D
0x18000ee0a  mov     rax, [rax]
0x18000ee0d  mov     r8, rax
0x18000ee10  lea     rdx, aUpdatingTheIns; "Updating the install state of device %w"...
0x18000ee17  lea     rcx, aDeviceconfigur_3; "DeviceConfiguration::DeviceManager::Con"...
0x18000ee1e  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000ee23  lea     rcx, [rsp+178h+var_D8]
0x18000ee2b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ee30  mov     edx, 1
0x18000ee35  mov     rcx, [rsi]
0x18000ee38  call    ?SetDeviceInstallationState@Device@DeviceConfiguration@@QEAAJW4DeviceInstallState@2@@Z; DeviceConfiguration::Device::SetDeviceInstallationState(DeviceConfiguration::DeviceInstallState)
0x18000ee3d  mov     edi, eax
0x18000ee3f  test    eax, eax
0x18000ee41  jns     short loc_18000EE59
0x18000ee43  mov     r8d, eax
0x18000ee46  lea     rdx, aSetdeviceinsta; "SetDeviceInstallationState (Installing)"...
0x18000ee4d  lea     rcx, aDeviceconfigur_3; "DeviceConfiguration::DeviceManager::Con"...
0x18000ee54  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000ee59  add     rsi, 10h
0x18000ee5d  jmp     short loc_18000EDE5
0x18000ee5f  mov     rsi, [rsp+178h+var_138]
0x18000ee64  lea     rcx, [rsp+178h+var_130]
0x18000ee69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ee6e  cmp     rbx, r14
0x18000ee71  jnz     short loc_18000EE90
0x18000ee73  lea     rdx, aNoDevicesWereD; "No devices were discovered that needed "...
0x18000ee7a  lea     rcx, aDeviceconfigur_3; "DeviceConfiguration::DeviceManager::Con"...
0x18000ee81  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000ee86  mov     edi, 80070490h
0x18000ee8b  jmp     loc_18000F0B2
0x18000ee90  mov     rcx, cs:?g_printDeviceConfigurationService@@3V?$unique_ptr@VPrintDeviceConfigurationService@DeviceConfiguration@@U?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@@std@@A; this
0x18000ee97  call    ?ResetStopTimer@PrintDeviceConfigurationService@DeviceConfiguration@@QEAAXXZ; DeviceConfiguration::PrintDeviceConfigurationService::ResetStopTimer(void)
0x18000ee9c  lea     rdx, [rsp+178h+var_108]
0x18000eea1  mov     rcx, cs:?g_printDeviceConfigurationService@@3V?$unique_ptr@VPrintDeviceConfigurationService@DeviceConfiguration@@U?$default_delete@VPrintDeviceConfigurationService@DeviceConfiguration@@@std@@@std@@A; std::unique_ptr<DeviceConfiguration::PrintDeviceConfigurationService> g_printDeviceConfigurationService
0x18000eea8  call    ?AcquireSpoolerLock@PrintDeviceConfigurationService@DeviceConfiguration@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; DeviceConfiguration::PrintDeviceConfigurationService::AcquireSpoolerLock(void)
0x18000eead  nop
0x18000eeae  cmp     rbx, r14
0x18000eeb1  jz      loc_18000F0A7
0x18000eeb7  lea     rcx, [rsi+10h]
0x18000eebb  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x18000eec0  mov     rcx, [rsp+178h]; this
0x18000eec8  lea     rdx, aShutdownInProg; "Shutdown in progress!"
0x18000eecf  mov     [rsp+178h+var_150], rdx; bool
0x18000eed4  mov     byte ptr [rsp+178h+var_158], al; char
0x18000eed8  mov     r9d, 45Bh; char *
0x18000eede  lea     r8, aPrintscanPrint_1; "printscan\\print\\spooler\\configuratio"...
0x18000eee5  mov     edx, 57h ; 'W'; void *
0x18000eeea  call    ?Throw_Win32IfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDK_N1ZZ; wil::details::in1diag3::Throw_Win32IfMsg(void *,uint,char const *,ulong,bool,char const *,...)
0x18000eeef  mov     r8, [rbx]
0x18000eef2  mov     ecx, [r8+0F4h]
0x18000eef9  call    ?StringifyDeviceType@DeviceConfiguration@@YAPEBGW4DeviceType@1@@Z; DeviceConfiguration::StringifyDeviceType(DeviceConfiguration::DeviceType)
0x18000eefe  mov     rdi, rax
0x18000ef01  lea     rdx, [rsp+178h+var_B8]
0x18000ef09  mov     rcx, r8
0x18000ef0c  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x18000ef11  cmp     qword ptr [rax+18h], 7
0x18000ef16  jbe     short loc_18000EF1B
0x18000ef18  mov     rax, [rax]
0x18000ef1b  mov     r9, rdi
0x18000ef1e  mov     r8, rax
0x18000ef21  lea     rdx, aStartingInstal; "Starting installation for device %ws (d"...
0x18000ef28  lea     rcx, aDeviceconfigur_3; "DeviceConfiguration::DeviceManager::Con"...
0x18000ef2f  call    ?WriteDbgTraceInfo@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000ef34  lea     rcx, [rsp+178h+var_B8]
0x18000ef3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000ef41  mov     rdx, rbx
0x18000ef44  lea     rcx, [rsp+178h+var_100]
0x18000ef49  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x18000ef4e  mov     rdx, rax
0x18000ef51  call    ?_ConfigureDevice@DeviceManager@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z; DeviceConfiguration::DeviceManager::_ConfigureDevice(std::shared_ptr<DeviceConfiguration::Device>)
0x18000ef56  mov     edi, eax
0x18000ef58  test    eax, eax
0x18000ef5a  js      loc_18000F08F
0x18000ef60  mov     rdx, rbx
0x18000ef63  lea     rcx, [rsp+178h+var_F0]
0x18000ef6b  call    ??0?$shared_ptr@VDeviceManager@DeviceConfiguration@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<DeviceConfiguration::DeviceManager>::shared_ptr<DeviceConfiguration::DeviceManager>(std::shared_ptr<DeviceConfiguration::DeviceManager> const &)
0x18000ef70  mov     rdx, rax
0x18000ef73  mov     rcx, rsi
0x18000ef76  call    ?_InstallDevice@DeviceManager@DeviceConfiguration@@AEAAJV?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@Z; DeviceConfiguration::DeviceManager::_InstallDevice(std::shared_ptr<DeviceConfiguration::Device>)
0x18000ef7b  mov     esi, eax
0x18000ef7d  mov     rcx, [rbx]
0x18000ef80  movups  xmm6, xmmword ptr [rcx+0E0h]
0x18000ef87  lea     rdx, [rsp+178h+var_78]
0x18000ef8f  call    ?GetDeviceId@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetDeviceId(void)
0x18000ef94  mov     r13, rax
0x18000ef97  cmp     qword ptr [rax+18h], 7
0x18000ef9c  jbe     short loc_18000EFA1
0x18000ef9e  mov     r13, [rax]
0x18000efa1  mov     r8, [rbx]
0x18000efa4  mov     ecx, [r8+0F4h]
0x18000efab  call    ?StringifyDeviceType@DeviceConfiguration@@YAPEBGW4DeviceType@1@@Z; DeviceConfiguration::StringifyDeviceType(DeviceConfiguration::DeviceType)
0x18000efb0  mov     [rsp+178h+var_128], rax
0x18000efb5  lea     rdx, [rsp+178h+var_98]
0x18000efbd  mov     rcx, r8
0x18000efc0  call    ?GetPortName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPortName(void)
0x18000efc5  mov     [rsp+178h+var_130], rax
0x18000efca  cmp     qword ptr [rax+18h], 7
0x18000efcf  jbe     short loc_18000EFD9
0x18000efd1  mov     rax, [rax]
0x18000efd4  mov     [rsp+178h+var_130], rax
0x18000efd9  lea     rdx, [rsp+178h+var_B8]
0x18000efe1  mov     rcx, [rbx]
0x18000efe4  call    ?GetPrinterName@Device@DeviceConfiguration@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; DeviceConfiguration::Device::GetPrinterName(void)
0x18000efe9  mov     r12, rax
0x18000efec  mov     edi, esi
0x18000efee  cmp     qword ptr [rax+18h], 7
0x18000eff3  jbe     short loc_18000EFF8
0x18000eff5  mov     r12, [rax]
0x18000eff8  call    ?IsEnabled@DeviceConfigurationTelemetry@@SA_NE_K@Z; DeviceConfigurationTelemetry::IsEnabled(uchar,unsigned __int64)
0x18000effd  test    al, al
0x18000efff  jz      short loc_18000F03E
0x18000f001  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_0266e7cb468ca894dc8f9195a1f762c1_@@CA@XZ; _lambda_0266e7cb468ca894dc8f9195a1f762c1_::_lambda_invoker_cdecl_(void)
0x18000f008  call    ?get@?$static_lazy@VDeviceConfigurationTelemetry@@@details@wil@@QEAAPEAVDeviceConfigurationTelemetry@@P6AXXZ@Z; wil::details::static_lazy<DeviceConfigurationTelemetry>::get(void (*)(void))
0x18000f00d  movdqa  xmmword ptr [rsp+178h+var_D8.Data1], xmm6
0x18000f016  mov     [rsp+178h+var_148], esi; int
0x18000f01a  lea     rax, [rsp+178h+var_D8]
0x18000f022  mov     [rsp+178h+var_150], rax; struct _GUID *
0x18000f027  mov     [rsp+178h+var_158], r13; unsigned __int16 *
0x18000f02c  mov     r9, [rsp+178h+var_128]; unsigned __int16 *
0x18000f031  mov     r8, [rsp+178h+var_130]; unsigned __int16 *
0x18000f036  mov     rdx, r12; unsigned __int16 *
0x18000f039  call    ?PnpDevice_@DeviceConfigurationTelemetry@@QEAAXPEBG000U_GUID@@J@Z; DeviceConfigurationTelemetry::PnpDevice_(ushort const *,ushort const *,ushort const *,ushort const *,_GUID,long)
0x18000f03e  lea     rcx, [rsp+178h+var_B8]
0x18000f046  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f04b  nop
0x18000f04c  lea     rcx, [rsp+178h+var_98]
0x18000f054  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f059  nop
0x18000f05a  lea     rcx, [rsp+178h+var_78]
0x18000f062  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000f067  test    esi, esi
0x18000f069  jns     short loc_18000F081
0x18000f06b  mov     r8d, esi
0x18000f06e  lea     rdx, aInstalldeviceF; "_InstallDevice failed with hr: 0x%x"
0x18000f075  lea     rcx, aDeviceconfigur_3; "DeviceConfiguration::DeviceManager::Con"...
0x18000f07c  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000f081  mov     rsi, [rsp+178h+var_138]
0x18000f086  add     rbx, 10h
0x18000f08a  jmp     loc_18000EEAE
0x18000f08f  mov     r8d, eax
0x18000f092  lea     rdx, aConfiguredevic; "_ConfigureDevice failed with hr: 0x%x"
0x18000f099  lea     rcx, aDeviceconfigur_3; "DeviceConfiguration::DeviceManager::Con"...
0x18000f0a0  call    ?WriteDbgTraceError@DeviceConfigurationTelemetry@@SAXPEADPEAGZZ; DeviceConfigurationTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000f0a5  jmp     short loc_18000F086
0x18000f0a7  lea     rcx, [rsp+178h+var_108]
0x18000f0ac  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000f0b1  nop
0x18000f0b2  lea     rcx, [rsp+178h+var_120]
0x18000f0b7  call    ?_Tidy@?$vector@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@V?$allocator@V?$shared_ptr@VDevice@DeviceConfiguration@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DeviceConfiguration::Device>>::_Tidy(void)
0x18000f0bc  mov     eax, edi
0x18000f0be  jmp     short loc_18000F0C4
0x18000f0c0  mov     eax, dword ptr [rsp+178h+var_138]
0x18000f0c4  mov     rcx, [rsp+178h+var_58]
0x18000f0cc  xor     rcx, rsp; StackCookie
0x18000f0cf  call    __security_check_cookie
0x18000f0d4  movaps  xmm6, [rsp+178h+var_48]
0x18000f0dc  add     rsp, 148h
0x18000f0e3  pop     r14
0x18000f0e5  pop     r13
0x18000f0e7  pop     r12
0x18000f0e9  pop     rdi
0x18000f0ea  pop     rsi
0x18000f0eb  pop     rbx
0x18000f0ec  retn
```
