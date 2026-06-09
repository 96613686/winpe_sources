# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0> * *)

- ea: `0x180024544`
- end: `0x1800247de`
- name: `??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@1234@@Z`
- size: `666`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800277c4`
- `0x1800473c4`
- `0x18005f6c0`
- `0x18006e74c`
- `0x18006f778`
- `0x1800a7600`
- `0x1800abd50`
- `0x1800abfec`
- `0x1800b552c`
- `0x1800f1964`
- `0x1800f8c88`
- `0x1800fad20`
- `0x180100498`
- `0x180101d00`
- `0x180104c18`
- `0x18010aff4`
- `0x18010cf14`
- `0x18010fa10`

## callees

- `0x180007350`
- `0x180024544`
- `0x180024a84`
- `0x180024ab0`
- `0x18008e690`
- `0x18009b108`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024788`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002479b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800247ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800247c1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024788`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002479b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800247ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800247c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024597`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800245d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800246a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024597`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800245d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800246a4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800246c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800246c0`

## string_xrefs

- `0x1800245c9`: `Windows.Foundation.Collections.IVectorView`1<Windows.Security.Credentials.WebAccount>`
- `0x180024590`: `Windows.Foundation.Collections.IVector`1<Windows.Security.Credentials.WebAccount>`
- `0x180024602`: `Windows.Foundation.Collections.IIterator`1<Windows.Security.Credentials.WebAccount>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
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
  __int64 v12; // rbx
  HRESULT v13; // eax
  int ActivationFactory; // ebx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v22[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v23; // [rsp+48h] [rbp-B8h]
  GUID v24; // [rsp+58h] [rbp-A8h]
  GUID v25; // [rsp+68h] [rbp-98h]
  GUID v26; // [rsp+78h] [rbp-88h]
  GUID v27; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v30; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v31; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v32; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v33; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v34; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v35; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x51u);
  v4 = v3 - 1;
  if ( v3 > 0x51 )
    v4 = 81;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Security.Credentials.WebAccount>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x55u);
  v7 = v6 - 1;
  if ( v6 > 0x55 )
    v7 = 85;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Security.Credentials.WebAccount>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x53u);
  v10 = v9 - 1;
  if ( v9 > 0x53 )
    v10 = 83;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Security.Credentials.WebAccount>",
          v10,
          &v32,
          &v33);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v22[0] = string;
  v22[1] = v31;
  v22[2] = v33;
  v23 = GUID_69473eb2_8031_49be_80bb_96cb46d99aba;
  v24 = GUID_fe11c488_371a_5330_b7fa_282326fdfbda;
  v25 = GUID_e0798d3d_2b4a_589a_ab12_02dccc158afc;
  v26 = GUID_cb15d439_a910_542a_89ed_7cfe67848a83;
  v27 = GUID_bfb82cca_aebc_567c_95d9_eba25c365faa;
  v20 = 0;
  v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v20);
  v35 = 0;
  v13 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v34, &v35);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v35, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, v12);
  if ( ActivationFactory < 0 )
  {
    v19 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  v15 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v15, v22, &v21);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    return (unsigned int)ActivationFactory;
  }
  v16 = v21;
  v21 = 0;
  *a2 = v16;
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180024544  mov     [rsp-8+arg_0], rbx
0x180024549  mov     [rsp-8+arg_10], rdi
0x18002454e  push    rbp
0x18002454f  lea     rbp, [rsp-30h]
0x180024554  sub     rsp, 130h
0x18002455b  mov     rax, cs:__security_cookie
0x180024562  xor     rax, rsp
0x180024565  mov     [rbp+30h+var_10], rax
0x180024569  mov     rdi, rdx
0x18002456c  mov     [rbp+30h+string], 0
0x180024574  mov     ebx, 51h ; 'Q'
0x180024579  mov     ecx, ebx; unsigned int
0x18002457b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180024580  lea     edx, [rax-1]
0x180024583  cmp     eax, ebx
0x180024585  cmova   edx, ebx; length
0x180024588  lea     r9, [rbp+30h+string]; string
0x18002458c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180024590  lea     rcx, aWindowsFoundat_31; "Windows.Foundation.Collections.IVector`"...
0x180024597  call    cs:__imp_WindowsCreateStringReference
0x18002459d  test    eax, eax
0x18002459f  js      loc_18002477C
0x1800245a5  mov     [rbp+30h+var_58], 0
0x1800245ad  mov     ebx, 55h ; 'U'
0x1800245b2  mov     ecx, ebx; unsigned int
0x1800245b4  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800245b9  lea     edx, [rax-1]
0x1800245bc  cmp     eax, ebx
0x1800245be  cmova   edx, ebx; length
0x1800245c1  lea     r9, [rbp+30h+var_58]; string
0x1800245c5  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800245c9  lea     rcx, aWindowsFoundat_41; "Windows.Foundation.Collections.IVectorV"...
0x1800245d0  call    cs:__imp_WindowsCreateStringReference
0x1800245d6  test    eax, eax
0x1800245d8  js      loc_18002478F
0x1800245de  mov     [rbp+30h+var_38], 0
0x1800245e6  mov     ebx, 53h ; 'S'
0x1800245eb  mov     ecx, ebx; unsigned int
0x1800245ed  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800245f2  lea     edx, [rax-1]
0x1800245f5  cmp     eax, ebx
0x1800245f7  cmova   edx, ebx; length
0x1800245fa  lea     r9, [rbp+30h+var_38]; string
0x1800245fe  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180024602  lea     rcx, aWindowsFoundat_21; "Windows.Foundation.Collections.IIterato"...
0x180024609  call    cs:__imp_WindowsCreateStringReference
0x18002460f  test    eax, eax
0x180024611  js      loc_1800247A2
0x180024617  mov     rax, [rbp+30h+string]
0x18002461b  mov     [rsp+130h+var_100], rax
0x180024620  mov     rax, [rbp+30h+var_58]
0x180024624  mov     [rsp+130h+var_F8], rax
0x180024629  mov     rax, [rbp+30h+var_38]
0x18002462d  mov     [rsp+130h+var_F0], rax
0x180024632  movups  xmm0, xmmword ptr cs:_GUID_69473eb2_8031_49be_80bb_96cb46d99aba.Data1
0x180024639  movdqu  [rsp+130h+var_E8], xmm0
0x18002463f  movups  xmm1, xmmword ptr cs:_GUID_fe11c488_371a_5330_b7fa_282326fdfbda.Data1
0x180024646  movdqu  [rsp+130h+var_D8], xmm1
0x18002464c  movups  xmm0, xmmword ptr cs:_GUID_e0798d3d_2b4a_589a_ab12_02dccc158afc.Data1
0x180024653  movdqu  [rsp+130h+var_C8], xmm0
0x180024659  movups  xmm1, xmmword ptr cs:_GUID_cb15d439_a910_542a_89ed_7cfe67848a83.Data1
0x180024660  movdqu  [rsp+130h+var_B8], xmm1
0x180024666  movups  xmm0, xmmword ptr cs:_GUID_bfb82cca_aebc_567c_95d9_eba25c365faa.Data1
0x18002466d  movdqu  [rbp+30h+var_A8], xmm0
0x180024672  mov     [rsp+130h+var_110], 0
0x18002467b  lea     rcx, [rsp+130h+var_110]
0x180024680  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x180024685  mov     rbx, rax
0x180024688  mov     [rbp+30h+var_18], 0
0x180024690  lea     r9, [rbp+30h+var_18]; string
0x180024694  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180024698  mov     edx, 2Ch ; ','; length
0x18002469d  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800246a4  call    cs:__imp_WindowsCreateStringReference
0x1800246aa  test    eax, eax
0x1800246ac  js      loc_1800247B5
0x1800246b2  mov     r8, rbx
0x1800246b5  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800246bc  mov     rcx, [rbp+30h+var_18]
0x1800246c0  call    cs:__imp_RoGetActivationFactory
0x1800246c6  mov     ebx, eax
0x1800246c8  test    eax, eax
0x1800246ca  js      loc_180024758
0x1800246d0  mov     [rsp+130h+var_108], 0
0x1800246d9  mov     rbx, [rsp+130h+var_110]
0x1800246de  lea     rcx, [rsp+130h+var_108]
0x1800246e3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800246e8  lea     r8, [rsp+130h+var_108]
0x1800246ed  lea     rdx, [rsp+130h+var_100]
0x1800246f2  mov     rcx, rbx
0x1800246f5  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800246fa  mov     ebx, eax
0x1800246fc  test    eax, eax
0x1800246fe  js      loc_1800247C8
0x180024704  mov     rax, [rsp+130h+var_108]
0x180024709  mov     [rsp+130h+var_108], 0
0x180024712  mov     [rdi], rax
0x180024715  mov     rcx, [rsp+130h+var_110]
0x18002471a  test    rcx, rcx
0x18002471d  jz      short loc_180024735
0x18002471f  mov     [rsp+130h+var_110], 0
0x180024728  mov     rax, [rcx]
0x18002472b  mov     rax, [rax+10h]
0x18002472f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024734  nop
0x180024735  xor     eax, eax
0x180024737  mov     rcx, [rbp+30h+var_10]
0x18002473b  xor     rcx, rsp; StackCookie
0x18002473e  call    __security_check_cookie
0x180024743  lea     r11, [rsp+130h+var_s0]
0x18002474b  mov     rbx, [r11+10h]
0x18002474f  mov     rdi, [r11+20h]
0x180024753  mov     rsp, r11
0x180024756  pop     rbp
0x180024757  retn
0x180024758  mov     rcx, [rsp+130h+var_110]
0x18002475d  test    rcx, rcx
0x180024760  jz      short loc_180024778
0x180024762  mov     [rsp+130h+var_110], 0
0x18002476b  mov     rdx, [rcx]
0x18002476e  mov     rax, [rdx+10h]
0x180024772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024777  nop
0x180024778  mov     eax, ebx
0x18002477a  jmp     short loc_180024737
0x18002477c  xor     r9d, r9d; lpArguments
0x18002477f  xor     r8d, r8d; nNumberOfArguments
0x180024782  lea     edx, [r9+1]; dwExceptionFlags
0x180024786  mov     ecx, eax; dwExceptionCode
0x180024788  call    cs:__imp_RaiseException
0x18002478e  int     3; Trap to Debugger
0x18002478f  xor     r9d, r9d; lpArguments
0x180024792  xor     r8d, r8d; nNumberOfArguments
0x180024795  lea     edx, [r9+1]; dwExceptionFlags
0x180024799  mov     ecx, eax; dwExceptionCode
0x18002479b  call    cs:__imp_RaiseException
0x1800247a1  int     3; Trap to Debugger
0x1800247a2  xor     r9d, r9d; lpArguments
0x1800247a5  xor     r8d, r8d; nNumberOfArguments
0x1800247a8  lea     edx, [r9+1]; dwExceptionFlags
0x1800247ac  mov     ecx, eax; dwExceptionCode
0x1800247ae  call    cs:__imp_RaiseException
0x1800247b4  int     3; Trap to Debugger
0x1800247b5  xor     r9d, r9d; lpArguments
0x1800247b8  xor     r8d, r8d; nNumberOfArguments
0x1800247bb  lea     edx, [r9+1]; dwExceptionFlags
0x1800247bf  mov     ecx, eax; dwExceptionCode
0x1800247c1  call    cs:__imp_RaiseException
0x1800247c7  int     3; Trap to Debugger
0x1800247c8  lea     rcx, [rsp+130h+var_108]
0x1800247cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800247d2  lea     rcx, [rsp+130h+var_110]
0x1800247d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800247dc  jmp     short loc_180024778
```
