# Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::DeleteValue(Platform::String *,Platform::String *)

- ea: `0x18009a6a0`
- end: `0x18009a94d`
- name: `?DeleteValue@ConstraintIndexRegistryContainer@Search@ConstraintIndex@Cortana@@QEBAXPE$AAVString@Platform@@0@Z`
- size: `685`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180084140`

## callees

- `0x1800049e0`
- `0x18000616e`
- `0x18000617a`
- `0x18000619e`
- `0x18003b2f4`
- `0x18003fd04`
- `0x18003feb4`
- `0x18003fee0`
- `0x18003ff8c`
- `0x180086f1c`
- `0x180087acc`
- `0x180092490`
- `0x180092c54`
- `0x180092ec4`
- `0x1800942dc`
- `0x1800999f0`
- `0x18009a630`
- `0x18009a6a0`
- `0x18009a954`
- `0x18009ad38`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a8cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009a8cb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18009a8ff`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18009a8ff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a926`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009a926`

## string_xrefs

- `0x18009a8dc`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexRegistryContainer.cpp`
- `0x18009a910`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexRegistryContainer.cpp`
- `0x18009a93b`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexRegistryContainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
HRESULT __fastcall Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::DeleteValue(
        _QWORD *a1,
        __int64 a2,
        HSTRING a3)
{
  HRESULT v5; // eax
  HSTRING v6; // rdi
  HSTRING v7; // rbx
  HSTRING v8; // r14
  Cortana::ConstraintIndex::Search *v9; // rcx
  __int64 v10; // rdi
  HSTRING v11; // rbx
  HSTRING v12; // r13
  __int64 Factory; // rbx
  __int64 v14; // r12
  const WCHAR *StringRawBuffer_0; // rax
  unsigned int v17; // eax
  const WCHAR *v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-60h]
  HSTRING v22; // [rsp+30h] [rbp-50h]
  __int64 Results; // [rsp+40h] [rbp-40h]
  __int64 v24; // [rsp+40h] [rbp-40h]
  __int64 v25; // [rsp+48h] [rbp-38h]
  __int64 v26; // [rsp+48h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  string = 0;
  v5 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
  if ( v5 < 0 )
    __abi_WinRTraiseException(v5);
  v22 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(*a1);
  v6 = (HSTRING)Platform::String::Concat(v22, string);
  string = v6;
  v7 = (HSTRING)Platform::String::Concat(v6, 0);
  v8 = (HSTRING)__abi_winrt_ptrto_string_ctor(v7);
  WindowsDeleteString_0(v7);
  WindowsDeleteString_0(v6);
  WindowsDeleteString_0(v22);
  if ( Cortana::ConstraintIndex::Search::IsCShellSettingsApp(v9) )
  {
    v10 = Windows::Storage::ApplicationData::Current::get();
    v11 = (HSTRING)Windows::Storage::IApplicationData::LocalSettings::get(v10);
    string = v11;
    v12 = (HSTRING)__abi_winrt_ptr_ctor(v11);
    string = v12;
    __abi_winrt_ptr_dtor(v11);
    __abi_winrt_ptr_dtor(v10);
    Factory = WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(v12, v8, 0);
    v14 = __abi_winrt_ptr_ctor(Factory);
    __abi_winrt_ptr_dtor(Factory);
    Results = Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(v14);
    v25 = __abi_winrt_cast_to(
            0,
            Results,
            _uuidof__AU__IMap_PE_AAVString_Platform__PE_AAVObject_2__Collections_Foundation_Windows__);
    LOBYTE(Factory) = Windows::Foundation::Collections::IMap<Platform::String __gc *,Platform::Object __gc *>::HasKey(
                        v25,
                        a3);
    __abi_winrt_ptr_dtor(v25);
    __abi_winrt_ptr_dtor(Results);
    if ( (_BYTE)Factory )
    {
      v26 = Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(v14);
      v24 = __abi_winrt_cast_to(
              0,
              v26,
              _uuidof__AU__IMap_PE_AAVString_Platform__PE_AAVObject_2__Collections_Foundation_Windows__);
      SystemSettings::DataModel::ISettingsEnvironmentDatabase::SettingsEnvironmentChanged::remove(v24, a3);
      __abi_winrt_ptr_dtor(v24);
      __abi_winrt_ptr_dtor(v26);
    }
    __abi_winrt_ptr_dtor(v14);
    __abi_winrt_ptr_dtor(v12);
  }
  else
  {
    string = 0;
    StringRawBuffer_0 = WindowsGetStringRawBuffer_0(v8, 0);
    v17 = RegOpenKeyExW(HKEY_CURRENT_USER, StringRawBuffer_0, 0, 2u, (PHKEY)&string);
    if ( v17 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x46,
        (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexRegistryContainer.cpp",
        (const char *)v17,
        phkResult);
    v18 = WindowsGetStringRawBuffer_0(a3, 0);
    v19 = RegDeleteValueW((HKEY)string, v18);
    if ( v19 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x47,
        (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexRegistryContainer.cpp",
        (const char *)v19,
        phkResult);
    v20 = RegCloseKey((HKEY)string);
    if ( v20 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x48,
        (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexRegistryContainer.cpp",
        (const char *)v20,
        phkResult);
  }
  return WindowsDeleteString_0(v8);
}

```

## disassembly

```asm
0x18009a6a0  mov     [rsp-38h+arg_8], rbx
0x18009a6a5  push    rbp
0x18009a6a6  push    rsi
0x18009a6a7  push    rdi
0x18009a6a8  push    r12
0x18009a6aa  push    r13
0x18009a6ac  push    r14
0x18009a6ae  push    r15
0x18009a6b0  mov     rbp, rsp
0x18009a6b3  sub     rsp, 80h
0x18009a6ba  mov     rax, cs:__security_cookie
0x18009a6c1  xor     rax, rsp
0x18009a6c4  mov     [rbp+var_10], rax
0x18009a6c8  mov     r15, r8
0x18009a6cb  mov     rbx, rcx
0x18009a6ce  mov     [rbp+string], 0
0x18009a6d6  lea     r9, [rbp+string]; string
0x18009a6da  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18009a6de  mov     edx, 1; length
0x18009a6e3  lea     rcx, asc_180104F88; "\\"
0x18009a6ea  call    WindowsCreateStringReference_0
0x18009a6ef  test    eax, eax
0x18009a6f1  jns     short loc_18009A6FB
0x18009a6f3  mov     ecx, eax; int
0x18009a6f5  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18009a6fb  mov     rcx, [rbx]
0x18009a6fe  call    ?get@BaseRegistryPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(void)
0x18009a703  mov     rsi, rax
0x18009a706  mov     [rbp+var_50], rax
0x18009a70a  mov     rdx, [rbp+string]
0x18009a70e  mov     rcx, rax
0x18009a711  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009a716  mov     rdi, rax
0x18009a719  mov     [rbp+string], rax
0x18009a71d  xor     edx, edx
0x18009a71f  mov     rcx, rax
0x18009a722  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009a727  mov     rbx, rax
0x18009a72a  mov     [rbp+var_48], rax
0x18009a72e  mov     rcx, rax
0x18009a731  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009a736  mov     r14, rax
0x18009a739  mov     [rbp+var_48], rax
0x18009a73d  mov     rcx, rbx; string
0x18009a740  call    WindowsDeleteString_0
0x18009a745  nop
0x18009a746  mov     rcx, rdi; string
0x18009a749  call    WindowsDeleteString_0
0x18009a74e  nop
0x18009a74f  mov     rcx, rsi; string
0x18009a752  call    WindowsDeleteString_0
0x18009a757  nop
0x18009a758  call    ?IsCShellSettingsApp@Search@ConstraintIndex@Cortana@@YA_NXZ; Cortana::ConstraintIndex::Search::IsCShellSettingsApp(void)
0x18009a75d  test    al, al
0x18009a75f  jz      loc_18009A89D
0x18009a765  call    ?get@Current@ApplicationData@Storage@Windows@@SAPE$AAV234@XZ; Windows::Storage::ApplicationData::Current::get(void)
0x18009a76a  mov     rdi, rax
0x18009a76d  mov     [rbp+var_50], rax
0x18009a771  mov     rcx, rax
0x18009a774  call    ?get@LocalSettings@IApplicationData@Storage@Windows@@UE$AAAPE$AAVApplicationDataContainer@34@XZ; Windows::Storage::IApplicationData::LocalSettings::get(void)
0x18009a779  mov     rbx, rax
0x18009a77c  mov     [rbp+string], rax
0x18009a780  mov     rcx, rax
0x18009a783  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009a788  mov     r13, rax
0x18009a78b  mov     [rbp+string], rax
0x18009a78f  mov     rcx, rbx
0x18009a792  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a797  nop
0x18009a798  mov     rcx, rdi
0x18009a79b  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a7a0  nop
0x18009a7a1  xor     r8d, r8d
0x18009a7a4  mov     rdx, r14
0x18009a7a7  mov     rcx, r13
0x18009a7aa  call    ?GetFactory@IExtensionFactoryStatics@AppExtensions@ApplicationModel@WindowsUdk@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@0@Z; WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(Platform::String *,Platform::String *)
0x18009a7af  mov     rbx, rax
0x18009a7b2  mov     [rbp+var_50], rax
0x18009a7b6  mov     rcx, rax
0x18009a7b9  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009a7be  mov     r12, rax
0x18009a7c1  mov     [rbp+var_50], rax
0x18009a7c5  mov     rcx, rbx
0x18009a7c8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a7cd  nop
0x18009a7ce  mov     rcx, r12
0x18009a7d1  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x18009a7d6  mov     rsi, rax
0x18009a7d9  mov     [rbp+var_40], rax
0x18009a7dd  lea     r8, __uuidof_?AU?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@
0x18009a7e4  mov     rdx, rax
0x18009a7e7  xor     ecx, ecx
0x18009a7e9  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009a7ee  mov     rdi, rax
0x18009a7f1  mov     [rbp+var_38], rax
0x18009a7f5  mov     rdx, r15
0x18009a7f8  mov     rcx, rax
0x18009a7fb  call    ?HasKey@?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@UE$AAA_NPE$AAVString@Platform@@@Z; Windows::Foundation::Collections::IMap<Platform::String *,Platform::Object *>::HasKey(Platform::String *)
0x18009a800  mov     bl, al
0x18009a802  mov     rcx, rdi
0x18009a805  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a80a  nop
0x18009a80b  mov     rcx, rsi
0x18009a80e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a813  test    bl, bl
0x18009a815  jz      short loc_18009A85C
0x18009a817  mov     rcx, r12
0x18009a81a  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x18009a81f  mov     rdi, rax
0x18009a822  mov     [rbp+var_38], rax
0x18009a826  lea     r8, __uuidof_?AU?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@
0x18009a82d  mov     rdx, rax
0x18009a830  xor     ecx, ecx
0x18009a832  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009a837  mov     rbx, rax
0x18009a83a  mov     [rbp+var_40], rax
0x18009a83e  mov     rdx, r15
0x18009a841  mov     rcx, rax
0x18009a844  call    ?remove@SettingsEnvironmentChanged@ISettingsEnvironmentDatabase@DataModel@SystemSettings@@UE$AAAXVEventRegistrationToken@Foundation@Windows@@@Z; SystemSettings::DataModel::ISettingsEnvironmentDatabase::SettingsEnvironmentChanged::remove(Windows::Foundation::EventRegistrationToken)
0x18009a849  nop
0x18009a84a  mov     rcx, rbx
0x18009a84d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a852  nop
0x18009a853  mov     rcx, rdi
0x18009a856  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a85b  nop
0x18009a85c  mov     rcx, r12
0x18009a85f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a864  nop
0x18009a865  mov     rcx, r13
0x18009a868  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009a86d  nop
0x18009a86e  mov     rcx, r14; string
0x18009a871  call    WindowsDeleteString_0
0x18009a876  mov     rcx, [rbp+var_10]
0x18009a87a  xor     rcx, rsp; StackCookie
0x18009a87d  call    __security_check_cookie
0x18009a882  mov     rbx, [rsp+80h+arg_8]
0x18009a88a  add     rsp, 80h
0x18009a891  pop     r15
0x18009a893  pop     r14
0x18009a895  pop     r13
0x18009a897  pop     r12
0x18009a899  pop     rdi
0x18009a89a  pop     rsi
0x18009a89b  pop     rbp
0x18009a89c  retn
0x18009a89d  mov     [rbp+string], 0
0x18009a8a5  xor     edx, edx; length
0x18009a8a7  mov     rcx, r14; string
0x18009a8aa  call    WindowsGetStringRawBuffer_0
0x18009a8af  lea     rcx, [rbp+string]
0x18009a8b3  mov     qword ptr [rsp+80h+phkResult], rcx; unsigned int
0x18009a8b8  mov     r9d, 2; samDesired
0x18009a8be  xor     r8d, r8d; ulOptions
0x18009a8c1  mov     rdx, rax; lpSubKey
0x18009a8c4  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009a8cb  call    cs:__imp_RegOpenKeyExW
0x18009a8d1  mov     rcx, [rbp+38h]; this
0x18009a8d5  test    eax, eax
0x18009a8d7  jz      short loc_18009A8EE
0x18009a8d9  mov     r9d, eax; char *
0x18009a8dc  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\cortana\\constraint"...
0x18009a8e3  mov     edx, 46h ; 'F'; void *
0x18009a8e8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18009a8ee  xor     edx, edx; length
0x18009a8f0  mov     rcx, r15; string
0x18009a8f3  call    WindowsGetStringRawBuffer_0
0x18009a8f8  mov     rdx, rax; lpValueName
0x18009a8fb  mov     rcx, [rbp+string]; hKey
0x18009a8ff  call    cs:__imp_RegDeleteValueW
0x18009a905  mov     rcx, [rbp+38h]; this
0x18009a909  test    eax, eax
0x18009a90b  jz      short loc_18009A922
0x18009a90d  mov     r9d, eax; char *
0x18009a910  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\cortana\\constraint"...
0x18009a917  mov     edx, 47h ; 'G'; void *
0x18009a91c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18009a922  mov     rcx, [rbp+string]; hKey
0x18009a926  call    cs:__imp_RegCloseKey
0x18009a92c  mov     rcx, [rbp+38h]; this
0x18009a930  test    eax, eax
0x18009a932  jz      loc_18009A86E
0x18009a938  mov     r9d, eax; char *
0x18009a93b  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\cortana\\constraint"...
0x18009a942  mov     edx, 48h ; 'H'; void *
0x18009a947  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
