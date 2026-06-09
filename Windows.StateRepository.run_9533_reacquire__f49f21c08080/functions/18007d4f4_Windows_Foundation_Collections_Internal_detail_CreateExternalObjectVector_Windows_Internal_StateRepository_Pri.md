# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PrimaryTileUserDataChange,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PrimaryTileUserDataChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PrimaryTileUserDataChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PrimaryTileUserDataChange *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PrimaryTileUserDataChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PrimaryTileUserDataChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PrimaryTileUserDataChange *>,0> * *)

- ea: `0x18007d4f4`
- end: `0x18007d7b5`
- name: `??$CreateExternalObjectVector@VPrimaryTileUserDataChange@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPrimaryTileUserDataChange@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPrimaryTileUserDataChange@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPrimaryTileUserDataChange@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPrimaryTileUserDataChange@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPrimaryTileUserDataChange@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPrimaryTileUserDataChange@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `705`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007d398`
- `0x1800b98c0`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18007d4f4`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d775`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d788`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d79b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d7ae`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d775`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d788`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d79b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007d7ae`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007d66d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007d66d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d5b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d64f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d5b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007d64f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PrimaryTileUserDataChange,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PrimaryTileUserDataChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PrimaryTileUserDataChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PrimaryTileUserDataChange *>,0>>(
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
  __int64 v19; // rcx
  __int64 v20; // rcx
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x64u);
  v4 = v3 - 1;
  if ( v3 > 0x64 )
    v4 = 100;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PrimaryTileUserDataChange>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x68u);
  v7 = v6 - 1;
  if ( v6 > 0x68 )
    v7 = 104;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PrimaryTileUserDataChange>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x66u);
  v10 = v9 - 1;
  if ( v9 > 0x66 )
    v10 = 102;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PrimaryTileUserDataChange>",
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
  v24 = GUID_16462b61_3298_441c_af1b_1c0995748cf7;
  v25 = GUID_1e3c8a0e_59d0_5e21_9b32_b88244a586f3;
  v26 = GUID_6dd00567_b07e_59ee_ad82_d9d8ec4c2914;
  v27 = GUID_da069297_d440_588a_8550_8302e7e879b8;
  v28 = GUID_15b2bc91_0a52_5ba5_8f3a_9302adfa28a6;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18007D7B4LL);
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
  {
    v14 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v22 = 0;
  v16 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)ActivationFactory;
  }
  v17 = v22;
  v22 = 0;
  *a2 = v17;
  v18 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18007d4f4  mov     [rsp-8+arg_0], rbx
0x18007d4f9  mov     [rsp-8+arg_10], rdi
0x18007d4fe  push    rbp
0x18007d4ff  lea     rbp, [rsp-30h]
0x18007d504  sub     rsp, 130h
0x18007d50b  mov     rax, cs:__security_cookie
0x18007d512  xor     rax, rsp
0x18007d515  mov     [rbp+30h+var_10], rax
0x18007d519  mov     rdi, rdx
0x18007d51c  mov     [rbp+30h+string], 0
0x18007d524  mov     ebx, 64h ; 'd'
0x18007d529  mov     ecx, ebx; unsigned int
0x18007d52b  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007d530  lea     edx, [rax-1]
0x18007d533  cmp     eax, ebx
0x18007d535  cmova   edx, ebx; length
0x18007d538  lea     r9, [rbp+30h+string]; string
0x18007d53c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18007d540  lea     rcx, aWindowsFoundat_171; "Windows.Foundation.Collections.IVector`"...
0x18007d547  call    cs:__imp_WindowsCreateStringReference
0x18007d54d  test    eax, eax
0x18007d54f  js      loc_18007D769
0x18007d555  mov     [rbp+30h+var_58], 0
0x18007d55d  mov     ebx, 68h ; 'h'
0x18007d562  mov     ecx, ebx; unsigned int
0x18007d564  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007d569  lea     edx, [rax-1]
0x18007d56c  cmp     eax, ebx
0x18007d56e  cmova   edx, ebx; length
0x18007d571  lea     r9, [rbp+30h+var_58]; string
0x18007d575  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18007d579  lea     rcx, aWindowsFoundat_65; "Windows.Foundation.Collections.IVectorV"...
0x18007d580  call    cs:__imp_WindowsCreateStringReference
0x18007d586  test    eax, eax
0x18007d588  js      loc_18007D77C
0x18007d58e  mov     [rbp+30h+var_38], 0
0x18007d596  mov     ebx, 66h ; 'f'
0x18007d59b  mov     ecx, ebx; unsigned int
0x18007d59d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007d5a2  lea     edx, [rax-1]
0x18007d5a5  cmp     eax, ebx
0x18007d5a7  cmova   edx, ebx; length
0x18007d5aa  lea     r9, [rbp+30h+var_38]; string
0x18007d5ae  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18007d5b2  lea     rcx, aWindowsFoundat_124; "Windows.Foundation.Collections.IIterato"...
0x18007d5b9  call    cs:__imp_WindowsCreateStringReference
0x18007d5bf  test    eax, eax
0x18007d5c1  js      loc_18007D78F
0x18007d5c7  mov     rax, [rbp+30h+string]
0x18007d5cb  mov     [rsp+130h+var_100], rax
0x18007d5d0  mov     rax, [rbp+30h+var_58]
0x18007d5d4  mov     [rsp+130h+var_F8], rax
0x18007d5d9  mov     rax, [rbp+30h+var_38]
0x18007d5dd  mov     [rsp+130h+var_F0], rax
0x18007d5e2  movups  xmm0, xmmword ptr cs:_GUID_16462b61_3298_441c_af1b_1c0995748cf7.Data1
0x18007d5e9  movdqu  [rsp+130h+var_E8], xmm0
0x18007d5ef  movups  xmm1, xmmword ptr cs:_GUID_1e3c8a0e_59d0_5e21_9b32_b88244a586f3.Data1
0x18007d5f6  movdqu  [rsp+130h+var_D8], xmm1
0x18007d5fc  movups  xmm0, xmmword ptr cs:_GUID_6dd00567_b07e_59ee_ad82_d9d8ec4c2914.Data1
0x18007d603  movdqu  [rsp+130h+var_C8], xmm0
0x18007d609  movups  xmm1, xmmword ptr cs:_GUID_da069297_d440_588a_8550_8302e7e879b8.Data1
0x18007d610  movdqu  [rsp+130h+var_B8], xmm1
0x18007d616  movups  xmm0, xmmword ptr cs:_GUID_15b2bc91_0a52_5ba5_8f3a_9302adfa28a6.Data1
0x18007d61d  movdqu  [rbp+30h+var_A8], xmm0
0x18007d622  mov     [rsp+130h+var_110], 0
0x18007d62b  lea     rcx, [rsp+130h+var_110]
0x18007d630  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d635  mov     [rbp+30h+var_18], 0
0x18007d63d  lea     r9, [rbp+30h+var_18]; string
0x18007d641  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18007d645  lea     edx, [rbx-3Ah]; length
0x18007d648  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18007d64f  call    cs:__imp_WindowsCreateStringReference
0x18007d655  test    eax, eax
0x18007d657  js      loc_18007D7A2
0x18007d65d  lea     r8, [rsp+130h+var_110]
0x18007d662  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18007d669  mov     rcx, [rbp+30h+var_18]
0x18007d66d  call    cs:__imp_RoGetActivationFactory
0x18007d673  mov     ebx, eax
0x18007d675  test    eax, eax
0x18007d677  jns     short loc_18007D6BC
0x18007d679  mov     rcx, [rsp+130h+var_110]
0x18007d67e  test    rcx, rcx
0x18007d681  jz      short loc_18007D699
0x18007d683  mov     [rsp+130h+var_110], 0
0x18007d68c  mov     rdx, [rcx]
0x18007d68f  mov     rax, [rdx+10h]
0x18007d693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d698  nop
0x18007d699  mov     eax, ebx
0x18007d69b  mov     rcx, [rbp+30h+var_10]
0x18007d69f  xor     rcx, rsp; StackCookie
0x18007d6a2  call    __security_check_cookie
0x18007d6a7  lea     r11, [rsp+130h+var_s0]
0x18007d6af  mov     rbx, [r11+10h]
0x18007d6b3  mov     rdi, [r11+20h]
0x18007d6b7  mov     rsp, r11
0x18007d6ba  pop     rbp
0x18007d6bb  retn
0x18007d6bc  mov     [rsp+130h+var_108], 0
0x18007d6c5  mov     rbx, [rsp+130h+var_110]
0x18007d6ca  lea     rcx, [rsp+130h+var_108]
0x18007d6cf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d6d4  lea     r8, [rsp+130h+var_108]
0x18007d6d9  lea     rdx, [rsp+130h+var_100]
0x18007d6de  mov     rcx, rbx
0x18007d6e1  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18007d6e6  mov     ebx, eax
0x18007d6e8  test    eax, eax
0x18007d6ea  js      short loc_18007D724
0x18007d6ec  mov     rax, [rsp+130h+var_108]
0x18007d6f1  mov     [rsp+130h+var_108], 0
0x18007d6fa  mov     [rdi], rax
0x18007d6fd  mov     rcx, [rsp+130h+var_110]
0x18007d702  test    rcx, rcx
0x18007d705  jz      short loc_18007D71D
0x18007d707  mov     [rsp+130h+var_110], 0
0x18007d710  mov     rax, [rcx]
0x18007d713  mov     rax, [rax+10h]
0x18007d717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d71c  nop
0x18007d71d  xor     eax, eax
0x18007d71f  jmp     loc_18007D69B
0x18007d724  mov     rcx, [rsp+130h+var_108]
0x18007d729  test    rcx, rcx
0x18007d72c  jz      short loc_18007D744
0x18007d72e  mov     [rsp+130h+var_108], 0
0x18007d737  mov     rdx, [rcx]
0x18007d73a  mov     rax, [rdx+10h]
0x18007d73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d743  nop
0x18007d744  mov     rcx, [rsp+130h+var_110]
0x18007d749  test    rcx, rcx
0x18007d74c  jz      short loc_18007D764
0x18007d74e  mov     [rsp+130h+var_110], 0
0x18007d757  mov     rax, [rcx]
0x18007d75a  mov     rax, [rax+10h]
0x18007d75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d763  nop
0x18007d764  jmp     loc_18007D699
0x18007d769  xor     r9d, r9d; lpArguments
0x18007d76c  xor     r8d, r8d; nNumberOfArguments
0x18007d76f  lea     edx, [r9+1]; dwExceptionFlags
0x18007d773  mov     ecx, eax; dwExceptionCode
0x18007d775  call    cs:__imp_RaiseException
0x18007d77b  int     3; Trap to Debugger
0x18007d77c  xor     r9d, r9d; lpArguments
0x18007d77f  xor     r8d, r8d; nNumberOfArguments
0x18007d782  lea     edx, [r9+1]; dwExceptionFlags
0x18007d786  mov     ecx, eax; dwExceptionCode
0x18007d788  call    cs:__imp_RaiseException
0x18007d78e  int     3; Trap to Debugger
0x18007d78f  xor     r9d, r9d; lpArguments
0x18007d792  xor     r8d, r8d; nNumberOfArguments
0x18007d795  lea     edx, [r9+1]; dwExceptionFlags
0x18007d799  mov     ecx, eax; dwExceptionCode
0x18007d79b  call    cs:__imp_RaiseException
0x18007d7a1  int     3; Trap to Debugger
0x18007d7a2  xor     r9d, r9d; lpArguments
0x18007d7a5  xor     r8d, r8d; nNumberOfArguments
0x18007d7a8  lea     edx, [r9+1]; dwExceptionFlags
0x18007d7ac  mov     ecx, eax; dwExceptionCode
0x18007d7ae  call    cs:__imp_RaiseException
```
