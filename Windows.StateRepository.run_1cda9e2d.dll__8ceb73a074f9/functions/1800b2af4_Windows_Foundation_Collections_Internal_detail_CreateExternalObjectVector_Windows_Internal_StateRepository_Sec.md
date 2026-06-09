# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::SecondaryTileView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SecondaryTileView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SecondaryTileView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SecondaryTileView *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SecondaryTileView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SecondaryTileView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SecondaryTileView *>,0> * *)

- ea: `0x1800b2af4`
- end: `0x1800b2d61`
- name: `??$CreateExternalObjectVector@VSecondaryTileView@StateRepository@Internal@Windows@@V?$AgileVector@PEAVSecondaryTileView@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVSecondaryTileView@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSecondaryTileView@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVSecondaryTileView@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVSecondaryTileView@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSecondaryTileView@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180065fec`
- `0x1800b2a34`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800b2af4`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2b5c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2ba3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2bea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2c91`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2b5c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2ba3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2bea`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b2c91`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2ca8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b2ca8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2b47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2bd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2b47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2b8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2bd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b2c7b`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::SecondaryTileView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SecondaryTileView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SecondaryTileView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SecondaryTileView *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v4 = v3 - 1;
  if ( v3 > 0x5C )
    v4 = 92;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.SecondaryTileView>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x60u);
  v7 = v6 - 1;
  if ( v6 > 0x60 )
    v7 = 96;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.SecondaryTileView>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Eu);
  v10 = v9 - 1;
  if ( v9 > 0x5E )
    v10 = 94;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.SecondaryTileView>",
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
  v21 = GUID_33f8621a_8511_4a50_89cf_a0dda265cd10;
  v22 = GUID_f1980009_f954_571f_bc34_2e8f46599e17;
  v23 = GUID_6f0d9940_d33b_5630_b26e_c3cab7795422;
  v24 = GUID_901b7e06_b5e1_50f2_9e7d_9d41972451b4;
  v25 = GUID_efd952b3_bcb1_5cc8_8c49_10603d8cf005;
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
0x1800b2af4  mov     [rsp-8+arg_0], rbx
0x1800b2af9  mov     [rsp-8+arg_10], rdi
0x1800b2afe  push    rbp
0x1800b2aff  lea     rbp, [rsp-30h]
0x1800b2b04  sub     rsp, 130h
0x1800b2b0b  mov     rax, cs:__security_cookie
0x1800b2b12  xor     rax, rsp
0x1800b2b15  mov     [rbp+30h+var_10], rax
0x1800b2b19  mov     rdi, rdx
0x1800b2b1c  mov     [rbp+30h+string], 0
0x1800b2b24  mov     ebx, 5Ch ; '\'
0x1800b2b29  mov     ecx, ebx; unsigned int
0x1800b2b2b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b2b30  lea     edx, [rax-1]
0x1800b2b33  cmp     eax, ebx
0x1800b2b35  cmova   edx, ebx; length
0x1800b2b38  lea     r9, [rbp+30h+string]; string
0x1800b2b3c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800b2b40  lea     rcx, aWindowsFoundat_178; "Windows.Foundation.Collections.IVector`"...
0x1800b2b47  call    cs:__imp_WindowsCreateStringReference
0x1800b2b4d  test    eax, eax
0x1800b2b4f  jns     short loc_1800B2B63
0x1800b2b51  xor     r9d, r9d; lpArguments
0x1800b2b54  xor     r8d, r8d; nNumberOfArguments
0x1800b2b57  lea     edx, [rbx-5Bh]; dwExceptionFlags
0x1800b2b5a  mov     ecx, eax; dwExceptionCode
0x1800b2b5c  call    cs:__imp_RaiseException
0x1800b2b62  int     3; Trap to Debugger
0x1800b2b63  mov     [rbp+30h+var_58], 0
0x1800b2b6b  mov     ebx, 60h ; '`'
0x1800b2b70  mov     ecx, ebx; unsigned int
0x1800b2b72  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b2b77  lea     edx, [rax-1]
0x1800b2b7a  cmp     eax, ebx
0x1800b2b7c  cmova   edx, ebx; length
0x1800b2b7f  lea     r9, [rbp+30h+var_58]; string
0x1800b2b83  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800b2b87  lea     rcx, aWindowsFoundat_120; "Windows.Foundation.Collections.IVectorV"...
0x1800b2b8e  call    cs:__imp_WindowsCreateStringReference
0x1800b2b94  test    eax, eax
0x1800b2b96  jns     short loc_1800B2BAA
0x1800b2b98  xor     r9d, r9d; lpArguments
0x1800b2b9b  xor     r8d, r8d; nNumberOfArguments
0x1800b2b9e  lea     edx, [rbx-5Fh]; dwExceptionFlags
0x1800b2ba1  mov     ecx, eax; dwExceptionCode
0x1800b2ba3  call    cs:__imp_RaiseException
0x1800b2ba9  int     3; Trap to Debugger
0x1800b2baa  mov     [rbp+30h+var_38], 0
0x1800b2bb2  mov     ebx, 5Eh ; '^'
0x1800b2bb7  mov     ecx, ebx; unsigned int
0x1800b2bb9  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800b2bbe  lea     edx, [rax-1]
0x1800b2bc1  cmp     eax, ebx
0x1800b2bc3  cmova   edx, ebx; length
0x1800b2bc6  lea     r9, [rbp+30h+var_38]; string
0x1800b2bca  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800b2bce  lea     rcx, aWindowsFoundat_114; "Windows.Foundation.Collections.IIterato"...
0x1800b2bd5  call    cs:__imp_WindowsCreateStringReference
0x1800b2bdb  test    eax, eax
0x1800b2bdd  jns     short loc_1800B2BF1
0x1800b2bdf  xor     r9d, r9d; lpArguments
0x1800b2be2  xor     r8d, r8d; nNumberOfArguments
0x1800b2be5  lea     edx, [rbx-5Dh]; dwExceptionFlags
0x1800b2be8  mov     ecx, eax; dwExceptionCode
0x1800b2bea  call    cs:__imp_RaiseException
0x1800b2bf0  int     3; Trap to Debugger
0x1800b2bf1  mov     rax, [rbp+30h+string]
0x1800b2bf5  mov     [rsp+130h+var_100], rax
0x1800b2bfa  mov     rax, [rbp+30h+var_58]
0x1800b2bfe  mov     [rsp+130h+var_F8], rax
0x1800b2c03  mov     rax, [rbp+30h+var_38]
0x1800b2c07  mov     [rsp+130h+var_F0], rax
0x1800b2c0c  movups  xmm0, xmmword ptr cs:_GUID_33f8621a_8511_4a50_89cf_a0dda265cd10.Data1
0x1800b2c13  movdqu  [rsp+130h+var_E8], xmm0
0x1800b2c19  movups  xmm1, xmmword ptr cs:_GUID_f1980009_f954_571f_bc34_2e8f46599e17.Data1
0x1800b2c20  movdqu  [rsp+130h+var_D8], xmm1
0x1800b2c26  movups  xmm0, xmmword ptr cs:_GUID_6f0d9940_d33b_5630_b26e_c3cab7795422.Data1
0x1800b2c2d  movdqu  [rsp+130h+var_C8], xmm0
0x1800b2c33  movups  xmm1, xmmword ptr cs:_GUID_901b7e06_b5e1_50f2_9e7d_9d41972451b4.Data1
0x1800b2c3a  movdqu  [rsp+130h+var_B8], xmm1
0x1800b2c40  movups  xmm0, xmmword ptr cs:_GUID_efd952b3_bcb1_5cc8_8c49_10603d8cf005.Data1
0x1800b2c47  movdqu  [rbp+30h+var_A8], xmm0
0x1800b2c4c  mov     [rsp+130h+var_110], 0
0x1800b2c55  lea     rcx, [rsp+130h+var_110]
0x1800b2c5a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2c5f  mov     [rbp+30h+var_18], 0
0x1800b2c67  lea     r9, [rbp+30h+var_18]; string
0x1800b2c6b  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800b2c6f  mov     edx, 2Ch ; ','; length
0x1800b2c74  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800b2c7b  call    cs:__imp_WindowsCreateStringReference
0x1800b2c81  test    eax, eax
0x1800b2c83  jns     short loc_1800B2C98
0x1800b2c85  xor     r9d, r9d; lpArguments
0x1800b2c88  xor     r8d, r8d; nNumberOfArguments
0x1800b2c8b  lea     edx, [r9+1]; dwExceptionFlags
0x1800b2c8f  mov     ecx, eax; dwExceptionCode
0x1800b2c91  call    cs:__imp_RaiseException
0x1800b2c97  int     3; Trap to Debugger
0x1800b2c98  lea     r8, [rsp+130h+var_110]
0x1800b2c9d  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800b2ca4  mov     rcx, [rbp+30h+var_18]
0x1800b2ca8  call    cs:__imp_RoGetActivationFactory
0x1800b2cae  mov     ebx, eax
0x1800b2cb0  test    eax, eax
0x1800b2cb2  jns     short loc_1800B2CD8
0x1800b2cb4  mov     rcx, [rsp+130h+var_110]
0x1800b2cb9  test    rcx, rcx
0x1800b2cbc  jz      short loc_1800B2CD4
0x1800b2cbe  mov     [rsp+130h+var_110], 0
0x1800b2cc7  mov     rdx, [rcx]
0x1800b2cca  mov     rax, [rdx+10h]
0x1800b2cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2cd3  nop
0x1800b2cd4  mov     eax, ebx
0x1800b2cd6  jmp     short loc_1800B2D40
0x1800b2cd8  mov     [rsp+130h+var_108], 0
0x1800b2ce1  mov     rbx, [rsp+130h+var_110]
0x1800b2ce6  lea     rcx, [rsp+130h+var_108]
0x1800b2ceb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2cf0  lea     r8, [rsp+130h+var_108]
0x1800b2cf5  lea     rdx, [rsp+130h+var_100]
0x1800b2cfa  mov     rcx, rbx
0x1800b2cfd  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800b2d02  mov     ebx, eax
0x1800b2d04  lea     rcx, [rsp+130h+var_108]
0x1800b2d09  test    eax, eax
0x1800b2d0b  jns     short loc_1800B2D1E
0x1800b2d0d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2d12  lea     rcx, [rsp+130h+var_110]
0x1800b2d17  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2d1c  jmp     short loc_1800B2CD4
0x1800b2d1e  mov     rax, [rsp+130h+var_108]
0x1800b2d23  mov     [rsp+130h+var_108], 0
0x1800b2d2c  mov     [rdi], rax
0x1800b2d2f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2d34  lea     rcx, [rsp+130h+var_110]
0x1800b2d39  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800b2d3e  xor     eax, eax
0x1800b2d40  mov     rcx, [rbp+30h+var_10]
0x1800b2d44  xor     rcx, rsp; StackCookie
0x1800b2d47  call    __security_check_cookie
0x1800b2d4c  lea     r11, [rsp+130h+var_s0]
0x1800b2d54  mov     rbx, [r11+10h]
0x1800b2d58  mov     rdi, [r11+20h]
0x1800b2d5c  mov     rsp, r11
0x1800b2d5f  pop     rbp
0x1800b2d60  retn
```
