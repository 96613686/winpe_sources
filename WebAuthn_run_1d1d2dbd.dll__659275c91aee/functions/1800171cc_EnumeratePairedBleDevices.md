# _EnumeratePairedBleDevices

- ea: `0x1800171cc`
- end: `0x18001756c`
- name: `_EnumeratePairedBleDevices`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800fb8fc`

## callees

- `0x1800171cc`
- `0x18002bbc8`
- `0x18002bbf4`
- `0x180044900`
- `0x1800f2594`
- `0x1800f2650`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017457`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180017457`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017225`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017225`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001727d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800172db`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001727d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800172db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001749c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001749c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800172c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017269`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800172c7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001729f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800172fd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001729f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800172fd`

## string_xrefs

- `0x180017262`: `Windows.Devices.Bluetooth.GenericAttributeProfile.GattDeviceService`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall EnumeratePairedBleDevices(_QWORD *a1)
{
  int NonzeroLastError; // eax
  signed int ActivationFactory; // ebx
  HRESULT v3; // eax
  HSTRING v4; // rbx
  HRESULT v5; // eax
  HSTRING v6; // rbx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, PVOID, __int64 *); // rsi
  PVOID *v9; // rax
  PVOID v10; // rdi
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, PVOID, __int64 *); // rsi
  PVOID *v13; // rax
  PVOID v14; // rdi
  signed int v15; // eax
  signed int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // [rsp+28h] [rbp-29h] BYREF
  __int64 v22; // [rsp+30h] [rbp-21h] BYREF
  __int64 v23; // [rsp+38h] [rbp-19h] BYREF
  __int64 v24; // [rsp+40h] [rbp-11h] BYREF
  HANDLE hHandle; // [rsp+48h] [rbp-9h] BYREF
  HSTRING v26; // [rsp+50h] [rbp-1h] BYREF
  __int64 v27; // [rsp+58h] [rbp+7h] BYREF
  __int64 v28; // [rsp+60h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+17h] BYREF
  HSTRING string; // [rsp+80h] [rbp+2Fh] BYREF
  _QWORD *v31; // [rsp+B8h] [rbp+67h] BYREF

  v31 = a1;
  v23 = 0;
  v22 = 0;
  v21 = 0;
  v27 = 0;
  v28 = 0;
  v26 = 0;
  hHandle = CreateEventW(0, 1, 0, 0);
  if ( !hHandle )
  {
    NonzeroLastError = _GetNonzeroLastError();
    ActivationFactory = NonzeroLastError;
    if ( NonzeroLastError > 0 )
      ActivationFactory = (unsigned __int16)NonzeroLastError | 0x80070000;
LABEL_29:
    if ( ActivationFactory >= 0 )
      goto LABEL_32;
    goto LABEL_30;
  }
  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Devices.Bluetooth.GenericAttributeProfile.GattDeviceService",
         0x43u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v4 = string;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v23);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_196d0022_faad_45dc_ae5b_2ac3184e84db, &v23);
  if ( ActivationFactory >= 0 )
  {
    string = 0;
    v5 = WindowsCreateStringReference(L"Windows.Devices.Enumeration.DeviceInformation", 0x2Du, &hstringHeader, &string);
    if ( v5 < 0 )
    {
      RaiseException(v5, 1u, 0, 0);
      __debugbreak();
    }
    v6 = string;
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v22);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v22);
    if ( ActivationFactory >= 0 )
    {
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = xmmword_18014FEE0;
      ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *, HSTRING *))(*(_QWORD *)v23 + 56LL))(
                            v23,
                            &hstringHeader,
                            &v26);
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v22 + 112LL))(
                              v22,
                              v26,
                              &v21);
        if ( ActivationFactory >= 0 )
        {
          v7 = v21;
          v8 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v21 + 96LL);
          hstringHeader.Reserved.Reserved1 = &hHandle;
          v9 = (PVOID *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Enumeration::DeviceWatcher___Windows::Devices::Enumeration::IDeviceWatcher____IInspectable___::___Windows::Devices::Enumeration::IDeviceWatcher___IInspectable____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::Devices::Enumeration::DeviceWatcher___IInspectable______EnumeratePairedBleDevices_::_2_::_lambda_1___1_Windows::Devices::Enumeration::IDeviceWatcher___IInspectable______EnumeratePairedBleDevices_::_2_::_lambda_1___(
                          &v24,
                          &hstringHeader);
          v10 = *v9;
          hstringHeader.Reserved.Reserved1 = *v9;
          *v9 = 0;
          if ( v24 )
          {
            v24 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release();
          }
          ActivationFactory = v8(v7, v10, &v28);
          if ( v10 )
            (*(void (__fastcall **)(PVOID))(*(_QWORD *)v10 + 16LL))(v10);
          if ( ActivationFactory >= 0 )
          {
            v11 = v21;
            v12 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v21 + 48LL);
            hstringHeader.Reserved.Reserved1 = &v31;
            v13 = (PVOID *)Microsoft::WRL::Details::Make_Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Devices::Enumeration::DeviceWatcher___Windows::Devices::Enumeration::IDeviceWatcher____Windows::Foundation::Internal::AggregateType_Windows::Devices::Enumeration::DeviceInformation___Windows::Devices::Enumeration::IDeviceInformation_____::___Windows::Devices::Enumeration::IDeviceWatcher___Windows::Devices::Enumeration::IDeviceInformation____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::Devices::Enumeration::DeviceWatcher___Windows::Devices::Enumeration::DeviceInformation______EnumeratePairedBleDevices_::_2_::_lambda_2___1_Windows::Devices::Enumeration::IDeviceWatcher___Windows::Devices::Enumeration::IDeviceInformation______EnumeratePairedBleDevices_::_2_::_lambda_2___(
                             &v24,
                             &hstringHeader);
            v14 = *v13;
            hstringHeader.Reserved.Reserved1 = *v13;
            *v13 = 0;
            if ( v24 )
            {
              v24 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release();
            }
            ActivationFactory = v12(v11, v14, &v27);
            if ( v14 )
              (*(void (__fastcall **)(PVOID))(*(_QWORD *)v14 + 16LL))(v14);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 136LL))(v21);
              if ( ActivationFactory >= 0 )
              {
                v15 = WaitForSingleObject(hHandle, 0x1388u);
                if ( v15 )
                {
                  if ( v15 > 0 )
                    ActivationFactory = (unsigned __int16)v15 | 0x80070000;
                  else
                    ActivationFactory = v15;
                }
                v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 144LL))(v21);
                if ( ActivationFactory >= 0 )
                {
                  ActivationFactory = v16;
                  goto LABEL_29;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_30:
  if ( (_QWORD *)*v31 != v31 )
    ActivationFactory = 0;
LABEL_32:
  WindowsDeleteString(v26);
  v17 = v21;
  if ( v21 )
  {
    if ( v27 )
    {
      (*(void (**)(void))(*(_QWORD *)v21 + 56LL))();
      v17 = v21;
    }
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 104LL))(v17);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v21);
    v17 = v21;
  }
  if ( hHandle )
  {
    CloseHandle(hHandle);
    v17 = v21;
  }
  if ( v17 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v23;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800171cc  mov     rax, rsp
0x1800171cf  mov     [rax+10h], rbx
0x1800171d3  mov     [rax+18h], rsi
0x1800171d7  mov     [rax+8], rcx
0x1800171db  push    rbp
0x1800171dc  push    rdi
0x1800171dd  push    r14
0x1800171df  lea     rbp, [rax-5Fh]
0x1800171e3  sub     rsp, 90h
0x1800171ea  mov     rax, cs:__security_cookie
0x1800171f1  xor     rax, rsp
0x1800171f4  mov     [rbp+57h+var_20], rax
0x1800171f8  xor     r14d, r14d
0x1800171fb  mov     [rbp+57h+var_70], r14
0x1800171ff  mov     [rbp+57h+var_78], r14
0x180017203  mov     [rbp+57h+var_80], r14
0x180017207  mov     [rbp+57h+var_50], r14
0x18001720b  mov     [rbp+57h+var_48], r14
0x18001720f  mov     [rbp+57h+hHandle], r14
0x180017213  mov     [rbp+57h+var_58], r14
0x180017217  xor     r9d, r9d; lpName
0x18001721a  xor     r8d, r8d; bInitialState
0x18001721d  lea     edi, [r14+1]
0x180017221  mov     edx, edi; bManualReset
0x180017223  xor     ecx, ecx; lpEventAttributes
0x180017225  call    cs:__imp_CreateEventW
0x18001722b  mov     [rbp+57h+hHandle], rax
0x18001722f  test    rax, rax
0x180017232  jnz     short loc_180017251
0x180017234  call    ?_GetNonzeroLastError@@YAKXZ; _GetNonzeroLastError(void)
0x180017239  mov     ebx, eax
0x18001723b  test    eax, eax
0x18001723d  jle     loc_180017489
0x180017243  movzx   ebx, ax
0x180017246  or      ebx, 80070000h
0x18001724c  jmp     loc_180017489
0x180017251  mov     [rbp+57h+string], r14
0x180017255  lea     r9, [rbp+57h+string]; string
0x180017259  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001725d  mov     edx, 43h ; 'C'; length
0x180017262  lea     rcx, ?RuntimeClass_Windows_Devices_Bluetooth_GenericAttributeProfile_GattDeviceService@@3QBGB; "Windows.Devices.Bluetooth.GenericAttrib"...
0x180017269  call    cs:__imp_WindowsCreateStringReference
0x18001726f  test    eax, eax
0x180017271  jns     short loc_180017284
0x180017273  xor     r9d, r9d; lpArguments
0x180017276  xor     r8d, r8d; nNumberOfArguments
0x180017279  mov     edx, edi; dwExceptionFlags
0x18001727b  mov     ecx, eax; dwExceptionCode
0x18001727d  call    cs:__imp_RaiseException
0x180017283  int     3; Trap to Debugger
0x180017284  mov     rbx, [rbp+57h+string]
0x180017288  lea     rcx, [rbp+57h+var_70]
0x18001728c  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x180017291  lea     r8, [rbp+57h+var_70]
0x180017295  lea     rdx, _GUID_196d0022_faad_45dc_ae5b_2ac3184e84db
0x18001729c  mov     rcx, rbx
0x18001729f  call    cs:__imp_RoGetActivationFactory
0x1800172a5  mov     ebx, eax
0x1800172a7  test    eax, eax
0x1800172a9  js      loc_18001748D
0x1800172af  mov     [rbp+57h+string], r14
0x1800172b3  lea     r9, [rbp+57h+string]; string
0x1800172b7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800172bb  mov     edx, 2Dh ; '-'; length
0x1800172c0  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x1800172c7  call    cs:__imp_WindowsCreateStringReference
0x1800172cd  test    eax, eax
0x1800172cf  jns     short loc_1800172E2
0x1800172d1  xor     r9d, r9d; lpArguments
0x1800172d4  xor     r8d, r8d; nNumberOfArguments
0x1800172d7  mov     edx, edi; dwExceptionFlags
0x1800172d9  mov     ecx, eax; dwExceptionCode
0x1800172db  call    cs:__imp_RaiseException
0x1800172e1  int     3; Trap to Debugger
0x1800172e2  mov     rbx, [rbp+57h+string]
0x1800172e6  lea     rcx, [rbp+57h+var_78]
0x1800172ea  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800172ef  lea     r8, [rbp+57h+var_78]
0x1800172f3  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x1800172fa  mov     rcx, rbx
0x1800172fd  call    cs:__imp_RoGetActivationFactory
0x180017303  mov     ebx, eax
0x180017305  test    eax, eax
0x180017307  js      loc_18001748D
0x18001730d  mov     rcx, [rbp+57h+var_70]
0x180017311  movups  xmm0, cs:xmmword_18014FEE0
0x180017318  movdqu  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x18001731d  mov     rax, [rcx]
0x180017320  lea     r8, [rbp+57h+var_58]
0x180017324  lea     rdx, [rbp+57h+hstringHeader]
0x180017328  mov     rax, [rax+38h]
0x18001732c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017331  mov     ebx, eax
0x180017333  test    eax, eax
0x180017335  js      loc_18001748D
0x18001733b  mov     rcx, [rbp+57h+var_78]
0x18001733f  mov     rax, [rcx]
0x180017342  lea     r8, [rbp+57h+var_80]
0x180017346  mov     rdx, [rbp+57h+var_58]
0x18001734a  mov     rax, [rax+70h]
0x18001734e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017353  mov     ebx, eax
0x180017355  test    eax, eax
0x180017357  js      loc_18001748D
0x18001735d  mov     rbx, [rbp+57h+var_80]
0x180017361  mov     rax, [rbx]
0x180017364  mov     rsi, [rax+60h]
0x180017368  lea     rax, [rbp+57h+hHandle]
0x18001736c  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x180017370  lea     rdx, [rbp+57h+hstringHeader]
0x180017374  lea     rcx, [rbp+57h+var_68]
0x180017378  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Devices__Enumeration__DeviceWatcher___Windows__Devices__Enumeration__IDeviceWatcher____IInspectable________Windows__Devices__Enumeration__IDeviceWatcher___IInspectable______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__Devices__Enumeration__DeviceWatcher___IInspectable______EnumeratePairedBleDevices____2____lambda_1___1_Windows__Devices__Enumeration__IDeviceWatcher___IInspectable______EnumeratePairedBleDevices____2____lambda_1___
0x18001737d  mov     rdi, [rax]
0x180017380  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdi
0x180017384  mov     [rax], r14
0x180017387  mov     rcx, [rbp+57h+var_68]
0x18001738b  test    rcx, rcx
0x18001738e  jz      short loc_18001739A
0x180017390  mov     [rbp+57h+var_68], r14
0x180017394  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWTSListenerCallback@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release(void)
0x180017399  nop
0x18001739a  lea     r8, [rbp+57h+var_48]
0x18001739e  mov     rdx, rdi
0x1800173a1  mov     rcx, rbx
0x1800173a4  mov     rax, rsi
0x1800173a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173ac  mov     ebx, eax
0x1800173ae  test    rdi, rdi
0x1800173b1  jz      short loc_1800173C3
0x1800173b3  mov     rax, [rdi]
0x1800173b6  mov     rcx, rdi
0x1800173b9  mov     rax, [rax+10h]
0x1800173bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173c2  nop
0x1800173c3  test    ebx, ebx
0x1800173c5  js      loc_18001748D
0x1800173cb  mov     rbx, [rbp+57h+var_80]
0x1800173cf  mov     rax, [rbx]
0x1800173d2  mov     rsi, [rax+30h]
0x1800173d6  lea     rax, [rbp+57h+arg_0]
0x1800173da  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800173de  lea     rdx, [rbp+57h+hstringHeader]
0x1800173e2  lea     rcx, [rbp+57h+var_68]
0x1800173e6  call    Microsoft__WRL__Details__Make_Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Devices__Enumeration__DeviceWatcher___Windows__Devices__Enumeration__IDeviceWatcher____Windows__Foundation__Internal__AggregateType_Windows__Devices__Enumeration__DeviceInformation___Windows__Devices__Enumeration__IDeviceInformation__________Windows__Devices__Enumeration__IDeviceWatcher___Windows__Devices__Enumeration__IDeviceInformation______DelegateInvokeHelper_Windows__Foundation__ITypedEventHandler_Windows__Devices__Enumeration__DeviceWatcher___Windows__Devices__Enumeration__DeviceInformation______EnumeratePairedBleDevices____2____lambda_2___1_Windows__Devices__Enumeration__IDeviceWatcher___Windows__Devices__Enumeration__IDeviceInformation______EnumeratePairedBleDevices____2____lambda_2___
0x1800173eb  mov     rdi, [rax]
0x1800173ee  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdi
0x1800173f2  mov     [rax], r14
0x1800173f5  mov     rcx, [rbp+57h+var_68]
0x1800173f9  test    rcx, rcx
0x1800173fc  jz      short loc_180017408
0x1800173fe  mov     [rbp+57h+var_68], r14
0x180017402  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWTSListenerCallback@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWTSListenerCallback>::Release(void)
0x180017407  nop
0x180017408  lea     r8, [rbp+57h+var_50]
0x18001740c  mov     rdx, rdi
0x18001740f  mov     rcx, rbx
0x180017412  mov     rax, rsi
0x180017415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001741a  mov     ebx, eax
0x18001741c  test    rdi, rdi
0x18001741f  jz      short loc_180017431
0x180017421  mov     rax, [rdi]
0x180017424  mov     rcx, rdi
0x180017427  mov     rax, [rax+10h]
0x18001742b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017430  nop
0x180017431  test    ebx, ebx
0x180017433  js      short loc_18001748D
0x180017435  mov     rcx, [rbp+57h+var_80]
0x180017439  mov     rax, [rcx]
0x18001743c  mov     rax, [rax+88h]
0x180017443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017448  mov     ebx, eax
0x18001744a  test    eax, eax
0x18001744c  js      short loc_18001748D
0x18001744e  mov     edx, 1388h; dwMilliseconds
0x180017453  mov     rcx, [rbp+57h+hHandle]; hHandle
0x180017457  call    cs:__imp_WaitForSingleObject
0x18001745d  test    eax, eax
0x18001745f  jz      short loc_180017470
0x180017461  jg      short loc_180017467
0x180017463  mov     ebx, eax
0x180017465  jmp     short loc_180017470
0x180017467  movzx   ebx, ax
0x18001746a  or      ebx, 80070000h
0x180017470  mov     rcx, [rbp+57h+var_80]
0x180017474  mov     rax, [rcx]
0x180017477  mov     rax, [rax+90h]
0x18001747e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017483  test    ebx, ebx
0x180017485  js      short loc_18001748D
0x180017487  mov     ebx, eax
0x180017489  test    ebx, ebx
0x18001748b  jns     short loc_180017498
0x18001748d  mov     rax, [rbp+57h+arg_0]
0x180017491  cmp     [rax], rax
0x180017494  cmovnz  ebx, r14d
0x180017498  mov     rcx, [rbp+57h+var_58]; string
0x18001749c  call    cs:__imp_WindowsDeleteString
0x1800174a2  mov     rcx, [rbp+57h+var_80]
0x1800174a6  test    rcx, rcx
0x1800174a9  jz      short loc_1800174E6
0x1800174ab  mov     rdx, [rbp+57h+var_50]
0x1800174af  test    rdx, rdx
0x1800174b2  jz      short loc_1800174C4
0x1800174b4  mov     rax, [rcx]
0x1800174b7  mov     rax, [rax+38h]
0x1800174bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c0  mov     rcx, [rbp+57h+var_80]
0x1800174c4  mov     rdx, [rbp+57h+var_48]
0x1800174c8  test    rdx, rdx
0x1800174cb  jz      short loc_1800174D9
0x1800174cd  mov     rax, [rcx]
0x1800174d0  mov     rax, [rax+68h]
0x1800174d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174d9  lea     rcx, [rbp+57h+var_80]
0x1800174dd  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x1800174e2  mov     rcx, [rbp+57h+var_80]
0x1800174e6  mov     rax, [rbp+57h+hHandle]
0x1800174ea  test    rax, rax
0x1800174ed  jz      short loc_1800174FC
0x1800174ef  mov     rcx, rax; hObject
0x1800174f2  call    cs:__imp_CloseHandle
0x1800174f8  mov     rcx, [rbp+57h+var_80]
0x1800174fc  test    rcx, rcx
0x1800174ff  jz      short loc_180017512
0x180017501  mov     [rbp+57h+var_80], r14
0x180017505  mov     rax, [rcx]
0x180017508  mov     rax, [rax+10h]
0x18001750c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017511  nop
0x180017512  mov     rcx, [rbp+57h+var_78]
0x180017516  test    rcx, rcx
0x180017519  jz      short loc_18001752C
0x18001751b  mov     [rbp+57h+var_78], r14
0x18001751f  mov     rax, [rcx]
0x180017522  mov     rax, [rax+10h]
0x180017526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001752b  nop
0x18001752c  mov     rcx, [rbp+57h+var_70]
0x180017530  test    rcx, rcx
0x180017533  jz      short loc_180017546
0x180017535  mov     [rbp+57h+var_70], r14
0x180017539  mov     rax, [rcx]
0x18001753c  mov     rax, [rax+10h]
0x180017540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017545  nop
0x180017546  mov     eax, ebx
0x180017548  mov     rcx, [rbp+57h+var_20]
0x18001754c  xor     rcx, rsp; StackCookie
0x18001754f  call    __security_check_cookie
0x180017554  lea     r11, [rsp+0A0h+var_10]
0x18001755c  mov     rbx, [r11+28h]
0x180017560  mov     rsi, [r11+30h]
0x180017564  mov     rsp, r11
0x180017567  pop     r14
0x180017569  pop     rdi
0x18001756a  pop     rbp
0x18001756b  retn
```
