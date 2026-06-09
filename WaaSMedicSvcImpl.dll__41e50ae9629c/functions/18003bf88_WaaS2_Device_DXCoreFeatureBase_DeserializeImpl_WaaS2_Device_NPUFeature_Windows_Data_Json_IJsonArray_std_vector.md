# WaaS2::Device::DXCoreFeatureBase::DeserializeImpl<WaaS2::Device::NPUFeature>(Windows::Data::Json::IJsonArray *,std::vector<WaaS2::Device::NPUFeature,std::allocator<WaaS2::Device::NPUFeature>> &)

- ea: `0x18003bf88`
- end: `0x18003c59a`
- name: `??$DeserializeImpl@VNPUFeature@Device@WaaS2@@@DXCoreFeatureBase@Device@WaaS2@@SAJPEAUIJsonArray@Json@Data@Windows@@AEAV?$vector@VNPUFeature@Device@WaaS2@@V?$allocator@VNPUFeature@Device@WaaS2@@@std@@@std@@@Z`
- size: `1554`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003bce8`
- `0x18004cdfc`

## callees

- `0x1800050a0`
- `0x180005108`
- `0x180008c80`
- `0x18000bbd4`
- `0x180024e48`
- `0x18002cbc4`
- `0x18003bf88`
- `0x18003c5a0`
- `0x180042008`
- `0x180042d1c`
- `0x180045008`
- `0x1800451a0`
- `0x180046e00`
- `0x180047300`
- `0x1800549d4`
- `0x18005ff5c`
- `0x18006341c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c0b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c158`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c0b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003c158`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall WaaS2::Device::DXCoreFeatureBase::DeserializeImpl<WaaS2::Device::NPUFeature>(__int64 a1, __int64 a2)
{
  unsigned int v4; // edi
  unsigned int i; // r14d
  int v7; // eax
  unsigned int v8; // esi
  __int64 v9; // rdx
  int v10; // eax
  __int64 *v11; // rsi
  __int64 v12; // r15
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int v16; // edi
  int v17; // eax
  __int64 v18; // rcx
  char v19; // al
  unsigned int v20; // edi
  int v21; // eax
  __int64 *v22; // rsi
  __int64 v23; // r15
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  int v27; // edi
  int v28; // eax
  __int64 v29; // rcx
  char v30; // al
  int v31; // eax
  __int64 v32; // r10
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // r9
  __int128 v36; // rax
  WaaS2::Device::DXCoreFeatureBase *v37; // rsi
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+20h] [rbp-E0h]
  __int64 *v40; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v43; // [rsp+48h] [rbp-B8h]
  __int128 v44; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h]
  WaaS2::Device::DXCoreFeatureBase *v46[2]; // [rsp+68h] [rbp-98h] BYREF
  WaaS2::Device::DXCoreFeatureBase *v47; // [rsp+78h] [rbp-88h]
  __int128 v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h]
  _QWORD *v50; // [rsp+98h] [rbp-68h]
  _QWORD v51[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v52[3]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v53[3]; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING string; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v56[544]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v57[76]; // [rsp+330h] [rbp+230h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+4D8h]

  v4 = 0;
  LODWORD(v43) = 0;
  if ( !a1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBAC,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)0x80070057LL,
      v38);
    return 2147942487LL;
  }
  *(_OWORD *)v46 = 0;
  v47 = 0;
  for ( i = 0; ; ++i )
  {
    v40 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)a1 + 48LL))(a1, i, &v40);
    v8 = v7;
    if ( v7 < 0 )
      break;
    `eh vector constructor iterator'(v56, 0x20u, 0x11u, std::wstring::wstring, std::wstring::~wstring);
    v10 = WaaS2::Device::DeserializeStringFields_17_(v40, v9, v56);
    v8 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBBC,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
        (const char *)(unsigned int)v10,
        v38);
      `eh vector destructor iterator'(v56, 0x20u, 0x11u, std::wstring::~wstring);
      if ( v40 )
        (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
      goto LABEL_49;
    }
    v44 = 0;
    v45 = 0;
    v41 = 0;
    v11 = v40;
    v12 = *v40;
    string = 0;
    v13 = WindowsCreateStringReference(L"SupportedHardwareIdList", 0x17u, &hstringHeader, &string);
    if ( v13 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
LABEL_54:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
      JUMPOUT(0x18003C599LL);
    }
    v16 = v4 | 1;
    LODWORD(v43) = v16;
    v17 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v12 + 72))(v11, string, &v41);
    if ( v17 >= 0 )
    {
      v18 = v41;
      if ( v41 )
      {
        v19 = 1;
        goto LABEL_10;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC1,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
        (const char *)(unsigned int)v17,
        v38);
      v18 = v41;
    }
    v19 = 0;
LABEL_10:
    v20 = v16 & 0xFFFFFFFE;
    if ( v19 )
    {
      v21 = WaaS2::Device::DXCoreFeatureBase::ParseHardwareIdListJsonArray(v18, &v44);
      v8 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBC3,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
          (const char *)(unsigned int)v21,
          v38);
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(&v44);
        `eh vector destructor iterator'(v56, 0x20u, 0x11u, std::wstring::~wstring);
        if ( v40 )
          (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
        goto LABEL_49;
      }
    }
    v48 = 0;
    v49 = 0;
    v42 = 0;
    v22 = v40;
    v23 = *v40;
    string = 0;
    v24 = WindowsCreateStringReference(L"UnsupportedHardwareIdList", 0x19u, &hstringHeader, &string);
    if ( v24 < 0 )
      goto LABEL_54;
    v27 = v20 | 2;
    LODWORD(v43) = v27;
    v28 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v23 + 72))(v22, string, &v42);
    if ( v28 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC8,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
        (const char *)(unsigned int)v28,
        v38);
      v29 = v42;
LABEL_18:
      v30 = 0;
      goto LABEL_19;
    }
    v29 = v42;
    v30 = 1;
    if ( !v42 )
      goto LABEL_18;
LABEL_19:
    v4 = v27 & 0xFFFFFFFD;
    if ( v30 )
    {
      v31 = WaaS2::Device::DXCoreFeatureBase::ParseHardwareIdListJsonArray(v29, &v48);
      v8 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBCA,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
          (const char *)(unsigned int)v31,
          v38);
        if ( v42 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(&v48);
        if ( v41 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(&v44);
        `eh vector destructor iterator'(v56, 0x20u, 0x11u, std::wstring::~wstring);
        if ( v40 )
          (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
LABEL_49:
        std::vector<WaaS2::Device::GPUFeature>::~vector<WaaS2::Device::GPUFeature>(v46);
        return v8;
      }
    }
    WaaS2::Device::DXCoreFeatureBase::DXCoreFeatureBase((WaaS2::Device::DXCoreFeatureBase *)v57);
    v57[0] = &WaaS2::Device::DXCoreFeatureBase::`vftable';
    v32 = v49;
    v49 = 0;
    v33 = *((_QWORD *)&v48 + 1);
    v34 = v48;
    v48 = 0u;
    v43 = v52;
    v35 = v45;
    v45 = 0;
    v36 = v44;
    v44 = 0u;
    v50 = v51;
    memset(v52, 0, sizeof(v52));
    v53[0] = v34;
    v53[1] = v33;
    v53[2] = v32;
    memset(v51, 0, sizeof(v51));
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v36;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = v35;
    WaaS2::Device::DXCoreFeatureBase::InitAllMembers(v57, v56, &hstringHeader, v53);
    std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(v51);
    std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(v52);
    v37 = v46[1];
    if ( v46[1] == v47 )
    {
      std::vector<WaaS2::Device::NPUFeature>::_Emplace_reallocate<WaaS2::Device::NPUFeature>(v46, v46[1], v57);
    }
    else
    {
      WaaS2::Device::DXCoreFeatureBase::DXCoreFeatureBase(v46[1], (const struct WaaS2::Device::DXCoreFeatureBase *)v57);
      *(_QWORD *)v37 = &WaaS2::Device::DXCoreFeatureBase::`vftable';
      v46[1] = (WaaS2::Device::DXCoreFeatureBase *)((char *)v46[1] + 600);
    }
    WaaS2::Device::DXCoreFeatureBase::~DXCoreFeatureBase((WaaS2::Device::DXCoreFeatureBase *)v57);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(&v48);
    if ( v41 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(&v44);
    `eh vector destructor iterator'(v56, 0x20u, 0x11u, std::wstring::~wstring);
    if ( v40 )
      (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xBB4,
    (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
    (const char *)(unsigned int)v7,
    v38);
  if ( v8 != -2147483637 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB6,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)v8,
      v39);
    if ( v40 )
      (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
    goto LABEL_49;
  }
  if ( v40 )
    (*(void (__fastcall **)(__int64 *))(*v40 + 16))(v40);
  std::vector<WaaS2::Device::GPUFeature>::_Insert_counted_range<std::move_iterator<WaaS2::Device::GPUFeature *>>(
    a2,
    *(_QWORD *)(a2 + 8),
    v46[0],
    0x2FC962FC962FC963LL * ((v46[1] - v46[0]) >> 3));
  std::vector<WaaS2::Device::GPUFeature>::~vector<WaaS2::Device::GPUFeature>(v46);
  return 0;
}

```

## disassembly

```asm
0x18003bf88  mov     [rsp-8+arg_10], rbx
0x18003bf8d  push    rbp
0x18003bf8e  push    rsi
0x18003bf8f  push    rdi
0x18003bf90  push    r12
0x18003bf92  push    r13
0x18003bf94  push    r14
0x18003bf96  push    r15
0x18003bf98  lea     rbp, [rsp-4A0h]
0x18003bfa0  sub     rsp, 5A0h
0x18003bfa7  mov     rax, cs:__security_cookie
0x18003bfae  xor     rax, rsp
0x18003bfb1  mov     [rbp+4D0h+var_40], rax
0x18003bfb8  mov     r13, rdx
0x18003bfbb  mov     r12, rcx
0x18003bfbe  xor     r15d, r15d
0x18003bfc1  mov     edi, r15d
0x18003bfc4  mov     dword ptr [rsp+5D0h+var_588], r15d
0x18003bfc9  test    rcx, rcx
0x18003bfcc  jnz     short loc_18003BFF5
0x18003bfce  mov     rcx, [rbp+4D8h]; this
0x18003bfd5  mov     edi, 80070057h
0x18003bfda  mov     r9d, edi; char *
0x18003bfdd  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003bfe4  mov     edx, 0BACh; void *
0x18003bfe9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bfee  mov     eax, edi
0x18003bff0  jmp     loc_18003C560
0x18003bff5  xorps   xmm0, xmm0
0x18003bff8  movdqu  xmmword ptr [rsp+5D0h+var_568], xmm0
0x18003bffe  mov     [rsp+5D0h+var_558], r15
0x18003c003  mov     r14d, r15d
0x18003c006  lea     rbx, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18003c00d  mov     [rsp+5D0h+var_5A0], r15
0x18003c012  mov     rax, [r12]
0x18003c016  lea     r8, [rsp+5D0h+var_5A0]
0x18003c01b  mov     edx, r14d
0x18003c01e  mov     rcx, r12
0x18003c021  mov     rax, [rax+30h]
0x18003c025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c02a  mov     esi, eax
0x18003c02c  mov     rcx, [rbp+4D8h]; this
0x18003c033  test    eax, eax
0x18003c035  js      loc_18003C4BC
0x18003c03b  lea     rax, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c042  mov     qword ptr [rsp+5D0h+var_5B0], rax; int
0x18003c047  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18003c04e  mov     edx, 20h ; ' '; unsigned __int64
0x18003c053  lea     r8d, [rdx-0Fh]; unsigned __int64
0x18003c057  lea     rcx, [rbp+4D0h+var_4C0]; void *
0x18003c05b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003c060  nop
0x18003c061  lea     r8, [rbp+4D0h+var_4C0]
0x18003c065  mov     rcx, [rsp+5D0h+var_5A0]
0x18003c06a  call    WaaS2__Device__DeserializeStringFields_17_
0x18003c06f  mov     esi, eax
0x18003c071  test    eax, eax
0x18003c073  js      loc_18003C471
0x18003c079  xorps   xmm0, xmm0
0x18003c07c  movdqu  [rsp+5D0h+var_580], xmm0
0x18003c082  mov     [rsp+5D0h+var_570], r15
0x18003c087  mov     [rsp+5D0h+var_598], r15
0x18003c08c  mov     rsi, [rsp+5D0h+var_5A0]
0x18003c091  mov     r15, [rsi]
0x18003c094  mov     [rbp+4D0h+string], 0
0x18003c09c  lea     r9, [rbp+4D0h+string]; string
0x18003c0a0  lea     r8, [rbp+4D0h+hstringHeader]; hstringHeader
0x18003c0a4  mov     edx, 17h; length
0x18003c0a9  lea     rcx, sourceString; "SupportedHardwareIdList"
0x18003c0b0  call    cs:__imp_WindowsCreateStringReference
0x18003c0b6  test    eax, eax
0x18003c0b8  js      loc_18003C58A
0x18003c0be  or      edi, 1
0x18003c0c1  mov     dword ptr [rsp+5D0h+var_588], edi
0x18003c0c5  lea     r8, [rsp+5D0h+var_598]
0x18003c0ca  mov     rdx, [rbp+4D0h+string]
0x18003c0ce  mov     rcx, rsi
0x18003c0d1  mov     rax, [r15+48h]
0x18003c0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0da  mov     rcx, [rbp+4D8h]; this
0x18003c0e1  test    eax, eax
0x18003c0e3  jns     loc_18003C1A7
0x18003c0e9  mov     r9d, eax; char *
0x18003c0ec  mov     r8, rbx; unsigned int
0x18003c0ef  mov     edx, 0BC1h; void *
0x18003c0f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c0f9  mov     rcx, [rsp+5D0h+var_598]
0x18003c0fe  xor     al, al
0x18003c100  and     edi, 0FFFFFFFEh
0x18003c103  test    al, al
0x18003c105  jz      short loc_18003C11B
0x18003c107  lea     rdx, [rsp+5D0h+var_580]
0x18003c10c  call    ?ParseHardwareIdListJsonArray@DXCoreFeatureBase@Device@WaaS2@@KAJPEAUIJsonArray@Json@Data@Windows@@AEAV?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@@Z; WaaS2::Device::DXCoreFeatureBase::ParseHardwareIdListJsonArray(Windows::Data::Json::IJsonArray *,std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts> &)
0x18003c111  mov     esi, eax
0x18003c113  test    eax, eax
0x18003c115  js      loc_18003C370
0x18003c11b  xorps   xmm0, xmm0
0x18003c11e  movdqu  [rbp+4D0h+var_550], xmm0
0x18003c123  mov     [rbp+4D0h+var_540], 0
0x18003c12b  mov     [rsp+5D0h+var_590], 0
0x18003c134  mov     rsi, [rsp+5D0h+var_5A0]
0x18003c139  mov     r15, [rsi]
0x18003c13c  mov     [rbp+4D0h+string], 0
0x18003c144  lea     r9, [rbp+4D0h+string]; string
0x18003c148  lea     r8, [rbp+4D0h+hstringHeader]; hstringHeader
0x18003c14c  mov     edx, 19h; length
0x18003c151  lea     rcx, aUnsupportedhar; "UnsupportedHardwareIdList"
0x18003c158  call    cs:__imp_WindowsCreateStringReference
0x18003c15e  test    eax, eax
0x18003c160  js      loc_18003C592
0x18003c166  or      edi, 2
0x18003c169  mov     dword ptr [rsp+5D0h+var_588], edi
0x18003c16d  lea     r8, [rsp+5D0h+var_590]
0x18003c172  mov     rdx, [rbp+4D0h+string]
0x18003c176  mov     rcx, rsi
0x18003c179  mov     rax, [r15+48h]
0x18003c17d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c182  mov     rcx, [rbp+4D8h]; this
0x18003c189  xor     r15d, r15d
0x18003c18c  test    eax, eax
0x18003c18e  jns     short loc_18003C1BC
0x18003c190  mov     r9d, eax; char *
0x18003c193  mov     r8, rbx; unsigned int
0x18003c196  mov     edx, 0BC8h; void *
0x18003c19b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003c1a0  mov     rcx, [rsp+5D0h+var_590]
0x18003c1a5  jmp     short loc_18003C1C8
0x18003c1a7  mov     rcx, [rsp+5D0h+var_598]
0x18003c1ac  test    rcx, rcx
0x18003c1af  jz      loc_18003C0FE
0x18003c1b5  mov     al, 1
0x18003c1b7  jmp     loc_18003C100
0x18003c1bc  mov     rcx, [rsp+5D0h+var_590]
0x18003c1c1  test    rcx, rcx
0x18003c1c4  mov     al, 1
0x18003c1c6  jnz     short loc_18003C1CB
0x18003c1c8  mov     al, r15b
0x18003c1cb  and     edi, 0FFFFFFFDh
0x18003c1ce  test    al, al
0x18003c1d0  jz      short loc_18003C1E5
0x18003c1d2  lea     rdx, [rbp+4D0h+var_550]
0x18003c1d6  call    ?ParseHardwareIdListJsonArray@DXCoreFeatureBase@Device@WaaS2@@KAJPEAUIJsonArray@Json@Data@Windows@@AEAV?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@@Z; WaaS2::Device::DXCoreFeatureBase::ParseHardwareIdListJsonArray(Windows::Data::Json::IJsonArray *,std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts> &)
0x18003c1db  mov     esi, eax
0x18003c1dd  test    eax, eax
0x18003c1df  js      loc_18003C3E0
0x18003c1e5  lea     rcx, [rbp+4D0h+var_2A0]; this
0x18003c1ec  call    ??0DXCoreFeatureBase@Device@WaaS2@@QEAA@XZ; WaaS2::Device::DXCoreFeatureBase::DXCoreFeatureBase(void)
0x18003c1f1  lea     rax, ??_7DXCoreFeatureBase@Device@WaaS2@@6B@; const WaaS2::Device::DXCoreFeatureBase::`vftable'
0x18003c1f8  mov     [rbp+4D0h+var_2A0], rax
0x18003c1ff  mov     r10, [rbp+4D0h+var_540]
0x18003c203  mov     [rbp+4D0h+var_540], r15
0x18003c207  mov     r8, qword ptr [rbp+4D0h+var_550+8]
0x18003c20b  mov     qword ptr [rbp+4D0h+var_550+8], r15
0x18003c20f  mov     rcx, qword ptr [rbp+4D0h+var_550]
0x18003c213  mov     qword ptr [rbp+4D0h+var_550], r15
0x18003c217  lea     rax, [rbp+4D0h+var_510]
0x18003c21b  mov     [rsp+5D0h+var_588], rax
0x18003c220  mov     r9, [rsp+5D0h+var_570]
0x18003c225  mov     [rsp+5D0h+var_570], r15
0x18003c22a  mov     rdx, qword ptr [rsp+5D0h+var_580+8]
0x18003c22f  mov     qword ptr [rsp+5D0h+var_580+8], r15
0x18003c234  mov     rax, qword ptr [rsp+5D0h+var_580]
0x18003c239  mov     qword ptr [rsp+5D0h+var_580], r15
0x18003c23e  lea     r11, [rbp+4D0h+var_528]
0x18003c242  mov     [rbp+4D0h+var_538], r11
0x18003c246  mov     [rbp+4D0h+var_500], r15
0x18003c24a  mov     [rbp+4D0h+var_508], r15
0x18003c24e  mov     [rbp+4D0h+var_510], r15
0x18003c252  mov     [rbp+4D0h+var_4F8], rcx
0x18003c256  mov     [rbp+4D0h+var_4F0], r8
0x18003c25a  mov     [rbp+4D0h+var_4E8], r10
0x18003c25e  mov     [rbp+4D0h+var_518], r15
0x18003c262  mov     [rbp+4D0h+var_520], r15
0x18003c266  mov     [rbp+4D0h+var_528], r15
0x18003c26a  mov     qword ptr [rbp+4D0h+hstringHeader.Reserved], rax
0x18003c26e  mov     qword ptr [rbp+4D0h+hstringHeader.Reserved+8], rdx
0x18003c272  mov     qword ptr [rbp+4D0h+hstringHeader.Reserved+10h], r9
0x18003c276  lea     r9, [rbp+4D0h+var_4F8]
0x18003c27a  lea     r8, [rbp+4D0h+hstringHeader]
0x18003c27e  lea     rdx, [rbp+4D0h+var_4C0]
0x18003c282  lea     rcx, [rbp+4D0h+var_2A0]
0x18003c289  call    ?InitAllMembers@DXCoreFeatureBase@Device@WaaS2@@IEAAXAEBV?$array@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0BB@@std@@V?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@5@1@Z; WaaS2::Device::DXCoreFeatureBase::InitAllMembers(std::array<std::wstring,17> const &,std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>,std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>)
0x18003c28e  nop
0x18003c28f  lea     rcx, [rbp+4D0h+var_528]
0x18003c293  call    ?_Tidy@?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAXXZ; std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(void)
0x18003c298  nop
0x18003c299  lea     rcx, [rbp+4D0h+var_510]
0x18003c29d  call    ?_Tidy@?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAXXZ; std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(void)
0x18003c2a2  mov     rsi, [rsp+5D0h+var_568+8]
0x18003c2a7  cmp     rsi, [rsp+5D0h+var_558]
0x18003c2ac  jz      short loc_18003C2D2
0x18003c2ae  lea     rdx, [rbp+4D0h+var_2A0]; struct WaaS2::Device::DXCoreFeatureBase *
0x18003c2b5  mov     rcx, rsi; this
0x18003c2b8  call    ??0DXCoreFeatureBase@Device@WaaS2@@QEAA@AEBV012@@Z; WaaS2::Device::DXCoreFeatureBase::DXCoreFeatureBase(WaaS2::Device::DXCoreFeatureBase const &)
0x18003c2bd  lea     rax, ??_7DXCoreFeatureBase@Device@WaaS2@@6B@; const WaaS2::Device::DXCoreFeatureBase::`vftable'
0x18003c2c4  mov     [rsi], rax
0x18003c2c7  add     [rsp+5D0h+var_568+8], 258h
0x18003c2d0  jmp     short loc_18003C2E7
0x18003c2d2  lea     r8, [rbp+4D0h+var_2A0]
0x18003c2d9  mov     rdx, rsi
0x18003c2dc  lea     rcx, [rsp+5D0h+var_568]
0x18003c2e1  call    ??$_Emplace_reallocate@VNPUFeature@Device@WaaS2@@@?$vector@VNPUFeature@Device@WaaS2@@V?$allocator@VNPUFeature@Device@WaaS2@@@std@@@std@@AEAAPEAVNPUFeature@Device@WaaS2@@QEAV234@$$QEAV234@@Z; std::vector<WaaS2::Device::NPUFeature>::_Emplace_reallocate<WaaS2::Device::NPUFeature>(WaaS2::Device::NPUFeature * const,WaaS2::Device::NPUFeature &&)
0x18003c2e6  nop
0x18003c2e7  lea     rcx, [rbp+4D0h+var_2A0]; this
0x18003c2ee  call    ??1DXCoreFeatureBase@Device@WaaS2@@UEAA@XZ; WaaS2::Device::DXCoreFeatureBase::~DXCoreFeatureBase(void)
0x18003c2f3  nop
0x18003c2f4  mov     rcx, [rsp+5D0h+var_590]
0x18003c2f9  test    rcx, rcx
0x18003c2fc  jz      short loc_18003C30B
0x18003c2fe  mov     rax, [rcx]
0x18003c301  mov     rax, [rax+10h]
0x18003c305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c30a  nop
0x18003c30b  lea     rcx, [rbp+4D0h+var_550]
0x18003c30f  call    ?_Tidy@?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAXXZ; std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(void)
0x18003c314  nop
0x18003c315  mov     rcx, [rsp+5D0h+var_598]
0x18003c31a  test    rcx, rcx
0x18003c31d  jz      short loc_18003C32C
0x18003c31f  mov     rax, [rcx]
0x18003c322  mov     rax, [rax+10h]
0x18003c326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c32b  nop
0x18003c32c  lea     rcx, [rsp+5D0h+var_580]
0x18003c331  call    ?_Tidy@?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAXXZ; std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(void)
0x18003c336  nop
0x18003c337  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18003c33e  mov     edx, 20h ; ' '; unsigned __int64
0x18003c343  lea     r8d, [rdx-0Fh]; unsigned __int64
0x18003c347  lea     rcx, [rbp+4D0h+var_4C0]; void *
0x18003c34b  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003c350  nop
0x18003c351  mov     rcx, [rsp+5D0h+var_5A0]
0x18003c356  test    rcx, rcx
0x18003c359  jz      short loc_18003C368
0x18003c35b  mov     rax, [rcx]
0x18003c35e  mov     rax, [rax+10h]
0x18003c362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c367  nop
0x18003c368  inc     r14d
0x18003c36b  jmp     loc_18003C00D
0x18003c370  mov     rcx, [rbp+4D8h]; this
0x18003c377  mov     r9d, eax; char *
0x18003c37a  mov     r8, rbx; unsigned int
0x18003c37d  mov     edx, 0BC3h; void *
0x18003c382  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c387  nop
0x18003c388  mov     rcx, [rsp+5D0h+var_598]
0x18003c38d  test    rcx, rcx
0x18003c390  jz      short loc_18003C39F
0x18003c392  mov     rax, [rcx]
0x18003c395  mov     rax, [rax+10h]
0x18003c399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c39e  nop
0x18003c39f  lea     rcx, [rsp+5D0h+var_580]
0x18003c3a4  call    ?_Tidy@?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAXXZ; std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(void)
0x18003c3a9  nop
0x18003c3aa  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18003c3b1  mov     edx, 20h ; ' '; unsigned __int64
0x18003c3b6  lea     r8d, [rdx-0Fh]; unsigned __int64
0x18003c3ba  lea     rcx, [rbp+4D0h+var_4C0]; void *
0x18003c3be  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003c3c3  nop
0x18003c3c4  mov     rcx, [rsp+5D0h+var_5A0]
0x18003c3c9  test    rcx, rcx
0x18003c3cc  jz      short loc_18003C3DB
0x18003c3ce  mov     rax, [rcx]
0x18003c3d1  mov     rax, [rax+10h]
0x18003c3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c3da  nop
0x18003c3db  jmp     loc_18003C503
0x18003c3e0  mov     rcx, [rbp+4D8h]; this
0x18003c3e7  mov     r9d, esi; char *
0x18003c3ea  mov     r8, rbx; unsigned int
0x18003c3ed  mov     edx, 0BCAh; void *
0x18003c3f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c3f7  nop
0x18003c3f8  mov     rcx, [rsp+5D0h+var_590]
0x18003c3fd  test    rcx, rcx
0x18003c400  jz      short loc_18003C40F
0x18003c402  mov     rax, [rcx]
0x18003c405  mov     rax, [rax+10h]
0x18003c409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c40e  nop
0x18003c40f  lea     rcx, [rbp+4D0h+var_550]
0x18003c413  call    ?_Tidy@?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAXXZ; std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(void)
0x18003c418  nop
0x18003c419  mov     rcx, [rsp+5D0h+var_598]
0x18003c41e  test    rcx, rcx
0x18003c421  jz      short loc_18003C430
0x18003c423  mov     rax, [rcx]
0x18003c426  mov     rax, [rax+10h]
0x18003c42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c42f  nop
0x18003c430  lea     rcx, [rsp+5D0h+var_580]
0x18003c435  call    ?_Tidy@?$vector@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@V?$allocator@VDetectDXCoreAdapterHardwareIdParts@Device@WaaS2@@@std@@@std@@AEAAXXZ; std::vector<WaaS2::Device::DetectDXCoreAdapterHardwareIdParts>::_Tidy(void)
0x18003c43a  nop
0x18003c43b  lea     r9, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x18003c442  mov     edx, 20h ; ' '; unsigned __int64
0x18003c447  lea     r8d, [rdx-0Fh]; unsigned __int64
  ... truncated ...
```
