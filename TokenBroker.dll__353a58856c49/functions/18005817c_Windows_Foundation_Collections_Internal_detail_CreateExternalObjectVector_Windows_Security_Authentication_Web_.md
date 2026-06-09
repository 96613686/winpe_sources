# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,0> * *)

- ea: `0x18005817c`
- end: `0x18005841e`
- name: `??$CreateExternalObjectVector@VWebAccountClientView@Provider@Web@Authentication@Security@Windows@@V?$AgileVector@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@6@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@PEAVWebAccountClientView@Provider@Web@Authentication@Security@Windows@@@89Foundation@6@$0A@@1234@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180063184`

## callees

- `0x180007350`
- `0x180024a84`
- `0x180024ab0`
- `0x18005817c`
- `0x18008e690`
- `0x18009b108`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800581e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005822b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180058272`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005831c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800581e4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005822b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180058272`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005831c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800581cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005825d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058306`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800581cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005825d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058306`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058331`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180058331`

## string_xrefs

- `0x1800581c8`: `Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.Web.Provider.WebAccountClientView>`
- `0x180058256`: `Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.Web.Provider.WebAccountClientView>`
- `0x18005820f`: `Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.Web.Provider.WebAccountClientView>`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Authentication::Web::Provider::WebAccountClientView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::Web::Provider::WebAccountClientView *>,0>>(
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
  __int64 v15; // rcx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v23[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v24; // [rsp+48h] [rbp-B8h]
  GUID v25; // [rsp+58h] [rbp-A8h]
  GUID v26; // [rsp+68h] [rbp-98h]
  GUID v27; // [rsp+78h] [rbp-88h]
  GUID v28; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v31; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v32; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v33; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v34; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v35; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v36; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Bu);
  v4 = v3 - 1;
  if ( v3 > 0x6B )
    v4 = 107;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Security.Authentication.Web.Provider.WebAccountClientView>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Fu);
  v7 = v6 - 1;
  if ( v6 > 0x6F )
    v7 = 111;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Security.Authentication.Web.Provider.WebAccountClientView>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Du);
  v10 = v9 - 1;
  if ( v9 > 0x6D )
    v10 = 109;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Security.Authentication.Web.Provider.WebAccountClientView>",
          v10,
          &v33,
          &v34);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v23[0] = string;
  v23[1] = v32;
  v23[2] = v34;
  v24 = GUID_e7bd66ba_0bc7_4c66_bfd4_65d3082cbca8;
  v25 = GUID_43184ef9_2c17_599d_8fa3_48270f365492;
  v26 = GUID_3dfd5eff_8fa4_5e9d_8d1c_0f18d542be35;
  v27 = GUID_610e0f9d_aae4_54e1_bb0b_1aca14110abf;
  v28 = GUID_a5984607_661d_5e9c_a0ba_5c7d5f41af1c;
  v22 = 0;
  v12 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(&v22);
  v36 = 0;
  v13 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, v12);
  if ( ActivationFactory < 0 )
  {
    v15 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  v17 = v22;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v17, v23, &v21);
  if ( ActivationFactory < 0 )
  {
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = v21;
  v21 = 0;
  *a2 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  return 0;
}

```

## disassembly

```asm
0x18005817c  mov     [rsp-8+arg_0], rbx
0x180058181  mov     [rsp-8+arg_10], rdi
0x180058186  push    rbp
0x180058187  lea     rbp, [rsp-30h]
0x18005818c  sub     rsp, 130h
0x180058193  mov     rax, cs:__security_cookie
0x18005819a  xor     rax, rsp
0x18005819d  mov     [rbp+30h+var_10], rax
0x1800581a1  mov     rdi, rdx
0x1800581a4  mov     [rbp+30h+string], 0
0x1800581ac  mov     ebx, 6Bh ; 'k'
0x1800581b1  mov     ecx, ebx; unsigned int
0x1800581b3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800581b8  lea     edx, [rax-1]
0x1800581bb  cmp     eax, ebx
0x1800581bd  cmova   edx, ebx; length
0x1800581c0  lea     r9, [rbp+30h+string]; string
0x1800581c4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800581c8  lea     rcx, aWindowsFoundat_3; "Windows.Foundation.Collections.IVector`"...
0x1800581cf  call    cs:__imp_WindowsCreateStringReference
0x1800581d5  test    eax, eax
0x1800581d7  jns     short loc_1800581EB
0x1800581d9  xor     r9d, r9d; lpArguments
0x1800581dc  xor     r8d, r8d; nNumberOfArguments
0x1800581df  lea     edx, [rbx-6Ah]; dwExceptionFlags
0x1800581e2  mov     ecx, eax; dwExceptionCode
0x1800581e4  call    cs:__imp_RaiseException
0x1800581ea  int     3; Trap to Debugger
0x1800581eb  mov     [rbp+30h+var_58], 0
0x1800581f3  mov     ebx, 6Fh ; 'o'
0x1800581f8  mov     ecx, ebx; unsigned int
0x1800581fa  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800581ff  lea     edx, [rax-1]
0x180058202  cmp     eax, ebx
0x180058204  cmova   edx, ebx; length
0x180058207  lea     r9, [rbp+30h+var_58]; string
0x18005820b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18005820f  lea     rcx, aWindowsFoundat_7; "Windows.Foundation.Collections.IVectorV"...
0x180058216  call    cs:__imp_WindowsCreateStringReference
0x18005821c  test    eax, eax
0x18005821e  jns     short loc_180058232
0x180058220  xor     r9d, r9d; lpArguments
0x180058223  xor     r8d, r8d; nNumberOfArguments
0x180058226  lea     edx, [rbx-6Eh]; dwExceptionFlags
0x180058229  mov     ecx, eax; dwExceptionCode
0x18005822b  call    cs:__imp_RaiseException
0x180058231  int     3; Trap to Debugger
0x180058232  mov     [rbp+30h+var_38], 0
0x18005823a  mov     ebx, 6Dh ; 'm'
0x18005823f  mov     ecx, ebx; unsigned int
0x180058241  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180058246  lea     edx, [rax-1]
0x180058249  cmp     eax, ebx
0x18005824b  cmova   edx, ebx; length
0x18005824e  lea     r9, [rbp+30h+var_38]; string
0x180058252  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180058256  lea     rcx, aWindowsFoundat_18; "Windows.Foundation.Collections.IIterato"...
0x18005825d  call    cs:__imp_WindowsCreateStringReference
0x180058263  test    eax, eax
0x180058265  jns     short loc_180058279
0x180058267  xor     r9d, r9d; lpArguments
0x18005826a  xor     r8d, r8d; nNumberOfArguments
0x18005826d  lea     edx, [rbx-6Ch]; dwExceptionFlags
0x180058270  mov     ecx, eax; dwExceptionCode
0x180058272  call    cs:__imp_RaiseException
0x180058278  int     3; Trap to Debugger
0x180058279  mov     rax, [rbp+30h+string]
0x18005827d  mov     [rsp+130h+var_100], rax
0x180058282  mov     rax, [rbp+30h+var_58]
0x180058286  mov     [rsp+130h+var_F8], rax
0x18005828b  mov     rax, [rbp+30h+var_38]
0x18005828f  mov     [rsp+130h+var_F0], rax
0x180058294  movups  xmm0, xmmword ptr cs:_GUID_e7bd66ba_0bc7_4c66_bfd4_65d3082cbca8.Data1
0x18005829b  movdqu  [rsp+130h+var_E8], xmm0
0x1800582a1  movups  xmm1, xmmword ptr cs:_GUID_43184ef9_2c17_599d_8fa3_48270f365492.Data1
0x1800582a8  movdqu  [rsp+130h+var_D8], xmm1
0x1800582ae  movups  xmm0, xmmword ptr cs:_GUID_3dfd5eff_8fa4_5e9d_8d1c_0f18d542be35.Data1
0x1800582b5  movdqu  [rsp+130h+var_C8], xmm0
0x1800582bb  movups  xmm1, xmmword ptr cs:_GUID_610e0f9d_aae4_54e1_bb0b_1aca14110abf.Data1
0x1800582c2  movdqu  [rsp+130h+var_B8], xmm1
0x1800582c8  movups  xmm0, xmmword ptr cs:_GUID_a5984607_661d_5e9c_a0ba_5c7d5f41af1c.Data1
0x1800582cf  movdqu  [rbp+30h+var_A8], xmm0
0x1800582d4  mov     [rsp+130h+var_108], 0
0x1800582dd  lea     rcx, [rsp+130h+var_108]
0x1800582e2  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>>)
0x1800582e7  mov     rbx, rax
0x1800582ea  mov     [rbp+30h+var_18], 0
0x1800582f2  lea     r9, [rbp+30h+var_18]; string
0x1800582f6  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800582fa  mov     edx, 2Ch ; ','; length
0x1800582ff  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180058306  call    cs:__imp_WindowsCreateStringReference
0x18005830c  test    eax, eax
0x18005830e  jns     short loc_180058323
0x180058310  xor     r9d, r9d; lpArguments
0x180058313  xor     r8d, r8d; nNumberOfArguments
0x180058316  lea     edx, [r9+1]; dwExceptionFlags
0x18005831a  mov     ecx, eax; dwExceptionCode
0x18005831c  call    cs:__imp_RaiseException
0x180058322  int     3; Trap to Debugger
0x180058323  mov     r8, rbx
0x180058326  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18005832d  mov     rcx, [rbp+30h+var_18]
0x180058331  call    cs:__imp_RoGetActivationFactory
0x180058337  mov     ebx, eax
0x180058339  test    eax, eax
0x18005833b  jns     short loc_180058364
0x18005833d  mov     rcx, [rsp+130h+var_108]
0x180058342  test    rcx, rcx
0x180058345  jz      short loc_18005835D
0x180058347  mov     [rsp+130h+var_108], 0
0x180058350  mov     rdx, [rcx]
0x180058353  mov     rax, [rdx+10h]
0x180058357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005835c  nop
0x18005835d  mov     eax, ebx
0x18005835f  jmp     loc_1800583FD
0x180058364  mov     [rsp+130h+var_110], 0
0x18005836d  mov     rbx, [rsp+130h+var_108]
0x180058372  lea     rcx, [rsp+130h+var_110]
0x180058377  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18005837c  lea     r8, [rsp+130h+var_110]
0x180058381  lea     rdx, [rsp+130h+var_100]
0x180058386  mov     rcx, rbx
0x180058389  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18005838e  mov     ebx, eax
0x180058390  test    eax, eax
0x180058392  jns     short loc_1800583D6
0x180058394  mov     rcx, [rsp+130h+var_110]
0x180058399  test    rcx, rcx
0x18005839c  jz      short loc_1800583B4
0x18005839e  mov     [rsp+130h+var_110], 0
0x1800583a7  mov     rdx, [rcx]
0x1800583aa  mov     rax, [rdx+10h]
0x1800583ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583b3  nop
0x1800583b4  mov     rcx, [rsp+130h+var_108]
0x1800583b9  test    rcx, rcx
0x1800583bc  jz      short loc_1800583D4
0x1800583be  mov     [rsp+130h+var_108], 0
0x1800583c7  mov     rax, [rcx]
0x1800583ca  mov     rax, [rax+10h]
0x1800583ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800583d3  nop
0x1800583d4  jmp     short loc_18005835D
0x1800583d6  mov     rax, [rsp+130h+var_110]
0x1800583db  mov     [rsp+130h+var_110], 0
0x1800583e4  mov     [rdi], rax
0x1800583e7  lea     rcx, [rsp+130h+var_110]
0x1800583ec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800583f1  lea     rcx, [rsp+130h+var_108]
0x1800583f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800583fb  xor     eax, eax
0x1800583fd  mov     rcx, [rbp+30h+var_10]
0x180058401  xor     rcx, rsp; StackCookie
0x180058404  call    __security_check_cookie
0x180058409  lea     r11, [rsp+130h+var_s0]
0x180058411  mov     rbx, [r11+10h]
0x180058415  mov     rdi, [r11+20h]
0x180058419  mov     rsp, r11
0x18005841c  pop     rbp
0x18005841d  retn
```
