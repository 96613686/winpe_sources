# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::SecondaryTileUserDataChange,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SecondaryTileUserDataChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SecondaryTileUserDataChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SecondaryTileUserDataChange *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SecondaryTileUserDataChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SecondaryTileUserDataChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SecondaryTileUserDataChange *>,0> * *)

- ea: `0x180060538`
- end: `0x1800607f7`
- name: `??$CreateExternalObjectVector@VSecondaryTileUserDataChange@StateRepository@Internal@Windows@@V?$AgileVector@PEAVSecondaryTileUserDataChange@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVSecondaryTileUserDataChange@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSecondaryTileUserDataChange@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVSecondaryTileUserDataChange@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVSecondaryTileUserDataChange@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVSecondaryTileUserDataChange@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800603f0`
- `0x1801c358c`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x180060538`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607ca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607f0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607b7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607ca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607dd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800607f0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800606b1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800606b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006058b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800605c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800605fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180060693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006058b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800605c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800605fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180060693`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::SecondaryTileUserDataChange,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::SecondaryTileUserDataChange *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::SecondaryTileUserDataChange *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::SecondaryTileUserDataChange *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x66u);
  v4 = v3 - 1;
  if ( v3 > 0x66 )
    v4 = 102;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.SecondaryTileUserDataChange>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x6Au);
  v7 = v6 - 1;
  if ( v6 > 0x6A )
    v7 = 106;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.SecondaryTileUserDataChange>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x68u);
  v10 = v9 - 1;
  if ( v9 > 0x68 )
    v10 = 104;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.SecondaryTileUserDataChange>",
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
  v24 = GUID_577f0ca3_d685_4480_9254_ccce83c68930;
  v25 = GUID_3407a6d3_6ff8_558a_8d39_ec9fa9c804ac;
  v26 = GUID_6a94ad8a_dd00_5816_a025_016d0ba262b6;
  v27 = GUID_d54e91cc_2033_5964_b69d_bd0f2459c396;
  v28 = GUID_3c310f81_daa9_5425_baa9_7e7958c75b5f;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x1800607F6LL);
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
0x180060538  mov     [rsp-8+arg_0], rbx
0x18006053d  mov     [rsp-8+arg_10], rdi
0x180060542  push    rbp
0x180060543  lea     rbp, [rsp-30h]
0x180060548  sub     rsp, 130h
0x18006054f  mov     rax, cs:__security_cookie
0x180060556  xor     rax, rsp
0x180060559  mov     [rbp+30h+var_10], rax
0x18006055d  mov     rdi, rdx
0x180060560  mov     [rbp+30h+string], 0
0x180060568  mov     ebx, 66h ; 'f'
0x18006056d  mov     ecx, ebx; unsigned int
0x18006056f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180060574  lea     edx, [rax-1]
0x180060577  cmp     eax, ebx
0x180060579  cmova   edx, ebx; length
0x18006057c  lea     r9, [rbp+30h+string]; string
0x180060580  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180060584  lea     rcx, aWindowsFoundat_78; "Windows.Foundation.Collections.IVector`"...
0x18006058b  call    cs:__imp_WindowsCreateStringReference
0x180060591  test    eax, eax
0x180060593  js      loc_1800607AB
0x180060599  mov     [rbp+30h+var_58], 0
0x1800605a1  mov     ebx, 6Ah ; 'j'
0x1800605a6  mov     ecx, ebx; unsigned int
0x1800605a8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800605ad  lea     edx, [rax-1]
0x1800605b0  cmp     eax, ebx
0x1800605b2  cmova   edx, ebx; length
0x1800605b5  lea     r9, [rbp+30h+var_58]; string
0x1800605b9  lea     r8, [rbp+30h+var_70]; hstringHeader
0x1800605bd  lea     rcx, aWindowsFoundat_34; "Windows.Foundation.Collections.IVectorV"...
0x1800605c4  call    cs:__imp_WindowsCreateStringReference
0x1800605ca  test    eax, eax
0x1800605cc  js      loc_1800607BE
0x1800605d2  mov     [rbp+30h+var_38], 0
0x1800605da  mov     ebx, 68h ; 'h'
0x1800605df  mov     ecx, ebx; unsigned int
0x1800605e1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800605e6  lea     edx, [rax-1]
0x1800605e9  cmp     eax, ebx
0x1800605eb  cmova   edx, ebx; length
0x1800605ee  lea     r9, [rbp+30h+var_38]; string
0x1800605f2  lea     r8, [rbp+30h+var_50]; hstringHeader
0x1800605f6  lea     rcx, aWindowsFoundat_180; "Windows.Foundation.Collections.IIterato"...
0x1800605fd  call    cs:__imp_WindowsCreateStringReference
0x180060603  test    eax, eax
0x180060605  js      loc_1800607D1
0x18006060b  mov     rax, [rbp+30h+string]
0x18006060f  mov     [rsp+130h+var_100], rax
0x180060614  mov     rax, [rbp+30h+var_58]
0x180060618  mov     [rsp+130h+var_F8], rax
0x18006061d  mov     rax, [rbp+30h+var_38]
0x180060621  mov     [rsp+130h+var_F0], rax
0x180060626  movups  xmm0, xmmword ptr cs:_GUID_577f0ca3_d685_4480_9254_ccce83c68930.Data1
0x18006062d  movdqu  [rsp+130h+var_E8], xmm0
0x180060633  movups  xmm1, xmmword ptr cs:_GUID_3407a6d3_6ff8_558a_8d39_ec9fa9c804ac.Data1
0x18006063a  movdqu  [rsp+130h+var_D8], xmm1
0x180060640  movups  xmm0, xmmword ptr cs:_GUID_6a94ad8a_dd00_5816_a025_016d0ba262b6.Data1
0x180060647  movdqu  [rsp+130h+var_C8], xmm0
0x18006064d  movups  xmm1, xmmword ptr cs:_GUID_d54e91cc_2033_5964_b69d_bd0f2459c396.Data1
0x180060654  movdqu  [rsp+130h+var_B8], xmm1
0x18006065a  movups  xmm0, xmmword ptr cs:_GUID_3c310f81_daa9_5425_baa9_7e7958c75b5f.Data1
0x180060661  movdqu  [rbp+30h+var_A8], xmm0
0x180060666  mov     [rsp+130h+var_110], 0
0x18006066f  lea     rcx, [rsp+130h+var_110]
0x180060674  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180060679  mov     [rbp+30h+var_18], 0
0x180060681  lea     r9, [rbp+30h+var_18]; string
0x180060685  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180060689  lea     edx, [rbx-3Ch]; length
0x18006068c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180060693  call    cs:__imp_WindowsCreateStringReference
0x180060699  test    eax, eax
0x18006069b  js      loc_1800607E4
0x1800606a1  lea     r8, [rsp+130h+var_110]
0x1800606a6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800606ad  mov     rcx, [rbp+30h+var_18]
0x1800606b1  call    cs:__imp_RoGetActivationFactory
0x1800606b7  mov     ebx, eax
0x1800606b9  test    eax, eax
0x1800606bb  js      loc_180060745
0x1800606c1  mov     [rsp+130h+var_108], 0
0x1800606ca  mov     rbx, [rsp+130h+var_110]
0x1800606cf  lea     rcx, [rsp+130h+var_108]
0x1800606d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800606d9  lea     r8, [rsp+130h+var_108]
0x1800606de  lea     rdx, [rsp+130h+var_100]
0x1800606e3  mov     rcx, rbx
0x1800606e6  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x1800606eb  mov     ebx, eax
0x1800606ed  test    eax, eax
0x1800606ef  js      short loc_180060769
0x1800606f1  mov     rax, [rsp+130h+var_108]
0x1800606f6  mov     [rsp+130h+var_108], 0
0x1800606ff  mov     [rdi], rax
0x180060702  mov     rcx, [rsp+130h+var_110]
0x180060707  test    rcx, rcx
0x18006070a  jz      short loc_180060722
0x18006070c  mov     [rsp+130h+var_110], 0
0x180060715  mov     rax, [rcx]
0x180060718  mov     rax, [rax+10h]
0x18006071c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060721  nop
0x180060722  xor     eax, eax
0x180060724  mov     rcx, [rbp+30h+var_10]
0x180060728  xor     rcx, rsp; StackCookie
0x18006072b  call    __security_check_cookie
0x180060730  lea     r11, [rsp+130h+var_s0]
0x180060738  mov     rbx, [r11+10h]
0x18006073c  mov     rdi, [r11+20h]
0x180060740  mov     rsp, r11
0x180060743  pop     rbp
0x180060744  retn
0x180060745  mov     rcx, [rsp+130h+var_110]
0x18006074a  test    rcx, rcx
0x18006074d  jz      short loc_180060765
0x18006074f  mov     [rsp+130h+var_110], 0
0x180060758  mov     rdx, [rcx]
0x18006075b  mov     rax, [rdx+10h]
0x18006075f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060764  nop
0x180060765  mov     eax, ebx
0x180060767  jmp     short loc_180060724
0x180060769  mov     rcx, [rsp+130h+var_108]
0x18006076e  test    rcx, rcx
0x180060771  jz      short loc_180060789
0x180060773  mov     [rsp+130h+var_108], 0
0x18006077c  mov     rdx, [rcx]
0x18006077f  mov     rax, [rdx+10h]
0x180060783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060788  nop
0x180060789  mov     rcx, [rsp+130h+var_110]
0x18006078e  test    rcx, rcx
0x180060791  jz      short loc_1800607A9
0x180060793  mov     [rsp+130h+var_110], 0
0x18006079c  mov     rax, [rcx]
0x18006079f  mov     rax, [rax+10h]
0x1800607a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800607a8  nop
0x1800607a9  jmp     short loc_180060765
0x1800607ab  xor     r9d, r9d; lpArguments
0x1800607ae  xor     r8d, r8d; nNumberOfArguments
0x1800607b1  lea     edx, [r9+1]; dwExceptionFlags
0x1800607b5  mov     ecx, eax; dwExceptionCode
0x1800607b7  call    cs:__imp_RaiseException
0x1800607bd  int     3; Trap to Debugger
0x1800607be  xor     r9d, r9d; lpArguments
0x1800607c1  xor     r8d, r8d; nNumberOfArguments
0x1800607c4  lea     edx, [r9+1]; dwExceptionFlags
0x1800607c8  mov     ecx, eax; dwExceptionCode
0x1800607ca  call    cs:__imp_RaiseException
0x1800607d0  int     3; Trap to Debugger
0x1800607d1  xor     r9d, r9d; lpArguments
0x1800607d4  xor     r8d, r8d; nNumberOfArguments
0x1800607d7  lea     edx, [r9+1]; dwExceptionFlags
0x1800607db  mov     ecx, eax; dwExceptionCode
0x1800607dd  call    cs:__imp_RaiseException
0x1800607e3  int     3; Trap to Debugger
0x1800607e4  xor     r9d, r9d; lpArguments
0x1800607e7  xor     r8d, r8d; nNumberOfArguments
0x1800607ea  lea     edx, [r9+1]; dwExceptionFlags
0x1800607ee  mov     ecx, eax; dwExceptionCode
0x1800607f0  call    cs:__imp_RaiseException
```
