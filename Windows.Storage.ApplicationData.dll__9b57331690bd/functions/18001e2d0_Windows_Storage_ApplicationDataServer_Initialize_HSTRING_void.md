# Windows::Storage::ApplicationDataServer::Initialize(HSTRING__ *,void *)

- ea: `0x18001e2d0`
- end: `0x18001e3ac`
- name: `?Initialize@ApplicationDataServer@Storage@Windows@@UEAAJPEAUHSTRING__@@PEAX@Z`
- size: `220`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataServer *this, HSTRING__ *packageFamilyName, void *token)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009778`
- `0x1800187c0`
- `0x180019bf4`
- `0x18001e2d0`
- `0x180021fc4`
- `0x180036abc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e389`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e39c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e389`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e39c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e309`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e351`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18001e316`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18001e316`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataServer::Initialize(
        Windows::Storage::ApplicationDataServer *this,
        HSTRING packageFamilyName,
        void *token)
{
  PCWSTR StringRawBuffer; // rax
  void *v5; // rax
  HRESULT v6; // ebx
  PCWSTR v7; // rax
  Windows::Internal::String *v9[4]; // [rsp+30h] [rbp-20h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  HSTRING string; // [rsp+78h] [rbp+28h] BYREF
  void *v12; // [rsp+80h] [rbp+30h] BYREF
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive lock; // [rsp+88h] [rbp+38h] BYREF

  v12 = token;
  string = packageFamilyName;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&lock, &this->m_applicationStateLock.SRWLock_);
  if ( this->m_applicationStateHandle.m_ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v5 = (void *)OpenStateExplicit(v12, StringRawBuffer);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &this->m_applicationStateHandle,
    v5);
  v9[0] = (Windows::Internal::String *)this;
  v9[1] = (Windows::Internal::String *)&v12;
  v9[2] = (Windows::Internal::String *)&string;
  v6 = lambda_a1b54a0e0d0c543c67e756a16c399ea7_::operator()(v9);
  if ( v6 >= 0 )
  {
    if ( lock.sync_ )
      ReleaseSRWLockExclusive(lock.sync_);
    return 0;
  }
  else
  {
    v7 = WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x106u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      v6,
      "Package %ws",
      v7);
    if ( lock.sync_ )
      ReleaseSRWLockExclusive(lock.sync_);
    return (unsigned int)v6;
  }
}

```

## disassembly

```asm
0x18001e2d0  mov     [rsp-18h+arg_10], token
0x18001e2d5  mov     [rsp-18h+string], packageFamilyName
0x18001e2da  push    rbp
0x18001e2db  push    rbx
0x18001e2dc  push    rdi
0x18001e2dd  mov     rbp, rsp
0x18001e2e0  sub     rsp, 50h
0x18001e2e4  mov     rbx, this
0x18001e2e7  lea     packageFamilyName, [this+0E8h]; __annotation("WILSTG:|60365688|Feature_2568426808|AlwaysEnabled")
0x18001e2ee  lea     this, [rbp+lock]; result
0x18001e2f2  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001e2f7  cmp     qword ptr [rbx+58h], 0
0x18001e2fc  jz      short loc_18001E303
0x18001e2fe  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!m_applicationStateHandle")
0x18001e303  mov     this, [rbp+string]; string
0x18001e307  xor     edx, edx; length
0x18001e309  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e30f  mov     this, [rbp+arg_10]
0x18001e313  mov     packageFamilyName, rax
0x18001e316  call    cs:__imp_OpenStateExplicit
0x18001e31c  mov     packageFamilyName, rax; ptr
0x18001e31f  lea     this, [rbx+58h]; this
0x18001e323  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001e328  lea     rax, [rbp+arg_10]
0x18001e32c  mov     [rbp+var_20], rbx
0x18001e330  mov     [rbp+var_18], rax
0x18001e334  lea     this, [rbp+var_20]
0x18001e338  lea     rax, [rbp+string]
0x18001e33c  mov     [rbp+var_10], rax
0x18001e340  call    _lambda_a1b54a0e0d0c543c67e756a16c399ea7___operator__
0x18001e345  mov     ebx, eax
0x18001e347  test    eax, eax
0x18001e349  jns     short loc_18001E393
0x18001e34b  mov     this, [rbp+string]; string
0x18001e34f  xor     edx, edx; length
0x18001e351  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e357  mov     this, [rbp+18h]; callerReturnAddress
0x18001e35b  lea     token, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e362  mov     [rsp+50h+var_28], rax
0x18001e367  mov     r9d, ebx; hr
0x18001e36a  lea     rax, aPackageWs; "Package %ws"
0x18001e371  mov     edx, 106h; lineNumber
0x18001e376  mov     [rsp+50h+formatString], rax; formatString
0x18001e37b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001e380  mov     this, [rbp+lock.sync_]; SRWLock
0x18001e384  test    this, this
0x18001e387  jz      short loc_18001E38F
0x18001e389  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e38f  mov     eax, ebx
0x18001e391  jmp     short loc_18001E3A4
0x18001e393  mov     this, [rbp+lock.sync_]; SRWLock
0x18001e397  test    this, this
0x18001e39a  jz      short loc_18001E3A2
0x18001e39c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e3a2  xor     eax, eax
0x18001e3a4  add     rsp, 50h
0x18001e3a8  pop     rdi
0x18001e3a9  pop     rbx
0x18001e3aa  pop     rbp
0x18001e3ab  retn
```
