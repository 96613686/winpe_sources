# EffectPack::GetMinProcessingPeriodForExclusiveMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,__int64 *)

- ea: `0x1800394f0`
- end: `0x18003997c`
- name: `?GetMinProcessingPeriodForExclusiveMode@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEA_J@Z`
- size: `1164`
- prototype: `__int64 __fastcall(EffectPack *__hidden this, enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001, __int64 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038e30`
- `0x180083210`

## callees

- `0x1800126bc`
- `0x180020760`
- `0x1800226b0`
- `0x1800394f0`
- `0x180039984`
- `0x180039db0`
- `0x18003a080`
- `0x18003a4a8`
- `0x18003cee0`
- `0x18004f728`
- `0x1800cf8c0`
- `0x1800d0740`
- `0x18016b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180039975`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180039975`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003996e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003996e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039643`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039925`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039934`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039643`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039925`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180039934`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800396b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800397e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800398d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800396b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800397e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800398d7`

## string_xrefs

- `0x1800398b4`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18003990f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
    if ( !memcmp_0((char *)&unk_1801870E0 + 16 * j, &Buf2, 0x10u) )
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
        && (unsigned int)IsValidWfxBlob(&Buf2) )
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
            (void *)0x1A14,
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
      (void *)0x2154,
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
      JUMPOUT(0x18003997BLL);
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
0x1800394f0  mov     rax, rsp
0x1800394f3  mov     [rax+10h], rbx
0x1800394f7  mov     [rax+20h], rsi
0x1800394fb  push    rbp
0x1800394fc  push    rdi
0x1800394fd  push    r12
0x1800394ff  push    r14
0x180039501  push    r15
0x180039503  lea     rbp, [rax-5Fh]
0x180039507  sub     rsp, 0B0h
0x18003950e  movaps  xmmword ptr [rax-38h], xmm6
0x180039512  mov     rax, cs:__security_cookie
0x180039519  xor     rax, rsp
0x18003951c  mov     [rbp+57h+var_40], rax
0x180039520  mov     r12, r8
0x180039523  mov     rdi, rcx
0x180039526  mov     [rbp+57h+pv], 0
0x18003952e  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180039535  movdqa  [rbp+57h+Buf2], xmm0
0x18003953a  xor     r9d, r9d
0x18003953d  xor     r8d, r8d
0x180039540  xor     edx, edx
0x180039542  call    ?GetSupportedConnectorModesInternal@EffectPack@@AEAAPEAVCAudioSignalProcessingModeArray@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4FXEnablementConsideration@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetSupportedConnectorModesInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,FXEnablementConsideration,SED_RESOLVEOPT)
0x180039547  mov     r8, rax
0x18003954a  xor     edx, edx
0x18003954c  lea     esi, [rdx+1]
0x18003954f  cmp     edx, [r8+8]
0x180039553  jge     short loc_180039582
0x180039555  movsxd  rcx, edx
0x180039558  shl     rcx, 4
0x18003955c  add     rcx, [r8]
0x18003955f  mov     rax, [rcx]
0x180039562  sub     rax, qword ptr [rbp+57h+Buf2]
0x180039566  jnz     short loc_180039570
0x180039568  mov     rax, [rcx+8]
0x18003956c  sub     rax, qword ptr [rbp+57h+Buf2+8]
0x180039570  test    rax, rax
0x180039573  jz      short loc_180039579
0x180039575  add     edx, esi
0x180039577  jmp     short loc_18003954F
0x180039579  cmp     edx, 0FFFFFFFFh
0x18003957c  jnz     loc_18003982D
0x180039582  xor     r9d, r9d
0x180039585  xor     r8d, r8d
0x180039588  lea     rdx, [rbp+57h+var_60]
0x18003958c  mov     rcx, rdi
0x18003958f  call    ?GetDefaultConnectorProcessingModeInternal@EffectPack@@AEAA?AU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4SED_RESOLVEOPT@@@Z; EffectPack::GetDefaultConnectorProcessingModeInternal(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,SED_RESOLVEOPT)
0x180039594  movups  xmm6, xmmword ptr [rax]
0x180039597  mov     qword ptr [r12], 0
0x18003959f  lea     rax, [rbp+57h+pv]
0x1800395a3  mov     [rbp+57h+var_78], rax
0x1800395a7  mov     [rbp+57h+var_70], 0
0x1800395af  mov     [rbp+57h+var_68], sil
0x1800395b3  xorps   xmm0, xmm0
0x1800395b6  xor     eax, eax
0x1800395b8  movups  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x1800395bc  mov     [rbp+57h+var_50], eax
0x1800395bf  movdqa  [rbp+57h+Buf2], xmm6
0x1800395c4  xor     ebx, ebx
0x1800395c6  cmp     ebx, 0Ah
0x1800395c9  jnb     short loc_180039649
0x1800395cb  mov     ecx, ebx
0x1800395cd  shl     rcx, 4
0x1800395d1  lea     rax, unk_1801870E0
0x1800395d8  add     rcx, rax; Buf1
0x1800395db  mov     r8d, 10h; Size
0x1800395e1  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800395e5  call    memcmp_0
0x1800395ea  test    eax, eax
0x1800395ec  jnz     loc_18003981F
0x1800395f2  movups  xmm0, cs:PKEY_AudioEngine_SignalProcessingMode_Specific_ConnectorFormat
0x1800395f9  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x1800395fe  lea     eax, [rbx+2]
0x180039601  mov     [rbp+57h+var_50], eax
0x180039604  xorps   xmm0, xmm0
0x180039607  xor     eax, eax
0x180039609  movups  [rbp+57h+Buf2], xmm0
0x18003960d  mov     [rbp+57h+Src], rax
0x180039611  mov     rax, [rdi+630h]
0x180039618  mov     rcx, [rax+48h]
0x18003961c  mov     rax, [rcx]
0x18003961f  lea     r8, [rbp+57h+Buf2]
0x180039623  lea     rdx, [rbp+57h+var_60]
0x180039627  mov     rax, [rax+28h]
0x18003962b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039630  test    eax, eax
0x180039632  js      short loc_18003963F
0x180039634  cmp     word ptr [rbp+57h+Buf2], 41h ; 'A'
0x180039639  jz      loc_1800398E4
0x18003963f  lea     rcx, [rbp+57h+Buf2]; pvar
0x180039643  call    cs:__imp_PropVariantClear
0x180039649  movdqa  [rbp+57h+Buf2], xmm6
0x18003964e  lea     r9, [rbp+57h+Buf2]; struct _GUID
0x180039652  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180039655  lea     rdx, [rbp+57h+var_60]; retstr
0x180039659  mov     rcx, rdi; this
0x18003965c  call    ?TranslateDeviceConnectorModeToStreamingConnectorMode@EffectPack@@QEAA?AU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U2@@Z; EffectPack::TranslateDeviceConnectorModeToStreamingConnectorMode(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID)
0x180039661  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x180039665  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x18003966a  mov     rdx, [rdi+630h]
0x180039671  lea     rax, [rbp+57h+var_70]
0x180039675  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18003967a  lea     r9, [rbp+57h+var_60]; struct _GUID *
0x18003967e  xor     r8d, r8d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180039681  mov     rdx, [rdx+48h]; struct IPropertyStore *
0x180039685  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; struct IMMDeviceEnumerator *
0x18003968c  call    ?GetProposedConnectorFormatForProcessingMode@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; GetProposedConnectorFormatForProcessingMode(IMMDeviceEnumerator *,IPropertyStore *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x180039691  mov     ebx, eax
0x180039693  test    eax, eax
0x180039695  js      loc_180039941
0x18003969b  cmp     [rbp+57h+var_68], 0
0x18003969f  jz      short loc_1800396BA
0x1800396a1  mov     rdx, [rbp+57h+var_78]
0x1800396a5  mov     rcx, [rdx]; pv
0x1800396a8  mov     rax, [rbp+57h+var_70]
0x1800396ac  mov     [rdx], rax
0x1800396af  test    rcx, rcx
0x1800396b2  jz      short loc_1800396BA
0x1800396b4  call    cs:__imp_CoTaskMemFree
0x1800396ba  test    ebx, ebx
0x1800396bc  js      loc_1800398AD
0x1800396c2  mov     qword ptr [r12], 7530h
0x1800396ca  cmp     qword ptr [rdi+760h], 0
0x1800396d2  jbe     loc_180039975
0x1800396d8  mov     r8, [rdi+768h]
0x1800396df  movdqa  [rbp+57h+Buf2], xmm6
0x1800396e4  xor     ecx, ecx
0x1800396e6  cmp     ecx, [r8+10h]
0x1800396ea  jge     short loc_180039719
0x1800396ec  movsxd  rdx, ecx
0x1800396ef  shl     rdx, 4
0x1800396f3  add     rdx, [r8]
0x1800396f6  mov     rax, [rdx]
0x1800396f9  sub     rax, qword ptr [rbp+57h+Buf2]
0x1800396fd  jnz     short loc_180039707
0x1800396ff  mov     rax, [rdx+8]
0x180039703  sub     rax, qword ptr [rbp+57h+Buf2+8]
0x180039707  test    rax, rax
0x18003970a  jnz     loc_180039826
0x180039710  cmp     ecx, 0FFFFFFFFh
0x180039713  jnz     loc_18003984B
0x180039719  movdqa  xmmword ptr [rbp+57h+var_60.Data1], xmm6
0x18003971e  lea     rcx, [rbp+57h+var_60]
0x180039722  mov     r14, [rbp+57h+pv]
0x180039726  mov     rax, [rdi+630h]
0x18003972d  movups  xmm0, xmmword ptr [rcx]
0x180039730  movdqu  [rbp+57h+Buf2], xmm0
0x180039735  mov     rdi, [rax+110h]
0x18003973c  mov     r15, [rax+118h]
0x180039743  cmp     rdi, r15
0x180039746  jz      loc_1800397D0
0x18003974c  mov     rcx, [rdi]
0x18003974f  mov     rax, [rcx]
0x180039752  sub     rax, qword ptr [rbp+57h+Buf2]
0x180039756  jnz     short loc_180039760
0x180039758  mov     rax, [rcx+8]
0x18003975c  sub     rax, qword ptr [rbp+57h+Buf2+8]
0x180039760  test    rax, rax
0x180039763  jnz     loc_180039816
0x180039769  mov     rbx, [rcx+10h]
0x18003976d  mov     rsi, [rcx+18h]
0x180039771  cmp     rbx, rsi
0x180039774  jz      loc_180039816
0x18003977a  mov     rdx, [rbx]
0x18003977d  mov     rdx, [rdx]; struct tWAVEFORMATEX *
0x180039780  mov     rcx, r14; struct tWAVEFORMATEX *
0x180039783  call    ?CompareWaveFormat@@YAHPEBUtWAVEFORMATEX@@0@Z; CompareWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX const *)
0x180039788  test    eax, eax
0x18003978a  jz      loc_180039842
0x180039790  mov     rax, [rbx]
0x180039793  mov     ecx, [rax+10h]
0x180039796  xorps   xmm1, xmm1
0x180039799  cvtsi2sd xmm1, rcx
0x18003979e  mulsd   xmm1, cs:__real@416312d000000000
0x1800397a6  mov     eax, [r14+4]
0x1800397aa  xorps   xmm0, xmm0
0x1800397ad  cvtsi2sd xmm0, rax
0x1800397b2  divsd   xmm1, xmm0
0x1800397b6  addsd   xmm1, cs:__real@3fe0000000000000
0x1800397be  cvttsd2si rax, xmm1
0x1800397c3  cmp     rax, [r12]
0x1800397c7  cmovge  rax, [r12]
0x1800397cc  mov     [r12], rax
0x1800397d0  mov     rcx, [rbp+57h+pv]; pv
0x1800397d4  mov     [rbp+57h+pv], 0
0x1800397dc  test    rcx, rcx
0x1800397df  jz      short loc_1800397E7
0x1800397e1  call    cs:__imp_CoTaskMemFree
0x1800397e7  xor     eax, eax
0x1800397e9  mov     rcx, [rbp+57h+var_40]
0x1800397ed  xor     rcx, rsp; StackCookie
0x1800397f0  call    __security_check_cookie
0x1800397f5  lea     r11, [rsp+0D0h+var_20]
0x1800397fd  mov     rbx, [r11+38h]
0x180039801  mov     rsi, [r11+48h]
0x180039805  movaps  xmm6, xmmword ptr [r11-10h]
0x18003980a  mov     rsp, r11
0x18003980d  pop     r15
0x18003980f  pop     r14
0x180039811  pop     r12
0x180039813  pop     rdi
0x180039814  pop     rbp
0x180039815  retn
0x180039816  add     rdi, 8
0x18003981a  jmp     loc_180039743
0x18003981f  add     ebx, esi
0x180039821  jmp     loc_1800395C6
0x180039826  add     ecx, esi
0x180039828  jmp     loc_1800396E6
0x18003982d  movaps  xmm0, xmmword ptr cs:_GUID_9e90ea20_b493_4fd1_a1a8_7e1361a956cf.Data1
0x180039834  movdqu  [rbp+57h+Buf2], xmm0
0x180039839  lea     rax, [rbp+57h+Buf2]
0x18003983d  jmp     loc_180039594
0x180039842  add     rbx, 8
0x180039846  jmp     loc_180039771
0x18003984b  movdqa  [rbp+57h+Buf2], xmm6
0x180039850  xor     eax, eax
0x180039852  cmp     eax, [r8+10h]
0x180039856  jge     short loc_1800398A4
0x180039858  movsxd  rdx, eax
0x18003985b  shl     rdx, 4
0x18003985f  add     rdx, [r8]
0x180039862  mov     rcx, [rdx]
0x180039865  sub     rcx, qword ptr [rbp+57h+Buf2]
0x180039869  jnz     short loc_180039873
0x18003986b  mov     rcx, [rdx+8]
0x18003986f  sub     rcx, qword ptr [rbp+57h+Buf2+8]
0x180039873  test    rcx, rcx
0x180039876  jnz     short loc_1800398A0
0x180039878  cmp     eax, 0FFFFFFFFh
0x18003987b  jz      short loc_1800398A4
0x18003987d  test    eax, eax
0x18003987f  js      loc_180039961
0x180039885  cdqe
0x180039887  shl     rax, 4
0x18003988b  add     rax, [r8+8]
0x18003988f  movups  xmm0, xmmword ptr [rax]
0x180039892  movdqu  [rbp+57h+Buf2], xmm0
0x180039897  lea     rcx, [rbp+57h+Buf2]
0x18003989b  jmp     loc_180039722
0x1800398a0  add     eax, esi
0x1800398a2  jmp     short loc_180039852
0x1800398a4  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800398ab  jmp     short loc_180039892
0x1800398ad  mov     rcx, [rbp+5Fh]; this
0x1800398b1  mov     r9d, ebx; char *
0x1800398b4  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1800398bb  mov     edx, 2154h; void *
0x1800398c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800398c5  nop
0x1800398c6  mov     rcx, [rbp+57h+pv]; pv
0x1800398ca  mov     [rbp+57h+pv], 0
0x1800398d2  test    rcx, rcx
0x1800398d5  jz      short loc_1800398DD
0x1800398d7  call    cs:__imp_CoTaskMemFree
0x1800398dd  mov     eax, ebx
0x1800398df  jmp     loc_1800397E9
0x1800398e4  lea     rcx, [rbp+57h+Buf2]; struct tagPROPVARIANT *
0x1800398e8  call    ?IsValidWfxBlob@@YAHPEAUtagPROPVARIANT@@@Z; IsValidWfxBlob(tagPROPVARIANT *)
0x1800398ed  test    eax, eax
0x1800398ef  jz      loc_18003963F
0x1800398f5  lea     rdx, [rbp+57h+var_70]; struct tWAVEFORMATEX **
0x1800398f9  mov     rcx, [rbp+57h+Src]; Src
0x1800398fd  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180039902  mov     ebx, eax
0x180039904  test    eax, eax
0x180039906  jns     short loc_180039930
0x180039908  mov     rcx, [rbp+5Fh]; this
0x18003990c  mov     r9d, eax; char *
0x18003990f  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180039916  mov     edx, 1A14h; void *
0x18003991b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039920  nop
0x180039921  lea     rcx, [rbp+57h+Buf2]; pvar
0x180039925  call    cs:__imp_PropVariantClear
0x18003992b  jmp     loc_18003969B
0x180039930  lea     rcx, [rbp+57h+Buf2]; pvar
0x180039934  call    cs:__imp_PropVariantClear
0x18003993a  xor     ebx, ebx
0x18003993c  jmp     loc_18003969B
0x180039941  lea     rax, [rbp+57h+var_70]
0x180039945  mov     qword ptr [rsp+0D0h+var_B0], rax; struct tWAVEFORMATEX **
0x18003994a  xor     r9d, r9d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003994d  xor     r8d, r8d; bool
0x180039950  xor     edx, edx; bool
0x180039952  mov     rcx, rdi; this
0x180039955  call    ?GetDeviceFormat@EffectPack@@QEAAJ_N0W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAPEAUtWAVEFORMATEX@@@Z; EffectPack::GetDeviceFormat(bool,bool,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX * *)
0x18003995a  mov     ebx, eax
0x18003995c  jmp     loc_18003969B
0x180039961  xor     r9d, r9d; lpArguments
0x180039964  xor     r8d, r8d; nNumberOfArguments
0x180039967  mov     edx, esi; dwExceptionFlags
0x180039969  mov     ecx, 0C000008Ch; dwExceptionCode
0x18003996e  call    cs:__imp_RaiseException
0x180039974  int     3; Trap to Debugger
0x180039975  call    cs:__imp__o_terminate
```
