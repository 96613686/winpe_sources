# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo,Windows::Foundation::Collections::Internal::Vector<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>> * *)

- ea: `0x1800068f8`
- end: `0x180006b48`
- name: `??$CreateExternalObjectVector@VPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@V?$Vector@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@U?$DefaultEqualityPredicate@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@7895@U?$DefaultVectorOptions@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@7895@@Internal@Collections@Foundation@5@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@U?$DefaultEqualityPredicate@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@7895@U?$DefaultVectorOptions@PEAVPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@7895@@1234@@Z`
- size: `592`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007de0`

## callees

- `0x1800016a0`
- `0x1800068f8`
- `0x180007124`
- `0x180008a10`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000693c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006990`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006a1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000693c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006966`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006990`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180006a1e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006a3c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180006a3c`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo,Windows::Foundation::Collections::Internal::Vector<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticTraceInfo *>>>(
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
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v24[3]; // [rsp+30h] [rbp-D0h] BYREF
  GUID v25; // [rsp+48h] [rbp-B8h]
  GUID v26; // [rsp+58h] [rbp-A8h]
  GUID v27; // [rsp+68h] [rbp-98h]
  GUID v28; // [rsp+78h] [rbp-88h]
  GUID v29; // [rsp+88h] [rbp-78h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER v32; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING v33; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER v34; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING v35; // [rsp+F8h] [rbp-8h] BYREF
  HSTRING_HEADER v36; // [rsp+100h] [rbp+0h] BYREF
  HSTRING v37; // [rsp+118h] [rbp+18h] BYREF

  string = 0;
  v3 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVector`1<Windows.System.Diagnostics.TraceReporting.PlatformDiagnosticTraceInfo>",
         0x6Fu,
         &hstringHeader,
         &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    __debugbreak();
  }
  v33 = 0;
  v6 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IVectorView`1<Windows.System.Diagnostics.TraceReporting.PlatformDiagnosticTraceInfo>",
         0x73u,
         &v32,
         &v33);
  if ( v6 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v6, v7, v8);
    __debugbreak();
  }
  v35 = 0;
  v9 = WindowsCreateStringReference(
         L"Windows.Foundation.Collections.IIterator`1<Windows.System.Diagnostics.TraceReporting.PlatformDiagnosticTraceInfo>",
         0x71u,
         &v34,
         &v35);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x180006B47LL);
  }
  v24[0] = string;
  v24[1] = v33;
  v24[2] = v35;
  v25 = GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2;
  v26 = GUID_73a40803_a6d3_5aa6_9830_efda7028f993;
  v27 = GUID_8f1b3397_4dc3_5b72_91fa_0fdc915d950c;
  v28 = GUID_ecb0c107_c97b_52fe_a5e6_a33e93493769;
  v29 = GUID_1af4598d_98bb_5e51_842b_cf691925b6c2;
  v22 = 0;
  v37 = 0;
  v12 = WindowsCreateStringReference(L"Windows.Foundation.Collections.Detail.Vector", 0x2Cu, &v36, &v37);
  if ( v12 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v12, v13, v14);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(v37, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v22);
  if ( ActivationFactory < 0 )
  {
    v16 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return (unsigned int)ActivationFactory;
  }
  v23 = 0;
  ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v22, v24, &v23);
  if ( ActivationFactory < 0 )
  {
    v18 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)ActivationFactory;
  }
  v20 = v23;
  v23 = 0;
  *a2 = v20;
  v21 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x1800068f8  mov     [rsp-8+arg_0], rbx
0x1800068fd  mov     [rsp-8+arg_10], rdi
0x180006902  push    rbp
0x180006903  lea     rbp, [rsp-30h]
0x180006908  sub     rsp, 130h
0x18000690f  mov     rax, cs:__security_cookie
0x180006916  xor     rax, rsp
0x180006919  mov     [rbp+30h+var_10], rax
0x18000691d  mov     rdi, rdx
0x180006920  mov     [rbp+30h+string], 0
0x180006928  lea     r9, [rbp+30h+string]; string
0x18000692c  lea     r8, [rbp+30h+hstringHeader]; hstringHeader
0x180006930  mov     edx, 6Fh ; 'o'; length
0x180006935  lea     rcx, sourceString; "Windows.Foundation.Collections.IVector`"...
0x18000693c  call    cs:__imp_WindowsCreateStringReference
0x180006942  test    eax, eax
0x180006944  js      loc_180006B30
0x18000694a  mov     [rbp+30h+var_58], 0
0x180006952  lea     r9, [rbp+30h+var_58]; string
0x180006956  lea     r8, [rbp+30h+var_70]; hstringHeader
0x18000695a  mov     edx, 73h ; 's'; length
0x18000695f  lea     rcx, aWindowsFoundat; "Windows.Foundation.Collections.IVectorV"...
0x180006966  call    cs:__imp_WindowsCreateStringReference
0x18000696c  test    eax, eax
0x18000696e  js      loc_180006B38
0x180006974  mov     [rbp+30h+var_38], 0
0x18000697c  lea     r9, [rbp+30h+var_38]; string
0x180006980  lea     r8, [rbp+30h+var_50]; hstringHeader
0x180006984  mov     edx, 71h ; 'q'; length
0x180006989  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IIterato"...
0x180006990  call    cs:__imp_WindowsCreateStringReference
0x180006996  test    eax, eax
0x180006998  js      loc_180006B40
0x18000699e  mov     rax, [rbp+30h+string]
0x1800069a2  mov     [rsp+130h+var_100], rax
0x1800069a7  mov     rax, [rbp+30h+var_58]
0x1800069ab  mov     [rsp+130h+var_F8], rax
0x1800069b0  mov     rax, [rbp+30h+var_38]
0x1800069b4  mov     [rsp+130h+var_F0], rax
0x1800069b9  movups  xmm0, xmmword ptr cs:_GUID_f870ed97_d597_4bf7_88dc_cf5c7dc2a1d2.Data1
0x1800069c0  movdqu  [rsp+130h+var_E8], xmm0
0x1800069c6  movups  xmm1, xmmword ptr cs:_GUID_73a40803_a6d3_5aa6_9830_efda7028f993.Data1
0x1800069cd  movdqu  [rsp+130h+var_D8], xmm1
0x1800069d3  movups  xmm0, xmmword ptr cs:_GUID_8f1b3397_4dc3_5b72_91fa_0fdc915d950c.Data1
0x1800069da  movdqu  [rsp+130h+var_C8], xmm0
0x1800069e0  movups  xmm1, xmmword ptr cs:_GUID_ecb0c107_c97b_52fe_a5e6_a33e93493769.Data1
0x1800069e7  movdqu  [rsp+130h+var_B8], xmm1
0x1800069ed  movups  xmm0, xmmword ptr cs:_GUID_1af4598d_98bb_5e51_842b_cf691925b6c2.Data1
0x1800069f4  movdqu  [rbp+30h+var_A8], xmm0
0x1800069f9  mov     [rsp+130h+var_110], 0
0x180006a02  mov     [rbp+30h+var_18], 0
0x180006a0a  lea     r9, [rbp+30h+var_18]; string
0x180006a0e  lea     r8, [rbp+30h+var_30]; hstringHeader
0x180006a12  mov     edx, 2Ch ; ','; length
0x180006a17  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x180006a1e  call    cs:__imp_WindowsCreateStringReference
0x180006a24  test    eax, eax
0x180006a26  js      loc_180006B28
0x180006a2c  lea     r8, [rsp+130h+var_110]
0x180006a31  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x180006a38  mov     rcx, [rbp+30h+var_18]
0x180006a3c  call    cs:__imp_RoGetActivationFactory
0x180006a42  mov     ebx, eax
0x180006a44  test    eax, eax
0x180006a46  jns     short loc_180006A6F
0x180006a48  mov     rcx, [rsp+130h+var_110]
0x180006a4d  test    rcx, rcx
0x180006a50  jz      short loc_180006A68
0x180006a52  mov     [rsp+130h+var_110], 0
0x180006a5b  mov     rdx, [rcx]
0x180006a5e  mov     rax, [rdx+10h]
0x180006a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a67  nop
0x180006a68  mov     eax, ebx
0x180006a6a  jmp     loc_180006B07
0x180006a6f  mov     [rsp+130h+var_108], 0
0x180006a78  lea     r8, [rsp+130h+var_108]
0x180006a7d  lea     rdx, [rsp+130h+var_100]
0x180006a82  mov     rcx, [rsp+130h+var_110]
0x180006a87  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x180006a8c  mov     ebx, eax
0x180006a8e  test    eax, eax
0x180006a90  jns     short loc_180006AD4
0x180006a92  mov     rcx, [rsp+130h+var_108]
0x180006a97  test    rcx, rcx
0x180006a9a  jz      short loc_180006AB2
0x180006a9c  mov     [rsp+130h+var_108], 0
0x180006aa5  mov     rdx, [rcx]
0x180006aa8  mov     rax, [rdx+10h]
0x180006aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab1  nop
0x180006ab2  mov     rcx, [rsp+130h+var_110]
0x180006ab7  test    rcx, rcx
0x180006aba  jz      short loc_180006AD2
0x180006abc  mov     [rsp+130h+var_110], 0
0x180006ac5  mov     rax, [rcx]
0x180006ac8  mov     rax, [rax+10h]
0x180006acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad1  nop
0x180006ad2  jmp     short loc_180006A68
0x180006ad4  mov     rax, [rsp+130h+var_108]
0x180006ad9  mov     [rsp+130h+var_108], 0
0x180006ae2  mov     [rdi], rax
0x180006ae5  mov     rcx, [rsp+130h+var_110]
0x180006aea  test    rcx, rcx
0x180006aed  jz      short loc_180006B05
0x180006aef  mov     [rsp+130h+var_110], 0
0x180006af8  mov     rax, [rcx]
0x180006afb  mov     rax, [rax+10h]
0x180006aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b04  nop
0x180006b05  xor     eax, eax
0x180006b07  mov     rcx, [rbp+30h+var_10]
0x180006b0b  xor     rcx, rsp; StackCookie
0x180006b0e  call    __security_check_cookie
0x180006b13  lea     r11, [rsp+130h+var_s0]
0x180006b1b  mov     rbx, [r11+10h]
0x180006b1f  mov     rdi, [r11+20h]
0x180006b23  mov     rsp, r11
0x180006b26  pop     rbp
0x180006b27  retn
0x180006b28  mov     ecx, eax; this
0x180006b2a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180006b2f  int     3; Trap to Debugger
0x180006b30  mov     ecx, eax; this
0x180006b32  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180006b37  int     3; Trap to Debugger
0x180006b38  mov     ecx, eax; this
0x180006b3a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180006b3f  int     3; Trap to Debugger
0x180006b40  mov     ecx, eax; this
0x180006b42  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
