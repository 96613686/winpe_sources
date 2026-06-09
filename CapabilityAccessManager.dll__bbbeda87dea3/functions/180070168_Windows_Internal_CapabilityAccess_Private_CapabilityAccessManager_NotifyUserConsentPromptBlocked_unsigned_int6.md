# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::NotifyUserConsentPromptBlocked(unsigned __int64)

- ea: `0x180070168`
- end: `0x180070364`
- name: `?NotifyUserConsentPromptBlocked@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@AEAAX_K@Z`
- size: `508`
- prototype: `void __fastcall(Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *__hidden this, unsigned __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18006f230`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001f5f4`
- `0x18002392c`
- `0x180029408`
- `0x180039e9c`
- `0x180043060`
- `0x18004325c`
- `0x180045f78`
- `0x1800658cc`
- `0x1800672c0`
- `0x18006eda4`
- `0x180070168`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180070317`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180070317`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180070243`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180070243`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180070203`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x180070203`

## string_xrefs

- `0x180070214`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18007024d`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x1800702d5`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x1800702fb`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::NotifyUserConsentPromptBlocked(
        HANDLE *this,
        __int64 a2)
{
  PVOID v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  const char *v8; // r9
  __int64 (__fastcall *v9)(__int64, __int64, _QWORD, __int64); // rsi
  const unsigned __int16 *v10; // rax
  __int64 v11; // rdi
  const unsigned __int16 *v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // [rsp+20h] [rbp-59h]
  int v16[2]; // [rsp+30h] [rbp-49h] BYREF
  char v17; // [rsp+39h] [rbp-40h]
  __int64 v18; // [rsp+40h] [rbp-39h] BYREF
  __int64 v19; // [rsp+48h] [rbp-31h] BYREF
  __int64 v20; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v21[32]; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v22[4]; // [rsp+78h] [rbp-1h] BYREF
  _QWORD v23[4]; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
  }
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GetUserPolicyHandler(v4, &v19);
  v5 = v19;
  if ( v19 )
  {
    Windows::Internal::CapabilityAccess::Private::GetUserFromContextToken(&v20, a2);
    v18 = 0;
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 21);
    v7 = AppContainerDeriveSidFromMoniker(v6, &v18);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA7D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)v7,
        v15);
    Windows::Internal::CapabilityAccess::Private::GetSidStringFromSid(v21, v18);
    v17 = 1;
    if ( !ImpersonateLoggedOnUser(this[56]) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xA84,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        v8);
    *(_QWORD *)v16 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v5 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v16);
    v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this + 37);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v22, v10);
    v11 = v22[0];
    v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)v23, v12);
    v13 = v9(v5, v20, v23[0], v11);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA8A,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)v13,
        (int)v16);
    v14 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(*(_QWORD *)v16);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA8B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        (const char *)(unsigned int)v14,
        (int)v16);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v16);
    RevertToSelf();
    std::wstring::_Tidy_deallocate(v21);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v18);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
}

```

## disassembly

```asm
0x180070168  mov     [rsp-8+arg_10], rbx
0x18007016d  push    rbp
0x18007016e  push    rsi
0x18007016f  push    rdi
0x180070170  lea     rbp, [rsp-47h]
0x180070175  sub     rsp, 0C0h
0x18007017c  mov     rax, cs:__security_cookie
0x180070183  xor     rax, rsp
0x180070186  mov     [rbp+57h+var_18], rax
0x18007018a  mov     rsi, rdx
0x18007018d  mov     rdi, rcx
0x180070190  lea     rax, WPP_GLOBAL_Control
0x180070197  mov     rcx, cs:WPP_GLOBAL_Control
0x18007019e  cmp     rcx, rax
0x1800701a1  jz      short loc_1800701C4
0x1800701a3  test    byte ptr [rcx+1Ch], 1
0x1800701a7  jz      short loc_1800701C4
0x1800701a9  cmp     byte ptr [rcx+19h], 5
0x1800701ad  jb      short loc_1800701C4
0x1800701af  mov     edx, 2Ah ; '*'
0x1800701b4  lea     r8, WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids
0x1800701bb  mov     rcx, [rcx+10h]
0x1800701bf  call    WPP_SF_
0x1800701c4  lea     rdx, [rbp+57h+var_88]
0x1800701c8  call    ?GetUserPolicyHandler@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@AEAA?AV?$ComPtr@UIDeviceAccessBrokerExtension@Internal@Privacy@ApplicationModel@Windows@@@WRL@Microsoft@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GetUserPolicyHandler(void)
0x1800701cd  nop
0x1800701ce  mov     rbx, [rbp+57h+var_88]
0x1800701d2  test    rbx, rbx
0x1800701d5  jz      loc_18007033C
0x1800701db  mov     rdx, rsi
0x1800701de  lea     rcx, [rbp+57h+var_80]
0x1800701e2  call    ?GetUserFromContextToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@_K@Z; Windows::Internal::CapabilityAccess::Private::GetUserFromContextToken(unsigned __int64)
0x1800701e7  nop
0x1800701e8  mov     [rbp+57h+var_90], 0
0x1800701f0  lea     rcx, [rdi+0A8h]
0x1800701f7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800701fc  lea     rdx, [rbp+57h+var_90]
0x180070200  mov     rcx, rax
0x180070203  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180070209  mov     rcx, [rbp+5Fh]; this
0x18007020d  test    eax, eax
0x18007020f  jns     short loc_180070226
0x180070211  mov     r9d, eax; char *
0x180070214  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x18007021b  mov     edx, 0A7Dh; void *
0x180070220  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180070226  mov     rdx, [rbp+57h+var_90]
0x18007022a  lea     rcx, [rbp+57h+var_78]
0x18007022e  call    ?GetSidStringFromSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAX@Z; Windows::Internal::CapabilityAccess::Private::GetSidStringFromSid(void * const)
0x180070233  nop
0x180070234  mov     [rbp+57h+var_97], 1
0x180070238  mov     rsi, [rbp+5Fh]
0x18007023c  mov     rcx, [rdi+1C0h]; hToken
0x180070243  call    cs:__imp_ImpersonateLoggedOnUser
0x180070249  test    eax, eax
0x18007024b  jnz     short loc_180070262
0x18007024d  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x180070254  mov     edx, 0A84h; void *
0x180070259  mov     rcx, rsi; this
0x18007025c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180070262  mov     qword ptr [rbp+57h+var_A0], 0
0x18007026a  mov     rax, [rbx]
0x18007026d  mov     rsi, [rax+50h]
0x180070271  lea     rcx, [rbp+57h+var_A0]
0x180070275  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007027a  lea     rcx, [rdi+128h]
0x180070281  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180070286  mov     rdx, rax; unsigned __int16 *
0x180070289  lea     rcx, [rbp+57h+var_58]; this
0x18007028d  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x180070292  mov     rdi, [rbp+57h+var_58]
0x180070296  lea     rcx, [rbp+57h+var_78]
0x18007029a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007029f  mov     rdx, rax; unsigned __int16 *
0x1800702a2  lea     rcx, [rbp+57h+var_38]; this
0x1800702a6  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x1800702ab  lea     rax, [rbp+57h+var_A0]
0x1800702af  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800702b4  mov     r9, rdi
0x1800702b7  mov     r8, [rbp+57h+var_38]
0x1800702bb  mov     rdx, [rbp+57h+var_80]
0x1800702bf  mov     rcx, rbx
0x1800702c2  mov     rax, rsi
0x1800702c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800702ca  mov     rcx, [rbp+5Fh]; this
0x1800702ce  test    eax, eax
0x1800702d0  jns     short loc_1800702E7
0x1800702d2  mov     r9d, eax; char *
0x1800702d5  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800702dc  mov     edx, 0A8Ah; void *
0x1800702e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800702e7  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1800702eb  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x1800702f0  mov     rcx, [rbp+5Fh]; this
0x1800702f4  test    eax, eax
0x1800702f6  jns     short loc_18007030D
0x1800702f8  mov     r9d, eax; char *
0x1800702fb  lea     r8, aOnecoreBaseDev_58; "onecore\\base\\devices\\cam\\core\\capa"...
0x180070302  mov     edx, 0A8Bh; void *
0x180070307  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007030d  lea     rcx, [rbp+57h+var_A0]
0x180070311  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070316  nop
0x180070317  call    cs:__imp_RevertToSelf
0x18007031d  nop
0x18007031e  lea     rcx, [rbp+57h+var_78]
0x180070322  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180070327  nop
0x180070328  lea     rcx, [rbp+57h+var_90]
0x18007032c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180070331  nop
0x180070332  lea     rcx, [rbp+57h+var_80]
0x180070336  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007033b  nop
0x18007033c  lea     rcx, [rbp+57h+var_88]
0x180070340  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180070345  mov     rcx, [rbp+57h+var_18]
0x180070349  xor     rcx, rsp; StackCookie
0x18007034c  call    __security_check_cookie
0x180070351  mov     rbx, [rsp+0D0h+arg_10]
0x180070359  add     rsp, 0C0h
0x180070360  pop     rdi
0x180070361  pop     rsi
0x180070362  pop     rbp
0x180070363  retn
```
