# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,0> * *)

- ea: `0x18007fd70`
- end: `0x180080011`
- name: `??$CreateExternalObjectVector@VCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@V?$AgileVector@PEAVCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@@6789@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVCDSLocalVolatileTileProperties@CDSProperties@Shell@WindowsInternal@@@6789@$0A@@1234@@Z`
- size: `673`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18007f9a0`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x18007fd70`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fdd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fe1f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fe66`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ff0d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fdd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fe1f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007fe66`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007ff0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fdc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fe0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fe51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fef7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fdc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fe0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fe51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18007fef7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007ff24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007ff24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::CDSProperties::CDSLocalVolatileTileProperties *>,0>>(
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
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Cu);
  v4 = v3 - 1;
  if ( v3 > 0x6C )
    v4 = 108;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<WindowsInternal.Shell.CDSProperties.CDSLocalVolatileTileProperties>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x70u);
  v7 = v6 - 1;
  if ( v6 > 0x70 )
    v7 = 112;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<WindowsInternal.Shell.CDSProperties.CDSLocalVolatileTileProperties>",
         v7,
         &v30,
         &v31);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v33 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Eu);
  v10 = v9 - 1;
  if ( v9 > 0x6E )
    v10 = 110;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<WindowsInternal.Shell.CDSProperties.CDSLocalVolatileTileProperties>",
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
  v23 = GUID_0b95d7ec_539e_4ad0_bab3_fc5acd05f716;
  v24 = GUID_25c38f78_9b8a_56c1_b051_4f0f8e8090fa;
  v25 = GUID_235d4a7a_1623_56c2_b025_0178912a1a38;
  v26 = GUID_c3913d00_5378_5397_bd8a_34cefc570171;
  v27 = GUID_aee1aa8e_9e99_5c50_8661_23ca957a8300;
  v20 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v35 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v34, &v35);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v35, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v20);
  if ( ActivationFactory < 0 )
  {
    v14 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v21 = 0;
  v16 = v20;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v22, &v21);
  if ( ActivationFactory < 0 )
  {
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = v21;
  v21 = 0;
  *a2 = v19;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return 0;
}

```

## disassembly

```asm
0x18007fd70  mov     [rsp-8+arg_0], rbx
0x18007fd75  mov     [rsp-8+arg_10], rdi
0x18007fd7a  push    rbp
0x18007fd7b  lea     rbp, [rsp-30h]
0x18007fd80  sub     rsp, 130h
0x18007fd87  mov     rax, cs:__security_cookie
0x18007fd8e  xor     rax, rsp
0x18007fd91  mov     [rbp+30h+var_10], rax
0x18007fd95  mov     rdi, rdx
0x18007fd98  mov     [rbp+30h+string], 0
0x18007fda0  mov     ebx, 6Ch ; 'l'
0x18007fda5  mov     ecx, ebx; unsigned int
0x18007fda7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007fdac  lea     edx, [rax-1]
0x18007fdaf  cmp     eax, ebx
0x18007fdb1  cmova   edx, ebx; length
0x18007fdb4  lea     r9, [rbp+30h+string]; string
0x18007fdb8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18007fdbc  lea     rcx, aWindowsFoundat_49; "Windows.Foundation.Collections.IVector`"...
0x18007fdc3  call    cs:__imp_WindowsCreateStringReference
0x18007fdc9  test    eax, eax
0x18007fdcb  jns     short loc_18007FDDF
0x18007fdcd  xor     r9d, r9d; lpArguments
0x18007fdd0  xor     r8d, r8d; nNumberOfArguments
0x18007fdd3  lea     edx, [rbx-6Bh]; dwExceptionFlags
0x18007fdd6  mov     ecx, eax; dwExceptionCode
0x18007fdd8  call    cs:__imp_RaiseException
0x18007fdde  int     3; Trap to Debugger
0x18007fddf  mov     [rbp+30h+var_58], 0
0x18007fde7  mov     ebx, 70h ; 'p'
0x18007fdec  mov     ecx, ebx; unsigned int
0x18007fdee  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007fdf3  lea     edx, [rax-1]
0x18007fdf6  cmp     eax, ebx
0x18007fdf8  cmova   edx, ebx; length
0x18007fdfb  lea     r9, [rbp+30h+var_58]; string
0x18007fdff  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18007fe03  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IVectorV"...
0x18007fe0a  call    cs:__imp_WindowsCreateStringReference
0x18007fe10  test    eax, eax
0x18007fe12  jns     short loc_18007FE26
0x18007fe14  xor     r9d, r9d; lpArguments
0x18007fe17  xor     r8d, r8d; nNumberOfArguments
0x18007fe1a  lea     edx, [rbx-6Fh]; dwExceptionFlags
0x18007fe1d  mov     ecx, eax; dwExceptionCode
0x18007fe1f  call    cs:__imp_RaiseException
0x18007fe25  int     3; Trap to Debugger
0x18007fe26  mov     [rbp+30h+var_38], 0
0x18007fe2e  mov     ebx, 6Eh ; 'n'
0x18007fe33  mov     ecx, ebx; unsigned int
0x18007fe35  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18007fe3a  lea     edx, [rax-1]
0x18007fe3d  cmp     eax, ebx
0x18007fe3f  cmova   edx, ebx; length
0x18007fe42  lea     r9, [rbp+30h+var_38]; string
0x18007fe46  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18007fe4a  lea     rcx, aWindowsFoundat_38; "Windows.Foundation.Collections.IIterato"...
0x18007fe51  call    cs:__imp_WindowsCreateStringReference
0x18007fe57  test    eax, eax
0x18007fe59  jns     short loc_18007FE6D
0x18007fe5b  xor     r9d, r9d; lpArguments
0x18007fe5e  xor     r8d, r8d; nNumberOfArguments
0x18007fe61  lea     edx, [rbx-6Dh]; dwExceptionFlags
0x18007fe64  mov     ecx, eax; dwExceptionCode
0x18007fe66  call    cs:__imp_RaiseException
0x18007fe6c  int     3; Trap to Debugger
0x18007fe6d  mov     rax, [rbp+30h+string]
0x18007fe71  mov     [rsp+130h+var_100], rax
0x18007fe76  mov     rax, [rbp+30h+var_58]
0x18007fe7a  mov     [rsp+130h+var_F8], rax
0x18007fe7f  mov     rax, [rbp+30h+var_38]
0x18007fe83  mov     [rsp+130h+var_F0], rax
0x18007fe88  movups  xmm0, xmmword ptr cs:_GUID_0b95d7ec_539e_4ad0_bab3_fc5acd05f716.Data1
0x18007fe8f  movdqu  [rsp+130h+var_E8], xmm0
0x18007fe95  movups  xmm1, xmmword ptr cs:_GUID_25c38f78_9b8a_56c1_b051_4f0f8e8090fa.Data1
0x18007fe9c  movdqu  [rsp+130h+var_D8], xmm1
0x18007fea2  movups  xmm0, xmmword ptr cs:_GUID_235d4a7a_1623_56c2_b025_0178912a1a38.Data1
0x18007fea9  movdqu  [rsp+130h+var_C8], xmm0
0x18007feaf  movups  xmm1, xmmword ptr cs:_GUID_c3913d00_5378_5397_bd8a_34cefc570171.Data1
0x18007feb6  movdqu  [rsp+130h+var_B8], xmm1
0x18007febc  movups  xmm0, xmmword ptr cs:_GUID_aee1aa8e_9e99_5c50_8661_23ca957a8300.Data1
0x18007fec3  movdqu  [rbp+30h+var_A8], xmm0
0x18007fec8  mov     [rsp+130h+var_110], 0
0x18007fed1  lea     rcx, [rsp+130h+var_110]
0x18007fed6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007fedb  mov     [rbp+30h+var_18], 0
0x18007fee3  lea     r9, [rbp+30h+var_18]; string
0x18007fee7  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18007feeb  mov     edx, 2Ch ; ','; length
0x18007fef0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18007fef7  call    cs:__imp_WindowsCreateStringReference
0x18007fefd  test    eax, eax
0x18007feff  jns     short loc_18007FF14
0x18007ff01  xor     r9d, r9d; lpArguments
0x18007ff04  xor     r8d, r8d; nNumberOfArguments
0x18007ff07  lea     edx, [r9+1]; dwExceptionFlags
0x18007ff0b  mov     ecx, eax; dwExceptionCode
0x18007ff0d  call    cs:__imp_RaiseException
0x18007ff13  int     3; Trap to Debugger
0x18007ff14  lea     r8, [rsp+130h+var_110]
0x18007ff19  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18007ff20  mov     rcx, [rbp+30h+var_18]
0x18007ff24  call    cs:__imp_RoGetActivationFactory
0x18007ff2a  mov     ebx, eax
0x18007ff2c  test    eax, eax
0x18007ff2e  jns     short loc_18007FF57
0x18007ff30  mov     rcx, [rsp+130h+var_110]
0x18007ff35  test    rcx, rcx
0x18007ff38  jz      short loc_18007FF50
0x18007ff3a  mov     [rsp+130h+var_110], 0
0x18007ff43  mov     rdx, [rcx]
0x18007ff46  mov     rax, [rdx+10h]
0x18007ff4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ff4f  nop
0x18007ff50  mov     eax, ebx
0x18007ff52  jmp     loc_18007FFF0
0x18007ff57  mov     [rsp+130h+var_108], 0
0x18007ff60  mov     rbx, [rsp+130h+var_110]
0x18007ff65  lea     rcx, [rsp+130h+var_108]
0x18007ff6a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ff6f  lea     r8, [rsp+130h+var_108]
0x18007ff74  lea     rdx, [rsp+130h+var_100]
0x18007ff79  mov     rcx, rbx
0x18007ff7c  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18007ff81  mov     ebx, eax
0x18007ff83  test    eax, eax
0x18007ff85  jns     short loc_18007FFC9
0x18007ff87  mov     rcx, [rsp+130h+var_108]
0x18007ff8c  test    rcx, rcx
0x18007ff8f  jz      short loc_18007FFA7
0x18007ff91  mov     [rsp+130h+var_108], 0
0x18007ff9a  mov     rdx, [rcx]
0x18007ff9d  mov     rax, [rdx+10h]
0x18007ffa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ffa6  nop
0x18007ffa7  mov     rcx, [rsp+130h+var_110]
0x18007ffac  test    rcx, rcx
0x18007ffaf  jz      short loc_18007FFC7
0x18007ffb1  mov     [rsp+130h+var_110], 0
0x18007ffba  mov     rax, [rcx]
0x18007ffbd  mov     rax, [rax+10h]
0x18007ffc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ffc6  nop
0x18007ffc7  jmp     short loc_18007FF50
0x18007ffc9  mov     rax, [rsp+130h+var_108]
0x18007ffce  mov     [rsp+130h+var_108], 0
0x18007ffd7  mov     [rdi], rax
0x18007ffda  lea     rcx, [rsp+130h+var_108]
0x18007ffdf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ffe4  lea     rcx, [rsp+130h+var_110]
0x18007ffe9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ffee  xor     eax, eax
0x18007fff0  mov     rcx, [rbp+30h+var_10]
0x18007fff4  xor     rcx, rsp; StackCookie
0x18007fff7  call    __security_check_cookie
0x18007fffc  lea     r11, [rsp+130h+var_s0]
0x180080004  mov     rbx, [r11+10h]
0x180080008  mov     rdi, [r11+20h]
0x18008000c  mov     rsp, r11
0x18008000f  pop     rbp
0x180080010  retn
```
