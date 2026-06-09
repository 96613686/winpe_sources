# EffectPack::GetMinProcessingPeriodForExclusiveMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,__int64 *)

- ea: `0x180039650`
- end: `0x180039adc`
- name: `?GetMinProcessingPeriodForExclusiveMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEA_J@Z`
- size: `1164`
- prototype: `__int64 __fastcall(EffectPack *__hidden this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, __int64 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038f90`
- `0x180082d10`

## callees

- `0x18001280c`
- `0x1800208b0`
- `0x180022800`
- `0x180039650`
- `0x180039ae4`
- `0x180039f10`
- `0x18003a1e0`
- `0x18003a608`
- `0x18003d040`
- `0x18004f298`
- `0x1800cd8d0`
- `0x1800ce750`
- `0x18016c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180039ad5`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180039ad5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039ace`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180039ace`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800397a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039a85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039a94`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800397a3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039a85`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039a94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180039a37`

## string_xrefs

- `0x180039a14`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180039a6f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EffectPack::GetMinProcessingPeriodForExclusiveMode(
        EffectPack *this,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a2,
        __int64 *a3)
{
  __int64 SupportedConnectorModesInternal; // r8
  int i; // edx
  _QWORD *v7; // rcx
  LONGLONG v8; // rax
  struct _GUID *DefaultConnectorProcessingModeInternal; // rax
  struct _GUID v10; // xmm6
  unsigned int j; // ebx
  LPVOID *v12; // rdx
  void *v13; // rcx
  int ProposedConnectorFormatForProcessingMode; // ebx
  __int64 v15; // r8
  int k; // ecx
  _QWORD *v17; // rdx
  LONGLONG v18; // rax
  struct _GUID *p_Buf2; // rcx
  const struct tWAVEFORMATEX *v20; // r14
  __int64 v21; // rax
  _QWORD *v22; // rdi
  _QWORD *v23; // r15
  _QWORD *v24; // rcx
  LONGLONG v25; // rax
  const struct tWAVEFORMATEX ***v26; // rbx
  const struct tWAVEFORMATEX ***v27; // rsi
  __int64 v28; // rax
  void *v29; // rcx
  int m; // eax
  _QWORD *v32; // rdx
  LONGLONG v33; // rcx
  GUID v34; // xmm0
  void *v35; // rcx
  int v36; // eax
  int v37; // [rsp+28h] [rbp-59h]
  struct tagPROPVARIANT Buf2; // [rsp+38h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-29h] BYREF
  LPVOID *p_pv; // [rsp+60h] [rbp-21h]
  struct tWAVEFORMATEX *v41; // [rsp+68h] [rbp-19h] BYREF
  char v42; // [rsp+70h] [rbp-11h]
  struct _GUID v43; // [rsp+78h] [rbp-9h] BYREF
  unsigned int v44; // [rsp+88h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  pv = 0;
  *(GUID *)&Buf2.vt = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
  SupportedConnectorModesInternal = EffectPack::GetSupportedConnectorModesInternal(this, 0, 0, 0);
  for ( i = 0; ; ++i )
  {
    if ( i >= *(_DWORD *)(SupportedConnectorModesInternal + 8) )
      goto LABEL_8;
    v7 = (_QWORD *)(*(_QWORD *)SupportedConnectorModesInternal + 16LL * i);
    v8 = *v7 - *(_QWORD *)&Buf2.vt;
    if ( *v7 == *(_QWORD *)&Buf2.vt )
      v8 = v7[1] - Buf2.hVal.QuadPart;
    if ( !v8 )
      break;
  }
  if ( i == -1 )
  {
LABEL_8:
    DefaultConnectorProcessingModeInternal = (struct _GUID *)EffectPack::GetDefaultConnectorProcessingModeInternal(
                                                               this,
                                                               &v43,
                                                               0,
                                                               0);
    goto LABEL_9;
  }
  *(GUID *)&Buf2.vt = GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf;
  DefaultConnectorProcessingModeInternal = (struct _GUID *)&Buf2;
LABEL_9:
  v10 = *DefaultConnectorProcessingModeInternal;
  *a3 = 0;
  p_pv = &pv;
  v41 = 0;
  v42 = 1;
  v43 = 0;
  v44 = 0;
  *(struct _GUID *)&Buf2.vt = v10;
  for ( j = 0; j < 0xA; ++j )
  {
    if ( !memcmp_0(&qword_180188140[2 * j], &Buf2, 0x10u) )
    {
      v43 = (struct _GUID)PKEY_AudioEngine_SignalProcessingMode_Specific_ConnectorFormat;
      v44 = j + 2;
      memset(&Buf2, 0, sizeof(Buf2));
      if ( (*(int (__fastcall **)(_QWORD, struct _GUID *, struct tagPROPVARIANT *))(**(_QWORD **)(*((_QWORD *)this + 198)
                                                                                                + 72LL)
                                                                                  + 40LL))(
             *(_QWORD *)(*((_QWORD *)this + 198) + 72LL),
             &v43,
             &Buf2) >= 0
        && Buf2.vt == 65
        && IsValidWfxBlob(&Buf2) )
      {
        v36 = CloneWaveFormat((const struct tWAVEFORMATEX *)Buf2.bstrblobVal.pData, &v41);
        ProposedConnectorFormatForProcessingMode = v36;
        if ( v36 >= 0 )
        {
          PropVariantClear((PROPVARIANT *)&Buf2);
          ProposedConnectorFormatForProcessingMode = 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A13,
            (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
            (const char *)(unsigned int)v36,
            v37);
          PropVariantClear((PROPVARIANT *)&Buf2);
        }
        goto LABEL_17;
      }
      PropVariantClear((PROPVARIANT *)&Buf2);
      break;
    }
  }
  *(struct _GUID *)&Buf2.vt = v10;
  EffectPack::TranslateDeviceConnectorModeToStreamingConnectorMode(
    this,
    &v43,
    eHostProcessConnector,
    (struct _GUID *)&Buf2);
  ProposedConnectorFormatForProcessingMode = GetProposedConnectorFormatForProcessingMode(
                                               g_DeviceEnumerator,
                                               *(struct IPropertyStore **)(*((_QWORD *)this + 198) + 72LL),
                                               eHostProcessConnector,
                                               &v43,
                                               &v41);
  if ( ProposedConnectorFormatForProcessingMode < 0 )
    ProposedConnectorFormatForProcessingMode = EffectPack::GetDeviceFormat(this, 0, 0, eHostProcessConnector, &v41);
LABEL_17:
  if ( v42 )
  {
    v12 = p_pv;
    v13 = *p_pv;
    *p_pv = v41;
    if ( v13 )
      CoTaskMemFree(v13);
  }
  if ( ProposedConnectorFormatForProcessingMode < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2153,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)ProposedConnectorFormatForProcessingMode,
      v37);
    v35 = pv;
    pv = 0;
    if ( v35 )
      CoTaskMemFree(v35);
    return (unsigned int)ProposedConnectorFormatForProcessingMode;
  }
  else
  {
    *a3 = 30000;
    if ( !*((_QWORD *)this + 236) )
    {
      _o_terminate(v13, v12);
      JUMPOUT(0x180039ADBLL);
    }
    v15 = *((_QWORD *)this + 237);
    *(struct _GUID *)&Buf2.vt = v10;
    for ( k = 0; ; ++k )
    {
      if ( k >= *(_DWORD *)(v15 + 16) )
        goto LABEL_28;
      v17 = (_QWORD *)(*(_QWORD *)v15 + 16LL * k);
      v18 = *v17 - *(_QWORD *)&Buf2.vt;
      if ( *v17 == *(_QWORD *)&Buf2.vt )
        v18 = v17[1] - Buf2.hVal.QuadPart;
      if ( !v18 )
        break;
    }
    if ( k == -1 )
    {
LABEL_28:
      v43 = v10;
      p_Buf2 = &v43;
      goto LABEL_29;
    }
    *(struct _GUID *)&Buf2.vt = v10;
    for ( m = 0; ; ++m )
    {
      if ( m >= *(_DWORD *)(v15 + 16) )
        goto LABEL_58;
      v32 = (_QWORD *)(*(_QWORD *)v15 + 16LL * m);
      v33 = *v32 - *(_QWORD *)&Buf2.vt;
      if ( *v32 == *(_QWORD *)&Buf2.vt )
        v33 = v32[1] - Buf2.hVal.QuadPart;
      if ( !v33 )
        break;
    }
    if ( m == -1 )
    {
LABEL_58:
      v34 = GUID_00000000_0000_0000_0000_000000000000;
      goto LABEL_56;
    }
    if ( m < 0 )
    {
      RaiseException(0xC000008C, 1u, 0, 0);
      __debugbreak();
    }
    v34 = *(GUID *)(*(_QWORD *)(v15 + 8) + 16LL * m);
LABEL_56:
    *(GUID *)&Buf2.vt = v34;
    p_Buf2 = (struct _GUID *)&Buf2;
LABEL_29:
    v20 = (const struct tWAVEFORMATEX *)pv;
    v21 = *((_QWORD *)this + 198);
    *(struct _GUID *)&Buf2.vt = *p_Buf2;
    v22 = *(_QWORD **)(v21 + 272);
    v23 = *(_QWORD **)(v21 + 280);
    while ( v22 != v23 )
    {
      v24 = (_QWORD *)*v22;
      v25 = *(_QWORD *)*v22 - *(_QWORD *)&Buf2.vt;
      if ( !v25 )
        v25 = v24[1] - Buf2.hVal.QuadPart;
      if ( !v25 )
      {
        v26 = (const struct tWAVEFORMATEX ***)v24[2];
        v27 = (const struct tWAVEFORMATEX ***)v24[3];
        while ( v26 != v27 )
        {
          if ( (unsigned int)CompareWaveFormat(v20, **v26) )
          {
            v28 = (unsigned int)(int)((double)*((int *)*v26 + 4) * 10000000.0 / (double)(int)v20->nSamplesPerSec + 0.5);
            if ( v28 >= *a3 )
              v28 = *a3;
            *a3 = v28;
            goto LABEL_40;
          }
          ++v26;
        }
      }
      ++v22;
    }
LABEL_40:
    v29 = pv;
    pv = 0;
    if ( v29 )
      CoTaskMemFree(v29);
    return 0;
  }
}

```

## disassembly

```asm
0x180039650  mov     rax, rsp
0x180039653  mov     [rax+10h], rbx
0x180039657  mov     [rax+20h], rsi
0x18003965b  push    rbp
0x18003965c  push    rdi
0x18003965d  push    r12
0x18003965f  push    r14
0x180039661  push    r15
0x180039663  lea     rbp, [rax-5Fh]
0x180039667  sub     rsp, 0B0h
0x18003966e  movaps  xmmword ptr [rax-38h], xmm6
0x180039672  mov     rax, cs:__security_cookie
0x180039679  xor     rax, rsp
0x18003967c  mov     [rbp+57h+var_40], rax
0x180039680  mov     r12, r8
0x180039683  mov     rdi, rcx
0x180039686  mov     [rbp+57h+pv], 0
0x18003968e  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180039695  movdqa  [rbp+57h+Buf2], xmm0
0x18003969a  xor     r9d, r9d
0x18003969d  xor     r8d, r8d
0x1800396a0  xor     edx, edx
0x1800396a2  call    ?GetSupportedConnectorModesInternal@EffectPack@@AEAAPEAVCAudioSignalProcessingModeArray@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetSupportedConnectorModesInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration,SED_RESOLVEOPT)
0x1800396a7  mov     r8, rax
0x1800396aa  xor     edx, edx
0x1800396ac  lea     esi, [rdx+1]
0x1800396af  cmp     edx, [r8+8]
0x1800396b3  jge     short loc_1800396E2
0x1800396b5  movsxd  rcx, edx
0x1800396b8  shl     rcx, 4
0x1800396bc  add     rcx, [r8]
0x1800396bf  mov     rax, [rcx]
0x1800396c2  sub     rax, qword ptr [rbp+57h+Buf2]
0x1800396c6  jnz     short loc_1800396D0
0x1800396c8  mov     rax, [rcx+8]
0x1800396cc  sub     rax, qword ptr [rbp+57h+Buf2+8]
0x1800396d0  test    rax, rax
0x1800396d3  jz      short loc_1800396D9
0x1800396d5  add     edx, esi
0x1800396d7  jmp     short loc_1800396AF
0x1800396d9  cmp     edx, 0FFFFFFFFh
0x1800396dc  jnz     loc_18003998D
0x1800396e2  xor     r9d, r9d
0x1800396e5  xor     r8d, r8d
0x1800396e8  lea     rdx, [rbp+57h+var_60]
0x1800396ec  mov     rcx, rdi
0x1800396ef  call    ?GetDefaultConnectorProcessingModeInternal@EffectPack@@AEAA?AU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetDefaultConnectorProcessingModeInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,SED_RESOLVEOPT)
0x1800396f4  movups  xmm6, xmmword ptr [rax]
0x1800396f7  mov     qword ptr [r12], 0
0x1800396ff  lea     rax, [rbp+57h+pv]
0x180039703  mov     [rbp+57h+var_78], rax
0x180039707  mov     [rbp+57h+var_70], 0
0x18003970f  mov     [rbp+57h+var_68], sil
0x180039713  xorps   xmm0, xmm0
0x180039716  xor     eax, eax
0x180039718  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x18003971c  mov     [rbp+57h+var_50], eax
0x18003971f  movdqa  [rbp+57h+Buf2], xmm6
0x180039724  xor     ebx, ebx
0x180039726  cmp     ebx, 0Ah
0x180039729  jnb     short loc_1800397A9
0x18003972b  mov     ecx, ebx
0x18003972d  shl     rcx, 4
0x180039731  lea     rax, qword_180188140
0x180039738  add     rcx, rax; Buf1
0x18003973b  mov     r8d, 10h; Size
0x180039741  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180039745  call    memcmp_0
0x18003974a  test    eax, eax
0x18003974c  jnz     loc_18003997F
0x180039752  movups  xmm0, cs:PKEY_AudioEngine_SignalProcessingMode_Specific_ConnectorFormat
0x180039759  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x18003975e  lea     eax, [rbx+2]
0x180039761  mov     [rbp+57h+var_50], eax
0x180039764  xorps   xmm0, xmm0
0x180039767  xor     eax, eax
0x180039769  movups  [rbp+57h+Buf2], xmm0
0x18003976d  mov     [rbp+57h+Src], rax
0x180039771  mov     rax, [rdi+630h]
0x180039778  mov     rcx, [rax+48h]
0x18003977c  mov     rax, [rcx]
0x18003977f  lea     r8, [rbp+57h+Buf2]
0x180039783  lea     rdx, [rbp+57h+var_60]
0x180039787  mov     rax, [rax+28h]
0x18003978b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039790  test    eax, eax
0x180039792  js      short loc_18003979F
0x180039794  cmp     word ptr [rbp+57h+Buf2], 41h ; 'A'
0x180039799  jz      loc_180039A44
0x18003979f  lea     rcx, [rbp+57h+Buf2]; pvar
0x1800397a3  call    cs:__imp_PropVariantClear
0x1800397a9  movdqa  [rbp+57h+Buf2], xmm6
0x1800397ae  lea     r9, [rbp+57h+Buf2]; struct _GUID
0x1800397b2  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800397b5  lea     rdx, [rbp+57h+var_60]; retstr
0x1800397b9  mov     rcx, rdi; this
0x1800397bc  call    ?TranslateDeviceConnectorModeToStreamingConnectorMode@EffectPack@@QEAA?AU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U2@@Z; EffectPack::TranslateDeviceConnectorModeToStreamingConnectorMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID)
0x1800397c1  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x1800397c5  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x1800397ca  mov     rdx, [rdi+630h]
0x1800397d1  lea     rax, [rbp+57h+var_70]
0x1800397d5  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800397da  lea     r9, [rbp+57h+var_60]; struct _GUID *
0x1800397de  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1800397e1  mov     rdx, [rdx+48h]; struct IPropertyStore *
0x1800397e5  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; struct IMMDeviceEnumerator *
0x1800397ec  call    ?GetProposedConnectorFormatForProcessingMode@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; GetProposedConnectorFormatForProcessingMode(IMMDeviceEnumerator *,IPropertyStore *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x1800397f1  mov     ebx, eax
0x1800397f3  test    eax, eax
0x1800397f5  js      loc_180039AA1
0x1800397fb  cmp     [rbp+57h+var_68], 0
0x1800397ff  jz      short loc_18003981A
0x180039801  mov     rdx, [rbp+57h+var_78]
0x180039805  mov     rcx, [rdx]; pv
0x180039808  mov     rax, [rbp+57h+var_70]
0x18003980c  mov     [rdx], rax
0x18003980f  test    rcx, rcx
0x180039812  jz      short loc_18003981A
0x180039814  call    cs:__imp_CoTaskMemFree
0x18003981a  test    ebx, ebx
0x18003981c  js      loc_180039A0D
0x180039822  mov     qword ptr [r12], 7530h
0x18003982a  cmp     qword ptr [rdi+760h], 0
0x180039832  jbe     loc_180039AD5
0x180039838  mov     r8, [rdi+768h]
0x18003983f  movdqa  [rbp+57h+Buf2], xmm6
0x180039844  xor     ecx, ecx
0x180039846  cmp     ecx, [r8+10h]
0x18003984a  jge     short loc_180039879
0x18003984c  movsxd  rdx, ecx
0x18003984f  shl     rdx, 4
0x180039853  add     rdx, [r8]
0x180039856  mov     rax, [rdx]
0x180039859  sub     rax, qword ptr [rbp+57h+Buf2]
0x18003985d  jnz     short loc_180039867
0x18003985f  mov     rax, [rdx+8]
0x180039863  sub     rax, qword ptr [rbp+57h+Buf2+8]
0x180039867  test    rax, rax
0x18003986a  jnz     loc_180039986
0x180039870  cmp     ecx, 0FFFFFFFFh
0x180039873  jnz     loc_1800399AB
0x180039879  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm6
0x18003987e  lea     rcx, [rbp+57h+var_60]
0x180039882  mov     r14, [rbp+57h+pv]
0x180039886  mov     rax, [rdi+630h]
0x18003988d  movups  xmm0, xmmword ptr [rcx]
0x180039890  movdqu  [rbp+57h+Buf2], xmm0
0x180039895  mov     rdi, [rax+110h]
0x18003989c  mov     r15, [rax+118h]
0x1800398a3  cmp     rdi, r15
0x1800398a6  jz      loc_180039930
0x1800398ac  mov     rcx, [rdi]
0x1800398af  mov     rax, [rcx]
0x1800398b2  sub     rax, qword ptr [rbp+57h+Buf2]
0x1800398b6  jnz     short loc_1800398C0
0x1800398b8  mov     rax, [rcx+8]
0x1800398bc  sub     rax, qword ptr [rbp+57h+Buf2+8]
0x1800398c0  test    rax, rax
0x1800398c3  jnz     loc_180039976
0x1800398c9  mov     rbx, [rcx+10h]
0x1800398cd  mov     rsi, [rcx+18h]
0x1800398d1  cmp     rbx, rsi
0x1800398d4  jz      loc_180039976
0x1800398da  mov     rdx, [rbx]
0x1800398dd  mov     rdx, [rdx]; struct tWAVEFORMATEX *
0x1800398e0  mov     rcx, r14; struct tWAVEFORMATEX *
0x1800398e3  call    ?CompareWaveFormat@@YAHPEBUtWAVEFORMATEX@@0@Z; CompareWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x1800398e8  test    eax, eax
0x1800398ea  jz      loc_1800399A2
0x1800398f0  mov     rax, [rbx]
0x1800398f3  mov     ecx, [rax+10h]
0x1800398f6  xorps   xmm1, xmm1
0x1800398f9  cvtsi2sd xmm1, rcx
0x1800398fe  mulsd   xmm1, cs:__real@416312d000000000
0x180039906  mov     eax, [r14+4]
0x18003990a  xorps   xmm0, xmm0
0x18003990d  cvtsi2sd xmm0, rax
0x180039912  divsd   xmm1, xmm0
0x180039916  addsd   xmm1, cs:__real@3fe0000000000000
0x18003991e  cvttsd2si rax, xmm1
0x180039923  cmp     rax, [r12]
0x180039927  cmovge  rax, [r12]
0x18003992c  mov     [r12], rax
0x180039930  mov     rcx, [rbp+57h+pv]; pv
0x180039934  mov     [rbp+57h+pv], 0
0x18003993c  test    rcx, rcx
0x18003993f  jz      short loc_180039947
0x180039941  call    cs:__imp_CoTaskMemFree
0x180039947  xor     eax, eax
0x180039949  mov     rcx, [rbp+57h+var_40]
0x18003994d  xor     rcx, rsp; StackCookie
0x180039950  call    __security_check_cookie
0x180039955  lea     r11, [rsp+0D0h+var_20]
0x18003995d  mov     rbx, [r11+38h]
0x180039961  mov     rsi, [r11+48h]
0x180039965  movaps  xmm6, xmmword ptr [r11-10h]
0x18003996a  mov     rsp, r11
0x18003996d  pop     r15
0x18003996f  pop     r14
0x180039971  pop     r12
0x180039973  pop     rdi
0x180039974  pop     rbp
0x180039975  retn
0x180039976  add     rdi, 8
0x18003997a  jmp     loc_1800398A3
0x18003997f  add     ebx, esi
0x180039981  jmp     loc_180039726
0x180039986  add     ecx, esi
0x180039988  jmp     loc_180039846
0x18003998d  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180039994  movdqu  [rbp+57h+Buf2], xmm0
0x180039999  lea     rax, [rbp+57h+Buf2]
0x18003999d  jmp     loc_1800396F4
0x1800399a2  add     rbx, 8
0x1800399a6  jmp     loc_1800398D1
0x1800399ab  movdqa  [rbp+57h+Buf2], xmm6
0x1800399b0  xor     eax, eax
0x1800399b2  cmp     eax, [r8+10h]
0x1800399b6  jge     short loc_180039A04
0x1800399b8  movsxd  rdx, eax
0x1800399bb  shl     rdx, 4
0x1800399bf  add     rdx, [r8]
0x1800399c2  mov     rcx, [rdx]
0x1800399c5  sub     rcx, qword ptr [rbp+57h+Buf2]
0x1800399c9  jnz     short loc_1800399D3
0x1800399cb  mov     rcx, [rdx+8]
0x1800399cf  sub     rcx, qword ptr [rbp+57h+Buf2+8]
0x1800399d3  test    rcx, rcx
0x1800399d6  jnz     short loc_180039A00
0x1800399d8  cmp     eax, 0FFFFFFFFh
0x1800399db  jz      short loc_180039A04
0x1800399dd  test    eax, eax
0x1800399df  js      loc_180039AC1
0x1800399e5  cdqe
0x1800399e7  shl     rax, 4
0x1800399eb  add     rax, [r8+8]
0x1800399ef  movups  xmm0, xmmword ptr [rax]
0x1800399f2  movdqu  [rbp+57h+Buf2], xmm0
0x1800399f7  lea     rcx, [rbp+57h+Buf2]
0x1800399fb  jmp     loc_180039882
0x180039a00  add     eax, esi
0x180039a02  jmp     short loc_1800399B2
0x180039a04  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180039a0b  jmp     short loc_1800399F2
0x180039a0d  mov     rcx, [rbp+5Fh]; this
0x180039a11  mov     r9d, ebx; char *
0x180039a14  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180039a1b  mov     edx, 2153h; void *
0x180039a20  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a25  nop
0x180039a26  mov     rcx, [rbp+57h+pv]; pv
0x180039a2a  mov     [rbp+57h+pv], 0
0x180039a32  test    rcx, rcx
0x180039a35  jz      short loc_180039A3D
0x180039a37  call    cs:__imp_CoTaskMemFree
0x180039a3d  mov     eax, ebx
0x180039a3f  jmp     loc_180039949
0x180039a44  lea     rcx, [rbp+57h+Buf2]; struct tagPROPVARIANT *
0x180039a48  call    ?IsValidWfxBlob@@YAHPEAUtagPROPVARIANT@@@Z; IsValidWfxBlob(tagPROPVARIANT *)
0x180039a4d  test    eax, eax
0x180039a4f  jz      loc_18003979F
0x180039a55  lea     rdx, [rbp+57h+var_70]; struct tWAVEFORMATEX **
0x180039a59  mov     rcx, [rbp+57h+Src]; Src
0x180039a5d  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180039a62  mov     ebx, eax
0x180039a64  test    eax, eax
0x180039a66  jns     short loc_180039A90
0x180039a68  mov     rcx, [rbp+5Fh]; this
0x180039a6c  mov     r9d, eax; char *
0x180039a6f  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180039a76  mov     edx, 1A13h; void *
0x180039a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a80  nop
0x180039a81  lea     rcx, [rbp+57h+Buf2]; pvar
0x180039a85  call    cs:__imp_PropVariantClear
0x180039a8b  jmp     loc_1800397FB
0x180039a90  lea     rcx, [rbp+57h+Buf2]; pvar
0x180039a94  call    cs:__imp_PropVariantClear
0x180039a9a  xor     ebx, ebx
0x180039a9c  jmp     loc_1800397FB
0x180039aa1  lea     rax, [rbp+57h+var_70]
0x180039aa5  mov     qword ptr [rsp+0D0h+var_B0], rax; struct tWAVEFORMATEX **
0x180039aaa  xor     r9d, r9d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180039aad  xor     r8d, r8d; bool
0x180039ab0  xor     edx, edx; bool
0x180039ab2  mov     rcx, rdi; this
0x180039ab5  call    ?GetDeviceFormat@EffectPack@@QEAAJ_N0W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetDeviceFormat(bool,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX * *)
0x180039aba  mov     ebx, eax
0x180039abc  jmp     loc_1800397FB
0x180039ac1  xor     r9d, r9d; lpArguments
0x180039ac4  xor     r8d, r8d; nNumberOfArguments
0x180039ac7  mov     edx, esi; dwExceptionFlags
0x180039ac9  mov     ecx, 0C000008Ch; dwExceptionCode
0x180039ace  call    cs:__imp_RaiseException
0x180039ad4  int     3; Trap to Debugger
0x180039ad5  call    cs:__imp__o_terminate
```
