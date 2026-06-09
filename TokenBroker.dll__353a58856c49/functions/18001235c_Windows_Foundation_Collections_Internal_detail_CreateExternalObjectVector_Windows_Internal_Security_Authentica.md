# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *>,0> * *)

- ea: `0x18001235c`
- end: `0x18001261e`
- name: `??$CreateExternalObjectVector@VWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@V?$AgileVector@PEAVWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@@5Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@@5896@$0A@@5Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@@5Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWamProviderRegistrationInformation@Web@Authentication@Security@Internal@Windows@@@5896@$0A@@1234@@Z`
- size: `706`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012290`

## callees

- `0x180007350`
- `0x18001235c`
- `0x180024a84`
- `0x180024ab0`
- `0x18008e690`
- `0x18009b108`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800125de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800125f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012604`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012617`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800125de`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800125f1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012604`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180012617`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800123af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800123e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800124bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800123af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800123e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180012421`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800124bc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800124d8`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800124d8`

## string_xrefs

- `0x18001241a`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.Security.Authentication.Web.WamProviderRegistrationInformation>`
- `0x1800123e1`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Security.Authentication.Web.WamProviderRegistrationInformation>`
- `0x1800123a8`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.Security.Authentication.Web.WamProviderRegistrationInformation>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Security::Authentication::Web::WamProviderRegistrationInformation *>,0>>(
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
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v24[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v25; // [rsp+48h] [rbp-B8h]
  GUID v26; // [rsp+58h] [rbp-A8h]
  GUID v27; // [rsp+68h] [rbp-98h]
  GUID v28; // [rsp+78h] [rbp-88h]
  GUID v29; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v32; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v33; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v34; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v35; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v36; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v37; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x79u);
  v4 = v3 - 1;
  if ( v3 > 0x79 )
    v4 = 121;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.Security.Authentication.Web.WamProviderRegistrationInformation>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x7Du);
  v7 = v6 - 1;
  if ( v6 > 0x7D )
    v7 = 125;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.Security.Authentication.Web.WamProviderRegistrationInformation>",
         v7,
         &v32,
         &v33);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v35 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x7Bu);
  v10 = v9 - 1;
  if ( v9 > 0x7B )
    v10 = 123;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.Security.Authentication.Web.WamProviderRegistrationInformation>",
          v10,
          &v34,
          &v35);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v24[0] = string;
  v24[1] = v33;
  v24[2] = v35;
  v25 = GUID_63a0a1e5_f8fe_4ba6_8508_caef1277dd35;
  v26 = GUID_c08c94c3_8959_5de0_89b9_9453e2fb4ad6;
  v27 = GUID_a6a36de6_0931_51a1_bdd2_d73f4f6dff22;
  v28 = GUID_37dc6a44_0dfb_59f1_8443_f5abbe570e26;
  v29 = GUID_ba332cec_b667_5c9d_a963_ff4b920887fe;
  v22 = 0;
  v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v22);
  v37 = 0;
  v13 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v36, &v37);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    JUMPOUT(0x18001261DLL);
  }
  ActivationFactory = RoGetActivationFactory(v37, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, v12);
  if ( ActivationFactory < 0 )
  {
    v21 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return (unsigned int)ActivationFactory;
  }
  v23 = 0;
  v15 = v22;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v15, v24, &v23);
  if ( ActivationFactory < 0 )
  {
    v16 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = v23;
  v23 = 0;
  *a2 = v19;
  v20 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return 0;
}

```

## disassembly

```asm
0x18001235c  mov     [rsp-8+arg_0], rbx
0x180012361  mov     [rsp-8+arg_10], rdi
0x180012366  push    rbp
0x180012367  lea     rbp, [rsp-30h]
0x18001236c  sub     rsp, 130h
0x180012373  mov     rax, cs:__security_cookie
0x18001237a  xor     rax, rsp
0x18001237d  mov     [rbp+30h+var_10], rax
0x180012381  mov     rdi, rdx
0x180012384  mov     [rbp+30h+string], 0
0x18001238c  mov     ebx, 79h ; 'y'
0x180012391  mov     ecx, ebx; unsigned int
0x180012393  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180012398  lea     edx, [rax-1]
0x18001239b  cmp     eax, ebx
0x18001239d  cmova   edx, ebx; length
0x1800123a0  lea     r9, [rbp+30h+string]; string
0x1800123a4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800123a8  lea     rcx, aWindowsFoundat_26; "Windows.Foundation.Collections.IVector`"...
0x1800123af  call    cs:__imp_WindowsCreateStringReference
0x1800123b5  test    eax, eax
0x1800123b7  js      loc_1800125D2
0x1800123bd  mov     [rbp+30h+var_58], 0
0x1800123c5  mov     ebx, 7Dh ; '}'
0x1800123ca  mov     ecx, ebx; unsigned int
0x1800123cc  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800123d1  lea     edx, [rax-1]
0x1800123d4  cmp     eax, ebx
0x1800123d6  cmova   edx, ebx; length
0x1800123d9  lea     r9, [rbp+30h+var_58]; string
0x1800123dd  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800123e1  lea     rcx, aWindowsFoundat_25; "Windows.Foundation.Collections.IVectorV"...
0x1800123e8  call    cs:__imp_WindowsCreateStringReference
0x1800123ee  test    eax, eax
0x1800123f0  js      loc_1800125E5
0x1800123f6  mov     [rbp+30h+var_38], 0
0x1800123fe  mov     ebx, 7Bh ; '{'
0x180012403  mov     ecx, ebx; unsigned int
0x180012405  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18001240a  lea     edx, [rax-1]
0x18001240d  cmp     eax, ebx
0x18001240f  cmova   edx, ebx; length
0x180012412  lea     r9, [rbp+30h+var_38]; string
0x180012416  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18001241a  lea     rcx, aWindowsFoundat_24; "Windows.Foundation.Collections.IIterato"...
0x180012421  call    cs:__imp_WindowsCreateStringReference
0x180012427  test    eax, eax
0x180012429  js      loc_1800125F8
0x18001242f  mov     rax, [rbp+30h+string]
0x180012433  mov     [rsp+130h+var_100], rax
0x180012438  mov     rax, [rbp+30h+var_58]
0x18001243c  mov     [rsp+130h+var_F8], rax
0x180012441  mov     rax, [rbp+30h+var_38]
0x180012445  mov     [rsp+130h+var_F0], rax
0x18001244a  movups  xmm0, xmmword ptr cs:_GUID_63a0a1e5_f8fe_4ba6_8508_caef1277dd35.Data1
0x180012451  movdqu  [rsp+130h+var_E8], xmm0
0x180012457  movups  xmm1, xmmword ptr cs:_GUID_c08c94c3_8959_5de0_89b9_9453e2fb4ad6.Data1
0x18001245e  movdqu  [rsp+130h+var_D8], xmm1
0x180012464  movups  xmm0, xmmword ptr cs:_GUID_a6a36de6_0931_51a1_bdd2_d73f4f6dff22.Data1
0x18001246b  movdqu  [rsp+130h+var_C8], xmm0
0x180012471  movups  xmm1, xmmword ptr cs:_GUID_37dc6a44_0dfb_59f1_8443_f5abbe570e26.Data1
0x180012478  movdqu  [rsp+130h+var_B8], xmm1
0x18001247e  movups  xmm0, xmmword ptr cs:_GUID_ba332cec_b667_5c9d_a963_ff4b920887fe.Data1
0x180012485  movdqu  [rbp+30h+var_A8], xmm0
0x18001248a  mov     [rsp+130h+var_110], 0
0x180012493  lea     rcx, [rsp+130h+var_110]
0x180012498  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x18001249d  mov     rbx, rax
0x1800124a0  mov     [rbp+30h+var_18], 0
0x1800124a8  lea     r9, [rbp+30h+var_18]; string
0x1800124ac  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800124b0  mov     edx, 2Ch ; ','; length
0x1800124b5  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800124bc  call    cs:__imp_WindowsCreateStringReference
0x1800124c2  test    eax, eax
0x1800124c4  js      loc_18001260B
0x1800124ca  mov     r8, rbx
0x1800124cd  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800124d4  mov     rcx, [rbp+30h+var_18]
0x1800124d8  call    cs:__imp_RoGetActivationFactory
0x1800124de  mov     ebx, eax
0x1800124e0  test    eax, eax
0x1800124e2  js      loc_1800125B0
0x1800124e8  mov     [rsp+130h+var_108], 0
0x1800124f1  mov     rbx, [rsp+130h+var_110]
0x1800124f6  lea     rcx, [rsp+130h+var_108]
0x1800124fb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180012500  lea     r8, [rsp+130h+var_108]
0x180012505  lea     rdx, [rsp+130h+var_100]
0x18001250a  mov     rcx, rbx
0x18001250d  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180012512  mov     ebx, eax
0x180012514  test    eax, eax
0x180012516  jns     short loc_18001257B
0x180012518  mov     rcx, [rsp+130h+var_108]
0x18001251d  test    rcx, rcx
0x180012520  jz      short loc_180012538
0x180012522  mov     [rsp+130h+var_108], 0
0x18001252b  mov     rdx, [rcx]
0x18001252e  mov     rax, [rdx+10h]
0x180012532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012537  nop
0x180012538  mov     rcx, [rsp+130h+var_110]
0x18001253d  test    rcx, rcx
0x180012540  jz      short loc_180012558
0x180012542  mov     [rsp+130h+var_110], 0
0x18001254b  mov     rax, [rcx]
0x18001254e  mov     rax, [rax+10h]
0x180012552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012557  nop
0x180012558  mov     eax, ebx
0x18001255a  mov     rcx, [rbp+30h+var_10]
0x18001255e  xor     rcx, rsp; StackCookie
0x180012561  call    __security_check_cookie
0x180012566  lea     r11, [rsp+130h+var_s0]
0x18001256e  mov     rbx, [r11+10h]
0x180012572  mov     rdi, [r11+20h]
0x180012576  mov     rsp, r11
0x180012579  pop     rbp
0x18001257a  retn
0x18001257b  mov     rax, [rsp+130h+var_108]
0x180012580  mov     [rsp+130h+var_108], 0
0x180012589  mov     [rdi], rax
0x18001258c  mov     rcx, [rsp+130h+var_110]
0x180012591  test    rcx, rcx
0x180012594  jz      short loc_1800125AC
0x180012596  mov     [rsp+130h+var_110], 0
0x18001259f  mov     rax, [rcx]
0x1800125a2  mov     rax, [rax+10h]
0x1800125a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125ab  nop
0x1800125ac  xor     eax, eax
0x1800125ae  jmp     short loc_18001255A
0x1800125b0  mov     rcx, [rsp+130h+var_110]
0x1800125b5  test    rcx, rcx
0x1800125b8  jz      short loc_1800125D0
0x1800125ba  mov     [rsp+130h+var_110], 0
0x1800125c3  mov     rdx, [rcx]
0x1800125c6  mov     rax, [rdx+10h]
0x1800125ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125cf  nop
0x1800125d0  jmp     short loc_180012558
0x1800125d2  xor     r9d, r9d; lpArguments
0x1800125d5  xor     r8d, r8d; nNumberOfArguments
0x1800125d8  lea     edx, [r9+1]; dwExceptionFlags
0x1800125dc  mov     ecx, eax; dwExceptionCode
0x1800125de  call    cs:__imp_RaiseException
0x1800125e4  int     3; Trap to Debugger
0x1800125e5  xor     r9d, r9d; lpArguments
0x1800125e8  xor     r8d, r8d; nNumberOfArguments
0x1800125eb  lea     edx, [r9+1]; dwExceptionFlags
0x1800125ef  mov     ecx, eax; dwExceptionCode
0x1800125f1  call    cs:__imp_RaiseException
0x1800125f7  int     3; Trap to Debugger
0x1800125f8  xor     r9d, r9d; lpArguments
0x1800125fb  xor     r8d, r8d; nNumberOfArguments
0x1800125fe  lea     edx, [r9+1]; dwExceptionFlags
0x180012602  mov     ecx, eax; dwExceptionCode
0x180012604  call    cs:__imp_RaiseException
0x18001260a  int     3; Trap to Debugger
0x18001260b  xor     r9d, r9d; lpArguments
0x18001260e  xor     r8d, r8d; nNumberOfArguments
0x180012611  lea     edx, [r9+1]; dwExceptionFlags
0x180012615  mov     ecx, eax; dwExceptionCode
0x180012617  call    cs:__imp_RaiseException
```
