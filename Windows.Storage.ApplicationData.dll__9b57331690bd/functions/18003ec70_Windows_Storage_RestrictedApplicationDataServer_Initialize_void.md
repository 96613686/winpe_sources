# Windows::Storage::RestrictedApplicationDataServer::Initialize(void)

- ea: `0x18003ec70`
- end: `0x18003eda6`
- name: `?Initialize@RestrictedApplicationDataServer@Storage@Windows@@UEAAJXZ`
- size: `310`
- prototype: `HRESULT __fastcall(Windows::Storage::RestrictedApplicationDataServer *this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x180019bf4`
- `0x180021fc4`
- `0x180029d20`
- `0x180029df0`
- `0x18003ec70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed37`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x18003ec8e`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x18003ed20`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x18003ec8e`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x18003ed20`

## string_xrefs

- `0x18003ecf8`: `OpenState 0x%0x`
- `0x18003ed72`: `OpenState`

## pseudocode

```c
__int64 __fastcall Windows::Storage::RestrictedApplicationDataServer::Initialize(
        Windows::Storage::RestrictedApplicationDataServer *this)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > *p_m_applicationStateHandle; // rdi
  void *v2; // rax
  signed int LastError; // eax
  Windows::System::IUser *v4; // r8
  signed int v5; // ebx
  int v6; // esi
  void *v8; // rax
  signed int v9; // eax
  void *retaddr; // [rsp+38h] [rbp+0h]

  p_m_applicationStateHandle = &this->m_applicationStateHandle;
  if ( this->m_applicationStateHandle.m_ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v2 = (void *)OpenState();
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    p_m_applicationStateHandle,
    v2);
  if ( !p_m_applicationStateHandle->m_ptr )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(L"Current", v5, v4);
    if ( v6 < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(L"Current", v5, 0);
      Windows::Storage::StateABIHelpers::ReportError(v5, 1u);
      if ( v5 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x36u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.restrictedapplicationdata.server.cpp",
          v5,
          "OpenState 0x%0x",
          v6);
      return (unsigned int)v5;
    }
    v8 = (void *)OpenState();
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      p_m_applicationStateHandle,
      v8);
    if ( !p_m_applicationStateHandle->m_ptr )
    {
      v9 = GetLastError();
      v5 = v9;
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(L"Current", v5, 0);
      Windows::Storage::StateABIHelpers::ReportError(v5, 1u);
      if ( v5 < 0 )
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x43u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.restrictedapplicationdata.server.cpp",
          v5,
          "OpenState");
      return (unsigned int)v5;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003ec70  mov     [rsp+arg_0], rbx
0x18003ec75  mov     [rsp+arg_8], rsi
0x18003ec7a  push    rdi
0x18003ec7b  sub     rsp, 30h
0x18003ec7f  lea     rdi, [this+58h]
0x18003ec83  cmp     qword ptr [rdi], 0
0x18003ec87  jz      short loc_18003EC8E
0x18003ec89  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!m_applicationStateHandle")
0x18003ec8e  call    cs:__imp_OpenState
0x18003ec94  mov     rdx, rax; ptr
0x18003ec97  mov     this, rdi; this
0x18003ec9a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003ec9f  cmp     qword ptr [rdi], 0
0x18003eca3  jnz     loc_18003ED94
0x18003eca9  call    cs:__imp_GetLastError
0x18003ecaf  mov     ebx, eax
0x18003ecb1  test    eax, eax
0x18003ecb3  jle     short loc_18003ECBE
0x18003ecb5  movzx   ebx, ax
0x18003ecb8  or      ebx, 80070000h
0x18003ecbe  mov     edx, ebx; inputHr
0x18003ecc0  lea     this, aCurrent; "Current"
0x18003ecc7  call    ?TriggerRepairStateLocationsIfNeeded@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(ushort const *,long,Windows::System::IUser *)
0x18003eccc  mov     esi, eax
0x18003ecce  test    eax, eax
0x18003ecd0  jns     short loc_18003ED20
0x18003ecd2  xor     r8d, r8d; userParam
0x18003ecd5  lea     this, aCurrent; "Current"
0x18003ecdc  mov     edx, ebx; inputHr
0x18003ecde  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x18003ece3  mov     edx, 1; idsValue
0x18003ece8  mov     ecx, ebx; hr
0x18003ecea  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18003ecef  test    ebx, ebx
0x18003ecf1  jns     short loc_18003ED1C
0x18003ecf3  mov     this, [rsp+38h]; callerReturnAddress
0x18003ecf8  lea     rax, aOpenstate0x0x; "OpenState 0x%0x"
0x18003ecff  mov     [rsp+38h+var_10], esi
0x18003ed03  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003ed0a  mov     r9d, ebx; hr
0x18003ed0d  mov     [rsp+38h+formatString], rax; formatString
0x18003ed12  mov     edx, 36h ; '6'; lineNumber
0x18003ed17  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ed1c  mov     eax, ebx
0x18003ed1e  jmp     short loc_18003ED96
0x18003ed20  call    cs:__imp_OpenState
0x18003ed26  mov     rdx, rax; ptr
0x18003ed29  mov     this, rdi; this
0x18003ed2c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003ed31  cmp     qword ptr [rdi], 0
0x18003ed35  jnz     short loc_18003ED94
0x18003ed37  call    cs:__imp_GetLastError
0x18003ed3d  mov     ebx, eax
0x18003ed3f  test    eax, eax
0x18003ed41  jle     short loc_18003ED4C
0x18003ed43  movzx   ebx, ax
0x18003ed46  or      ebx, 80070000h
0x18003ed4c  xor     r8d, r8d; userParam
0x18003ed4f  lea     this, aCurrent; "Current"
0x18003ed56  mov     edx, ebx; inputHr
0x18003ed58  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x18003ed5d  mov     edx, 1; idsValue
0x18003ed62  mov     ecx, ebx; hr
0x18003ed64  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18003ed69  test    ebx, ebx
0x18003ed6b  jns     short loc_18003ED1C
0x18003ed6d  mov     this, [rsp+38h]; callerReturnAddress
0x18003ed72  lea     rax, aOpenstate_0; "OpenState"
0x18003ed79  mov     r9d, ebx; hr
0x18003ed7c  mov     [rsp+38h+formatString], rax; formatString
0x18003ed81  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003ed88  mov     edx, 43h ; 'C'; lineNumber
0x18003ed8d  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ed92  jmp     short loc_18003ED1C
0x18003ed94  xor     eax, eax
0x18003ed96  mov     rbx, [rsp+38h+arg_0]
0x18003ed9b  mov     rsi, [rsp+38h+arg_8]
0x18003eda0  add     rsp, 30h
0x18003eda4  pop     rdi
0x18003eda5  retn
```
