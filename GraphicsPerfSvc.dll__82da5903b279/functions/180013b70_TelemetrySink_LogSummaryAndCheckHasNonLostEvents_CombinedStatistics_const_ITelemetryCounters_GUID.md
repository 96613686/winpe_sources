# TelemetrySink::LogSummaryAndCheckHasNonLostEvents(CombinedStatistics const &,ITelemetryCounters *,_GUID)

- ea: `0x180013b70`
- end: `0x180014129`
- name: `?LogSummaryAndCheckHasNonLostEvents@TelemetrySink@@UEAA_NAEBUCombinedStatistics@@PEAUITelemetryCounters@@U_GUID@@@Z`
- size: `1465`
- prototype: `bool(TelemetrySink *__hidden this, const struct CombinedStatistics *, struct ITelemetryCounters *, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800018ac`
- `0x1800028d8`
- `0x18000cd2c`
- `0x18000fbbc`
- `0x18000fc54`
- `0x180011274`
- `0x180013b70`
- `0x180014130`
- `0x180031010`

## pseudocode

```c
char __fastcall TelemetrySink::LogSummaryAndCheckHasNonLostEvents(
        TelemetrySink *this,
        const struct CombinedStatistics *a2,
        struct ITelemetryCounters *a3,
        struct _GUID *a4)
{
  const struct CombinedStatistics *v4; // r15
  __int64 v5; // rdx
  const struct _GUID *v6; // r12
  struct ITelemetryCounters *v7; // rsi
  unsigned int v8; // r14d
  __int64 *v9; // rbx
  char v10; // di
  __int64 *v11; // r13
  unsigned int v12; // r8d
  unsigned int v13; // r12d
  unsigned int v14; // edx
  unsigned int v15; // ecx
  unsigned int v16; // eax
  const struct _tlgProvider_t *v17; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v24; // [rsp+1A0h] [rbp-80h] BYREF
  int v25; // [rsp+1A4h] [rbp-7Ch] BYREF
  int v26; // [rsp+1A8h] [rbp-78h] BYREF
  int v27; // [rsp+1ACh] [rbp-74h] BYREF
  int v28; // [rsp+1B0h] [rbp-70h] BYREF
  int v29; // [rsp+1B4h] [rbp-6Ch] BYREF
  int v30; // [rsp+1B8h] [rbp-68h] BYREF
  int v31; // [rsp+1BCh] [rbp-64h] BYREF
  int v32; // [rsp+1C0h] [rbp-60h] BYREF
  int v33; // [rsp+1C4h] [rbp-5Ch] BYREF
  int v34; // [rsp+1C8h] [rbp-58h] BYREF
  int v35; // [rsp+1CCh] [rbp-54h] BYREF
  int v36; // [rsp+1D0h] [rbp-50h] BYREF
  int v37; // [rsp+1D4h] [rbp-4Ch] BYREF
  int v38; // [rsp+1D8h] [rbp-48h] BYREF
  unsigned int v39; // [rsp+1DCh] [rbp-44h] BYREF
  int v40; // [rsp+1E0h] [rbp-40h] BYREF
  int v41; // [rsp+1E4h] [rbp-3Ch] BYREF
  int v42; // [rsp+1E8h] [rbp-38h] BYREF
  int v43; // [rsp+1ECh] [rbp-34h] BYREF
  int v44; // [rsp+1F0h] [rbp-30h] BYREF
  int v45; // [rsp+1F4h] [rbp-2Ch] BYREF
  int v46; // [rsp+1F8h] [rbp-28h] BYREF
  int v47; // [rsp+1FCh] [rbp-24h] BYREF
  int v48; // [rsp+200h] [rbp-20h] BYREF
  int v49; // [rsp+204h] [rbp-1Ch] BYREF
  int v50; // [rsp+208h] [rbp-18h] BYREF
  int v51; // [rsp+20Ch] [rbp-14h] BYREF
  int v52; // [rsp+210h] [rbp-10h] BYREF
  struct _GUID *v53; // [rsp+218h] [rbp-8h]
  __int64 v54; // [rsp+220h] [rbp+0h] BYREF
  __int64 v55; // [rsp+228h] [rbp+8h] BYREF
  __int64 v56; // [rsp+230h] [rbp+10h] BYREF
  __int64 v57; // [rsp+238h] [rbp+18h] BYREF
  __int64 v58; // [rsp+240h] [rbp+20h] BYREF
  __int64 v59; // [rsp+248h] [rbp+28h] BYREF
  __int64 v60; // [rsp+250h] [rbp+30h] BYREF
  __int64 v61; // [rsp+258h] [rbp+38h] BYREF
  __int64 v62; // [rsp+260h] [rbp+40h] BYREF
  __int64 v63; // [rsp+268h] [rbp+48h] BYREF
  __int64 v64; // [rsp+270h] [rbp+50h] BYREF
  __int64 v65; // [rsp+278h] [rbp+58h] BYREF
  struct _GUID *v66; // [rsp+280h] [rbp+60h] BYREF
  __int64 v67; // [rsp+288h] [rbp+68h] BYREF
  const struct CombinedStatistics *v68; // [rsp+290h] [rbp+70h]
  __int64 *v69; // [rsp+298h] [rbp+78h] BYREF
  int v70; // [rsp+2A0h] [rbp+80h]
  __int64 *v71; // [rsp+2A8h] [rbp+88h] BYREF
  int v72; // [rsp+2B0h] [rbp+90h]
  __int64 *v73; // [rsp+2B8h] [rbp+98h] BYREF
  int v74; // [rsp+2C0h] [rbp+A0h]
  __int64 *v75; // [rsp+2C8h] [rbp+A8h] BYREF
  int v76; // [rsp+2D0h] [rbp+B0h]
  __int64 *v77; // [rsp+2D8h] [rbp+B8h] BYREF
  int v78; // [rsp+2E0h] [rbp+C0h]

  v4 = a2;
  v68 = a2;
  v5 = 1;
  v53 = a4;
  v6 = a4;
  v7 = a3;
  v8 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 2, 1u);
  v9 = *(__int64 **)v4;
  v10 = 0;
  v11 = (__int64 *)*((_QWORD *)v4 + 1);
  if ( *(__int64 **)v4 != v11 )
  {
    do
    {
      if ( *((_DWORD *)v9 + 195) || *((_DWORD *)v9 + 196) )
      {
        LOBYTE(a3) = 3;
        LOBYTE(v5) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl'::`2'::impl,
          v5,
          a3);
        v12 = 0;
        v13 = 0;
        v14 = 0;
        do
        {
          v15 = *((_DWORD *)v9 + (int)v14 + 180);
          v16 = v14;
          if ( v15 <= v12 )
            v16 = v13;
          ++v14;
          v13 = v16;
          if ( v15 <= v12 )
            v15 = v12;
          v12 = v15;
        }
        while ( v14 < 0xD );
        v17 = gpm::TraceProvider::Provider();
        if ( *(_DWORD *)v17 > 5u && (unsigned __int8)tlgKeywordOn(v17, 0x400000000000LL) )
        {
          v54 = v9[104];
          v55 = v9[103];
          v26 = *((_DWORD *)v9 + 204);
          v27 = *((_DWORD *)v9 + 203);
          v20 = *((_DWORD *)v9 + 213);
          v28 = *((_DWORD *)v9 + 202);
          v29 = *((_DWORD *)v9 + 201);
          v30 = *((_DWORD *)v9 + 200);
          v31 = *((_DWORD *)v9 + 214);
          v32 = *((_DWORD *)v9 + 221);
          v33 = *((_DWORD *)v9 + 222);
          v34 = *((_DWORD *)v9 + 224);
          v35 = *((_DWORD *)v9 + 223);
          v36 = *((_DWORD *)v9 + 220);
          v37 = *((_DWORD *)v9 + 226);
          v38 = *((_DWORD *)v9 + 225);
          v69 = v9 + 90;
          v40 = *((_DWORD *)v9 + 212);
          v41 = *((_DWORD *)v9 + 211);
          v42 = *((_DWORD *)v9 + 210);
          v43 = *((_DWORD *)v9 + 199);
          v44 = *((_DWORD *)v9 + 198);
          v45 = *((_DWORD *)v9 + 197);
          v46 = *((_DWORD *)v9 + 196);
          v47 = *((_DWORD *)v9 + 195);
          v48 = *((_DWORD *)v9 + 194);
          v71 = v9 + 69;
          v56 = v9[68];
          v57 = v9[67];
          v73 = v9 + 46;
          v58 = v9[45];
          v59 = v9[44];
          v75 = v9 + 24;
          v60 = v9[109];
          v21 = v9[23];
          v25 = v20;
          v61 = v21;
          v22 = v9[22];
          v72 = 168;
          v74 = 168;
          v62 = v22;
          v24 = v8;
          v70 = 52;
          v39 = v13;
          v76 = 160;
          v77 = v9 + 2;
          v63 = v9[108];
          v64 = v9[1];
          v65 = *v9;
          v6 = v53;
          v78 = 160;
          v49 = 1;
          v50 = 1;
          v51 = 22;
          v66 = v53;
          v52 = 1;
          v67 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v18,
            (__int64)byte_18003AB61,
            v18,
            v19,
            (__int64)&v67,
            (__int64)&v52,
            (__int64 *)&v66,
            (__int64)&v51,
            (__int64)&v50,
            (__int64)&v49,
            (__int64)&v65,
            (__int64)&v64,
            (__int64)&v63,
            (__int64 *)&v77,
            (__int64)&v62,
            (__int64)&v61,
            (__int64)&v60,
            (__int64 *)&v75,
            (__int64)&v59,
            (__int64)&v58,
            (__int64 *)&v73,
            (__int64)&v57,
            (__int64)&v56,
            (__int64 *)&v71,
            (__int64)&v48,
            (__int64)&v47,
            (__int64)&v46,
            (__int64)&v45,
            (__int64)&v44,
            (__int64)&v43,
            (__int64)&v42,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)&v39,
            (__int64 *)&v69,
            (__int64)&v38,
            (__int64)&v37,
            (__int64)&v36,
            (__int64)&v35,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v32,
            (__int64)&v31,
            (__int64)&v30,
            (__int64)&v29,
            (__int64)&v28,
            (__int64)&v27,
            (__int64)&v26,
            (__int64)&v55,
            (__int64)&v54,
            (__int64)&v25,
            (__int64)&v24);
        }
        else
        {
          v6 = v53;
        }
        (**(void (__fastcall ***)(struct ITelemetryCounters *))v7)(v7);
        (*(void (__fastcall **)(struct ITelemetryCounters *, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v7 + 8LL))(
          v7,
          *((unsigned int *)v9 + 224),
          *((unsigned int *)v9 + 221),
          *((unsigned int *)v9 + 222),
          *((_DWORD *)v9 + 223),
          *((_DWORD *)v9 + 220));
        if ( *((_DWORD *)v9 + 195) )
          v10 = 1;
      }
      v9 += 114;
    }
    while ( v9 != v11 );
    v4 = v68;
  }
  LOBYTE(a3) = 3;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl'::`2'::impl,
    1,
    a3);
  if ( *((_QWORD *)v4 + 5)
    || wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetImpl'::`2'::impl)
    && *((_QWORD *)v4 + 30) )
  {
    TelemetrySink::LogTrackedProcessStatisticsSummary((const struct CombinedStatistics *)((char *)v4 + 40), v6, v8);
  }
  return v10;
}

```

## disassembly

```asm
0x180013b70  push    rbp
0x180013b72  push    rbx
0x180013b73  push    rsi
0x180013b74  push    rdi
0x180013b75  push    r12
0x180013b77  push    r13
0x180013b79  push    r14
0x180013b7b  push    r15
0x180013b7d  lea     rbp, [rsp-0D8h]
0x180013b85  sub     rsp, 2F8h
0x180013b8c  mov     r15, rdx
0x180013b8f  mov     [rbp+110h+var_A0], rdx
0x180013b93  mov     edx, 1
0x180013b98  mov     [rbp+110h+var_118], r9
0x180013b9c  mov     r14d, edx
0x180013b9f  mov     r12, r9
0x180013ba2  mov     rsi, r8
0x180013ba5  lock xadd [rcx+8], r14d
0x180013bab  mov     rbx, [r15]
0x180013bae  xor     dil, dil
0x180013bb1  mov     r13, [r15+8]
0x180013bb5  cmp     rbx, r13
0x180013bb8  jz      loc_1800140D3
0x180013bbe  mov     r15d, edx
0x180013bc1  cmp     dword ptr [rbx+30Ch], 0
0x180013bc8  jnz     short loc_180013BD7
0x180013bca  cmp     dword ptr [rbx+310h], 0
0x180013bd1  jz      loc_1800140BA
0x180013bd7  mov     r8b, 3
0x180013bda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl(void)'::`2'::impl
0x180013be1  mov     dl, r15b
0x180013be4  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180013be9  xor     r8d, r8d
0x180013bec  xor     r12d, r12d
0x180013bef  xor     edx, edx
0x180013bf1  movsxd  rax, edx
0x180013bf4  mov     ecx, [rbx+rax*4+2D0h]
0x180013bfb  cmp     ecx, r8d
0x180013bfe  mov     eax, edx
0x180013c00  cmovbe  eax, r12d
0x180013c04  add     edx, r15d
0x180013c07  cmp     ecx, r8d
0x180013c0a  mov     r12d, eax
0x180013c0d  cmovbe  ecx, r8d
0x180013c11  mov     r8d, ecx
0x180013c14  cmp     edx, 0Dh
0x180013c17  jb      short loc_180013BF1
0x180013c19  call    ?Provider@TraceProvider@gpm@@SAPEBU_tlgProvider_t@@XZ; gpm::TraceProvider::Provider(void)
0x180013c1e  mov     r8, rax
0x180013c21  mov     ecx, [rax]
0x180013c23  cmp     ecx, 5
0x180013c26  jbe     loc_180014062
0x180013c2c  mov     rdx, 400000000000h
0x180013c36  mov     rcx, rax
0x180013c39  call    _tlgKeywordOn
0x180013c3e  test    al, al
0x180013c40  jz      loc_180014062
0x180013c46  mov     rax, [rbx+340h]
0x180013c4d  mov     [rbp+110h+var_110], rax
0x180013c51  mov     rax, [rbx+338h]
0x180013c58  mov     [rbp+110h+var_108], rax
0x180013c5c  mov     eax, [rbx+330h]
0x180013c62  mov     [rbp+110h+var_188], eax
0x180013c65  mov     eax, [rbx+32Ch]
0x180013c6b  mov     [rbp+110h+var_184], eax
0x180013c6e  mov     eax, [rbx+328h]
0x180013c74  mov     ecx, [rbx+354h]
0x180013c7a  mov     [rbp+110h+var_180], eax
0x180013c7d  mov     eax, [rbx+324h]
0x180013c83  mov     [rbp+110h+var_17C], eax
0x180013c86  mov     eax, [rbx+320h]
0x180013c8c  mov     [rbp+110h+var_178], eax
0x180013c8f  mov     eax, [rbx+358h]
0x180013c95  mov     [rbp+110h+var_174], eax
0x180013c98  mov     eax, [rbx+374h]
0x180013c9e  mov     [rbp+110h+var_170], eax
0x180013ca1  mov     eax, [rbx+378h]
0x180013ca7  mov     [rbp+110h+var_16C], eax
0x180013caa  mov     eax, [rbx+380h]
0x180013cb0  mov     [rbp+110h+var_168], eax
0x180013cb3  mov     eax, [rbx+37Ch]
0x180013cb9  mov     [rbp+110h+var_164], eax
0x180013cbc  mov     eax, [rbx+370h]
0x180013cc2  mov     [rbp+110h+var_160], eax
0x180013cc5  mov     eax, [rbx+388h]
0x180013ccb  mov     [rbp+110h+var_15C], eax
0x180013cce  mov     eax, [rbx+384h]
0x180013cd4  mov     [rbp+110h+var_158], eax
0x180013cd7  lea     rax, [rbx+2D0h]
0x180013cde  mov     [rbp+110h+var_98], rax
0x180013ce2  mov     eax, [rbx+350h]
0x180013ce8  mov     [rbp+110h+var_150], eax
0x180013ceb  mov     eax, [rbx+34Ch]
0x180013cf1  mov     [rbp+110h+var_14C], eax
0x180013cf4  mov     eax, [rbx+348h]
0x180013cfa  mov     [rbp+110h+var_148], eax
0x180013cfd  mov     eax, [rbx+31Ch]
0x180013d03  mov     [rbp+110h+var_144], eax
0x180013d06  mov     eax, [rbx+318h]
0x180013d0c  mov     [rbp+110h+var_140], eax
0x180013d0f  mov     eax, [rbx+314h]
0x180013d15  mov     [rbp+110h+var_13C], eax
0x180013d18  mov     eax, [rbx+310h]
0x180013d1e  mov     [rbp+110h+var_138], eax
0x180013d21  mov     eax, [rbx+30Ch]
0x180013d27  mov     [rbp+110h+var_134], eax
0x180013d2a  mov     eax, [rbx+308h]
0x180013d30  mov     [rbp+110h+var_130], eax
0x180013d33  lea     rax, [rbx+228h]
0x180013d3a  mov     [rbp+110h+var_88], rax
0x180013d41  mov     rax, [rbx+220h]
0x180013d48  mov     [rbp+110h+var_100], rax
0x180013d4c  mov     rax, [rbx+218h]
0x180013d53  mov     [rbp+110h+var_F8], rax
0x180013d57  lea     rax, [rbx+170h]
0x180013d5e  mov     [rbp+110h+var_78], rax
0x180013d65  mov     rax, [rbx+168h]
0x180013d6c  mov     [rbp+110h+var_F0], rax
0x180013d70  mov     rax, [rbx+160h]
0x180013d77  mov     [rbp+110h+var_E8], rax
0x180013d7b  lea     rax, [rbx+0C0h]
0x180013d82  mov     [rbp+110h+var_68], rax
0x180013d89  mov     rax, [rbx+368h]
0x180013d90  mov     [rbp+110h+var_E0], rax
0x180013d94  mov     rax, [rbx+0B8h]
0x180013d9b  mov     [rbp+110h+var_18C], ecx
0x180013d9e  mov     ecx, 0A8h
0x180013da3  mov     [rbp+110h+var_D8], rax
0x180013da7  mov     rax, [rbx+0B0h]
0x180013dae  mov     [rbp+110h+var_80], ecx
0x180013db4  mov     [rbp+110h+var_70], ecx
0x180013dba  mov     ecx, 0A0h
0x180013dbf  mov     [rbp+110h+var_D0], rax
0x180013dc3  lea     rax, [rbx+10h]
0x180013dc7  mov     [rbp+110h+var_190], r14d
0x180013dcb  mov     [rbp+110h+var_90], 34h ; '4'
0x180013dd5  mov     [rbp+110h+var_154], r12d
0x180013dd9  mov     [rbp+110h+var_60], ecx
0x180013ddf  mov     [rbp+110h+var_58], rax
0x180013de6  mov     rax, [rbx+360h]
0x180013ded  mov     [rbp+110h+var_C8], rax
0x180013df1  mov     rax, [rbx+8]
0x180013df5  mov     [rbp+110h+var_C0], rax
0x180013df9  mov     rax, [rbx]
0x180013dfc  mov     [rbp+110h+var_B8], rax
0x180013e00  lea     rax, [rbp+110h+var_190]
0x180013e04  mov     [rsp+330h+var_198], rax
0x180013e0c  lea     rax, [rbp+110h+var_18C]
0x180013e10  mov     [rsp+330h+var_1A0], rax
0x180013e18  lea     rax, [rbp+110h+var_110]
0x180013e1c  mov     [rsp+330h+var_1A8], rax
0x180013e24  lea     rax, [rbp+110h+var_108]
0x180013e28  mov     [rsp+330h+var_1B0], rax
0x180013e30  lea     rax, [rbp+110h+var_188]
0x180013e34  mov     [rsp+330h+var_1B8], rax
0x180013e3c  lea     rax, [rbp+110h+var_184]
0x180013e40  mov     [rsp+330h+var_1C0], rax
0x180013e48  lea     rax, [rbp+110h+var_180]
0x180013e4c  mov     [rsp+330h+var_1C8], rax
0x180013e54  lea     rax, [rbp+110h+var_17C]
0x180013e58  mov     [rsp+330h+var_1D0], rax
0x180013e60  lea     rax, [rbp+110h+var_178]
0x180013e64  mov     [rsp+330h+var_1D8], rax
0x180013e6c  lea     rax, [rbp+110h+var_174]
0x180013e70  mov     [rsp+330h+var_1E0], rax
0x180013e78  lea     rax, [rbp+110h+var_170]
0x180013e7c  mov     [rsp+330h+var_1E8], rax
0x180013e84  lea     rax, [rbp+110h+var_16C]
0x180013e88  mov     [rsp+330h+var_1F0], rax
0x180013e90  lea     rax, [rbp+110h+var_168]
0x180013e94  mov     [rsp+330h+var_1F8], rax
0x180013e9c  lea     rax, [rbp+110h+var_164]
0x180013ea0  mov     [rsp+330h+var_200], rax
0x180013ea8  lea     rax, [rbp+110h+var_160]
0x180013eac  mov     [rsp+330h+var_208], rax
0x180013eb4  lea     rax, [rbp+110h+var_15C]
0x180013eb8  mov     [rsp+330h+var_210], rax
0x180013ec0  lea     rax, [rbp+110h+var_158]
0x180013ec4  mov     [rsp+330h+var_218], rax
0x180013ecc  lea     rax, [rbp+110h+var_98]
0x180013ed0  mov     r12, [rbp+110h+var_118]
0x180013ed4  mov     [rsp+330h+var_220], rax
0x180013edc  lea     rax, [rbp+110h+var_154]
0x180013ee0  mov     [rsp+330h+var_228], rax
0x180013ee8  lea     rax, [rbp+110h+var_150]
0x180013eec  mov     [rsp+330h+var_230], rax
0x180013ef4  lea     rax, [rbp+110h+var_14C]
0x180013ef8  mov     [rsp+330h+var_238], rax
0x180013f00  lea     rax, [rbp+110h+var_148]
0x180013f04  mov     [rsp+330h+var_240], rax
0x180013f0c  lea     rax, [rbp+110h+var_144]
0x180013f10  mov     [rsp+330h+var_248], rax
0x180013f18  lea     rax, [rbp+110h+var_140]
0x180013f1c  mov     [rsp+330h+var_250], rax
0x180013f24  lea     rax, [rbp+110h+var_13C]
0x180013f28  mov     [rsp+330h+var_258], rax
0x180013f30  lea     rax, [rbp+110h+var_138]
0x180013f34  mov     [rsp+330h+var_260], rax
0x180013f3c  lea     rax, [rbp+110h+var_134]
0x180013f40  mov     [rsp+330h+var_268], rax
0x180013f48  lea     rax, [rbp+110h+var_130]
0x180013f4c  mov     [rsp+330h+var_270], rax
0x180013f54  lea     rax, [rbp+110h+var_88]
0x180013f5b  mov     [rsp+330h+var_278], rax
0x180013f63  lea     rax, [rbp+110h+var_100]
0x180013f67  mov     [rsp+330h+var_280], rax
0x180013f6f  lea     rax, [rbp+110h+var_F8]
0x180013f73  mov     [rsp+330h+var_288], rax
0x180013f7b  lea     rax, [rbp+110h+var_78]
0x180013f82  mov     [rsp+330h+var_290], rax
0x180013f8a  lea     rax, [rbp+110h+var_F0]
0x180013f8e  mov     [rsp+330h+var_298], rax
0x180013f96  mov     [rbp+110h+var_50], ecx
0x180013f9c  mov     [rbp+110h+var_12C], r15d
0x180013fa0  mov     [rbp+110h+var_128], r15d
0x180013fa4  mov     [rbp+110h+var_124], 16h
0x180013fab  mov     [rbp+110h+var_B0], r12
0x180013faf  mov     [rbp+110h+var_120], r15d
0x180013fb3  mov     [rbp+110h+var_A8], 1000000h
0x180013fbb  lea     rax, [rbp+110h+var_E8]
0x180013fbf  mov     rcx, r8
0x180013fc2  mov     [rsp+330h+var_2A0], rax
0x180013fca  lea     rdx, byte_18003AB61
0x180013fd1  lea     rax, [rbp+110h+var_68]
0x180013fd8  mov     [rsp+330h+var_2A8], rax
0x180013fe0  lea     rax, [rbp+110h+var_E0]
0x180013fe4  mov     [rsp+330h+var_2B0], rax
0x180013fec  lea     rax, [rbp+110h+var_D8]
0x180013ff0  mov     [rsp+330h+var_2B8], rax
0x180013ff5  lea     rax, [rbp+110h+var_D0]
0x180013ff9  mov     [rsp+330h+var_2C0], rax
0x180013ffe  lea     rax, [rbp+110h+var_58]
0x180014005  mov     [rsp+330h+var_2C8], rax
0x18001400a  lea     rax, [rbp+110h+var_C8]
0x18001400e  mov     [rsp+330h+var_2D0], rax
0x180014013  lea     rax, [rbp+110h+var_C0]
0x180014017  mov     [rsp+330h+var_2D8], rax
0x18001401c  lea     rax, [rbp+110h+var_B8]
0x180014020  mov     [rsp+330h+var_2E0], rax
0x180014025  lea     rax, [rbp+110h+var_12C]
0x180014029  mov     [rsp+330h+var_2E8], rax
0x18001402e  lea     rax, [rbp+110h+var_128]
0x180014032  mov     [rsp+330h+var_2F0], rax
0x180014037  lea     rax, [rbp+110h+var_124]
0x18001403b  mov     [rsp+330h+var_2F8], rax
0x180014040  lea     rax, [rbp+110h+var_B0]
0x180014044  mov     [rsp+330h+var_300], rax
0x180014049  lea     rax, [rbp+110h+var_120]
0x18001404d  mov     [rsp+330h+var_308], rax
0x180014052  lea     rax, [rbp+110h+var_A8]
0x180014056  mov     [rsp+330h+var_310], rax
0x18001405b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U2@U2@U2@U1@U1@U1@U_tlgWrapperPtrSize@@U1@U1@U1@U4@U1@U1@U4@U1@U1@U4@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U4@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U2@U1@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@444333AEBU_tlgWrapperPtrSize@@33363363364444444444644444444444443344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperPtrSize,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperPtrSize const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180014060  jmp     short loc_180014066
0x180014062  mov     r12, [rbp+110h+var_118]
0x180014066  mov     rax, [rsi]
0x180014069  mov     rcx, rsi
0x18001406c  mov     rax, [rax]
0x18001406f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014074  mov     ecx, [rbx+370h]
0x18001407a  mov     rax, [rsi]
0x18001407d  mov     r9d, [rbx+378h]
0x180014084  mov     r8d, [rbx+374h]
0x18001408b  mov     edx, [rbx+380h]
0x180014091  mov     rax, [rax+8]
0x180014095  mov     dword ptr [rsp+330h+var_308], ecx
0x180014099  mov     ecx, [rbx+37Ch]
0x18001409f  mov     dword ptr [rsp+330h+var_310], ecx
0x1800140a3  mov     rcx, rsi
0x1800140a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140ab  cmp     dword ptr [rbx+30Ch], 0
0x1800140b2  movzx   edi, dil
0x1800140b6  cmovnz  edi, r15d
0x1800140ba  add     rbx, 390h
0x1800140c1  cmp     rbx, r13
0x1800140c4  jnz     loc_180013BC1
0x1800140ca  mov     r15, [rbp+110h+var_A0]
0x1800140ce  mov     edx, 1
0x1800140d3  mov     r8b, 3
0x1800140d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetImpl(void)'::`2'::impl
0x1800140dd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800140e2  cmp     qword ptr [r15+28h], 0
0x1800140e7  jnz     short loc_180014103
0x1800140e9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetImpl(void)'::`2'::impl
0x1800140f0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::__private_IsEnabled(void)
0x1800140f5  test    al, al
0x1800140f7  jz      short loc_180014112
0x1800140f9  cmp     qword ptr [r15+0F0h], 0
0x180014101  jz      short loc_180014112
0x180014103  mov     r8d, r14d; unsigned int
0x180014106  lea     rcx, [r15+28h]; struct TrackedProcessStatistics *
0x18001410a  mov     rdx, r12; struct _GUID *
0x18001410d  call    ?LogTrackedProcessStatisticsSummary@TelemetrySink@@CAXAEBUTrackedProcessStatistics@@AEBU_GUID@@I@Z; TelemetrySink::LogTrackedProcessStatisticsSummary(TrackedProcessStatistics const &,_GUID const &,uint)
0x180014112  mov     al, dil
0x180014115  add     rsp, 2F8h
0x18001411c  pop     r15
0x18001411e  pop     r14
0x180014120  pop     r13
0x180014122  pop     r12
0x180014124  pop     rdi
0x180014125  pop     rsi
  ... truncated ...
```
