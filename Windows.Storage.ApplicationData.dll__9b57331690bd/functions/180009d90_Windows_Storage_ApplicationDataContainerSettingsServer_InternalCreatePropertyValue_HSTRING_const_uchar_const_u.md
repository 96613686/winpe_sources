# Windows::Storage::ApplicationDataContainerSettingsServer::InternalCreatePropertyValue(HSTRING__ * const &,uchar const *,uint,tag_STATE_VALUE_TYPE,IInspectable * *)

- ea: `0x180009d90`
- end: `0x180009ea1`
- name: `?InternalCreatePropertyValue@ApplicationDataContainerSettingsServer@Storage@Windows@@EEAAJAEBQEAUHSTRING__@@PEBEIW4tag_STATE_VALUE_TYPE@@PEAPEAUIInspectable@@@Z`
- size: `273`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerSettingsServer *this, HSTRING__ *const *key, const unsigned __int8 *valueBuffer, const unsigned int valueBufferBytes, const tag_STATE_VALUE_TYPE valueType, IInspectable **propertyValue)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x180009d90`
- `0x180009ea8`
- `0x180022648`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009e64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009e64`

## string_xrefs

- `0x180009e29`: `InternalLookupCompositeValue %ws %u`
- `0x180009e8b`: `CreatePropertyValueFromSettingData %ws %u %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerSettingsServer::InternalCreatePropertyValue(
        Windows::Storage::ApplicationDataContainerSettingsServer *this,
        HSTRING__ *const *key,
        const unsigned __int8 *valueBuffer,
        unsigned int valueBufferBytes,
        tag_STATE_VALUE_TYPE valueType,
        IInspectable **propertyValue)
{
  int PropertyValueFromSettingData; // eax
  int v9; // ebx
  PCWSTR StringRawBuffer; // rax
  Windows::Storage::ApplicationDataCompositeValueServer *v12; // rcx
  PCWSTR v13; // rax
  void *retaddr; // [rsp+48h] [rbp+0h]

  if ( valueType == STATE_VALUE_ATOM )
  {
    v9 = this->InternalLookupCompositeValue(this, key, propertyValue);
    if ( v9 < 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*key, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x26Fu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
        v9,
        "InternalLookupCompositeValue %ws %u",
        StringRawBuffer,
        valueBufferBytes);
    }
  }
  else
  {
    PropertyValueFromSettingData = Windows::Storage::StateABIHelpers::CreatePropertyValueFromSettingData(
                                     valueBuffer,
                                     valueBufferBytes,
                                     valueType,
                                     &this->m_propertyValueStaticInterface,
                                     propertyValue);
    v9 = PropertyValueFromSettingData;
    if ( PropertyValueFromSettingData >= 0 )
      return 0;
    Windows::Storage::StateABIHelpers::ReportError(PropertyValueFromSettingData, 0x72u);
    if ( v9 != -2147024809 && v9 != -2147024882 )
      Windows::Storage::ApplicationDataContainerSettingsServer::SqmReadSettingError(v12, v9);
    v13 = WindowsGetStringRawBuffer(*key, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x284u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
      v9,
      "CreatePropertyValueFromSettingData %ws %u %u",
      v13,
      valueBufferBytes,
      valueBufferBytes);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009d90  mov     [rsp+arg_0], rbx
0x180009d95  mov     [rsp+arg_8], rsi
0x180009d9a  push    rdi
0x180009d9b  sub     rsp, 40h
0x180009d9f  mov     r10, valueBuffer
0x180009da2  mov     edi, valueBufferBytes
0x180009da5  mov     r8d, [rsp+48h+arg_20]; valueType
0x180009daa  mov     rsi, key
0x180009dad  cmp     r8d, 0Dh
0x180009db1  jz      short loc_180009DE3
0x180009db3  mov     rax, [rsp+48h+arg_28]
0x180009db8  lea     r9, [this+68h]; propertyValueStaticInterface
0x180009dbc  mov     this, r10; valueBuffer
0x180009dbf  mov     [rsp+48h+var_28], rax; propertyValue
0x180009dc4  mov     edx, edi; valueBufferBytes
0x180009dc6  call    ?CreatePropertyValueFromSettingData@StateABIHelpers@Storage@Windows@@YAJPEBEIW4tag_STATE_VALUE_TYPE@@AEAV?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@PEAPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::CreatePropertyValueFromSettingData(uchar const *,uint,tag_STATE_VALUE_TYPE,Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics> &,IInspectable * *)
0x180009dcb  mov     ebx, eax
0x180009dcd  test    eax, eax
0x180009dcf  js      short loc_180009E3C
0x180009dd1  xor     eax, eax
0x180009dd3  mov     rbx, [rsp+48h+arg_0]
0x180009dd8  mov     rsi, [rsp+48h+arg_8]
0x180009ddd  add     rsp, 40h
0x180009de1  pop     rdi
0x180009de2  retn
0x180009de3  mov     rax, [this]
0x180009de6  mov     valueBuffer, [rsp+48h+arg_28]
0x180009deb  mov     rax, [rax+80h]
0x180009df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df7  mov     ebx, eax
0x180009df9  test    eax, eax
0x180009dfb  js      short loc_180009E01
0x180009dfd  mov     eax, ebx
0x180009dff  jmp     short loc_180009DD3
0x180009e01  mov     this, [rsi]; string
0x180009e04  xor     edx, edx; length
0x180009e06  call    cs:__imp_WindowsGetStringRawBuffer
0x180009e0c  mov     this, [rsp+48h]; callerReturnAddress
0x180009e11  lea     valueBuffer, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009e18  mov     [rsp+48h+var_18], edi
0x180009e1c  mov     valueBufferBytes, ebx; hr
0x180009e1f  mov     [rsp+48h+var_20], rax
0x180009e24  mov     edx, 26Fh; lineNumber
0x180009e29  lea     rax, aInternallookup; "InternalLookupCompositeValue %ws %u"
0x180009e30  mov     [rsp+48h+var_28], rax; formatString
0x180009e35  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009e3a  jmp     short loc_180009DFD
0x180009e3c  mov     edx, 72h ; 'r'; idsValue
0x180009e41  mov     ecx, ebx; hr
0x180009e43  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180009e48  cmp     ebx, 80070057h
0x180009e4e  jz      short loc_180009E5F
0x180009e50  cmp     ebx, 8007000Eh
0x180009e56  jz      short loc_180009E5F
0x180009e58  mov     edx, ebx; hr
0x180009e5a  call    ?SqmReadSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmReadSettingError(long)
0x180009e5f  mov     this, [rsi]; string
0x180009e62  xor     edx, edx; length
0x180009e64  call    cs:__imp_WindowsGetStringRawBuffer
0x180009e6a  mov     this, [rsp+48h]; callerReturnAddress
0x180009e6f  lea     valueBuffer, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009e76  mov     [rsp+48h+var_10], edi
0x180009e7a  mov     valueBufferBytes, ebx; hr
0x180009e7d  mov     [rsp+48h+var_18], edi
0x180009e81  mov     edx, 284h; lineNumber
0x180009e86  mov     [rsp+48h+var_20], rax
0x180009e8b  lea     rax, aCreateproperty_3; "CreatePropertyValueFromSettingData %ws "...
0x180009e92  mov     [rsp+48h+var_28], rax; formatString
0x180009e97  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009e9c  jmp     loc_180009DFD
```
