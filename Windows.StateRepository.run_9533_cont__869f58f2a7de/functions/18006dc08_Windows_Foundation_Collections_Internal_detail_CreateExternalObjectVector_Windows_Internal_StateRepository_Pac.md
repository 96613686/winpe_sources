# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageProperty,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageProperty *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageProperty *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageProperty *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageProperty *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageProperty *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageProperty *>,0> * *)

- ea: `0x18006dc08`
- end: `0x18006de75`
- name: `??$CreateExternalObjectVector@VPackageProperty@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackageProperty@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageProperty@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageProperty@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackageProperty@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageProperty@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageProperty@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006dac0`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18006dc08`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dc70`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dcb7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dcfe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dda5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dc70`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dcb7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dcfe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006dda5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006ddbc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006ddbc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dc5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dca2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dce9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dd8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dc5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dca2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dce9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006dd8f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageProperty,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageProperty *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageProperty *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageProperty *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v4 = v3 - 1;
  if ( v3 > 0x5A )
    v4 = 90;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageProperty>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Eu);
  v7 = v6 - 1;
  if ( v6 > 0x5E )
    v7 = 94;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageProperty>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v10 = v9 - 1;
  if ( v9 > 0x5C )
    v10 = 92;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageProperty>",
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
  v21 = GUID_bac7aafa_fbb8_4b69_b8cf_7c987fd8dc1a;
  v22 = GUID_64e63837_bfa8_5263_bb01_03273936c8a7;
  v23 = GUID_79a5c465_ef19_5e2a_bdf2_7b368df9c018;
  v24 = GUID_b3eb17fe_34a5_5bde_be4b_18d3ad226dc7;
  v25 = GUID_d0a4f700_c2e7_55fe_9d6d_95251e374aea;
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
0x18006dc08  mov     [rsp-8+arg_0], rbx
0x18006dc0d  mov     [rsp-8+arg_10], rdi
0x18006dc12  push    rbp
0x18006dc13  lea     rbp, [rsp-30h]
0x18006dc18  sub     rsp, 130h
0x18006dc1f  mov     rax, cs:__security_cookie
0x18006dc26  xor     rax, rsp
0x18006dc29  mov     [rbp+30h+var_10], rax
0x18006dc2d  mov     rdi, rdx
0x18006dc30  mov     [rbp+30h+string], 0
0x18006dc38  mov     ebx, 5Ah ; 'Z'
0x18006dc3d  mov     ecx, ebx; unsigned int
0x18006dc3f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18006dc44  lea     edx, [rax-1]
0x18006dc47  cmp     eax, ebx
0x18006dc49  cmova   edx, ebx; length
0x18006dc4c  lea     r9, [rbp+30h+string]; string
0x18006dc50  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18006dc54  lea     rcx, aWindowsFoundat_76; "Windows.Foundation.Collections.IVector`"...
0x18006dc5b  call    cs:__imp_WindowsCreateStringReference
0x18006dc61  test    eax, eax
0x18006dc63  jns     short loc_18006DC77
0x18006dc65  xor     r9d, r9d; lpArguments
0x18006dc68  xor     r8d, r8d; nNumberOfArguments
0x18006dc6b  lea     edx, [rbx-59h]; dwExceptionFlags
0x18006dc6e  mov     ecx, eax; dwExceptionCode
0x18006dc70  call    cs:__imp_RaiseException
0x18006dc76  int     3; Trap to Debugger
0x18006dc77  mov     [rbp+30h+var_58], 0
0x18006dc7f  mov     ebx, 5Eh ; '^'
0x18006dc84  mov     ecx, ebx; unsigned int
0x18006dc86  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18006dc8b  lea     edx, [rax-1]
0x18006dc8e  cmp     eax, ebx
0x18006dc90  cmova   edx, ebx; length
0x18006dc93  lea     r9, [rbp+30h+var_58]; string
0x18006dc97  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18006dc9b  lea     rcx, aWindowsFoundat_63; "Windows.Foundation.Collections.IVectorV"...
0x18006dca2  call    cs:__imp_WindowsCreateStringReference
0x18006dca8  test    eax, eax
0x18006dcaa  jns     short loc_18006DCBE
0x18006dcac  xor     r9d, r9d; lpArguments
0x18006dcaf  xor     r8d, r8d; nNumberOfArguments
0x18006dcb2  lea     edx, [rbx-5Dh]; dwExceptionFlags
0x18006dcb5  mov     ecx, eax; dwExceptionCode
0x18006dcb7  call    cs:__imp_RaiseException
0x18006dcbd  int     3; Trap to Debugger
0x18006dcbe  mov     [rbp+30h+var_38], 0
0x18006dcc6  mov     ebx, 5Ch ; '\'
0x18006dccb  mov     ecx, ebx; unsigned int
0x18006dccd  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18006dcd2  lea     edx, [rax-1]
0x18006dcd5  cmp     eax, ebx
0x18006dcd7  cmova   edx, ebx; length
0x18006dcda  lea     r9, [rbp+30h+var_38]; string
0x18006dcde  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18006dce2  lea     rcx, aWindowsFoundat_84; "Windows.Foundation.Collections.IIterato"...
0x18006dce9  call    cs:__imp_WindowsCreateStringReference
0x18006dcef  test    eax, eax
0x18006dcf1  jns     short loc_18006DD05
0x18006dcf3  xor     r9d, r9d; lpArguments
0x18006dcf6  xor     r8d, r8d; nNumberOfArguments
0x18006dcf9  lea     edx, [rbx-5Bh]; dwExceptionFlags
0x18006dcfc  mov     ecx, eax; dwExceptionCode
0x18006dcfe  call    cs:__imp_RaiseException
0x18006dd04  int     3; Trap to Debugger
0x18006dd05  mov     rax, [rbp+30h+string]
0x18006dd09  mov     [rsp+130h+var_100], rax
0x18006dd0e  mov     rax, [rbp+30h+var_58]
0x18006dd12  mov     [rsp+130h+var_F8], rax
0x18006dd17  mov     rax, [rbp+30h+var_38]
0x18006dd1b  mov     [rsp+130h+var_F0], rax
0x18006dd20  movups  xmm0, xmmword ptr cs:_GUID_bac7aafa_fbb8_4b69_b8cf_7c987fd8dc1a.Data1
0x18006dd27  movdqu  [rsp+130h+var_E8], xmm0
0x18006dd2d  movups  xmm1, xmmword ptr cs:_GUID_64e63837_bfa8_5263_bb01_03273936c8a7.Data1
0x18006dd34  movdqu  [rsp+130h+var_D8], xmm1
0x18006dd3a  movups  xmm0, xmmword ptr cs:_GUID_79a5c465_ef19_5e2a_bdf2_7b368df9c018.Data1
0x18006dd41  movdqu  [rsp+130h+var_C8], xmm0
0x18006dd47  movups  xmm1, xmmword ptr cs:_GUID_b3eb17fe_34a5_5bde_be4b_18d3ad226dc7.Data1
0x18006dd4e  movdqu  [rsp+130h+var_B8], xmm1
0x18006dd54  movups  xmm0, xmmword ptr cs:_GUID_d0a4f700_c2e7_55fe_9d6d_95251e374aea.Data1
0x18006dd5b  movdqu  [rbp+30h+var_A8], xmm0
0x18006dd60  mov     [rsp+130h+var_110], 0
0x18006dd69  lea     rcx, [rsp+130h+var_110]
0x18006dd6e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006dd73  mov     [rbp+30h+var_18], 0
0x18006dd7b  lea     r9, [rbp+30h+var_18]; string
0x18006dd7f  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18006dd83  mov     edx, 2Ch ; ','; length
0x18006dd88  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18006dd8f  call    cs:__imp_WindowsCreateStringReference
0x18006dd95  test    eax, eax
0x18006dd97  jns     short loc_18006DDAC
0x18006dd99  xor     r9d, r9d; lpArguments
0x18006dd9c  xor     r8d, r8d; nNumberOfArguments
0x18006dd9f  lea     edx, [r9+1]; dwExceptionFlags
0x18006dda3  mov     ecx, eax; dwExceptionCode
0x18006dda5  call    cs:__imp_RaiseException
0x18006ddab  int     3; Trap to Debugger
0x18006ddac  lea     r8, [rsp+130h+var_110]
0x18006ddb1  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18006ddb8  mov     rcx, [rbp+30h+var_18]
0x18006ddbc  call    cs:__imp_RoGetActivationFactory
0x18006ddc2  mov     ebx, eax
0x18006ddc4  test    eax, eax
0x18006ddc6  jns     short loc_18006DDEC
0x18006ddc8  mov     rcx, [rsp+130h+var_110]
0x18006ddcd  test    rcx, rcx
0x18006ddd0  jz      short loc_18006DDE8
0x18006ddd2  mov     [rsp+130h+var_110], 0
0x18006dddb  mov     rdx, [rcx]
0x18006ddde  mov     rax, [rdx+10h]
0x18006dde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006dde7  nop
0x18006dde8  mov     eax, ebx
0x18006ddea  jmp     short loc_18006DE54
0x18006ddec  mov     [rsp+130h+var_108], 0
0x18006ddf5  mov     rbx, [rsp+130h+var_110]
0x18006ddfa  lea     rcx, [rsp+130h+var_108]
0x18006ddff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006de04  lea     r8, [rsp+130h+var_108]
0x18006de09  lea     rdx, [rsp+130h+var_100]
0x18006de0e  mov     rcx, rbx
0x18006de11  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18006de16  mov     ebx, eax
0x18006de18  lea     rcx, [rsp+130h+var_108]
0x18006de1d  test    eax, eax
0x18006de1f  jns     short loc_18006DE32
0x18006de21  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006de26  lea     rcx, [rsp+130h+var_110]
0x18006de2b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006de30  jmp     short loc_18006DDE8
0x18006de32  mov     rax, [rsp+130h+var_108]
0x18006de37  mov     [rsp+130h+var_108], 0
0x18006de40  mov     [rdi], rax
0x18006de43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006de48  lea     rcx, [rsp+130h+var_110]
0x18006de4d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006de52  xor     eax, eax
0x18006de54  mov     rcx, [rbp+30h+var_10]
0x18006de58  xor     rcx, rsp; StackCookie
0x18006de5b  call    __security_check_cookie
0x18006de60  lea     r11, [rsp+130h+var_s0]
0x18006de68  mov     rbx, [r11+10h]
0x18006de6c  mov     rdi, [r11+20h]
0x18006de70  mov     rsp, r11
0x18006de73  pop     rbp
0x18006de74  retn
```
