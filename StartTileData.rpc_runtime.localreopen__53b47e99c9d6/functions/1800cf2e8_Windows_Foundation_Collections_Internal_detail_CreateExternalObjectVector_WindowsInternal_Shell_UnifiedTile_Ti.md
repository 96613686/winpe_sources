# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *>,0> * *)

- ea: `0x1800cf2e8`
- end: `0x1800cf570`
- name: `??$CreateExternalObjectVector@VTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@V?$AgileVector@PEAVTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@1234@@Z`
- size: `648`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800ce560`
- `0x1800ce6b0`
- `0x1800cedec`
- `0x180177388`
- `0x1801add7c`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x1800cf2e8`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4f9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4d3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4e6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf4f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf33b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf443`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf33b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf3ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf443`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cf461`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cf461`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileCollectionContainer *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x63u);
  v4 = v3 - 1;
  if ( v3 > 0x63 )
    v4 = 99;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<WindowsInternal.Shell.UnifiedTile.TileCollectionContainer>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x67u);
  v7 = v6 - 1;
  if ( v6 > 0x67 )
    v7 = 103;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<WindowsInternal.Shell.UnifiedTile.TileCollectionContainer>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x65u);
  v10 = v9 - 1;
  if ( v9 > 0x65 )
    v10 = 101;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<WindowsInternal.Shell.UnifiedTile.TileCollectionContainer>",
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
  v21 = GUID_6fe03efc_a8af_4faf_9c23_bc0cb5bf29d3;
  v22 = GUID_172af1d9_dd8f_5d5c_8bb8_2c48b59a3c8b;
  v23 = GUID_b450e264_cd01_5105_81d1_c9c5d64ac1aa;
  v24 = GUID_9959a6a3_91aa_57ab_b442_ebfe77b3e7a9;
  v25 = GUID_7e0724e4_d8d6_5dc2_b0d5_8e737c8c2886;
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
0x1800cf2e8  mov     [rsp-8+arg_0], rbx
0x1800cf2ed  mov     [rsp-8+arg_10], rdi
0x1800cf2f2  push    rbp
0x1800cf2f3  lea     rbp, [rsp-30h]
0x1800cf2f8  sub     rsp, 130h
0x1800cf2ff  mov     rax, cs:__security_cookie
0x1800cf306  xor     rax, rsp
0x1800cf309  mov     [rbp+30h+var_10], rax
0x1800cf30d  mov     rdi, rdx
0x1800cf310  mov     [rbp+30h+string], 0
0x1800cf318  mov     ebx, 63h ; 'c'
0x1800cf31d  mov     ecx, ebx; unsigned int
0x1800cf31f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800cf324  lea     edx, [rax-1]
0x1800cf327  cmp     eax, ebx
0x1800cf329  cmova   edx, ebx; length
0x1800cf32c  lea     r9, [rbp+30h+string]; string
0x1800cf330  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800cf334  lea     rcx, aWindowsFoundat_42; "Windows.Foundation.Collections.IVector`"...
0x1800cf33b  call    cs:__imp_WindowsCreateStringReference
0x1800cf341  test    eax, eax
0x1800cf343  js      loc_1800CF4B4
0x1800cf349  mov     [rbp+30h+var_58], 0
0x1800cf351  mov     ebx, 67h ; 'g'
0x1800cf356  mov     ecx, ebx; unsigned int
0x1800cf358  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800cf35d  lea     edx, [rax-1]
0x1800cf360  cmp     eax, ebx
0x1800cf362  cmova   edx, ebx; length
0x1800cf365  lea     r9, [rbp+30h+var_58]; string
0x1800cf369  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800cf36d  lea     rcx, aWindowsFoundat_16; "Windows.Foundation.Collections.IVectorV"...
0x1800cf374  call    cs:__imp_WindowsCreateStringReference
0x1800cf37a  test    eax, eax
0x1800cf37c  js      loc_1800CF4C7
0x1800cf382  mov     [rbp+30h+var_38], 0
0x1800cf38a  mov     ebx, 65h ; 'e'
0x1800cf38f  mov     ecx, ebx; unsigned int
0x1800cf391  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800cf396  lea     edx, [rax-1]
0x1800cf399  cmp     eax, ebx
0x1800cf39b  cmova   edx, ebx; length
0x1800cf39e  lea     r9, [rbp+30h+var_38]; string
0x1800cf3a2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800cf3a6  lea     rcx, aWindowsFoundat_43; "Windows.Foundation.Collections.IIterato"...
0x1800cf3ad  call    cs:__imp_WindowsCreateStringReference
0x1800cf3b3  test    eax, eax
0x1800cf3b5  js      loc_1800CF4DA
0x1800cf3bb  mov     rax, [rbp+30h+string]
0x1800cf3bf  mov     [rsp+130h+var_100], rax
0x1800cf3c4  mov     rax, [rbp+30h+var_58]
0x1800cf3c8  mov     [rsp+130h+var_F8], rax
0x1800cf3cd  mov     rax, [rbp+30h+var_38]
0x1800cf3d1  mov     [rsp+130h+var_F0], rax
0x1800cf3d6  movups  xmm0, xmmword ptr cs:_GUID_6fe03efc_a8af_4faf_9c23_bc0cb5bf29d3.Data1
0x1800cf3dd  movdqu  [rsp+130h+var_E8], xmm0
0x1800cf3e3  movups  xmm1, xmmword ptr cs:_GUID_172af1d9_dd8f_5d5c_8bb8_2c48b59a3c8b.Data1
0x1800cf3ea  movdqu  [rsp+130h+var_D8], xmm1
0x1800cf3f0  movups  xmm0, xmmword ptr cs:_GUID_b450e264_cd01_5105_81d1_c9c5d64ac1aa.Data1
0x1800cf3f7  movdqu  [rsp+130h+var_C8], xmm0
0x1800cf3fd  movups  xmm1, xmmword ptr cs:_GUID_9959a6a3_91aa_57ab_b442_ebfe77b3e7a9.Data1
0x1800cf404  movdqu  [rsp+130h+var_B8], xmm1
0x1800cf40a  movups  xmm0, xmmword ptr cs:_GUID_7e0724e4_d8d6_5dc2_b0d5_8e737c8c2886.Data1
0x1800cf411  movdqu  [rbp+30h+var_A8], xmm0
0x1800cf416  mov     [rsp+130h+var_110], 0
0x1800cf41f  lea     rcx, [rsp+130h+var_110]
0x1800cf424  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf429  mov     [rbp+30h+var_18], 0
0x1800cf431  lea     r9, [rbp+30h+var_18]; string
0x1800cf435  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800cf439  lea     edx, [rbx-39h]; length
0x1800cf43c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800cf443  call    cs:__imp_WindowsCreateStringReference
0x1800cf449  test    eax, eax
0x1800cf44b  js      loc_1800CF4ED
0x1800cf451  lea     r8, [rsp+130h+var_110]
0x1800cf456  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800cf45d  mov     rcx, [rbp+30h+var_18]
0x1800cf461  call    cs:__imp_RoGetActivationFactory
0x1800cf467  mov     ebx, eax
0x1800cf469  test    eax, eax
0x1800cf46b  jns     loc_1800CF500
0x1800cf471  mov     rcx, [rsp+130h+var_110]
0x1800cf476  test    rcx, rcx
0x1800cf479  jz      short loc_1800CF491
0x1800cf47b  mov     [rsp+130h+var_110], 0
0x1800cf484  mov     rdx, [rcx]
0x1800cf487  mov     rax, [rdx+10h]
0x1800cf48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf490  nop
0x1800cf491  mov     eax, ebx
0x1800cf493  mov     rcx, [rbp+30h+var_10]
0x1800cf497  xor     rcx, rsp; StackCookie
0x1800cf49a  call    __security_check_cookie
0x1800cf49f  lea     r11, [rsp+130h+var_s0]
0x1800cf4a7  mov     rbx, [r11+10h]
0x1800cf4ab  mov     rdi, [r11+20h]
0x1800cf4af  mov     rsp, r11
0x1800cf4b2  pop     rbp
0x1800cf4b3  retn
0x1800cf4b4  xor     r9d, r9d; lpArguments
0x1800cf4b7  xor     r8d, r8d; nNumberOfArguments
0x1800cf4ba  lea     edx, [r9+1]; dwExceptionFlags
0x1800cf4be  mov     ecx, eax; dwExceptionCode
0x1800cf4c0  call    cs:__imp_RaiseException
0x1800cf4c6  int     3; Trap to Debugger
0x1800cf4c7  xor     r9d, r9d; lpArguments
0x1800cf4ca  xor     r8d, r8d; nNumberOfArguments
0x1800cf4cd  lea     edx, [r9+1]; dwExceptionFlags
0x1800cf4d1  mov     ecx, eax; dwExceptionCode
0x1800cf4d3  call    cs:__imp_RaiseException
0x1800cf4d9  int     3; Trap to Debugger
0x1800cf4da  xor     r9d, r9d; lpArguments
0x1800cf4dd  xor     r8d, r8d; nNumberOfArguments
0x1800cf4e0  lea     edx, [r9+1]; dwExceptionFlags
0x1800cf4e4  mov     ecx, eax; dwExceptionCode
0x1800cf4e6  call    cs:__imp_RaiseException
0x1800cf4ec  int     3; Trap to Debugger
0x1800cf4ed  xor     r9d, r9d; lpArguments
0x1800cf4f0  xor     r8d, r8d; nNumberOfArguments
0x1800cf4f3  lea     edx, [r9+1]; dwExceptionFlags
0x1800cf4f7  mov     ecx, eax; dwExceptionCode
0x1800cf4f9  call    cs:__imp_RaiseException
0x1800cf4ff  int     3; Trap to Debugger
0x1800cf500  mov     [rsp+130h+var_108], 0
0x1800cf509  mov     rbx, [rsp+130h+var_110]
0x1800cf50e  lea     rcx, [rsp+130h+var_108]
0x1800cf513  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf518  lea     r8, [rsp+130h+var_108]
0x1800cf51d  lea     rdx, [rsp+130h+var_100]
0x1800cf522  mov     rcx, rbx
0x1800cf525  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800cf52a  mov     ebx, eax
0x1800cf52c  lea     rcx, [rsp+130h+var_108]
0x1800cf531  test    eax, eax
0x1800cf533  jns     short loc_1800CF549
0x1800cf535  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf53a  lea     rcx, [rsp+130h+var_110]
0x1800cf53f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf544  jmp     loc_1800CF491
0x1800cf549  mov     rax, [rsp+130h+var_108]
0x1800cf54e  mov     [rsp+130h+var_108], 0
0x1800cf557  mov     [rdi], rax
0x1800cf55a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf55f  lea     rcx, [rsp+130h+var_110]
0x1800cf564  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf569  xor     eax, eax
0x1800cf56b  jmp     loc_1800CF493
```
