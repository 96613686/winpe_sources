# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>> * *)

- ea: `0x1800294f8`
- end: `0x180029702`
- name: `??$CreateExternalObjectVector@VUri@Foundation@Windows@@V?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@Internal@Collections@23@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVUri@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAVUri@Foundation@Windows@@@Internal@Collections@23@U?$DefaultLifetimeTraits@PEAVUri@Foundation@Windows@@@5623@U?$DefaultVectorOptions@PEAVUri@Foundation@Windows@@@5623@@1234@@Z`
- size: `522`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002ace0`

## callees

- `0x180016288`
- `0x18002535c`
- `0x1800294f8`
- `0x18002989c`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029646`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180029646`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002953c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002953c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029566`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029590`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180029628`

## string_xrefs

- `0x180029535`: `Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>`
- `0x18002955f`: `Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>`
- `0x180029589`: `Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Foundation::Uri,Windows::Foundation::Collections::Internal::Vector<Windows::Foundation::Uri *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::Uri *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Foundation::Uri *>>>(
        __int64 a1,
        _QWORD *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  HRESULT v6; // eax
  int v7; // edx
  unsigned int v8; // r8d
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  HRESULT v12; // eax
  int v13; // edx
  unsigned int v14; // r8d
  int ActivationFactory; // ebx
  __int64 v17; // rcx
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
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.Foundation.Uri>",
         0x40u,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    __debugbreak();
  }
  v29 = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.Foundation.Uri>",
         0x44u,
         &v28,
         &v29);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  v31 = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.Foundation.Uri>",
         0x42u,
         &v30,
         &v31);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x180029701LL);
  }
  v20[0] = string;
  v21 = GUID_9e365e57_48b2_4160_956f_c7385120bbfc;
  v20[1] = v29;
  v22 = GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e;
  v20[2] = v31;
  v18 = 0;
  v23 = GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50;
  v24 = GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447;
  v25 = GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v18);
  v33 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v32, &v33);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v33, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v18);
  if ( ActivationFactory < 0 )
    goto LABEL_6;
  v19 = 0;
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v18, v20, &v19);
  if ( ActivationFactory < 0 )
  {
    v17 = v19;
    if ( v19 )
    {
      v19 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
LABEL_6:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v18);
    return (unsigned int)ActivationFactory;
  }
  *a2 = v19;
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(&v18);
  return 0;
}

```

## disassembly

```asm
0x1800294f8  mov     [rsp-8+arg_0], rbx
0x1800294fd  mov     [rsp-8+arg_10], rdi
0x180029502  push    rbp
0x180029503  lea     rbp, [rsp-30h]
0x180029508  sub     rsp, 130h
0x18002950f  mov     rax, cs:__security_cookie
0x180029516  xor     rax, rsp
0x180029519  mov     [rbp+30h+var_10], rax
0x18002951d  mov     rdi, rdx
0x180029520  mov     [rbp+30h+string], 0
0x180029528  mov     edx, 40h ; '@'; length
0x18002952d  lea     r9, [rbp+30h+string]; string
0x180029531  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180029535  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x18002953c  call    cs:__imp_WindowsCreateStringReference
0x180029542  test    eax, eax
0x180029544  js      loc_1800296EA
0x18002954a  lea     r9, [rbp+30h+var_58]; string
0x18002954e  mov     [rbp+30h+var_58], 0
0x180029556  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18002955a  mov     edx, 44h ; 'D'; length
0x18002955f  lea     rcx, aWindowsFoundat_1; "Windows.Foundation.Collections.IVectorV"...
0x180029566  call    cs:__imp_WindowsCreateStringReference
0x18002956c  test    eax, eax
0x18002956e  js      loc_1800296F2
0x180029574  lea     r9, [rbp+30h+var_38]; string
0x180029578  mov     [rbp+30h+var_38], 0
0x180029580  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180029584  mov     edx, 42h ; 'B'; length
0x180029589  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IIterato"...
0x180029590  call    cs:__imp_WindowsCreateStringReference
0x180029596  test    eax, eax
0x180029598  js      loc_1800296FA
0x18002959e  movups  xmm0, xmmword ptr cs:_GUID_9e365e57_48b2_4160_956f_c7385120bbfc.Data1
0x1800295a5  mov     rax, [rbp+30h+string]
0x1800295a9  lea     rcx, [rsp+130h+var_110]
0x1800295ae  movups  xmm1, xmmword ptr cs:_GUID_0d82bd8d_fe62_5d67_a7b9_7886dd75bc4e.Data1
0x1800295b5  mov     [rsp+130h+var_100], rax
0x1800295ba  mov     rax, [rbp+30h+var_58]
0x1800295be  movdqu  [rsp+130h+var_E8], xmm0
0x1800295c4  mov     [rsp+130h+var_F8], rax
0x1800295c9  movups  xmm0, xmmword ptr cs:_GUID_4b8385bd_a2cd_5ff1_bf74_7ea580423e50.Data1
0x1800295d0  mov     rax, [rbp+30h+var_38]
0x1800295d4  movdqu  [rsp+130h+var_D8], xmm1
0x1800295da  mov     [rsp+130h+var_F0], rax
0x1800295df  movups  xmm1, xmmword ptr cs:_GUID_b0d63b78_78ad_5e31_b6d8_e32a0e16c447.Data1
0x1800295e6  mov     [rsp+130h+var_110], 0
0x1800295ef  movdqu  [rsp+130h+var_C8], xmm0
0x1800295f5  movups  xmm0, xmmword ptr cs:_GUID_1c157d0f_5efe_5cec_bbd6_0c6ce9af07a5.Data1
0x1800295fc  movdqu  [rsp+130h+var_B8], xmm1
0x180029602  movdqu  [rbp+30h+var_A8], xmm0
0x180029607  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x18002960c  lea     r9, [rbp+30h+var_18]; string
0x180029610  mov     [rbp+30h+var_18], 0
0x180029618  lea     r8, [rbp+30h+var_30]; hstringHeader
0x18002961c  mov     edx, 2Ch ; ','; length
0x180029621  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180029628  call    cs:__imp_WindowsCreateStringReference
0x18002962e  test    eax, eax
0x180029630  js      loc_1800296E2
0x180029636  mov     rcx, [rbp+30h+var_18]
0x18002963a  lea     r8, [rsp+130h+var_110]
0x18002963f  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180029646  call    cs:__imp_RoGetActivationFactory
0x18002964c  mov     ebx, eax
0x18002964e  test    eax, eax
0x180029650  jns     short loc_180029660
0x180029652  lea     rcx, [rsp+130h+var_110]
0x180029657  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x18002965c  mov     eax, ebx
0x18002965e  jmp     short loc_1800296C1
0x180029660  mov     rcx, [rsp+130h+var_110]
0x180029665  lea     r8, [rsp+130h+var_108]
0x18002966a  lea     rdx, [rsp+130h+var_100]
0x18002966f  mov     [rsp+130h+var_108], 0
0x180029678  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x18002967d  mov     ebx, eax
0x18002967f  test    eax, eax
0x180029681  jns     short loc_1800296A4
0x180029683  mov     rcx, [rsp+130h+var_108]
0x180029688  test    rcx, rcx
0x18002968b  jz      short loc_180029652
0x18002968d  mov     [rsp+130h+var_108], 0
0x180029696  mov     rdx, [rcx]
0x180029699  mov     rax, [rdx+10h]
0x18002969d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296a2  jmp     short loc_180029652
0x1800296a4  mov     rax, [rsp+130h+var_108]
0x1800296a9  lea     rcx, [rsp+130h+var_110]
0x1800296ae  mov     [rdi], rax
0x1800296b1  mov     [rsp+130h+var_108], 0
0x1800296ba  call    ?InternalRelease@?$ComPtr@UIVectorStatics@Detail@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Detail::IVectorStatics>::InternalRelease(void)
0x1800296bf  xor     eax, eax
0x1800296c1  mov     rcx, [rbp+30h+var_10]
0x1800296c5  xor     rcx, rsp; StackCookie
0x1800296c8  call    __security_check_cookie
0x1800296cd  lea     r11, [rsp+130h+var_s0]
0x1800296d5  mov     rbx, [r11+10h]
0x1800296d9  mov     rdi, [r11+20h]
0x1800296dd  mov     rsp, r11
0x1800296e0  pop     rbp
0x1800296e1  retn
0x1800296e2  mov     ecx, eax; this
0x1800296e4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800296e9  int     3; Trap to Debugger
0x1800296ea  mov     ecx, eax; this
0x1800296ec  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800296f1  int     3; Trap to Debugger
0x1800296f2  mov     ecx, eax; this
0x1800296f4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800296f9  int     3; Trap to Debugger
0x1800296fa  mov     ecx, eax; this
0x1800296fc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
