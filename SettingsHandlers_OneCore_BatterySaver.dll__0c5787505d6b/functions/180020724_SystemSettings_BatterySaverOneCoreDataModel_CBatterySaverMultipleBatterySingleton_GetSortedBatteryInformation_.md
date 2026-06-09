# SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::GetSortedBatteryInformation(void)

- ea: `0x180020724`
- end: `0x180020c49`
- name: `?GetSortedBatteryInformation@CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJXZ`
- size: `1317`
- prototype: `__int64 __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800255d0`

## callees

- `0x180009190`
- `0x18000967c`
- `0x18000cfa4`
- `0x18000eacc`
- `0x180015208`
- `0x180015d30`
- `0x180017e18`
- `0x180017f1c`
- `0x18001b030`
- `0x18001d0f8`
- `0x18001e6c0`
- `0x180020724`
- `0x180029a40`
- `0x18004c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180020b52`
- `api-ms-win-crt-private-l1-1-0!_o_qsort` at `0x180020b52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020acb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020aba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020adf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020b2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020aba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020adf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180020b2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800209a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800209a6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ac3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020ac3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002083e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020936`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002083e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180020936`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180020b1b`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180020b1b`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800207c6`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1800207c6`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180020832`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180020874`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180020832`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180020874`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180020808`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180020808`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::GetSortedBatteryInformation(
        SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *this)
{
  __int64 v2; // r12
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  HDEVINFO ClassDevsW; // rsi
  unsigned int v7; // r15d
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v8; // rax
  wchar_t *v9; // r13
  char *v10; // rax
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rax
  size_t *v13; // r8
  wchar_t *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING, __int64 *); // rbx
  __int64 *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 (__fastcall *v21)(__int64, __int64); // rdi
  SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *v22; // rcx
  const struct _DEVPROPKEY *v23; // r9
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // r15d
  __int64 v27; // rsi
  __int64 v28; // rdi
  void (__fastcall *v29)(__int64, __int64, char *); // rbx
  __int64 v30; // rax
  char *v31; // r8
  __int64 v32; // rsi
  int DeviceInterfaceData; // [rsp+20h] [rbp-99h]
  DWORD RequiredSize; // [rsp+30h] [rbp-89h] BYREF
  __int64 v36; // [rsp+38h] [rbp-81h] BYREF
  __int64 v37; // [rsp+40h] [rbp-79h] BYREF
  __int64 v38; // [rsp+48h] [rbp-71h] BYREF
  HSTRING string; // [rsp+50h] [rbp-69h] BYREF
  __int64 v40; // [rsp+58h] [rbp-61h] BYREF
  __int64 v41; // [rsp+60h] [rbp-59h] BYREF
  __int64 (__fastcall *v42)(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *__hidden, struct Windows::Devices::Power::IBattery *, struct IInspectable *); // [rsp+68h] [rbp-51h] BYREF
  volatile signed __int32 *v43; // [rsp+70h] [rbp-49h]
  SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *v44; // [rsp+78h] [rbp-41h] BYREF
  __int64 v45; // [rsp+80h] [rbp-39h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA v46; // [rsp+88h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v48; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v2 = 0;
  v38 = 0;
  v41 = 0;
  v45 = 0;
  v36 = 0;
  *((_DWORD *)this + 58) = 0;
  RequiredSize = 0;
  memset(&v46, 0, sizeof(v46));
  v48 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Power.Battery",
    0x1Eu,
    0x1Du);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>(
         v48,
         (__int64)&v38);
  v4 = v3;
  if ( v3 >= 0 )
  {
    ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVICE_BATTERY, 0, 0, 0x12u);
    if ( ClassDevsW == (HDEVINFO)-1LL )
    {
      OutputDebugStringW(L"Error: SetupDiGetClassDevs on GUID_DEVICE_BATTERY, failed \n");
    }
    else
    {
      v7 = 0;
      v46.cbSize = 32;
      while ( v7 < 8 )
      {
        if ( SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVICE_BATTERY, v7, &v46) )
        {
          SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &v46, 0, 0, &RequiredSize, 0);
          v8 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)LocalAlloc(0, RequiredSize);
          v9 = (wchar_t *)v8;
          if ( v8 )
          {
            v8->cbSize = 8;
            if ( SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &v46, v8, RequiredSize, &RequiredSize, 0) )
            {
              v10 = (char *)operator new(0x38u);
              v44 = (SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *)v10;
              *(_OWORD *)v10 = 0;
              *((_DWORD *)v10 + 2) = 1;
              *((_DWORD *)v10 + 3) = 1;
              *(_QWORD *)v10 = &std::_Ref_count_obj2<SystemSettings::BatterySaverOneCoreDataModel::IndividualBattery>::`vftable';
              *((_QWORD *)v10 + 5) = 0;
              *((_QWORD *)v10 + 6) = 0;
              v42 = (__int64 (__fastcall *)(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton *__hidden, struct Windows::Devices::Power::IBattery *, struct IInspectable *))(v10 + 16);
              v43 = (volatile signed __int32 *)v10;
              std::shared_ptr<SystemSettings::BatterySaverOneCoreDataModel::IndividualBattery>::operator=(
                (char *)this + 16 * *((unsigned int *)this + 58) + 240,
                &v42);
              v11 = v43;
              if ( v43 )
              {
                if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
                  if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
                }
              }
              v12 = -1;
              do
                ++v12;
              while ( v9[v12 + 2] );
              RequiredSize = 2 * v12 + 2;
              *(_QWORD *)(*((_QWORD *)this + 2 * *((unsigned int *)this + 58) + 30) + 8LL) = LocalAlloc(0, RequiredSize);
              v14 = *(wchar_t **)(*((_QWORD *)this + 2 * *((unsigned int *)this + 58) + 30) + 8LL);
              if ( v14 )
              {
                if ( (unsigned __int64)RequiredSize >> 1 )
                  StringCopyWorkerW_0(v14, (unsigned __int64)RequiredSize >> 1, v13, v9 + 2, 0x7FFFFFFEu);
                string = 0;
                v15 = -1;
                do
                  ++v15;
                while ( v9[v15 + 2] );
                v3 = WindowsCreateString(v9 + 2, v15, &string);
                v4 = v3;
                if ( v3 < 0 )
                {
                  v5 = 1519;
                  goto LABEL_36;
                }
                v16 = v38;
                v17 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v38 + 56LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
                v3 = v17(v16, string, &v36);
                v4 = v3;
                if ( v3 < 0 )
                {
                  v5 = 1521;
                  goto LABEL_36;
                }
                v18 = wil::wait_for_completion<Windows::Devices::Power::Battery *,Microsoft::WRL::ComPtr<Windows::Devices::Power::IBattery>>(
                        &v37,
                        v36);
                if ( &v40 != v18 )
                {
                  v2 = *v18;
                  *v18 = 0;
                }
                v40 = 0;
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
                v19 = *((_QWORD *)this + 2 * *((unsigned int *)this + 58) + 30);
                v41 = 0;
                v20 = *(_QWORD *)(v19 + 24);
                if ( v20 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
                *(_QWORD *)(v19 + 24) = v2;
                v21 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 56LL);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19 + 32);
                v3 = v21(v2, v19 + 32);
                v4 = v3;
                v2 = 0;
                if ( v3 < 0 )
                {
                  v5 = 1524;
                  goto LABEL_36;
                }
                SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::GetDevicePropertyInfo(
                  v22,
                  ClassDevsW,
                  v7,
                  v23,
                  (unsigned __int16 **)(*((_QWORD *)this + 2 * *((unsigned int *)this + 58) + 30) + 16LL));
                ++*((_DWORD *)this + 58);
              }
            }
            else
            {
              OutputDebugStringW(L"Error: SetupDiGetInterfaceDeviceDetail failed \n");
            }
            LocalFree(v9);
          }
        }
        else
        {
          if ( GetLastError() == 259 )
            break;
          OutputDebugStringW(L"Error: SetupDiEnumInterfaceDevice, failed \n");
        }
        ++v7;
      }
      SetupDiDestroyDeviceInfoList(ClassDevsW);
    }
    v24 = *((_DWORD *)this + 58);
    if ( v24 > 1 )
      qsort((char *)this + 240, v24, 0x10u, SystemSettings::BatterySaverOneCoreDataModel::DeviceInfoSortCallback);
    v25 = 0;
    if ( *((_DWORD *)this + 58) )
    {
      do
      {
        v26 = v25 + 1;
        v27 = v25;
        **((_DWORD **)this + 2 * v25 + 30) = v25 + 1;
        v28 = *(_QWORD *)(*((_QWORD *)this + 2 * v25 + 30) + 24LL);
        v29 = *(void (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v28 + 64LL);
        v42 = SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::OnBatteryReportChanged;
        v44 = this;
        v30 = _lambda_eb7c2e257d91cb7bda74a3cb2a170578_::_lambda_eb7c2e257d91cb7bda74a3cb2a170578_(
                &hstringHeader,
                &v44,
                &v42);
        Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Devices::Power::Battery *,IInspectable *>,_lambda_650484c8b498dabf96094ba327a174b2_>(
          &v37,
          v30);
        v31 = (char *)this + 8 * v27 + 368;
        v32 = v37;
        v29(v28, v37, v31);
        if ( v32 )
        {
          v37 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
        v25 = v26;
      }
      while ( v26 < *((_DWORD *)this + 58) );
    }
    v4 = 0;
  }
  else
  {
    v5 = 1467;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batterysaver\\lib\\batterysaver.cpp",
      (const char *)(unsigned int)v3,
      DeviceInterfaceData);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  return v4;
}

```

## disassembly

```asm
0x180020724  push    rbp
0x180020726  push    rbx
0x180020727  push    rsi
0x180020728  push    rdi
0x180020729  push    r12
0x18002072b  push    r13
0x18002072d  push    r14
0x18002072f  push    r15
0x180020731  lea     rbp, [rsp-1Fh]
0x180020736  sub     rsp, 0D8h
0x18002073d  mov     rax, cs:__security_cookie
0x180020744  xor     rax, rsp
0x180020747  mov     [rbp+57h+var_48], rax
0x18002074b  mov     r14, rcx
0x18002074e  xor     r12d, r12d
0x180020751  mov     [rbp+57h+var_C8], r12
0x180020755  mov     [rbp+57h+var_B0], r12
0x180020759  mov     [rbp+57h+var_90], r12
0x18002075d  mov     [rsp+110h+var_D8], r12
0x180020762  mov     [rcx+0E8h], r12d
0x180020769  mov     [rsp+110h+RequiredSize], r12d
0x18002076e  xorps   xmm0, xmm0
0x180020771  movups  xmmword ptr [rbp+57h+var_88.cbSize], xmm0
0x180020775  movups  xmmword ptr [rbp+57h+var_88.InterfaceClassGuid.Data4+4], xmm0
0x180020779  mov     [rbp+57h+var_50], r12
0x18002077d  lea     r9d, [r12+1Dh]; unsigned int
0x180020782  lea     r8d, [r12+1Eh]; unsigned int
0x180020787  lea     rdx, ?RuntimeClass_Windows_Devices_Power_Battery@@3QBGB; "Windows.Devices.Power.Battery"
0x18002078e  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180020792  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020797  lea     rdx, [rbp+57h+var_C8]
0x18002079b  mov     rcx, [rbp+57h+var_50]
0x18002079f  call    ??$GetActivationFactory@V?$ComPtr@UIBatteryStatics@Power@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIBatteryStatics@Power@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Power::IBatteryStatics>>)
0x1800207a4  mov     ebx, eax
0x1800207a6  test    eax, eax
0x1800207a8  jns     short loc_1800207B4
0x1800207aa  mov     edx, 5BBh
0x1800207af  jmp     loc_180020B00
0x1800207b4  mov     r9d, 12h; Flags
0x1800207ba  xor     r8d, r8d; hwndParent
0x1800207bd  xor     edx, edx; Enumerator
0x1800207bf  lea     rcx, GUID_DEVICE_BATTERY; ClassGuid
0x1800207c6  call    cs:__imp_SetupDiGetClassDevsW
0x1800207cc  mov     rsi, rax
0x1800207cf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800207d3  cmp     rax, rdi
0x1800207d6  jz      loc_180020B23
0x1800207dc  mov     r15d, r12d
0x1800207df  mov     [rbp+57h+var_88.cbSize], 20h ; ' '
0x1800207e6  cmp     r15d, 8
0x1800207ea  jnb     loc_180020B18
0x1800207f0  lea     rax, [rbp+57h+var_88]
0x1800207f4  mov     [rsp+110h+DeviceInterfaceData], rax; DeviceInterfaceData
0x1800207f9  mov     r9d, r15d; MemberIndex
0x1800207fc  lea     r8, GUID_DEVICE_BATTERY; InterfaceClassGuid
0x180020803  xor     edx, edx; DeviceInfoData
0x180020805  mov     rcx, rsi; DeviceInfoSet
0x180020808  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18002080e  test    eax, eax
0x180020810  jz      loc_180020ACB
0x180020816  mov     [rsp+110h+DeviceInfoData], r12; DeviceInfoData
0x18002081b  lea     rax, [rsp+110h+RequiredSize]
0x180020820  mov     [rsp+110h+DeviceInterfaceData], rax; RequiredSize
0x180020825  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x180020828  xor     r8d, r8d; DeviceInterfaceDetailData
0x18002082b  lea     rdx, [rbp+57h+var_88]; DeviceInterfaceData
0x18002082f  mov     rcx, rsi; DeviceInfoSet
0x180020832  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x180020838  mov     edx, [rsp+110h+RequiredSize]; uBytes
0x18002083c  xor     ecx, ecx; uFlags
0x18002083e  call    cs:__imp_LocalAlloc
0x180020844  mov     r13, rax
0x180020847  test    rax, rax
0x18002084a  jz      loc_180020AE5
0x180020850  mov     dword ptr [rax], 8
0x180020856  mov     [rsp+110h+DeviceInfoData], r12; DeviceInfoData
0x18002085b  lea     rax, [rsp+110h+RequiredSize]
0x180020860  mov     [rsp+110h+DeviceInterfaceData], rax; RequiredSize
0x180020865  mov     r9d, [rsp+110h+RequiredSize]; DeviceInterfaceDetailDataSize
0x18002086a  mov     r8, r13; DeviceInterfaceDetailData
0x18002086d  lea     rdx, [rbp+57h+var_88]; DeviceInterfaceData
0x180020871  mov     rcx, rsi; DeviceInfoSet
0x180020874  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18002087a  test    eax, eax
0x18002087c  jz      loc_180020AB3
0x180020882  mov     ecx, 38h ; '8'; Size
0x180020887  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002088c  mov     [rbp+57h+var_98], rax
0x180020890  xorps   xmm0, xmm0
0x180020893  movups  xmmword ptr [rax], xmm0
0x180020896  mov     dword ptr [rax+8], 1
0x18002089d  mov     dword ptr [rax+0Ch], 1
0x1800208a4  lea     rcx, ??_7?$_Ref_count_obj2@VIndividualBattery@BatterySaverOneCoreDataModel@SystemSettings@@@std@@6B@; const std::_Ref_count_obj2<SystemSettings::BatterySaverOneCoreDataModel::IndividualBattery>::`vftable'
0x1800208ab  mov     [rax], rcx
0x1800208ae  lea     rcx, [rax+10h]
0x1800208b2  mov     [rcx+18h], r12
0x1800208b6  mov     [rcx+20h], r12
0x1800208ba  mov     [rbp+57h+var_A8], rcx
0x1800208be  mov     [rbp+57h+var_A0], rax
0x1800208c2  mov     ecx, [r14+0E8h]
0x1800208c9  add     rcx, 0Fh
0x1800208cd  shl     rcx, 4
0x1800208d1  add     rcx, r14
0x1800208d4  lea     rdx, [rbp+57h+var_A8]
0x1800208d8  call    ??4?$shared_ptr@VIndividualBattery@BatterySaverOneCoreDataModel@SystemSettings@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<SystemSettings::BatterySaverOneCoreDataModel::IndividualBattery>::operator=(std::shared_ptr<SystemSettings::BatterySaverOneCoreDataModel::IndividualBattery> &&)
0x1800208dd  mov     rbx, [rbp+57h+var_A0]
0x1800208e1  test    rbx, rbx
0x1800208e4  jz      short loc_180020919
0x1800208e6  mov     eax, edi
0x1800208e8  lock xadd [rbx+8], eax
0x1800208ed  add     eax, edi
0x1800208ef  jnz     short loc_180020919
0x1800208f1  mov     rax, [rbx]
0x1800208f4  mov     rcx, rbx
0x1800208f7  mov     rax, [rax]
0x1800208fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208ff  mov     eax, edi
0x180020901  lock xadd [rbx+0Ch], eax
0x180020906  add     eax, edi
0x180020908  jnz     short loc_180020919
0x18002090a  mov     rax, [rbx]
0x18002090d  mov     rcx, rbx
0x180020910  mov     rax, [rax+8]
0x180020914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020919  mov     rax, rdi
0x18002091c  inc     rax
0x18002091f  cmp     [r13+rax*2+4], r12w
0x180020925  jnz     short loc_18002091C
0x180020927  lea     eax, ds:2[rax*2]
0x18002092e  mov     [rsp+110h+RequiredSize], eax
0x180020932  mov     edx, eax; uBytes
0x180020934  xor     ecx, ecx; uFlags
0x180020936  call    cs:__imp_LocalAlloc
0x18002093c  mov     ecx, [r14+0E8h]
0x180020943  add     rcx, 0Fh
0x180020947  add     rcx, rcx
0x18002094a  mov     rcx, [r14+rcx*8]
0x18002094e  mov     [rcx+8], rax
0x180020952  mov     eax, [r14+0E8h]
0x180020959  add     rax, 0Fh
0x18002095d  add     rax, rax
0x180020960  mov     rax, [r14+rax*8]
0x180020964  mov     rcx, [rax+8]; pszDest
0x180020968  test    rcx, rcx
0x18002096b  jz      loc_180020AC0
0x180020971  mov     edx, [rsp+110h+RequiredSize]
0x180020975  shr     rdx, 1; cchDest
0x180020978  jz      short loc_18002098C
0x18002097a  mov     [rsp+110h+DeviceInterfaceData], 7FFFFFFEh; int
0x180020983  lea     r9, [r13+4]; pszSrc
0x180020987  call    StringCopyWorkerW_0
0x18002098c  mov     [rbp+57h+string], r12
0x180020990  mov     rdx, rdi
0x180020993  inc     rdx; length
0x180020996  cmp     [r13+rdx*2+4], r12w
0x18002099c  jnz     short loc_180020993
0x18002099e  lea     r8, [rbp+57h+string]; string
0x1800209a2  lea     rcx, [r13+4]; sourceString
0x1800209a6  call    cs:__imp_WindowsCreateString
0x1800209ac  mov     ebx, eax
0x1800209ae  test    eax, eax
0x1800209b0  js      loc_180020AFB
0x1800209b6  mov     rdi, [rbp+57h+var_C8]
0x1800209ba  mov     rax, [rdi]
0x1800209bd  mov     rbx, [rax+38h]
0x1800209c1  lea     rcx, [rsp+110h+var_D8]
0x1800209c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800209cb  lea     r8, [rsp+110h+var_D8]
0x1800209d0  mov     rdx, [rbp+57h+string]
0x1800209d4  mov     rcx, rdi
0x1800209d7  mov     rax, rbx
0x1800209da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209df  mov     ebx, eax
0x1800209e1  test    eax, eax
0x1800209e3  js      loc_180020AF4
0x1800209e9  mov     rdx, [rsp+110h+var_D8]
0x1800209ee  lea     rcx, [rbp+57h+var_D0]
0x1800209f2  call    ??$wait_for_completion@PEAVBattery@Power@Devices@Windows@@V?$ComPtr@UIBattery@Power@Devices@Windows@@@WRL@Microsoft@@@wil@@YA?AV?$ComPtr@UIBattery@Power@Devices@Windows@@@WRL@Microsoft@@PEAU?$IAsyncOperation@PEAVBattery@Power@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@@Z; wil::wait_for_completion<Windows::Devices::Power::Battery *,Microsoft::WRL::ComPtr<Windows::Devices::Power::IBattery>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Power::Battery *> *,tagCOWAIT_FLAGS)
0x1800209f7  lea     rcx, [rbp+57h+var_B8]
0x1800209fb  cmp     rcx, rax
0x1800209fe  jz      short loc_180020A0A
0x180020a00  mov     r12, [rax]
0x180020a03  mov     qword ptr [rax], 0
0x180020a0a  mov     [rbp+57h+var_B8], 0
0x180020a12  lea     rcx, [rbp+57h+var_B8]
0x180020a16  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020a1b  lea     rcx, [rbp+57h+var_D0]
0x180020a1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020a24  mov     eax, [r14+0E8h]
0x180020a2b  add     rax, 0Fh
0x180020a2f  add     rax, rax
0x180020a32  mov     rbx, [r14+rax*8]
0x180020a36  mov     [rbp+57h+var_B0], 0
0x180020a3e  mov     rcx, [rbx+18h]
0x180020a42  test    rcx, rcx
0x180020a45  jz      short loc_180020A53
0x180020a47  mov     rax, [rcx]
0x180020a4a  mov     rax, [rax+10h]
0x180020a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a53  mov     [rbx+18h], r12
0x180020a57  mov     rax, [r12]
0x180020a5b  mov     rdi, [rax+38h]
0x180020a5f  lea     rcx, [rbx+20h]
0x180020a63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180020a68  lea     rdx, [rbx+20h]
0x180020a6c  mov     rcx, r12
0x180020a6f  mov     rax, rdi
0x180020a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a77  mov     ebx, eax
0x180020a79  xor     r12d, r12d
0x180020a7c  test    eax, eax
0x180020a7e  js      short loc_180020AED
0x180020a80  mov     eax, [r14+0E8h]
0x180020a87  add     rax, 0Fh
0x180020a8b  add     rax, rax
0x180020a8e  mov     rax, [r14+rax*8]
0x180020a92  add     rax, 10h
0x180020a96  mov     [rsp+110h+DeviceInterfaceData], rax; unsigned __int16 **
0x180020a9b  mov     r8d, r15d; unsigned int
0x180020a9e  mov     rdx, rsi; void *
0x180020aa1  call    ?GetDevicePropertyInfo@CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@AEAAXPEAXIPEBU_DEVPROPKEY@@PEAPEAG@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::GetDevicePropertyInfo(void *,uint,_DEVPROPKEY const *,ushort * *)
0x180020aa6  inc     dword ptr [r14+0E8h]
0x180020aad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180020ab1  jmp     short loc_180020AC0
0x180020ab3  lea     rcx, OutputString; "Error: SetupDiGetInterfaceDeviceDetail "...
0x180020aba  call    cs:__imp_OutputDebugStringW
0x180020ac0  mov     rcx, r13; hMem
0x180020ac3  call    cs:__imp_LocalFree
0x180020ac9  jmp     short loc_180020AE5
0x180020acb  call    cs:__imp_GetLastError
0x180020ad1  cmp     eax, 103h
0x180020ad6  jz      short loc_180020B18
0x180020ad8  lea     rcx, aErrorSetupdien; "Error: SetupDiEnumInterfaceDevice, fail"...
0x180020adf  call    cs:__imp_OutputDebugStringW
0x180020ae5  inc     r15d
0x180020ae8  jmp     loc_1800207E6
0x180020aed  mov     edx, 5F4h
0x180020af2  jmp     short loc_180020B00
0x180020af4  mov     edx, 5F1h
0x180020af9  jmp     short loc_180020B00
0x180020afb  mov     edx, 5EFh; void *
0x180020b00  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\coresettinghandlers"...
0x180020b07  mov     r9d, eax; char *
0x180020b0a  mov     rcx, [rbp+5Fh]; this
0x180020b0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020b13  jmp     loc_180020BFF
0x180020b18  mov     rcx, rsi; DeviceInfoSet
0x180020b1b  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180020b21  jmp     short loc_180020B30
0x180020b23  lea     rcx, aErrorSetupdige_0; "Error: SetupDiGetClassDevs on GUID_DEVI"...
0x180020b2a  call    cs:__imp_OutputDebugStringW
0x180020b30  mov     eax, [r14+0E8h]
0x180020b37  cmp     eax, 1
0x180020b3a  jbe     short loc_180020B58
0x180020b3c  mov     edx, eax; NumOfElements
0x180020b3e  lea     rcx, [r14+0F0h]; Base
0x180020b45  lea     r9, ?DeviceInfoSortCallback@BatterySaverOneCoreDataModel@SystemSettings@@YAHPEBX0@Z; CompareFunction
0x180020b4c  mov     r8d, 10h; SizeOfElements
0x180020b52  call    cs:__imp_qsort
0x180020b58  mov     eax, r12d
0x180020b5b  cmp     [r14+0E8h], r12d
0x180020b62  jbe     loc_180020BFC
0x180020b68  lea     r15d, [rax+1]
0x180020b6c  mov     esi, eax
0x180020b6e  lea     rcx, [rsi+0Fh]
0x180020b72  add     rcx, rcx
0x180020b75  mov     rax, [r14+rcx*8]
0x180020b79  mov     [rax], r15d
0x180020b7c  mov     rax, [r14+rcx*8]
0x180020b80  mov     rdi, [rax+18h]
0x180020b84  mov     rax, [rdi]
0x180020b87  mov     rbx, [rax+40h]
0x180020b8b  lea     rax, ?OnBatteryReportChanged@CBatterySaverMultipleBatterySingleton@BatterySaverOneCoreDataModel@SystemSettings@@QEAAJPEAUIBattery@Power@Devices@Windows@@PEAUIInspectable@@@Z; SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverMultipleBatterySingleton::OnBatteryReportChanged(Windows::Devices::Power::IBattery *,IInspectable *)
0x180020b92  mov     [rbp+57h+var_A8], rax
0x180020b96  mov     [rbp+57h+var_98], r14
0x180020b9a  lea     r8, [rbp+57h+var_A8]
0x180020b9e  lea     rdx, [rbp+57h+var_98]
0x180020ba2  lea     rcx, [rbp+57h+hstringHeader]
0x180020ba6  call    ??0_lambda_eb7c2e257d91cb7bda74a3cb2a170578_@@QEAA@AEBQEAVCBatterySaverBatteryInfoSingleton@BatterySaverOneCoreDataModel@SystemSettings@@AEBQ8123@EAAJPEAUIInspectable@@1@Z@Z; _lambda_eb7c2e257d91cb7bda74a3cb2a170578_::_lambda_eb7c2e257d91cb7bda74a3cb2a170578_(SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverBatteryInfoSingleton * const &,long (SystemSettings::BatterySaverOneCoreDataModel::CBatterySaverBatteryInfoSingleton::*const &)(IInspectable *,IInspectable *))
0x180020bab  mov     rdx, rax
0x180020bae  lea     rcx, [rbp+57h+var_D0]
0x180020bb2  call    ??$Callback@U?$ITypedEventHandler@PEAVBattery@Power@Devices@Windows@@PEAUIInspectable@@@Foundation@Windows@@V_lambda_650484c8b498dabf96094ba327a174b2_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAVBattery@Power@Devices@Windows@@PEAUIInspectable@@@Foundation@Windows@@@01@$$QEAV_lambda_650484c8b498dabf96094ba327a174b2_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Devices::Power::Battery *,IInspectable *>,_lambda_650484c8b498dabf96094ba327a174b2_>(_lambda_650484c8b498dabf96094ba327a174b2_ &&)
0x180020bb7  nop
0x180020bb8  add     rsi, 2Eh ; '.'
0x180020bbc  lea     r8, [r14+rsi*8]
0x180020bc0  mov     rsi, [rbp+57h+var_D0]
0x180020bc4  mov     rdx, rsi
0x180020bc7  mov     rcx, rdi
0x180020bca  mov     rax, rbx
0x180020bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bd2  nop
0x180020bd3  test    rsi, rsi
0x180020bd6  jz      short loc_180020BEC
0x180020bd8  mov     [rbp+57h+var_D0], r12
0x180020bdc  mov     rax, [rsi]
0x180020bdf  mov     rcx, rsi
0x180020be2  mov     rax, [rax+10h]
0x180020be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020beb  nop
0x180020bec  mov     eax, r15d
  ... truncated ...
```
