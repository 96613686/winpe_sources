# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *>,0> * *)

- ea: `0x180079de0`
- end: `0x18007a0a6`
- name: `??$CreateExternalObjectVector@UICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@V?$AgileVector@PEAUICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAUICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@@6789@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAUICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUICDSTilePropertiesItem@CDSProperties@Shell@WindowsInternal@@@6789@$0A@@1234@@Z`
- size: `710`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180043b94`
- `0x180079354`
- `0x1800ac100`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x180079de0`
- `0x180201e50`
- `0x180210488`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079ffd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a010`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a023`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a036`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180079ffd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a010`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a023`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007a036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079e6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079ea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079f3b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079e6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079ea5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180079f3b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180079f59`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180079f59`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::CDSProperties::ICDSTilePropertiesItem *>,0>>(
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
  __int64 v15; // rax
  __int64 v16; // rcx
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
         L"Windows.Foundation.Collections.IVector`1<WindowsInternal.Shell.CDSProperties.ICDSTilePropertiesItem>",
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
         L"Windows.Foundation.Collections.IVectorView`1<WindowsInternal.Shell.CDSProperties.ICDSTilePropertiesItem>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  ActivationFactory = 102;
  v10 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x66u);
  v11 = v10 - 1;
  if ( v10 > 0x66 )
    v11 = 102;
  v12 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<WindowsInternal.Shell.CDSProperties.ICDSTilePropertiesItem>",
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
  v24 = GUID_0b95d7ec_539e_4ad0_bab3_fc5acd05f716;
  v25 = GUID_a08e9c14_bf8d_5cce_af50_94b0eafd06ab;
  v26 = GUID_d332ce08_4b29_5724_bd56_ff69c15e6279;
  v27 = GUID_7bcb79a4_b7dc_5480_b54c_81f41a1e2a13;
  v28 = GUID_27f9afe0_bc18_54b2_8328_318b11dfa22b;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v13 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v13 < 0 )
  {
    RaiseException(v13, 1u, 0, 0);
LABEL_20:
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
    goto LABEL_20;
  v22 = 0;
  v14 = v21;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v14, v23, &v22);
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
  v15 = v22;
  v22 = 0;
  *a2 = v15;
  v16 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x180079de0  mov     [rsp-8+arg_0], rbx
0x180079de5  mov     [rsp-8+arg_10], rdi
0x180079dea  push    rbp
0x180079deb  lea     rbp, [rsp-30h]
0x180079df0  sub     rsp, 130h
0x180079df7  mov     rax, cs:__security_cookie
0x180079dfe  xor     rax, rsp
0x180079e01  mov     [rbp+30h+var_10], rax
0x180079e05  mov     rdi, rdx
0x180079e08  mov     [rbp+30h+string], 0
0x180079e10  mov     ebx, 64h ; 'd'
0x180079e15  mov     ecx, ebx; unsigned int
0x180079e17  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180079e1c  lea     edx, [rax-1]
0x180079e1f  cmp     eax, ebx
0x180079e21  cmova   edx, ebx; length
0x180079e24  lea     r9, [rbp+30h+string]; string
0x180079e28  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180079e2c  lea     rcx, aWindowsFoundat_20; "Windows.Foundation.Collections.IVector`"...
0x180079e33  call    cs:__imp_WindowsCreateStringReference
0x180079e39  test    eax, eax
0x180079e3b  js      loc_180079FF1
0x180079e41  mov     [rbp+30h+var_58], 0
0x180079e49  mov     ebx, 68h ; 'h'
0x180079e4e  mov     ecx, ebx; unsigned int
0x180079e50  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180079e55  lea     edx, [rax-1]
0x180079e58  cmp     eax, ebx
0x180079e5a  cmova   edx, ebx; length
0x180079e5d  lea     r9, [rbp+30h+var_58]; string
0x180079e61  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180079e65  lea     rcx, aWindowsFoundat_21; "Windows.Foundation.Collections.IVectorV"...
0x180079e6c  call    cs:__imp_WindowsCreateStringReference
0x180079e72  test    eax, eax
0x180079e74  js      loc_18007A004
0x180079e7a  mov     [rbp+30h+var_38], 0
0x180079e82  mov     ebx, 66h ; 'f'
0x180079e87  mov     ecx, ebx; unsigned int
0x180079e89  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180079e8e  lea     edx, [rax-1]
0x180079e91  cmp     eax, ebx
0x180079e93  cmova   edx, ebx; length
0x180079e96  lea     r9, [rbp+30h+var_38]; string
0x180079e9a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180079e9e  lea     rcx, aWindowsFoundat_17; "Windows.Foundation.Collections.IIterato"...
0x180079ea5  call    cs:__imp_WindowsCreateStringReference
0x180079eab  test    eax, eax
0x180079ead  js      loc_18007A017
0x180079eb3  mov     rax, [rbp+30h+string]
0x180079eb7  mov     [rsp+130h+var_100], rax
0x180079ebc  mov     rax, [rbp+30h+var_58]
0x180079ec0  mov     [rsp+130h+var_F8], rax
0x180079ec5  mov     rax, [rbp+30h+var_38]
0x180079ec9  mov     [rsp+130h+var_F0], rax
0x180079ece  movups  xmm0, xmmword ptr cs:_GUID_0b95d7ec_539e_4ad0_bab3_fc5acd05f716.Data1
0x180079ed5  movdqu  [rsp+130h+var_E8], xmm0
0x180079edb  movups  xmm1, xmmword ptr cs:_GUID_a08e9c14_bf8d_5cce_af50_94b0eafd06ab.Data1
0x180079ee2  movdqu  [rsp+130h+var_D8], xmm1
0x180079ee8  movups  xmm0, xmmword ptr cs:_GUID_d332ce08_4b29_5724_bd56_ff69c15e6279.Data1
0x180079eef  movdqu  [rsp+130h+var_C8], xmm0
0x180079ef5  movups  xmm1, xmmword ptr cs:_GUID_7bcb79a4_b7dc_5480_b54c_81f41a1e2a13.Data1
0x180079efc  movdqu  [rsp+130h+var_B8], xmm1
0x180079f02  movups  xmm0, xmmword ptr cs:_GUID_27f9afe0_bc18_54b2_8328_318b11dfa22b.Data1
0x180079f09  movdqu  [rbp+30h+var_A8], xmm0
0x180079f0e  mov     [rsp+130h+var_110], 0
0x180079f17  lea     rcx, [rsp+130h+var_110]
0x180079f1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079f21  mov     [rbp+30h+var_18], 0
0x180079f29  lea     r9, [rbp+30h+var_18]; string
0x180079f2d  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180079f31  lea     edx, [rbx-3Ah]; length
0x180079f34  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180079f3b  call    cs:__imp_WindowsCreateStringReference
0x180079f41  test    eax, eax
0x180079f43  js      loc_18007A02A
0x180079f49  lea     r8, [rsp+130h+var_110]
0x180079f4e  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180079f55  mov     rcx, [rbp+30h+var_18]
0x180079f59  call    cs:__imp_RoGetActivationFactory
0x180079f5f  mov     ebx, eax
0x180079f61  test    eax, eax
0x180079f63  js      loc_18007A03D
0x180079f69  mov     [rsp+130h+var_108], 0
0x180079f72  mov     rbx, [rsp+130h+var_110]
0x180079f77  lea     rcx, [rsp+130h+var_108]
0x180079f7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180079f81  lea     r8, [rsp+130h+var_108]
0x180079f86  lea     rdx, [rsp+130h+var_100]
0x180079f8b  mov     rcx, rbx
0x180079f8e  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180079f93  mov     ebx, eax
0x180079f95  test    eax, eax
0x180079f97  js      loc_18007A064
0x180079f9d  mov     rax, [rsp+130h+var_108]
0x180079fa2  mov     [rsp+130h+var_108], 0
0x180079fab  mov     [rdi], rax
0x180079fae  mov     rcx, [rsp+130h+var_110]
0x180079fb3  test    rcx, rcx
0x180079fb6  jz      short loc_180079FCE
0x180079fb8  mov     [rsp+130h+var_110], 0
0x180079fc1  mov     rax, [rcx]
0x180079fc4  mov     rax, [rax+10h]
0x180079fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079fcd  nop
0x180079fce  xor     eax, eax
0x180079fd0  mov     rcx, [rbp+30h+var_10]
0x180079fd4  xor     rcx, rsp; StackCookie
0x180079fd7  call    __security_check_cookie
0x180079fdc  lea     r11, [rsp+130h+var_s0]
0x180079fe4  mov     rbx, [r11+10h]
0x180079fe8  mov     rdi, [r11+20h]
0x180079fec  mov     rsp, r11
0x180079fef  pop     rbp
0x180079ff0  retn
0x180079ff1  xor     r9d, r9d; lpArguments
0x180079ff4  xor     r8d, r8d; nNumberOfArguments
0x180079ff7  lea     edx, [r9+1]; dwExceptionFlags
0x180079ffb  mov     ecx, eax; dwExceptionCode
0x180079ffd  call    cs:__imp_RaiseException
0x18007a003  int     3; Trap to Debugger
0x18007a004  xor     r9d, r9d; lpArguments
0x18007a007  xor     r8d, r8d; nNumberOfArguments
0x18007a00a  lea     edx, [r9+1]; dwExceptionFlags
0x18007a00e  mov     ecx, eax; dwExceptionCode
0x18007a010  call    cs:__imp_RaiseException
0x18007a016  int     3; Trap to Debugger
0x18007a017  xor     r9d, r9d; lpArguments
0x18007a01a  xor     r8d, r8d; nNumberOfArguments
0x18007a01d  lea     edx, [r9+1]; dwExceptionFlags
0x18007a021  mov     ecx, eax; dwExceptionCode
0x18007a023  call    cs:__imp_RaiseException
0x18007a029  int     3; Trap to Debugger
0x18007a02a  xor     r9d, r9d; lpArguments
0x18007a02d  xor     r8d, r8d; nNumberOfArguments
0x18007a030  lea     edx, [r9+1]; dwExceptionFlags
0x18007a034  mov     ecx, eax; dwExceptionCode
0x18007a036  call    cs:__imp_RaiseException
0x18007a03c  nop
0x18007a03d  mov     rcx, [rsp+130h+var_110]
0x18007a042  test    rcx, rcx
0x18007a045  jz      short loc_18007A05D
0x18007a047  mov     [rsp+130h+var_110], 0
0x18007a050  mov     rdx, [rcx]
0x18007a053  mov     rax, [rdx+10h]
0x18007a057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a05c  nop
0x18007a05d  mov     eax, ebx
0x18007a05f  jmp     loc_180079FD0
0x18007a064  mov     rcx, [rsp+130h+var_108]
0x18007a069  test    rcx, rcx
0x18007a06c  jz      short loc_18007A084
0x18007a06e  mov     [rsp+130h+var_108], 0
0x18007a077  mov     rdx, [rcx]
0x18007a07a  mov     rax, [rdx+10h]
0x18007a07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a083  nop
0x18007a084  mov     rcx, [rsp+130h+var_110]
0x18007a089  test    rcx, rcx
0x18007a08c  jz      short loc_18007A0A4
0x18007a08e  mov     [rsp+130h+var_110], 0
0x18007a097  mov     rax, [rcx]
0x18007a09a  mov     rax, [rax+10h]
0x18007a09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a0a3  nop
0x18007a0a4  jmp     short loc_18007A05D
```
