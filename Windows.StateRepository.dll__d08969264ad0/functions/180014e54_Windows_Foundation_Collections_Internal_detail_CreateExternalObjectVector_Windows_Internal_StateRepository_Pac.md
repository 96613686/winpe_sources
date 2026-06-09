# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Package,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Package *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Package *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Package *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Package *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Package *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Package *>,0> * *)

- ea: `0x180014e54`
- end: `0x1800150eb`
- name: `??$CreateExternalObjectVector@VPackage@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackage@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackage@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackage@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackage@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackage@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackage@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `663`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000bb70`
- `0x180013c58`
- `0x1800a612c`
- `0x1800f3210`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x180014e54`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015095`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150ce`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015095`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150bb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800150ce`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014fcd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014fcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ea7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014f19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014faf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ea7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014f19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014faf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Package,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Package *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Package *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Package *>,0>>(
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
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x52u);
  v4 = v3 - 1;
  if ( v3 > 0x52 )
    v4 = 82;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.Package>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x56u);
  v7 = v6 - 1;
  if ( v6 > 0x56 )
    v7 = 86;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.Package>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x54u);
  v10 = v9 - 1;
  if ( v9 > 0x54 )
    v10 = 84;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.Package>",
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
  v22 = GUID_13299364_13fc_4945_a823_e0824cd6707b;
  v23 = GUID_519918d3_758a_5aa2_9592_d7189150ddef;
  v24 = GUID_a5ffa16c_7580_5fae_8e73_9a16cac7d3b5;
  v25 = GUID_fc6918ac_8f6e_5c3d_a576_5d51378162bf;
  v26 = GUID_356c5904_984b_5a51_b970_76914963bbef;
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
    v18 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = 0;
  v14 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v21, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return (unsigned int)ActivationFactory;
  }
  v15 = v20;
  v20 = 0;
  *a2 = v15;
  v16 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x180014e54  mov     [rsp-8+arg_0], rbx
0x180014e59  mov     [rsp-8+arg_10], rdi
0x180014e5e  push    rbp
0x180014e5f  lea     rbp, [rsp-30h]
0x180014e64  sub     rsp, 130h
0x180014e6b  mov     rax, cs:__security_cookie
0x180014e72  xor     rax, rsp
0x180014e75  mov     [rbp+30h+var_10], rax
0x180014e79  mov     rdi, rdx
0x180014e7c  mov     [rbp+30h+string], 0
0x180014e84  mov     ebx, 52h ; 'R'
0x180014e89  mov     ecx, ebx; unsigned int
0x180014e8b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180014e90  lea     edx, [rax-1]
0x180014e93  cmp     eax, ebx
0x180014e95  cmova   edx, ebx; length
0x180014e98  lea     r9, [rbp+30h+string]; string
0x180014e9c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180014ea0  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x180014ea7  call    cs:__imp_WindowsCreateStringReference
0x180014ead  test    eax, eax
0x180014eaf  js      loc_180015089
0x180014eb5  mov     [rbp+30h+var_58], 0
0x180014ebd  mov     ebx, 56h ; 'V'
0x180014ec2  mov     ecx, ebx; unsigned int
0x180014ec4  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180014ec9  lea     edx, [rax-1]
0x180014ecc  cmp     eax, ebx
0x180014ece  cmova   edx, ebx; length
0x180014ed1  lea     r9, [rbp+30h+var_58]; string
0x180014ed5  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180014ed9  lea     rcx, aWindowsFoundat_81; "Windows.Foundation.Collections.IVectorV"...
0x180014ee0  call    cs:__imp_WindowsCreateStringReference
0x180014ee6  test    eax, eax
0x180014ee8  js      loc_18001509C
0x180014eee  mov     [rbp+30h+var_38], 0
0x180014ef6  mov     ebx, 54h ; 'T'
0x180014efb  mov     ecx, ebx; unsigned int
0x180014efd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180014f02  lea     edx, [rax-1]
0x180014f05  cmp     eax, ebx
0x180014f07  cmova   edx, ebx; length
0x180014f0a  lea     r9, [rbp+30h+var_38]; string
0x180014f0e  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180014f12  lea     rcx, aWindowsFoundat_38; "Windows.Foundation.Collections.IIterato"...
0x180014f19  call    cs:__imp_WindowsCreateStringReference
0x180014f1f  test    eax, eax
0x180014f21  js      loc_1800150AF
0x180014f27  mov     rax, [rbp+30h+string]
0x180014f2b  mov     [rsp+130h+var_100], rax
0x180014f30  mov     rax, [rbp+30h+var_58]
0x180014f34  mov     [rsp+130h+var_F8], rax
0x180014f39  mov     rax, [rbp+30h+var_38]
0x180014f3d  mov     [rsp+130h+var_F0], rax
0x180014f42  movups  xmm0, xmmword ptr cs:_GUID_13299364_13fc_4945_a823_e0824cd6707b.Data1
0x180014f49  movdqu  [rsp+130h+var_E8], xmm0
0x180014f4f  movups  xmm1, xmmword ptr cs:_GUID_519918d3_758a_5aa2_9592_d7189150ddef.Data1
0x180014f56  movdqu  [rsp+130h+var_D8], xmm1
0x180014f5c  movups  xmm0, xmmword ptr cs:_GUID_a5ffa16c_7580_5fae_8e73_9a16cac7d3b5.Data1
0x180014f63  movdqu  [rsp+130h+var_C8], xmm0
0x180014f69  movups  xmm1, xmmword ptr cs:_GUID_fc6918ac_8f6e_5c3d_a576_5d51378162bf.Data1
0x180014f70  movdqu  [rsp+130h+var_B8], xmm1
0x180014f76  movups  xmm0, xmmword ptr cs:_GUID_356c5904_984b_5a51_b970_76914963bbef.Data1
0x180014f7d  movdqu  [rbp+30h+var_A8], xmm0
0x180014f82  mov     [rsp+130h+var_110], 0
0x180014f8b  lea     rcx, [rsp+130h+var_110]
0x180014f90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014f95  mov     [rbp+30h+var_18], 0
0x180014f9d  lea     r9, [rbp+30h+var_18]; string
0x180014fa1  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180014fa5  lea     edx, [rbx-28h]; length
0x180014fa8  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180014faf  call    cs:__imp_WindowsCreateStringReference
0x180014fb5  test    eax, eax
0x180014fb7  js      loc_1800150C2
0x180014fbd  lea     r8, [rsp+130h+var_110]
0x180014fc2  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180014fc9  mov     rcx, [rbp+30h+var_18]
0x180014fcd  call    cs:__imp_RoGetActivationFactory
0x180014fd3  mov     ebx, eax
0x180014fd5  test    eax, eax
0x180014fd7  js      loc_180015065
0x180014fdd  mov     [rsp+130h+var_108], 0
0x180014fe6  mov     rbx, [rsp+130h+var_110]
0x180014feb  lea     rcx, [rsp+130h+var_108]
0x180014ff0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014ff5  lea     r8, [rsp+130h+var_108]
0x180014ffa  lea     rdx, [rsp+130h+var_100]
0x180014fff  mov     rcx, rbx
0x180015002  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180015007  mov     ebx, eax
0x180015009  test    eax, eax
0x18001500b  js      loc_1800150D5
0x180015011  mov     rax, [rsp+130h+var_108]
0x180015016  mov     [rsp+130h+var_108], 0
0x18001501f  mov     [rdi], rax
0x180015022  mov     rcx, [rsp+130h+var_110]
0x180015027  test    rcx, rcx
0x18001502a  jz      short loc_180015042
0x18001502c  mov     [rsp+130h+var_110], 0
0x180015035  mov     rax, [rcx]
0x180015038  mov     rax, [rax+10h]
0x18001503c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015041  nop
0x180015042  xor     eax, eax
0x180015044  mov     rcx, [rbp+30h+var_10]
0x180015048  xor     rcx, rsp; StackCookie
0x18001504b  call    __security_check_cookie
0x180015050  lea     r11, [rsp+130h+var_s0]
0x180015058  mov     rbx, [r11+10h]
0x18001505c  mov     rdi, [r11+20h]
0x180015060  mov     rsp, r11
0x180015063  pop     rbp
0x180015064  retn
0x180015065  mov     rcx, [rsp+130h+var_110]
0x18001506a  test    rcx, rcx
0x18001506d  jz      short loc_180015085
0x18001506f  mov     [rsp+130h+var_110], 0
0x180015078  mov     rdx, [rcx]
0x18001507b  mov     rax, [rdx+10h]
0x18001507f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015084  nop
0x180015085  mov     eax, ebx
0x180015087  jmp     short loc_180015044
0x180015089  xor     r9d, r9d; lpArguments
0x18001508c  xor     r8d, r8d; nNumberOfArguments
0x18001508f  lea     edx, [r9+1]; dwExceptionFlags
0x180015093  mov     ecx, eax; dwExceptionCode
0x180015095  call    cs:__imp_RaiseException
0x18001509b  int     3; Trap to Debugger
0x18001509c  xor     r9d, r9d; lpArguments
0x18001509f  xor     r8d, r8d; nNumberOfArguments
0x1800150a2  lea     edx, [r9+1]; dwExceptionFlags
0x1800150a6  mov     ecx, eax; dwExceptionCode
0x1800150a8  call    cs:__imp_RaiseException
0x1800150ae  int     3; Trap to Debugger
0x1800150af  xor     r9d, r9d; lpArguments
0x1800150b2  xor     r8d, r8d; nNumberOfArguments
0x1800150b5  lea     edx, [r9+1]; dwExceptionFlags
0x1800150b9  mov     ecx, eax; dwExceptionCode
0x1800150bb  call    cs:__imp_RaiseException
0x1800150c1  int     3; Trap to Debugger
0x1800150c2  xor     r9d, r9d; lpArguments
0x1800150c5  xor     r8d, r8d; nNumberOfArguments
0x1800150c8  lea     edx, [r9+1]; dwExceptionFlags
0x1800150cc  mov     ecx, eax; dwExceptionCode
0x1800150ce  call    cs:__imp_RaiseException
0x1800150d4  int     3; Trap to Debugger
0x1800150d5  lea     rcx, [rsp+130h+var_108]
0x1800150da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800150df  lea     rcx, [rsp+130h+var_110]
0x1800150e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800150e9  jmp     short loc_180015085
```
