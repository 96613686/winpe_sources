# Windows::Storage::RestrictedApplicationDataServer::Initialize(HSTRING__ *,HSTRING__ *,Windows::System::IUser *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)

- ea: `0x180021440`
- end: `0x18002167d`
- name: `?Initialize@RestrictedApplicationDataServer@Storage@Windows@@UEAAJPEAUHSTRING__@@0PEAUIUser@System@3@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `573`
- prototype: `HRESULT __fastcall(Windows::Storage::RestrictedApplicationDataServer *this, HSTRING__ *packageFamilyName, HSTRING__ *userSID, Windows::System::IUser *userParam, wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *tokenParam)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180009778`
- `0x1800133f0`
- `0x180016aac`
- `0x180019bf4`
- `0x180021440`
- `0x180021efc`
- `0x180021fc4`
- `0x180029d20`
- `0x180029df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800215eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021512`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800215eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800214dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800214eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800215b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800215c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800214dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800214eb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021562`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800215b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800215c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021634`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x1800214f7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x1800215d0`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x1800214f7`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicitForUserSidString` at `0x1800215d0`

## string_xrefs

- `0x180021658`: `OpenStateExplicitForUserSidString %ws userSid %ws`
- `0x180021599`: `OpenStateExplicitForUserSidString %ws %ws 0x%0x`

## pseudocode

```c
__int64 __fastcall Windows::Storage::RestrictedApplicationDataServer::Initialize(
        Windows::Storage::RestrictedApplicationDataServer *this,
        HSTRING packageFamilyName,
        HSTRING userSID,
        Windows::System::IUser *userParam,
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (__cdecl*)(void *),&CloseHandle> > > *tokenParam)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > *p_m_applicationStateHandle; // r14
  unsigned int v10; // edx
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v13; // rax
  void *v14; // rax
  signed int LastError; // eax
  Windows::System::IUser *v16; // r8
  signed int v17; // edi
  int v18; // r15d
  PCWSTR v19; // rbx
  PCWSTR v20; // rax
  PCWSTR v21; // rbx
  PCWSTR v22; // rax
  void *v23; // rax
  signed int v24; // eax
  PCWSTR v25; // rbx
  PCWSTR v26; // rax
  void *retaddr; // [rsp+78h] [rbp+0h]

  p_m_applicationStateHandle = &this->m_applicationStateHandle;
  if ( this->m_applicationStateHandle.m_ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !packageFamilyName )
  {
    v10 = 131;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v10,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.restrictedapplicationdata.server.cpp",
      -2147024809);
    return 2147942487LL;
  }
  if ( !userSID )
  {
    v10 = 132;
    goto LABEL_5;
  }
  if ( userParam && (((unsigned __int64)tokenParam->m_ptr + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v10 = 135;
    goto LABEL_5;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::operator=(&this->m_user, userParam);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    &this->m_token,
    tokenParam);
  StringRawBuffer = WindowsGetStringRawBuffer(packageFamilyName, 0);
  v13 = WindowsGetStringRawBuffer(userSID, 0);
  v14 = (void *)OpenStateExplicitForUserSidString(v13, StringRawBuffer);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    p_m_applicationStateHandle,
    v14);
  if ( !p_m_applicationStateHandle->m_ptr )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    v18 = Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(L"Current", v17, v16);
    if ( v18 < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(L"Current", v17, 0);
      Windows::Storage::StateABIHelpers::ReportError(v17, 2u);
      if ( v17 < 0 )
      {
        v19 = WindowsGetStringRawBuffer(userSID, 0);
        v20 = WindowsGetStringRawBuffer(packageFamilyName, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0xA1u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.restrictedapplicationdata.server.cpp",
          v17,
          "OpenStateExplicitForUserSidString %ws %ws 0x%0x",
          v20,
          v19,
          v18);
      }
      return (unsigned int)v17;
    }
    v21 = WindowsGetStringRawBuffer(packageFamilyName, 0);
    v22 = WindowsGetStringRawBuffer(userSID, 0);
    v23 = (void *)OpenStateExplicitForUserSidString(v22, v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      p_m_applicationStateHandle,
      v23);
    if ( !p_m_applicationStateHandle->m_ptr )
    {
      v24 = GetLastError();
      v17 = v24;
      if ( v24 > 0 )
        v17 = (unsigned __int16)v24 | 0x80070000;
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(L"Current", v17, 0);
      Windows::Storage::StateABIHelpers::ReportError(v17, 2u);
      if ( v17 < 0 )
      {
        v25 = WindowsGetStringRawBuffer(userSID, 0);
        v26 = WindowsGetStringRawBuffer(packageFamilyName, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0xB2u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.restrictedapplicationdata.server.cpp",
          v17,
          "OpenStateExplicitForUserSidString %ws userSid %ws",
          v26,
          v25);
      }
      return (unsigned int)v17;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180021440  push    rbx
0x180021442  push    rbp
0x180021443  push    rsi
0x180021444  push    rdi
0x180021445  push    r14
0x180021447  push    r15
0x180021449  sub     rsp, 48h
0x18002144d  lea     r14, [this+58h]
0x180021451  mov     r15, userParam
0x180021454  cmp     qword ptr [r14], 0
0x180021458  mov     rsi, userSID
0x18002145b  mov     rbp, packageFamilyName
0x18002145e  mov     rdi, this
0x180021461  jz      short loc_180021468
0x180021463  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!m_applicationStateHandle")
0x180021468  test    rbp, rbp
0x18002146b  jnz     short loc_180021492
0x18002146d  mov     edx, 83h; lineNumber
0x180021472  mov     this, [rsp+78h]; callerReturnAddress
0x180021477  lea     userSID, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002147e  mov     ebx, 80070057h
0x180021483  mov     r9d, ebx; hr
0x180021486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002148b  mov     eax, ebx
0x18002148d  jmp     loc_180021670
0x180021492  test    rsi, rsi
0x180021495  jnz     short loc_18002149E
0x180021497  mov     edx, 84h
0x18002149c  jmp     short loc_180021472
0x18002149e  mov     rbx, [rsp+78h+other]
0x1800214a6  test    r15, r15
0x1800214a9  jz      short loc_1800214C0
0x1800214ab  mov     rax, [rbx]
0x1800214ae  inc     rax
0x1800214b1  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800214b7  jnz     short loc_1800214C0
0x1800214b9  mov     edx, 87h
0x1800214be  jmp     short loc_180021472
0x1800214c0  lea     this, [rdi+68h]; this
0x1800214c4  mov     packageFamilyName, r15; other
0x1800214c7  call    ??4?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIUser@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::IUser>::operator=(Windows::System::IUser *)
0x1800214cc  lea     this, [rdi+70h]; this
0x1800214d0  mov     packageFamilyName, rbx; other
0x1800214d3  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x1800214d8  xor     edx, edx; length
0x1800214da  mov     this, rbp; string
0x1800214dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800214e3  xor     edx, edx; length
0x1800214e5  mov     this, rsi; string
0x1800214e8  mov     rbx, rax
0x1800214eb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800214f1  mov     this, rax
0x1800214f4  mov     packageFamilyName, rbx
0x1800214f7  call    cs:__imp_OpenStateExplicitForUserSidString
0x1800214fd  mov     packageFamilyName, rax; ptr
0x180021500  mov     this, r14; this
0x180021503  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180021508  cmp     qword ptr [r14], 0
0x18002150c  jnz     loc_18002166E
0x180021512  call    cs:__imp_GetLastError
0x180021518  mov     edi, eax
0x18002151a  test    eax, eax
0x18002151c  jle     short loc_180021527
0x18002151e  movzx   edi, ax
0x180021521  or      edi, 80070000h
0x180021527  mov     edx, edi; inputHr
0x180021529  lea     this, aCurrent; "Current"
0x180021530  call    ?TriggerRepairStateLocationsIfNeeded@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180021535  mov     r15d, eax
0x180021538  test    eax, eax
0x18002153a  jns     short loc_1800215B1
0x18002153c  xor     r8d, r8d; userParam
0x18002153f  lea     this, aCurrent; "Current"
0x180021546  mov     edx, edi; inputHr
0x180021548  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x18002154d  mov     edx, 2; idsValue
0x180021552  mov     ecx, edi; hr
0x180021554  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180021559  test    edi, edi
0x18002155b  jns     short loc_1800215AA
0x18002155d  xor     edx, edx; length
0x18002155f  mov     this, rsi; string
0x180021562  call    cs:__imp_WindowsGetStringRawBuffer
0x180021568  xor     edx, edx; length
0x18002156a  mov     this, rbp; string
0x18002156d  mov     rbx, rax
0x180021570  call    cs:__imp_WindowsGetStringRawBuffer
0x180021576  mov     this, [rsp+78h]; callerReturnAddress
0x18002157b  lea     userSID, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\statemanage"...
0x180021582  mov     [rsp+78h+var_40], r15d
0x180021587  mov     r9d, edi; hr
0x18002158a  mov     [rsp+78h+var_48], rbx
0x18002158f  mov     edx, 0A1h; lineNumber
0x180021594  mov     [rsp+78h+var_50], rax
0x180021599  lea     rax, aOpenstateexpli_3; "OpenStateExplicitForUserSidString %ws %"...
0x1800215a0  mov     [rsp+78h+formatString], rax; formatString
0x1800215a5  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800215aa  mov     eax, edi
0x1800215ac  jmp     loc_180021670
0x1800215b1  xor     edx, edx; length
0x1800215b3  mov     this, rbp; string
0x1800215b6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800215bc  xor     edx, edx; length
0x1800215be  mov     this, rsi; string
0x1800215c1  mov     rbx, rax
0x1800215c4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800215ca  mov     this, rax
0x1800215cd  mov     packageFamilyName, rbx
0x1800215d0  call    cs:__imp_OpenStateExplicitForUserSidString
0x1800215d6  mov     packageFamilyName, rax; ptr
0x1800215d9  mov     this, r14; this
0x1800215dc  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800215e1  cmp     qword ptr [r14], 0
0x1800215e5  jnz     loc_18002166E
0x1800215eb  call    cs:__imp_GetLastError
0x1800215f1  mov     edi, eax
0x1800215f3  test    eax, eax
0x1800215f5  jle     short loc_180021600
0x1800215f7  movzx   edi, ax
0x1800215fa  or      edi, 80070000h
0x180021600  xor     r8d, r8d; userParam
0x180021603  lea     this, aCurrent; "Current"
0x18002160a  mov     edx, edi; inputHr
0x18002160c  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x180021611  mov     edx, 2; idsValue
0x180021616  mov     ecx, edi; hr
0x180021618  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18002161d  test    edi, edi
0x18002161f  jns     short loc_1800215AA
0x180021621  xor     edx, edx; length
0x180021623  mov     this, rsi; string
0x180021626  call    cs:__imp_WindowsGetStringRawBuffer
0x18002162c  xor     edx, edx; length
0x18002162e  mov     this, rbp; string
0x180021631  mov     rbx, rax
0x180021634  call    cs:__imp_WindowsGetStringRawBuffer
0x18002163a  mov     this, [rsp+78h]; callerReturnAddress
0x18002163f  lea     userSID, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\statemanage"...
0x180021646  mov     [rsp+78h+var_48], rbx
0x18002164b  mov     r9d, edi; hr
0x18002164e  mov     [rsp+78h+var_50], rax
0x180021653  mov     edx, 0B2h; lineNumber
0x180021658  lea     rax, aOpenstateexpli_1; "OpenStateExplicitForUserSidString %ws u"...
0x18002165f  mov     [rsp+78h+formatString], rax; formatString
0x180021664  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180021669  jmp     loc_1800215AA
0x18002166e  xor     eax, eax
0x180021670  add     rsp, 48h
0x180021674  pop     r15
0x180021676  pop     r14
0x180021678  pop     rdi
0x180021679  pop     rsi
0x18002167a  pop     rbp
0x18002167b  pop     rbx
0x18002167c  retn
```
