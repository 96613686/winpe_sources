# Windows::Storage::RestrictedApplicationDataServer::Initialize(HSTRING__ *)

- ea: `0x18003eae0`
- end: `0x18003ec5c`
- name: `?Initialize@RestrictedApplicationDataServer@Storage@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `380`
- prototype: `HRESULT __fastcall(Windows::Storage::RestrictedApplicationDataServer *this, HSTRING__ *packageFamilyName)`
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
- `0x18003eae0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003eb2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ebe1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003eb00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003eb7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ebba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ec1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003eb00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003eb7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ebba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003ec1c`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18003eb10`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18003ebca`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18003eb10`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenStateExplicit` at `0x18003ebca`

## string_xrefs

- `0x18003eb9d`: `OpenStateExplicit %ws 0x%0x`
- `0x18003ec36`: `OpenStateExplicit %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::RestrictedApplicationDataServer::Initialize(
        Windows::Storage::RestrictedApplicationDataServer *this,
        HSTRING packageFamilyName)
{
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,int (__cdecl*)(void *),&CloseState,wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t> > > *p_m_applicationStateHandle; // rdi
  PCWSTR StringRawBuffer; // rax
  void *v5; // rax
  signed int LastError; // eax
  Windows::System::IUser *v7; // r8
  signed int v8; // ebx
  int v9; // ebp
  PCWSTR v10; // rax
  PCWSTR v12; // rax
  void *v13; // rax
  signed int v14; // eax
  PCWSTR v15; // rax
  int v16; // [rsp+30h] [rbp-38h]
  void *retaddr; // [rsp+68h] [rbp+0h]

  p_m_applicationStateHandle = &this->m_applicationStateHandle;
  if ( this->m_applicationStateHandle.m_ptr )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  StringRawBuffer = WindowsGetStringRawBuffer(packageFamilyName, 0);
  v5 = (void *)OpenStateExplicit(-4, StringRawBuffer);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    p_m_applicationStateHandle,
    v5);
  if ( !p_m_applicationStateHandle->m_ptr )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(L"Current", v8, v7);
    if ( v9 < 0 )
    {
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(L"Current", v8, 0);
      Windows::Storage::StateABIHelpers::ReportError(v8, 2u);
      if ( v8 < 0 )
      {
        v10 = WindowsGetStringRawBuffer(packageFamilyName, 0);
        v16 = v9;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x65u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.restrictedapplicationdata.server.cpp",
          v8,
          "OpenStateExplicit %ws 0x%0x",
          v10,
          v16);
      }
      return (unsigned int)v8;
    }
    v12 = WindowsGetStringRawBuffer(packageFamilyName, 0);
    v13 = (void *)OpenStateExplicit(-4, v12);
    wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      p_m_applicationStateHandle,
      v13);
    if ( !p_m_applicationStateHandle->m_ptr )
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(L"Current", v8, 0);
      Windows::Storage::StateABIHelpers::ReportError(v8, 2u);
      if ( v8 < 0 )
      {
        v15 = WindowsGetStringRawBuffer(packageFamilyName, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x73u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.restrictedapplicationdata.server.cpp",
          v8,
          "OpenStateExplicit %ws",
          v15);
      }
      return (unsigned int)v8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003eae0  push    rbx
0x18003eae2  push    rbp
0x18003eae3  push    rsi
0x18003eae4  push    rdi
0x18003eae5  sub     rsp, 48h
0x18003eae9  lea     rdi, [this+58h]
0x18003eaed  mov     rsi, packageFamilyName
0x18003eaf0  cmp     qword ptr [rdi], 0
0x18003eaf4  jz      short loc_18003EAFB
0x18003eaf6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!m_applicationStateHandle")
0x18003eafb  xor     edx, edx; length
0x18003eafd  mov     this, rsi; string
0x18003eb00  call    cs:__imp_WindowsGetStringRawBuffer
0x18003eb06  mov     packageFamilyName, rax
0x18003eb09  mov     this, 0FFFFFFFFFFFFFFFCh
0x18003eb10  call    cs:__imp_OpenStateExplicit
0x18003eb16  mov     packageFamilyName, rax; ptr
0x18003eb19  mov     this, rdi; this
0x18003eb1c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003eb21  cmp     qword ptr [rdi], 0
0x18003eb25  jnz     loc_18003EC51
0x18003eb2b  call    cs:__imp_GetLastError
0x18003eb31  mov     ebx, eax
0x18003eb33  test    eax, eax
0x18003eb35  jle     short loc_18003EB40
0x18003eb37  movzx   ebx, ax
0x18003eb3a  or      ebx, 80070000h
0x18003eb40  mov     edx, ebx; inputHr
0x18003eb42  lea     this, aCurrent; "Current"
0x18003eb49  call    ?TriggerRepairStateLocationsIfNeeded@StateABIHelpers@Storage@Windows@@YAJPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairStateLocationsIfNeeded(ushort const *,long,Windows::System::IUser *)
0x18003eb4e  mov     ebp, eax
0x18003eb50  test    eax, eax
0x18003eb52  jns     short loc_18003EBB5
0x18003eb54  xor     r8d, r8d; userParam
0x18003eb57  lea     this, aCurrent; "Current"
0x18003eb5e  mov     edx, ebx; inputHr
0x18003eb60  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x18003eb65  mov     edx, 2; idsValue
0x18003eb6a  mov     ecx, ebx; hr
0x18003eb6c  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18003eb71  test    ebx, ebx
0x18003eb73  jns     short loc_18003EBAE
0x18003eb75  xor     edx, edx; length
0x18003eb77  mov     this, rsi; string
0x18003eb7a  call    cs:__imp_WindowsGetStringRawBuffer
0x18003eb80  mov     this, [rsp+68h]; callerReturnAddress
0x18003eb85  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003eb8c  mov     [rsp+68h+var_38], ebp
0x18003eb90  mov     r9d, ebx; hr
0x18003eb93  mov     [rsp+68h+var_40], rax
0x18003eb98  mov     edx, 65h ; 'e'; lineNumber
0x18003eb9d  lea     rax, aOpenstateexpli_6; "OpenStateExplicit %ws 0x%0x"
0x18003eba4  mov     [rsp+68h+formatString], rax; formatString
0x18003eba9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ebae  mov     eax, ebx
0x18003ebb0  jmp     loc_18003EC53
0x18003ebb5  xor     edx, edx; length
0x18003ebb7  mov     this, rsi; string
0x18003ebba  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ebc0  mov     packageFamilyName, rax
0x18003ebc3  mov     this, 0FFFFFFFFFFFFFFFCh
0x18003ebca  call    cs:__imp_OpenStateExplicit
0x18003ebd0  mov     packageFamilyName, rax; ptr
0x18003ebd3  mov     this, rdi; this
0x18003ebd6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?CloseState@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&CloseState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18003ebdb  cmp     qword ptr [rdi], 0
0x18003ebdf  jnz     short loc_18003EC51
0x18003ebe1  call    cs:__imp_GetLastError
0x18003ebe7  mov     ebx, eax
0x18003ebe9  test    eax, eax
0x18003ebeb  jle     short loc_18003EBF6
0x18003ebed  movzx   ebx, ax
0x18003ebf0  or      ebx, 80070000h
0x18003ebf6  xor     r8d, r8d; userParam
0x18003ebf9  lea     this, aCurrent; "Current"
0x18003ec00  mov     edx, ebx; inputHr
0x18003ec02  call    ?TriggerRepairAppRegistrationIfNeeded@StateABIHelpers@Storage@Windows@@YAXPEBGJPEAUIUser@System@3@@Z; Windows::Storage::StateABIHelpers::TriggerRepairAppRegistrationIfNeeded(ushort const *,long,Windows::System::IUser *)
0x18003ec07  mov     edx, 2; idsValue
0x18003ec0c  mov     ecx, ebx; hr
0x18003ec0e  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18003ec13  test    ebx, ebx
0x18003ec15  jns     short loc_18003EBAE
0x18003ec17  xor     edx, edx; length
0x18003ec19  mov     this, rsi; string
0x18003ec1c  call    cs:__imp_WindowsGetStringRawBuffer
0x18003ec22  mov     this, [rsp+68h]; callerReturnAddress
0x18003ec27  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\statemanage"...
0x18003ec2e  mov     [rsp+68h+var_40], rax
0x18003ec33  mov     r9d, ebx; hr
0x18003ec36  lea     rax, aOpenstateexpli_2; "OpenStateExplicit %ws"
0x18003ec3d  mov     edx, 73h ; 's'; lineNumber
0x18003ec42  mov     [rsp+68h+formatString], rax; formatString
0x18003ec47  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003ec4c  jmp     loc_18003EBAE
0x18003ec51  xor     eax, eax
0x18003ec53  add     rsp, 48h
0x18003ec57  pop     rdi
0x18003ec58  pop     rsi
0x18003ec59  pop     rbp
0x18003ec5a  pop     rbx
0x18003ec5b  retn
```
