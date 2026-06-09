# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::UnifiedTile,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::UnifiedTile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::UnifiedTile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,0> * *)

- ea: `0x180033e08`
- end: `0x18003409d`
- name: `??$CreateExternalObjectVector@VUnifiedTile@1Shell@WindowsInternal@@V?$AgileVector@PEAVUnifiedTile@1Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVUnifiedTile@1Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVUnifiedTile@1Shell@WindowsInternal@@@5678@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUnifiedTile@1Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVUnifiedTile@1Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVUnifiedTile@1Shell@WindowsInternal@@@5678@$0A@@1234@@Z`
- size: `661`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180033bc0`
- `0x1801bbca0`
- `0x1802f34f0`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x180033e08`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033fdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033fef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034002`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034015`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033fdc`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033fef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034002`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180034015`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033f63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033e94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033f63`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033f7d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180033f7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::UnifiedTile,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::UnifiedTile *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::UnifiedTile *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x57u);
  v4 = v3 - 1;
  if ( v3 > 0x57 )
    v4 = 87;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<WindowsInternal.Shell.UnifiedTile.UnifiedTile>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Bu);
  v7 = v6 - 1;
  if ( v6 > 0x5B )
    v7 = 91;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<WindowsInternal.Shell.UnifiedTile.UnifiedTile>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x59u);
  v10 = v9 - 1;
  if ( v9 > 0x59 )
    v10 = 89;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<WindowsInternal.Shell.UnifiedTile.UnifiedTile>",
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
  v22 = GUID_65b4e03e_a32e_40cf_8bab_b2d9c5287307;
  v23 = GUID_a2f17a98_0768_546f_8ad8_66f6953b777e;
  v24 = GUID_6381c4ce_6bb6_5164_93f9_4dc16358f384;
  v25 = GUID_daea49c4_acd7_5b49_813d_1157e9973e48;
  v26 = GUID_ae3b8b16_237d_597f_bf2b_aedf30e0022f;
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
0x180033e08  mov     [rsp-8+arg_0], rbx
0x180033e0d  mov     [rsp-8+arg_10], rdi
0x180033e12  push    rbp
0x180033e13  lea     rbp, [rsp-30h]
0x180033e18  sub     rsp, 130h
0x180033e1f  mov     rax, cs:__security_cookie
0x180033e26  xor     rax, rsp
0x180033e29  mov     [rbp+30h+var_10], rax
0x180033e2d  mov     rdi, rdx
0x180033e30  mov     [rbp+30h+string], 0
0x180033e38  mov     ebx, 57h ; 'W'
0x180033e3d  mov     ecx, ebx; unsigned int
0x180033e3f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180033e44  lea     edx, [rax-1]
0x180033e47  cmp     eax, ebx
0x180033e49  cmova   edx, ebx; length
0x180033e4c  lea     r9, [rbp+30h+string]; string
0x180033e50  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180033e54  lea     rcx, aWindowsFoundat_46; "Windows.Foundation.Collections.IVector`"...
0x180033e5b  call    cs:__imp_WindowsCreateStringReference
0x180033e61  test    eax, eax
0x180033e63  js      loc_180033FE3
0x180033e69  mov     [rbp+30h+var_58], 0
0x180033e71  mov     ebx, 5Bh ; '['
0x180033e76  mov     ecx, ebx; unsigned int
0x180033e78  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180033e7d  lea     edx, [rax-1]
0x180033e80  cmp     eax, ebx
0x180033e82  cmova   edx, ebx; length
0x180033e85  lea     r9, [rbp+30h+var_58]; string
0x180033e89  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180033e8d  lea     rcx, aWindowsFoundat_51; "Windows.Foundation.Collections.IVectorV"...
0x180033e94  call    cs:__imp_WindowsCreateStringReference
0x180033e9a  test    eax, eax
0x180033e9c  js      loc_180033FF6
0x180033ea2  mov     [rbp+30h+var_38], 0
0x180033eaa  mov     ebx, 59h ; 'Y'
0x180033eaf  mov     ecx, ebx; unsigned int
0x180033eb1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180033eb6  lea     edx, [rax-1]
0x180033eb9  cmp     eax, ebx
0x180033ebb  cmova   edx, ebx; length
0x180033ebe  lea     r9, [rbp+30h+var_38]; string
0x180033ec2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180033ec6  lea     rcx, aWindowsFoundat_28; "Windows.Foundation.Collections.IIterato"...
0x180033ecd  call    cs:__imp_WindowsCreateStringReference
0x180033ed3  test    eax, eax
0x180033ed5  js      loc_180034009
0x180033edb  mov     rax, [rbp+30h+string]
0x180033edf  mov     [rsp+130h+var_100], rax
0x180033ee4  mov     rax, [rbp+30h+var_58]
0x180033ee8  mov     [rsp+130h+var_F8], rax
0x180033eed  mov     rax, [rbp+30h+var_38]
0x180033ef1  mov     [rsp+130h+var_F0], rax
0x180033ef6  movups  xmm0, xmmword ptr cs:_GUID_65b4e03e_a32e_40cf_8bab_b2d9c5287307.Data1
0x180033efd  movdqu  [rsp+130h+var_E8], xmm0
0x180033f03  movups  xmm1, xmmword ptr cs:_GUID_a2f17a98_0768_546f_8ad8_66f6953b777e.Data1
0x180033f0a  movdqu  [rsp+130h+var_D8], xmm1
0x180033f10  movups  xmm0, xmmword ptr cs:_GUID_6381c4ce_6bb6_5164_93f9_4dc16358f384.Data1
0x180033f17  movdqu  [rsp+130h+var_C8], xmm0
0x180033f1d  movups  xmm1, xmmword ptr cs:_GUID_daea49c4_acd7_5b49_813d_1157e9973e48.Data1
0x180033f24  movdqu  [rsp+130h+var_B8], xmm1
0x180033f2a  movups  xmm0, xmmword ptr cs:_GUID_ae3b8b16_237d_597f_bf2b_aedf30e0022f.Data1
0x180033f31  movdqu  [rbp+30h+var_A8], xmm0
0x180033f36  mov     [rsp+130h+var_110], 0
0x180033f3f  lea     rcx, [rsp+130h+var_110]
0x180033f44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180033f49  mov     [rbp+30h+var_18], 0
0x180033f51  lea     r9, [rbp+30h+var_18]; string
0x180033f55  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180033f59  lea     edx, [rbx-2Dh]; length
0x180033f5c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180033f63  call    cs:__imp_WindowsCreateStringReference
0x180033f69  test    eax, eax
0x180033f6b  js      short loc_180033FD0
0x180033f6d  lea     r8, [rsp+130h+var_110]
0x180033f72  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180033f79  mov     rcx, [rbp+30h+var_18]
0x180033f7d  call    cs:__imp_RoGetActivationFactory
0x180033f83  mov     ebx, eax
0x180033f85  test    eax, eax
0x180033f87  jns     loc_18003401C
0x180033f8d  mov     rcx, [rsp+130h+var_110]
0x180033f92  test    rcx, rcx
0x180033f95  jz      short loc_180033FAD
0x180033f97  mov     [rsp+130h+var_110], 0
0x180033fa0  mov     rdx, [rcx]
0x180033fa3  mov     rax, [rdx+10h]
0x180033fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033fac  nop
0x180033fad  mov     eax, ebx
0x180033faf  mov     rcx, [rbp+30h+var_10]
0x180033fb3  xor     rcx, rsp; StackCookie
0x180033fb6  call    __security_check_cookie
0x180033fbb  lea     r11, [rsp+130h+var_s0]
0x180033fc3  mov     rbx, [r11+10h]
0x180033fc7  mov     rdi, [r11+20h]
0x180033fcb  mov     rsp, r11
0x180033fce  pop     rbp
0x180033fcf  retn
0x180033fd0  xor     r9d, r9d; lpArguments
0x180033fd3  xor     r8d, r8d; nNumberOfArguments
0x180033fd6  lea     edx, [r9+1]; dwExceptionFlags
0x180033fda  mov     ecx, eax; dwExceptionCode
0x180033fdc  call    cs:__imp_RaiseException
0x180033fe2  int     3; Trap to Debugger
0x180033fe3  xor     r9d, r9d; lpArguments
0x180033fe6  xor     r8d, r8d; nNumberOfArguments
0x180033fe9  lea     edx, [r9+1]; dwExceptionFlags
0x180033fed  mov     ecx, eax; dwExceptionCode
0x180033fef  call    cs:__imp_RaiseException
0x180033ff5  int     3; Trap to Debugger
0x180033ff6  xor     r9d, r9d; lpArguments
0x180033ff9  xor     r8d, r8d; nNumberOfArguments
0x180033ffc  lea     edx, [r9+1]; dwExceptionFlags
0x180034000  mov     ecx, eax; dwExceptionCode
0x180034002  call    cs:__imp_RaiseException
0x180034008  int     3; Trap to Debugger
0x180034009  xor     r9d, r9d; lpArguments
0x18003400c  xor     r8d, r8d; nNumberOfArguments
0x18003400f  lea     edx, [r9+1]; dwExceptionFlags
0x180034013  mov     ecx, eax; dwExceptionCode
0x180034015  call    cs:__imp_RaiseException
0x18003401b  int     3; Trap to Debugger
0x18003401c  mov     [rsp+130h+var_108], 0
0x180034025  mov     rbx, [rsp+130h+var_110]
0x18003402a  lea     rcx, [rsp+130h+var_108]
0x18003402f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034034  lea     r8, [rsp+130h+var_108]
0x180034039  lea     rdx, [rsp+130h+var_100]
0x18003403e  mov     rcx, rbx
0x180034041  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180034046  mov     ebx, eax
0x180034048  test    eax, eax
0x18003404a  js      short loc_180034084
0x18003404c  mov     rax, [rsp+130h+var_108]
0x180034051  mov     [rsp+130h+var_108], 0
0x18003405a  mov     [rdi], rax
0x18003405d  mov     rcx, [rsp+130h+var_110]
0x180034062  test    rcx, rcx
0x180034065  jz      short loc_18003407D
0x180034067  mov     [rsp+130h+var_110], 0
0x180034070  mov     rax, [rcx]
0x180034073  mov     rax, [rax+10h]
0x180034077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003407c  nop
0x18003407d  xor     eax, eax
0x18003407f  jmp     loc_180033FAF
0x180034084  lea     rcx, [rsp+130h+var_108]
0x180034089  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003408e  lea     rcx, [rsp+130h+var_110]
0x180034093  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034098  jmp     loc_180033FAD
```
