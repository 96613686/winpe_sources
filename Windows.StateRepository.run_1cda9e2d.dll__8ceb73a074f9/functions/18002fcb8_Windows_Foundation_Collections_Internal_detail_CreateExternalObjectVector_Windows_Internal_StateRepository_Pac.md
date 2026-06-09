# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageFamilyPolicy,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageFamilyPolicy *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageFamilyPolicy *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageFamilyPolicy *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageFamilyPolicy *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageFamilyPolicy *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageFamilyPolicy *>,0> * *)

- ea: `0x18002fcb8`
- end: `0x18002ff77`
- name: `??$CreateExternalObjectVector@VPackageFamilyPolicy@StateRepository@Internal@Windows@@V?$AgileVector@PEAVPackageFamilyPolicy@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageFamilyPolicy@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageFamilyPolicy@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVPackageFamilyPolicy@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVPackageFamilyPolicy@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVPackageFamilyPolicy@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002fb5c`
- `0x1801b8e50`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18002fcb8`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff4a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff70`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff37`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff4a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002ff70`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002fe31`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002fe31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fd0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fd44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fd7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fe13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fd0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fd44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fd7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fe13`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::PackageFamilyPolicy,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::PackageFamilyPolicy *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::PackageFamilyPolicy *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::PackageFamilyPolicy *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Eu);
  v4 = v3 - 1;
  if ( v3 > 0x5E )
    v4 = 94;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.PackageFamilyPolicy>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x62u);
  v7 = v6 - 1;
  if ( v6 > 0x62 )
    v7 = 98;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.PackageFamilyPolicy>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x60u);
  v10 = v9 - 1;
  if ( v9 > 0x60 )
    v10 = 96;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.PackageFamilyPolicy>",
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
  v24 = GUID_da46ca2b_6126_4aae_a5f7_672a94ca776c;
  v25 = GUID_e7dafe36_3d1f_5365_b5f9_7c9fc22a0869;
  v26 = GUID_96362321_f8c2_591f_b3ef_32979d06a8bb;
  v27 = GUID_26a0ca21_7625_52f9_88e4_6f22468715c2;
  v28 = GUID_f24af43d_ba14_52a7_a845_0e89e78dbbc8;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18002FF76LL);
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
0x18002fcb8  mov     [rsp-8+arg_0], rbx
0x18002fcbd  mov     [rsp-8+arg_10], rdi
0x18002fcc2  push    rbp
0x18002fcc3  lea     rbp, [rsp-30h]
0x18002fcc8  sub     rsp, 130h
0x18002fccf  mov     rax, cs:__security_cookie
0x18002fcd6  xor     rax, rsp
0x18002fcd9  mov     [rbp+30h+var_10], rax
0x18002fcdd  mov     rdi, rdx
0x18002fce0  mov     [rbp+30h+string], 0
0x18002fce8  mov     ebx, 5Eh ; '^'
0x18002fced  mov     ecx, ebx; unsigned int
0x18002fcef  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002fcf4  lea     edx, [rax-1]
0x18002fcf7  cmp     eax, ebx
0x18002fcf9  cmova   edx, ebx; length
0x18002fcfc  lea     r9, [rbp+30h+string]; string
0x18002fd00  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002fd04  lea     rcx, aWindowsFoundat_159; "Windows.Foundation.Collections.IVector`"...
0x18002fd0b  call    cs:__imp_WindowsCreateStringReference
0x18002fd11  test    eax, eax
0x18002fd13  js      loc_18002FF2B
0x18002fd19  mov     [rbp+30h+var_58], 0
0x18002fd21  mov     ebx, 62h ; 'b'
0x18002fd26  mov     ecx, ebx; unsigned int
0x18002fd28  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002fd2d  lea     edx, [rax-1]
0x18002fd30  cmp     eax, ebx
0x18002fd32  cmova   edx, ebx; length
0x18002fd35  lea     r9, [rbp+30h+var_58]; string
0x18002fd39  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002fd3d  lea     rcx, aWindowsFoundat_77; "Windows.Foundation.Collections.IVectorV"...
0x18002fd44  call    cs:__imp_WindowsCreateStringReference
0x18002fd4a  test    eax, eax
0x18002fd4c  js      loc_18002FF3E
0x18002fd52  mov     [rbp+30h+var_38], 0
0x18002fd5a  mov     ebx, 60h ; '`'
0x18002fd5f  mov     ecx, ebx; unsigned int
0x18002fd61  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002fd66  lea     edx, [rax-1]
0x18002fd69  cmp     eax, ebx
0x18002fd6b  cmova   edx, ebx; length
0x18002fd6e  lea     r9, [rbp+30h+var_38]; string
0x18002fd72  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002fd76  lea     rcx, aWindowsFoundat_207; "Windows.Foundation.Collections.IIterato"...
0x18002fd7d  call    cs:__imp_WindowsCreateStringReference
0x18002fd83  test    eax, eax
0x18002fd85  js      loc_18002FF51
0x18002fd8b  mov     rax, [rbp+30h+string]
0x18002fd8f  mov     [rsp+130h+var_100], rax
0x18002fd94  mov     rax, [rbp+30h+var_58]
0x18002fd98  mov     [rsp+130h+var_F8], rax
0x18002fd9d  mov     rax, [rbp+30h+var_38]
0x18002fda1  mov     [rsp+130h+var_F0], rax
0x18002fda6  movups  xmm0, xmmword ptr cs:_GUID_da46ca2b_6126_4aae_a5f7_672a94ca776c.Data1
0x18002fdad  movdqu  [rsp+130h+var_E8], xmm0
0x18002fdb3  movups  xmm1, xmmword ptr cs:_GUID_e7dafe36_3d1f_5365_b5f9_7c9fc22a0869.Data1
0x18002fdba  movdqu  [rsp+130h+var_D8], xmm1
0x18002fdc0  movups  xmm0, xmmword ptr cs:_GUID_96362321_f8c2_591f_b3ef_32979d06a8bb.Data1
0x18002fdc7  movdqu  [rsp+130h+var_C8], xmm0
0x18002fdcd  movups  xmm1, xmmword ptr cs:_GUID_26a0ca21_7625_52f9_88e4_6f22468715c2.Data1
0x18002fdd4  movdqu  [rsp+130h+var_B8], xmm1
0x18002fdda  movups  xmm0, xmmword ptr cs:_GUID_f24af43d_ba14_52a7_a845_0e89e78dbbc8.Data1
0x18002fde1  movdqu  [rbp+30h+var_A8], xmm0
0x18002fde6  mov     [rsp+130h+var_110], 0
0x18002fdef  lea     rcx, [rsp+130h+var_110]
0x18002fdf4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fdf9  mov     [rbp+30h+var_18], 0
0x18002fe01  lea     r9, [rbp+30h+var_18]; string
0x18002fe05  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002fe09  lea     edx, [rbx-34h]; length
0x18002fe0c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002fe13  call    cs:__imp_WindowsCreateStringReference
0x18002fe19  test    eax, eax
0x18002fe1b  js      loc_18002FF64
0x18002fe21  lea     r8, [rsp+130h+var_110]
0x18002fe26  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002fe2d  mov     rcx, [rbp+30h+var_18]
0x18002fe31  call    cs:__imp_RoGetActivationFactory
0x18002fe37  mov     ebx, eax
0x18002fe39  test    eax, eax
0x18002fe3b  js      loc_18002FEC5
0x18002fe41  mov     [rsp+130h+var_108], 0
0x18002fe4a  mov     rbx, [rsp+130h+var_110]
0x18002fe4f  lea     rcx, [rsp+130h+var_108]
0x18002fe54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fe59  lea     r8, [rsp+130h+var_108]
0x18002fe5e  lea     rdx, [rsp+130h+var_100]
0x18002fe63  mov     rcx, rbx
0x18002fe66  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18002fe6b  mov     ebx, eax
0x18002fe6d  test    eax, eax
0x18002fe6f  js      short loc_18002FEE9
0x18002fe71  mov     rax, [rsp+130h+var_108]
0x18002fe76  mov     [rsp+130h+var_108], 0
0x18002fe7f  mov     [rdi], rax
0x18002fe82  mov     rcx, [rsp+130h+var_110]
0x18002fe87  test    rcx, rcx
0x18002fe8a  jz      short loc_18002FEA2
0x18002fe8c  mov     [rsp+130h+var_110], 0
0x18002fe95  mov     rax, [rcx]
0x18002fe98  mov     rax, [rax+10h]
0x18002fe9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fea1  nop
0x18002fea2  xor     eax, eax
0x18002fea4  mov     rcx, [rbp+30h+var_10]
0x18002fea8  xor     rcx, rsp; StackCookie
0x18002feab  call    __security_check_cookie
0x18002feb0  lea     r11, [rsp+130h+var_s0]
0x18002feb8  mov     rbx, [r11+10h]
0x18002febc  mov     rdi, [r11+20h]
0x18002fec0  mov     rsp, r11
0x18002fec3  pop     rbp
0x18002fec4  retn
0x18002fec5  mov     rcx, [rsp+130h+var_110]
0x18002feca  test    rcx, rcx
0x18002fecd  jz      short loc_18002FEE5
0x18002fecf  mov     [rsp+130h+var_110], 0
0x18002fed8  mov     rdx, [rcx]
0x18002fedb  mov     rax, [rdx+10h]
0x18002fedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fee4  nop
0x18002fee5  mov     eax, ebx
0x18002fee7  jmp     short loc_18002FEA4
0x18002fee9  mov     rcx, [rsp+130h+var_108]
0x18002feee  test    rcx, rcx
0x18002fef1  jz      short loc_18002FF09
0x18002fef3  mov     [rsp+130h+var_108], 0
0x18002fefc  mov     rdx, [rcx]
0x18002feff  mov     rax, [rdx+10h]
0x18002ff03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff08  nop
0x18002ff09  mov     rcx, [rsp+130h+var_110]
0x18002ff0e  test    rcx, rcx
0x18002ff11  jz      short loc_18002FF29
0x18002ff13  mov     [rsp+130h+var_110], 0
0x18002ff1c  mov     rax, [rcx]
0x18002ff1f  mov     rax, [rax+10h]
0x18002ff23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff28  nop
0x18002ff29  jmp     short loc_18002FEE5
0x18002ff2b  xor     r9d, r9d; lpArguments
0x18002ff2e  xor     r8d, r8d; nNumberOfArguments
0x18002ff31  lea     edx, [r9+1]; dwExceptionFlags
0x18002ff35  mov     ecx, eax; dwExceptionCode
0x18002ff37  call    cs:__imp_RaiseException
0x18002ff3d  int     3; Trap to Debugger
0x18002ff3e  xor     r9d, r9d; lpArguments
0x18002ff41  xor     r8d, r8d; nNumberOfArguments
0x18002ff44  lea     edx, [r9+1]; dwExceptionFlags
0x18002ff48  mov     ecx, eax; dwExceptionCode
0x18002ff4a  call    cs:__imp_RaiseException
0x18002ff50  int     3; Trap to Debugger
0x18002ff51  xor     r9d, r9d; lpArguments
0x18002ff54  xor     r8d, r8d; nNumberOfArguments
0x18002ff57  lea     edx, [r9+1]; dwExceptionFlags
0x18002ff5b  mov     ecx, eax; dwExceptionCode
0x18002ff5d  call    cs:__imp_RaiseException
0x18002ff63  int     3; Trap to Debugger
0x18002ff64  xor     r9d, r9d; lpArguments
0x18002ff67  xor     r8d, r8d; nNumberOfArguments
0x18002ff6a  lea     edx, [r9+1]; dwExceptionFlags
0x18002ff6e  mov     ecx, eax; dwExceptionCode
0x18002ff70  call    cs:__imp_RaiseException
```
