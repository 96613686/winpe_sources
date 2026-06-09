# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Application,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Application *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Application *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Application *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Application *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Application *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Application *>,0> * *)

- ea: `0x18002ef7c`
- end: `0x18002f23b`
- name: `??$CreateExternalObjectVector@VApplication@StateRepository@Internal@Windows@@V?$AgileVector@PEAVApplication@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVApplication@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplication@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVApplication@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVApplication@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVApplication@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002ee24`
- `0x1800b4cfc`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18002ef7c`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f1fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f20e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f221`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f234`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f1fb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f20e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f221`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f234`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f0f5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f0f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002efcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f0d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002efcf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f008`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f0d7`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::Application,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::Application *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::Application *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::Application *>,0>>(
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
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x56u);
  v4 = v3 - 1;
  if ( v3 > 0x56 )
    v4 = 86;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.Application>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v32 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x5Au);
  v7 = v6 - 1;
  if ( v6 > 0x5A )
    v7 = 90;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.Application>",
         v7,
         &v31,
         &v32);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v34 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x58u);
  v10 = v9 - 1;
  if ( v9 > 0x58 )
    v10 = 88;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.Application>",
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
  v24 = GUID_1de40eaa_987d_4cf8_b107_4c23a0f6160a;
  v25 = GUID_b372eafd_7eb6_567c_a156_8ce7516f139a;
  v26 = GUID_511fa560_2c85_5436_a7f0_fa2c4e577a3f;
  v27 = GUID_52384ae4_02b2_581d_b976_80c8813cef40;
  v28 = GUID_0625471c_4d39_57df_82fd_490d1041e209;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18002F23ALL);
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
0x18002ef7c  mov     [rsp-8+arg_0], rbx
0x18002ef81  mov     [rsp-8+arg_10], rdi
0x18002ef86  push    rbp
0x18002ef87  lea     rbp, [rsp-30h]
0x18002ef8c  sub     rsp, 130h
0x18002ef93  mov     rax, cs:__security_cookie
0x18002ef9a  xor     rax, rsp
0x18002ef9d  mov     [rbp+30h+var_10], rax
0x18002efa1  mov     rdi, rdx
0x18002efa4  mov     [rbp+30h+string], 0
0x18002efac  mov     ebx, 56h ; 'V'
0x18002efb1  mov     ecx, ebx; unsigned int
0x18002efb3  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002efb8  lea     edx, [rax-1]
0x18002efbb  cmp     eax, ebx
0x18002efbd  cmova   edx, ebx; length
0x18002efc0  lea     r9, [rbp+30h+string]; string
0x18002efc4  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002efc8  lea     rcx, aWindowsFoundat_128; "Windows.Foundation.Collections.IVector`"...
0x18002efcf  call    cs:__imp_WindowsCreateStringReference
0x18002efd5  test    eax, eax
0x18002efd7  js      loc_18002F1EF
0x18002efdd  mov     [rbp+30h+var_58], 0
0x18002efe5  mov     ebx, 5Ah ; 'Z'
0x18002efea  mov     ecx, ebx; unsigned int
0x18002efec  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002eff1  lea     edx, [rax-1]
0x18002eff4  cmp     eax, ebx
0x18002eff6  cmova   edx, ebx; length
0x18002eff9  lea     r9, [rbp+30h+var_58]; string
0x18002effd  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002f001  lea     rcx, aWindowsFoundat_193; "Windows.Foundation.Collections.IVectorV"...
0x18002f008  call    cs:__imp_WindowsCreateStringReference
0x18002f00e  test    eax, eax
0x18002f010  js      loc_18002F202
0x18002f016  mov     [rbp+30h+var_38], 0
0x18002f01e  mov     ebx, 58h ; 'X'
0x18002f023  mov     ecx, ebx; unsigned int
0x18002f025  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f02a  lea     edx, [rax-1]
0x18002f02d  cmp     eax, ebx
0x18002f02f  cmova   edx, ebx; length
0x18002f032  lea     r9, [rbp+30h+var_38]; string
0x18002f036  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002f03a  lea     rcx, aWindowsFoundat_224; "Windows.Foundation.Collections.IIterato"...
0x18002f041  call    cs:__imp_WindowsCreateStringReference
0x18002f047  test    eax, eax
0x18002f049  js      loc_18002F215
0x18002f04f  mov     rax, [rbp+30h+string]
0x18002f053  mov     [rsp+130h+var_100], rax
0x18002f058  mov     rax, [rbp+30h+var_58]
0x18002f05c  mov     [rsp+130h+var_F8], rax
0x18002f061  mov     rax, [rbp+30h+var_38]
0x18002f065  mov     [rsp+130h+var_F0], rax
0x18002f06a  movups  xmm0, xmmword ptr cs:_GUID_1de40eaa_987d_4cf8_b107_4c23a0f6160a.Data1
0x18002f071  movdqu  [rsp+130h+var_E8], xmm0
0x18002f077  movups  xmm1, xmmword ptr cs:_GUID_b372eafd_7eb6_567c_a156_8ce7516f139a.Data1
0x18002f07e  movdqu  [rsp+130h+var_D8], xmm1
0x18002f084  movups  xmm0, xmmword ptr cs:_GUID_511fa560_2c85_5436_a7f0_fa2c4e577a3f.Data1
0x18002f08b  movdqu  [rsp+130h+var_C8], xmm0
0x18002f091  movups  xmm1, xmmword ptr cs:_GUID_52384ae4_02b2_581d_b976_80c8813cef40.Data1
0x18002f098  movdqu  [rsp+130h+var_B8], xmm1
0x18002f09e  movups  xmm0, xmmword ptr cs:_GUID_0625471c_4d39_57df_82fd_490d1041e209.Data1
0x18002f0a5  movdqu  [rbp+30h+var_A8], xmm0
0x18002f0aa  mov     [rsp+130h+var_110], 0
0x18002f0b3  lea     rcx, [rsp+130h+var_110]
0x18002f0b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f0bd  mov     [rbp+30h+var_18], 0
0x18002f0c5  lea     r9, [rbp+30h+var_18]; string
0x18002f0c9  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002f0cd  lea     edx, [rbx-2Ch]; length
0x18002f0d0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002f0d7  call    cs:__imp_WindowsCreateStringReference
0x18002f0dd  test    eax, eax
0x18002f0df  js      loc_18002F228
0x18002f0e5  lea     r8, [rsp+130h+var_110]
0x18002f0ea  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002f0f1  mov     rcx, [rbp+30h+var_18]
0x18002f0f5  call    cs:__imp_RoGetActivationFactory
0x18002f0fb  mov     ebx, eax
0x18002f0fd  test    eax, eax
0x18002f0ff  js      loc_18002F189
0x18002f105  mov     [rsp+130h+var_108], 0
0x18002f10e  mov     rbx, [rsp+130h+var_110]
0x18002f113  lea     rcx, [rsp+130h+var_108]
0x18002f118  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f11d  lea     r8, [rsp+130h+var_108]
0x18002f122  lea     rdx, [rsp+130h+var_100]
0x18002f127  mov     rcx, rbx
0x18002f12a  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18002f12f  mov     ebx, eax
0x18002f131  test    eax, eax
0x18002f133  js      short loc_18002F1AD
0x18002f135  mov     rax, [rsp+130h+var_108]
0x18002f13a  mov     [rsp+130h+var_108], 0
0x18002f143  mov     [rdi], rax
0x18002f146  mov     rcx, [rsp+130h+var_110]
0x18002f14b  test    rcx, rcx
0x18002f14e  jz      short loc_18002F166
0x18002f150  mov     [rsp+130h+var_110], 0
0x18002f159  mov     rax, [rcx]
0x18002f15c  mov     rax, [rax+10h]
0x18002f160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f165  nop
0x18002f166  xor     eax, eax
0x18002f168  mov     rcx, [rbp+30h+var_10]
0x18002f16c  xor     rcx, rsp; StackCookie
0x18002f16f  call    __security_check_cookie
0x18002f174  lea     r11, [rsp+130h+var_s0]
0x18002f17c  mov     rbx, [r11+10h]
0x18002f180  mov     rdi, [r11+20h]
0x18002f184  mov     rsp, r11
0x18002f187  pop     rbp
0x18002f188  retn
0x18002f189  mov     rcx, [rsp+130h+var_110]
0x18002f18e  test    rcx, rcx
0x18002f191  jz      short loc_18002F1A9
0x18002f193  mov     [rsp+130h+var_110], 0
0x18002f19c  mov     rdx, [rcx]
0x18002f19f  mov     rax, [rdx+10h]
0x18002f1a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1a8  nop
0x18002f1a9  mov     eax, ebx
0x18002f1ab  jmp     short loc_18002F168
0x18002f1ad  mov     rcx, [rsp+130h+var_108]
0x18002f1b2  test    rcx, rcx
0x18002f1b5  jz      short loc_18002F1CD
0x18002f1b7  mov     [rsp+130h+var_108], 0
0x18002f1c0  mov     rdx, [rcx]
0x18002f1c3  mov     rax, [rdx+10h]
0x18002f1c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1cc  nop
0x18002f1cd  mov     rcx, [rsp+130h+var_110]
0x18002f1d2  test    rcx, rcx
0x18002f1d5  jz      short loc_18002F1ED
0x18002f1d7  mov     [rsp+130h+var_110], 0
0x18002f1e0  mov     rax, [rcx]
0x18002f1e3  mov     rax, [rax+10h]
0x18002f1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f1ec  nop
0x18002f1ed  jmp     short loc_18002F1A9
0x18002f1ef  xor     r9d, r9d; lpArguments
0x18002f1f2  xor     r8d, r8d; nNumberOfArguments
0x18002f1f5  lea     edx, [r9+1]; dwExceptionFlags
0x18002f1f9  mov     ecx, eax; dwExceptionCode
0x18002f1fb  call    cs:__imp_RaiseException
0x18002f201  int     3; Trap to Debugger
0x18002f202  xor     r9d, r9d; lpArguments
0x18002f205  xor     r8d, r8d; nNumberOfArguments
0x18002f208  lea     edx, [r9+1]; dwExceptionFlags
0x18002f20c  mov     ecx, eax; dwExceptionCode
0x18002f20e  call    cs:__imp_RaiseException
0x18002f214  int     3; Trap to Debugger
0x18002f215  xor     r9d, r9d; lpArguments
0x18002f218  xor     r8d, r8d; nNumberOfArguments
0x18002f21b  lea     edx, [r9+1]; dwExceptionFlags
0x18002f21f  mov     ecx, eax; dwExceptionCode
0x18002f221  call    cs:__imp_RaiseException
0x18002f227  int     3; Trap to Debugger
0x18002f228  xor     r9d, r9d; lpArguments
0x18002f22b  xor     r8d, r8d; nNumberOfArguments
0x18002f22e  lea     edx, [r9+1]; dwExceptionFlags
0x18002f232  mov     ecx, eax; dwExceptionCode
0x18002f234  call    cs:__imp_RaiseException
```
