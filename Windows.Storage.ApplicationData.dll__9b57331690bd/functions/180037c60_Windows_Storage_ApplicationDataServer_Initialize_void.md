# Windows::Storage::ApplicationDataServer::Initialize(void)

- ea: `0x180037c60`
- end: `0x180037e0a`
- name: `?Initialize@ApplicationDataServer@Storage@Windows@@UEAAJXZ`
- size: `426`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataServer *this)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000275c`
- `0x180005ee0`
- `0x1800093d0`
- `0x180009778`
- `0x180013b54`
- `0x1800187c0`
- `0x180019bf4`
- `0x180021fc4`
- `0x180029d20`
- `0x180029df0`
- `0x180037c60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037ca7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037d48`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037d24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037df9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037d24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180037df9`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x180037c8c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x180037d31`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x180037c8c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x180037d31`

## string_xrefs

- `0x180037cf6`: `OpenState 0x%0x`
- `0x180037d7e`: `OpenState`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataServer::Initialize(Windows::Storage::ApplicationDataServer *this)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > *p_m_applicationStateHandle; // rdi
  void *v3; // rax
  signed int LastError; // eax
  Windows::System::IUser *v5; // r8
  signed int PropertyValueStaticInterface; // ebx
  int v7; // ebp
  void *v9; // rax
  signed int v10; // eax
  void *retaddr; // [rsp+58h] [rbp+0h]
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive lock; // [rsp+68h] [rbp+10h] BYREF

  p_m_applicationStateHandle = &this->m_applicationStateHandle;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&lock, &this->m_applicationStateLock.SRWLock_);
  if ( p_m_applicationStateHandle->m_ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v3 = (void *)OpenState();
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    p_m_applicationStateHandle,
    v3);
  if ( !p_m_applicationStateHandle->m_ptr )
  {
    LastError = GetLastError();
    PropertyValueStaticInterface = LastError;
    if ( LastError > 0 )
      PropertyValueStaticInterface = (unsigned __int16)LastError | 0x80070000;
    v7 = Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(
           L"Current",
           PropertyValueStaticInterface,
           v5);
    if ( v7 < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        L"Current",
        PropertyValueStaticInterface,
        0);
      Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 1u);
      if ( PropertyValueStaticInterface < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x7Bu,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
          PropertyValueStaticInterface,
          "OpenState 0x%0x",
          v7);
      goto LABEL_9;
    }
    v9 = (void *)OpenState();
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      p_m_applicationStateHandle,
      v9);
    if ( !p_m_applicationStateHandle->m_ptr )
    {
      v10 = GetLastError();
      PropertyValueStaticInterface = v10;
      if ( v10 > 0 )
        PropertyValueStaticInterface = (unsigned __int16)v10 | 0x80070000;
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(
        L"Current",
        PropertyValueStaticInterface,
        0);
      Windows::Storage::StateABIHelpers::ReportError(PropertyValueStaticInterface, 1u);
      if ( PropertyValueStaticInterface < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x88u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
          PropertyValueStaticInterface,
          "OpenState");
      goto LABEL_9;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease((Microsoft::WRL::ComPtr<Windows::Storage::IApplicationDataContainer> *)&this->m_propertyValueStaticInterface);
  PropertyValueStaticInterface = Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(&this->m_propertyValueStaticInterface.ptr_);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x8Du,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "GetPropertyValueStaticInterface");
LABEL_9:
    if ( lock.sync_ )
      ReleaseSRWLockExclusive(lock.sync_);
    return (unsigned int)PropertyValueStaticInterface;
  }
  PropertyValueStaticInterface = Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(this);
  if ( PropertyValueStaticInterface < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x8Eu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      PropertyValueStaticInterface,
      "InitializeDataChangedSignaler");
    goto LABEL_9;
  }
  if ( lock.sync_ )
    ReleaseSRWLockExclusive(lock.sync_);
  return 0;
}

```

## disassembly

```asm
0x180037c60  push    rbx
0x180037c62  push    rbp
0x180037c63  push    rsi
0x180037c64  push    rdi
0x180037c65  sub     rsp, 38h
0x180037c69  mov     rsi, this
0x180037c6c  lea     rdi, [this+58h]; __annotation("WILSTG:|60365688|Feature_2568426808|AlwaysEnabled")
0x180037c70  lea     rdx, [this+0E8h]; lock
0x180037c77  lea     this, [rsp+58h+lock]; result
0x180037c7c  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180037c81  cmp     qword ptr [rdi], 0
0x180037c85  jz      short loc_180037C8C
0x180037c87  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!m_applicationStateHandle")
0x180037c8c  call    cs:__imp_OpenState
0x180037c92  mov     rdx, rax; ptr
0x180037c95  mov     this, rdi; this
0x180037c98  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180037c9d  cmp     qword ptr [rdi], 0
0x180037ca1  jnz     loc_180037DA8
0x180037ca7  call    cs:__imp_GetLastError
0x180037cad  mov     ebx, eax
0x180037caf  test    eax, eax
0x180037cb1  jle     short loc_180037CBC
0x180037cb3  movzx   ebx, ax
0x180037cb6  or      ebx, 80070000h
0x180037cbc  mov     edx, ebx; inputHr
0x180037cbe  lea     this, aCurrent; "Current"
0x180037cc5  call    ?TriggerRepairStateLocationsIfNeeded@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180037cca  mov     ebp, eax
0x180037ccc  test    eax, eax
0x180037cce  jns     short loc_180037D31
0x180037cd0  xor     r8d, r8d; userParam
0x180037cd3  lea     this, aCurrent; "Current"
0x180037cda  mov     edx, ebx; inputHr
0x180037cdc  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180037ce1  mov     edx, 1; idsValue
0x180037ce6  mov     ecx, ebx; hr
0x180037ce8  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180037ced  test    ebx, ebx
0x180037cef  jns     short loc_180037D1A
0x180037cf1  mov     this, [rsp+58h]; callerReturnAddress
0x180037cf6  lea     rax, aOpenstate0x0x; "OpenState 0x%0x"
0x180037cfd  mov     [rsp+58h+var_30], ebp
0x180037d01  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180037d08  mov     r9d, ebx; hr
0x180037d0b  mov     [rsp+58h+formatString], rax; formatString
0x180037d10  mov     edx, 7Bh ; '{'; lineNumber
0x180037d15  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180037d1a  mov     this, [rsp+58h+lock.sync_]; SRWLock
0x180037d1f  test    this, this
0x180037d22  jz      short loc_180037D2A
0x180037d24  call    cs:__imp_ReleaseSRWLockExclusive
0x180037d2a  mov     eax, ebx
0x180037d2c  jmp     loc_180037E01
0x180037d31  call    cs:__imp_OpenState
0x180037d37  mov     rdx, rax; ptr
0x180037d3a  mov     this, rdi; this
0x180037d3d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180037d42  cmp     qword ptr [rdi], 0
0x180037d46  jnz     short loc_180037DA8
0x180037d48  call    cs:__imp_GetLastError
0x180037d4e  mov     ebx, eax
0x180037d50  test    eax, eax
0x180037d52  jle     short loc_180037D5D
0x180037d54  movzx   ebx, ax
0x180037d57  or      ebx, 80070000h
0x180037d5d  xor     r8d, r8d; userParam
0x180037d60  lea     this, aCurrent; "Current"
0x180037d67  mov     edx, ebx; inputHr
0x180037d69  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180037d6e  mov     edx, 1; idsValue
0x180037d73  mov     ecx, ebx; hr
0x180037d75  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180037d7a  test    ebx, ebx
0x180037d7c  jns     short loc_180037D1A
0x180037d7e  lea     rax, aOpenstate_0; "OpenState"
0x180037d85  mov     edx, 88h; lineNumber
0x180037d8a  mov     this, [rsp+58h]; callerReturnAddress
0x180037d8f  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x180037d96  mov     r9d, ebx; hr
0x180037d99  mov     [rsp+58h+formatString], rax; formatString
0x180037d9e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180037da3  jmp     loc_180037D1A
0x180037da8  lea     rbx, [rsi+0C8h]
0x180037daf  mov     this, rbx; this
0x180037db2  call    ?InternalRelease@?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>::InternalRelease(void)
0x180037db7  mov     this, rbx; propertyValueStaticInterface
0x180037dba  call    ?GetPropertyValueStaticInterface@StateABIHelpers@Storage@Windows@@YAJPEAPEAUIPropertyValueStatics@Foundation@3@@Z; Windows::Storage::StateABIHelpers::GetPropertyValueStaticInterface(Windows::Foundation::IPropertyValueStatics * *)
0x180037dbf  mov     ebx, eax
0x180037dc1  test    eax, eax
0x180037dc3  jns     short loc_180037DD3
0x180037dc5  lea     rax, aGetpropertyval_0; "GetPropertyValueStaticInterface"
0x180037dcc  mov     edx, 8Dh
0x180037dd1  jmp     short loc_180037D8A
0x180037dd3  mov     this, rsi; this
0x180037dd6  call    ?InitializeDataChangedSignaler@ApplicationDataServer@Storage@Windows@@AEAAJXZ; Windows::Storage::ApplicationDataServer::InitializeDataChangedSignaler(void)
0x180037ddb  mov     ebx, eax
0x180037ddd  test    eax, eax
0x180037ddf  jns     short loc_180037DEF
0x180037de1  lea     rax, aInitializedata_0; "InitializeDataChangedSignaler"
0x180037de8  mov     edx, 8Eh
0x180037ded  jmp     short loc_180037D8A
0x180037def  mov     this, [rsp+58h+lock.sync_]; SRWLock
0x180037df4  test    this, this
0x180037df7  jz      short loc_180037DFF
0x180037df9  call    cs:__imp_ReleaseSRWLockExclusive
0x180037dff  xor     eax, eax
0x180037e01  add     rsp, 38h
0x180037e05  pop     rdi
0x180037e06  pop     rsi
0x180037e07  pop     rbp
0x180037e08  pop     rbx
0x180037e09  retn
```
