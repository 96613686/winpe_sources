# WaaS::Device::FeatureEvaluator::CreateDetectFeatureObject(Windows::Data::Json::IJsonObject *,std::unique_ptr<WaaS::Device::DetectFeature,std::default_delete<WaaS::Device::DetectFeature>> &)

- ea: `0x180049ce4`
- end: `0x18004a149`
- name: `?CreateDetectFeatureObject@FeatureEvaluator@Device@WaaS@@AEAAJPEAUIJsonObject@Json@Data@Windows@@AEAV?$unique_ptr@VDetectFeature@Device@WaaS@@U?$default_delete@VDetectFeature@Device@WaaS@@@std@@@std@@@Z`
- size: `1125`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004a150`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x18000bbd4`
- `0x180024e48`
- `0x1800406b8`
- `0x180047034`
- `0x180049ce4`
- `0x18004ac48`
- `0x18004bc7c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049dd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049f82`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049d40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049dd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180049f82`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall WaaS::Device::FeatureEvaluator::CreateDetectFeatureObject(
        __int64 a1,
        __int64 *a2,
        void (__fastcall ****a3)(_QWORD, __int64))
{
  __int64 v6; // rbx
  HRESULT v7; // eax
  int v8; // edx
  unsigned int v9; // r8d
  int v10; // eax
  unsigned int v11; // ebx
  __int64 *v13; // rbx
  __int64 v14; // rdi
  HRESULT v15; // eax
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // eax
  int NPUFeaturesObject; // eax
  _QWORD *v20; // rdi
  _QWORD *v21; // rbx
  __int64 v22; // rdi
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // esi
  int v29; // eax
  void (__fastcall ***v30)(_QWORD, __int64); // rcx
  void (__fastcall ***v31)(_QWORD, __int64); // rcx
  __int64 v32; // [rsp+20h] [rbp-49h] BYREF
  __int64 *v33; // [rsp+28h] [rbp-41h] BYREF
  __int64 v34; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v35; // [rsp+38h] [rbp-31h]
  _QWORD *v36; // [rsp+40h] [rbp-29h]
  _QWORD *v37; // [rsp+48h] [rbp-21h]
  __int128 v38; // [rsp+50h] [rbp-19h] BYREF
  __int64 v39; // [rsp+60h] [rbp-9h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v33 = 0;
  v37 = 0;
  v36 = 0;
  v6 = *a2;
  string = 0;
  v7 = WindowsCreateStringReference(L"Hardware", 8u, &hstringHeader, &string);
  if ( v7 < 0 )
    goto LABEL_47;
  v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v6 + 64))(a2, string, &v33);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v10,
      v32);
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    return v11;
  }
  v13 = v33;
  v32 = 0;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v14 = *v33;
  string = 0;
  v15 = WindowsCreateStringReference(L"NPU", 3u, &hstringHeader, &string);
  if ( v15 < 0 )
  {
LABEL_48:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v15, v16, v17);
    JUMPOUT(0x18004A148LL);
  }
  v18 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v14 + 72))(v13, string, &v32);
  v11 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E1,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v18,
      v32);
    std::vector<WaaS::Device::NPUFeature>::~vector<WaaS::Device::NPUFeature>(&v38);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x208,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)v11,
      v32);
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    return v11;
  }
  NPUFeaturesObject = WaaS::Device::FeatureEvaluator::CreateNPUFeaturesObject(a1, v32, (__int64)&v38);
  v11 = NPUFeaturesObject;
  if ( NPUFeaturesObject < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E2,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)NPUFeaturesObject,
      v32);
    std::vector<WaaS::Device::NPUFeature>::~vector<WaaS::Device::NPUFeature>(&v38);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    goto LABEL_14;
  }
  v20 = operator new(0x20u);
  *v20 = &WaaS::Device::HardwareFeature::`vftable';
  v20[1] = 0;
  v20[2] = 0;
  v20[3] = 0;
  v35 = v20;
  if ( v20 + 1 != (_QWORD *)&v38 )
    std::vector<WaaS::Device::NPUFeature>::_Assign_counted_range<WaaS::Device::NPUFeature *>(
      v20 + 1,
      v38,
      0xF0F0F0F0F0F0F0F1uLL * ((__int64)(*((_QWORD *)&v38 + 1) - v38) >> 4));
  v36 = v20;
  std::vector<WaaS::Device::NPUFeature>::~vector<WaaS::Device::NPUFeature>(&v38);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  v21 = operator new(0x18u);
  v35 = v21;
  *v21 = &WaaS::Device::DetectFeature::`vftable';
  v21[2] = 0;
  v37 = v21;
  v36 = 0;
  v21[1] = v20;
  v34 = 0;
  v32 = 0;
  v22 = *a2;
  string = 0;
  v23 = WindowsCreateStringReference(L"Software", 8u, &hstringHeader, &string);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
LABEL_47:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v7, v8, v9);
    goto LABEL_48;
  }
  v26 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v22 + 64))(a2, string, &v34);
  v28 = v26;
  if ( v26 >= 0 )
  {
    v29 = WaaS::Device::FeatureEvaluator::CreateSoftwareFeatureObject(v27, v34, &v32);
    v28 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
        (const char *)(unsigned int)v29,
        v32);
      if ( v32 )
        (**(void (__fastcall ***)(__int64, __int64))v32)(v32, 1);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      (*(void (__fastcall **)(_QWORD *, __int64))*v21)(v21, 1);
      if ( v33 )
        (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
      return v28;
    }
    v30 = (void (__fastcall ***)(_QWORD, __int64))v21[2];
    v21[2] = v32;
    if ( v30 )
      (**v30)(v30, 1);
  }
  else if ( v26 != -2089484279 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v26,
      v32);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    (*(void (__fastcall **)(_QWORD *, __int64))*v21)(v21, 1);
    if ( v33 )
      (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
    return v28;
  }
  v37 = 0;
  v31 = *a3;
  *a3 = (void (__fastcall ***)(_QWORD, __int64))v21;
  if ( v31 )
    (**v31)(v31, 1);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v33 )
    (*(void (__fastcall **)(__int64 *))(*v33 + 16))(v33);
  return 0;
}

```

## disassembly

```asm
0x180049ce4  mov     [rsp-8+arg_18], rbx
0x180049ce9  push    rbp
0x180049cea  push    rsi
0x180049ceb  push    rdi
0x180049cec  push    r12
0x180049cee  push    r13
0x180049cf0  push    r14
0x180049cf2  push    r15
0x180049cf4  lea     rbp, [rsp-27h]
0x180049cf9  sub     rsp, 90h
0x180049d00  mov     rax, cs:__security_cookie
0x180049d07  xor     rax, rsp
0x180049d0a  mov     [rbp+57h+var_38], rax
0x180049d0e  mov     r14, r8
0x180049d11  mov     r15, rdx
0x180049d14  mov     r12, rcx
0x180049d17  xor     r13d, r13d
0x180049d1a  mov     [rbp+57h+var_98], r13
0x180049d1e  mov     [rbp+57h+var_78], r13
0x180049d22  mov     [rbp+57h+var_80], r13
0x180049d26  mov     rbx, [rdx]
0x180049d29  mov     [rbp+57h+string], r13
0x180049d2d  lea     r9, [rbp+57h+string]; string
0x180049d31  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180049d35  lea     edx, [r13+8]; length
0x180049d39  lea     rcx, aHardware; "Hardware"
0x180049d40  call    cs:__imp_WindowsCreateStringReference
0x180049d46  test    eax, eax
0x180049d48  js      loc_18004A139
0x180049d4e  lea     r8, [rbp+57h+var_98]
0x180049d52  mov     rdx, [rbp+57h+string]
0x180049d56  mov     rcx, r15
0x180049d59  mov     rax, [rbx+40h]
0x180049d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d62  mov     ebx, eax
0x180049d64  test    eax, eax
0x180049d66  jns     short loc_180049D9E
0x180049d68  mov     rcx, [rbp+5Fh]; this
0x180049d6c  mov     r9d, eax; char *
0x180049d6f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180049d76  mov     edx, 207h; void *
0x180049d7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d80  nop
0x180049d81  mov     rcx, [rbp+57h+var_98]
0x180049d85  test    rcx, rcx
0x180049d88  jz      short loc_180049D97
0x180049d8a  mov     rax, [rcx]
0x180049d8d  mov     rax, [rax+10h]
0x180049d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d96  nop
0x180049d97  mov     eax, ebx
0x180049d99  jmp     loc_18004A10A
0x180049d9e  mov     rbx, [rbp+57h+var_98]
0x180049da2  mov     [rbp+57h+var_A0], r13
0x180049da6  mov     [rbp+57h+var_88], r13
0x180049daa  xorps   xmm0, xmm0
0x180049dad  movdqu  [rbp+57h+var_70], xmm0
0x180049db2  mov     [rbp+57h+var_60], r13
0x180049db6  mov     rdi, [rbx]
0x180049db9  mov     [rbp+57h+string], r13
0x180049dbd  lea     r9, [rbp+57h+string]; string
0x180049dc1  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180049dc5  mov     edx, 3; length
0x180049dca  lea     rcx, aNpu; "NPU"
0x180049dd1  call    cs:__imp_WindowsCreateStringReference
0x180049dd7  test    eax, eax
0x180049dd9  js      loc_18004A141
0x180049ddf  lea     r8, [rbp+57h+var_A0]
0x180049de3  mov     rdx, [rbp+57h+string]
0x180049de7  mov     rcx, rbx
0x180049dea  mov     rax, [rdi+48h]
0x180049dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049df3  mov     ebx, eax
0x180049df5  test    eax, eax
0x180049df7  jns     short loc_180049E34
0x180049df9  mov     rcx, [rbp+5Fh]; this
0x180049dfd  mov     r9d, eax; char *
0x180049e00  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180049e07  mov     edx, 1E1h; void *
0x180049e0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e11  nop
0x180049e12  lea     rcx, [rbp+57h+var_70]
0x180049e16  call    ??1?$vector@VNPUFeature@Device@WaaS@@V?$allocator@VNPUFeature@Device@WaaS@@@std@@@std@@QEAA@XZ; std::vector<WaaS::Device::NPUFeature>::~vector<WaaS::Device::NPUFeature>(void)
0x180049e1b  nop
0x180049e1c  mov     rcx, [rbp+57h+var_A0]
0x180049e20  test    rcx, rcx
0x180049e23  jz      short loc_180049E32
0x180049e25  mov     rax, [rcx]
0x180049e28  mov     rax, [rax+10h]
0x180049e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e31  nop
0x180049e32  jmp     short loc_180049E83
0x180049e34  lea     r8, [rbp+57h+var_70]
0x180049e38  mov     rdx, [rbp+57h+var_A0]
0x180049e3c  mov     rcx, r12
0x180049e3f  call    ?CreateNPUFeaturesObject@FeatureEvaluator@Device@WaaS@@AEAAJPEAUIJsonArray@Json@Data@Windows@@AEAV?$vector@VNPUFeature@Device@WaaS@@V?$allocator@VNPUFeature@Device@WaaS@@@std@@@std@@@Z; WaaS::Device::FeatureEvaluator::CreateNPUFeaturesObject(Windows::Data::Json::IJsonArray *,std::vector<WaaS::Device::NPUFeature> &)
0x180049e44  mov     ebx, eax
0x180049e46  test    eax, eax
0x180049e48  jns     short loc_180049EB7
0x180049e4a  mov     rcx, [rbp+5Fh]; this
0x180049e4e  mov     r9d, eax; char *
0x180049e51  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180049e58  mov     edx, 1E2h; void *
0x180049e5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e62  nop
0x180049e63  lea     rcx, [rbp+57h+var_70]
0x180049e67  call    ??1?$vector@VNPUFeature@Device@WaaS@@V?$allocator@VNPUFeature@Device@WaaS@@@std@@@std@@QEAA@XZ; std::vector<WaaS::Device::NPUFeature>::~vector<WaaS::Device::NPUFeature>(void)
0x180049e6c  nop
0x180049e6d  mov     rcx, [rbp+57h+var_A0]
0x180049e71  test    rcx, rcx
0x180049e74  jz      short loc_180049E83
0x180049e76  mov     rax, [rcx]
0x180049e79  mov     rax, [rax+10h]
0x180049e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e82  nop
0x180049e83  mov     rcx, [rbp+5Fh]; this
0x180049e87  mov     r9d, ebx; char *
0x180049e8a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180049e91  mov     edx, 208h; void *
0x180049e96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e9b  nop
0x180049e9c  mov     rcx, [rbp+57h+var_98]
0x180049ea0  test    rcx, rcx
0x180049ea3  jz      short loc_180049EB2
0x180049ea5  mov     rdx, [rcx]
0x180049ea8  mov     rax, [rdx+10h]
0x180049eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049eb1  nop
0x180049eb2  jmp     loc_180049D97
0x180049eb7  mov     ecx, 20h ; ' '; Size
0x180049ebc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049ec1  mov     rdi, rax
0x180049ec4  mov     [rbp+57h+var_88], rax
0x180049ec8  lea     rax, ??_7HardwareFeature@Device@WaaS@@6B@; const WaaS::Device::HardwareFeature::`vftable'
0x180049ecf  mov     [rdi], rax
0x180049ed2  lea     rcx, [rdi+8]
0x180049ed6  mov     [rcx], r13
0x180049ed9  mov     [rcx+8], r13
0x180049edd  mov     [rcx+10h], r13
0x180049ee1  mov     [rbp+57h+var_88], rdi
0x180049ee5  lea     rax, [rbp+57h+var_70]
0x180049ee9  cmp     rcx, rax
0x180049eec  jz      short loc_180049F10
0x180049eee  mov     rdx, qword ptr [rbp+57h+var_70]
0x180049ef2  mov     r8, qword ptr [rbp+57h+var_70+8]
0x180049ef6  sub     r8, rdx
0x180049ef9  sar     r8, 4
0x180049efd  mov     rax, 0F0F0F0F0F0F0F0F1h
0x180049f07  imul    r8, rax
0x180049f0b  call    ??$_Assign_counted_range@PEAVNPUFeature@Device@WaaS@@@?$vector@VNPUFeature@Device@WaaS@@V?$allocator@VNPUFeature@Device@WaaS@@@std@@@std@@AEAAXPEAVNPUFeature@Device@WaaS@@_K@Z; std::vector<WaaS::Device::NPUFeature>::_Assign_counted_range<WaaS::Device::NPUFeature *>(WaaS::Device::NPUFeature *,unsigned __int64)
0x180049f10  mov     [rbp+57h+var_80], rdi
0x180049f14  lea     rcx, [rbp+57h+var_70]
0x180049f18  call    ??1?$vector@VNPUFeature@Device@WaaS@@V?$allocator@VNPUFeature@Device@WaaS@@@std@@@std@@QEAA@XZ; std::vector<WaaS::Device::NPUFeature>::~vector<WaaS::Device::NPUFeature>(void)
0x180049f1d  nop
0x180049f1e  mov     rcx, [rbp+57h+var_A0]
0x180049f22  test    rcx, rcx
0x180049f25  jz      short loc_180049F34
0x180049f27  mov     rax, [rcx]
0x180049f2a  mov     rax, [rax+10h]
0x180049f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f33  nop
0x180049f34  mov     ecx, 18h; Size
0x180049f39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049f3e  mov     rbx, rax
0x180049f41  mov     [rbp+57h+var_88], rax
0x180049f45  lea     rax, ??_7DetectFeature@Device@WaaS@@6B@; const WaaS::Device::DetectFeature::`vftable'
0x180049f4c  mov     [rbx], rax
0x180049f4f  mov     [rbx+10h], r13
0x180049f53  mov     [rbp+57h+var_78], rbx
0x180049f57  mov     [rbp+57h+var_80], r13
0x180049f5b  mov     [rbx+8], rdi
0x180049f5f  mov     [rbp+57h+var_90], r13
0x180049f63  mov     [rbp+57h+var_A0], r13
0x180049f67  mov     rdi, [r15]
0x180049f6a  mov     [rbp+57h+string], r13
0x180049f6e  lea     r9, [rbp+57h+string]; string
0x180049f72  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180049f76  mov     edx, 8; length
0x180049f7b  lea     rcx, aSoftware; "Software"
0x180049f82  call    cs:__imp_WindowsCreateStringReference
0x180049f88  test    eax, eax
0x180049f8a  js      loc_18004A131
0x180049f90  lea     r8, [rbp+57h+var_90]
0x180049f94  mov     rdx, [rbp+57h+string]
0x180049f98  mov     rcx, r15
0x180049f9b  mov     rax, [rdi+40h]
0x180049f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fa4  mov     esi, eax
0x180049fa6  mov     edi, 1
0x180049fab  test    eax, eax
0x180049fad  jns     short loc_18004A017
0x180049faf  cmp     eax, 83750009h
0x180049fb4  jz      loc_18004A0BF
0x180049fba  mov     rcx, [rbp+5Fh]; this
0x180049fbe  mov     r9d, eax; char *
0x180049fc1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180049fc8  mov     edx, 213h; void *
0x180049fcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049fd2  nop
0x180049fd3  mov     rcx, [rbp+57h+var_90]
0x180049fd7  test    rcx, rcx
0x180049fda  jz      short loc_180049FE9
0x180049fdc  mov     rax, [rcx]
0x180049fdf  mov     rax, [rax+10h]
0x180049fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049fe8  nop
0x180049fe9  mov     rax, [rbx]
0x180049fec  mov     edx, edi
0x180049fee  mov     rcx, rbx
0x180049ff1  mov     rax, [rax]
0x180049ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ff9  nop
0x180049ffa  mov     rcx, [rbp+57h+var_98]
0x180049ffe  test    rcx, rcx
0x18004a001  jz      short loc_18004A010
0x18004a003  mov     rax, [rcx]
0x18004a006  mov     rax, [rax+10h]
0x18004a00a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a00f  nop
0x18004a010  mov     eax, esi
0x18004a012  jmp     loc_18004A10A
0x18004a017  lea     r8, [rbp+57h+var_A0]
0x18004a01b  mov     rdx, [rbp+57h+var_90]
0x18004a01f  call    ?CreateSoftwareFeatureObject@FeatureEvaluator@Device@WaaS@@AEAAJPEAUIJsonObject@Json@Data@Windows@@AEAV?$unique_ptr@VSoftwareFeature@Device@WaaS@@U?$default_delete@VSoftwareFeature@Device@WaaS@@@std@@@std@@@Z; WaaS::Device::FeatureEvaluator::CreateSoftwareFeatureObject(Windows::Data::Json::IJsonObject *,std::unique_ptr<WaaS::Device::SoftwareFeature> &)
0x18004a024  mov     esi, eax
0x18004a026  test    eax, eax
0x18004a028  jns     short loc_18004A0A1
0x18004a02a  mov     rcx, [rbp+5Fh]; this
0x18004a02e  mov     r9d, eax; char *
0x18004a031  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004a038  mov     edx, 216h; void *
0x18004a03d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a042  nop
0x18004a043  mov     edi, 1
0x18004a048  mov     rcx, [rbp+57h+var_A0]
0x18004a04c  test    rcx, rcx
0x18004a04f  jz      short loc_18004A05F
0x18004a051  mov     rax, [rcx]
0x18004a054  mov     edx, edi
0x18004a056  mov     rax, [rax]
0x18004a059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a05e  nop
0x18004a05f  mov     rcx, [rbp+57h+var_90]
0x18004a063  test    rcx, rcx
0x18004a066  jz      short loc_18004A075
0x18004a068  mov     rax, [rcx]
0x18004a06b  mov     rax, [rax+10h]
0x18004a06f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a074  nop
0x18004a075  mov     rax, [rbx]
0x18004a078  mov     edx, edi
0x18004a07a  mov     rcx, rbx
0x18004a07d  mov     rax, [rax]
0x18004a080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a085  nop
0x18004a086  mov     rcx, [rbp+57h+var_98]
0x18004a08a  test    rcx, rcx
0x18004a08d  jz      short loc_18004A09C
0x18004a08f  mov     rax, [rcx]
0x18004a092  mov     rax, [rax+10h]
0x18004a096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a09b  nop
0x18004a09c  jmp     loc_18004A010
0x18004a0a1  mov     rax, [rbp+57h+var_A0]
0x18004a0a5  mov     rcx, [rbx+10h]
0x18004a0a9  mov     [rbx+10h], rax
0x18004a0ad  test    rcx, rcx
0x18004a0b0  jz      short loc_18004A0BF
0x18004a0b2  mov     rax, [rcx]
0x18004a0b5  mov     edx, edi
0x18004a0b7  mov     rax, [rax]
0x18004a0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0bf  mov     [rbp+57h+var_78], r13
0x18004a0c3  mov     rcx, [r14]
0x18004a0c6  mov     [r14], rbx
0x18004a0c9  test    rcx, rcx
0x18004a0cc  jz      short loc_18004A0DC
0x18004a0ce  mov     rax, [rcx]
0x18004a0d1  mov     edx, edi
0x18004a0d3  mov     rax, [rax]
0x18004a0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0db  nop
0x18004a0dc  mov     rcx, [rbp+57h+var_90]
0x18004a0e0  test    rcx, rcx
0x18004a0e3  jz      short loc_18004A0F2
0x18004a0e5  mov     rax, [rcx]
0x18004a0e8  mov     rax, [rax+10h]
0x18004a0ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0f1  nop
0x18004a0f2  mov     rcx, [rbp+57h+var_98]
0x18004a0f6  test    rcx, rcx
0x18004a0f9  jz      short loc_18004A108
0x18004a0fb  mov     rax, [rcx]
0x18004a0fe  mov     rax, [rax+10h]
0x18004a102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a107  nop
0x18004a108  xor     eax, eax
0x18004a10a  mov     rcx, [rbp+57h+var_38]
0x18004a10e  xor     rcx, rsp; StackCookie
0x18004a111  call    __security_check_cookie
  ... truncated ...
```
