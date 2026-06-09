# BingOnlineServices::CopyrightRequest::GetValueFromConfig(ConfigurationManagerKeys)

- ea: `0x180013c90`
- end: `0x180013e9a`
- name: `?GetValueFromConfig@CopyrightRequest@BingOnlineServices@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationManagerKeys@@@Z`
- size: `522`
- prototype: `__int64 __fastcall(BingOnlineServices::CopyrightRequest *this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800136f0`
- `0x180013940`

## callees

- `0x180002c2c`
- `0x180004fa0`
- `0x1800096f8`
- `0x180009778`
- `0x18000e5a8`
- `0x18000f9f0`
- `0x180013630`
- `0x180013b90`
- `0x180013ea0`
- `0x180015914`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013e4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013dcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180013e4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013e09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180013e09`
- `MapConfiguration!ConfigurationManager_Create` at `0x180013d12`
- `MapConfiguration!ConfigurationManager_Create` at `0x180013d12`

## string_xrefs

- `0x180013d18`: `Acquire configuration manager failed.`
- `0x180013dad`: `Acquire localeMapConfiguration failed.`
- `0x180013df1`: `Acquire configuration key value for copyright  request failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
const WCHAR *__fastcall BingOnlineServices::CopyrightRequest::GetValueFromConfig(
        BingOnlineServices::CopyrightRequest *this,
        const WCHAR *a2,
        unsigned int a3)
{
  int v6; // eax
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, PVOID, PVOID, _QWORD, __int64 *); // rdi
  PVOID Reserved1; // rbx
  HSTRING_HEADER *v10; // rax
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, HSTRING *); // rbx
  int v14; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v16; // r8
  HSTRING string; // [rsp+30h] [rbp-99h] BYREF
  __int64 v19; // [rsp+38h] [rbp-91h] BYREF
  __int64 v20; // [rsp+40h] [rbp-89h] BYREF
  const WCHAR *v21[2]; // [rsp+48h] [rbp-81h] BYREF
  _BYTE v22[32]; // [rsp+58h] [rbp-71h] BYREF
  _BYTE v23[32]; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v24[32]; // [rsp+98h] [rbp-31h] BYREF
  HSTRING_HEADER v25; // [rsp+B8h] [rbp-11h] BYREF
  HSTRING_HEADER v26; // [rsp+D8h] [rbp+Fh] BYREF

  v21[0] = a2;
  v20 = 0;
  v19 = 0;
  string = 0;
  std::wstring::wstring(v24);
  std::wstring::wstring(v23);
  std::wstring::wstring(v22);
  Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(&v20);
  v6 = ConfigurationManager_Create(&v20);
  BingOnlineServices::CopyrightRequest::CheckHResultThrowAtFailed(this, v6, "Acquire configuration manager failed.");
  BingOnlineServices::CopyrightRequest::GetSystemLocaleInfo(this, v24, v23);
  v7 = v20;
  v8 = *(__int64 (__fastcall **)(__int64, PVOID, PVOID, _QWORD, __int64 *))(*(_QWORD *)v20 + 48LL);
  Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(&v19);
  v21[0] = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
  Reserved1 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v25, v21)[1].Reserved.Reserved1;
  v21[0] = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v26, v21);
  v11 = v8(v7, v10[1].Reserved.Reserved1, Reserved1, 0, &v19);
  BingOnlineServices::CopyrightRequest::CheckHResultThrowAtFailed(this, v11, "Acquire localeMapConfiguration failed.");
  v12 = v19;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v19 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v14 = v13(v12, a3, &string);
  BingOnlineServices::CopyrightRequest::CheckHResultThrowAtFailed(
    this,
    v14,
    "Acquire configuration key value for copyright  request failed.");
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::assign(v22, StringRawBuffer);
  std::wstring::wstring(a2, v22, v16);
  std::wstring::_Tidy_deallocate(v22);
  std::wstring::_Tidy_deallocate(v23);
  std::wstring::_Tidy_deallocate(v24);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(&v20);
  return a2;
}

```

## disassembly

```asm
0x180013c90  mov     [rsp-8+arg_0], rbx
0x180013c95  mov     [rsp-8+arg_18], rsi
0x180013c9a  push    rbp
0x180013c9b  push    rdi
0x180013c9c  push    r12
0x180013c9e  push    r14
0x180013ca0  push    r15
0x180013ca2  lea     rbp, [rsp-37h]
0x180013ca7  sub     rsp, 100h
0x180013cae  mov     rax, cs:__security_cookie
0x180013cb5  xor     rax, rsp
0x180013cb8  mov     [rbp+57h+var_28], rax
0x180013cbc  mov     r14d, r8d
0x180013cbf  mov     r12, rdx
0x180013cc2  mov     r15, rcx
0x180013cc5  mov     [rsp+120h+var_D8], rdx
0x180013cca  mov     [rsp+120h+var_E0], 0
0x180013cd3  mov     [rsp+120h+var_E8], 0
0x180013cdc  mov     [rsp+120h+string], 0
0x180013ce5  lea     rcx, [rbp+57h+var_88]
0x180013ce9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013cee  nop
0x180013cef  lea     rcx, [rbp+57h+var_A8]
0x180013cf3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013cf8  nop
0x180013cf9  lea     rcx, [rbp+57h+var_C8]
0x180013cfd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180013d02  nop
0x180013d03  lea     rcx, [rsp+120h+var_E0]
0x180013d08  call    ?InternalRelease@?$ComPtr@UIConfigurationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(void)
0x180013d0d  lea     rcx, [rsp+120h+var_E0]
0x180013d12  call    cs:__imp_ConfigurationManager_Create
0x180013d18  lea     r8, aAcquireConfigu; "Acquire configuration manager failed."
0x180013d1f  mov     edx, eax; int
0x180013d21  mov     rcx, r15; this
0x180013d24  call    ?CheckHResultThrowAtFailed@CopyrightRequest@BingOnlineServices@@AEAAXJPEBD@Z; BingOnlineServices::CopyrightRequest::CheckHResultThrowAtFailed(long,char const *)
0x180013d29  lea     r8, [rbp+57h+var_A8]
0x180013d2d  lea     rdx, [rbp+57h+var_88]
0x180013d31  mov     rcx, r15
0x180013d34  call    ?GetSystemLocaleInfo@CopyrightRequest@BingOnlineServices@@AEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; BingOnlineServices::CopyrightRequest::GetSystemLocaleInfo(std::wstring *,std::wstring *)
0x180013d39  mov     rsi, [rsp+120h+var_E0]
0x180013d3e  mov     rax, [rsi]
0x180013d41  mov     rdi, [rax+30h]
0x180013d45  lea     rcx, [rsp+120h+var_E8]
0x180013d4a  call    ?InternalRelease@?$ComPtr@UIConfigurationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(void)
0x180013d4f  lea     rcx, [rbp+57h+var_88]
0x180013d53  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013d58  mov     [rsp+120h+var_D8], rax
0x180013d5d  lea     rdx, [rsp+120h+var_D8]
0x180013d62  lea     rcx, [rbp+57h+var_68]
0x180013d66  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180013d6b  nop
0x180013d6c  mov     rbx, [rax+18h]
0x180013d70  lea     rcx, [rbp+57h+var_A8]
0x180013d74  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013d79  mov     [rsp+120h+var_D8], rax
0x180013d7e  lea     rdx, [rsp+120h+var_D8]
0x180013d83  lea     rcx, [rbp+57h+var_48]
0x180013d87  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180013d8c  nop
0x180013d8d  lea     rcx, [rsp+120h+var_E8]
0x180013d92  mov     [rsp+120h+var_100], rcx
0x180013d97  xor     r9d, r9d
0x180013d9a  mov     r8, rbx
0x180013d9d  mov     rdx, [rax+18h]
0x180013da1  mov     rcx, rsi
0x180013da4  mov     rax, rdi
0x180013da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013dac  nop
0x180013dad  lea     r8, aAcquireLocalem; "Acquire localeMapConfiguration failed."
0x180013db4  mov     edx, eax; int
0x180013db6  mov     rcx, r15; this
0x180013db9  call    ?CheckHResultThrowAtFailed@CopyrightRequest@BingOnlineServices@@AEAAXJPEBD@Z; BingOnlineServices::CopyrightRequest::CheckHResultThrowAtFailed(long,char const *)
0x180013dbe  mov     rdi, [rsp+120h+var_E8]
0x180013dc3  mov     rax, [rdi]
0x180013dc6  mov     rbx, [rax+30h]
0x180013dca  mov     rcx, [rsp+120h+string]; string
0x180013dcf  call    cs:__imp_WindowsDeleteString
0x180013dd5  mov     [rsp+120h+string], 0
0x180013dde  lea     r8, [rsp+120h+string]
0x180013de3  mov     edx, r14d
0x180013de6  mov     rcx, rdi
0x180013de9  mov     rax, rbx
0x180013dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013df1  lea     r8, aAcquireConfigu_0; "Acquire configuration key value for cop"...
0x180013df8  mov     edx, eax; int
0x180013dfa  mov     rcx, r15; this
0x180013dfd  call    ?CheckHResultThrowAtFailed@CopyrightRequest@BingOnlineServices@@AEAAXJPEBD@Z; BingOnlineServices::CopyrightRequest::CheckHResultThrowAtFailed(long,char const *)
0x180013e02  xor     edx, edx; length
0x180013e04  mov     rcx, [rsp+120h+string]; string
0x180013e09  call    cs:__imp_WindowsGetStringRawBuffer
0x180013e0f  mov     rdx, rax
0x180013e12  lea     rcx, [rbp+57h+var_C8]
0x180013e16  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x180013e1b  lea     rdx, [rbp+57h+var_C8]
0x180013e1f  mov     rcx, r12
0x180013e22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180013e27  nop
0x180013e28  lea     rcx, [rbp+57h+var_C8]
0x180013e2c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013e31  nop
0x180013e32  lea     rcx, [rbp+57h+var_A8]
0x180013e36  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013e3b  nop
0x180013e3c  lea     rcx, [rbp+57h+var_88]
0x180013e40  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180013e45  nop
0x180013e46  mov     rcx, [rsp+120h+string]; string
0x180013e4b  call    cs:__imp_WindowsDeleteString
0x180013e51  mov     [rsp+120h+string], 0
0x180013e5a  lea     rcx, [rsp+120h+var_E8]
0x180013e5f  call    ?InternalRelease@?$ComPtr@UIConfigurationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(void)
0x180013e64  nop
0x180013e65  lea     rcx, [rsp+120h+var_E0]
0x180013e6a  call    ?InternalRelease@?$ComPtr@UIConfigurationManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurationManager>::InternalRelease(void)
0x180013e6f  mov     rax, r12
0x180013e72  mov     rcx, [rbp+57h+var_28]
0x180013e76  xor     rcx, rsp; StackCookie
0x180013e79  call    __security_check_cookie
0x180013e7e  lea     r11, [rsp+120h+var_20]
0x180013e86  mov     rbx, [r11+30h]
0x180013e8a  mov     rsi, [r11+48h]
0x180013e8e  mov     rsp, r11
0x180013e91  pop     r15
0x180013e93  pop     r14
0x180013e95  pop     r12
0x180013e97  pop     rdi
0x180013e98  pop     rbp
0x180013e99  retn
```
