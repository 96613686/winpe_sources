# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackagePolicy,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackagePolicy *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackagePolicy *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackagePolicy *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackagePolicy *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackagePolicy *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackagePolicy *>,0> * *)

- ea: `0x180081350`
- end: `0x1800815e9`
- name: `??$CreateExternalObjectVector@VPackagePolicy@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackagePolicy@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackagePolicy@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackagePolicy@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackagePolicy@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackagePolicy@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackagePolicy@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `665`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800811f4`
- `0x1800bbff4`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x180081350`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180081590`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800815a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800815b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800815c9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180081590`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800815a3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800815b6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800815c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800814c9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800814c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800813a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800813dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180081415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800814ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800813a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800813dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180081415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800814ab`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackagePolicy,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackagePolicy *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackagePolicy *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackagePolicy *>,0>>(
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
  __int64 v18; // rcx
  __int64 v19; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v20; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v21[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v22; // [rsp+48h] [rbp-B8h]
  GUID v23; // [rsp+58h] [rbp-A8h]
  GUID v24; // [rsp+68h] [rbp-98h]
  GUID v25; // [rsp+78h] [rbp-88h]
  GUID v26; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v29; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v30; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v31; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v32; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v33; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v34; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v4 = v3 - 1;
  if ( v3 > 0x58 )
    v4 = 88;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackagePolicy>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v7 = v6 - 1;
  if ( v6 > 0x5C )
    v7 = 92;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackagePolicy>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v10 = v9 - 1;
  if ( v9 > 0x5A )
    v10 = 90;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackagePolicy>",
          v10,
          &v31,
          &v32);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v21[0] = string;
  v21[1] = v30;
  v21[2] = v32;
  v22 = GUID_d8cc81b3_171d_4e8b_8663_79cc87408d04;
  v23 = GUID_02a77490_52ec_5a77_b7cf_eaadc112c9ea;
  v24 = GUID_f3e74273_0be4_580a_a90b_d7880a95b914;
  v25 = GUID_ac04be95_d70c_5475_8e8b_77131b57e318;
  v26 = GUID_706476b0_7978_59a8_96a5_2c72e0fd6964;
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  v34 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v33, &v34);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v34, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v19);
  if ( ActivationFactory < 0 )
  {
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = 0;
  v16 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v21, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return (unsigned int)ActivationFactory;
  }
  v17 = v20;
  v20 = 0;
  *a2 = v17;
  v18 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x180081350  mov     [rsp-8+arg_0], rbx
0x180081355  mov     [rsp-8+arg_10], rdi
0x18008135a  push    rbp
0x18008135b  lea     rbp, [rsp-30h]
0x180081360  sub     rsp, 130h
0x180081367  mov     rax, cs:__security_cookie
0x18008136e  xor     rax, rsp
0x180081371  mov     [rbp+30h+var_10], rax
0x180081375  mov     rdi, rdx
0x180081378  mov     [rbp+30h+string], 0
0x180081380  mov     ebx, 58h ; 'X'
0x180081385  mov     ecx, ebx; unsigned int
0x180081387  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18008138c  lea     edx, [rax-1]
0x18008138f  cmp     eax, ebx
0x180081391  cmova   edx, ebx; length
0x180081394  lea     r9, [rbp+30h+string]; string
0x180081398  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18008139c  lea     rcx, aWindowsFoundat_166; "Windows.Foundation.Collections.IVector`"...
0x1800813a3  call    cs:__imp_WindowsCreateStringReference
0x1800813a9  test    eax, eax
0x1800813ab  js      loc_180081584
0x1800813b1  mov     [rbp+30h+var_58], 0
0x1800813b9  mov     ebx, 5Ch ; '\'
0x1800813be  mov     ecx, ebx; unsigned int
0x1800813c0  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800813c5  lea     edx, [rax-1]
0x1800813c8  cmp     eax, ebx
0x1800813ca  cmova   edx, ebx; length
0x1800813cd  lea     r9, [rbp+30h+var_58]; string
0x1800813d1  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800813d5  lea     rcx, aWindowsFoundat_48; "Windows.Foundation.Collections.IVectorV"...
0x1800813dc  call    cs:__imp_WindowsCreateStringReference
0x1800813e2  test    eax, eax
0x1800813e4  js      loc_180081597
0x1800813ea  mov     [rbp+30h+var_38], 0
0x1800813f2  mov     ebx, 5Ah ; 'Z'
0x1800813f7  mov     ecx, ebx; unsigned int
0x1800813f9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800813fe  lea     edx, [rax-1]
0x180081401  cmp     eax, ebx
0x180081403  cmova   edx, ebx; length
0x180081406  lea     r9, [rbp+30h+var_38]; string
0x18008140a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18008140e  lea     rcx, aWindowsFoundat_62; "Windows.Foundation.Collections.IIterato"...
0x180081415  call    cs:__imp_WindowsCreateStringReference
0x18008141b  test    eax, eax
0x18008141d  js      loc_1800815AA
0x180081423  mov     rax, [rbp+30h+string]
0x180081427  mov     [rsp+130h+var_100], rax
0x18008142c  mov     rax, [rbp+30h+var_58]
0x180081430  mov     [rsp+130h+var_F8], rax
0x180081435  mov     rax, [rbp+30h+var_38]
0x180081439  mov     [rsp+130h+var_F0], rax
0x18008143e  movups  xmm0, xmmword ptr cs:_GUID_d8cc81b3_171d_4e8b_8663_79cc87408d04.Data1
0x180081445  movdqu  [rsp+130h+var_E8], xmm0
0x18008144b  movups  xmm1, xmmword ptr cs:_GUID_02a77490_52ec_5a77_b7cf_eaadc112c9ea.Data1
0x180081452  movdqu  [rsp+130h+var_D8], xmm1
0x180081458  movups  xmm0, xmmword ptr cs:_GUID_f3e74273_0be4_580a_a90b_d7880a95b914.Data1
0x18008145f  movdqu  [rsp+130h+var_C8], xmm0
0x180081465  movups  xmm1, xmmword ptr cs:_GUID_ac04be95_d70c_5475_8e8b_77131b57e318.Data1
0x18008146c  movdqu  [rsp+130h+var_B8], xmm1
0x180081472  movups  xmm0, xmmword ptr cs:_GUID_706476b0_7978_59a8_96a5_2c72e0fd6964.Data1
0x180081479  movdqu  [rbp+30h+var_A8], xmm0
0x18008147e  mov     [rsp+130h+var_110], 0
0x180081487  lea     rcx, [rsp+130h+var_110]
0x18008148c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081491  mov     [rbp+30h+var_18], 0
0x180081499  lea     r9, [rbp+30h+var_18]; string
0x18008149d  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800814a1  lea     edx, [rbx-2Eh]; length
0x1800814a4  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800814ab  call    cs:__imp_WindowsCreateStringReference
0x1800814b1  test    eax, eax
0x1800814b3  js      loc_1800815BD
0x1800814b9  lea     r8, [rsp+130h+var_110]
0x1800814be  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800814c5  mov     rcx, [rbp+30h+var_18]
0x1800814c9  call    cs:__imp_RoGetActivationFactory
0x1800814cf  mov     ebx, eax
0x1800814d1  test    eax, eax
0x1800814d3  jns     short loc_180081518
0x1800814d5  mov     rcx, [rsp+130h+var_110]
0x1800814da  test    rcx, rcx
0x1800814dd  jz      short loc_1800814F5
0x1800814df  mov     [rsp+130h+var_110], 0
0x1800814e8  mov     rdx, [rcx]
0x1800814eb  mov     rax, [rdx+10h]
0x1800814ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800814f4  nop
0x1800814f5  mov     eax, ebx
0x1800814f7  mov     rcx, [rbp+30h+var_10]
0x1800814fb  xor     rcx, rsp; StackCookie
0x1800814fe  call    __security_check_cookie
0x180081503  lea     r11, [rsp+130h+var_s0]
0x18008150b  mov     rbx, [r11+10h]
0x18008150f  mov     rdi, [r11+20h]
0x180081513  mov     rsp, r11
0x180081516  pop     rbp
0x180081517  retn
0x180081518  mov     [rsp+130h+var_108], 0
0x180081521  mov     rbx, [rsp+130h+var_110]
0x180081526  lea     rcx, [rsp+130h+var_108]
0x18008152b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081530  lea     r8, [rsp+130h+var_108]
0x180081535  lea     rdx, [rsp+130h+var_100]
0x18008153a  mov     rcx, rbx
0x18008153d  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180081542  mov     ebx, eax
0x180081544  test    eax, eax
0x180081546  js      loc_1800815D0
0x18008154c  mov     rax, [rsp+130h+var_108]
0x180081551  mov     [rsp+130h+var_108], 0
0x18008155a  mov     [rdi], rax
0x18008155d  mov     rcx, [rsp+130h+var_110]
0x180081562  test    rcx, rcx
0x180081565  jz      short loc_18008157D
0x180081567  mov     [rsp+130h+var_110], 0
0x180081570  mov     rax, [rcx]
0x180081573  mov     rax, [rax+10h]
0x180081577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008157c  nop
0x18008157d  xor     eax, eax
0x18008157f  jmp     loc_1800814F7
0x180081584  xor     r9d, r9d; lpArguments
0x180081587  xor     r8d, r8d; nNumberOfArguments
0x18008158a  lea     edx, [r9+1]; dwExceptionFlags
0x18008158e  mov     ecx, eax; dwExceptionCode
0x180081590  call    cs:__imp_RaiseException
0x180081596  int     3; Trap to Debugger
0x180081597  xor     r9d, r9d; lpArguments
0x18008159a  xor     r8d, r8d; nNumberOfArguments
0x18008159d  lea     edx, [r9+1]; dwExceptionFlags
0x1800815a1  mov     ecx, eax; dwExceptionCode
0x1800815a3  call    cs:__imp_RaiseException
0x1800815a9  int     3; Trap to Debugger
0x1800815aa  xor     r9d, r9d; lpArguments
0x1800815ad  xor     r8d, r8d; nNumberOfArguments
0x1800815b0  lea     edx, [r9+1]; dwExceptionFlags
0x1800815b4  mov     ecx, eax; dwExceptionCode
0x1800815b6  call    cs:__imp_RaiseException
0x1800815bc  int     3; Trap to Debugger
0x1800815bd  xor     r9d, r9d; lpArguments
0x1800815c0  xor     r8d, r8d; nNumberOfArguments
0x1800815c3  lea     edx, [r9+1]; dwExceptionFlags
0x1800815c7  mov     ecx, eax; dwExceptionCode
0x1800815c9  call    cs:__imp_RaiseException
0x1800815cf  int     3; Trap to Debugger
0x1800815d0  lea     rcx, [rsp+130h+var_108]
0x1800815d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800815da  lea     rcx, [rsp+130h+var_110]
0x1800815df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800815e4  jmp     loc_1800814F5
```
