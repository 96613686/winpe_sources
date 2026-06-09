# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageExtension,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageExtension *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageExtension *>,0> * *)

- ea: `0x1800720e8`
- end: `0x180072355`
- name: `??$CreateExternalObjectVector@VPackageExtension@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackageExtension@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageExtension@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageExtension@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackageExtension@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageExtension@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageExtension@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180071fc8`
- `0x1801df238`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800720e8`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072150`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072197`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800721de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072285`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072150`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072197`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800721de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180072285`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007229c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007229c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007213b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800721c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007226f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007213b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072182`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800721c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007226f`

## string_xrefs

- `0x180072134`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageExtension>`
- `0x18007217b`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageExtension>`
- `0x1800721c2`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageExtension>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageExtension,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageExtension *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageExtension *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageExtension *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  UINT32 v4; // edx
  HRESULT v5; // eax
  unsigned int v6; // eax
  UINT32 v7; // edx
  HRESULT v8; // eax
  unsigned int v9; // eax
  UINT32 v10; // edx
  HRESULT v11; // eax
  HRESULT v12; // eax
  int ActivationFactory; // ebx
  __int64 v14; // rcx
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v21; // [rsp+48h] [rbp-B8h]
  GUID v22; // [rsp+58h] [rbp-A8h]
  GUID v23; // [rsp+68h] [rbp-98h]
  GUID v24; // [rsp+78h] [rbp-88h]
  GUID v25; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v28; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v30; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v31; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v32; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v33; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Bu);
  v4 = v3 - 1;
  if ( v3 > 0x5B )
    v4 = 91;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageExtension>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Fu);
  v7 = v6 - 1;
  if ( v6 > 0x5F )
    v7 = 95;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageExtension>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Du);
  v10 = v9 - 1;
  if ( v9 > 0x5D )
    v10 = 93;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageExtension>",
          v10,
          &v30,
          &v31);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v20[0] = string;
  v20[1] = v29;
  v20[2] = v31;
  v21 = GUID_481ce8e6_a35a_493c_9d4a_becd8c2c3dbd;
  v22 = GUID_814a54a7_fa77_52b0_a098_047efd7079e9;
  v23 = GUID_e09d0063_1c2f_5a94_85a9_0a5325818844;
  v24 = GUID_a7339786_3069_5b34_9a6e_4fee9c2e226e;
  v25 = GUID_ef566730_d07d_5bcb_8717_2e1e1a2a9345;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v33 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v32, &v33);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v18);
  if ( ActivationFactory < 0 )
  {
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v16 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1800720e8  mov     [rsp-8+arg_0], rbx
0x1800720ed  mov     [rsp-8+arg_10], rdi
0x1800720f2  push    rbp
0x1800720f3  lea     rbp, [rsp-30h]
0x1800720f8  sub     rsp, 130h
0x1800720ff  mov     rax, cs:__security_cookie
0x180072106  xor     rax, rsp
0x180072109  mov     [rbp+30h+var_10], rax
0x18007210d  mov     rdi, rdx
0x180072110  mov     [rbp+30h+string], 0
0x180072118  mov     ebx, 5Bh ; '['
0x18007211d  mov     ecx, ebx; unsigned int
0x18007211f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180072124  lea     edx, [rax-1]
0x180072127  cmp     eax, ebx
0x180072129  cmova   edx, ebx; length
0x18007212c  lea     r9, [rbp+30h+string]; string
0x180072130  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180072134  lea     rcx, aWindowsFoundat_181; "Windows.Foundation.Collections.IVector`"...
0x18007213b  call    cs:__imp_WindowsCreateStringReference
0x180072141  test    eax, eax
0x180072143  jns     short loc_180072157
0x180072145  xor     r9d, r9d; lpArguments
0x180072148  xor     r8d, r8d; nNumberOfArguments
0x18007214b  lea     edx, [rbx-5Ah]; dwExceptionFlags
0x18007214e  mov     ecx, eax; dwExceptionCode
0x180072150  call    cs:__imp_RaiseException
0x180072156  int     3; Trap to Debugger
0x180072157  mov     [rbp+30h+var_58], 0
0x18007215f  mov     ebx, 5Fh ; '_'
0x180072164  mov     ecx, ebx; unsigned int
0x180072166  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007216b  lea     edx, [rax-1]
0x18007216e  cmp     eax, ebx
0x180072170  cmova   edx, ebx; length
0x180072173  lea     r9, [rbp+30h+var_58]; string
0x180072177  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18007217b  lea     rcx, aWindowsFoundat_12; "Windows.Foundation.Collections.IVectorV"...
0x180072182  call    cs:__imp_WindowsCreateStringReference
0x180072188  test    eax, eax
0x18007218a  jns     short loc_18007219E
0x18007218c  xor     r9d, r9d; lpArguments
0x18007218f  xor     r8d, r8d; nNumberOfArguments
0x180072192  lea     edx, [rbx-5Eh]; dwExceptionFlags
0x180072195  mov     ecx, eax; dwExceptionCode
0x180072197  call    cs:__imp_RaiseException
0x18007219d  int     3; Trap to Debugger
0x18007219e  mov     [rbp+30h+var_38], 0
0x1800721a6  mov     ebx, 5Dh ; ']'
0x1800721ab  mov     ecx, ebx; unsigned int
0x1800721ad  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800721b2  lea     edx, [rax-1]
0x1800721b5  cmp     eax, ebx
0x1800721b7  cmova   edx, ebx; length
0x1800721ba  lea     r9, [rbp+30h+var_38]; string
0x1800721be  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800721c2  lea     rcx, aWindowsFoundat_176; "Windows.Foundation.Collections.IIterato"...
0x1800721c9  call    cs:__imp_WindowsCreateStringReference
0x1800721cf  test    eax, eax
0x1800721d1  jns     short loc_1800721E5
0x1800721d3  xor     r9d, r9d; lpArguments
0x1800721d6  xor     r8d, r8d; nNumberOfArguments
0x1800721d9  lea     edx, [rbx-5Ch]; dwExceptionFlags
0x1800721dc  mov     ecx, eax; dwExceptionCode
0x1800721de  call    cs:__imp_RaiseException
0x1800721e4  int     3; Trap to Debugger
0x1800721e5  mov     rax, [rbp+30h+string]
0x1800721e9  mov     [rsp+130h+var_100], rax
0x1800721ee  mov     rax, [rbp+30h+var_58]
0x1800721f2  mov     [rsp+130h+var_F8], rax
0x1800721f7  mov     rax, [rbp+30h+var_38]
0x1800721fb  mov     [rsp+130h+var_F0], rax
0x180072200  movups  xmm0, xmmword ptr cs:_GUID_481ce8e6_a35a_493c_9d4a_becd8c2c3dbd.Data1
0x180072207  movdqu  [rsp+130h+var_E8], xmm0
0x18007220d  movups  xmm1, xmmword ptr cs:_GUID_814a54a7_fa77_52b0_a098_047efd7079e9.Data1
0x180072214  movdqu  [rsp+130h+var_D8], xmm1
0x18007221a  movups  xmm0, xmmword ptr cs:_GUID_e09d0063_1c2f_5a94_85a9_0a5325818844.Data1
0x180072221  movdqu  [rsp+130h+var_C8], xmm0
0x180072227  movups  xmm1, xmmword ptr cs:_GUID_a7339786_3069_5b34_9a6e_4fee9c2e226e.Data1
0x18007222e  movdqu  [rsp+130h+var_B8], xmm1
0x180072234  movups  xmm0, xmmword ptr cs:_GUID_ef566730_d07d_5bcb_8717_2e1e1a2a9345.Data1
0x18007223b  movdqu  [rbp+30h+var_A8], xmm0
0x180072240  mov     [rsp+130h+var_110], 0
0x180072249  lea     rcx, [rsp+130h+var_110]
0x18007224e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072253  mov     [rbp+30h+var_18], 0
0x18007225b  lea     r9, [rbp+30h+var_18]; string
0x18007225f  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180072263  mov     edx, 2Ch ; ','; length
0x180072268  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18007226f  call    cs:__imp_WindowsCreateStringReference
0x180072275  test    eax, eax
0x180072277  jns     short loc_18007228C
0x180072279  xor     r9d, r9d; lpArguments
0x18007227c  xor     r8d, r8d; nNumberOfArguments
0x18007227f  lea     edx, [r9+1]; dwExceptionFlags
0x180072283  mov     ecx, eax; dwExceptionCode
0x180072285  call    cs:__imp_RaiseException
0x18007228b  int     3; Trap to Debugger
0x18007228c  lea     r8, [rsp+130h+var_110]
0x180072291  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180072298  mov     rcx, [rbp+30h+var_18]
0x18007229c  call    cs:__imp_RoGetActivationFactory
0x1800722a2  mov     ebx, eax
0x1800722a4  test    eax, eax
0x1800722a6  jns     short loc_1800722CC
0x1800722a8  mov     rcx, [rsp+130h+var_110]
0x1800722ad  test    rcx, rcx
0x1800722b0  jz      short loc_1800722C8
0x1800722b2  mov     [rsp+130h+var_110], 0
0x1800722bb  mov     rdx, [rcx]
0x1800722be  mov     rax, [rdx+10h]
0x1800722c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800722c7  nop
0x1800722c8  mov     eax, ebx
0x1800722ca  jmp     short loc_180072334
0x1800722cc  mov     [rsp+130h+var_108], 0
0x1800722d5  mov     rbx, [rsp+130h+var_110]
0x1800722da  lea     rcx, [rsp+130h+var_108]
0x1800722df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800722e4  lea     r8, [rsp+130h+var_108]
0x1800722e9  lea     rdx, [rsp+130h+var_100]
0x1800722ee  mov     rcx, rbx
0x1800722f1  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800722f6  mov     ebx, eax
0x1800722f8  lea     rcx, [rsp+130h+var_108]
0x1800722fd  test    eax, eax
0x1800722ff  jns     short loc_180072312
0x180072301  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072306  lea     rcx, [rsp+130h+var_110]
0x18007230b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072310  jmp     short loc_1800722C8
0x180072312  mov     rax, [rsp+130h+var_108]
0x180072317  mov     [rsp+130h+var_108], 0
0x180072320  mov     [rdi], rax
0x180072323  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072328  lea     rcx, [rsp+130h+var_110]
0x18007232d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180072332  xor     eax, eax
0x180072334  mov     rcx, [rbp+30h+var_10]
0x180072338  xor     rcx, rsp; StackCookie
0x18007233b  call    __security_check_cookie
0x180072340  lea     r11, [rsp+130h+var_s0]
0x180072348  mov     rbx, [r11+10h]
0x18007234c  mov     rdi, [r11+20h]
0x180072350  mov     rsp, r11
0x180072353  pop     rbp
0x180072354  retn
```
