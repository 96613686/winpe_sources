# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::TileView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::TileView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::TileView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::TileView *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::TileView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::TileView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::TileView *>,0> * *)

- ea: `0x180040b6c`
- end: `0x180040e2b`
- name: `??$CreateExternalObjectVector@VTileView@StateRepository@Internal@Windows@@V?$AgileVector@PEAVTileView@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVTileView@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVTileView@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVTileView@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVTileView@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVTileView@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180040a10`
- `0x1800bbf34`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x180040b6c`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040deb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040dfe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040e11`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040e24`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040deb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040dfe`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040e11`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040e24`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040ce5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040bbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040bf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040c31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180040cc7`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::TileView,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::TileView *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::TileView *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::TileView *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x53u);
  v4 = v3 - 1;
  if ( v3 > 0x53 )
    v4 = 83;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.TileView>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x57u);
  v7 = v6 - 1;
  if ( v6 > 0x57 )
    v7 = 87;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.TileView>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x55u);
  v10 = v9 - 1;
  if ( v9 > 0x55 )
    v10 = 85;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.TileView>",
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
  v24 = GUID_eac6bde3_486e_43d7_84de_f3526d5155a0;
  v25 = GUID_7387ba43_fe7c_53ac_8fb4_fb83aeb77cb7;
  v26 = GUID_638c5efb_2eb2_52bc_aa50_72f0e3bf4ad1;
  v27 = GUID_2698c31f_3890_5d02_ab12_7102fe62b99f;
  v28 = GUID_aa628c08_ca3a_5f48_bb79_7fe55814755b;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x180040E2ALL);
  }
  ActivationFactory = RoGetActivationFactory(v36, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v21);
  if ( ActivationFactory < 0 )
  {
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)ActivationFactory;
  }
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
0x180040b6c  mov     [rsp-8+arg_0], rbx
0x180040b71  mov     [rsp-8+arg_10], rdi
0x180040b76  push    rbp
0x180040b77  lea     rbp, [rsp-30h]
0x180040b7c  sub     rsp, 130h
0x180040b83  mov     rax, cs:__security_cookie
0x180040b8a  xor     rax, rsp
0x180040b8d  mov     [rbp+30h+var_10], rax
0x180040b91  mov     rdi, rdx
0x180040b94  mov     [rbp+30h+string], 0
0x180040b9c  mov     ebx, 53h ; 'S'
0x180040ba1  mov     ecx, ebx; unsigned int
0x180040ba3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180040ba8  lea     edx, [rax-1]
0x180040bab  cmp     eax, ebx
0x180040bad  cmova   edx, ebx; length
0x180040bb0  lea     r9, [rbp+30h+string]; string
0x180040bb4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180040bb8  lea     rcx, aWindowsFoundat_216; "Windows.Foundation.Collections.IVector`"...
0x180040bbf  call    cs:__imp_WindowsCreateStringReference
0x180040bc5  test    eax, eax
0x180040bc7  js      loc_180040DDF
0x180040bcd  mov     [rbp+30h+var_58], 0
0x180040bd5  mov     ebx, 57h ; 'W'
0x180040bda  mov     ecx, ebx; unsigned int
0x180040bdc  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180040be1  lea     edx, [rax-1]
0x180040be4  cmp     eax, ebx
0x180040be6  cmova   edx, ebx; length
0x180040be9  lea     r9, [rbp+30h+var_58]; string
0x180040bed  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180040bf1  lea     rcx, aWindowsFoundat_15; "Windows.Foundation.Collections.IVectorV"...
0x180040bf8  call    cs:__imp_WindowsCreateStringReference
0x180040bfe  test    eax, eax
0x180040c00  js      loc_180040DF2
0x180040c06  mov     [rbp+30h+var_38], 0
0x180040c0e  mov     ebx, 55h ; 'U'
0x180040c13  mov     ecx, ebx; unsigned int
0x180040c15  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180040c1a  lea     edx, [rax-1]
0x180040c1d  cmp     eax, ebx
0x180040c1f  cmova   edx, ebx; length
0x180040c22  lea     r9, [rbp+30h+var_38]; string
0x180040c26  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180040c2a  lea     rcx, aWindowsFoundat_85; "Windows.Foundation.Collections.IIterato"...
0x180040c31  call    cs:__imp_WindowsCreateStringReference
0x180040c37  test    eax, eax
0x180040c39  js      loc_180040E05
0x180040c3f  mov     rax, [rbp+30h+string]
0x180040c43  mov     [rsp+130h+var_100], rax
0x180040c48  mov     rax, [rbp+30h+var_58]
0x180040c4c  mov     [rsp+130h+var_F8], rax
0x180040c51  mov     rax, [rbp+30h+var_38]
0x180040c55  mov     [rsp+130h+var_F0], rax
0x180040c5a  movups  xmm0, xmmword ptr cs:_GUID_eac6bde3_486e_43d7_84de_f3526d5155a0.Data1
0x180040c61  movdqu  [rsp+130h+var_E8], xmm0
0x180040c67  movups  xmm1, xmmword ptr cs:_GUID_7387ba43_fe7c_53ac_8fb4_fb83aeb77cb7.Data1
0x180040c6e  movdqu  [rsp+130h+var_D8], xmm1
0x180040c74  movups  xmm0, xmmword ptr cs:_GUID_638c5efb_2eb2_52bc_aa50_72f0e3bf4ad1.Data1
0x180040c7b  movdqu  [rsp+130h+var_C8], xmm0
0x180040c81  movups  xmm1, xmmword ptr cs:_GUID_2698c31f_3890_5d02_ab12_7102fe62b99f.Data1
0x180040c88  movdqu  [rsp+130h+var_B8], xmm1
0x180040c8e  movups  xmm0, xmmword ptr cs:_GUID_aa628c08_ca3a_5f48_bb79_7fe55814755b.Data1
0x180040c95  movdqu  [rbp+30h+var_A8], xmm0
0x180040c9a  mov     [rsp+130h+var_110], 0
0x180040ca3  lea     rcx, [rsp+130h+var_110]
0x180040ca8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040cad  mov     [rbp+30h+var_18], 0
0x180040cb5  lea     r9, [rbp+30h+var_18]; string
0x180040cb9  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180040cbd  lea     edx, [rbx-29h]; length
0x180040cc0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180040cc7  call    cs:__imp_WindowsCreateStringReference
0x180040ccd  test    eax, eax
0x180040ccf  js      loc_180040E18
0x180040cd5  lea     r8, [rsp+130h+var_110]
0x180040cda  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180040ce1  mov     rcx, [rbp+30h+var_18]
0x180040ce5  call    cs:__imp_RoGetActivationFactory
0x180040ceb  mov     ebx, eax
0x180040ced  test    eax, eax
0x180040cef  js      loc_180040D79
0x180040cf5  mov     [rsp+130h+var_108], 0
0x180040cfe  mov     rbx, [rsp+130h+var_110]
0x180040d03  lea     rcx, [rsp+130h+var_108]
0x180040d08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180040d0d  lea     r8, [rsp+130h+var_108]
0x180040d12  lea     rdx, [rsp+130h+var_100]
0x180040d17  mov     rcx, rbx
0x180040d1a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180040d1f  mov     ebx, eax
0x180040d21  test    eax, eax
0x180040d23  js      short loc_180040D9D
0x180040d25  mov     rax, [rsp+130h+var_108]
0x180040d2a  mov     [rsp+130h+var_108], 0
0x180040d33  mov     [rdi], rax
0x180040d36  mov     rcx, [rsp+130h+var_110]
0x180040d3b  test    rcx, rcx
0x180040d3e  jz      short loc_180040D56
0x180040d40  mov     [rsp+130h+var_110], 0
0x180040d49  mov     rax, [rcx]
0x180040d4c  mov     rax, [rax+10h]
0x180040d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d55  nop
0x180040d56  xor     eax, eax
0x180040d58  mov     rcx, [rbp+30h+var_10]
0x180040d5c  xor     rcx, rsp; StackCookie
0x180040d5f  call    __security_check_cookie
0x180040d64  lea     r11, [rsp+130h+var_s0]
0x180040d6c  mov     rbx, [r11+10h]
0x180040d70  mov     rdi, [r11+20h]
0x180040d74  mov     rsp, r11
0x180040d77  pop     rbp
0x180040d78  retn
0x180040d79  mov     rcx, [rsp+130h+var_110]
0x180040d7e  test    rcx, rcx
0x180040d81  jz      short loc_180040D99
0x180040d83  mov     [rsp+130h+var_110], 0
0x180040d8c  mov     rdx, [rcx]
0x180040d8f  mov     rax, [rdx+10h]
0x180040d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d98  nop
0x180040d99  mov     eax, ebx
0x180040d9b  jmp     short loc_180040D58
0x180040d9d  mov     rcx, [rsp+130h+var_108]
0x180040da2  test    rcx, rcx
0x180040da5  jz      short loc_180040DBD
0x180040da7  mov     [rsp+130h+var_108], 0
0x180040db0  mov     rdx, [rcx]
0x180040db3  mov     rax, [rdx+10h]
0x180040db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dbc  nop
0x180040dbd  mov     rcx, [rsp+130h+var_110]
0x180040dc2  test    rcx, rcx
0x180040dc5  jz      short loc_180040DDD
0x180040dc7  mov     [rsp+130h+var_110], 0
0x180040dd0  mov     rax, [rcx]
0x180040dd3  mov     rax, [rax+10h]
0x180040dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ddc  nop
0x180040ddd  jmp     short loc_180040D99
0x180040ddf  xor     r9d, r9d; lpArguments
0x180040de2  xor     r8d, r8d; nNumberOfArguments
0x180040de5  lea     edx, [r9+1]; dwExceptionFlags
0x180040de9  mov     ecx, eax; dwExceptionCode
0x180040deb  call    cs:__imp_RaiseException
0x180040df1  int     3; Trap to Debugger
0x180040df2  xor     r9d, r9d; lpArguments
0x180040df5  xor     r8d, r8d; nNumberOfArguments
0x180040df8  lea     edx, [r9+1]; dwExceptionFlags
0x180040dfc  mov     ecx, eax; dwExceptionCode
0x180040dfe  call    cs:__imp_RaiseException
0x180040e04  int     3; Trap to Debugger
0x180040e05  xor     r9d, r9d; lpArguments
0x180040e08  xor     r8d, r8d; nNumberOfArguments
0x180040e0b  lea     edx, [r9+1]; dwExceptionFlags
0x180040e0f  mov     ecx, eax; dwExceptionCode
0x180040e11  call    cs:__imp_RaiseException
0x180040e17  int     3; Trap to Debugger
0x180040e18  xor     r9d, r9d; lpArguments
0x180040e1b  xor     r8d, r8d; nNumberOfArguments
0x180040e1e  lea     edx, [r9+1]; dwExceptionFlags
0x180040e22  mov     ecx, eax; dwExceptionCode
0x180040e24  call    cs:__imp_RaiseException
```
