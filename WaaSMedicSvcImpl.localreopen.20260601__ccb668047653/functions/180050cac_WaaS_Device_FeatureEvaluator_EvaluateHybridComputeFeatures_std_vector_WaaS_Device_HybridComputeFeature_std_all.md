# WaaS::Device::FeatureEvaluator::EvaluateHybridComputeFeatures(std::vector<WaaS::Device::HybridComputeFeature,std::allocator<WaaS::Device::HybridComputeFeature>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180050cac`
- end: `0x180051291`
- name: `?EvaluateHybridComputeFeatures@FeatureEvaluator@Device@WaaS@@AEAAJAEAV?$vector@VHybridComputeFeature@Device@WaaS@@V?$allocator@VHybridComputeFeature@Device@WaaS@@@std@@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@@Z`
- size: `1509`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800529d8`

## callees

- `0x1800050a0`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x180010e54`
- `0x18001e5a0`
- `0x18002cbc4`
- `0x18003e700`
- `0x18003e838`
- `0x18003e970`
- `0x180048ffc`
- `0x180050cac`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005100a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051077`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800510cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051123`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050f8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050fe6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005100a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051077`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800510cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051123`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180050e31`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180050e31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050de6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050de6`
- `RPCRT4!UuidFromStringW` at `0x180050daa`
- `RPCRT4!UuidFromStringW` at `0x180050daa`

## string_xrefs

- `0x180050cfd`: `Device\Detect\Software\HybridCompute`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WaaS::Device::FeatureEvaluator::EvaluateHybridComputeFeatures(__int64 a1, __int64 *a2, _QWORD *a3)
{
  _QWORD *v5; // rdi
  _QWORD *v6; // rsi
  _QWORD *i; // rbx
  const wchar_t *v8; // rdx
  size_t v9; // r8
  const wchar_t *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r15
  const WCHAR *v13; // rsi
  unsigned __int16 *v14; // rcx
  RPC_STATUS v15; // eax
  unsigned int v16; // edi
  HRESULT v17; // eax
  HRESULT v18; // eax
  struct IUnknownVtbl *lpVtbl; // rax
  int v20; // eax
  int Com; // eax
  const WCHAR *v22; // rcx
  int v23; // eax
  const WCHAR *v24; // rcx
  int v25; // eax
  __int64 v26; // rdi
  __int64 j; // rbx
  __int64 v29; // rsi
  __int64 v30; // rsi
  void (__fastcall ***v31)(_QWORD, _QWORD); // rsi
  void (__fastcall ***k)(_QWORD, _QWORD); // rdi
  int ppv; // [rsp+20h] [rbp-79h]
  int ppva; // [rsp+20h] [rbp-79h]
  LPVOID pv; // [rsp+40h] [rbp-59h] BYREF
  __int64 v36; // [rsp+48h] [rbp-51h] BYREF
  IUnknown *pProxy; // [rsp+50h] [rbp-49h] BYREF
  _QWORD v38[2]; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v39[2]; // [rsp+68h] [rbp-31h] BYREF
  wchar_t *S2[2]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v41; // [rsp+88h] [rbp-11h]
  UUID Uuid; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v5 = (_QWORD *)a3[1];
  if ( v5 == (_QWORD *)*a3 )
    return 0;
  *(_OWORD *)S2 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S2, L"Device\\Detect\\Software\\HybridCompute", 36);
  v6 = (_QWORD *)a3[1];
  for ( i = (_QWORD *)*a3; i != v6; i += 4 )
  {
    v8 = (const wchar_t *)S2;
    if ( *((_QWORD *)&v41 + 1) > 7u )
      v8 = S2[0];
    v9 = i[2];
    v10 = i[3] <= 7u ? (const wchar_t *)i : (const wchar_t *)*i;
    if ( v9 == (_QWORD)v41 && (!v9 || !wmemcmp(v10, v8, v9)) )
      break;
  }
  std::wstring::~wstring(S2);
  if ( v5 == i )
    return 0;
  v11 = *a2;
  v12 = a2[1];
  if ( *a2 == v12 )
  {
LABEL_70:
    v26 = a2[1];
    for ( j = *a2; j != v26 && *(_BYTE *)(j + 104); j += 112 )
      ;
    if ( j != v26 )
    {
      v29 = j + 112;
      if ( j + 112 == v26 )
        goto LABEL_106;
      do
      {
        if ( *(_BYTE *)(v29 + 104) )
        {
          std::wstring::operator=(j + 8, v29 + 8);
          std::wstring::operator=(j + 40, v29 + 40);
          std::wstring::operator=(j + 72, v29 + 72);
          *(_BYTE *)(j + 104) = *(_BYTE *)(v29 + 104);
          j += 112;
        }
        v29 += 112;
      }
      while ( v29 != v26 );
      if ( j != v26 )
      {
LABEL_106:
        v30 = a2[1];
        while ( v26 != v30 )
        {
          std::wstring::operator=(j + 8, v26 + 8);
          std::wstring::operator=(j + 40, v26 + 40);
          std::wstring::operator=(j + 72, v26 + 72);
          *(_BYTE *)(j + 104) = *(_BYTE *)(v26 + 104);
          j += 112;
          v26 += 112;
        }
        v31 = (void (__fastcall ***)(_QWORD, _QWORD))a2[1];
        for ( k = (void (__fastcall ***)(_QWORD, _QWORD))j; k != v31; k += 14 )
          (**k)(k, 0);
        a2[1] = j;
      }
    }
    return 0;
  }
  while ( *(_BYTE *)(v11 + 104) )
  {
LABEL_69:
    v11 += 112;
    if ( v11 == v12 )
      goto LABEL_70;
  }
  Uuid = GUID_NULL;
  v13 = (const WCHAR *)(v11 + 72);
  if ( *(_QWORD *)(v11 + 96) <= 7u )
    v14 = (unsigned __int16 *)(v11 + 72);
  else
    v14 = *(unsigned __int16 **)v13;
  v15 = UuidFromStringW(v14, &Uuid);
  v16 = v15;
  if ( v15 >= 1 )
    v16 = (unsigned __int16)v15 | 0x80010000;
  if ( (v16 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)v16,
      ppv);
    return v16;
  }
  pProxy = 0;
  v17 = CoCreateInstance(&Uuid, 0, 4u, &GUID_00000000_0000_0000_c000_000000000046, (LPVOID *)&pProxy);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v17,
      ppva);
    goto LABEL_67;
  }
  v18 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 2u, 0, 0);
  v16 = v18;
  if ( v18 >= 0 )
  {
    v36 = 0;
    lpVtbl = pProxy->lpVtbl;
    v36 = 0;
    v20 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))lpVtbl->QueryInterface)(
            pProxy,
            &GUID_dfcee1c8_648e_4903_8ac1_f8a18d35e524,
            &v36);
    if ( v20 >= 0 )
    {
      if ( *(_QWORD *)(v11 + 24) )
      {
        pv = 0;
        v38[0] = &v36;
        v38[1] = &pv;
        Com = WaaS::ComTimeout::MakeComCall<_lambda_6367910aca77f9e7ff545ce583bdabd5_>(v38);
        v16 = Com;
        if ( Com < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x306,
            (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
            (const char *)(unsigned int)Com,
            ppv);
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          if ( pProxy )
            ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
          return v16;
        }
        v22 = (const WCHAR *)(v11 + 8);
        if ( *(_QWORD *)(v11 + 32) > 7u )
          v22 = *(const WCHAR **)v22;
        if ( (unsigned __int8)WaaS::Device::AreStringsNotEqualI(v22, (PCNZWCH)pv) )
        {
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          goto LABEL_67;
        }
        if ( pv )
          CoTaskMemFree(pv);
      }
      if ( *(_QWORD *)(v11 + 56) )
      {
        pv = 0;
        v39[0] = &v36;
        v39[1] = &pv;
        v23 = WaaS::ComTimeout::MakeComCall<_lambda_29772b305d449e03bde9e75e95bbf6c4_>(v39);
        v16 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x311,
            (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
            (const char *)(unsigned int)v23,
            ppv);
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          if ( pProxy )
            ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
          return v16;
        }
        v24 = (const WCHAR *)(v11 + 40);
        if ( *(_QWORD *)(v11 + 64) > 7u )
          v24 = *(const WCHAR **)v24;
        if ( (unsigned __int8)WaaS::Device::AreStringsNotEqualI(v24, (PCNZWCH)pv) )
        {
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          goto LABEL_67;
        }
        if ( pv )
          CoTaskMemFree(pv);
      }
      if ( *(_QWORD *)(v11 + 88) )
      {
        pv = 0;
        S2[0] = (wchar_t *)&v36;
        S2[1] = (wchar_t *)&pv;
        v25 = WaaS::ComTimeout::MakeComCall<_lambda_17081ffd41afdefee409225a436c3101_>(S2);
        v16 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x31C,
            (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
            (const char *)(unsigned int)v25,
            ppv);
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          if ( pProxy )
            ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
          return v16;
        }
        if ( *(_QWORD *)(v11 + 96) > 7u )
          v13 = *(const WCHAR **)v13;
        if ( (unsigned __int8)WaaS::Device::AreStringsNotEqualI(v13, (PCNZWCH)pv) )
        {
          if ( pv )
            CoTaskMemFree(pv);
          if ( v36 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          goto LABEL_67;
        }
        if ( pv )
          CoTaskMemFree(pv);
      }
      *(_BYTE *)(v11 + 104) = 1;
      if ( v36 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      goto LABEL_67;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2FE,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v20,
      ppv);
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
LABEL_67:
    if ( pProxy )
      ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    goto LABEL_69;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2FB,
    (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
    (const char *)(unsigned int)v18,
    ppv);
  if ( pProxy )
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
  return v16;
}

```

## disassembly

```asm
0x180050cac  push    rbp
0x180050cae  push    rbx
0x180050caf  push    rsi
0x180050cb0  push    rdi
0x180050cb1  push    r12
0x180050cb3  push    r13
0x180050cb5  push    r14
0x180050cb7  push    r15
0x180050cb9  lea     rbp, [rsp-1Fh]
0x180050cbe  sub     rsp, 0B8h
0x180050cc5  mov     rax, cs:__security_cookie
0x180050ccc  xor     rax, rsp
0x180050ccf  mov     [rbp+57h+var_48], rax
0x180050cd3  mov     rbx, r8
0x180050cd6  mov     r14, rdx
0x180050cd9  xor     r12d, r12d
0x180050cdc  mov     rdi, [r8+8]
0x180050ce0  cmp     rdi, [r8]
0x180050ce3  jz      loc_18005126F
0x180050ce9  xorps   xmm0, xmm0
0x180050cec  movups  xmmword ptr [rbp+57h+S2], xmm0
0x180050cf0  xorps   xmm1, xmm1
0x180050cf3  movdqu  [rbp+57h+var_68], xmm1
0x180050cf8  lea     r8d, [r12+24h]
0x180050cfd  lea     rdx, aDeviceDetectSo; "Device\\Detect\\Software\\HybridCompute"
0x180050d04  lea     rcx, [rbp+57h+S2]
0x180050d08  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180050d0d  mov     rsi, [rbx+8]
0x180050d11  mov     rbx, [rbx]
0x180050d14  jmp     short loc_180050D4F
0x180050d16  lea     rdx, [rbp+57h+S2]
0x180050d1a  cmp     qword ptr [rbp+57h+var_68+8], 7
0x180050d1f  cmova   rdx, [rbp+57h+S2]; S2
0x180050d24  mov     r8, [rbx+10h]; N
0x180050d28  cmp     qword ptr [rbx+18h], 7
0x180050d2d  jbe     short loc_180050D34
0x180050d2f  mov     rcx, [rbx]
0x180050d32  jmp     short loc_180050D37
0x180050d34  mov     rcx, rbx; S1
0x180050d37  cmp     r8, qword ptr [rbp+57h+var_68]
0x180050d3b  jnz     short loc_180050D4B
0x180050d3d  test    r8, r8
0x180050d40  jz      short loc_180050D54
0x180050d42  call    wmemcmp
0x180050d47  test    eax, eax
0x180050d49  jz      short loc_180050D54
0x180050d4b  add     rbx, 20h ; ' '
0x180050d4f  cmp     rbx, rsi
0x180050d52  jnz     short loc_180050D16
0x180050d54  lea     rcx, [rbp+57h+S2]; void *
0x180050d58  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050d5d  cmp     rdi, rbx
0x180050d60  jz      loc_18005126F
0x180050d66  mov     rbx, [r14]
0x180050d69  mov     r15, [r14+8]
0x180050d6d  cmp     rbx, r15
0x180050d70  jz      loc_18005104D
0x180050d76  lea     r13, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180050d7d  cmp     [rbx+68h], r12b
0x180050d81  jnz     loc_180051040
0x180050d87  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180050d8e  movdqu  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x180050d93  lea     rsi, [rbx+48h]
0x180050d97  cmp     qword ptr [rbx+60h], 7
0x180050d9c  jbe     short loc_180050DA3
0x180050d9e  mov     rcx, [rsi]
0x180050da1  jmp     short loc_180050DA6
0x180050da3  mov     rcx, rsi; StringUuid
0x180050da6  lea     rdx, [rbp+57h+Uuid]; Uuid
0x180050daa  call    cs:__imp_UuidFromStringW
0x180050db0  mov     edi, eax
0x180050db2  cmp     eax, 1
0x180050db5  jl      short loc_180050DC0
0x180050db7  movzx   edi, ax
0x180050dba  or      edi, 80010000h
0x180050dc0  test    edi, edi
0x180050dc2  js      loc_180051185
0x180050dc8  mov     [rbp+57h+pProxy], r12
0x180050dcc  lea     rax, [rbp+57h+pProxy]
0x180050dd0  mov     [rsp+0F0h+ppv], rax; int
0x180050dd5  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180050ddc  xor     edx, edx; pUnkOuter
0x180050dde  lea     r8d, [rdx+4]; dwClsContext
0x180050de2  lea     rcx, [rbp+57h+Uuid]; rclsid
0x180050de6  call    cs:__imp_CoCreateInstance
0x180050dec  mov     rcx, [rbp+5Fh]; this
0x180050df0  test    eax, eax
0x180050df2  jns     short loc_180050E0A
0x180050df4  mov     r9d, eax; char *
0x180050df7  mov     r8, r13; unsigned int
0x180050dfa  mov     edx, 2EFh; void *
0x180050dff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050e04  nop
0x180050e05  jmp     loc_18005102A
0x180050e0a  mov     [rsp+0F0h+dwCapabilities], r12d; dwCapabilities
0x180050e0f  mov     [rsp+0F0h+pAuthInfo], r12; pAuthInfo
0x180050e14  mov     [rsp+0F0h+dwImpLevel], 2; dwImpLevel
0x180050e1c  mov     dword ptr [rsp+0F0h+ppv], r12d; int
0x180050e21  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x180050e25  or      eax, 0FFFFFFFFh
0x180050e28  mov     r8d, eax; dwAuthzSvc
0x180050e2b  mov     edx, eax; dwAuthnSvc
0x180050e2d  mov     rcx, [rbp+57h+pProxy]; pProxy
0x180050e31  call    cs:__imp_CoSetProxyBlanket
0x180050e37  mov     edi, eax
0x180050e39  test    eax, eax
0x180050e3b  js      loc_180051158
0x180050e41  mov     [rbp+57h+var_A8], r12
0x180050e45  mov     rcx, [rbp+57h+pProxy]
0x180050e49  mov     rax, [rcx]
0x180050e4c  mov     [rbp+57h+var_A8], r12
0x180050e50  lea     r8, [rbp+57h+var_A8]
0x180050e54  lea     rdx, _GUID_dfcee1c8_648e_4903_8ac1_f8a18d35e524
0x180050e5b  mov     rax, [rax]
0x180050e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e63  mov     rcx, [rbp+5Fh]; this
0x180050e67  test    eax, eax
0x180050e69  jns     short loc_180050E97
0x180050e6b  mov     r9d, eax; char *
0x180050e6e  mov     r8, r13; unsigned int
0x180050e71  mov     edx, 2FEh; void *
0x180050e76  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180050e7b  nop
0x180050e7c  mov     rcx, [rbp+57h+var_A8]
0x180050e80  test    rcx, rcx
0x180050e83  jz      short loc_180050E92
0x180050e85  mov     rax, [rcx]
0x180050e88  mov     rax, [rax+10h]
0x180050e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e91  nop
0x180050e92  jmp     loc_18005102A
0x180050e97  cmp     [rbx+18h], r12
0x180050e9b  jz      short loc_180050F16
0x180050e9d  mov     [rbp+57h+pv], r12
0x180050ea1  lea     rax, [rbp+57h+var_A8]
0x180050ea5  mov     [rbp+57h+var_98], rax
0x180050ea9  lea     rax, [rbp+57h+pv]
0x180050ead  mov     [rbp+57h+var_90], rax
0x180050eb1  lea     rcx, [rbp+57h+var_98]
0x180050eb5  call    ??$MakeComCall@V_lambda_6367910aca77f9e7ff545ce583bdabd5_@@@ComTimeout@WaaS@@SAJAEBV_lambda_6367910aca77f9e7ff545ce583bdabd5_@@K@Z; WaaS::ComTimeout::MakeComCall<_lambda_6367910aca77f9e7ff545ce583bdabd5_>(_lambda_6367910aca77f9e7ff545ce583bdabd5_ const &,ulong)
0x180050eba  mov     edi, eax
0x180050ebc  test    eax, eax
0x180050ebe  js      loc_180051059
0x180050ec4  lea     rcx, [rbx+8]
0x180050ec8  cmp     qword ptr [rbx+20h], 7
0x180050ecd  jbe     short loc_180050ED2
0x180050ecf  mov     rcx, [rcx]; lpString1
0x180050ed2  mov     rdx, [rbp+57h+pv]; lpString2
0x180050ed6  call    WaaS__Device__AreStringsNotEqualI
0x180050edb  nop
0x180050edc  mov     rcx, [rbp+57h+pv]; pv
0x180050ee0  test    al, al
0x180050ee2  jz      short loc_180050F0B
0x180050ee4  test    rcx, rcx
0x180050ee7  jz      short loc_180050EF0
0x180050ee9  call    cs:__imp_CoTaskMemFree
0x180050eef  nop
0x180050ef0  mov     rcx, [rbp+57h+var_A8]
0x180050ef4  test    rcx, rcx
0x180050ef7  jz      short loc_180050F06
0x180050ef9  mov     rax, [rcx]
0x180050efc  mov     rax, [rax+10h]
0x180050f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f05  nop
0x180050f06  jmp     loc_18005102A
0x180050f0b  test    rcx, rcx
0x180050f0e  jz      short loc_180050F16
0x180050f10  call    cs:__imp_CoTaskMemFree
0x180050f16  cmp     [rbx+38h], r12
0x180050f1a  jz      short loc_180050F95
0x180050f1c  mov     [rbp+57h+pv], r12
0x180050f20  lea     rax, [rbp+57h+var_A8]
0x180050f24  mov     [rbp+57h+var_88], rax
0x180050f28  lea     rax, [rbp+57h+pv]
0x180050f2c  mov     [rbp+57h+var_80], rax
0x180050f30  lea     rcx, [rbp+57h+var_88]
0x180050f34  call    ??$MakeComCall@V_lambda_29772b305d449e03bde9e75e95bbf6c4_@@@ComTimeout@WaaS@@SAJAEBV_lambda_29772b305d449e03bde9e75e95bbf6c4_@@K@Z; WaaS::ComTimeout::MakeComCall<_lambda_29772b305d449e03bde9e75e95bbf6c4_>(_lambda_29772b305d449e03bde9e75e95bbf6c4_ const &,ulong)
0x180050f39  mov     edi, eax
0x180050f3b  test    eax, eax
0x180050f3d  js      loc_1800510AF
0x180050f43  lea     rcx, [rbx+28h]
0x180050f47  cmp     qword ptr [rbx+40h], 7
0x180050f4c  jbe     short loc_180050F51
0x180050f4e  mov     rcx, [rcx]; lpString1
0x180050f51  mov     rdx, [rbp+57h+pv]; lpString2
0x180050f55  call    WaaS__Device__AreStringsNotEqualI
0x180050f5a  nop
0x180050f5b  mov     rcx, [rbp+57h+pv]; pv
0x180050f5f  test    al, al
0x180050f61  jz      short loc_180050F8A
0x180050f63  test    rcx, rcx
0x180050f66  jz      short loc_180050F6F
0x180050f68  call    cs:__imp_CoTaskMemFree
0x180050f6e  nop
0x180050f6f  mov     rcx, [rbp+57h+var_A8]
0x180050f73  test    rcx, rcx
0x180050f76  jz      short loc_180050F85
0x180050f78  mov     rax, [rcx]
0x180050f7b  mov     rax, [rax+10h]
0x180050f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f84  nop
0x180050f85  jmp     loc_18005102A
0x180050f8a  test    rcx, rcx
0x180050f8d  jz      short loc_180050F95
0x180050f8f  call    cs:__imp_CoTaskMemFree
0x180050f95  cmp     [rbx+58h], r12
0x180050f99  jz      short loc_180051010
0x180050f9b  mov     [rbp+57h+pv], r12
0x180050f9f  lea     rax, [rbp+57h+var_A8]
0x180050fa3  mov     [rbp+57h+S2], rax
0x180050fa7  lea     rax, [rbp+57h+pv]
0x180050fab  mov     [rbp+57h+S2+8], rax
0x180050faf  lea     rcx, [rbp+57h+S2]
0x180050fb3  call    ??$MakeComCall@V_lambda_17081ffd41afdefee409225a436c3101_@@@ComTimeout@WaaS@@SAJAEBV_lambda_17081ffd41afdefee409225a436c3101_@@K@Z; WaaS::ComTimeout::MakeComCall<_lambda_17081ffd41afdefee409225a436c3101_>(_lambda_17081ffd41afdefee409225a436c3101_ const &,ulong)
0x180050fb8  mov     edi, eax
0x180050fba  test    eax, eax
0x180050fbc  js      loc_180051105
0x180050fc2  cmp     qword ptr [rbx+60h], 7
0x180050fc7  jbe     short loc_180050FCC
0x180050fc9  mov     rsi, [rsi]
0x180050fcc  mov     rdx, [rbp+57h+pv]; lpString2
0x180050fd0  mov     rcx, rsi; lpString1
0x180050fd3  call    WaaS__Device__AreStringsNotEqualI
0x180050fd8  nop
0x180050fd9  mov     rcx, [rbp+57h+pv]; pv
0x180050fdd  test    al, al
0x180050fdf  jz      short loc_180051005
0x180050fe1  test    rcx, rcx
0x180050fe4  jz      short loc_180050FED
0x180050fe6  call    cs:__imp_CoTaskMemFree
0x180050fec  nop
0x180050fed  mov     rcx, [rbp+57h+var_A8]
0x180050ff1  test    rcx, rcx
0x180050ff4  jz      short loc_180051003
0x180050ff6  mov     rax, [rcx]
0x180050ff9  mov     rax, [rax+10h]
0x180050ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051002  nop
0x180051003  jmp     short loc_18005102A
0x180051005  test    rcx, rcx
0x180051008  jz      short loc_180051010
0x18005100a  call    cs:__imp_CoTaskMemFree
0x180051010  mov     byte ptr [rbx+68h], 1
0x180051014  mov     rcx, [rbp+57h+var_A8]
0x180051018  test    rcx, rcx
0x18005101b  jz      short loc_18005102A
0x18005101d  mov     rax, [rcx]
0x180051020  mov     rax, [rax+10h]
0x180051024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051029  nop
0x18005102a  mov     rcx, [rbp+57h+pProxy]
0x18005102e  test    rcx, rcx
0x180051031  jz      short loc_180051040
0x180051033  mov     rax, [rcx]
0x180051036  mov     rax, [rax+10h]
0x18005103a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005103f  nop
0x180051040  add     rbx, 70h ; 'p'
0x180051044  cmp     rbx, r15
0x180051047  jnz     loc_180050D7D
0x18005104d  mov     rdi, [r14+8]
0x180051051  mov     rbx, [r14]
0x180051054  jmp     loc_1800511AA
0x180051059  mov     rcx, [rbp+5Fh]; this
0x18005105d  mov     r9d, edi; char *
0x180051060  mov     r8, r13; unsigned int
0x180051063  mov     edx, 306h; void *
0x180051068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005106d  nop
0x18005106e  mov     rcx, [rbp+57h+pv]; pv
0x180051072  test    rcx, rcx
0x180051075  jz      short loc_18005107E
0x180051077  call    cs:__imp_CoTaskMemFree
0x18005107d  nop
0x18005107e  mov     rcx, [rbp+57h+var_A8]
0x180051082  test    rcx, rcx
0x180051085  jz      short loc_180051094
0x180051087  mov     rax, [rcx]
0x18005108a  mov     rax, [rax+10h]
0x18005108e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051093  nop
0x180051094  mov     rcx, [rbp+57h+pProxy]
0x180051098  test    rcx, rcx
0x18005109b  jz      short loc_1800510AA
0x18005109d  mov     rax, [rcx]
0x1800510a0  mov     rax, [rax+10h]
0x1800510a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800510a9  nop
0x1800510aa  jmp     loc_180051199
0x1800510af  mov     rcx, [rbp+5Fh]; this
0x1800510b3  mov     r9d, edi; char *
0x1800510b6  mov     r8, r13; unsigned int
0x1800510b9  mov     edx, 311h; void *
0x1800510be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800510c3  nop
0x1800510c4  mov     rcx, [rbp+57h+pv]; pv
0x1800510c8  test    rcx, rcx
0x1800510cb  jz      short loc_1800510D4
0x1800510cd  call    cs:__imp_CoTaskMemFree
0x1800510d3  nop
  ... truncated ...
```
