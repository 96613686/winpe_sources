# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> * *)

- ea: `0x180014e1c`
- end: `0x180014fbe`
- name: `??$CreateExternalObjectVector@VUri@Foundation@Windows@@V?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@23@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@1234@@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800169b8`

## callees

- `0x180014db8`
- `0x180014e1c`
- `0x1800150e0`
- `0x180015244`
- `0x180017348`
- `0x18001f420`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014f31`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180014f31`

## string_xrefs

- `0x180014e78`: `Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>`
- `0x180014e5e`: `Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>`
- `0x180014e44`: `Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>>>(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v9[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v11; // [rsp+58h] [rbp-A8h]
  GUID v12; // [rsp+68h] [rbp-98h]
  GUID v13; // [rsp+78h] [rbp-88h]
  GUID v14; // [rsp+88h] [rbp-78h]
  GUID v15; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v17; // [rsp+C8h] [rbp-38h]
  _BYTE v18[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-18h]
  _BYTE v20[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v21; // [rsp+108h] [rbp+8h]
  _BYTE v22[24]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v23; // [rsp+128h] [rbp+28h]

  v9[0] = L"Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v18, v9);
  v9[0] = L"Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, v9);
  v9[0] = L"Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, v9);
  v10[0] = v19;
  v10[1] = v21;
  v10[2] = v23;
  v11 = GUID_9e365e57_48b2_4160_956f_c7385120bbfc;
  v12 = GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e;
  v13 = GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50;
  v14 = GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447;
  v15 = GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5;
  v8 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v8);
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.Detail.Vector",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v17, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v8);
  if ( ActivationFactory >= 0 )
  {
    v7 = 0;
    v4 = v8;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v7);
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v4, v10, &v7);
    if ( ActivationFactory >= 0 )
    {
      v5 = v7;
      v7 = 0;
      *a2 = v5;
      ActivationFactory = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v7);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v8);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x180014e1c  mov     [rsp-8+arg_0], rbx
0x180014e21  mov     [rsp-8+arg_10], rdi
0x180014e26  push    rbp
0x180014e27  lea     rbp, [rsp-40h]
0x180014e2c  sub     rsp, 140h
0x180014e33  mov     rax, cs:__security_cookie
0x180014e3a  xor     rax, rsp
0x180014e3d  mov     [rbp+40h+var_10], rax
0x180014e41  mov     rdi, rdx
0x180014e44  lea     rax, aWindowsFoundat; "Windows.Foundation.Collections.IVector`"...
0x180014e4b  mov     [rsp+140h+var_110], rax
0x180014e50  lea     rdx, [rsp+140h+var_110]
0x180014e55  lea     rcx, [rbp+40h+var_70]
0x180014e59  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180014e5e  lea     rax, aWindowsFoundat_1; "Windows.Foundation.Collections.IVectorV"...
0x180014e65  mov     [rsp+140h+var_110], rax
0x180014e6a  lea     rdx, [rsp+140h+var_110]
0x180014e6f  lea     rcx, [rbp+40h+var_50]
0x180014e73  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180014e78  lea     rax, aWindowsFoundat_0; "Windows.Foundation.Collections.IIterato"...
0x180014e7f  mov     [rsp+140h+var_110], rax
0x180014e84  lea     rdx, [rsp+140h+var_110]
0x180014e89  lea     rcx, [rbp+40h+var_30]
0x180014e8d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180014e92  mov     rax, [rbp+40h+var_58]
0x180014e96  mov     [rsp+140h+var_100], rax
0x180014e9b  mov     rax, [rbp+40h+var_38]
0x180014e9f  mov     [rsp+140h+var_F8], rax
0x180014ea4  mov     rax, [rbp+40h+var_18]
0x180014ea8  mov     [rsp+140h+var_F0], rax
0x180014ead  movups  xmm0, xmmword ptr cs:_GUID_9e365e57_48b2_4160_956f_c7385120bbfc.Data1
0x180014eb4  movdqu  [rsp+140h+var_E8], xmm0
0x180014eba  movups  xmm1, xmmword ptr cs:_GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e.Data1
0x180014ec1  movdqu  [rsp+140h+var_D8], xmm1
0x180014ec7  movups  xmm0, xmmword ptr cs:_GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50.Data1
0x180014ece  movdqu  [rsp+140h+var_C8], xmm0
0x180014ed4  movups  xmm1, xmmword ptr cs:_GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447.Data1
0x180014edb  movdqu  [rbp+40h+var_B8], xmm1
0x180014ee0  movups  xmm0, xmmword ptr cs:_GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5.Data1
0x180014ee7  movdqu  [rbp+40h+var_A8], xmm0
0x180014eec  mov     [rsp+140h+var_118], 0
0x180014ef5  lea     rcx, [rsp+140h+var_118]
0x180014efa  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180014eff  mov     [rbp+40h+var_78], 0
0x180014f07  mov     r9d, 2Ch ; ','; unsigned int
0x180014f0d  lea     r8d, [r9+1]; unsigned int
0x180014f11  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180014f18  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x180014f1c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180014f21  lea     r8, [rsp+140h+var_118]
0x180014f26  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180014f2d  mov     rcx, [rbp+40h+var_78]
0x180014f31  call    cs:__imp_RoGetActivationFactory
0x180014f38  nop     dword ptr [rax+rax+00h]
0x180014f3d  mov     ebx, eax
0x180014f3f  test    eax, eax
0x180014f41  js      short loc_180014F90
0x180014f43  mov     [rsp+140h+var_120], 0
0x180014f4c  mov     rbx, [rsp+140h+var_118]
0x180014f51  lea     rcx, [rsp+140h+var_120]
0x180014f56  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180014f5b  lea     r8, [rsp+140h+var_120]
0x180014f60  lea     rdx, [rsp+140h+var_100]
0x180014f65  mov     rcx, rbx
0x180014f68  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x180014f6d  mov     ebx, eax
0x180014f6f  test    eax, eax
0x180014f71  js      short loc_180014F86
0x180014f73  mov     rax, [rsp+140h+var_120]
0x180014f78  mov     [rsp+140h+var_120], 0
0x180014f81  mov     [rdi], rax
0x180014f84  xor     ebx, ebx
0x180014f86  lea     rcx, [rsp+140h+var_120]
0x180014f8b  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180014f90  lea     rcx, [rsp+140h+var_118]
0x180014f95  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x180014f9a  mov     eax, ebx
0x180014f9c  mov     rcx, [rbp+40h+var_10]
0x180014fa0  xor     rcx, rsp; StackCookie
0x180014fa3  call    __security_check_cookie
0x180014fa8  lea     r11, [rsp+140h+var_s0]
0x180014fb0  mov     rbx, [r11+10h]
0x180014fb4  mov     rdi, [r11+20h]
0x180014fb8  mov     rsp, r11
0x180014fbb  pop     rbp
0x180014fbc  retn
```
