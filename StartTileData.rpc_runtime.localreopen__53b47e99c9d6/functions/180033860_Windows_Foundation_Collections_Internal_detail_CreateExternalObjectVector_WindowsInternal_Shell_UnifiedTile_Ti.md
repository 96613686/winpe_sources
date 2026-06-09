# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileVerb,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0> * *)

- ea: `0x180033860`
- end: `0x180033b22`
- name: `??$CreateExternalObjectVector@VTileVerb@UnifiedTile@Shell@WindowsInternal@@V?$AgileVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@1234@@Z`
- size: `706`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180031900`
- `0x1800328c0`
- `0x1800342c0`
- `0x180035700`
- `0x18011d2c0`
- `0x18013f6a0`
- `0x1802db560`
- `0x1803039a0`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x180033860`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033abd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033ad0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033ae3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033af6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033abd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033ad0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033ae3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180033af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800338b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800338ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800339bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800338b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800338ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180033925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800339bb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800339d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800339d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileVerb,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0>>(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // eax
  UINT32 v4; // edx
  HRESULT v5; // eax
  unsigned int v6; // eax
  UINT32 v7; // edx
  HRESULT v8; // eax
  int ActivationFactory; // ebx
  unsigned int v10; // eax
  UINT32 v11; // edx
  HRESULT v12; // eax
  HRESULT v13; // eax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rax
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x54u);
  v4 = v3 - 1;
  if ( v3 > 0x54 )
    v4 = 84;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<WindowsInternal.Shell.UnifiedTile.TileVerb>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v7 = v6 - 1;
  if ( v6 > 0x58 )
    v7 = 88;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<WindowsInternal.Shell.UnifiedTile.TileVerb>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  ActivationFactory = 86;
  v10 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x56u);
  v11 = v10 - 1;
  if ( v10 > 0x56 )
    v11 = 86;
  v12 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<WindowsInternal.Shell.UnifiedTile.TileVerb>",
          v11,
          &v33,
          &v34);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  v23[0] = string;
  v23[1] = v32;
  v23[2] = v34;
  v24 = GUID_f9ad7985_244a_4e61_8ba2_55a3f5e1c665;
  v25 = GUID_22e86da4_c5d3_50e2_b649_dd5a9e58fd26;
  v26 = GUID_11ddba60_bddf_5fe6_a694_983f146cf3a7;
  v27 = GUID_f22828b6_4de0_5f0f_92ce_18d99ed3efab;
  v28 = GUID_547264b8_ca74_57c4_a5fc_3da5ee8715df;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v13 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
LABEL_25:
    v20 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    return (unsigned int)ActivationFactory;
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
    goto LABEL_25;
  v22 = 0;
  v14 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v23, &v22);
  if ( ActivationFactory < 0 )
  {
    v15 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return (unsigned int)ActivationFactory;
  }
  v18 = v22;
  v22 = 0;
  *a2 = v18;
  v19 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180033860  mov     [rsp-8+arg_0], rbx
0x180033865  mov     [rsp-8+arg_10], rdi
0x18003386a  push    rbp
0x18003386b  lea     rbp, [rsp-30h]
0x180033870  sub     rsp, 130h
0x180033877  mov     rax, cs:__security_cookie
0x18003387e  xor     rax, rsp
0x180033881  mov     [rbp+30h+var_10], rax
0x180033885  mov     rdi, rdx
0x180033888  mov     [rbp+30h+string], 0
0x180033890  mov     ebx, 54h ; 'T'
0x180033895  mov     ecx, ebx; unsigned int
0x180033897  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003389c  lea     edx, [rax-1]
0x18003389f  cmp     eax, ebx
0x1800338a1  cmova   edx, ebx; length
0x1800338a4  lea     r9, [rbp+30h+string]; string
0x1800338a8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x1800338ac  lea     rcx, aWindowsFoundat_6; "Windows.Foundation.Collections.IVector`"...
0x1800338b3  call    cs:__imp_WindowsCreateStringReference
0x1800338b9  test    eax, eax
0x1800338bb  js      loc_180033AB1
0x1800338c1  mov     [rbp+30h+var_58], 0
0x1800338c9  mov     ebx, 58h ; 'X'
0x1800338ce  mov     ecx, ebx; unsigned int
0x1800338d0  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800338d5  lea     edx, [rax-1]
0x1800338d8  cmp     eax, ebx
0x1800338da  cmova   edx, ebx; length
0x1800338dd  lea     r9, [rbp+30h+var_58]; string
0x1800338e1  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800338e5  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IVectorV"...
0x1800338ec  call    cs:__imp_WindowsCreateStringReference
0x1800338f2  test    eax, eax
0x1800338f4  js      loc_180033AC4
0x1800338fa  mov     [rbp+30h+var_38], 0
0x180033902  mov     ebx, 56h ; 'V'
0x180033907  mov     ecx, ebx; unsigned int
0x180033909  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18003390e  lea     edx, [rax-1]
0x180033911  cmp     eax, ebx
0x180033913  cmova   edx, ebx; length
0x180033916  lea     r9, [rbp+30h+var_38]; string
0x18003391a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18003391e  lea     rcx, aWindowsFoundat_70; "Windows.Foundation.Collections.IIterato"...
0x180033925  call    cs:__imp_WindowsCreateStringReference
0x18003392b  test    eax, eax
0x18003392d  js      loc_180033AD7
0x180033933  mov     rax, [rbp+30h+string]
0x180033937  mov     [rsp+130h+var_100], rax
0x18003393c  mov     rax, [rbp+30h+var_58]
0x180033940  mov     [rsp+130h+var_F8], rax
0x180033945  mov     rax, [rbp+30h+var_38]
0x180033949  mov     [rsp+130h+var_F0], rax
0x18003394e  movups  xmm0, xmmword ptr cs:_GUID_f9ad7985_244a_4e61_8ba2_55a3f5e1c665.Data1
0x180033955  movdqu  [rsp+130h+var_E8], xmm0
0x18003395b  movups  xmm1, xmmword ptr cs:_GUID_22e86da4_c5d3_50e2_b649_dd5a9e58fd26.Data1
0x180033962  movdqu  [rsp+130h+var_D8], xmm1
0x180033968  movups  xmm0, xmmword ptr cs:_GUID_11ddba60_bddf_5fe6_a694_983f146cf3a7.Data1
0x18003396f  movdqu  [rsp+130h+var_C8], xmm0
0x180033975  movups  xmm1, xmmword ptr cs:_GUID_f22828b6_4de0_5f0f_92ce_18d99ed3efab.Data1
0x18003397c  movdqu  [rsp+130h+var_B8], xmm1
0x180033982  movups  xmm0, xmmword ptr cs:_GUID_547264b8_ca74_57c4_a5fc_3da5ee8715df.Data1
0x180033989  movdqu  [rbp+30h+var_A8], xmm0
0x18003398e  mov     [rsp+130h+var_110], 0
0x180033997  lea     rcx, [rsp+130h+var_110]
0x18003399c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800339a1  mov     [rbp+30h+var_18], 0
0x1800339a9  lea     r9, [rbp+30h+var_18]; string
0x1800339ad  lea     r8, [rbp+30h+var_30]; hstringHeader
0x1800339b1  lea     edx, [rbx-2Ah]; length
0x1800339b4  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800339bb  call    cs:__imp_WindowsCreateStringReference
0x1800339c1  test    eax, eax
0x1800339c3  js      loc_180033AEA
0x1800339c9  lea     r8, [rsp+130h+var_110]
0x1800339ce  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800339d5  mov     rcx, [rbp+30h+var_18]
0x1800339d9  call    cs:__imp_RoGetActivationFactory
0x1800339df  mov     ebx, eax
0x1800339e1  test    eax, eax
0x1800339e3  js      loc_180033AFD
0x1800339e9  mov     [rsp+130h+var_108], 0
0x1800339f2  mov     rbx, [rsp+130h+var_110]
0x1800339f7  lea     rcx, [rsp+130h+var_108]
0x1800339fc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180033a01  lea     r8, [rsp+130h+var_108]
0x180033a06  lea     rdx, [rsp+130h+var_100]
0x180033a0b  mov     rcx, rbx
0x180033a0e  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180033a13  mov     ebx, eax
0x180033a15  test    eax, eax
0x180033a17  jns     short loc_180033A7C
0x180033a19  mov     rcx, [rsp+130h+var_108]
0x180033a1e  test    rcx, rcx
0x180033a21  jz      short loc_180033A39
0x180033a23  mov     [rsp+130h+var_108], 0
0x180033a2c  mov     rdx, [rcx]
0x180033a2f  mov     rax, [rdx+10h]
0x180033a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a38  nop
0x180033a39  mov     rcx, [rsp+130h+var_110]
0x180033a3e  test    rcx, rcx
0x180033a41  jz      short loc_180033A59
0x180033a43  mov     [rsp+130h+var_110], 0
0x180033a4c  mov     rax, [rcx]
0x180033a4f  mov     rax, [rax+10h]
0x180033a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a58  nop
0x180033a59  mov     eax, ebx
0x180033a5b  mov     rcx, [rbp+30h+var_10]
0x180033a5f  xor     rcx, rsp; StackCookie
0x180033a62  call    __security_check_cookie
0x180033a67  lea     r11, [rsp+130h+var_s0]
0x180033a6f  mov     rbx, [r11+10h]
0x180033a73  mov     rdi, [r11+20h]
0x180033a77  mov     rsp, r11
0x180033a7a  pop     rbp
0x180033a7b  retn
0x180033a7c  mov     rax, [rsp+130h+var_108]
0x180033a81  mov     [rsp+130h+var_108], 0
0x180033a8a  mov     [rdi], rax
0x180033a8d  mov     rcx, [rsp+130h+var_110]
0x180033a92  test    rcx, rcx
0x180033a95  jz      short loc_180033AAD
0x180033a97  mov     [rsp+130h+var_110], 0
0x180033aa0  mov     rax, [rcx]
0x180033aa3  mov     rax, [rax+10h]
0x180033aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033aac  nop
0x180033aad  xor     eax, eax
0x180033aaf  jmp     short loc_180033A5B
0x180033ab1  xor     r9d, r9d; lpArguments
0x180033ab4  xor     r8d, r8d; nNumberOfArguments
0x180033ab7  lea     edx, [r9+1]; dwExceptionFlags
0x180033abb  mov     ecx, eax; dwExceptionCode
0x180033abd  call    cs:__imp_RaiseException
0x180033ac3  int     3; Trap to Debugger
0x180033ac4  xor     r9d, r9d; lpArguments
0x180033ac7  xor     r8d, r8d; nNumberOfArguments
0x180033aca  lea     edx, [r9+1]; dwExceptionFlags
0x180033ace  mov     ecx, eax; dwExceptionCode
0x180033ad0  call    cs:__imp_RaiseException
0x180033ad6  int     3; Trap to Debugger
0x180033ad7  xor     r9d, r9d; lpArguments
0x180033ada  xor     r8d, r8d; nNumberOfArguments
0x180033add  lea     edx, [r9+1]; dwExceptionFlags
0x180033ae1  mov     ecx, eax; dwExceptionCode
0x180033ae3  call    cs:__imp_RaiseException
0x180033ae9  int     3; Trap to Debugger
0x180033aea  xor     r9d, r9d; lpArguments
0x180033aed  xor     r8d, r8d; nNumberOfArguments
0x180033af0  lea     edx, [r9+1]; dwExceptionFlags
0x180033af4  mov     ecx, eax; dwExceptionCode
0x180033af6  call    cs:__imp_RaiseException
0x180033afc  nop
0x180033afd  mov     rcx, [rsp+130h+var_110]
0x180033b02  test    rcx, rcx
0x180033b05  jz      short loc_180033B1D
0x180033b07  mov     [rsp+130h+var_110], 0
0x180033b10  mov     rdx, [rcx]
0x180033b13  mov     rax, [rdx+10h]
0x180033b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b1c  nop
0x180033b1d  jmp     loc_180033A59
```
