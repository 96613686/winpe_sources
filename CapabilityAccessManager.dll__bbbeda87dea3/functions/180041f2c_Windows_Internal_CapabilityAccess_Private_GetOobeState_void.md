# Windows::Internal::CapabilityAccess::Private::GetOobeState(void)

- ea: `0x180041f2c`
- end: `0x18004204e`
- name: `?GetOobeState@Private@CapabilityAccess@Internal@Windows@@YAIXZ`
- size: `290`
- prototype: `unsigned int __fastcall(Windows::Internal::CapabilityAccess::Private *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180043fe8`
- `0x18006874c`

## callees

- `0x1800094c0`
- `0x18001f5f4`
- `0x18002392c`
- `0x180041f2c`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041fa0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041fa0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041fc1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180041fc1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041f84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041f84`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetOobeState(
        Windows::Internal::CapabilityAccess::Private *this)
{
  HSTRING v2; // rbx
  int ActivationFactory; // eax
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // [rsp+20h] [rbp-40h] BYREF
  __int64 v7; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  if ( Windows::Internal::CapabilityAccess::Private::Globals::StateCache::m_SystemOutOfBoxExperienceStateCompleted )
    return 2;
  v6 = 0;
  v7 = 0;
  if ( WindowsCreateStringReference(L"Windows.System.Profile.SystemSetupInfo", 0x26u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = string;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
  ActivationFactory = RoGetActivationFactory(v2, &GUID_b8366a4b_fb6a_4571_be0a_9a0f67954123, &v7);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x688,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v6);
  v4 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v7 + 48LL))(v7, &v6);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x689,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)(unsigned int)v4,
      v6);
  v5 = v6;
  if ( v6 == 2 )
  {
    Windows::Internal::CapabilityAccess::Private::Globals::StateCache::m_SystemOutOfBoxExperienceStateCompleted = 1;
    v5 = 2;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v7);
  return v5;
}

```

## disassembly

```asm
0x180041f2c  mov     [rsp-8+arg_0], rbx
0x180041f31  mov     [rsp-8+arg_8], rdi
0x180041f36  push    rbp
0x180041f37  mov     rbp, rsp
0x180041f3a  sub     rsp, 60h
0x180041f3e  mov     rax, cs:__security_cookie
0x180041f45  xor     rax, rsp
0x180041f48  mov     [rbp+var_10], rax
0x180041f4c  mov     al, cs:?m_SystemOutOfBoxExperienceStateCompleted@StateCache@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@_N@std@@A; std::atomic<bool> Windows::Internal::CapabilityAccess::Private::Globals::StateCache::m_SystemOutOfBoxExperienceStateCompleted
0x180041f52  nop
0x180041f53  test    al, al
0x180041f55  jz      short loc_180041F61
0x180041f57  mov     eax, 2
0x180041f5c  jmp     loc_180042008
0x180041f61  mov     [rbp+var_40], 0
0x180041f68  mov     [rbp+var_38], 0
0x180041f70  lea     r9, [rbp+string]; string
0x180041f74  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180041f78  mov     edx, 26h ; '&'; length
0x180041f7d  lea     rcx, ?RuntimeClass_Windows_System_Profile_SystemSetupInfo@@3QBGB; "Windows.System.Profile.SystemSetupInfo"
0x180041f84  call    cs:__imp_WindowsCreateStringReference
0x180041f8a  mov     edi, 1
0x180041f8f  test    eax, eax
0x180041f91  jns     short loc_180041FA6
0x180041f93  xor     r9d, r9d; lpArguments
0x180041f96  xor     r8d, r8d; nNumberOfArguments
0x180041f99  mov     edx, edi; dwExceptionFlags
0x180041f9b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180041fa0  call    cs:__imp_RaiseException
0x180041fa6  mov     rbx, [rbp+string]
0x180041faa  lea     rcx, [rbp+var_38]
0x180041fae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041fb3  lea     r8, [rbp+var_38]
0x180041fb7  lea     rdx, _GUID_b8366a4b_fb6a_4571_be0a_9a0f67954123
0x180041fbe  mov     rcx, rbx
0x180041fc1  call    cs:__imp_RoGetActivationFactory
0x180041fc7  mov     rcx, [rbp+8]; this
0x180041fcb  test    eax, eax
0x180041fcd  js      short loc_180042039
0x180041fcf  mov     rcx, [rbp+var_38]
0x180041fd3  mov     rax, [rcx]
0x180041fd6  lea     rdx, [rbp+var_40]
0x180041fda  mov     rax, [rax+30h]
0x180041fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041fe3  mov     rcx, [rbp+8]; this
0x180041fe7  test    eax, eax
0x180041fe9  js      short loc_180042024
0x180041feb  mov     ebx, [rbp+var_40]
0x180041fee  cmp     ebx, 2
0x180041ff1  jnz     short loc_180041FFD
0x180041ff3  xchg    dil, cs:?m_SystemOutOfBoxExperienceStateCompleted@StateCache@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@_N@std@@A; std::atomic<bool> Windows::Internal::CapabilityAccess::Private::Globals::StateCache::m_SystemOutOfBoxExperienceStateCompleted
0x180041ffa  mov     ebx, [rbp+var_40]
0x180041ffd  lea     rcx, [rbp+var_38]
0x180042001  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180042006  mov     eax, ebx
0x180042008  mov     rcx, [rbp+var_10]
0x18004200c  xor     rcx, rsp; StackCookie
0x18004200f  call    __security_check_cookie
0x180042014  mov     rbx, [rsp+60h+arg_0]
0x180042019  mov     rdi, [rsp+60h+arg_8]
0x18004201e  add     rsp, 60h
0x180042022  pop     rbp
0x180042023  retn
0x180042024  mov     r9d, eax; char *
0x180042027  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004202e  mov     edx, 689h; void *
0x180042033  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180042039  mov     r9d, eax; char *
0x18004203c  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042043  mov     edx, 688h; void *
0x180042048  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
