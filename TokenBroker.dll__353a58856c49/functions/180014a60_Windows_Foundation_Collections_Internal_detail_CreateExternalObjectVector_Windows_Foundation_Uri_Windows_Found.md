# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,0> * *)

- ea: `0x180014a60`
- end: `0x180014c84`
- name: `??$CreateExternalObjectVector@VUri@Foundation@Windows@@V?$AgileVector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@$0A@@Internal@Collections@23@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@$0A@@1234@@Z`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180014020`

## callees

- `0x180007350`
- `0x180014a60`
- `0x18008e690`
- `0x18009b108`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c3a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c62`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c26`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c3a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c4e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014c62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ac2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014b69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ac2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014ae8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014b69`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014b87`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014b87`

## string_xrefs

- `0x180014a95`: `Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>`
- `0x180014abb`: `Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>`
- `0x180014ae1`: `Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::AgileVector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  HRESULT v4; // eax
  HRESULT v5; // eax
  HRESULT v6; // eax
  int ActivationFactory; // ebx
  int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v12; // rcx
  __int64 v13; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v14; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v15[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v16; // [rsp+48h] [rbp-B8h]
  GUID v17; // [rsp+58h] [rbp-A8h]
  GUID v18; // [rsp+68h] [rbp-98h]
  GUID v19; // [rsp+78h] [rbp-88h]
  GUID v20; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v23; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v24; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v25; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v26; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v27; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v28; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>",
         0x40u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  v24 = 0;
  v4 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>",
         0x44u,
         &v23,
         &v24);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  v26 = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>",
         0x42u,
         &v25,
         &v26);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v15[0] = string;
  v15[1] = v24;
  v15[2] = v26;
  v16 = GUID_9e365e57_48b2_4160_956f_c7385120bbfc;
  v17 = GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e;
  v18 = GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50;
  v19 = GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447;
  v20 = GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5;
  v13 = 0;
  v28 = 0;
  v6 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v27, &v28);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v28, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v13);
  if ( ActivationFactory < 0 )
  {
    v12 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return (unsigned int)ActivationFactory;
  }
  else
  {
    v14 = 0;
    v8 =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v13, v15, &v14);
    if ( v8 < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
      return (unsigned int)v8;
    }
    else
    {
      v9 = v14;
      v14 = 0;
      *a2 = v9;
      v10 = v13;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      return 0;
    }
  }
}

```

## disassembly

```asm
0x180014a60  push    rbp
0x180014a62  push    rbx
0x180014a63  push    rsi
0x180014a64  push    rdi
0x180014a65  lea     rbp, [rsp-38h]
0x180014a6a  sub     rsp, 138h
0x180014a71  mov     rax, cs:__security_cookie
0x180014a78  xor     rax, rsp
0x180014a7b  mov     [rbp+50h+var_30], rax
0x180014a7f  mov     rdi, rdx
0x180014a82  xor     esi, esi
0x180014a84  mov     [rbp+50h+string], rsi
0x180014a88  lea     r9, [rbp+50h+string]; string
0x180014a8c  lea     r8, [rbp+50h+hstringHeader]; hstringHeader
0x180014a90  mov     edx, 40h ; '@'; length
0x180014a95  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IVector`"...
0x180014a9c  call    cs:__imp_WindowsCreateStringReference
0x180014aa2  test    eax, eax
0x180014aa4  js      loc_180014C19
0x180014aaa  mov     [rbp+50h+var_78], rsi
0x180014aae  lea     r9, [rbp+50h+var_78]; string
0x180014ab2  lea     r8, [rbp+50h+var_90]; hstringHeader
0x180014ab6  mov     edx, 44h ; 'D'; length
0x180014abb  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IVectorV"...
0x180014ac2  call    cs:__imp_WindowsCreateStringReference
0x180014ac8  test    eax, eax
0x180014aca  js      loc_180014C2D
0x180014ad0  mov     [rbp+50h+var_58], rsi
0x180014ad4  lea     r9, [rbp+50h+var_58]; string
0x180014ad8  lea     r8, [rbp+50h+var_70]; hstringHeader
0x180014adc  mov     edx, 42h ; 'B'; length
0x180014ae1  lea     rcx, aWindowsFoundat_11; "Windows.Foundation.Collections.IIterato"...
0x180014ae8  call    cs:__imp_WindowsCreateStringReference
0x180014aee  test    eax, eax
0x180014af0  js      loc_180014C41
0x180014af6  mov     rax, [rbp+50h+string]
0x180014afa  mov     [rsp+150h+var_120], rax
0x180014aff  mov     rax, [rbp+50h+var_78]
0x180014b03  mov     [rsp+150h+var_118], rax
0x180014b08  mov     rax, [rbp+50h+var_58]
0x180014b0c  mov     [rsp+150h+var_110], rax
0x180014b11  movups  xmm0, xmmword ptr cs:_GUID_9e365e57_48b2_4160_956f_c7385120bbfc.Data1
0x180014b18  movups  [rsp+150h+var_108], xmm0
0x180014b1d  movups  xmm1, xmmword ptr cs:_GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e.Data1
0x180014b24  movups  [rsp+150h+var_F8], xmm1
0x180014b29  movups  xmm0, xmmword ptr cs:_GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50.Data1
0x180014b30  movups  [rsp+150h+var_E8], xmm0
0x180014b35  movups  xmm1, xmmword ptr cs:_GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447.Data1
0x180014b3c  movups  [rsp+150h+var_D8], xmm1
0x180014b41  movups  xmm0, xmmword ptr cs:_GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5.Data1
0x180014b48  movups  [rbp+50h+var_C8], xmm0
0x180014b4c  mov     [rsp+150h+var_130], rsi
0x180014b51  mov     [rbp+50h+var_38], rsi
0x180014b55  lea     r9, [rbp+50h+var_38]; string
0x180014b59  lea     r8, [rbp+50h+var_50]; hstringHeader
0x180014b5d  mov     edx, 2Ch ; ','; length
0x180014b62  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180014b69  call    cs:__imp_WindowsCreateStringReference
0x180014b6f  test    eax, eax
0x180014b71  js      loc_180014C55
0x180014b77  lea     r8, [rsp+150h+var_130]
0x180014b7c  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180014b83  mov     rcx, [rbp+50h+var_38]
0x180014b87  call    cs:__imp_RoGetActivationFactory
0x180014b8d  mov     ebx, eax
0x180014b8f  test    eax, eax
0x180014b91  js      short loc_180014BF9
0x180014b93  mov     [rsp+150h+var_128], rsi
0x180014b98  lea     r8, [rsp+150h+var_128]
0x180014b9d  lea     rdx, [rsp+150h+var_120]
0x180014ba2  mov     rcx, [rsp+150h+var_130]
0x180014ba7  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180014bac  mov     ebx, eax
0x180014bae  test    eax, eax
0x180014bb0  js      loc_180014C69
0x180014bb6  mov     rax, [rsp+150h+var_128]
0x180014bbb  mov     [rsp+150h+var_128], rsi
0x180014bc0  mov     [rdi], rax
0x180014bc3  mov     rcx, [rsp+150h+var_130]
0x180014bc8  test    rcx, rcx
0x180014bcb  jz      short loc_180014BDF
0x180014bcd  mov     [rsp+150h+var_130], rsi
0x180014bd2  mov     rax, [rcx]
0x180014bd5  mov     rax, [rax+10h]
0x180014bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bde  nop
0x180014bdf  xor     eax, eax
0x180014be1  mov     rcx, [rbp+50h+var_30]
0x180014be5  xor     rcx, rsp; StackCookie
0x180014be8  call    __security_check_cookie
0x180014bed  add     rsp, 138h
0x180014bf4  pop     rdi
0x180014bf5  pop     rsi
0x180014bf6  pop     rbx
0x180014bf7  pop     rbp
0x180014bf8  retn
0x180014bf9  mov     rcx, [rsp+150h+var_130]
0x180014bfe  test    rcx, rcx
0x180014c01  jz      short loc_180014C15
0x180014c03  mov     [rsp+150h+var_130], rsi
0x180014c08  mov     rax, [rcx]
0x180014c0b  mov     rax, [rax+10h]
0x180014c0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c14  nop
0x180014c15  mov     eax, ebx
0x180014c17  jmp     short loc_180014BE1
0x180014c19  xor     r9d, r9d; lpArguments
0x180014c1c  xor     r8d, r8d; nNumberOfArguments
0x180014c1f  mov     edx, 1; dwExceptionFlags
0x180014c24  mov     ecx, eax; dwExceptionCode
0x180014c26  call    cs:__imp_RaiseException
0x180014c2c  int     3; Trap to Debugger
0x180014c2d  xor     r9d, r9d; lpArguments
0x180014c30  xor     r8d, r8d; nNumberOfArguments
0x180014c33  mov     edx, 1; dwExceptionFlags
0x180014c38  mov     ecx, eax; dwExceptionCode
0x180014c3a  call    cs:__imp_RaiseException
0x180014c40  int     3; Trap to Debugger
0x180014c41  xor     r9d, r9d; lpArguments
0x180014c44  xor     r8d, r8d; nNumberOfArguments
0x180014c47  mov     edx, 1; dwExceptionFlags
0x180014c4c  mov     ecx, eax; dwExceptionCode
0x180014c4e  call    cs:__imp_RaiseException
0x180014c54  int     3; Trap to Debugger
0x180014c55  xor     r9d, r9d; lpArguments
0x180014c58  xor     r8d, r8d; nNumberOfArguments
0x180014c5b  mov     edx, 1; dwExceptionFlags
0x180014c60  mov     ecx, eax; dwExceptionCode
0x180014c62  call    cs:__imp_RaiseException
0x180014c68  int     3; Trap to Debugger
0x180014c69  lea     rcx, [rsp+150h+var_128]
0x180014c6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014c73  lea     rcx, [rsp+150h+var_130]
0x180014c78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014c7d  mov     eax, ebx
0x180014c7f  jmp     loc_180014BE1
```
