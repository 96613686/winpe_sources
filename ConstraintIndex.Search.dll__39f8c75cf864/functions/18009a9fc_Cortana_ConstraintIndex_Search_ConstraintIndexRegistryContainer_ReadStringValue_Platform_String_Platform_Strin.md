# Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::ReadStringValue(Platform::String *,Platform::String *)

- ea: `0x18009a9fc`
- end: `0x18009ad31`
- name: `?ReadStringValue@ConstraintIndexRegistryContainer@Search@ConstraintIndex@Cortana@@QEBAPE$AAVString@Platform@@PE$AAV56@0@Z`
- size: `821`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180084140`
- `0x1800968f4`
- `0x1800a5238`
- `0x1800a5330`
- `0x1800a5ed8`
- `0x1800a5fd0`
- `0x1800a60c8`
- `0x1800a61c4`
- `0x1800a6440`
- `0x1800ce9b0`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18000616e`
- `0x18000617a`
- `0x18000619e`
- `0x18003a5f4`
- `0x18003b2f4`
- `0x18003b6f8`
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
- `0x18009a954`
- `0x18009a9fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009acac`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009acac`
- `wincorlib!?__abi_cast_Object_to_String@__abi_details@@YAPE$AAVString@Platform@@_NPE$AAVObject@3@@Z` at `0x18009abc1`
- `wincorlib!?__abi_cast_Object_to_String@__abi_details@@YAPE$AAVString@Platform@@_NPE$AAVObject@3@@Z` at `0x18009abc1`

## string_xrefs

- `0x18009acc0`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexRegistryContainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::ReadStringValue(
        _QWORD *a1,
        __int64 a2,
        HSTRING a3)
{
  HRESULT v5; // eax
  HSTRING v6; // rdi
  HSTRING v7; // rbx
  HSTRING v8; // r15
  Cortana::ConstraintIndex::Search *v9; // rcx
  __int64 v10; // rcx
  HSTRING v11; // rdi
  __int64 v12; // rbx
  HSTRING Factory; // rbx
  __int64 v14; // r13
  HSTRING Results; // rsi
  HSTRING v16; // rsi
  __int64 v17; // r12
  HRESULT v18; // eax
  const WCHAR *StringRawBuffer_0; // rbx
  const WCHAR *v21; // rax
  unsigned int ValueW; // eax
  __int64 v23; // rbx
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  HSTRING v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+40h] [rbp-C0h]
  HSTRING v27; // [rsp+48h] [rbp-B8h]
  HSTRING v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-90h] BYREF
  HSTRING_HEADER v33; // [rsp+88h] [rbp-78h] BYREF
  HSTRING string[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pvData[528]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  string[0] = 0;
  v5 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, string);
  if ( v5 < 0 )
    __abi_WinRTraiseException(v5);
  v25 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(*a1);
  v6 = (HSTRING)Platform::String::Concat(v25, string[0]);
  string[0] = v6;
  v7 = (HSTRING)Platform::String::Concat(v6, 0);
  v8 = (HSTRING)__abi_winrt_ptrto_string_ctor(v7);
  WindowsDeleteString_0(v7);
  WindowsDeleteString_0(v6);
  WindowsDeleteString_0(v25);
  if ( Cortana::ConstraintIndex::Search::IsCShellSettingsApp(v9) )
  {
    v11 = (HSTRING)Windows::Storage::ApplicationData::Current::get(v10);
    string[0] = v11;
    v12 = Windows::Storage::IApplicationData::LocalSettings::get(v11);
    v26 = __abi_winrt_ptr_ctor(v12);
    __abi_winrt_ptr_dtor(v12);
    __abi_winrt_ptr_dtor(v11);
    Factory = (HSTRING)WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(v26, v8, 0);
    string[0] = Factory;
    v14 = __abi_winrt_ptr_ctor(Factory);
    __abi_winrt_ptr_dtor(Factory);
    Results = (HSTRING)Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(v14);
    string[0] = Results;
    v29 = __abi_winrt_cast_to(
            0,
            Results,
            _uuidof__AU__IMap_PE_AAVString_Platform__PE_AAVObject_2__Collections_Foundation_Windows__);
    LOBYTE(Factory) = Windows::Foundation::Collections::IMap<Platform::String __gc *,Platform::Object __gc *>::HasKey(
                        v29,
                        a3);
    __abi_winrt_ptr_dtor(v29);
    __abi_winrt_ptr_dtor(Results);
    if ( (_BYTE)Factory )
    {
      v30 = Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(v14);
      v16 = (HSTRING)__abi_winrt_cast_to(
                       0,
                       v30,
                       _uuidof__AU__IMap_PE_AAVString_Platform__PE_AAVObject_2__Collections_Foundation_Windows__);
      string[0] = v16;
      v31 = Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue __gc *>::GetAt(v16, a3);
      v27 = (HSTRING)__abi_details::__abi_cast_Object_to_String(0, v31);
      v17 = __abi_winrt_ptrto_string_ctor(v27);
      WindowsDeleteString_0(v27);
      __abi_winrt_ptr_dtor(v31);
      __abi_winrt_ptr_dtor(v16);
      __abi_winrt_ptr_dtor(v30);
    }
    else
    {
      string[0] = 0;
      v18 = WindowsCreateStringReference_0(&LocaleName, 0, &v33, string);
      if ( v18 < 0 )
        __abi_WinRTraiseException(v18);
      v17 = __abi_winrt_ptrto_string_ctor(string[0]);
    }
    __abi_winrt_ptr_dtor(v14);
    __abi_winrt_ptr_dtor(v26);
    WindowsDeleteString_0(v8);
    return v17;
  }
  else
  {
    memset_0(pvData, 0, 0x208u);
    LODWORD(string[0]) = 520;
    StringRawBuffer_0 = WindowsGetStringRawBuffer_0(a3, 0);
    v21 = WindowsGetStringRawBuffer_0(v8, 0);
    ValueW = RegGetValueW(HKEY_CURRENT_USER, v21, StringRawBuffer_0, 2u, 0, pvData, (LPDWORD)string);
    if ( ValueW )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x6A,
        (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexRegistryContainer.cpp",
        (const char *)ValueW,
        pdwType);
    v28 = (HSTRING)Platform::String::String(retaddr, pvData);
    v23 = __abi_winrt_ptrto_string_ctor(v28);
    WindowsDeleteString_0(v28);
    WindowsDeleteString_0(v8);
    return v23;
  }
}

```

## disassembly

```asm
0x18009a9fc  mov     [rsp-8+arg_8], rbx
0x18009aa01  push    rbp
0x18009aa02  push    rsi
0x18009aa03  push    rdi
0x18009aa04  push    r12
0x18009aa06  push    r13
0x18009aa08  push    r14
0x18009aa0a  push    r15
0x18009aa0c  lea     rbp, [rsp-1D0h]
0x18009aa14  sub     rsp, 2D0h
0x18009aa1b  mov     rax, cs:__security_cookie
0x18009aa22  xor     rax, rsp
0x18009aa25  mov     [rbp+200h+var_40], rax
0x18009aa2c  mov     r12, r8
0x18009aa2f  mov     rbx, rcx
0x18009aa32  xor     r14d, r14d
0x18009aa35  mov     [rbp+200h+string], r14
0x18009aa39  lea     r9, [rbp+200h+string]; string
0x18009aa3d  lea     r8, [rsp+300h+hstringHeader]; hstringHeader
0x18009aa42  lea     edx, [r14+1]; length
0x18009aa46  lea     rcx, asc_180104F88; "\\"
0x18009aa4d  call    WindowsCreateStringReference_0
0x18009aa52  test    eax, eax
0x18009aa54  jns     short loc_18009AA5E
0x18009aa56  mov     ecx, eax; int
0x18009aa58  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18009aa5e  mov     rcx, [rbx]
0x18009aa61  call    ?get@BaseRegistryPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(void)
0x18009aa66  mov     rsi, rax
0x18009aa69  mov     [rsp+300h+var_2C0], rax
0x18009aa6e  mov     rdx, [rbp+200h+string]
0x18009aa72  mov     rcx, rax
0x18009aa75  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009aa7a  mov     rdi, rax
0x18009aa7d  mov     [rbp+200h+string], rax
0x18009aa81  xor     edx, edx
0x18009aa83  mov     rcx, rax
0x18009aa86  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009aa8b  mov     rbx, rax
0x18009aa8e  mov     [rsp+300h+var_2B0], rax
0x18009aa93  mov     rcx, rax
0x18009aa96  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009aa9b  mov     r15, rax
0x18009aa9e  mov     [rsp+300h+var_2B0], rax
0x18009aaa3  mov     rcx, rbx; string
0x18009aaa6  call    WindowsDeleteString_0
0x18009aaab  nop
0x18009aaac  mov     rcx, rdi; string
0x18009aaaf  call    WindowsDeleteString_0
0x18009aab4  nop
0x18009aab5  mov     rcx, rsi; string
0x18009aab8  call    WindowsDeleteString_0
0x18009aabd  nop
0x18009aabe  call    ?IsCShellSettingsApp@Search@ConstraintIndex@Cortana@@YA_NXZ; Cortana::ConstraintIndex::Search::IsCShellSettingsApp(void)
0x18009aac3  test    al, al
0x18009aac5  jz      loc_18009AC55
0x18009aacb  call    ?get@Current@ApplicationData@Storage@Windows@@SAPE$AAV234@XZ; Windows::Storage::ApplicationData::Current::get(void)
0x18009aad0  mov     rdi, rax
0x18009aad3  mov     [rbp+200h+string], rax
0x18009aad7  mov     rcx, rax
0x18009aada  call    ?get@LocalSettings@IApplicationData@Storage@Windows@@UE$AAAPE$AAVApplicationDataContainer@34@XZ; Windows::Storage::IApplicationData::LocalSettings::get(void)
0x18009aadf  mov     rbx, rax
0x18009aae2  mov     [rsp+300h+var_2C0], rax
0x18009aae7  mov     rcx, rax
0x18009aaea  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009aaef  mov     rsi, rax
0x18009aaf2  mov     [rsp+300h+var_2C0], rax
0x18009aaf7  mov     rcx, rbx
0x18009aafa  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009aaff  nop
0x18009ab00  mov     rcx, rdi
0x18009ab03  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ab08  nop
0x18009ab09  xor     r8d, r8d
0x18009ab0c  mov     rdx, r15
0x18009ab0f  mov     rcx, rsi
0x18009ab12  call    ?GetFactory@IExtensionFactoryStatics@AppExtensions@ApplicationModel@WindowsUdk@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@0@Z; WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(Platform::String *,Platform::String *)
0x18009ab17  mov     rbx, rax
0x18009ab1a  mov     [rbp+200h+string], rax
0x18009ab1e  mov     rcx, rax
0x18009ab21  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009ab26  mov     r13, rax
0x18009ab29  mov     [rsp+300h+var_2A0], rax
0x18009ab2e  mov     rcx, rbx
0x18009ab31  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ab36  nop
0x18009ab37  mov     rcx, r13
0x18009ab3a  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x18009ab3f  mov     rsi, rax
0x18009ab42  mov     [rbp+200h+string], rax
0x18009ab46  lea     r8, __uuidof_?AU?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@
0x18009ab4d  mov     rdx, rax
0x18009ab50  xor     ecx, ecx
0x18009ab52  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009ab57  mov     rdi, rax
0x18009ab5a  mov     [rsp+300h+var_2A8], rax
0x18009ab5f  mov     rdx, r12
0x18009ab62  mov     rcx, rax
0x18009ab65  call    ?HasKey@?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@UE$AAA_NPE$AAVString@Platform@@@Z; Windows::Foundation::Collections::IMap<Platform::String *,Platform::Object *>::HasKey(Platform::String *)
0x18009ab6a  mov     bl, al
0x18009ab6c  mov     rcx, rdi
0x18009ab6f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ab74  nop
0x18009ab75  mov     rcx, rsi
0x18009ab78  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ab7d  test    bl, bl
0x18009ab7f  jz      short loc_18009ABFF
0x18009ab81  mov     rcx, r13
0x18009ab84  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x18009ab89  mov     r14, rax
0x18009ab8c  mov     [rsp+300h+var_2A8], rax
0x18009ab91  lea     r8, __uuidof_?AU?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@
0x18009ab98  mov     rdx, rax
0x18009ab9b  xor     ecx, ecx
0x18009ab9d  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009aba2  mov     rsi, rax
0x18009aba5  mov     [rbp+200h+string], rax
0x18009aba9  mov     rdx, r12
0x18009abac  mov     rcx, rax
0x18009abaf  call    ?GetAt@?$IVector@PE$AAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@UE$AAAPE$AAUIJsonValue@Json@Data@4@I@Z; Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>::GetAt(uint)
0x18009abb4  mov     rdi, rax
0x18009abb7  mov     [rsp+300h+var_298], rax
0x18009abbc  mov     rdx, rax
0x18009abbf  xor     ecx, ecx
0x18009abc1  call    cs:__imp_?__abi_cast_Object_to_String@__abi_details@@YAPE$AAVString@Platform@@_NPE$AAVObject@3@@Z; __abi_details::__abi_cast_Object_to_String(bool,Platform::Object *)
0x18009abc7  mov     rbx, rax
0x18009abca  mov     [rsp+300h+var_2B8], rax
0x18009abcf  mov     rcx, rax
0x18009abd2  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009abd7  mov     r12, rax
0x18009abda  mov     rcx, rbx; string
0x18009abdd  call    WindowsDeleteString_0
0x18009abe2  nop
0x18009abe3  mov     rcx, rdi
0x18009abe6  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009abeb  nop
0x18009abec  mov     rcx, rsi
0x18009abef  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009abf4  nop
0x18009abf5  mov     rcx, r14
0x18009abf8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009abfd  jmp     short loc_18009AC31
0x18009abff  mov     [rbp+200h+string], r14
0x18009ac03  lea     r9, [rbp+200h+string]; string
0x18009ac07  lea     r8, [rbp+200h+var_278]; hstringHeader
0x18009ac0b  xor     edx, edx; length
0x18009ac0d  lea     rcx, LocaleName; sourceString
0x18009ac14  call    WindowsCreateStringReference_0
0x18009ac19  test    eax, eax
0x18009ac1b  jns     short loc_18009AC25
0x18009ac1d  mov     ecx, eax; int
0x18009ac1f  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18009ac25  mov     rcx, [rbp+200h+string]
0x18009ac29  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009ac2e  mov     r12, rax
0x18009ac31  mov     rcx, r13
0x18009ac34  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ac39  nop
0x18009ac3a  mov     rcx, [rsp+300h+var_2C0]
0x18009ac3f  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ac44  nop
0x18009ac45  mov     rcx, r15; string
0x18009ac48  call    WindowsDeleteString_0
0x18009ac4d  mov     rax, r12
0x18009ac50  jmp     loc_18009AD07
0x18009ac55  mov     ebx, 208h
0x18009ac5a  mov     r8d, ebx; Size
0x18009ac5d  xor     edx, edx; Val
0x18009ac5f  lea     rcx, [rbp+200h+var_250]; void *
0x18009ac63  call    memset_0
0x18009ac68  mov     dword ptr [rbp+200h+string], ebx
0x18009ac6b  xor     edx, edx; length
0x18009ac6d  mov     rcx, r12; string
0x18009ac70  call    WindowsGetStringRawBuffer_0
0x18009ac75  mov     rbx, rax
0x18009ac78  xor     edx, edx; length
0x18009ac7a  mov     rcx, r15; string
0x18009ac7d  call    WindowsGetStringRawBuffer_0
0x18009ac82  lea     rcx, [rbp+200h+string]
0x18009ac86  mov     [rsp+300h+pcbData], rcx; pcbData
0x18009ac8b  lea     rcx, [rbp+200h+var_250]
0x18009ac8f  mov     [rsp+300h+pvData], rcx; pvData
0x18009ac94  mov     [rsp+300h+pdwType], r14; unsigned int
0x18009ac99  mov     r9d, 2; dwFlags
0x18009ac9f  mov     r8, rbx; lpValue
0x18009aca2  mov     rdx, rax; lpSubKey
0x18009aca5  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18009acac  call    cs:__imp_RegGetValueW
0x18009acb2  mov     rcx, [rbp+208h]; this
0x18009acb9  test    eax, eax
0x18009acbb  jz      short loc_18009ACD2
0x18009acbd  mov     r9d, eax; char *
0x18009acc0  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\cortana\\constraint"...
0x18009acc7  mov     edx, 6Ah ; 'j'; void *
0x18009accc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18009acd2  mov     [rsp+300h+var_2B8], r14
0x18009acd7  lea     rdx, [rbp+200h+var_250]
0x18009acdb  call    ??0String@Platform@@QE$AAA@PEB_W@Z; Platform::String::String(wchar_t const *)
0x18009ace0  mov     rdi, rax
0x18009ace3  mov     [rsp+300h+var_2B8], rax
0x18009ace8  mov     rcx, rax
0x18009aceb  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009acf0  mov     rbx, rax
0x18009acf3  mov     rcx, rdi; string
0x18009acf6  call    WindowsDeleteString_0
0x18009acfb  nop
0x18009acfc  mov     rcx, r15; string
0x18009acff  call    WindowsDeleteString_0
0x18009ad04  mov     rax, rbx
0x18009ad07  mov     rcx, [rbp+200h+var_40]
0x18009ad0e  xor     rcx, rsp; StackCookie
0x18009ad11  call    __security_check_cookie
0x18009ad16  mov     rbx, [rsp+300h+arg_8]
0x18009ad1e  add     rsp, 2D0h
0x18009ad25  pop     r15
0x18009ad27  pop     r14
0x18009ad29  pop     r13
0x18009ad2b  pop     r12
0x18009ad2d  pop     rdi
0x18009ad2e  pop     rsi
0x18009ad2f  pop     rbp
0x18009ad30  retn
```
