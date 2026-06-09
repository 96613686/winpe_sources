# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IUXCategory,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IUXCategory *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IUXCategory *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IUXCategory *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IUXCategory *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IUXCategory *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IUXCategory *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IUXCategory *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IUXCategory *>> * *)

- ea: `0x180020b8c`
- end: `0x180020d8a`
- name: `??$CreateExternalObjectVector@UIUXCategory@UX@Networking@Windows@@V?$Vector@PEAUIUXCategory@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIUXCategory@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIUXCategory@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIUXCategory@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIUXCategory@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIUXCategory@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIUXCategory@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIUXCategory@UX@Networking@Windows@@@6784@@1234@@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015d80`

## callees

- `0x180016600`
- `0x18001d0a4`
- `0x180020b8c`
- `0x18002cd20`
- `0x1800519c4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020cba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020cba`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020cd1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020cd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020ca4`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IUXCategory,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IUXCategory *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IUXCategory *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IUXCategory *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IUXCategory *>>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  int ActivationFactory; // ebx
  __int64 v5; // rcx
  __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v10; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v11[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v12; // [rsp+48h] [rbp-B8h]
  GUID v13; // [rsp+58h] [rbp-A8h]
  GUID v14; // [rsp+68h] [rbp-98h]
  GUID v15; // [rsp+78h] [rbp-88h]
  GUID v16; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v19; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-28h]
  HSTRING_HEADER v21; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v22; // [rsp+F8h] [rbp-8h]
  HSTRING_HEADER v23; // [rsp+100h] [rbp+0h] BYREF
  __int64 v24; // [rsp+118h] [rbp+18h]

  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v19,
    L"Windows.Foundation.Collections.IVector`1<Windows.Networking.UX.IUXCategory>",
    0x4Cu,
    0x4Bu);
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v21,
    L"Windows.Foundation.Collections.IVectorView`1<Windows.Networking.UX.IUXCategory>",
    0x50u,
    0x4Fu);
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v23,
    L"Windows.Foundation.Collections.IIterator`1<Windows.Networking.UX.IUXCategory>",
    0x4Eu,
    0x4Du);
  v11[0] = v20;
  v11[1] = v22;
  v11[2] = v24;
  v12 = GUID_91e76f1b_9eef_4592_b3aa_630094a37d41;
  v13 = GUID_6feabef1_e897_57d2_a8d2_bb3ec1b38f5d;
  v14 = GUID_0e30d042_3085_5f5c_a317_548444eca130;
  v15 = GUID_9405cadf_64e0_55bc_8e19_07a783f3000d;
  v16 = GUID_a2a54126_8ea1_5732_ac3d_2e4928583b07;
  v9 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    RaiseException(v3, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v9);
  if ( ActivationFactory < 0 )
  {
    v5 = v9;
    if ( v9 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    return (unsigned int)ActivationFactory;
  }
  v10 = 0;
  v7 = v9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v7, v11, &v10);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    return (unsigned int)ActivationFactory;
  }
  v8 = v10;
  v10 = 0;
  *a2 = v8;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  return 0;
}

```

## disassembly

```asm
0x180020b8c  mov     [rsp-8+arg_0], rbx
0x180020b91  mov     [rsp-8+arg_10], rdi
0x180020b96  push    rbp
0x180020b97  lea     rbp, [rsp-30h]
0x180020b9c  sub     rsp, 130h
0x180020ba3  mov     rax, cs:__security_cookie
0x180020baa  xor     rax, rsp
0x180020bad  mov     [rbp+30h+var_10], rax
0x180020bb1  mov     rdi, rdx
0x180020bb4  mov     [rbp+30h+var_58], 0
0x180020bbc  mov     r9d, 4Bh ; 'K'; unsigned int
0x180020bc2  lea     r8d, [r9+1]; unsigned int
0x180020bc6  lea     rdx, aWindowsFoundat_8; "Windows.Foundation.Collections.IVector`"...
0x180020bcd  lea     rcx, [rbp+30h+var_70]; hstringHeader
0x180020bd1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020bd6  mov     [rbp+30h+var_38], 0
0x180020bde  mov     r9d, 4Fh ; 'O'; unsigned int
0x180020be4  lea     r8d, [r9+1]; unsigned int
0x180020be8  lea     rdx, aWindowsFoundat_4; "Windows.Foundation.Collections.IVectorV"...
0x180020bef  lea     rcx, [rbp+30h+var_50]; hstringHeader
0x180020bf3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020bf8  mov     [rbp+30h+var_18], 0
0x180020c00  mov     r9d, 4Dh ; 'M'; unsigned int
0x180020c06  lea     r8d, [r9+1]; unsigned int
0x180020c0a  lea     rdx, aWindowsFoundat_10; "Windows.Foundation.Collections.IIterato"...
0x180020c11  lea     rcx, [rbp+30h+var_30]; hstringHeader
0x180020c15  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020c1a  mov     rax, [rbp+30h+var_58]
0x180020c1e  mov     [rsp+130h+var_100], rax
0x180020c23  mov     rax, [rbp+30h+var_38]
0x180020c27  mov     [rsp+130h+var_F8], rax
0x180020c2c  mov     rax, [rbp+30h+var_18]
0x180020c30  mov     [rsp+130h+var_F0], rax
0x180020c35  movups  xmm0, xmmword ptr cs:_GUID_91e76f1b_9eef_4592_b3aa_630094a37d41.Data1
0x180020c3c  movdqu  [rsp+130h+var_E8], xmm0
0x180020c42  movups  xmm1, xmmword ptr cs:_GUID_6feabef1_e897_57d2_a8d2_bb3ec1b38f5d.Data1
0x180020c49  movdqu  [rsp+130h+var_D8], xmm1
0x180020c4f  movups  xmm0, xmmword ptr cs:_GUID_0e30d042_3085_5f5c_a317_548444eca130.Data1
0x180020c56  movdqu  [rsp+130h+var_C8], xmm0
0x180020c5c  movups  xmm1, xmmword ptr cs:_GUID_9405cadf_64e0_55bc_8e19_07a783f3000d.Data1
0x180020c63  movdqu  [rsp+130h+var_B8], xmm1
0x180020c69  movups  xmm0, xmmword ptr cs:_GUID_a2a54126_8ea1_5732_ac3d_2e4928583b07.Data1
0x180020c70  movdqu  [rbp+30h+var_A8], xmm0
0x180020c75  mov     [rsp+130h+var_110], 0
0x180020c7e  lea     rcx, [rsp+130h+var_110]
0x180020c83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020c88  mov     [rbp+30h+string], 0
0x180020c90  lea     r9, [rbp+30h+string]; string
0x180020c94  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180020c98  mov     edx, 2Ch ; ','; length
0x180020c9d  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180020ca4  call    cs:__imp_WindowsCreateStringReference
0x180020caa  test    eax, eax
0x180020cac  jns     short loc_180020CC1
0x180020cae  xor     r9d, r9d; lpArguments
0x180020cb1  xor     r8d, r8d; nNumberOfArguments
0x180020cb4  lea     edx, [r9+1]; dwExceptionFlags
0x180020cb8  mov     ecx, eax; dwExceptionCode
0x180020cba  call    cs:__imp_RaiseException
0x180020cc0  int     3; Trap to Debugger
0x180020cc1  lea     r8, [rsp+130h+var_110]
0x180020cc6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180020ccd  mov     rcx, [rbp+30h+string]
0x180020cd1  call    cs:__imp_RoGetActivationFactory
0x180020cd7  mov     ebx, eax
0x180020cd9  test    eax, eax
0x180020cdb  jns     short loc_180020D01
0x180020cdd  mov     rcx, [rsp+130h+var_110]
0x180020ce2  test    rcx, rcx
0x180020ce5  jz      short loc_180020CFD
0x180020ce7  mov     [rsp+130h+var_110], 0
0x180020cf0  mov     rdx, [rcx]
0x180020cf3  mov     rax, [rdx+10h]
0x180020cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cfc  nop
0x180020cfd  mov     eax, ebx
0x180020cff  jmp     short loc_180020D69
0x180020d01  mov     [rsp+130h+var_108], 0
0x180020d0a  mov     rbx, [rsp+130h+var_110]
0x180020d0f  lea     rcx, [rsp+130h+var_108]
0x180020d14  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020d19  lea     r8, [rsp+130h+var_108]
0x180020d1e  lea     rdx, [rsp+130h+var_100]
0x180020d23  mov     rcx, rbx
0x180020d26  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x180020d2b  mov     ebx, eax
0x180020d2d  lea     rcx, [rsp+130h+var_108]
0x180020d32  test    eax, eax
0x180020d34  jns     short loc_180020D47
0x180020d36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020d3b  lea     rcx, [rsp+130h+var_110]
0x180020d40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020d45  jmp     short loc_180020CFD
0x180020d47  mov     rax, [rsp+130h+var_108]
0x180020d4c  mov     [rsp+130h+var_108], 0
0x180020d55  mov     [rdi], rax
0x180020d58  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020d5d  lea     rcx, [rsp+130h+var_110]
0x180020d62  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020d67  xor     eax, eax
0x180020d69  mov     rcx, [rbp+30h+var_10]
0x180020d6d  xor     rcx, rsp; StackCookie
0x180020d70  call    __security_check_cookie
0x180020d75  lea     r11, [rsp+130h+var_s0]
0x180020d7d  mov     rbx, [r11+10h]
0x180020d81  mov     rdi, [r11+20h]
0x180020d85  mov     rsp, r11
0x180020d88  pop     rbp
0x180020d89  retn
```
