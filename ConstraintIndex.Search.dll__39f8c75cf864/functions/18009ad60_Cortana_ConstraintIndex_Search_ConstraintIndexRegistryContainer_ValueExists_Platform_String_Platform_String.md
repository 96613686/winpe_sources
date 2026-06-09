# Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::ValueExists(Platform::String *,Platform::String *)

- ea: `0x18009ad60`
- end: `0x18009af89`
- name: `?ValueExists@ConstraintIndexRegistryContainer@Search@ConstraintIndex@Cortana@@QEBA_NPE$AAVString@Platform@@0@Z`
- size: `553`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `10`
- callee_count: `19`
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
- `0x18009a954`
- `0x18009ad60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009af2d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18009af2d`

## string_xrefs

- `0x18009af42`: `shellcommon\shell\cortana\constraintindex\src\Search\ConstraintIndexRegistryContainer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char __fastcall Cortana::ConstraintIndex::Search::ConstraintIndexRegistryContainer::ValueExists(
        _QWORD *a1,
        __int64 a2,
        HSTRING a3)
{
  HRESULT v5; // eax
  HSTRING v6; // rdi
  HSTRING v7; // rbx
  HSTRING v8; // r12
  Cortana::ConstraintIndex::Search *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdi
  HSTRING v12; // rbx
  HSTRING v13; // r15
  __int64 Factory; // rbx
  const WCHAR *StringRawBuffer_0; // rbx
  const WCHAR *v17; // rax
  LSTATUS ValueW; // eax
  bool v19; // bl
  unsigned int pdwType; // [rsp+20h] [rbp-49h]
  HSTRING v21; // [rsp+40h] [rbp-29h]
  __int64 v22; // [rsp+40h] [rbp-29h]
  __int64 Results; // [rsp+50h] [rbp-19h]
  __int64 v24; // [rsp+58h] [rbp-11h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-9h] BYREF
  HSTRING string; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  string = 0;
  v5 = WindowsCreateStringReference_0(L"\\", 1u, &hstringHeader, &string);
  if ( v5 < 0 )
    __abi_WinRTraiseException(v5);
  v21 = (HSTRING)Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(*a1);
  v6 = (HSTRING)Platform::String::Concat(v21, string);
  string = v6;
  v7 = (HSTRING)Platform::String::Concat(v6, 0);
  v8 = (HSTRING)__abi_winrt_ptrto_string_ctor(v7);
  WindowsDeleteString_0(v7);
  WindowsDeleteString_0(v6);
  WindowsDeleteString_0(v21);
  if ( Cortana::ConstraintIndex::Search::IsCShellSettingsApp(v9) )
  {
    v11 = Windows::Storage::ApplicationData::Current::get(v10);
    v12 = (HSTRING)Windows::Storage::IApplicationData::LocalSettings::get(v11);
    string = v12;
    v13 = (HSTRING)__abi_winrt_ptr_ctor(v12);
    string = v13;
    __abi_winrt_ptr_dtor(v12);
    __abi_winrt_ptr_dtor(v11);
    Factory = WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(v13, v8, 0);
    v22 = __abi_winrt_ptr_ctor(Factory);
    __abi_winrt_ptr_dtor(Factory);
    Results = Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock __gc *>::GetResults(v22);
    v24 = __abi_winrt_cast_to(
            0,
            Results,
            _uuidof__AU__IMap_PE_AAVString_Platform__PE_AAVObject_2__Collections_Foundation_Windows__);
    LOBYTE(v11) = Windows::Foundation::Collections::IMap<Platform::String __gc *,Platform::Object __gc *>::HasKey(
                    v24,
                    a3);
    __abi_winrt_ptr_dtor(v24);
    __abi_winrt_ptr_dtor(Results);
    __abi_winrt_ptr_dtor(v22);
    __abi_winrt_ptr_dtor(v13);
    WindowsDeleteString_0(v8);
    return v11;
  }
  else
  {
    StringRawBuffer_0 = WindowsGetStringRawBuffer_0(a3, 0);
    v17 = WindowsGetStringRawBuffer_0(v8, 0);
    ValueW = RegGetValueW(HKEY_CURRENT_USER, v17, StringRawBuffer_0, 0xFFFFu, 0, 0, 0);
    if ( ValueW == 5 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2C,
        (unsigned int)"shellcommon\\shell\\cortana\\constraintindex\\src\\Search\\ConstraintIndexRegistryContainer.cpp",
        (const char *)5,
        pdwType);
    v19 = ValueW == 0;
    WindowsDeleteString_0(v8);
    return v19;
  }
}

```

## disassembly

```asm
0x18009ad60  mov     [rsp-8+arg_8], rbx
0x18009ad65  push    rbp
0x18009ad66  push    rsi
0x18009ad67  push    rdi
0x18009ad68  push    r12
0x18009ad6a  push    r13
0x18009ad6c  push    r14
0x18009ad6e  push    r15
0x18009ad70  lea     rbp, [rsp-27h]
0x18009ad75  sub     rsp, 90h
0x18009ad7c  mov     rax, cs:__security_cookie
0x18009ad83  xor     rax, rsp
0x18009ad86  mov     [rbp+57h+var_40], rax
0x18009ad8a  mov     r13, r8
0x18009ad8d  mov     rbx, rcx
0x18009ad90  xor     r14d, r14d
0x18009ad93  mov     [rbp+57h+string], r14
0x18009ad97  lea     r9, [rbp+57h+string]; string
0x18009ad9b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18009ad9f  lea     edx, [r14+1]; length
0x18009ada3  lea     rcx, asc_180104F88; "\\"
0x18009adaa  call    WindowsCreateStringReference_0
0x18009adaf  test    eax, eax
0x18009adb1  jns     short loc_18009ADBB
0x18009adb3  mov     ecx, eax; int
0x18009adb5  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x18009adbb  mov     rcx, [rbx]
0x18009adbe  call    ?get@BaseRegistryPath@IConstraintIndexOptions@Search@ConstraintIndex@Cortana@@UE$AAAPE$AAVString@Platform@@XZ; Cortana::ConstraintIndex::Search::IConstraintIndexOptions::BaseRegistryPath::get(void)
0x18009adc3  mov     rsi, rax
0x18009adc6  mov     [rbp+57h+var_80], rax
0x18009adca  mov     rdx, [rbp+57h+string]
0x18009adce  mov     rcx, rax
0x18009add1  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009add6  mov     rdi, rax
0x18009add9  mov     [rbp+57h+string], rax
0x18009addd  xor     edx, edx
0x18009addf  mov     rcx, rax
0x18009ade2  call    ?Concat@String@Platform@@SAPE$AAV12@PE$AAV12@0@Z; Platform::String::Concat(Platform::String *,Platform::String *)
0x18009ade7  mov     rbx, rax
0x18009adea  mov     [rbp+57h+var_78], rax
0x18009adee  mov     rcx, rax
0x18009adf1  call    ?__abi_winrt_ptrto_string_ctor@@YAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_ctor(Platform::String const volatile *)
0x18009adf6  mov     r12, rax
0x18009adf9  mov     [rbp+57h+var_78], rax
0x18009adfd  mov     rcx, rbx; string
0x18009ae00  call    WindowsDeleteString_0
0x18009ae05  nop
0x18009ae06  mov     rcx, rdi; string
0x18009ae09  call    WindowsDeleteString_0
0x18009ae0e  nop
0x18009ae0f  mov     rcx, rsi; string
0x18009ae12  call    WindowsDeleteString_0
0x18009ae17  nop
0x18009ae18  call    ?IsCShellSettingsApp@Search@ConstraintIndex@Cortana@@YA_NXZ; Cortana::ConstraintIndex::Search::IsCShellSettingsApp(void)
0x18009ae1d  test    al, al
0x18009ae1f  jz      loc_18009AEF4
0x18009ae25  call    ?get@Current@ApplicationData@Storage@Windows@@SAPE$AAV234@XZ; Windows::Storage::ApplicationData::Current::get(void)
0x18009ae2a  mov     rdi, rax
0x18009ae2d  mov     [rbp+57h+var_80], rax
0x18009ae31  mov     rcx, rax
0x18009ae34  call    ?get@LocalSettings@IApplicationData@Storage@Windows@@UE$AAAPE$AAVApplicationDataContainer@34@XZ; Windows::Storage::IApplicationData::LocalSettings::get(void)
0x18009ae39  mov     rbx, rax
0x18009ae3c  mov     [rbp+57h+string], rax
0x18009ae40  mov     rcx, rax
0x18009ae43  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009ae48  mov     r15, rax
0x18009ae4b  mov     [rbp+57h+string], rax
0x18009ae4f  mov     rcx, rbx
0x18009ae52  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ae57  nop
0x18009ae58  mov     rcx, rdi
0x18009ae5b  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ae60  nop
0x18009ae61  xor     r8d, r8d
0x18009ae64  mov     rdx, r12
0x18009ae67  mov     rcx, r15
0x18009ae6a  call    ?GetFactory@IExtensionFactoryStatics@AppExtensions@ApplicationModel@WindowsUdk@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@6@0@Z; WindowsUdk::ApplicationModel::AppExtensions::IExtensionFactoryStatics::GetFactory(Platform::String *,Platform::String *)
0x18009ae6f  mov     rbx, rax
0x18009ae72  mov     [rbp+57h+var_80], rax
0x18009ae76  mov     rcx, rax
0x18009ae79  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18009ae7e  mov     r14, rax
0x18009ae81  mov     [rbp+57h+var_80], rax
0x18009ae85  mov     rcx, rbx
0x18009ae88  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009ae8d  nop
0x18009ae8e  mov     rcx, r14
0x18009ae91  call    ?GetResults@?$IAsyncOperation@PE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@@Foundation@Windows@@UE$AAAPE$AAVExperiencePackLock@Experiences@Services@WindowsUdk@@XZ; Windows::Foundation::IAsyncOperation<WindowsUdk::Services::Experiences::ExperiencePackLock *>::GetResults(void)
0x18009ae96  mov     rsi, rax
0x18009ae99  mov     [rbp+57h+var_70], rax
0x18009ae9d  lea     r8, __uuidof_?AU?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@
0x18009aea4  mov     rdx, rax
0x18009aea7  xor     ecx, ecx
0x18009aea9  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18009aeae  mov     rbx, rax
0x18009aeb1  mov     [rbp+57h+var_68], rax
0x18009aeb5  mov     rdx, r13
0x18009aeb8  mov     rcx, rax
0x18009aebb  call    ?HasKey@?$IMap@PE$AAVString@Platform@@PE$AAVObject@2@@Collections@Foundation@Windows@@UE$AAA_NPE$AAVString@Platform@@@Z; Windows::Foundation::Collections::IMap<Platform::String *,Platform::Object *>::HasKey(Platform::String *)
0x18009aec0  mov     dil, al
0x18009aec3  mov     rcx, rbx
0x18009aec6  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009aecb  nop
0x18009aecc  mov     rcx, rsi
0x18009aecf  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009aed4  nop
0x18009aed5  mov     rcx, r14
0x18009aed8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009aedd  nop
0x18009aede  mov     rcx, r15
0x18009aee1  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18009aee6  nop
0x18009aee7  mov     rcx, r12; string
0x18009aeea  call    WindowsDeleteString_0
0x18009aeef  mov     al, dil
0x18009aef2  jmp     short loc_18009AF62
0x18009aef4  xor     edx, edx; length
0x18009aef6  mov     rcx, r13; string
0x18009aef9  call    WindowsGetStringRawBuffer_0
0x18009aefe  mov     rbx, rax
0x18009af01  xor     edx, edx; length
0x18009af03  mov     rcx, r12; string
0x18009af06  call    WindowsGetStringRawBuffer_0
0x18009af0b  mov     [rsp+0C0h+pcbData], r14; pcbData
0x18009af10  mov     [rsp+0C0h+pvData], r14; pvData
0x18009af15  mov     [rsp+0C0h+pdwType], r14; unsigned int
0x18009af1a  mov     r9d, 0FFFFh; dwFlags
0x18009af20  mov     r8, rbx; lpValue
0x18009af23  mov     rdx, rax; lpSubKey
0x18009af26  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18009af2d  call    cs:__imp_RegGetValueW
0x18009af33  mov     r9d, 5; char *
0x18009af39  cmp     eax, r9d
0x18009af3c  jnz     short loc_18009AF53
0x18009af3e  mov     rcx, [rbp+5Fh]; this
0x18009af42  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\cortana\\constraint"...
0x18009af49  lea     edx, [r9+27h]; void *
0x18009af4d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18009af53  test    eax, eax
0x18009af55  setz    bl
0x18009af58  mov     rcx, r12; string
0x18009af5b  call    WindowsDeleteString_0
0x18009af60  mov     al, bl
0x18009af62  mov     rcx, [rbp+57h+var_40]
0x18009af66  xor     rcx, rsp; StackCookie
0x18009af69  call    __security_check_cookie
0x18009af6e  mov     rbx, [rsp+0C0h+arg_8]
0x18009af76  add     rsp, 90h
0x18009af7d  pop     r15
0x18009af7f  pop     r14
0x18009af81  pop     r13
0x18009af83  pop     r12
0x18009af85  pop     rdi
0x18009af86  pop     rsi
0x18009af87  pop     rbp
0x18009af88  retn
```
