# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::DynamicAppUriHandler,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::DynamicAppUriHandler *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::DynamicAppUriHandler *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::DynamicAppUriHandler *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::DynamicAppUriHandler *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::DynamicAppUriHandler *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::DynamicAppUriHandler *>,0> * *)

- ea: `0x1800be0b0`
- end: `0x1800be31d`
- name: `??$CreateExternalObjectVector@VDynamicAppUriHandler@StateRepository@Internal@Windows@@V?$AgileVector@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800869ec`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x1800be0b0`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be118`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be15f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be1a6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be24d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be118`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be15f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be1a6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800be24d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800be264`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800be264`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be14a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be237`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be103`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be14a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be191`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800be237`

## string_xrefs

- `0x1800be0fc`: `Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.DynamicAppUriHandler>`
- `0x1800be18a`: `Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.DynamicAppUriHandler>`
- `0x1800be143`: `Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.DynamicAppUriHandler>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::DynamicAppUriHandler,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::DynamicAppUriHandler *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::DynamicAppUriHandler *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::DynamicAppUriHandler *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Fu);
  v4 = v3 - 1;
  if ( v3 > 0x5F )
    v4 = 95;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.DynamicAppUriHandler>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v7 = v6 - 1;
  if ( v6 > 0x63 )
    v7 = 99;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.DynamicAppUriHandler>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x61u);
  v10 = v9 - 1;
  if ( v9 > 0x61 )
    v10 = 97;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.DynamicAppUriHandler>",
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
  v21 = GUID_6b7ae682_ed6f_478c_b6ae_1e22dfbc58f9;
  v22 = GUID_b18c9933_68c0_5b1d_bf3f_99cc5670b63b;
  v23 = GUID_a3bf7cc6_fe9a_5abe_a3bd_65ebd8312d4d;
  v24 = GUID_535914f4_18b3_5734_b7da_ef3b6585f492;
  v25 = GUID_2d1e4bc0_a9fe_5961_a2fc_6cbb4460f7eb;
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
0x1800be0b0  mov     [rsp-8+arg_0], rbx
0x1800be0b5  mov     [rsp-8+arg_10], rdi
0x1800be0ba  push    rbp
0x1800be0bb  lea     rbp, [rsp-30h]
0x1800be0c0  sub     rsp, 130h
0x1800be0c7  mov     rax, cs:__security_cookie
0x1800be0ce  xor     rax, rsp
0x1800be0d1  mov     [rbp+30h+var_10], rax
0x1800be0d5  mov     rdi, rdx
0x1800be0d8  mov     [rbp+30h+string], 0
0x1800be0e0  mov     ebx, 5Fh ; '_'
0x1800be0e5  mov     ecx, ebx; unsigned int
0x1800be0e7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800be0ec  lea     edx, [rax-1]
0x1800be0ef  cmp     eax, ebx
0x1800be0f1  cmova   edx, ebx; length
0x1800be0f4  lea     r9, [rbp+30h+string]; string
0x1800be0f8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800be0fc  lea     rcx, aWindowsFoundat_146; "Windows.Foundation.Collections.IVector`"...
0x1800be103  call    cs:__imp_WindowsCreateStringReference
0x1800be109  test    eax, eax
0x1800be10b  jns     short loc_1800BE11F
0x1800be10d  xor     r9d, r9d; lpArguments
0x1800be110  xor     r8d, r8d; nNumberOfArguments
0x1800be113  lea     edx, [rbx-5Eh]; dwExceptionFlags
0x1800be116  mov     ecx, eax; dwExceptionCode
0x1800be118  call    cs:__imp_RaiseException
0x1800be11e  int     3; Trap to Debugger
0x1800be11f  mov     [rbp+30h+var_58], 0
0x1800be127  mov     ebx, 63h ; 'c'
0x1800be12c  mov     ecx, ebx; unsigned int
0x1800be12e  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800be133  lea     edx, [rax-1]
0x1800be136  cmp     eax, ebx
0x1800be138  cmova   edx, ebx; length
0x1800be13b  lea     r9, [rbp+30h+var_58]; string
0x1800be13f  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800be143  lea     rcx, aWindowsFoundat_7; "Windows.Foundation.Collections.IVectorV"...
0x1800be14a  call    cs:__imp_WindowsCreateStringReference
0x1800be150  test    eax, eax
0x1800be152  jns     short loc_1800BE166
0x1800be154  xor     r9d, r9d; lpArguments
0x1800be157  xor     r8d, r8d; nNumberOfArguments
0x1800be15a  lea     edx, [rbx-62h]; dwExceptionFlags
0x1800be15d  mov     ecx, eax; dwExceptionCode
0x1800be15f  call    cs:__imp_RaiseException
0x1800be165  int     3; Trap to Debugger
0x1800be166  mov     [rbp+30h+var_38], 0
0x1800be16e  mov     ebx, 61h ; 'a'
0x1800be173  mov     ecx, ebx; unsigned int
0x1800be175  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800be17a  lea     edx, [rax-1]
0x1800be17d  cmp     eax, ebx
0x1800be17f  cmova   edx, ebx; length
0x1800be182  lea     r9, [rbp+30h+var_38]; string
0x1800be186  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800be18a  lea     rcx, aWindowsFoundat_95; "Windows.Foundation.Collections.IIterato"...
0x1800be191  call    cs:__imp_WindowsCreateStringReference
0x1800be197  test    eax, eax
0x1800be199  jns     short loc_1800BE1AD
0x1800be19b  xor     r9d, r9d; lpArguments
0x1800be19e  xor     r8d, r8d; nNumberOfArguments
0x1800be1a1  lea     edx, [rbx-60h]; dwExceptionFlags
0x1800be1a4  mov     ecx, eax; dwExceptionCode
0x1800be1a6  call    cs:__imp_RaiseException
0x1800be1ac  int     3; Trap to Debugger
0x1800be1ad  mov     rax, [rbp+30h+string]
0x1800be1b1  mov     [rsp+130h+var_100], rax
0x1800be1b6  mov     rax, [rbp+30h+var_58]
0x1800be1ba  mov     [rsp+130h+var_F8], rax
0x1800be1bf  mov     rax, [rbp+30h+var_38]
0x1800be1c3  mov     [rsp+130h+var_F0], rax
0x1800be1c8  movups  xmm0, xmmword ptr cs:_GUID_6b7ae682_ed6f_478c_b6ae_1e22dfbc58f9.Data1
0x1800be1cf  movdqu  [rsp+130h+var_E8], xmm0
0x1800be1d5  movups  xmm1, xmmword ptr cs:_GUID_b18c9933_68c0_5b1d_bf3f_99cc5670b63b.Data1
0x1800be1dc  movdqu  [rsp+130h+var_D8], xmm1
0x1800be1e2  movups  xmm0, xmmword ptr cs:_GUID_a3bf7cc6_fe9a_5abe_a3bd_65ebd8312d4d.Data1
0x1800be1e9  movdqu  [rsp+130h+var_C8], xmm0
0x1800be1ef  movups  xmm1, xmmword ptr cs:_GUID_535914f4_18b3_5734_b7da_ef3b6585f492.Data1
0x1800be1f6  movdqu  [rsp+130h+var_B8], xmm1
0x1800be1fc  movups  xmm0, xmmword ptr cs:_GUID_2d1e4bc0_a9fe_5961_a2fc_6cbb4460f7eb.Data1
0x1800be203  movdqu  [rbp+30h+var_A8], xmm0
0x1800be208  mov     [rsp+130h+var_110], 0
0x1800be211  lea     rcx, [rsp+130h+var_110]
0x1800be216  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be21b  mov     [rbp+30h+var_18], 0
0x1800be223  lea     r9, [rbp+30h+var_18]; string
0x1800be227  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800be22b  mov     edx, 2Ch ; ','; length
0x1800be230  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800be237  call    cs:__imp_WindowsCreateStringReference
0x1800be23d  test    eax, eax
0x1800be23f  jns     short loc_1800BE254
0x1800be241  xor     r9d, r9d; lpArguments
0x1800be244  xor     r8d, r8d; nNumberOfArguments
0x1800be247  lea     edx, [r9+1]; dwExceptionFlags
0x1800be24b  mov     ecx, eax; dwExceptionCode
0x1800be24d  call    cs:__imp_RaiseException
0x1800be253  int     3; Trap to Debugger
0x1800be254  lea     r8, [rsp+130h+var_110]
0x1800be259  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800be260  mov     rcx, [rbp+30h+var_18]
0x1800be264  call    cs:__imp_RoGetActivationFactory
0x1800be26a  mov     ebx, eax
0x1800be26c  test    eax, eax
0x1800be26e  jns     short loc_1800BE294
0x1800be270  mov     rcx, [rsp+130h+var_110]
0x1800be275  test    rcx, rcx
0x1800be278  jz      short loc_1800BE290
0x1800be27a  mov     [rsp+130h+var_110], 0
0x1800be283  mov     rdx, [rcx]
0x1800be286  mov     rax, [rdx+10h]
0x1800be28a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be28f  nop
0x1800be290  mov     eax, ebx
0x1800be292  jmp     short loc_1800BE2FC
0x1800be294  mov     [rsp+130h+var_108], 0
0x1800be29d  mov     rbx, [rsp+130h+var_110]
0x1800be2a2  lea     rcx, [rsp+130h+var_108]
0x1800be2a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be2ac  lea     r8, [rsp+130h+var_108]
0x1800be2b1  lea     rdx, [rsp+130h+var_100]
0x1800be2b6  mov     rcx, rbx
0x1800be2b9  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800be2be  mov     ebx, eax
0x1800be2c0  lea     rcx, [rsp+130h+var_108]
0x1800be2c5  test    eax, eax
0x1800be2c7  jns     short loc_1800BE2DA
0x1800be2c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be2ce  lea     rcx, [rsp+130h+var_110]
0x1800be2d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be2d8  jmp     short loc_1800BE290
0x1800be2da  mov     rax, [rsp+130h+var_108]
0x1800be2df  mov     [rsp+130h+var_108], 0
0x1800be2e8  mov     [rdi], rax
0x1800be2eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be2f0  lea     rcx, [rsp+130h+var_110]
0x1800be2f5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800be2fa  xor     eax, eax
0x1800be2fc  mov     rcx, [rbp+30h+var_10]
0x1800be300  xor     rcx, rsp; StackCookie
0x1800be303  call    __security_check_cookie
0x1800be308  lea     r11, [rsp+130h+var_s0]
0x1800be310  mov     rbx, [r11+10h]
0x1800be314  mov     rdi, [r11+20h]
0x1800be318  mov     rsp, r11
0x1800be31b  pop     rbp
0x1800be31c  retn
```
