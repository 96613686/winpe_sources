# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::User,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::User *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::User *>,0> * *)

- ea: `0x180067a80`
- end: `0x180067ced`
- name: `??$CreateExternalObjectVector@VUser@StateRepository@Internal@Windows@@V?$AgileVector@PEAVUser@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVUser@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVUser@StateRepository@Internal@Windows@@@3674@$0A@@3Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVUser@StateRepository@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVUser@StateRepository@Internal@Windows@@@3Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVUser@StateRepository@Internal@Windows@@@3674@$0A@@1234@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180067938`

## callees

- `0x180003e54`
- `0x180013ddc`
- `0x180067a80`
- `0x18018f650`
- `0x1801a5ba0`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067ae8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067b2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067b76`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067c1d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067ae8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067b2f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067b76`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180067c1d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180067c34`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180067c34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067ad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067c07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067ad3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067b61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180067c07`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Internal::StateRepository::User,Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::StateRepository::User *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::StateRepository::User *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::StateRepository::User *>,0>>(
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
  __int64 v18; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v21; // [rsp+48h] [rbp-B8h]
  GUID v22; // [rsp+58h] [rbp-A8h]
  GUID v23; // [rsp+68h] [rbp-98h]
  GUID v24; // [rsp+78h] [rbp-88h]
  GUID v25; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v28; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v29; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v30; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v31; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v32; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v33; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x4Fu);
  v4 = v3 - 1;
  if ( v3 > 0x4F )
    v4 = 79;
  v5 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Internal.StateRepository.User>",
         v4,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  v29 = 0;
  v6 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x53u);
  v7 = v6 - 1;
  if ( v6 > 0x53 )
    v7 = 83;
  v8 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Internal.StateRepository.User>",
         v7,
         &v28,
         &v29);
  if ( v8 < 0 )
  {
    RaiseException(v8, 1u, 0, 0);
    __debugbreak();
  }
  v31 = 0;
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(0x51u);
  v10 = v9 - 1;
  if ( v9 > 0x51 )
    v10 = 81;
  v11 = WindowsCreateStringReference(
          L"Windows.Foundation.Collections.IIterator`1<Windows.Internal.StateRepository.User>",
          v10,
          &v30,
          &v31);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  v20[0] = string;
  v20[1] = v29;
  v20[2] = v31;
  v21 = GUID_5232f8ea_49c7_4840_bfbb_66e785689e88;
  v22 = GUID_653d6637_30ce_5ee0_b430_168981bdf52f;
  v23 = GUID_714197c3_4234_5620_a053_b28bb2be0c59;
  v24 = GUID_d4984968_6523_5158_b859_3abcc9044c1c;
  v25 = GUID_c5d6c52e_df48_5307_b75f_49d8dc480c61;
  v18 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  v33 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v32, &v33);
  if ( v12 < 0 )
  {
    RaiseException(v12, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v18);
  if ( ActivationFactory < 0 )
  {
    v14 = v18;
    if ( v18 )
    {
      v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return (unsigned int)ActivationFactory;
  }
  v19 = 0;
  v16 = v18;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}(v16, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  v17 = v19;
  v19 = 0;
  *a2 = v17;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x180067a80  mov     [rsp-8+arg_0], rbx
0x180067a85  mov     [rsp-8+arg_10], rdi
0x180067a8a  push    rbp
0x180067a8b  lea     rbp, [rsp-30h]
0x180067a90  sub     rsp, 130h
0x180067a97  mov     rax, cs:__security_cookie
0x180067a9e  xor     rax, rsp
0x180067aa1  mov     [rbp+30h+var_10], rax
0x180067aa5  mov     rdi, rdx
0x180067aa8  mov     [rbp+30h+string], 0
0x180067ab0  mov     ebx, 4Fh ; 'O'
0x180067ab5  mov     ecx, ebx; unsigned int
0x180067ab7  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180067abc  lea     edx, [rax-1]
0x180067abf  cmp     eax, ebx
0x180067ac1  cmova   edx, ebx; length
0x180067ac4  lea     r9, [rbp+30h+string]; string
0x180067ac8  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180067acc  lea     rcx, aWindowsFoundat_169; "Windows.Foundation.Collections.IVector`"...
0x180067ad3  call    cs:__imp_WindowsCreateStringReference
0x180067ad9  test    eax, eax
0x180067adb  jns     short loc_180067AEF
0x180067add  xor     r9d, r9d; lpArguments
0x180067ae0  xor     r8d, r8d; nNumberOfArguments
0x180067ae3  lea     edx, [rbx-4Eh]; dwExceptionFlags
0x180067ae6  mov     ecx, eax; dwExceptionCode
0x180067ae8  call    cs:__imp_RaiseException
0x180067aee  int     3; Trap to Debugger
0x180067aef  mov     [rbp+30h+var_58], 0
0x180067af7  mov     ebx, 53h ; 'S'
0x180067afc  mov     ecx, ebx; unsigned int
0x180067afe  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180067b03  lea     edx, [rax-1]
0x180067b06  cmp     eax, ebx
0x180067b08  cmova   edx, ebx; length
0x180067b0b  lea     r9, [rbp+30h+var_58]; string
0x180067b0f  lea     r8, [rbp+30h+var_70]; hstringHeader
0x180067b13  lea     rcx, aWindowsFoundat_50; "Windows.Foundation.Collections.IVectorV"...
0x180067b1a  call    cs:__imp_WindowsCreateStringReference
0x180067b20  test    eax, eax
0x180067b22  jns     short loc_180067B36
0x180067b24  xor     r9d, r9d; lpArguments
0x180067b27  xor     r8d, r8d; nNumberOfArguments
0x180067b2a  lea     edx, [rbx-52h]; dwExceptionFlags
0x180067b2d  mov     ecx, eax; dwExceptionCode
0x180067b2f  call    cs:__imp_RaiseException
0x180067b35  int     3; Trap to Debugger
0x180067b36  mov     [rbp+30h+var_38], 0
0x180067b3e  mov     ebx, 51h ; 'Q'
0x180067b43  mov     ecx, ebx; unsigned int
0x180067b45  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180067b4a  lea     edx, [rax-1]
0x180067b4d  cmp     eax, ebx
0x180067b4f  cmova   edx, ebx; length
0x180067b52  lea     r9, [rbp+30h+var_38]; string
0x180067b56  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180067b5a  lea     rcx, aWindowsFoundat_49; "Windows.Foundation.Collections.IIterato"...
0x180067b61  call    cs:__imp_WindowsCreateStringReference
0x180067b67  test    eax, eax
0x180067b69  jns     short loc_180067B7D
0x180067b6b  xor     r9d, r9d; lpArguments
0x180067b6e  xor     r8d, r8d; nNumberOfArguments
0x180067b71  lea     edx, [rbx-50h]; dwExceptionFlags
0x180067b74  mov     ecx, eax; dwExceptionCode
0x180067b76  call    cs:__imp_RaiseException
0x180067b7c  int     3; Trap to Debugger
0x180067b7d  mov     rax, [rbp+30h+string]
0x180067b81  mov     [rsp+130h+var_100], rax
0x180067b86  mov     rax, [rbp+30h+var_58]
0x180067b8a  mov     [rsp+130h+var_F8], rax
0x180067b8f  mov     rax, [rbp+30h+var_38]
0x180067b93  mov     [rsp+130h+var_F0], rax
0x180067b98  movups  xmm0, xmmword ptr cs:_GUID_5232f8ea_49c7_4840_bfbb_66e785689e88.Data1
0x180067b9f  movdqu  [rsp+130h+var_E8], xmm0
0x180067ba5  movups  xmm1, xmmword ptr cs:_GUID_653d6637_30ce_5ee0_b430_168981bdf52f.Data1
0x180067bac  movdqu  [rsp+130h+var_D8], xmm1
0x180067bb2  movups  xmm0, xmmword ptr cs:_GUID_714197c3_4234_5620_a053_b28bb2be0c59.Data1
0x180067bb9  movdqu  [rsp+130h+var_C8], xmm0
0x180067bbf  movups  xmm1, xmmword ptr cs:_GUID_d4984968_6523_5158_b859_3abcc9044c1c.Data1
0x180067bc6  movdqu  [rsp+130h+var_B8], xmm1
0x180067bcc  movups  xmm0, xmmword ptr cs:_GUID_c5d6c52e_df48_5307_b75f_49d8dc480c61.Data1
0x180067bd3  movdqu  [rbp+30h+var_A8], xmm0
0x180067bd8  mov     [rsp+130h+var_110], 0
0x180067be1  lea     rcx, [rsp+130h+var_110]
0x180067be6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067beb  mov     [rbp+30h+var_18], 0
0x180067bf3  lea     r9, [rbp+30h+var_18]; string
0x180067bf7  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180067bfb  mov     edx, 2Ch ; ','; length
0x180067c00  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180067c07  call    cs:__imp_WindowsCreateStringReference
0x180067c0d  test    eax, eax
0x180067c0f  jns     short loc_180067C24
0x180067c11  xor     r9d, r9d; lpArguments
0x180067c14  xor     r8d, r8d; nNumberOfArguments
0x180067c17  lea     edx, [r9+1]; dwExceptionFlags
0x180067c1b  mov     ecx, eax; dwExceptionCode
0x180067c1d  call    cs:__imp_RaiseException
0x180067c23  int     3; Trap to Debugger
0x180067c24  lea     r8, [rsp+130h+var_110]
0x180067c29  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180067c30  mov     rcx, [rbp+30h+var_18]
0x180067c34  call    cs:__imp_RoGetActivationFactory
0x180067c3a  mov     ebx, eax
0x180067c3c  test    eax, eax
0x180067c3e  jns     short loc_180067C64
0x180067c40  mov     rcx, [rsp+130h+var_110]
0x180067c45  test    rcx, rcx
0x180067c48  jz      short loc_180067C60
0x180067c4a  mov     [rsp+130h+var_110], 0
0x180067c53  mov     rdx, [rcx]
0x180067c56  mov     rax, [rdx+10h]
0x180067c5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c5f  nop
0x180067c60  mov     eax, ebx
0x180067c62  jmp     short loc_180067CCC
0x180067c64  mov     [rsp+130h+var_108], 0
0x180067c6d  mov     rbx, [rsp+130h+var_110]
0x180067c72  lea     rcx, [rsp+130h+var_108]
0x180067c77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067c7c  lea     r8, [rsp+130h+var_108]
0x180067c81  lea     rdx, [rsp+130h+var_100]
0x180067c86  mov     rcx, rbx
0x180067c89  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPI@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{248,{flat}}
0x180067c8e  mov     ebx, eax
0x180067c90  lea     rcx, [rsp+130h+var_108]
0x180067c95  test    eax, eax
0x180067c97  jns     short loc_180067CAA
0x180067c99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067c9e  lea     rcx, [rsp+130h+var_110]
0x180067ca3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067ca8  jmp     short loc_180067C60
0x180067caa  mov     rax, [rsp+130h+var_108]
0x180067caf  mov     [rsp+130h+var_108], 0
0x180067cb8  mov     [rdi], rax
0x180067cbb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067cc0  lea     rcx, [rsp+130h+var_110]
0x180067cc5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180067cca  xor     eax, eax
0x180067ccc  mov     rcx, [rbp+30h+var_10]
0x180067cd0  xor     rcx, rsp; StackCookie
0x180067cd3  call    __security_check_cookie
0x180067cd8  lea     r11, [rsp+130h+var_s0]
0x180067ce0  mov     rbx, [r11+10h]
0x180067ce4  mov     rdi, [r11+20h]
0x180067ce8  mov     rsp, r11
0x180067ceb  pop     rbp
0x180067cec  retn
```
