# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IAvailableNetwork,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAvailableNetwork *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAvailableNetwork *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAvailableNetwork *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAvailableNetwork *>> * *)

- ea: `0x180020988`
- end: `0x180020b86`
- name: `??$CreateExternalObjectVector@UIAvailableNetwork@UX@Networking@Windows@@V?$Vector@PEAUIAvailableNetwork@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIAvailableNetwork@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIAvailableNetwork@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIAvailableNetwork@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIAvailableNetwork@UX@Networking@Windows@@@6784@@1234@@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004980`

## callees

- `0x180016600`
- `0x18001d0a4`
- `0x180020988`
- `0x18002cd20`
- `0x1800519c4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020ab6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180020ab6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020acd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180020acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020aa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180020aa0`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IAvailableNetwork,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAvailableNetwork *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAvailableNetwork *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAvailableNetwork *>>>(
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
    L"Windows.Foundation.Collections.IVector`1<Windows.Networking.UX.IAvailableNetwork>",
    0x52u,
    0x51u);
  v22 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v21,
    L"Windows.Foundation.Collections.IVectorView`1<Windows.Networking.UX.IAvailableNetwork>",
    0x56u,
    0x55u);
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v23,
    L"Windows.Foundation.Collections.IIterator`1<Windows.Networking.UX.IAvailableNetwork>",
    0x54u,
    0x53u);
  v11[0] = v20;
  v11[1] = v22;
  v11[2] = v24;
  v12 = GUID_cefb4dcc_ee0b_4a2e_ba6e_b1e2789a964e;
  v13 = GUID_0a0f6e0b_65ae_5f3f_941b_3597508526e9;
  v14 = GUID_1baf803a_4275_5787_9cf2_a3c03737c8fc;
  v15 = GUID_fcbb8770_8eb0_5f9c_97e2_6989656ef9bd;
  v16 = GUID_610c2632_122a_5bad_bf77_c324a56d5bdd;
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
0x180020988  mov     [rsp-8+arg_0], rbx
0x18002098d  mov     [rsp-8+arg_10], rdi
0x180020992  push    rbp
0x180020993  lea     rbp, [rsp-30h]
0x180020998  sub     rsp, 130h
0x18002099f  mov     rax, cs:__security_cookie
0x1800209a6  xor     rax, rsp
0x1800209a9  mov     [rbp+30h+var_10], rax
0x1800209ad  mov     rdi, rdx
0x1800209b0  mov     [rbp+30h+var_58], 0
0x1800209b8  mov     r9d, 51h ; 'Q'; unsigned int
0x1800209be  lea     r8d, [r9+1]; unsigned int
0x1800209c2  lea     rdx, aWindowsFoundat_5; "Windows.Foundation.Collections.IVector`"...
0x1800209c9  lea     rcx, [rbp+30h+var_70]; hstringHeader
0x1800209cd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800209d2  mov     [rbp+30h+var_38], 0
0x1800209da  mov     r9d, 55h ; 'U'; unsigned int
0x1800209e0  lea     r8d, [r9+1]; unsigned int
0x1800209e4  lea     rdx, aWindowsFoundat_11; "Windows.Foundation.Collections.IVectorV"...
0x1800209eb  lea     rcx, [rbp+30h+var_50]; hstringHeader
0x1800209ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800209f4  mov     [rbp+30h+var_18], 0
0x1800209fc  mov     r9d, 53h ; 'S'; unsigned int
0x180020a02  lea     r8d, [r9+1]; unsigned int
0x180020a06  lea     rdx, aWindowsFoundat_7; "Windows.Foundation.Collections.IIterato"...
0x180020a0d  lea     rcx, [rbp+30h+var_30]; hstringHeader
0x180020a11  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180020a16  mov     rax, [rbp+30h+var_58]
0x180020a1a  mov     [rsp+130h+var_100], rax
0x180020a1f  mov     rax, [rbp+30h+var_38]
0x180020a23  mov     [rsp+130h+var_F8], rax
0x180020a28  mov     rax, [rbp+30h+var_18]
0x180020a2c  mov     [rsp+130h+var_F0], rax
0x180020a31  movups  xmm0, xmmword ptr cs:_GUID_cefb4dcc_ee0b_4a2e_ba6e_b1e2789a964e.Data1
0x180020a38  movdqu  [rsp+130h+var_E8], xmm0
0x180020a3e  movups  xmm1, xmmword ptr cs:_GUID_0a0f6e0b_65ae_5f3f_941b_3597508526e9.Data1
0x180020a45  movdqu  [rsp+130h+var_D8], xmm1
0x180020a4b  movups  xmm0, xmmword ptr cs:_GUID_1baf803a_4275_5787_9cf2_a3c03737c8fc.Data1
0x180020a52  movdqu  [rsp+130h+var_C8], xmm0
0x180020a58  movups  xmm1, xmmword ptr cs:_GUID_fcbb8770_8eb0_5f9c_97e2_6989656ef9bd.Data1
0x180020a5f  movdqu  [rsp+130h+var_B8], xmm1
0x180020a65  movups  xmm0, xmmword ptr cs:_GUID_610c2632_122a_5bad_bf77_c324a56d5bdd.Data1
0x180020a6c  movdqu  [rbp+30h+var_A8], xmm0
0x180020a71  mov     [rsp+130h+var_110], 0
0x180020a7a  lea     rcx, [rsp+130h+var_110]
0x180020a7f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020a84  mov     [rbp+30h+string], 0
0x180020a8c  lea     r9, [rbp+30h+string]; string
0x180020a90  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180020a94  mov     edx, 2Ch ; ','; length
0x180020a99  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180020aa0  call    cs:__imp_WindowsCreateStringReference
0x180020aa6  test    eax, eax
0x180020aa8  jns     short loc_180020ABD
0x180020aaa  xor     r9d, r9d; lpArguments
0x180020aad  xor     r8d, r8d; nNumberOfArguments
0x180020ab0  lea     edx, [r9+1]; dwExceptionFlags
0x180020ab4  mov     ecx, eax; dwExceptionCode
0x180020ab6  call    cs:__imp_RaiseException
0x180020abc  int     3; Trap to Debugger
0x180020abd  lea     r8, [rsp+130h+var_110]
0x180020ac2  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180020ac9  mov     rcx, [rbp+30h+string]
0x180020acd  call    cs:__imp_RoGetActivationFactory
0x180020ad3  mov     ebx, eax
0x180020ad5  test    eax, eax
0x180020ad7  jns     short loc_180020AFD
0x180020ad9  mov     rcx, [rsp+130h+var_110]
0x180020ade  test    rcx, rcx
0x180020ae1  jz      short loc_180020AF9
0x180020ae3  mov     [rsp+130h+var_110], 0
0x180020aec  mov     rdx, [rcx]
0x180020aef  mov     rax, [rdx+10h]
0x180020af3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020af8  nop
0x180020af9  mov     eax, ebx
0x180020afb  jmp     short loc_180020B65
0x180020afd  mov     [rsp+130h+var_108], 0
0x180020b06  mov     rbx, [rsp+130h+var_110]
0x180020b0b  lea     rcx, [rsp+130h+var_108]
0x180020b10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020b15  lea     r8, [rsp+130h+var_108]
0x180020b1a  lea     rdx, [rsp+130h+var_100]
0x180020b1f  mov     rcx, rbx
0x180020b22  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x180020b27  mov     ebx, eax
0x180020b29  lea     rcx, [rsp+130h+var_108]
0x180020b2e  test    eax, eax
0x180020b30  jns     short loc_180020B43
0x180020b32  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020b37  lea     rcx, [rsp+130h+var_110]
0x180020b3c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020b41  jmp     short loc_180020AF9
0x180020b43  mov     rax, [rsp+130h+var_108]
0x180020b48  mov     [rsp+130h+var_108], 0
0x180020b51  mov     [rdi], rax
0x180020b54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020b59  lea     rcx, [rsp+130h+var_110]
0x180020b5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180020b63  xor     eax, eax
0x180020b65  mov     rcx, [rbp+30h+var_10]
0x180020b69  xor     rcx, rsp; StackCookie
0x180020b6c  call    __security_check_cookie
0x180020b71  lea     r11, [rsp+130h+var_s0]
0x180020b79  mov     rbx, [r11+10h]
0x180020b7d  mov     rdi, [r11+20h]
0x180020b81  mov     rsp, r11
0x180020b84  pop     rbp
0x180020b85  retn
```
