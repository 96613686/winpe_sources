# Windows::Storage::ApplicationDataServer::Initialize(HSTRING__ *,HSTRING__ *,Windows::System::IUser *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)

- ea: `0x18001e100`
- end: `0x18001e2c9`
- name: `?Initialize@ApplicationDataServer@Storage@Windows@@UEAAJPEAUHSTRING__@@0PEAUIUser@System@3@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `457`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataServer *this, HSTRING__ *packageFamilyName, HSTRING__ *userSID, Windows::System::IUser *userParam, wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *tokenParam)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009778`
- `0x1800133f0`
- `0x180016aac`
- `0x1800187c0`
- `0x180019bf4`
- `0x18001e100`
- `0x180021efc`
- `0x180021fc4`
- `0x180035c28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e29b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e2ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e29b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e1e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e1e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e24a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001e259`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x18001e1fb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x18001e1fb`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataServer::Initialize(
        Windows::Storage::ApplicationDataServer *this,
        HSTRING packageFamilyName,
        HSTRING userSID,
        Windows::System::IUser *userParam,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *tokenParam)
{
  unsigned int v6; // edx
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *v8; // rbx
  char *m_ptr; // rax
  const wchar_t *v10; // rax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v12; // rax
  void *v13; // rax
  HRESULT v14; // esi
  const wchar_t *v15; // rdi
  PCWSTR v16; // rbx
  PCWSTR v17; // rax
  const wchar_t *operation; // [rsp+40h] [rbp-40h] BYREF
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive lock; // [rsp+48h] [rbp-38h] BYREF
  Windows::Internal::String *v20[6]; // [rsp+50h] [rbp-30h] BYREF
  void *retaddr; // [rsp+98h] [rbp+18h]
  HSTRING string; // [rsp+A8h] [rbp+28h] BYREF
  HSTRING v23; // [rsp+B0h] [rbp+30h] BYREF
  Windows::System::IUser *other; // [rsp+B8h] [rbp+38h] BYREF

  other = userParam;
  v23 = userSID;
  string = packageFamilyName;
  if ( !packageFamilyName )
  {
    v6 = 347;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v6,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      -2147024809);
    return 2147942487LL;
  }
  if ( !userSID )
  {
    v6 = 348;
    goto LABEL_3;
  }
  v8 = tokenParam;
  m_ptr = (char *)tokenParam->m_ptr;
  if ( userParam )
  {
    if ( ((unsigned __int64)(m_ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      v6 = 351;
      goto LABEL_3;
    }
  }
  else if ( (unsigned __int64)(m_ptr - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v6 = 356;
    goto LABEL_3;
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&lock, &this->m_applicationStateLock.SRWLock_);
  if ( this->m_applicationStateHandle.m_ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v10 = L"GetForUserAsync";
  if ( !other )
    v10 = L"Current";
  operation = v10;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::operator=(&this->m_user, other);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this->m_token,
    v8);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = WindowsGetStringRawBuffer(v23, 0);
  v13 = (void *)OpenStateExplicitForUserSidString(v12, StringRawBuffer);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &this->m_applicationStateHandle,
    v13);
  v20[0] = (Windows::Internal::String *)this;
  v20[1] = (Windows::Internal::String *)&operation;
  v20[2] = (Windows::Internal::String *)&v23;
  v20[3] = (Windows::Internal::String *)&string;
  v20[4] = (Windows::Internal::String *)&other;
  v14 = lambda_2f650bdc441fb3338cfbabd2d791d9eb_::operator()(v20);
  if ( v14 >= 0 )
  {
    if ( lock.sync_ )
      ReleaseSRWLockExclusive(lock.sync_);
    return 0;
  }
  else
  {
    v15 = operation;
    v16 = WindowsGetStringRawBuffer(v23, 0);
    v17 = WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x1D1u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdata.server.cpp",
      v14,
      "Package %ws %ws %ws",
      v17,
      v16,
      v15);
    if ( lock.sync_ )
      ReleaseSRWLockExclusive(lock.sync_);
    return (unsigned int)v14;
  }
}

```

## disassembly

```asm
0x18001e100  mov     rax, rsp
0x18001e103  mov     [rax+8], rbx
0x18001e107  mov     [rax+20h], userParam
0x18001e10b  mov     [rax+18h], userSID
0x18001e10f  mov     [rax+10h], packageFamilyName
0x18001e113  push    rbp
0x18001e114  push    rsi
0x18001e115  push    rdi
0x18001e116  mov     rbp, rsp
0x18001e119  sub     rsp, 80h
0x18001e120  mov     rdi, this
0x18001e123  test    packageFamilyName, packageFamilyName; __annotation("WILSTG:|60365688|Feature_2568426808|AlwaysEnabled")
0x18001e126  jnz     short loc_18001E14C
0x18001e128  mov     edx, 15Bh; lineNumber
0x18001e12d  mov     this, [rbp+18h]; callerReturnAddress
0x18001e131  lea     userSID, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e138  mov     ebx, 80070057h
0x18001e13d  mov     r9d, ebx; hr
0x18001e140  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e145  mov     eax, ebx
0x18001e147  jmp     loc_18001E2B6
0x18001e14c  test    userSID, userSID
0x18001e14f  jnz     short loc_18001E158
0x18001e151  mov     edx, 15Ch
0x18001e156  jmp     short loc_18001E12D
0x18001e158  mov     rbx, [rbp+arg_20]
0x18001e15c  mov     rax, [rbx]
0x18001e15f  test    userParam, userParam
0x18001e162  jz      short loc_18001E176
0x18001e164  inc     rax
0x18001e167  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001e16d  jnz     short loc_18001E186
0x18001e16f  mov     edx, 15Fh
0x18001e174  jmp     short loc_18001E12D
0x18001e176  dec     rax
0x18001e179  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001e17d  ja      short loc_18001E186
0x18001e17f  mov     edx, 164h
0x18001e184  jmp     short loc_18001E12D
0x18001e186  lea     packageFamilyName, [this+0E8h]; lock
0x18001e18d  lea     this, [rbp+lock]; result
0x18001e191  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001e196  cmp     qword ptr [rdi+58h], 0
0x18001e19b  jz      short loc_18001E1A2
0x18001e19d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!m_applicationStateHandle")
0x18001e1a2  mov     packageFamilyName, [rbp+other]; other
0x18001e1a6  lea     this, aCurrent; "Current"
0x18001e1ad  test    packageFamilyName, packageFamilyName
0x18001e1b0  lea     rax, aGetforuserasyn; "GetForUserAsync"
0x18001e1b7  cmovz   rax, this
0x18001e1bb  lea     this, [rdi+0D8h]; this
0x18001e1c2  mov     [rbp+operation], rax
0x18001e1c6  call    ??4?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUser@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::operator=(Windows::System::IUser *)
0x18001e1cb  lea     this, [rdi+0E0h]; this
0x18001e1d2  mov     packageFamilyName, rbx; other
0x18001e1d5  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18001e1da  mov     this, [rbp+string]; string
0x18001e1de  xor     edx, edx; length
0x18001e1e0  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e1e6  mov     this, [rbp+arg_10]; string
0x18001e1ea  xor     edx, edx; length
0x18001e1ec  mov     rbx, rax
0x18001e1ef  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e1f5  mov     this, rax
0x18001e1f8  mov     packageFamilyName, rbx
0x18001e1fb  call    cs:__imp_OpenStateExplicitForUserSidString
0x18001e201  mov     packageFamilyName, rax; ptr
0x18001e204  lea     this, [rdi+58h]; this
0x18001e208  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18001e20d  lea     rax, [rbp+operation]
0x18001e211  mov     [rbp+var_30], rdi
0x18001e215  mov     [rbp+var_28], rax
0x18001e219  lea     this, [rbp+var_30]
0x18001e21d  lea     rax, [rbp+arg_10]
0x18001e221  mov     [rbp+var_20], rax
0x18001e225  lea     rax, [rbp+string]
0x18001e229  mov     [rbp+var_18], rax
0x18001e22d  lea     rax, [rbp+other]
0x18001e231  mov     [rbp+var_10], rax
0x18001e235  call    _lambda_2f650bdc441fb3338cfbabd2d791d9eb___operator__
0x18001e23a  mov     esi, eax
0x18001e23c  test    eax, eax
0x18001e23e  jns     short loc_18001E2A5
0x18001e240  mov     this, [rbp+arg_10]; string
0x18001e244  xor     edx, edx; length
0x18001e246  mov     rdi, [rbp+operation]
0x18001e24a  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e250  mov     this, [rbp+string]; string
0x18001e254  xor     edx, edx; length
0x18001e256  mov     rbx, rax
0x18001e259  call    cs:__imp_WindowsGetStringRawBuffer
0x18001e25f  mov     this, [rbp+18h]; callerReturnAddress
0x18001e263  lea     userSID, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\statemanage"...
0x18001e26a  mov     [rsp+80h+var_48], rdi
0x18001e26f  mov     r9d, esi; hr
0x18001e272  mov     [rsp+80h+var_50], rbx
0x18001e277  mov     edx, 1D1h; lineNumber
0x18001e27c  mov     [rsp+80h+var_58], rax
0x18001e281  lea     rax, aPackageWsWsWs; "Package %ws %ws %ws"
0x18001e288  mov     [rsp+80h+formatString], rax; formatString
0x18001e28d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001e292  mov     this, [rbp+lock.sync_]; SRWLock
0x18001e296  test    this, this
0x18001e299  jz      short loc_18001E2A1
0x18001e29b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e2a1  mov     eax, esi
0x18001e2a3  jmp     short loc_18001E2B6
0x18001e2a5  mov     this, [rbp+lock.sync_]; SRWLock
0x18001e2a9  test    this, this
0x18001e2ac  jz      short loc_18001E2B4
0x18001e2ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e2b4  xor     eax, eax
0x18001e2b6  mov     rbx, [rsp+80h+arg_0]
0x18001e2be  add     rsp, 80h
0x18001e2c5  pop     rdi
0x18001e2c6  pop     rsi
0x18001e2c7  pop     rbp
0x18001e2c8  retn
```
