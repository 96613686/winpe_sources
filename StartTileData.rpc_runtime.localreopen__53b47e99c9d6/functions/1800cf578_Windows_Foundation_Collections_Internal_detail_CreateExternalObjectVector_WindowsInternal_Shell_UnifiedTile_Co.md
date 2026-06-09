# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::CollectionTile,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::CollectionTile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::CollectionTile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::CollectionTile *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::CollectionTile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::CollectionTile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::CollectionTile *>,0> * *)

- ea: `0x1800cf578`
- end: `0x1800cf7f6`
- name: `??$CreateExternalObjectVector@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@V?$AgileVector@PEAVCollectionTile@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVCollectionTile@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVCollectionTile@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVCollectionTile@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVCollectionTile@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVCollectionTile@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@1234@@Z`
- size: `638`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800ce8c8`
- `0x1800cea40`
- `0x1800cec60`
- `0x1800cedec`
- `0x180177388`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x1800cf578`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf5e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf627`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf66e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf715`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf5e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf627`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf66e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cf715`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf5cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf612`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf6ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf5cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf612`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf659`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cf6ff`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cf72c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cf72c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::CollectionTile,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::CollectionTile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::CollectionTile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::CollectionTile *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v4 = v3 - 1;
  if ( v3 > 0x5A )
    v4 = 90;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<WindowsInternal.Shell.UnifiedTile.CollectionTile>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Eu);
  v7 = v6 - 1;
  if ( v6 > 0x5E )
    v7 = 94;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<WindowsInternal.Shell.UnifiedTile.CollectionTile>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Cu);
  v10 = v9 - 1;
  if ( v9 > 0x5C )
    v10 = 92;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<WindowsInternal.Shell.UnifiedTile.CollectionTile>",
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
  v22 = GUID_e21a4ddc_1944_40dc_9b8f_6d35d4b7eeb9;
  v23 = GUID_52fadd1d_556d_5542_b6f6_80803040d0f3;
  v24 = GUID_20686dbe_18a2_57e9_b98a_941ef7adebcc;
  v25 = GUID_db9bf009_39f6_537f_8391_f0c6be1dc2d9;
  v26 = GUID_a0a7d866_903c_547d_899e_eaeb106717c6;
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
    v14 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = 0;
  v16 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v21, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    return (unsigned int)ActivationFactory;
  }
  v17 = v20;
  v20 = 0;
  *a2 = v17;
  v18 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x1800cf578  mov     [rsp-8+arg_0], rbx
0x1800cf57d  mov     [rsp-8+arg_10], rdi
0x1800cf582  push    rbp
0x1800cf583  lea     rbp, [rsp-30h]
0x1800cf588  sub     rsp, 130h
0x1800cf58f  mov     rax, cs:__security_cookie
0x1800cf596  xor     rax, rsp
0x1800cf599  mov     [rbp+30h+var_10], rax
0x1800cf59d  mov     rdi, rdx
0x1800cf5a0  mov     [rbp+30h+string], 0
0x1800cf5a8  mov     ebx, 5Ah ; 'Z'
0x1800cf5ad  mov     ecx, ebx; unsigned int
0x1800cf5af  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800cf5b4  lea     edx, [rax-1]
0x1800cf5b7  cmp     eax, ebx
0x1800cf5b9  cmova   edx, ebx; length
0x1800cf5bc  lea     r9, [rbp+30h+string]; string
0x1800cf5c0  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800cf5c4  lea     rcx, aWindowsFoundat_25; "Windows.Foundation.Collections.IVector`"...
0x1800cf5cb  call    cs:__imp_WindowsCreateStringReference
0x1800cf5d1  test    eax, eax
0x1800cf5d3  jns     short loc_1800CF5E7
0x1800cf5d5  xor     r9d, r9d; lpArguments
0x1800cf5d8  xor     r8d, r8d; nNumberOfArguments
0x1800cf5db  lea     edx, [rbx-59h]; dwExceptionFlags
0x1800cf5de  mov     ecx, eax; dwExceptionCode
0x1800cf5e0  call    cs:__imp_RaiseException
0x1800cf5e6  int     3; Trap to Debugger
0x1800cf5e7  mov     [rbp+30h+var_58], 0
0x1800cf5ef  mov     ebx, 5Eh ; '^'
0x1800cf5f4  mov     ecx, ebx; unsigned int
0x1800cf5f6  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800cf5fb  lea     edx, [rax-1]
0x1800cf5fe  cmp     eax, ebx
0x1800cf600  cmova   edx, ebx; length
0x1800cf603  lea     r9, [rbp+30h+var_58]; string
0x1800cf607  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800cf60b  lea     rcx, aWindowsFoundat_14; "Windows.Foundation.Collections.IVectorV"...
0x1800cf612  call    cs:__imp_WindowsCreateStringReference
0x1800cf618  test    eax, eax
0x1800cf61a  jns     short loc_1800CF62E
0x1800cf61c  xor     r9d, r9d; lpArguments
0x1800cf61f  xor     r8d, r8d; nNumberOfArguments
0x1800cf622  lea     edx, [rbx-5Dh]; dwExceptionFlags
0x1800cf625  mov     ecx, eax; dwExceptionCode
0x1800cf627  call    cs:__imp_RaiseException
0x1800cf62d  int     3; Trap to Debugger
0x1800cf62e  mov     [rbp+30h+var_38], 0
0x1800cf636  mov     ebx, 5Ch ; '\'
0x1800cf63b  mov     ecx, ebx; unsigned int
0x1800cf63d  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800cf642  lea     edx, [rax-1]
0x1800cf645  cmp     eax, ebx
0x1800cf647  cmova   edx, ebx; length
0x1800cf64a  lea     r9, [rbp+30h+var_38]; string
0x1800cf64e  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800cf652  lea     rcx, aWindowsFoundat_22; "Windows.Foundation.Collections.IIterato"...
0x1800cf659  call    cs:__imp_WindowsCreateStringReference
0x1800cf65f  test    eax, eax
0x1800cf661  jns     short loc_1800CF675
0x1800cf663  xor     r9d, r9d; lpArguments
0x1800cf666  xor     r8d, r8d; nNumberOfArguments
0x1800cf669  lea     edx, [rbx-5Bh]; dwExceptionFlags
0x1800cf66c  mov     ecx, eax; dwExceptionCode
0x1800cf66e  call    cs:__imp_RaiseException
0x1800cf674  int     3; Trap to Debugger
0x1800cf675  mov     rax, [rbp+30h+string]
0x1800cf679  mov     [rsp+130h+var_100], rax
0x1800cf67e  mov     rax, [rbp+30h+var_58]
0x1800cf682  mov     [rsp+130h+var_F8], rax
0x1800cf687  mov     rax, [rbp+30h+var_38]
0x1800cf68b  mov     [rsp+130h+var_F0], rax
0x1800cf690  movups  xmm0, xmmword ptr cs:_GUID_e21a4ddc_1944_40dc_9b8f_6d35d4b7eeb9.Data1
0x1800cf697  movdqu  [rsp+130h+var_E8], xmm0
0x1800cf69d  movups  xmm1, xmmword ptr cs:_GUID_52fadd1d_556d_5542_b6f6_80803040d0f3.Data1
0x1800cf6a4  movdqu  [rsp+130h+var_D8], xmm1
0x1800cf6aa  movups  xmm0, xmmword ptr cs:_GUID_20686dbe_18a2_57e9_b98a_941ef7adebcc.Data1
0x1800cf6b1  movdqu  [rsp+130h+var_C8], xmm0
0x1800cf6b7  movups  xmm1, xmmword ptr cs:_GUID_db9bf009_39f6_537f_8391_f0c6be1dc2d9.Data1
0x1800cf6be  movdqu  [rsp+130h+var_B8], xmm1
0x1800cf6c4  movups  xmm0, xmmword ptr cs:_GUID_a0a7d866_903c_547d_899e_eaeb106717c6.Data1
0x1800cf6cb  movdqu  [rbp+30h+var_A8], xmm0
0x1800cf6d0  mov     [rsp+130h+var_110], 0
0x1800cf6d9  lea     rcx, [rsp+130h+var_110]
0x1800cf6de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf6e3  mov     [rbp+30h+var_18], 0
0x1800cf6eb  lea     r9, [rbp+30h+var_18]; string
0x1800cf6ef  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800cf6f3  mov     edx, 2Ch ; ','; length
0x1800cf6f8  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800cf6ff  call    cs:__imp_WindowsCreateStringReference
0x1800cf705  test    eax, eax
0x1800cf707  jns     short loc_1800CF71C
0x1800cf709  xor     r9d, r9d; lpArguments
0x1800cf70c  xor     r8d, r8d; nNumberOfArguments
0x1800cf70f  lea     edx, [r9+1]; dwExceptionFlags
0x1800cf713  mov     ecx, eax; dwExceptionCode
0x1800cf715  call    cs:__imp_RaiseException
0x1800cf71b  int     3; Trap to Debugger
0x1800cf71c  lea     r8, [rsp+130h+var_110]
0x1800cf721  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800cf728  mov     rcx, [rbp+30h+var_18]
0x1800cf72c  call    cs:__imp_RoGetActivationFactory
0x1800cf732  mov     ebx, eax
0x1800cf734  test    eax, eax
0x1800cf736  jns     short loc_1800CF75C
0x1800cf738  mov     rcx, [rsp+130h+var_110]
0x1800cf73d  test    rcx, rcx
0x1800cf740  jz      short loc_1800CF758
0x1800cf742  mov     [rsp+130h+var_110], 0
0x1800cf74b  mov     rdx, [rcx]
0x1800cf74e  mov     rax, [rdx+10h]
0x1800cf752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf757  nop
0x1800cf758  mov     eax, ebx
0x1800cf75a  jmp     short loc_1800CF7D5
0x1800cf75c  mov     [rsp+130h+var_108], 0
0x1800cf765  mov     rbx, [rsp+130h+var_110]
0x1800cf76a  lea     rcx, [rsp+130h+var_108]
0x1800cf76f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf774  lea     r8, [rsp+130h+var_108]
0x1800cf779  lea     rdx, [rsp+130h+var_100]
0x1800cf77e  mov     rcx, rbx
0x1800cf781  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800cf786  mov     ebx, eax
0x1800cf788  test    eax, eax
0x1800cf78a  jns     short loc_1800CF7A2
0x1800cf78c  lea     rcx, [rsp+130h+var_108]
0x1800cf791  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf796  lea     rcx, [rsp+130h+var_110]
0x1800cf79b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800cf7a0  jmp     short loc_1800CF758
0x1800cf7a2  mov     rax, [rsp+130h+var_108]
0x1800cf7a7  mov     [rsp+130h+var_108], 0
0x1800cf7b0  mov     [rdi], rax
0x1800cf7b3  mov     rcx, [rsp+130h+var_110]
0x1800cf7b8  test    rcx, rcx
0x1800cf7bb  jz      short loc_1800CF7D3
0x1800cf7bd  mov     [rsp+130h+var_110], 0
0x1800cf7c6  mov     rax, [rcx]
0x1800cf7c9  mov     rax, [rax+10h]
0x1800cf7cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cf7d2  nop
0x1800cf7d3  xor     eax, eax
0x1800cf7d5  mov     rcx, [rbp+30h+var_10]
0x1800cf7d9  xor     rcx, rsp; StackCookie
0x1800cf7dc  call    __security_check_cookie
0x1800cf7e1  lea     r11, [rsp+130h+var_s0]
0x1800cf7e9  mov     rbx, [r11+10h]
0x1800cf7ed  mov     rdi, [r11+20h]
0x1800cf7f1  mov     rsp, r11
0x1800cf7f4  pop     rbp
0x1800cf7f5  retn
```
