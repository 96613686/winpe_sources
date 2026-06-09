# StoreApplication::GetStoreAppInstallLocationFromPackageSr(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &)

- ea: `0x1800dae40`
- end: `0x1800dafb0`
- name: `?GetStoreAppInstallLocationFromPackageSr@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800db8b8`
- `0x1800dd87c`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18000faf0`
- `0x18001082c`
- `0x1800252b0`
- `0x1800c97f0`
- `0x1800d8684`
- `0x1800d8b3c`
- `0x1800dae40`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800daf5d`

## string_xrefs

- `0x1800daeb8`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800daefb`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`
- `0x1800daf45`: `onecore\base\appcompat\inventory\software\inv\lib\storeapplication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall StoreApplication::GetStoreAppInstallLocationFromPackageSr(__int64 a1, _QWORD *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int v10; // eax
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v14; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v15[2]; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v17; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v14 = 0;
  v15[0] = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.PackageLocation",
    0x31u,
    0x30u);
  v4 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(
         v17,
         v15);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32C,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v4,
      (int)string);
  v5 = v15[0];
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15[0] + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  v7 = v6(v5, *a2, &v14);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x32E,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v7,
      (int)string);
  string = 0;
  v8 = v14;
  v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v14 + 88LL);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v10 = v9(v8, &string);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x331,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeapplication.cpp",
      (const char *)(unsigned int)v10,
      (int)string);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(a1, StringRawBuffer);
  Windows::Internal::String::~String(&string);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return a1;
}

```

## disassembly

```asm
0x1800dae40  mov     [rsp-18h+arg_10], rbx
0x1800dae45  mov     [rsp-18h+arg_18], rsi
0x1800dae4a  push    rbp
0x1800dae4b  push    rdi
0x1800dae4c  push    r14
0x1800dae4e  mov     rbp, rsp
0x1800dae51  sub     rsp, 70h
0x1800dae55  mov     rax, cs:__security_cookie
0x1800dae5c  xor     rax, rsp
0x1800dae5f  mov     [rbp+var_10], rax
0x1800dae63  mov     r14, rdx
0x1800dae66  mov     rsi, rcx
0x1800dae69  mov     [rbp+var_40], rcx
0x1800dae6d  mov     [rbp+var_48], 0
0x1800dae75  mov     [rbp+var_40], 0
0x1800dae7d  mov     [rbp+var_18], 0
0x1800dae85  mov     r9d, 30h ; '0'; unsigned int
0x1800dae8b  lea     r8d, [r9+1]; unsigned int
0x1800dae8f  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageLocation@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800dae96  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800dae9a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800dae9f  nop
0x1800daea0  lea     rdx, [rbp+var_40]
0x1800daea4  mov     rcx, [rbp+var_18]
0x1800daea8  call    ??$GetActivationFactory@V?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>>)
0x1800daead  mov     rcx, [rbp+18h]; this
0x1800daeb1  test    eax, eax
0x1800daeb3  jns     short loc_1800DAECA
0x1800daeb5  mov     r9d, eax; char *
0x1800daeb8  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800daebf  mov     edx, 32Ch; void *
0x1800daec4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800daeca  mov     rdi, [rbp+var_40]
0x1800daece  mov     rax, [rdi]
0x1800daed1  mov     rbx, [rax+60h]
0x1800daed5  lea     rcx, [rbp+var_48]
0x1800daed9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daede  lea     r8, [rbp+var_48]
0x1800daee2  mov     rdx, [r14]
0x1800daee5  mov     rcx, rdi
0x1800daee8  mov     rax, rbx
0x1800daeeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daef0  mov     rcx, [rbp+18h]; this
0x1800daef4  test    eax, eax
0x1800daef6  jns     short loc_1800DAF0D
0x1800daef8  mov     r9d, eax; char *
0x1800daefb  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800daf02  mov     edx, 32Eh; void *
0x1800daf07  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800daf0d  mov     [rbp+string], 0
0x1800daf15  mov     rdi, [rbp+var_48]
0x1800daf19  mov     rax, [rdi]
0x1800daf1c  mov     rbx, [rax+58h]
0x1800daf20  xor     edx, edx
0x1800daf22  lea     rcx, [rbp+string]
0x1800daf26  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800daf2b  lea     rdx, [rbp+string]
0x1800daf2f  mov     rcx, rdi
0x1800daf32  mov     rax, rbx
0x1800daf35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800daf3a  mov     rcx, [rbp+18h]; this
0x1800daf3e  test    eax, eax
0x1800daf40  jns     short loc_1800DAF57
0x1800daf42  mov     r9d, eax; char *
0x1800daf45  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appcompat\\inventory\\so"...
0x1800daf4c  mov     edx, 331h; void *
0x1800daf51  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800daf57  xor     edx, edx; length
0x1800daf59  mov     rcx, [rbp+string]; string
0x1800daf5d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800daf63  mov     rdx, rax
0x1800daf66  mov     rcx, rsi
0x1800daf69  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800daf6e  nop
0x1800daf6f  lea     rcx, [rbp+string]; this
0x1800daf73  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800daf78  nop
0x1800daf79  lea     rcx, [rbp+var_40]
0x1800daf7d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daf82  nop
0x1800daf83  lea     rcx, [rbp+var_48]
0x1800daf87  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800daf8c  mov     rax, rsi
0x1800daf8f  mov     rcx, [rbp+var_10]
0x1800daf93  xor     rcx, rsp; StackCookie
0x1800daf96  call    __security_check_cookie
0x1800daf9b  lea     r11, [rsp+70h+var_s0]
0x1800dafa0  mov     rbx, [r11+30h]
0x1800dafa4  mov     rsi, [r11+38h]
0x1800dafa8  mov     rsp, r11
0x1800dafab  pop     r14
0x1800dafad  pop     rdi
0x1800dafae  pop     rbp
0x1800dafaf  retn
```
