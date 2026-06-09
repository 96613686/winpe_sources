# Windows::Storage::ApplicationDataCompositeValueServer::Initialize(void *,HSTRING__ *)

- ea: `0x1800137d0`
- end: `0x1800138b1`
- name: `?Initialize@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAXPEAUHSTRING__@@@Z`
- size: `225`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, void *containerHandle, HSTRING__ *key)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005ee0`
- `0x1800093d0`
- `0x180009778`
- `0x1800137d0`
- `0x180013b54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013832`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013832`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800137ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001385c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001387a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800137ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001385c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001387a`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateAtom` at `0x1800137f9`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateAtom` at `0x1800137f9`

## string_xrefs

- `0x180013896`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18001386c`: `OpenStateAtom %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Initialize(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        void *containerHandle,
        HSTRING key)
{
  PCWSTR StringRawBuffer; // rax
  void *v7; // rax
  HRESULT PropertyValueStaticInterface; // ebx
  signed int LastError; // eax
  PCWSTR v11; // [rsp+28h] [rbp-10h]
  PCWSTR v12; // [rsp+28h] [rbp-10h]
  void *retaddr; // [rsp+38h] [rbp+0h]

  StringRawBuffer = WindowsGetStringRawBuffer(key, 0);
  v7 = (void *)OpenStateAtom(containerHandle, StringRawBuffer);
  this->atomHandle = v7;
  if ( v7 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)&this->propertyValueStaticInterface);
    PropertyValueStaticInterface = Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(&this->propertyValueStaticInterface.ptr_);
    if ( PropertyValueStaticInterface >= 0 )
      return 0;
    v12 = WindowsGetStringRawBuffer(key, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x4Fu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      PropertyValueStaticInterface,
      "GetPropertyValueStaticInterface %ws",
      v12);
  }
  else
  {
    LastError = GetLastError();
    PropertyValueStaticInterface = LastError;
    if ( LastError > 0 )
      PropertyValueStaticInterface = (unsigned __int16)LastError | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 0x12u);
    if ( PropertyValueStaticInterface < 0 )
    {
      v11 = WindowsGetStringRawBuffer(key, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x4Cu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        PropertyValueStaticInterface,
        "OpenStateAtom %ws",
        v11);
    }
  }
  return (unsigned int)PropertyValueStaticInterface;
}

```

## disassembly

```asm
0x1800137d0  mov     [rsp+arg_0], rbx
0x1800137d5  mov     [rsp+arg_8], rsi
0x1800137da  push    rdi
0x1800137db  sub     rsp, 30h
0x1800137df  mov     rbx, containerHandle
0x1800137e2  mov     rdi, this
0x1800137e5  xor     edx, edx; length
0x1800137e7  mov     this, key; string
0x1800137ea  mov     rsi, key
0x1800137ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800137f3  mov     containerHandle, rax
0x1800137f6  mov     this, rbx
0x1800137f9  call    cs:__imp_OpenStateAtom
0x1800137ff  mov     [rdi+60h], rax
0x180013803  test    rax, rax
0x180013806  jz      short loc_180013832
0x180013808  lea     this, [rdi+68h]; this
0x18001380c  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x180013811  lea     this, [rdi+68h]; propertyValueStaticInterface
0x180013815  call    ?GetPropertyValueStaticInterface@StateABIHelpers@Storage@Windows@@YAJPEAPEAUIPropertyValueStatics@Foundation@3@@Z; Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(Windows::Foundation::IPropertyValueStatics * *)
0x18001381a  mov     ebx, eax
0x18001381c  test    eax, eax
0x18001381e  js      short loc_180013875
0x180013820  xor     eax, eax
0x180013822  mov     rbx, [rsp+38h+arg_0]
0x180013827  mov     rsi, [rsp+38h+arg_8]
0x18001382c  add     rsp, 30h
0x180013830  pop     rdi
0x180013831  retn
0x180013832  call    cs:__imp_GetLastError
0x180013838  mov     ebx, eax
0x18001383a  test    eax, eax
0x18001383c  jle     short loc_180013847
0x18001383e  movzx   ebx, ax
0x180013841  or      ebx, 80070000h
0x180013847  mov     edx, 12h; idsValue
0x18001384c  mov     ecx, ebx; hr
0x18001384e  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180013853  test    ebx, ebx
0x180013855  jns     short loc_1800138AA
0x180013857  xor     edx, edx; length
0x180013859  mov     this, rsi; string
0x18001385c  call    cs:__imp_WindowsGetStringRawBuffer
0x180013862  mov     [rsp+38h+var_10], rax
0x180013867  mov     edx, 4Ch ; 'L'
0x18001386c  lea     rax, aOpenstateatomW; "OpenStateAtom %ws"
0x180013873  jmp     short loc_180013891
0x180013875  xor     edx, edx; length
0x180013877  mov     this, rsi; string
0x18001387a  call    cs:__imp_WindowsGetStringRawBuffer
0x180013880  mov     [rsp+38h+var_10], rax
0x180013885  mov     edx, 4Fh ; 'O'; lineNumber
0x18001388a  lea     rax, aGetpropertyval; "GetPropertyValueStaticInterface %ws"
0x180013891  mov     this, [rsp+38h]; callerReturnAddress
0x180013896  lea     key, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001389d  mov     r9d, ebx; hr
0x1800138a0  mov     [rsp+38h+formatString], rax; formatString
0x1800138a5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800138aa  mov     eax, ebx
0x1800138ac  jmp     loc_180013822
```
