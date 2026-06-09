# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>,0> * *)

- ea: `0x1801af0bc`
- end: `0x1801af329`
- name: `??$CreateExternalObjectVector@VUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@V?$AgileVector@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@@789Windows@@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVUnifiedTileVerbProvider@Private@UnifiedTile@Shell@WindowsInternal@@@789Windows@@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180035b00`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x1801af0bc`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af124`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af16b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af1b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af259`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af124`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af16b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af1b2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1801af259`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af10f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af19d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af243`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af10f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af19d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1801af243`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801af270`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801af270`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::Private::UnifiedTileVerbProvider *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Bu);
  v4 = v3 - 1;
  if ( v3 > 0x6B )
    v4 = 107;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<WindowsInternal.Shell.UnifiedTile.Private.UnifiedTileVerbProvider>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Fu);
  v7 = v6 - 1;
  if ( v6 > 0x6F )
    v7 = 111;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<WindowsInternal.Shell.UnifiedTile.Private.UnifiedTileVerbProvider>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Du);
  v10 = v9 - 1;
  if ( v9 > 0x6D )
    v10 = 109;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<WindowsInternal.Shell.UnifiedTile.Private.UnifiedTileVerbProvider>",
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
  v21 = GUID_28fc5cfc_9a90_44d7_9acd_9f019013ec54;
  v22 = GUID_0f917c50_c0c6_5de0_93d7_cf7d4e9c6278;
  v23 = GUID_7d0ec789_3e50_54f0_8fa6_06b8b9525b48;
  v24 = GUID_da70d26a_1a42_522c_b804_e7658b31fe95;
  v25 = GUID_8729d758_599e_557a_81f3_3acbf0e241a6;
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
0x1801af0bc  mov     [rsp-8+arg_0], rbx
0x1801af0c1  mov     [rsp-8+arg_10], rdi
0x1801af0c6  push    rbp
0x1801af0c7  lea     rbp, [rsp-30h]
0x1801af0cc  sub     rsp, 130h
0x1801af0d3  mov     rax, cs:__security_cookie
0x1801af0da  xor     rax, rsp
0x1801af0dd  mov     [rbp+30h+var_10], rax
0x1801af0e1  mov     rdi, rdx
0x1801af0e4  mov     [rbp+30h+string], 0
0x1801af0ec  mov     ebx, 6Bh ; 'k'
0x1801af0f1  mov     ecx, ebx; unsigned int
0x1801af0f3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801af0f8  lea     edx, [rax-1]
0x1801af0fb  cmp     eax, ebx
0x1801af0fd  cmova   edx, ebx; length
0x1801af100  lea     r9, [rbp+30h+string]; string
0x1801af104  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1801af108  lea     rcx, aWindowsFoundat_24; "Windows.Foundation.Collections.IVector`"...
0x1801af10f  call    cs:__imp_WindowsCreateStringReference
0x1801af115  test    eax, eax
0x1801af117  jns     short loc_1801AF12B
0x1801af119  xor     r9d, r9d; lpArguments
0x1801af11c  xor     r8d, r8d; nNumberOfArguments
0x1801af11f  lea     edx, [rbx-6Ah]; dwExceptionFlags
0x1801af122  mov     ecx, eax; dwExceptionCode
0x1801af124  call    cs:__imp_RaiseException
0x1801af12a  int     3; Trap to Debugger
0x1801af12b  mov     [rbp+30h+var_58], 0
0x1801af133  mov     ebx, 6Fh ; 'o'
0x1801af138  mov     ecx, ebx; unsigned int
0x1801af13a  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801af13f  lea     edx, [rax-1]
0x1801af142  cmp     eax, ebx
0x1801af144  cmova   edx, ebx; length
0x1801af147  lea     r9, [rbp+30h+var_58]; string
0x1801af14b  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1801af14f  lea     rcx, aWindowsFoundat_36; "Windows.Foundation.Collections.IVectorV"...
0x1801af156  call    cs:__imp_WindowsCreateStringReference
0x1801af15c  test    eax, eax
0x1801af15e  jns     short loc_1801AF172
0x1801af160  xor     r9d, r9d; lpArguments
0x1801af163  xor     r8d, r8d; nNumberOfArguments
0x1801af166  lea     edx, [rbx-6Eh]; dwExceptionFlags
0x1801af169  mov     ecx, eax; dwExceptionCode
0x1801af16b  call    cs:__imp_RaiseException
0x1801af171  int     3; Trap to Debugger
0x1801af172  mov     [rbp+30h+var_38], 0
0x1801af17a  mov     ebx, 6Dh ; 'm'
0x1801af17f  mov     ecx, ebx; unsigned int
0x1801af181  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1801af186  lea     edx, [rax-1]
0x1801af189  cmp     eax, ebx
0x1801af18b  cmova   edx, ebx; length
0x1801af18e  lea     r9, [rbp+30h+var_38]; string
0x1801af192  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1801af196  lea     rcx, aWindowsFoundat_71; "Windows.Foundation.Collections.IIterato"...
0x1801af19d  call    cs:__imp_WindowsCreateStringReference
0x1801af1a3  test    eax, eax
0x1801af1a5  jns     short loc_1801AF1B9
0x1801af1a7  xor     r9d, r9d; lpArguments
0x1801af1aa  xor     r8d, r8d; nNumberOfArguments
0x1801af1ad  lea     edx, [rbx-6Ch]; dwExceptionFlags
0x1801af1b0  mov     ecx, eax; dwExceptionCode
0x1801af1b2  call    cs:__imp_RaiseException
0x1801af1b8  int     3; Trap to Debugger
0x1801af1b9  mov     rax, [rbp+30h+string]
0x1801af1bd  mov     [rsp+130h+var_100], rax
0x1801af1c2  mov     rax, [rbp+30h+var_58]
0x1801af1c6  mov     [rsp+130h+var_F8], rax
0x1801af1cb  mov     rax, [rbp+30h+var_38]
0x1801af1cf  mov     [rsp+130h+var_F0], rax
0x1801af1d4  movups  xmm0, xmmword ptr cs:_GUID_28fc5cfc_9a90_44d7_9acd_9f019013ec54.Data1
0x1801af1db  movdqu  [rsp+130h+var_E8], xmm0
0x1801af1e1  movups  xmm1, xmmword ptr cs:_GUID_0f917c50_c0c6_5de0_93d7_cf7d4e9c6278.Data1
0x1801af1e8  movdqu  [rsp+130h+var_D8], xmm1
0x1801af1ee  movups  xmm0, xmmword ptr cs:_GUID_7d0ec789_3e50_54f0_8fa6_06b8b9525b48.Data1
0x1801af1f5  movdqu  [rsp+130h+var_C8], xmm0
0x1801af1fb  movups  xmm1, xmmword ptr cs:_GUID_da70d26a_1a42_522c_b804_e7658b31fe95.Data1
0x1801af202  movdqu  [rsp+130h+var_B8], xmm1
0x1801af208  movups  xmm0, xmmword ptr cs:_GUID_8729d758_599e_557a_81f3_3acbf0e241a6.Data1
0x1801af20f  movdqu  [rbp+30h+var_A8], xmm0
0x1801af214  mov     [rsp+130h+var_110], 0
0x1801af21d  lea     rcx, [rsp+130h+var_110]
0x1801af222  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801af227  mov     [rbp+30h+var_18], 0
0x1801af22f  lea     r9, [rbp+30h+var_18]; string
0x1801af233  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1801af237  mov     edx, 2Ch ; ','; length
0x1801af23c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1801af243  call    cs:__imp_WindowsCreateStringReference
0x1801af249  test    eax, eax
0x1801af24b  jns     short loc_1801AF260
0x1801af24d  xor     r9d, r9d; lpArguments
0x1801af250  xor     r8d, r8d; nNumberOfArguments
0x1801af253  lea     edx, [r9+1]; dwExceptionFlags
0x1801af257  mov     ecx, eax; dwExceptionCode
0x1801af259  call    cs:__imp_RaiseException
0x1801af25f  int     3; Trap to Debugger
0x1801af260  lea     r8, [rsp+130h+var_110]
0x1801af265  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1801af26c  mov     rcx, [rbp+30h+var_18]
0x1801af270  call    cs:__imp_RoGetActivationFactory
0x1801af276  mov     ebx, eax
0x1801af278  test    eax, eax
0x1801af27a  jns     short loc_1801AF2A0
0x1801af27c  mov     rcx, [rsp+130h+var_110]
0x1801af281  test    rcx, rcx
0x1801af284  jz      short loc_1801AF29C
0x1801af286  mov     [rsp+130h+var_110], 0
0x1801af28f  mov     rdx, [rcx]
0x1801af292  mov     rax, [rdx+10h]
0x1801af296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801af29b  nop
0x1801af29c  mov     eax, ebx
0x1801af29e  jmp     short loc_1801AF308
0x1801af2a0  mov     [rsp+130h+var_108], 0
0x1801af2a9  mov     rbx, [rsp+130h+var_110]
0x1801af2ae  lea     rcx, [rsp+130h+var_108]
0x1801af2b3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801af2b8  lea     r8, [rsp+130h+var_108]
0x1801af2bd  lea     rdx, [rsp+130h+var_100]
0x1801af2c2  mov     rcx, rbx
0x1801af2c5  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1801af2ca  mov     ebx, eax
0x1801af2cc  lea     rcx, [rsp+130h+var_108]
0x1801af2d1  test    eax, eax
0x1801af2d3  jns     short loc_1801AF2E6
0x1801af2d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801af2da  lea     rcx, [rsp+130h+var_110]
0x1801af2df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801af2e4  jmp     short loc_1801AF29C
0x1801af2e6  mov     rax, [rsp+130h+var_108]
0x1801af2eb  mov     [rsp+130h+var_108], 0
0x1801af2f4  mov     [rdi], rax
0x1801af2f7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801af2fc  lea     rcx, [rsp+130h+var_110]
0x1801af301  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801af306  xor     eax, eax
0x1801af308  mov     rcx, [rbp+30h+var_10]
0x1801af30c  xor     rcx, rsp; StackCookie
0x1801af30f  call    __security_check_cookie
0x1801af314  lea     r11, [rsp+130h+var_s0]
0x1801af31c  mov     rbx, [r11+10h]
0x1801af320  mov     rdi, [r11+20h]
0x1801af324  mov     rsp, r11
0x1801af327  pop     rbp
0x1801af328  retn
```
