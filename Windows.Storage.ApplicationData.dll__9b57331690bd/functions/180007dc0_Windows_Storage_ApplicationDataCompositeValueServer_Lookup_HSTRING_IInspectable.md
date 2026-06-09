# Windows::Storage::ApplicationDataCompositeValueServer::Lookup(HSTRING__ *,IInspectable * *)

- ea: `0x180007dc0`
- end: `0x180007f91`
- name: `?Lookup@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `465`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, HSTRING__ *key, IInspectable **value)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180007dc0`
- `0x1800092d0`
- `0x180009778`
- `0x180009ea8`
- `0x180021fc4`
- `0x180025004`
- `0x180034a3c`
- `0x180034a88`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007f16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007f59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007f16`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180007f59`

## string_xrefs

- `0x180007f20`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x180007f63`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Lookup(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        HSTRING__ *key,
        IInspectable **value)
{
  __int64 v4; // rax
  HRESULT v5; // eax
  __int64 v6; // rcx
  HRESULT v7; // edi
  IInspectable **propertyValue; // rax
  int PropertyValueFromSettingData; // eax
  unsigned int v11; // esi
  unsigned int v12; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned int v14; // ebx
  PCWSTR v15; // rax
  unsigned int *v16; // [rsp+30h] [rbp-79h]
  unsigned int returnEmptyPropertyValue; // [rsp+50h] [rbp-59h] BYREF
  unsigned int settingValueBytesRequired; // [rsp+54h] [rbp-55h] BYREF
  unsigned int settingValueFastBufferSize; // [rsp+58h] [rbp-51h] BYREF
  tag_STATE_VALUE_TYPE apisetValueType[25]; // [rsp+5Ch] [rbp-4Dh] BYREF
  Windows::Storage::ApplicationDataCompositeValueServer _This_88; // [rsp+C0h] [rbp+17h] BYREF
  void *retaddr; // [rsp+108h] [rbp+5Fh]

  *(_QWORD *)&apisetValueType[5] = key;
  *(_QWORD *)&apisetValueType[3] = value;
  apisetValueType[0] = STATE_VALUE_UNDEFINED;
  settingValueBytesRequired = 0;
  settingValueFastBufferSize = 32;
  *(_QWORD *)&apisetValueType[1] = 0;
  LOBYTE(returnEmptyPropertyValue) = 0;
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LOOKUP_START);
  lambda_852c15b476940bbd06823789b55330c4_::_lambda_852c15b476940bbd06823789b55330c4_(
    (IInspectable ***)&apisetValueType[7],
    (Windows::Storage::ApplicationDataCompositeValueServer *)&apisetValueType[3],
    (HSTRING__ **)this,
    &apisetValueType[5],
    (bool *)apisetValueType,
    &returnEmptyPropertyValue,
    &settingValueBytesRequired,
    (unsigned __int8 **)&settingValueFastBufferSize,
    (unsigned __int8 (*)[32])&apisetValueType[1]);
  v5 = lambda_852c15b476940bbd06823789b55330c4_::operator()(v4);
  v6 = *(_QWORD *)&apisetValueType[1];
  v7 = v5;
  if ( *(Windows::Storage::ApplicationDataCompositeValueServer **)&apisetValueType[1] != &_This_88
    && *(_QWORD *)&apisetValueType[1] )
  {
    operator delete(*(void **)&apisetValueType[1]);
    *(_QWORD *)&apisetValueType[1] = 0;
  }
  if ( !(_BYTE)returnEmptyPropertyValue )
    goto LABEL_3;
  if ( v7 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
  propertyValue = *(IInspectable ***)&apisetValueType[3];
  if ( **(_QWORD **)&apisetValueType[3] )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    propertyValue = *(IInspectable ***)&apisetValueType[3];
  }
  PropertyValueFromSettingData = Windows::Storage::StateABIHelpers::CreatePropertyValueFromSettingData(
                                   0,
                                   0,
                                   STATE_VALUE_UNDEFINED,
                                   &this->propertyValueStaticInterface,
                                   propertyValue);
  v11 = PropertyValueFromSettingData;
  if ( PropertyValueFromSettingData < 0 )
  {
    Windows::Storage::StateABIHelpers::ReportError(PropertyValueFromSettingData, 0x72u);
    v12 = settingValueBytesRequired;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&apisetValueType[5], 0);
    LODWORD(v16) = v12;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xF6u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      v11,
      "Key %ws size %u",
      StringRawBuffer,
      v16);
    return v11;
  }
  else
  {
LABEL_3:
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LOOKUP_STOP);
    if ( v7 < 0 )
    {
      v14 = settingValueBytesRequired;
      v15 = WindowsGetStringRawBuffer(*(HSTRING *)&apisetValueType[5], 0);
      LODWORD(v16) = v14;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0xFBu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        v7,
        "Key %ws size %u",
        v15,
        v16);
    }
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180007dc0  mov     [rsp-8+arg_18], rbx
0x180007dc5  push    rbp
0x180007dc6  push    rsi
0x180007dc7  push    rdi
0x180007dc8  lea     rbp, [rsp-47h]
0x180007dcd  sub     rsp, 0F0h
0x180007dd4  mov     rax, cs:__security_cookie
0x180007ddb  xor     rax, rsp
0x180007dde  mov     qword ptr [rbp+57h+_This.dataChangedSignaler.targetsPointerLock_.SRWLock_.___u0], rax
0x180007de2  mov     rbx, this
0x180007de5  mov     [rbp+57h+_This.Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>.__vftable], key
0x180007de9  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LOOKUP_START; eventDescriptor
0x180007df0  mov     [rbp+57h+_This.__vftable], value
0x180007df4  mov     [rbp+57h+apisetValueType], 0
0x180007dfb  mov     [rbp+57h+settingValueBytesRequired], 0
0x180007e02  mov     [rbp+57h+settingValueFastBufferSize], 20h ; ' '
0x180007e09  mov     [rbp+57h+settingValue], 0
0x180007e11  mov     byte ptr [rbp+57h+returnEmptyPropertyValue], 0
0x180007e15  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180007e1a  lea     rax, [rbp+57h+_This.refCount_]
0x180007e1e  mov     value, rbx; <key>
0x180007e21  mov     [rsp+100h+var_B8], rax
0x180007e26  lea     r9, [rbp+57h+_This.Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>]; <apisetValueType>
0x180007e2a  lea     rax, [rbp+57h+settingValue]
0x180007e2e  mov     [rsp+100h+var_C0], rax; <settingValueFastBuffer>
0x180007e33  lea     key, [rbp+57h+_This]; _This
0x180007e37  lea     rax, [rbp+57h+settingValueFastBufferSize]
0x180007e3b  mov     [rsp+100h+var_C8], rax; <settingValue>
0x180007e40  lea     this, [rbp+57h+_This.Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>.Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>]; <value>
0x180007e44  lea     rax, [rbp+57h+settingValueBytesRequired]
0x180007e48  mov     [rsp+100h+var_D0], rax; <settingValueFastBufferSize>
0x180007e4d  lea     rax, [rbp+57h+returnEmptyPropertyValue]
0x180007e51  mov     [rsp+100h+var_D8], rax; <settingValueBytesRequired>
0x180007e56  lea     rax, [rbp+57h+apisetValueType]
0x180007e5a  mov     [rsp+100h+propertyValue], rax; <returnEmptyPropertyValue>
0x180007e5f  call    _lambda_852c15b476940bbd06823789b55330c4____lambda_852c15b476940bbd06823789b55330c4_
0x180007e64  mov     this, rax
0x180007e67  call    _lambda_852c15b476940bbd06823789b55330c4___operator__
0x180007e6c  mov     this, [rbp+57h+settingValue]; p
0x180007e70  mov     edi, eax
0x180007e72  lea     rax, [rbp+57h+_This.refCount_]
0x180007e76  cmp     this, rax
0x180007e79  jnz     short loc_180007EB6
0x180007e7b  cmp     byte ptr [rbp+57h+returnEmptyPropertyValue], 0
0x180007e7f  jnz     short loc_180007ECA
0x180007e81  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_LOOKUP_STOP; eventDescriptor
0x180007e88  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180007e8d  test    edi, edi
0x180007e8f  js      loc_180007F50
0x180007e95  mov     eax, edi
0x180007e97  mov     this, qword ptr [rbp+57h+_This.dataChangedSignaler.targetsPointerLock_.SRWLock_.___u0]
0x180007e9b  xor     this, rsp; StackCookie
0x180007e9e  call    __security_check_cookie
0x180007ea3  mov     rbx, [rsp+100h+arg_18]
0x180007eab  add     rsp, 0F0h
0x180007eb2  pop     rdi
0x180007eb3  pop     rsi
0x180007eb4  pop     rbp
0x180007eb5  retn
0x180007eb6  test    this, this
0x180007eb9  jz      short loc_180007E7B
0x180007ebb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007ec0  mov     [rbp+57h+settingValue], 0
0x180007ec8  jmp     short loc_180007E7B
0x180007eca  test    edi, edi
0x180007ecc  jns     short loc_180007ED3
0x180007ece  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "SUCCEEDED(hrLookup)")
0x180007ed3  mov     rax, [rbp+57h+_This.__vftable]
0x180007ed7  cmp     qword ptr [rax], 0
0x180007edb  jz      short loc_180007EE6
0x180007edd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "*value == nullptr")
0x180007ee2  mov     rax, [rbp+57h+_This.__vftable]
0x180007ee6  lea     r9, [rbx+68h]; propertyValueStaticInterface
0x180007eea  mov     [rsp+100h+propertyValue], rax; propertyValue
0x180007eef  xor     r8d, r8d; valueType
0x180007ef2  xor     edx, edx; valueBufferBytes
0x180007ef4  xor     ecx, ecx; valueBuffer
0x180007ef6  call    ?CreatePropertyValueFromSettingData@StateABIHelpers@Storage@Windows@@YAJPEBEIW4tag_STATE_VALUE_TYPE@@AEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::CreatePropertyValueFromSettingData(uchar const *,uint,tag_STATE_VALUE_TYPE,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x180007efb  mov     esi, eax
0x180007efd  test    eax, eax
0x180007eff  jns     short loc_180007E81
0x180007f01  mov     edx, 72h ; 'r'; idsValue
0x180007f06  mov     ecx, eax; hr
0x180007f08  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180007f0d  mov     this, [rbp+57h+_This.Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>.__vftable]; string
0x180007f11  xor     edx, edx; length
0x180007f13  mov     ebx, [rbp+57h+settingValueBytesRequired]
0x180007f16  call    cs:__imp_WindowsGetStringRawBuffer
0x180007f1c  mov     this, [rbp+5Fh]; callerReturnAddress
0x180007f20  lea     value, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x180007f27  mov     dword ptr [rsp+100h+var_D0], ebx
0x180007f2b  mov     r9d, esi; hr
0x180007f2e  mov     [rsp+100h+var_D8], rax
0x180007f33  mov     edx, 0F6h; lineNumber
0x180007f38  lea     rax, aKeyWsSizeU; "Key %ws size %u"
0x180007f3f  mov     [rsp+100h+propertyValue], rax; formatString
0x180007f44  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007f49  mov     eax, esi
0x180007f4b  jmp     loc_180007E97
0x180007f50  mov     this, [rbp+57h+_This.Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,IInspectable *> *>,Windows::Foundation::Collections::IObservableMap<HSTRING__ *,IInspectable *>,Windows::Foundation::Collections::IPropertySet,Windows::Storage::Private::IApplicationDataCompositeValueInternal,Microsoft::WRL::FtmBase>.__vftable]; string
0x180007f54  xor     edx, edx; length
0x180007f56  mov     ebx, [rbp+57h+settingValueBytesRequired]
0x180007f59  call    cs:__imp_WindowsGetStringRawBuffer
0x180007f5f  mov     this, [rbp+5Fh]; callerReturnAddress
0x180007f63  lea     value, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x180007f6a  mov     dword ptr [rsp+100h+var_D0], ebx
0x180007f6e  mov     r9d, edi; hr
0x180007f71  mov     [rsp+100h+var_D8], rax
0x180007f76  mov     edx, 0FBh; lineNumber
0x180007f7b  lea     rax, aKeyWsSizeU; "Key %ws size %u"
0x180007f82  mov     [rsp+100h+propertyValue], rax; formatString
0x180007f87  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007f8c  jmp     loc_180007E95
```
