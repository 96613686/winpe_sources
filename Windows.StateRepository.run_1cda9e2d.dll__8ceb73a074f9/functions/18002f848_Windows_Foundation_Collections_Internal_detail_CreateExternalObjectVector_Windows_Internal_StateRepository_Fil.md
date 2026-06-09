# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::FileTypeAssociation,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociation *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociation *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociation *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociation *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociation *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociation *>,0> * *)

- ea: `0x18002f848`
- end: `0x18002fb07`
- name: `??$CreateExternalObjectVector@VFileTypeAssociation@StateRepository@Internal@Windows@@V?$AgileVector@PEAVFileTypeAssociation@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFileTypeAssociation@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFileTypeAssociation@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVFileTypeAssociation@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVFileTypeAssociation@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVFileTypeAssociation@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002f700`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x18002f848`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fac7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fada`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002faed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fb00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fac7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fada`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002faed`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fb00`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f9c1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002f9c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f89b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f8d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f90d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f89b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f8d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f90d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002f9a3`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::FileTypeAssociation,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::FileTypeAssociation *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::FileTypeAssociation *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::FileTypeAssociation *>,0>>(
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
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.FileTypeAssociation>",
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
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.FileTypeAssociation>",
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
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.FileTypeAssociation>",
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
  v24 = GUID_4cc8fe6a_5976_4ece_ac32_62e2a5497f46;
  v25 = GUID_78df7f26_afd7_5cc1_9d62_ec831a44ac80;
  v26 = GUID_89bc3f49_f8d9_5103_ba13_de497e609167;
  v27 = GUID_eecbe8a8_4e02_5054_be0d_6dfd5db89a8c;
  v28 = GUID_0e371b49_375d_5b9b_9413_0697026cff94;
  v21 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v21);
  v36 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v35, &v36);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    JUMPOUT(0x18002FB06LL);
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
0x18002f848  mov     [rsp-8+arg_0], rbx
0x18002f84d  mov     [rsp-8+arg_10], rdi
0x18002f852  push    rbp
0x18002f853  lea     rbp, [rsp-30h]
0x18002f858  sub     rsp, 130h
0x18002f85f  mov     rax, cs:__security_cookie
0x18002f866  xor     rax, rsp
0x18002f869  mov     [rbp+30h+var_10], rax
0x18002f86d  mov     rdi, rdx
0x18002f870  mov     [rbp+30h+string], 0
0x18002f878  mov     ebx, 5Eh ; '^'
0x18002f87d  mov     ecx, ebx; unsigned int
0x18002f87f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f884  lea     edx, [rax-1]
0x18002f887  cmp     eax, ebx
0x18002f889  cmova   edx, ebx; length
0x18002f88c  lea     r9, [rbp+30h+string]; string
0x18002f890  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x18002f894  lea     rcx, aWindowsFoundat_67; "Windows.Foundation.Collections.IVector`"...
0x18002f89b  call    cs:__imp_WindowsCreateStringReference
0x18002f8a1  test    eax, eax
0x18002f8a3  js      loc_18002FABB
0x18002f8a9  mov     [rbp+30h+var_58], 0
0x18002f8b1  mov     ebx, 62h ; 'b'
0x18002f8b6  mov     ecx, ebx; unsigned int
0x18002f8b8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f8bd  lea     edx, [rax-1]
0x18002f8c0  cmp     eax, ebx
0x18002f8c2  cmova   edx, ebx; length
0x18002f8c5  lea     r9, [rbp+30h+var_58]; string
0x18002f8c9  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002f8cd  lea     rcx, aWindowsFoundat_21; "Windows.Foundation.Collections.IVectorV"...
0x18002f8d4  call    cs:__imp_WindowsCreateStringReference
0x18002f8da  test    eax, eax
0x18002f8dc  js      loc_18002FACE
0x18002f8e2  mov     [rbp+30h+var_38], 0
0x18002f8ea  mov     ebx, 60h ; '`'
0x18002f8ef  mov     ecx, ebx; unsigned int
0x18002f8f1  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x18002f8f6  lea     edx, [rax-1]
0x18002f8f9  cmp     eax, ebx
0x18002f8fb  cmova   edx, ebx; length
0x18002f8fe  lea     r9, [rbp+30h+var_38]; string
0x18002f902  lea     r8, [rbp+30h+var_50]; hstringHeader
0x18002f906  lea     rcx, aWindowsFoundat_194; "Windows.Foundation.Collections.IIterato"...
0x18002f90d  call    cs:__imp_WindowsCreateStringReference
0x18002f913  test    eax, eax
0x18002f915  js      loc_18002FAE1
0x18002f91b  mov     rax, [rbp+30h+string]
0x18002f91f  mov     [rsp+130h+var_100], rax
0x18002f924  mov     rax, [rbp+30h+var_58]
0x18002f928  mov     [rsp+130h+var_F8], rax
0x18002f92d  mov     rax, [rbp+30h+var_38]
0x18002f931  mov     [rsp+130h+var_F0], rax
0x18002f936  movups  xmm0, xmmword ptr cs:_GUID_4cc8fe6a_5976_4ece_ac32_62e2a5497f46.Data1
0x18002f93d  movdqu  [rsp+130h+var_E8], xmm0
0x18002f943  movups  xmm1, xmmword ptr cs:_GUID_78df7f26_afd7_5cc1_9d62_ec831a44ac80.Data1
0x18002f94a  movdqu  [rsp+130h+var_D8], xmm1
0x18002f950  movups  xmm0, xmmword ptr cs:_GUID_89bc3f49_f8d9_5103_ba13_de497e609167.Data1
0x18002f957  movdqu  [rsp+130h+var_C8], xmm0
0x18002f95d  movups  xmm1, xmmword ptr cs:_GUID_eecbe8a8_4e02_5054_be0d_6dfd5db89a8c.Data1
0x18002f964  movdqu  [rsp+130h+var_B8], xmm1
0x18002f96a  movups  xmm0, xmmword ptr cs:_GUID_0e371b49_375d_5b9b_9413_0697026cff94.Data1
0x18002f971  movdqu  [rbp+30h+var_A8], xmm0
0x18002f976  mov     [rsp+130h+var_110], 0
0x18002f97f  lea     rcx, [rsp+130h+var_110]
0x18002f984  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f989  mov     [rbp+30h+var_18], 0
0x18002f991  lea     r9, [rbp+30h+var_18]; string
0x18002f995  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002f999  lea     edx, [rbx-34h]; length
0x18002f99c  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x18002f9a3  call    cs:__imp_WindowsCreateStringReference
0x18002f9a9  test    eax, eax
0x18002f9ab  js      loc_18002FAF4
0x18002f9b1  lea     r8, [rsp+130h+var_110]
0x18002f9b6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x18002f9bd  mov     rcx, [rbp+30h+var_18]
0x18002f9c1  call    cs:__imp_RoGetActivationFactory
0x18002f9c7  mov     ebx, eax
0x18002f9c9  test    eax, eax
0x18002f9cb  js      loc_18002FA55
0x18002f9d1  mov     [rsp+130h+var_108], 0
0x18002f9da  mov     rbx, [rsp+130h+var_110]
0x18002f9df  lea     rcx, [rsp+130h+var_108]
0x18002f9e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002f9e9  lea     r8, [rsp+130h+var_108]
0x18002f9ee  lea     rdx, [rsp+130h+var_100]
0x18002f9f3  mov     rcx, rbx
0x18002f9f6  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x18002f9fb  mov     ebx, eax
0x18002f9fd  test    eax, eax
0x18002f9ff  js      short loc_18002FA79
0x18002fa01  mov     rax, [rsp+130h+var_108]
0x18002fa06  mov     [rsp+130h+var_108], 0
0x18002fa0f  mov     [rdi], rax
0x18002fa12  mov     rcx, [rsp+130h+var_110]
0x18002fa17  test    rcx, rcx
0x18002fa1a  jz      short loc_18002FA32
0x18002fa1c  mov     [rsp+130h+var_110], 0
0x18002fa25  mov     rax, [rcx]
0x18002fa28  mov     rax, [rax+10h]
0x18002fa2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa31  nop
0x18002fa32  xor     eax, eax
0x18002fa34  mov     rcx, [rbp+30h+var_10]
0x18002fa38  xor     rcx, rsp; StackCookie
0x18002fa3b  call    __security_check_cookie
0x18002fa40  lea     r11, [rsp+130h+var_s0]
0x18002fa48  mov     rbx, [r11+10h]
0x18002fa4c  mov     rdi, [r11+20h]
0x18002fa50  mov     rsp, r11
0x18002fa53  pop     rbp
0x18002fa54  retn
0x18002fa55  mov     rcx, [rsp+130h+var_110]
0x18002fa5a  test    rcx, rcx
0x18002fa5d  jz      short loc_18002FA75
0x18002fa5f  mov     [rsp+130h+var_110], 0
0x18002fa68  mov     rdx, [rcx]
0x18002fa6b  mov     rax, [rdx+10h]
0x18002fa6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa74  nop
0x18002fa75  mov     eax, ebx
0x18002fa77  jmp     short loc_18002FA34
0x18002fa79  mov     rcx, [rsp+130h+var_108]
0x18002fa7e  test    rcx, rcx
0x18002fa81  jz      short loc_18002FA99
0x18002fa83  mov     [rsp+130h+var_108], 0
0x18002fa8c  mov     rdx, [rcx]
0x18002fa8f  mov     rax, [rdx+10h]
0x18002fa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa98  nop
0x18002fa99  mov     rcx, [rsp+130h+var_110]
0x18002fa9e  test    rcx, rcx
0x18002faa1  jz      short loc_18002FAB9
0x18002faa3  mov     [rsp+130h+var_110], 0
0x18002faac  mov     rax, [rcx]
0x18002faaf  mov     rax, [rax+10h]
0x18002fab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fab8  nop
0x18002fab9  jmp     short loc_18002FA75
0x18002fabb  xor     r9d, r9d; lpArguments
0x18002fabe  xor     r8d, r8d; nNumberOfArguments
0x18002fac1  lea     edx, [r9+1]; dwExceptionFlags
0x18002fac5  mov     ecx, eax; dwExceptionCode
0x18002fac7  call    cs:__imp_RaiseException
0x18002facd  int     3; Trap to Debugger
0x18002face  xor     r9d, r9d; lpArguments
0x18002fad1  xor     r8d, r8d; nNumberOfArguments
0x18002fad4  lea     edx, [r9+1]; dwExceptionFlags
0x18002fad8  mov     ecx, eax; dwExceptionCode
0x18002fada  call    cs:__imp_RaiseException
0x18002fae0  int     3; Trap to Debugger
0x18002fae1  xor     r9d, r9d; lpArguments
0x18002fae4  xor     r8d, r8d; nNumberOfArguments
0x18002fae7  lea     edx, [r9+1]; dwExceptionFlags
0x18002faeb  mov     ecx, eax; dwExceptionCode
0x18002faed  call    cs:__imp_RaiseException
0x18002faf3  int     3; Trap to Debugger
0x18002faf4  xor     r9d, r9d; lpArguments
0x18002faf7  xor     r8d, r8d; nNumberOfArguments
0x18002fafa  lea     edx, [r9+1]; dwExceptionFlags
0x18002fafe  mov     ecx, eax; dwExceptionCode
0x18002fb00  call    cs:__imp_RaiseException
```
