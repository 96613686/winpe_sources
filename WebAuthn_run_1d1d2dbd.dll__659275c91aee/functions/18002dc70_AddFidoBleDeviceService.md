# _AddFidoBleDeviceService

- ea: `0x18002dc70`
- end: `0x18002e249`
- name: `_AddFidoBleDeviceService`
- size: `1497`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fb8fc`

## callees

- `0x18000bb40`
- `0x18002bbc8`
- `0x18002cbb4`
- `0x18002dc70`
- `0x18002e6d4`
- `0x18002e81c`
- `0x180045560`
- `0x180045940`
- `0x18005378c`
- `0x1800f22a8`
- `0x1800f24bc`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e0d2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e0d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e1f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e09f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e09f`

## string_xrefs

- `0x18002e1e3`: `_AddFidoBleDeviceService`
- `0x18002df7d`: `ServicesGet`
- `0x18002df08`: `ServicesBlock`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall AddFidoBleDeviceService(__int64 a1, __int64 a2)
{
  const char *v3; // r12
  int v4; // edi
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 (__fastcall *v15)(__int64, __int64 *); // rdi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 (__fastcall ***v19)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v20)(_QWORD, GUID *, __int64 *); // rdi
  unsigned int i; // r14d
  PCWSTR StringRawBuffer; // rax
  PCWSTR v23; // r13
  unsigned int v24; // r15d
  __int64 v25; // rcx
  char *v26; // rax
  _QWORD *v27; // rsi
  char *v28; // rbx
  void *v29; // rbx
  __int64 v30; // r15
  _QWORD *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 (__fastcall ***v35)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v37; // [rsp+20h] [rbp-69h]
  __int64 v38; // [rsp+30h] [rbp-59h] BYREF
  __int64 v39; // [rsp+38h] [rbp-51h] BYREF
  unsigned __int16 v40; // [rsp+40h] [rbp-49h] BYREF
  __int64 v41; // [rsp+48h] [rbp-41h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-39h] BYREF
  __int64 v43; // [rsp+58h] [rbp-31h] BYREF
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  __int64 v45; // [rsp+68h] [rbp-21h] BYREF
  __int64 v46; // [rsp+70h] [rbp-19h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v48; // [rsp+98h] [rbp+Fh]

  v46 = a1;
  v42 = 0;
  v43 = 0;
  string = 0;
  v45 = 0;
  v3 = 0;
  v39 = 0;
  v38 = 0;
  v48 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Bluetooth.BluetoothLEDevice",
    0x2Cu,
    0x2Bu);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Bluetooth::IBluetoothLEDeviceStatics>>(
         v48,
         &v39);
  if ( v4 < 0 )
    goto LABEL_69;
  v4 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 48LL))(v39, a2, &v38);
  if ( v4 < 0 )
  {
    v5 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    goto LABEL_69;
  }
  v6 = v38;
  if ( !v38 )
  {
    v3 = "DeviceBlock";
    v4 = -2147418113;
LABEL_69:
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v39);
    goto LABEL_70;
  }
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::BluetoothLEDevice *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::BluetoothLEDevice *>>(v38);
  if ( v4 < 0
    || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v6 + 64LL))(
               v6,
               &v42),
        v4 < 0) )
  {
    v34 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    goto LABEL_69;
  }
  if ( !v42 )
  {
    v3 = "DeviceGet";
    v4 = -2147418113;
    v7 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    goto LABEL_69;
  }
  v4 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v42)[10])(v42, &v45);
  if ( v4 < 0 )
  {
    v8 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_69;
  }
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v42)[7])(v42, &string);
  v9 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v39);
  v39 = 0;
  v41 = 0;
  v38 = 0;
  v4 = Microsoft::WRL::ComPtr<Windows::Devices::Bluetooth::IBluetoothLEDevice>::As<Windows::Devices::Bluetooth::IBluetoothLEDevice3>(
         &v42,
         &v39);
  if ( v4 < 0 )
  {
    v10 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
LABEL_23:
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v41);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v39);
    goto LABEL_70;
  }
  *(_OWORD *)&hstringHeader.Reserved.Reserved1 = xmmword_18014FEE0;
  v4 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, _QWORD, __int64 *))(*(_QWORD *)v39 + 88LL))(
         v39,
         &hstringHeader,
         0,
         &v38);
  if ( v4 < 0 )
  {
    v11 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_23;
  }
  v12 = v38;
  v4 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult *>>(v38);
  if ( v4 < 0 || (v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v12 + 64LL))(v12, &v41), v4 < 0) )
  {
    v33 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    goto LABEL_23;
  }
  v13 = v41;
  if ( !v41 )
  {
    v3 = "ServicesBlock";
    v4 = -2147418113;
    v14 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    goto LABEL_23;
  }
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 64LL);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v43);
  v4 = v15(v13, &v43);
  if ( v4 < 0 )
  {
    v16 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    goto LABEL_23;
  }
  if ( !v43 )
  {
    v3 = "ServicesGet";
    v4 = -2147418113;
    v17 = v38;
    if ( v38 )
    {
      v38 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_23;
  }
  v18 = v38;
  if ( v38 )
  {
    v38 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v41);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v39);
  LODWORD(v38) = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v43 + 56LL))(v43, &v38);
  if ( (_DWORD)v38 )
  {
    v39 = 0;
    v19 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
    v20 = **v42;
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v39);
    v4 = v20(v19, &GUID_26f062b3_7aee_4d31_baba_b1b9775f5916, &v39);
    if ( v4 < 0 )
      goto LABEL_69;
    v4 = CheckBleDeviceProtectionLevel(v39);
    if ( v4 < 0 )
      goto LABEL_69;
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v39);
    for ( i = 0; i < (unsigned int)v38; ++i )
    {
      v39 = 0;
      v40 = 0;
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 48LL))(v43, i, &v39);
      if ( v39 )
      {
        (*(void (__fastcall **)(__int64, unsigned __int16 *))(*(_QWORD *)v39 + 80LL))(v39, &v40);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v23 = StringRawBuffer;
        v24 = 0;
        if ( StringRawBuffer )
        {
          v25 = -1;
          do
            ++v25;
          while ( StringRawBuffer[v25] );
          v24 = v25 + 1;
        }
        v26 = (char *)LocalAlloc(0x40u, 2LL * (v24 + 22) + 288);
        v27 = v26;
        if ( v26 )
        {
          v28 = v26 + 288;
          *((_QWORD *)v26 + 1) = v26;
          *(_QWORD *)v26 = v26;
          *((_DWORD *)v26 + 4) = 1;
          *((_QWORD *)v26 + 3) = L"Ble";
          *((_QWORD *)v26 + 4) = L"MicrosoftCtapBleProvider";
          LODWORD(v37) = v40;
          StringCchPrintfW((unsigned __int16 *)v26 + 144, 0x16u, L"ble:%012I64x_%04x", v45, v37);
          v27[6] = v28;
          if ( v24 )
          {
            v29 = v28 + 44;
            memcpy_0(v29, v23, 2LL * v24);
            v27[10] = v29;
          }
          v30 = v46;
          v31 = *(_QWORD **)(v46 + 8);
          if ( *v31 != v46 )
            __fastfail(3u);
          *v27 = v46;
          v27[1] = v31;
          *v31 = v27;
          *(_QWORD *)(v30 + 8) = v27;
        }
        v32 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        }
      }
    }
  }
LABEL_70:
  CtapBleLogError((unsigned int)v4, "_AddFidoBleDeviceService", v3);
  WindowsDeleteString(string);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v43);
  v35 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v42;
  if ( v42 )
  {
    v42 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v35)[2])(v35);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002dc70  mov     [rsp-8+arg_10], rbx
0x18002dc75  push    rbp
0x18002dc76  push    rsi
0x18002dc77  push    rdi
0x18002dc78  push    r12
0x18002dc7a  push    r13
0x18002dc7c  push    r14
0x18002dc7e  push    r15
0x18002dc80  lea     rbp, [rsp-27h]
0x18002dc85  sub     rsp, 0B0h
0x18002dc8c  mov     rax, cs:__security_cookie
0x18002dc93  xor     rax, rsp
0x18002dc96  mov     [rbp+57h+var_40], rax
0x18002dc9a  mov     rbx, rdx
0x18002dc9d  mov     [rbp+57h+var_70], rcx
0x18002dca1  xor     esi, esi
0x18002dca3  mov     [rbp+57h+var_90], rsi
0x18002dca7  mov     [rbp+57h+var_88], rsi
0x18002dcab  mov     [rbp+57h+string], rsi
0x18002dcaf  mov     [rbp+57h+var_78], rsi
0x18002dcb3  mov     r12d, esi
0x18002dcb6  mov     [rbp+57h+var_A8], rsi
0x18002dcba  mov     [rbp+57h+var_B0], rsi
0x18002dcbe  mov     [rbp+57h+var_48], rsi
0x18002dcc2  lea     r9d, [rsi+2Bh]; unsigned int
0x18002dcc6  lea     r8d, [rsi+2Ch]; unsigned int
0x18002dcca  lea     rdx, ?RuntimeClass_Windows_Devices_Bluetooth_BluetoothLEDevice@@3QBGB; "Windows.Devices.Bluetooth.BluetoothLEDe"...
0x18002dcd1  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002dcd5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002dcda  lea     rdx, [rbp+57h+var_A8]
0x18002dcde  mov     rcx, [rbp+57h+var_48]
0x18002dce2  call    ??$GetActivationFactory@V?$ComPtr@UIBluetoothLEDeviceStatics@Bluetooth@Devices@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIBluetoothLEDeviceStatics@Bluetooth@Devices@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Devices::Bluetooth::IBluetoothLEDeviceStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Bluetooth::IBluetoothLEDeviceStatics>>)
0x18002dce7  mov     edi, eax
0x18002dce9  test    eax, eax
0x18002dceb  jns     short loc_18002DD0C
0x18002dced  mov     rcx, [rbp+57h+var_B0]
0x18002dcf1  test    rcx, rcx
0x18002dcf4  jz      short loc_18002DD07
0x18002dcf6  mov     [rbp+57h+var_B0], rsi
0x18002dcfa  mov     rdx, [rcx]
0x18002dcfd  mov     rax, [rdx+10h]
0x18002dd01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd06  nop
0x18002dd07  jmp     loc_18002E1D7
0x18002dd0c  mov     rcx, [rbp+57h+var_A8]
0x18002dd10  mov     rax, [rcx]
0x18002dd13  lea     r8, [rbp+57h+var_B0]
0x18002dd17  mov     rdx, rbx
0x18002dd1a  mov     rax, [rax+30h]
0x18002dd1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd23  mov     edi, eax
0x18002dd25  test    eax, eax
0x18002dd27  jns     short loc_18002DD48
0x18002dd29  mov     rcx, [rbp+57h+var_B0]
0x18002dd2d  test    rcx, rcx
0x18002dd30  jz      short loc_18002DD43
0x18002dd32  mov     [rbp+57h+var_B0], rsi
0x18002dd36  mov     rax, [rcx]
0x18002dd39  mov     rax, [rax+10h]
0x18002dd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd42  nop
0x18002dd43  jmp     loc_18002E1D7
0x18002dd48  mov     rbx, [rbp+57h+var_B0]
0x18002dd4c  test    rbx, rbx
0x18002dd4f  jnz     short loc_18002DD62
0x18002dd51  lea     r12, aDeviceblock; "DeviceBlock"
0x18002dd58  mov     edi, 8000FFFFh
0x18002dd5d  jmp     loc_18002E1D7
0x18002dd62  mov     rcx, rbx
0x18002dd65  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVBluetoothLEDevice@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVBluetoothLEDevice@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVBluetoothLEDevice@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::BluetoothLEDevice *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::BluetoothLEDevice *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::BluetoothLEDevice *> *,tagCOWAIT_FLAGS,void *)
0x18002dd6a  mov     edi, eax
0x18002dd6c  test    eax, eax
0x18002dd6e  js      loc_18002E1BD
0x18002dd74  mov     rax, [rbx]
0x18002dd77  lea     rdx, [rbp+57h+var_90]
0x18002dd7b  mov     rcx, rbx
0x18002dd7e  mov     rax, [rax+40h]
0x18002dd82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dd87  mov     edi, eax
0x18002dd89  test    eax, eax
0x18002dd8b  js      loc_18002E1BD
0x18002dd91  mov     rcx, [rbp+57h+var_90]
0x18002dd95  test    rcx, rcx
0x18002dd98  jnz     short loc_18002DDC5
0x18002dd9a  lea     r12, aDeviceget; "DeviceGet"
0x18002dda1  mov     edi, 8000FFFFh
0x18002dda6  mov     rcx, [rbp+57h+var_B0]
0x18002ddaa  test    rcx, rcx
0x18002ddad  jz      short loc_18002DDC0
0x18002ddaf  mov     [rbp+57h+var_B0], rsi
0x18002ddb3  mov     rax, [rcx]
0x18002ddb6  mov     rax, [rax+10h]
0x18002ddba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddbf  nop
0x18002ddc0  jmp     loc_18002E1D7
0x18002ddc5  mov     rax, [rcx]
0x18002ddc8  lea     rdx, [rbp+57h+var_78]
0x18002ddcc  mov     rax, [rax+50h]
0x18002ddd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddd5  mov     edi, eax
0x18002ddd7  test    eax, eax
0x18002ddd9  jns     short loc_18002DDFA
0x18002dddb  mov     rcx, [rbp+57h+var_B0]
0x18002dddf  test    rcx, rcx
0x18002dde2  jz      short loc_18002DDF5
0x18002dde4  mov     [rbp+57h+var_B0], rsi
0x18002dde8  mov     rax, [rcx]
0x18002ddeb  mov     rax, [rax+10h]
0x18002ddef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddf4  nop
0x18002ddf5  jmp     loc_18002E1D7
0x18002ddfa  mov     rcx, [rbp+57h+var_90]
0x18002ddfe  mov     rax, [rcx]
0x18002de01  lea     rdx, [rbp+57h+string]
0x18002de05  mov     rax, [rax+38h]
0x18002de09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de0e  nop
0x18002de0f  mov     rcx, [rbp+57h+var_B0]
0x18002de13  test    rcx, rcx
0x18002de16  jz      short loc_18002DE29
0x18002de18  mov     [rbp+57h+var_B0], rsi
0x18002de1c  mov     rax, [rcx]
0x18002de1f  mov     rax, [rax+10h]
0x18002de23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de28  nop
0x18002de29  lea     rcx, [rbp+57h+var_A8]
0x18002de2d  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002de32  mov     [rbp+57h+var_A8], rsi
0x18002de36  mov     [rbp+57h+var_98], rsi
0x18002de3a  mov     [rbp+57h+var_B0], rsi
0x18002de3e  lea     rdx, [rbp+57h+var_A8]
0x18002de42  lea     rcx, [rbp+57h+var_90]
0x18002de46  call    ??$As@UIBluetoothLEDevice3@Bluetooth@Devices@Windows@@@?$ComPtr@UIBluetoothLEDevice@Bluetooth@Devices@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBluetoothLEDevice3@Bluetooth@Devices@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Devices::Bluetooth::IBluetoothLEDevice>::As<Windows::Devices::Bluetooth::IBluetoothLEDevice3>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Devices::Bluetooth::IBluetoothLEDevice3>>)
0x18002de4b  mov     edi, eax
0x18002de4d  test    eax, eax
0x18002de4f  jns     short loc_18002DE83
0x18002de51  mov     rcx, [rbp+57h+var_B0]
0x18002de55  test    rcx, rcx
0x18002de58  jz      short loc_18002DE6B
0x18002de5a  mov     [rbp+57h+var_B0], rsi
0x18002de5e  mov     rax, [rcx]
0x18002de61  mov     rax, [rax+10h]
0x18002de65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002de6a  nop
0x18002de6b  lea     rcx, [rbp+57h+var_98]
0x18002de6f  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002de74  nop
0x18002de75  lea     rcx, [rbp+57h+var_A8]
0x18002de79  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002de7e  jmp     loc_18002E1E0
0x18002de83  mov     rcx, [rbp+57h+var_A8]
0x18002de87  movups  xmm0, cs:xmmword_18014FEE0
0x18002de8e  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18002de93  mov     rax, [rcx]
0x18002de96  lea     r9, [rbp+57h+var_B0]
0x18002de9a  xor     r8d, r8d
0x18002de9d  lea     rdx, [rbp+57h+hstringHeader]
0x18002dea1  mov     rax, [rax+58h]
0x18002dea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002deaa  mov     edi, eax
0x18002deac  test    eax, eax
0x18002deae  jns     short loc_18002DECC
0x18002deb0  mov     rcx, [rbp+57h+var_B0]
0x18002deb4  test    rcx, rcx
0x18002deb7  jz      short loc_18002DECA
0x18002deb9  mov     [rbp+57h+var_B0], rsi
0x18002debd  mov     rax, [rcx]
0x18002dec0  mov     rax, [rax+10h]
0x18002dec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dec9  nop
0x18002deca  jmp     short loc_18002DE6B
0x18002decc  mov     rbx, [rbp+57h+var_B0]
0x18002ded0  mov     rcx, rbx
0x18002ded3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattDeviceServicesResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattDeviceServicesResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattDeviceServicesResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattDeviceServicesResult *> *,tagCOWAIT_FLAGS,void *)
0x18002ded8  mov     edi, eax
0x18002deda  test    eax, eax
0x18002dedc  js      loc_18002E19E
0x18002dee2  mov     rax, [rbx]
0x18002dee5  lea     rdx, [rbp+57h+var_98]
0x18002dee9  mov     rcx, rbx
0x18002deec  mov     rax, [rax+40h]
0x18002def0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002def5  mov     edi, eax
0x18002def7  test    eax, eax
0x18002def9  js      loc_18002E19E
0x18002deff  mov     rbx, [rbp+57h+var_98]
0x18002df03  test    rbx, rbx
0x18002df06  jnz     short loc_18002DF33
0x18002df08  lea     r12, aServicesblock; "ServicesBlock"
0x18002df0f  mov     edi, 8000FFFFh
0x18002df14  mov     rcx, [rbp+57h+var_B0]
0x18002df18  test    rcx, rcx
0x18002df1b  jz      short loc_18002DF2E
0x18002df1d  mov     [rbp+57h+var_B0], rsi
0x18002df21  mov     rax, [rcx]
0x18002df24  mov     rax, [rax+10h]
0x18002df28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df2d  nop
0x18002df2e  jmp     loc_18002DE6B
0x18002df33  mov     rax, [rbx]
0x18002df36  mov     rdi, [rax+40h]
0x18002df3a  lea     rcx, [rbp+57h+var_88]
0x18002df3e  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002df43  lea     rdx, [rbp+57h+var_88]
0x18002df47  mov     rcx, rbx
0x18002df4a  mov     rax, rdi
0x18002df4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df52  mov     edi, eax
0x18002df54  test    eax, eax
0x18002df56  jns     short loc_18002DF77
0x18002df58  mov     rcx, [rbp+57h+var_B0]
0x18002df5c  test    rcx, rcx
0x18002df5f  jz      short loc_18002DF72
0x18002df61  mov     [rbp+57h+var_B0], rsi
0x18002df65  mov     rax, [rcx]
0x18002df68  mov     rax, [rax+10h]
0x18002df6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df71  nop
0x18002df72  jmp     loc_18002DE6B
0x18002df77  cmp     [rbp+57h+var_88], rsi
0x18002df7b  jnz     short loc_18002DFA8
0x18002df7d  lea     r12, aServicesget; "ServicesGet"
0x18002df84  mov     edi, 8000FFFFh
0x18002df89  mov     rcx, [rbp+57h+var_B0]
0x18002df8d  test    rcx, rcx
0x18002df90  jz      short loc_18002DFA3
0x18002df92  mov     [rbp+57h+var_B0], rsi
0x18002df96  mov     rax, [rcx]
0x18002df99  mov     rax, [rax+10h]
0x18002df9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfa2  nop
0x18002dfa3  jmp     loc_18002DE6B
0x18002dfa8  mov     rcx, [rbp+57h+var_B0]
0x18002dfac  test    rcx, rcx
0x18002dfaf  jz      short loc_18002DFC2
0x18002dfb1  mov     [rbp+57h+var_B0], rsi
0x18002dfb5  mov     rax, [rcx]
0x18002dfb8  mov     rax, [rax+10h]
0x18002dfbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfc1  nop
0x18002dfc2  lea     rcx, [rbp+57h+var_98]
0x18002dfc6  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002dfcb  nop
0x18002dfcc  lea     rcx, [rbp+57h+var_A8]
0x18002dfd0  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002dfd5  mov     dword ptr [rbp+57h+var_B0], esi
0x18002dfd8  mov     rcx, [rbp+57h+var_88]
0x18002dfdc  mov     rax, [rcx]
0x18002dfdf  lea     rdx, [rbp+57h+var_B0]
0x18002dfe3  mov     rax, [rax+38h]
0x18002dfe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfec  cmp     dword ptr [rbp+57h+var_B0], esi
0x18002dfef  jz      loc_18002E1E0
0x18002dff5  mov     [rbp+57h+var_A8], rsi
0x18002dff9  mov     rbx, [rbp+57h+var_90]
0x18002dffd  mov     rax, [rbx]
0x18002e000  mov     rdi, [rax]
0x18002e003  lea     rcx, [rbp+57h+var_A8]
0x18002e007  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002e00c  lea     r8, [rbp+57h+var_A8]
0x18002e010  lea     rdx, _GUID_26f062b3_7aee_4d31_baba_b1b9775f5916
0x18002e017  mov     rcx, rbx
0x18002e01a  mov     rax, rdi
0x18002e01d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e022  mov     edi, eax
0x18002e024  test    eax, eax
0x18002e026  jns     short loc_18002E036
0x18002e028  lea     rcx, [rbp+57h+var_A8]
0x18002e02c  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002e031  jmp     loc_18002E1E0
0x18002e036  mov     rcx, [rbp+57h+var_A8]
0x18002e03a  call    _CheckBleDeviceProtectionLevel
0x18002e03f  mov     edi, eax
0x18002e041  lea     rcx, [rbp+57h+var_A8]
0x18002e045  test    eax, eax
0x18002e047  js      short loc_18002E02C
0x18002e049  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002e04e  mov     r14d, esi
0x18002e051  cmp     dword ptr [rbp+57h+var_B0], esi
0x18002e054  jbe     loc_18002E1E0
0x18002e05a  mov     [rbp+57h+var_A8], rsi
0x18002e05e  mov     [rbp+57h+var_A0], si
0x18002e062  mov     rcx, [rbp+57h+var_88]
0x18002e066  mov     rax, [rcx]
0x18002e069  lea     r8, [rbp+57h+var_A8]
0x18002e06d  mov     edx, r14d
0x18002e070  mov     rax, [rax+30h]
0x18002e074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e079  mov     edi, eax
0x18002e07b  mov     rcx, [rbp+57h+var_A8]
0x18002e07f  test    rcx, rcx
0x18002e082  jnz     short loc_18002E089
0x18002e084  jmp     loc_18002E188
0x18002e089  mov     rax, [rcx]
0x18002e08c  lea     rdx, [rbp+57h+var_A0]
0x18002e090  mov     rax, [rax+50h]
0x18002e094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e099  xor     edx, edx; length
0x18002e09b  mov     rcx, [rbp+57h+string]; string
0x18002e09f  call    cs:__imp_WindowsGetStringRawBuffer
  ... truncated ...
```
