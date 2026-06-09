# _lambda_a1b54a0e0d0c543c67e756a16c399ea7_::operator()

- ea: `0x180036abc`
- end: `0x180036c94`
- name: `_lambda_a1b54a0e0d0c543c67e756a16c399ea7_::operator()`
- size: `472`
- prototype: `HRESULT __fastcall()`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e2d0`

## callees

- `0x18000275c`
- `0x180005ee0`
- `0x1800093d0`
- `0x180009778`
- `0x1800134f0`
- `0x180013b54`
- `0x180019bf4`
- `0x18001ca9c`
- `0x180029d20`
- `0x180029df0`
- `0x180036abc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036b62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036b62`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x180036b72`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x180036b72`

## string_xrefs

- `0x180036b2b`: `OpenStateExplicit 0x%0x`
- `0x180036bc4`: `OpenStateExplicit`

## pseudocode

```c
__int64 __fastcall lambda_a1b54a0e0d0c543c67e756a16c399ea7_::operator()(Windows::Internal::String **a1)
{
  Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *v1; // rbx
  signed int LastError; // eax
  Windows::System::IUser *v4; // r8
  int PropertyValueStaticInterface; // ebx
  int v6; // esi
  wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > *v8; // rbx
  PCWSTR StringRawBuffer; // rax
  void *v10; // rax
  signed int v11; // eax
  Windows::Storage::ApplicationDataServer *v12; // rdi
  void *retaddr; // [rsp+38h] [rbp+0h]

  v1 = (Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)*a1;
  if ( !(*a1)[11]._hstring )
  {
    LastError = GetLastError();
    PropertyValueStaticInterface = LastError;
    if ( LastError > 0 )
      PropertyValueStaticInterface = (unsigned __int16)LastError | 0x80070000;
    v6 = Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(
           L"Current",
           PropertyValueStaticInterface,
           v4);
    if ( v6 < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        L"Current",
        PropertyValueStaticInterface,
        0);
      Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 2u);
      if ( PropertyValueStaticInterface < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0xE1u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
          PropertyValueStaticInterface,
          "OpenStateExplicit 0x%0x",
          v6);
      return (unsigned int)PropertyValueStaticInterface;
    }
    v8 = (wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > *)*a1;
    StringRawBuffer = WindowsGetStringRawBuffer(a1[2]->_hstring, 0);
    v10 = (void *)OpenStateExplicit(a1[1]->_hstring, StringRawBuffer);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      v8 + 11,
      v10);
    v1 = (Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)*a1;
    if ( !(*a1)[11]._hstring )
    {
      v11 = GetLastError();
      PropertyValueStaticInterface = v11;
      if ( v11 > 0 )
        PropertyValueStaticInterface = (unsigned __int16)v11 | 0x80070000;
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        L"Current",
        PropertyValueStaticInterface,
        0);
      Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 2u);
      if ( PropertyValueStaticInterface < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0xF2u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
          PropertyValueStaticInterface,
          "OpenStateExplicit");
      return (unsigned int)PropertyValueStaticInterface;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(v1 + 25);
  PropertyValueStaticInterface = Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface((Windows::Foundation::IPropertyValueStatics **)&v1[25]);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xF7u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "GetPropertyValueStaticInterface");
    return (unsigned int)PropertyValueStaticInterface;
  }
  PropertyValueStaticInterface = Windows::Internal::String::Initialize(*a1 + 12, &a1[2]->_hstring);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0xFAu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "Initialize");
    return (unsigned int)PropertyValueStaticInterface;
  }
  v12 = (Windows::Storage::ApplicationDataServer *)*a1;
  PropertyValueStaticInterface = Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(v12);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x101u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "InitializeDataChangedSignaler");
    Windows::Internal::String::Release(&v12->m_packageFamilyNameForFullTrustActivation);
    return (unsigned int)PropertyValueStaticInterface;
  }
  return 0;
}

```

## disassembly

```asm
0x180036abc  mov     [rsp+arg_0], rbx
0x180036ac1  mov     [rsp+arg_8], rsi
0x180036ac6  push    rdi
0x180036ac7  sub     rsp, 30h
0x180036acb  mov     rbx, [this]
0x180036ace  mov     rdi, this
0x180036ad1  cmp     qword ptr [rbx+58h], 0
0x180036ad6  jnz     loc_180036BEE
0x180036adc  call    cs:__imp_GetLastError
0x180036ae2  mov     ebx, eax
0x180036ae4  test    eax, eax
0x180036ae6  jle     short loc_180036AF1
0x180036ae8  movzx   ebx, ax
0x180036aeb  or      ebx, 80070000h
0x180036af1  mov     edx, ebx; inputHr
0x180036af3  lea     this, aCurrent; "Current"
0x180036afa  call    ?TriggerRepairStateLocationsIfNeeded@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180036aff  mov     esi, eax
0x180036b01  test    eax, eax
0x180036b03  jns     short loc_180036B56
0x180036b05  xor     r8d, r8d; userParam
0x180036b08  lea     this, aCurrent; "Current"
0x180036b0f  mov     edx, ebx; inputHr
0x180036b11  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180036b16  mov     edx, 2; idsValue
0x180036b1b  mov     ecx, ebx; hr
0x180036b1d  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180036b22  test    ebx, ebx
0x180036b24  jns     short loc_180036B4F
0x180036b26  mov     this, [rsp+38h]; callerReturnAddress
0x180036b2b  lea     rax, aOpenstateexpli_8; "OpenStateExplicit 0x%0x"
0x180036b32  mov     [rsp+38h+var_10], esi
0x180036b36  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180036b3d  mov     r9d, ebx; hr
0x180036b40  mov     [rsp+38h+formatString], rax; formatString
0x180036b45  mov     edx, 0E1h; lineNumber
0x180036b4a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036b4f  mov     eax, ebx
0x180036b51  jmp     loc_180036C84
0x180036b56  mov     this, [rdi+10h]
0x180036b5a  xor     edx, edx; length
0x180036b5c  mov     rbx, [rdi]
0x180036b5f  mov     this, [this]; string
0x180036b62  call    cs:__imp_WindowsGetStringRawBuffer
0x180036b68  mov     this, [rdi+8]
0x180036b6c  mov     rdx, rax
0x180036b6f  mov     this, [this]
0x180036b72  call    cs:__imp_OpenStateExplicit
0x180036b78  mov     rdx, rax; ptr
0x180036b7b  lea     this, [rbx+58h]; this
0x180036b7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180036b84  mov     rbx, [rdi]
0x180036b87  cmp     qword ptr [rbx+58h], 0
0x180036b8c  jnz     short loc_180036BEE
0x180036b8e  call    cs:__imp_GetLastError
0x180036b94  mov     ebx, eax
0x180036b96  test    eax, eax
0x180036b98  jle     short loc_180036BA3
0x180036b9a  movzx   ebx, ax
0x180036b9d  or      ebx, 80070000h
0x180036ba3  xor     r8d, r8d; userParam
0x180036ba6  lea     this, aCurrent; "Current"
0x180036bad  mov     edx, ebx; inputHr
0x180036baf  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180036bb4  mov     edx, 2; idsValue
0x180036bb9  mov     ecx, ebx; hr
0x180036bbb  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180036bc0  test    ebx, ebx
0x180036bc2  jns     short loc_180036B4F
0x180036bc4  lea     rax, aOpenstateexpli_5; "OpenStateExplicit"
0x180036bcb  mov     edx, 0F2h; lineNumber
0x180036bd0  mov     this, [rsp+38h]; callerReturnAddress
0x180036bd5  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180036bdc  mov     r9d, ebx; hr
0x180036bdf  mov     [rsp+38h+formatString], rax; formatString
0x180036be4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036be9  jmp     loc_180036B4F
0x180036bee  lea     this, [rbx+0C8h]; this
0x180036bf5  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x180036bfa  lea     this, [rbx+0C8h]; propertyValueStaticInterface
0x180036c01  call    ?GetPropertyValueStaticInterface@StateABIHelpers@Storage@Windows@@YAJPEAPEAUIPropertyValueStatics@Foundation@3@@Z; Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(Windows::Foundation::IPropertyValueStatics * *)
0x180036c06  mov     ebx, eax
0x180036c08  test    eax, eax
0x180036c0a  jns     short loc_180036C1A
0x180036c0c  lea     rax, aGetpropertyval_0; "GetPropertyValueStaticInterface"
0x180036c13  mov     edx, 0F7h
0x180036c18  jmp     short loc_180036BD0
0x180036c1a  mov     this, [rdi]
0x180036c1d  mov     rdx, [rdi+10h]; other
0x180036c21  add     this, 60h ; '`'; this
0x180036c25  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x180036c2a  mov     ebx, eax
0x180036c2c  test    eax, eax
0x180036c2e  jns     short loc_180036C3E
0x180036c30  lea     rax, aInitialize; "Initialize"
0x180036c37  mov     edx, 0FAh
0x180036c3c  jmp     short loc_180036BD0
0x180036c3e  mov     rdi, [rdi]
0x180036c41  mov     this, rdi; this
0x180036c44  call    ?InitializeDataChangedSignaler@ApplicationDataServer@Storage@Windows@@AEAAJXZ; Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(void)
0x180036c49  mov     ebx, eax
0x180036c4b  test    eax, eax
0x180036c4d  jns     short loc_180036C82
0x180036c4f  mov     this, [rsp+38h]; callerReturnAddress
0x180036c54  lea     rax, aInitializedata_0; "InitializeDataChangedSignaler"
0x180036c5b  mov     r9d, ebx; hr
0x180036c5e  mov     [rsp+38h+formatString], rax; formatString
0x180036c63  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180036c6a  mov     edx, 101h; lineNumber
0x180036c6f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180036c74  lea     this, [rdi+60h]; this
0x180036c78  call    ?Release@String@Internal@Windows@@QEAAXXZ; Windows::Internal::String::Release(void)
0x180036c7d  jmp     loc_180036B4F
0x180036c82  xor     eax, eax
0x180036c84  mov     rbx, [rsp+38h+arg_0]
0x180036c89  mov     rsi, [rsp+38h+arg_8]
0x180036c8e  add     rsp, 30h
0x180036c92  pop     rdi
0x180036c93  retn
```
