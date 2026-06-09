# Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::WriteStringValue(Platform::String *,Platform::String *,Platform::String *)

- ea: `0x18009af90`
- end: `0x18009b1e1`
- name: `?WriteStringValue@ConstraintIndexRegistryContainer@Search@ConstraintIndex@Cortana@@QEBAXPE$AAVString@Platform@@00@Z`
- size: `593`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180084140`
- `0x180096a68`
- `0x1800a6a94`
- `0x1800a6b24`
- `0x1800a6bb4`
- `0x1800a6c44`
- `0x1800cd570`

## callees

- `0x1800049e0`
- `0x18000616e`
- `0x18000617a`
- `0x180006192`
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
- `0x18009a9a8`
- `0x18009af90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009b1ba`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18009b1ba`
- `wincorlib!?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z` at `0x18009b0f5`
- `wincorlib!?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z` at `0x18009b0f5`

## string_xrefs

- `0x18009b1cf`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexRegistryContainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
HRESULT __fastcall Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::WriteStringValue(
        _QWORD *a1,
        __int64 a2,
        HSTRING a3,
        HSTRING a4)
{
  HRESULT v7; // eax
  HSTRING v8; // rdi
  HSTRING v9; // rbx
  HSTRING v10; // r12
  Cortana::ConstraintIndex::Search *v11; // rcx
  __int64 v12; // rdi
  HSTRING v13; // rbx
  HSTRING v14; // r15
  __int64 Factory; // rbx
  DWORD cbData; // esi
  PCWSTR StringRawBuffer_0; // rdi
  const WCHAR *v19; // rbx
  const WCHAR *v20; // rax
  unsigned int v21; // eax
  unsigned int lpData; // [rsp+20h] [rbp-49h]
  HSTRING v23; // [rsp+30h] [rbp-39h]
  __int64 v24; // [rsp+30h] [rbp-39h]
  __int64 Results; // [rsp+48h] [rbp-21h]
  __int64 v27; // [rsp+50h] [rbp-19h]
  __int64 v28; // [rsp+58h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  string = 0;
  v7 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
  if ( v7 < 0 )
    __abi_WinRTraiseException(v7);
  v23 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(*a1);
  v8 = (HSTRING)Platform::String::Concat(v23, string);
  string = v8;
  v9 = (HSTRING)Platform::String::Concat(v8, 0);
  v10 = (HSTRING)__abi_winrt_ptrto_string_ctor(v9);
  WindowsDeleteString_0(v9);
  WindowsDeleteString_0(v8);
  WindowsDeleteString_0(v23);
  if ( Cortana::ConstraintIndex::Search::IsCShellSettingsApp(v11) )
  {
    v12 = Windows::Storage::ApplicationData::Current::get();
    v13 = (HSTRING)Windows::Storage::IApplicationData::LocalSettings::get(v12);
    string = v13;
    v14 = (HSTRING)__abi_winrt_ptr_ctor(v13);
    string = v14;
    __abi_winrt_ptr_dtor(v13);
    __abi_winrt_ptr_dtor(v12);
    Factory = WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(v14, v10, 0);
    v24 = __abi_winrt_ptr_ctor(Factory);
    __abi_winrt_ptr_dtor(Factory);
    Results = Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(v24);
    v27 = __abi_winrt_cast_to(
            0,
            Results,
            _uuidof__AU__IMap_PE_AAVString_Platform__PE_AAVObject_2__Collections_Foundation_Windows__);
    v28 = __abi_details::__abi_cast_String_to_Object(a4);
    Windows::Foundation::Collections::IMap<Platform::String __gc *,Platform::Object __gc *>::Insert(v27, a3, v28);
    __abi_winrt_ptr_dtor(v28);
    __abi_winrt_ptr_dtor(v27);
    __abi_winrt_ptr_dtor(Results);
    __abi_winrt_ptr_dtor(v24);
    __abi_winrt_ptr_dtor(v14);
  }
  else
  {
    cbData = 2 * _Platform_WindowsGetStringLen(a4) + 2;
    StringRawBuffer_0 = WindowsGetStringRawBuffer_0(a4, 0);
    v19 = WindowsGetStringRawBuffer_0(a3, 0);
    v20 = WindowsGetStringRawBuffer_0(v10, 0);
    v21 = RegSetKeyValueW(HKEY_CURRENT_USER, v20, v19, 1u, StringRawBuffer_0, cbData);
    if ( v21 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xD1,
        (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexRegistryContainer.cpp",
        (const char *)v21,
        lpData);
  }
  return WindowsDeleteString_0(v10);
}

```

## disassembly

```asm
0x18009af90  mov     [rsp-8+arg_8], rbx
0x18009af95  push    rbp
0x18009af96  push    rsi
0x18009af97  push    rdi
0x18009af98  push    r12
0x18009af9a  push    r13
0x18009af9c  push    r14
0x18009af9e  push    r15
0x18009afa0  lea     rbp, [rsp-27h]
0x18009afa5  sub     rsp, 90h
0x18009afac  mov     rax, cs:__security_cookie
0x18009afb3  xor     rax, rsp
0x18009afb6  mov     [rbp+57h+var_40], rax
0x18009afba  mov     r13, r9
0x18009afbd  mov     r14, r8
0x18009afc0  mov     [rbp+57h+var_88], r8
0x18009afc4  mov     rbx, rcx
0x18009afc7  mov     [rbp+57h+string], 0
0x18009afcf  lea     r9, [rbp+57h+string]; string
0x18009afd3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18009afd7  mov     r15d, 1
0x18009afdd  mov     edx, r15d; length
0x18009afe0  lea     rcx, asc_180104F88; "\\"
0x18009afe7  call    WindowsCreateStringReference_0
0x18009afec  test    eax, eax
0x18009afee  jns     short loc_18009AFF8
0x18009aff0  mov     ecx, eax; int
0x18009aff2  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18009aff8  mov     rcx, [rbx]
0x18009affb  call    ?get@BaseRegistryPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(void)
0x18009b000  mov     rsi, rax
0x18009b003  mov     [rbp+57h+var_90], rax
0x18009b007  mov     rdx, [rbp+57h+string]
0x18009b00b  mov     rcx, rax
0x18009b00e  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009b013  mov     rdi, rax
0x18009b016  mov     [rbp+57h+string], rax
0x18009b01a  xor     edx, edx
0x18009b01c  mov     rcx, rax
0x18009b01f  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009b024  mov     rbx, rax
0x18009b027  mov     [rbp+57h+var_80], rax
0x18009b02b  mov     rcx, rax
0x18009b02e  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009b033  mov     r12, rax
0x18009b036  mov     [rbp+57h+var_80], rax
0x18009b03a  mov     rcx, rbx; string
0x18009b03d  call    WindowsDeleteString_0
0x18009b042  nop
0x18009b043  mov     rcx, rdi; string
0x18009b046  call    WindowsDeleteString_0
0x18009b04b  nop
0x18009b04c  mov     rcx, rsi; string
0x18009b04f  call    WindowsDeleteString_0
0x18009b054  nop
0x18009b055  call    ?IsCShellSettingsApp@Search@ConstraintIndex@Cortana@@YA_NXZ; Cortana::ConstraintIndex::Search::IsCShellSettingsApp(void)
0x18009b05a  test    al, al
0x18009b05c  jz      loc_18009B16E
0x18009b062  call    ?get@Current@ApplicationData@Storage@Windows@@SAPE$AAV234@XZ; Windows::Storage::ApplicationData::Current::get(void)
0x18009b067  mov     rdi, rax
0x18009b06a  mov     [rbp+57h+var_90], rax
0x18009b06e  mov     rcx, rax
0x18009b071  call    ?get@LocalSettings@IApplicationData@Storage@Windows@@UE$AAAPE$AAVApplicationDataContainer@34@XZ; Windows::Storage::IApplicationData::LocalSettings::get(void)
0x18009b076  mov     rbx, rax
0x18009b079  mov     [rbp+57h+string], rax
0x18009b07d  mov     rcx, rax
0x18009b080  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009b085  mov     r15, rax
0x18009b088  mov     [rbp+57h+string], rax
0x18009b08c  mov     rcx, rbx
0x18009b08f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b094  nop
0x18009b095  mov     rcx, rdi
0x18009b098  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b09d  nop
0x18009b09e  xor     r8d, r8d
0x18009b0a1  mov     rdx, r12
0x18009b0a4  mov     rcx, r15
0x18009b0a7  call    ?GetFactory@IExtensionFactoryStatics@AppExtensions@ApplicationModel@WindowsUdk@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@0@Z; WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(Platform::String *,Platform::String *)
0x18009b0ac  mov     rbx, rax
0x18009b0af  mov     [rbp+57h+var_90], rax
0x18009b0b3  mov     rcx, rax
0x18009b0b6  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009b0bb  mov     r14, rax
0x18009b0be  mov     [rbp+57h+var_90], rax
0x18009b0c2  mov     rcx, rbx
0x18009b0c5  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b0ca  nop
0x18009b0cb  mov     rcx, r14
0x18009b0ce  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x18009b0d3  mov     rsi, rax
0x18009b0d6  mov     [rbp+57h+var_78], rax
0x18009b0da  lea     r8, __uuidof_?AU?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@
0x18009b0e1  mov     rdx, rax
0x18009b0e4  xor     ecx, ecx
0x18009b0e6  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009b0eb  mov     rdi, rax
0x18009b0ee  mov     [rbp+57h+var_70], rax
0x18009b0f2  mov     rcx, r13
0x18009b0f5  call    cs:__imp_?__abi_cast_String_to_Object@__abi_details@@YAPE$AAVObject@Platform@@PE$AAVString@3@@Z; __abi_details::__abi_cast_String_to_Object(Platform::String *)
0x18009b0fb  mov     rbx, rax
0x18009b0fe  mov     [rbp+57h+var_68], rax
0x18009b102  mov     r8, rax
0x18009b105  mov     rdx, [rbp+57h+var_88]
0x18009b109  mov     rcx, rdi
0x18009b10c  call    ?Insert@?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@UE$AAA_NPE$AAVString@Platform@@PE$AAVObject@6@@Z; Windows::Foundation::Collections::IMap<Platform::String *,Platform::Object *>::Insert(Platform::String *,Platform::Object *)
0x18009b111  nop
0x18009b112  mov     rcx, rbx
0x18009b115  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b11a  nop
0x18009b11b  mov     rcx, rdi
0x18009b11e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b123  nop
0x18009b124  mov     rcx, rsi
0x18009b127  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b12c  nop
0x18009b12d  mov     rcx, r14
0x18009b130  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b135  nop
0x18009b136  mov     rcx, r15
0x18009b139  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009b13e  nop
0x18009b13f  mov     rcx, r12; string
0x18009b142  call    WindowsDeleteString_0
0x18009b147  mov     rcx, [rbp+57h+var_40]
0x18009b14b  xor     rcx, rsp; StackCookie
0x18009b14e  call    __security_check_cookie
0x18009b153  mov     rbx, [rsp+0C0h+arg_8]
0x18009b15b  add     rsp, 90h
0x18009b162  pop     r15
0x18009b164  pop     r14
0x18009b166  pop     r13
0x18009b168  pop     r12
0x18009b16a  pop     rdi
0x18009b16b  pop     rsi
0x18009b16c  pop     rbp
0x18009b16d  retn
0x18009b16e  mov     rcx, r13; string
0x18009b171  call    __Platform_WindowsGetStringLen
0x18009b176  lea     esi, ds:2[rax*2]
0x18009b17d  xor     edx, edx; length
0x18009b17f  mov     rcx, r13; string
0x18009b182  call    WindowsGetStringRawBuffer_0
0x18009b187  mov     rdi, rax
0x18009b18a  xor     edx, edx; length
0x18009b18c  mov     rcx, r14; string
0x18009b18f  call    WindowsGetStringRawBuffer_0
0x18009b194  mov     rbx, rax
0x18009b197  xor     edx, edx; length
0x18009b199  mov     rcx, r12; string
0x18009b19c  call    WindowsGetStringRawBuffer_0
0x18009b1a1  mov     [rsp+0C0h+cbData], esi; cbData
0x18009b1a5  mov     [rsp+0C0h+lpData], rdi; unsigned int
0x18009b1aa  mov     r9d, r15d; dwType
0x18009b1ad  mov     r8, rbx; lpValueName
0x18009b1b0  mov     rdx, rax; lpSubKey
0x18009b1b3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18009b1ba  call    cs:__imp_RegSetKeyValueW
0x18009b1c0  mov     rcx, [rbp+5Fh]; this
0x18009b1c4  test    eax, eax
0x18009b1c6  jz      loc_18009B13F
0x18009b1cc  mov     r9d, eax; char *
0x18009b1cf  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\cortana\\constraint"...
0x18009b1d6  mov     edx, 0D1h; void *
0x18009b1db  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
