# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Internal::IActiveMediaAppInfo,Windows::Foundation::Collections::Internal::Vector<Windows::Media::Internal::IActiveMediaAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::IActiveMediaAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::IActiveMediaAppInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Internal::IActiveMediaAppInfo *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Media::Internal::IActiveMediaAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::IActiveMediaAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::IActiveMediaAppInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Internal::IActiveMediaAppInfo *>> * *)

- ea: `0x18002b2a0`
- end: `0x18002b539`
- name: `??$CreateExternalObjectVector@UIActiveMediaAppInfo@Internal@Media@Windows@@V?$Vector@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@U?$DefaultEqualityPredicate@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@@2Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@@2674@U?$DefaultVectorOptions@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@@2674@@2Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@U?$DefaultEqualityPredicate@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@@2Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@@2674@U?$DefaultVectorOptions@PEAUIActiveMediaAppInfo@Internal@Media@Windows@@@2674@@1234@@Z`
- size: `665`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002afd0`
- `0x18002c200`

## callees

- `0x18000d11c`
- `0x18002b2a0`
- `0x18002b5d0`
- `0x180087e80`
- `0x1800f4450`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b4e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b4f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b506`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b519`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b4e0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b4f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b506`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b2f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b32c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b3fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b2f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b32c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b365`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b3fb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b419`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b419`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::Internal::IActiveMediaAppInfo,Windows::Foundation::Collections::Internal::Vector<Windows::Media::Internal::IActiveMediaAppInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::Internal::IActiveMediaAppInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::Internal::IActiveMediaAppInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Media::Internal::IActiveMediaAppInfo *>>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x54u);
  v4 = v3 - 1;
  if ( v3 > 0x54 )
    v4 = 84;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Media.Internal.IActiveMediaAppInfo>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v30 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v7 = v6 - 1;
  if ( v6 > 0x58 )
    v7 = 88;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Media.Internal.IActiveMediaAppInfo>",
         v7,
         &v29,
         &v30);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x56u);
  v10 = v9 - 1;
  if ( v9 > 0x56 )
    v10 = 86;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Media.Internal.IActiveMediaAppInfo>",
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
  v22 = GUID_d522b0f3_349a_4afa_8c28_f4227aaaa410;
  v23 = GUID_24ccfbbe_fa65_5bd7_88b8_da2cf4f96998;
  v24 = GUID_f1ba560a_c735_5442_8b30_fd6a398899ca;
  v25 = GUID_e337aef7_d734_5e7f_a9e6_c30d4685a9f1;
  v26 = GUID_14020c87_81a6_5c8b_94be_89266ed89db9;
  v19 = 0;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v19);
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
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v20);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v16, v21, &v20);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v20);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v19);
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
0x18002b2a0  mov     [rsp-8+arg_0], rbx
0x18002b2a5  mov     [rsp-8+arg_10], rdi
0x18002b2aa  push    rbp
0x18002b2ab  lea     rbp, [rsp-30h]
0x18002b2b0  sub     rsp, 130h
0x18002b2b7  mov     rax, cs:__security_cookie
0x18002b2be  xor     rax, rsp
0x18002b2c1  mov     [rbp+30h+var_10], rax
0x18002b2c5  mov     rdi, rdx
0x18002b2c8  mov     [rbp+30h+string], 0
0x18002b2d0  mov     ebx, 54h ; 'T'
0x18002b2d5  mov     ecx, ebx; unsigned int
0x18002b2d7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002b2dc  lea     edx, [rax-1]
0x18002b2df  cmp     eax, ebx
0x18002b2e1  cmova   edx, ebx; length
0x18002b2e4  lea     r9, [rbp+30h+string]; string
0x18002b2e8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002b2ec  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IVector`"...
0x18002b2f3  call    cs:__imp_WindowsCreateStringReference
0x18002b2f9  test    eax, eax
0x18002b2fb  js      loc_18002B4D4
0x18002b301  mov     [rbp+30h+var_58], 0
0x18002b309  mov     ebx, 58h ; 'X'
0x18002b30e  mov     ecx, ebx; unsigned int
0x18002b310  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002b315  lea     edx, [rax-1]
0x18002b318  cmp     eax, ebx
0x18002b31a  cmova   edx, ebx; length
0x18002b31d  lea     r9, [rbp+30h+var_58]; string
0x18002b321  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002b325  lea     rcx, aWindowsFoundat_9; "Windows.Foundation.Collections.IVectorV"...
0x18002b32c  call    cs:__imp_WindowsCreateStringReference
0x18002b332  test    eax, eax
0x18002b334  js      loc_18002B4E7
0x18002b33a  mov     [rbp+30h+var_38], 0
0x18002b342  mov     ebx, 56h ; 'V'
0x18002b347  mov     ecx, ebx; unsigned int
0x18002b349  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002b34e  lea     edx, [rax-1]
0x18002b351  cmp     eax, ebx
0x18002b353  cmova   edx, ebx; length
0x18002b356  lea     r9, [rbp+30h+var_38]; string
0x18002b35a  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002b35e  lea     rcx, aWindowsFoundat_8; "Windows.Foundation.Collections.IIterato"...
0x18002b365  call    cs:__imp_WindowsCreateStringReference
0x18002b36b  test    eax, eax
0x18002b36d  js      loc_18002B4FA
0x18002b373  mov     rax, [rbp+30h+string]
0x18002b377  mov     [rsp+130h+var_100], rax
0x18002b37c  mov     rax, [rbp+30h+var_58]
0x18002b380  mov     [rsp+130h+var_F8], rax
0x18002b385  mov     rax, [rbp+30h+var_38]
0x18002b389  mov     [rsp+130h+var_F0], rax
0x18002b38e  movups  xmm0, xmmword ptr cs:_GUID_d522b0f3_349a_4afa_8c28_f4227aaaa410.Data1
0x18002b395  movdqu  [rsp+130h+var_E8], xmm0
0x18002b39b  movups  xmm1, xmmword ptr cs:_GUID_24ccfbbe_fa65_5bd7_88b8_da2cf4f96998.Data1
0x18002b3a2  movdqu  [rsp+130h+var_D8], xmm1
0x18002b3a8  movups  xmm0, xmmword ptr cs:_GUID_f1ba560a_c735_5442_8b30_fd6a398899ca.Data1
0x18002b3af  movdqu  [rsp+130h+var_C8], xmm0
0x18002b3b5  movups  xmm1, xmmword ptr cs:_GUID_e337aef7_d734_5e7f_a9e6_c30d4685a9f1.Data1
0x18002b3bc  movdqu  [rsp+130h+var_B8], xmm1
0x18002b3c2  movups  xmm0, xmmword ptr cs:_GUID_14020c87_81a6_5c8b_94be_89266ed89db9.Data1
0x18002b3c9  movdqu  [rbp+30h+var_A8], xmm0
0x18002b3ce  mov     [rsp+130h+var_110], 0
0x18002b3d7  lea     rcx, [rsp+130h+var_110]
0x18002b3dc  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002b3e1  mov     [rbp+30h+var_18], 0
0x18002b3e9  lea     r9, [rbp+30h+var_18]; string
0x18002b3ed  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002b3f1  lea     edx, [rbx-2Ah]; length
0x18002b3f4  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002b3fb  call    cs:__imp_WindowsCreateStringReference
0x18002b401  test    eax, eax
0x18002b403  js      loc_18002B50D
0x18002b409  lea     r8, [rsp+130h+var_110]
0x18002b40e  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002b415  mov     rcx, [rbp+30h+var_18]
0x18002b419  call    cs:__imp_RoGetActivationFactory
0x18002b41f  mov     ebx, eax
0x18002b421  test    eax, eax
0x18002b423  jns     short loc_18002B468
0x18002b425  mov     rcx, [rsp+130h+var_110]
0x18002b42a  test    rcx, rcx
0x18002b42d  jz      short loc_18002B445
0x18002b42f  mov     [rsp+130h+var_110], 0
0x18002b438  mov     rdx, [rcx]
0x18002b43b  mov     rax, [rdx+10h]
0x18002b43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b444  nop
0x18002b445  mov     eax, ebx
0x18002b447  mov     rcx, [rbp+30h+var_10]
0x18002b44b  xor     rcx, rsp; StackCookie
0x18002b44e  call    __security_check_cookie
0x18002b453  lea     r11, [rsp+130h+var_s0]
0x18002b45b  mov     rbx, [r11+10h]
0x18002b45f  mov     rdi, [r11+20h]
0x18002b463  mov     rsp, r11
0x18002b466  pop     rbp
0x18002b467  retn
0x18002b468  mov     [rsp+130h+var_108], 0
0x18002b471  mov     rbx, [rsp+130h+var_110]
0x18002b476  lea     rcx, [rsp+130h+var_108]
0x18002b47b  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002b480  lea     r8, [rsp+130h+var_108]
0x18002b485  lea     rdx, [rsp+130h+var_100]
0x18002b48a  mov     rcx, rbx
0x18002b48d  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18002b492  mov     ebx, eax
0x18002b494  test    eax, eax
0x18002b496  js      loc_18002B520
0x18002b49c  mov     rax, [rsp+130h+var_108]
0x18002b4a1  mov     [rsp+130h+var_108], 0
0x18002b4aa  mov     [rdi], rax
0x18002b4ad  mov     rcx, [rsp+130h+var_110]
0x18002b4b2  test    rcx, rcx
0x18002b4b5  jz      short loc_18002B4CD
0x18002b4b7  mov     [rsp+130h+var_110], 0
0x18002b4c0  mov     rax, [rcx]
0x18002b4c3  mov     rax, [rax+10h]
0x18002b4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4cc  nop
0x18002b4cd  xor     eax, eax
0x18002b4cf  jmp     loc_18002B447
0x18002b4d4  xor     r9d, r9d; lpArguments
0x18002b4d7  xor     r8d, r8d; nNumberOfArguments
0x18002b4da  lea     edx, [r9+1]; dwExceptionFlags
0x18002b4de  mov     ecx, eax; dwExceptionCode
0x18002b4e0  call    cs:__imp_RaiseException
0x18002b4e6  int     3; Trap to Debugger
0x18002b4e7  xor     r9d, r9d; lpArguments
0x18002b4ea  xor     r8d, r8d; nNumberOfArguments
0x18002b4ed  lea     edx, [r9+1]; dwExceptionFlags
0x18002b4f1  mov     ecx, eax; dwExceptionCode
0x18002b4f3  call    cs:__imp_RaiseException
0x18002b4f9  int     3; Trap to Debugger
0x18002b4fa  xor     r9d, r9d; lpArguments
0x18002b4fd  xor     r8d, r8d; nNumberOfArguments
0x18002b500  lea     edx, [r9+1]; dwExceptionFlags
0x18002b504  mov     ecx, eax; dwExceptionCode
0x18002b506  call    cs:__imp_RaiseException
0x18002b50c  int     3; Trap to Debugger
0x18002b50d  xor     r9d, r9d; lpArguments
0x18002b510  xor     r8d, r8d; nNumberOfArguments
0x18002b513  lea     edx, [r9+1]; dwExceptionFlags
0x18002b517  mov     ecx, eax; dwExceptionCode
0x18002b519  call    cs:__imp_RaiseException
0x18002b51f  int     3; Trap to Debugger
0x18002b520  lea     rcx, [rsp+130h+var_108]
0x18002b525  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002b52a  lea     rcx, [rsp+130h+var_110]
0x18002b52f  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18002b534  jmp     loc_18002B445
```
