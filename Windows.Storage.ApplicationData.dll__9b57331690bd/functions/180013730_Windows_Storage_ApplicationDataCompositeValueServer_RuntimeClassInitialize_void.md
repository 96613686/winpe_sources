# Windows::Storage::ApplicationDataCompositeValueServer::RuntimeClassInitialize(void)

- ea: `0x180013730`
- end: `0x1800137c4`
- name: `?RuntimeClassInitialize@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJXZ`
- size: `148`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180005ee0`
- `0x1800093d0`
- `0x180009778`
- `0x180013730`
- `0x180013b54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013768`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013768`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateAtom` at `0x180013739`
- `ext-ms-win-appmodel-state-ext-l1-2-0!CreateStateAtom` at `0x180013739`

## string_xrefs

- `0x1800137ac`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18001378d`: `CreateStateAtom`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::RuntimeClassInitialize(
        Windows::Storage::ApplicationDataCompositeValueServer *this)
{
  void *StateAtom; // rax
  HRESULT PropertyValueStaticInterface; // ebx
  signed int LastError; // eax
  void *retaddr; // [rsp+38h] [rbp+0h]

  StateAtom = (void *)CreateStateAtom();
  this->atomHandle = StateAtom;
  if ( StateAtom )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)&this->propertyValueStaticInterface);
    PropertyValueStaticInterface = Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(&this->propertyValueStaticInterface.ptr_);
    if ( PropertyValueStaticInterface >= 0 )
      return 0;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x3Bu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      PropertyValueStaticInterface,
      "GetPropertyValueStaticInterface");
  }
  else
  {
    LastError = GetLastError();
    PropertyValueStaticInterface = LastError;
    if ( LastError > 0 )
      PropertyValueStaticInterface = (unsigned __int16)LastError | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 0x11u);
    if ( PropertyValueStaticInterface < 0 )
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x38u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        PropertyValueStaticInterface,
        "CreateStateAtom");
  }
  return (unsigned int)PropertyValueStaticInterface;
}

```

## disassembly

```asm
0x180013730  push    rbx
0x180013732  sub     rsp, 30h
0x180013736  mov     rbx, this
0x180013739  call    cs:__imp_CreateStateAtom
0x18001373f  mov     [rbx+60h], rax
0x180013743  test    rax, rax
0x180013746  jz      short loc_180013768
0x180013748  lea     this, [rbx+68h]; this
0x18001374c  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x180013751  lea     this, [rbx+68h]; propertyValueStaticInterface
0x180013755  call    ?GetPropertyValueStaticInterface@StateABIHelpers@Storage@Windows@@YAJPEAPEAUIPropertyValueStatics@Foundation@3@@Z; Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(Windows::Foundation::IPropertyValueStatics * *)
0x18001375a  mov     ebx, eax
0x18001375c  test    eax, eax
0x18001375e  js      short loc_18001379B
0x180013760  xor     eax, eax
0x180013762  add     rsp, 30h
0x180013766  pop     rbx
0x180013767  retn
0x180013768  call    cs:__imp_GetLastError
0x18001376e  mov     ebx, eax
0x180013770  test    eax, eax
0x180013772  jle     short loc_18001377D
0x180013774  movzx   ebx, ax
0x180013777  or      ebx, 80070000h
0x18001377d  mov     edx, 11h; idsValue
0x180013782  mov     ecx, ebx; hr
0x180013784  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180013789  test    ebx, ebx
0x18001378b  jns     short loc_1800137C0
0x18001378d  lea     rax, aCreatestateato_0; "CreateStateAtom"
0x180013794  mov     edx, 38h ; '8'
0x180013799  jmp     short loc_1800137A7
0x18001379b  lea     rax, aGetpropertyval_0; "GetPropertyValueStaticInterface"
0x1800137a2  mov     edx, 3Bh ; ';'; lineNumber
0x1800137a7  mov     this, [rsp+38h]; callerReturnAddress
0x1800137ac  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800137b3  mov     r9d, ebx; hr
0x1800137b6  mov     [rsp+38h+formatString], rax; formatString
0x1800137bb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800137c0  mov     eax, ebx
0x1800137c2  jmp     short loc_180013762
```
