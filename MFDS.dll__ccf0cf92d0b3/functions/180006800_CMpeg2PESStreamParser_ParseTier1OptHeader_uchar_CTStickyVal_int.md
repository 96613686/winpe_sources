# CMpeg2PESStreamParser::ParseTier1OptHeader_(uchar *,CTStickyVal<int> *)

- ea: `0x180006800`
- end: `0x180007226`
- name: `?ParseTier1OptHeader_@CMpeg2PESStreamParser@@IEAAHPEAEPEAV?$CTStickyVal@H@@@Z`
- size: `2598`
- prototype: `__int64 __fastcall(CMpeg2PESStreamParser *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005a20`

## callees

- `0x180002820`
- `0x180004fd8`
- `0x180005578`
- `0x1800056a4`
- `0x180006800`
- `0x180007f20`
- `0x1800098e0`
- `0x18000b8c0`
- `0x1800140b0`
- `0x18002d514`
- `0x18003a0ec`
- `0x180051ce4`
- `0x1800527ac`
- `0x18007c8e8`
- `0x1800a3738`
- `0x1800a7c3c`
- `0x1800a9100`
- `0x1800a941c`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000689e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069ee`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000689e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800069ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006db5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006db5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a3d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006883`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800069d4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006883`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800069d4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006dfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800071d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180006dfa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800071d7`

## string_xrefs

- `0x180006e86`: `CMpeg2PESStreamParser::CompletePESCollection_`

## pseudocode

```c
__int64 __fastcall CMpeg2PESStreamParser::ParseTier1OptHeader_(CMpeg2PESStreamParser *this, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  bool v4; // zf
  int v5; // r14d
  __int64 v6; // r15
  BOOL v7; // r12d
  CallStackTracing *v9; // rbx
  char *v10; // rsi
  DWORD LastError; // r15d
  char *Value; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  _BYTE *v15; // rsi
  _DWORD *v16; // rbx
  int v17; // r12d
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  int v21; // r8d
  CallStackTracing *v22; // rbx
  GUID *v23; // rdi
  DWORD v24; // esi
  GUID *v25; // rax
  int v26; // eax
  int v27; // eax
  unsigned __int64 v29; // rcx
  unsigned int v30; // r14d
  __int64 v31; // rsi
  __int64 v32; // rbx
  _QWORD *v33; // rax
  _DWORD *v34; // rcx
  CallStackTracing *v35; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rax
  CallStackTracing *v40; // rcx
  __int64 v41; // rax
  CallStackTracing *v42; // rcx
  __int64 v43; // rax
  CallStackTracing *v44; // rax
  unsigned int (__fastcall *v45)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v46; // rbx
  char v47; // dl
  int v48; // ecx
  CallStackTracing *v49; // rax
  __int64 v50; // [rsp+50h] [rbp-28h] BYREF
  __int64 v51; // [rsp+58h] [rbp-20h] BYREF
  __int64 v52; // [rsp+A0h] [rbp+28h] BYREF
  __int64 v53; // [rsp+B0h] [rbp+38h]
  int v54; // [rsp+B8h] [rbp+40h] BYREF

  v53 = a3;
  v3 = a2;
  v4 = (*((_DWORD *)this + 112) & 2) == 0;
  v5 = *((_DWORD *)this + 112) & 2;
  v6 = a3;
  v50 = 0;
  v7 = !v4;
  v51 = 0;
  v54 = 0;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v9 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v10 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v9 + 3));
    if ( Value )
    {
      v10 = Value;
    }
    else if ( !GetLastError() )
    {
      v40 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v40 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v40 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v41 = (**(__int64 (__fastcall ***)(CallStackTracing *))v40)(v40);
      if ( v41 )
        v10 = (char *)v41;
    }
    SetLastError(LastError);
    v13 = *((unsigned int *)v10 + 497);
    v6 = v53;
    if ( (unsigned int)v13 < *((_DWORD *)v10 + 498) )
    {
      v14 = 2 * v13;
      *(_QWORD *)&v10[8 * v14] = "CMpeg2PESStreamParser::ParseTier1OptHeader_";
      *(_DWORD *)&v10[8 * v14 + 8] = 1908;
    }
    ++*((_DWORD *)v10 + 497);
  }
  v15 = (_BYTE *)(v3 + 14);
  v16 = (_DWORD *)((char *)this + 476);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qDDDD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      a2,
      a3,
      this,
      v7,
      *v16,
      *((_DWORD *)this + 118),
      (unsigned __int8)*v15);
  if ( v5 )
  {
    v17 = CBufferSourceManager::Complete((__int64)this + 48, v6);
    if ( v17 < 0 )
    {
      CallStackScopeTrace::CallStackScopeTrace(
        (CallStackScopeTrace *)&v52,
        "CMpeg2PESStreamParser::CompletePESCollection_",
        1218);
      if ( byte_1800EACCB )
      {
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 47, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, this, v17);
        v16 = (_DWORD *)((char *)this + 476);
      }
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v52);
      v15 = (_BYTE *)(v3 + 14);
    }
    *((_QWORD *)this + 19) = 0;
  }
  if ( *((_DWORD *)this + 118) && (int)*v16 >= 22 && *v15 == 0x8E )
  {
    *((_DWORD *)this + 123) = 1;
    *((_OWORD *)this + 31) = *(_OWORD *)(v3 + 15);
  }
  if ( !v5 )
  {
    if ( *((_DWORD *)this + 162) == 1 )
    {
      CMpeg2PESStreamParser::CompletePESCollection_(this, a2, v6);
      v46 = *((_QWORD *)this + 13) / 300LL;
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, __int64 *, __int64 *, int *))(**((_QWORD **)this + 68) + 16LL))(
        *((_QWORD *)this + 68),
        *((unsigned int *)this + 167),
        *((_QWORD *)this + 69),
        *((unsigned int *)this + 105),
        v46,
        v6,
        &v50,
        &v51,
        &v54);
      if ( v50 == -1 )
      {
        CMpeg2PESStreamParser::ResetAndWaitForNextPESPacket_(this);
        if ( (unsigned __int8)byte_1800EACCB >= 2u )
          WPP_SF_qqq(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            76,
            &WPP_2790e164590a3ed111972434a23f3cea_Traceguids,
            this,
            *((_QWORD *)this + 82),
            *((_QWORD *)this + 82) / 10000LL);
      }
      else
      {
        *((_DWORD *)this + 161) = 0;
        CBufferSourceManager::SetTimestampNext((CMpeg2PESStreamParser *)((char *)this + 48), &v50, &v51);
        if ( (unsigned __int8)byte_1800EACCB >= 8u )
          WPP_SF_qDiiiII(
            *((_QWORD *)WPP_GLOBAL_Control + 17),
            75,
            v50 / 10000,
            this,
            *((_DWORD *)this + 105),
            v46,
            v46 / 90,
            v50,
            v50,
            v50 / 10000);
      }
    }
LABEL_17:
    v18 = (*((_DWORD *)this + 112) & 2) != 0 ? 10 : 5;
    if ( (*((_DWORD *)this + 112) & 1) == 0 )
      v18 = (*((_DWORD *)this + 112) & 2) != 0 ? 5 : 0;
    v19 = v18 + 1;
    if ( !*((_DWORD *)this + 115) )
      v19 = v18;
    v20 = v19 + 1;
    if ( !*((_DWORD *)this + 116) )
      v20 = v19;
    v21 = v20 + 2;
    if ( !*((_DWORD *)this + 117) )
      v21 = v20;
    if ( *((_DWORD *)this + 118) )
    {
      v47 = *(_BYTE *)(v3 + 5);
      v48 = v21 + 17;
      if ( v47 >= 0 )
        v48 = v21 + 1;
      v21 = v48 + 2;
      if ( (v47 & 0x20) == 0 )
        v21 = v48;
      if ( (v47 & 0x10) != 0 )
        v21 += 2;
    }
    *((_DWORD *)this + 122) = *((_DWORD *)this + 119) - v21;
    goto LABEL_27;
  }
  v29 = *(_QWORD *)(v3 + 9);
  v3 += 9;
  v30 = *((_DWORD *)this + 105);
  v31 = (((unsigned __int16)v29 & 0xFF00 | ((v29 & 0xE) << 15)) << 14)
      | ((v29 & 0xFE0000 | (((unsigned int)v29 & 0xFF000000 | (v29 >> 16) & 0xFE0000) >> 15)) >> 2);
  v52 = v31;
  if ( v30 - 224 <= 0xF )
  {
    CMpeg2Stats::VideoPESPTS(*((CMpeg2Stats **)this + 67), &v52, v30);
    v31 = v52;
  }
  else
  {
    v32 = *((_QWORD *)this + 67);
    if ( *(_QWORD *)v32 )
    {
      *(_QWORD *)(*(_QWORD *)v32 + 200LL) = v31;
      *(_QWORD *)(*(_QWORD *)v32 + 216LL) = *(_QWORD *)(*(_QWORD *)v32 + 200LL)
                                          - *(_QWORD *)(*(_QWORD *)v32 + 176LL) / 300LL;
    }
    v33 = *(_QWORD **)(v32 + 8616);
    v34 = (_DWORD *)*v33;
    if ( *(_DWORD *)*v33 )
    {
      if ( *(_QWORD *)(v32 + 8592) )
      {
        v45 = *(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(v33[2] + 48LL);
        if ( v45 )
        {
          if ( v45((unsigned int)v34[1], *(unsigned int *)(v32 + 8600), *(unsigned __int8 *)(v32 + 8604)) )
          {
            **(_QWORD **)(v32 + 8592) = v31 | ((unsigned __int64)(v30 & 0x1FFF) << 33);
            Mpeg2DemuxTrace::CeHomeETWDLL::ehTraceEvent(
              *(Mpeg2DemuxTrace::CeHomeETWDLL **)(*(_QWORD *)(v32 + 8616) + 16LL),
              *(_DWORD *)(**(_QWORD **)(v32 + 8616) + 4LL),
              *(_DWORD *)(v32 + 8608),
              *(void **)(v32 + 8592),
              *(_DWORD *)(v32 + 8600),
              *(_BYTE *)(v32 + 8604),
              *(_BYTE *)(v32 + 8605));
          }
        }
      }
    }
  }
  (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, __int64, __int64, __int64 *, __int64 *, int *))(**((_QWORD **)this + 68) + 16LL))(
    *((_QWORD *)this + 68),
    *((unsigned int *)this + 167),
    *((_QWORD *)this + 69),
    *((unsigned int *)this + 105),
    v31,
    v6,
    &v50,
    &v51,
    &v54);
  if ( !*((_DWORD *)this + 161) || (unsigned int)CMpeg2PESStreamParser::CheckIfStartValid_(this, &v50) )
  {
    if ( v50 == -1 )
    {
      if ( (unsigned __int8)byte_1800EACCB >= 4u )
        WPP_SF_qDqq(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          74,
          &WPP_2790e164590a3ed111972434a23f3cea_Traceguids,
          this,
          *((_DWORD *)this + 105),
          v31,
          v31 / 90);
    }
    else
    {
      if ( v54 && (unsigned int)(*((_DWORD *)this + 105) - 192) <= 0x1F )
        *((_DWORD *)this + 30) = 1;
      (*(void (__fastcall **)(CMpeg2PESStreamParser *, __int64 *, __int64 *))(*(_QWORD *)this + 80LL))(this, &v50, &v51);
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v35 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v35);
        v37 = *((unsigned int *)ThreadRelativeContext + 497);
        if ( (unsigned int)v37 < *((_DWORD *)ThreadRelativeContext + 498) )
        {
          v38 = 2 * v37;
          *((_QWORD *)ThreadRelativeContext + v38) = "CBufferSourceManager::SetTimestampNext";
          *((_DWORD *)ThreadRelativeContext + 2 * v38 + 2) = 622;
        }
        ++*((_DWORD *)ThreadRelativeContext + 497);
      }
      if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          24,
          &WPP_2790e164590a3ed111972434a23f3cea_Traceguids,
          (char *)this + 48);
      *((_QWORD *)this + 10) = v50;
      *((_QWORD *)this + 11) = v51;
      v39 = *((_QWORD *)this + 20);
      *((_DWORD *)this + 19) = 1;
      if ( v39 == -1 )
        v39 = -1;
      else
        *((_QWORD *)this + 20) = -1;
      *((_QWORD *)this + 21) = v39;
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v52);
      if ( (unsigned __int8)byte_1800EACCB >= 8u )
        WPP_SF_qDiiiII(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          73,
          v50 / 10000,
          this,
          *((_DWORD *)this + 105),
          v31,
          v31 / 90,
          v50,
          v50,
          v50 / 10000);
    }
    goto LABEL_17;
  }
LABEL_27:
  v22 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v23 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v24 = GetLastError();
    v25 = (GUID *)TlsGetValue(*((_DWORD *)v22 + 3));
    if ( v25 )
    {
      v23 = v25;
    }
    else if ( !GetLastError() )
    {
      v42 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v49 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v49;
        if ( v49 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v49 + 8LL))(v49, 2032) )
        {
          v42 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v42 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v43 = (**(__int64 (__fastcall ***)(CallStackTracing *))v42)(v42);
      if ( v43 )
        v23 = (GUID *)v43;
    }
    SetLastError(v24);
    v26 = *(_DWORD *)&v23[124].Data2;
    if ( v26 )
    {
      v27 = v26 - 1;
      *(_DWORD *)&v23[124].Data2 = v27;
      if ( !v27 )
      {
        *(_DWORD *)&v23[124].Data2 = 0;
        *(_QWORD *)&v23[126].Data1 = 0;
        *(_DWORD *)&v23[124].Data4[4] = 0;
        v23[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v23[126].Data4 = 0;
        v23[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180006800  mov     [rsp-20h+arg_10], r8
0x180006805  push    rbp
0x180006806  push    rbx
0x180006807  push    rdi
0x180006808  push    r12
0x18000680a  mov     rbp, rsp
0x18000680d  sub     rsp, 78h
0x180006811  xor     eax, eax
0x180006813  mov     [rsp+78h+var_8], r13
0x180006818  mov     [rsp+78h+var_10], r14
0x18000681d  mov     r12d, eax
0x180006820  mov     r14d, [rcx+1C0h]
0x180006827  mov     r13, rdx
0x18000682a  and     r14d, 2
0x18000682e  mov     [rsp+78h+var_18], r15
0x180006833  mov     r15, r8
0x180006836  mov     [rbp+var_28], rax
0x18000683a  setnz   r12b
0x18000683e  mov     [rbp+var_20], rax
0x180006842  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180006849  mov     rdi, rcx
0x18000684c  mov     [rbp+arg_18], eax
0x18000684f  jz      loc_180006DF0
0x180006855  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18000685c  mov     [rsp+78h+arg_8], rsi
0x180006864  cmp     byte ptr [rbx+8], 0
0x180006868  jz      short loc_1800068D8
0x18000686a  lea     rsi, [rbx+0D0h]
0x180006871  call    cs:__imp_GetLastError
0x180006878  nop     dword ptr [rax+rax+00h]
0x18000687d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180006880  mov     r15d, eax
0x180006883  call    cs:__imp_TlsGetValue
0x18000688a  nop     dword ptr [rax+rax+00h]
0x18000688f  test    rax, rax
0x180006892  jz      loc_180006D7E
0x180006898  mov     rsi, rax
0x18000689b  mov     ecx, r15d; dwErrCode
0x18000689e  call    cs:__imp_SetLastError
0x1800068a5  nop     dword ptr [rax+rax+00h]
0x1800068aa  mov     eax, [rsi+7C4h]
0x1800068b0  mov     r15, [rbp+arg_10]
0x1800068b4  cmp     eax, [rsi+7C8h]
0x1800068ba  jnb     short loc_1800068D2
0x1800068bc  add     rax, rax
0x1800068bf  lea     rcx, aCmpeg2pesstrea_15; "CMpeg2PESStreamParser::ParseTier1OptHea"...
0x1800068c6  mov     [rsi+rax*8], rcx
0x1800068ca  mov     dword ptr [rsi+rax*8+8], 774h
0x1800068d2  inc     dword ptr [rsi+7C4h]
0x1800068d8  cmp     cs:byte_1800EACCB, 20h ; ' '
0x1800068df  lea     rsi, [r13+0Eh]
0x1800068e3  lea     rbx, [rdi+1DCh]
0x1800068ea  jnb     loc_180006E49
0x1800068f0  test    r14d, r14d
0x1800068f3  jz      loc_180006CA2
0x1800068f9  lea     rcx, [rdi+30h]
0x1800068fd  mov     rdx, r15
0x180006900  call    ?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::Complete(CTStickyVal<int> *)
0x180006905  mov     r12d, eax
0x180006908  test    eax, eax
0x18000690a  js      loc_180006E80
0x180006910  xor     r12d, r12d
0x180006913  mov     [rdi+98h], r12
0x18000691a  cmp     dword ptr [rdi+1D8h], 0
0x180006921  jnz     loc_180006CDF
0x180006927  test    r14d, r14d
0x18000692a  jnz     loc_180006A67
0x180006930  cmp     dword ptr [rdi+288h], 1
0x180006937  jz      loc_180007015
0x18000693d  mov     edx, [rdi+1C0h]
0x180006943  mov     eax, edx
0x180006945  and     al, 2
0x180006947  neg     al
0x180006949  sbb     ecx, ecx
0x18000694b  and     ecx, 5
0x18000694e  test    dl, 1
0x180006951  lea     eax, [rcx+5]
0x180006954  cmovz   eax, ecx
0x180006957  cmp     dword ptr [rdi+1CCh], 0
0x18000695e  lea     ecx, [rax+1]
0x180006961  cmovz   ecx, eax
0x180006964  cmp     dword ptr [rdi+1D0h], 0
0x18000696b  lea     eax, [rcx+1]
0x18000696e  cmovz   eax, ecx
0x180006971  cmp     dword ptr [rdi+1D4h], 0
0x180006978  lea     r8d, [rax+2]
0x18000697c  cmovz   r8d, eax
0x180006980  cmp     dword ptr [rdi+1D8h], 0
0x180006987  jnz     loc_1800071A9
0x18000698d  mov     eax, [rdi+1DCh]
0x180006993  sub     eax, r8d
0x180006996  mov     [rdi+1E8h], eax
0x18000699c  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800069a3  mov     r15, [rsp+78h+var_18]
0x1800069a8  mov     r14, [rsp+78h+var_10]
0x1800069ad  mov     r13, [rsp+78h+var_8]
0x1800069b2  cmp     byte ptr [rbx+8], 0
0x1800069b6  jz      loc_180006A4F
0x1800069bc  lea     rdi, [rbx+0D0h]
0x1800069c3  call    cs:__imp_GetLastError
0x1800069ca  nop     dword ptr [rax+rax+00h]
0x1800069cf  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800069d2  mov     esi, eax
0x1800069d4  call    cs:__imp_TlsGetValue
0x1800069db  nop     dword ptr [rax+rax+00h]
0x1800069e0  test    rax, rax
0x1800069e3  jz      loc_180006DB5
0x1800069e9  mov     rdi, rax
0x1800069ec  mov     ecx, esi; dwErrCode
0x1800069ee  call    cs:__imp_SetLastError
0x1800069f5  nop     dword ptr [rax+rax+00h]
0x1800069fa  mov     eax, [rdi+7C4h]
0x180006a00  test    eax, eax
0x180006a02  jz      short loc_180006A4F
0x180006a04  sub     eax, 1
0x180006a07  mov     [rdi+7C4h], eax
0x180006a0d  jnz     short loc_180006A4F
0x180006a0f  mov     [rdi+7C4h], r12d
0x180006a16  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180006a1d  mov     qword ptr [rdi+7E0h], 0
0x180006a28  mov     [rdi+7CCh], r12d
0x180006a2f  movups  xmmword ptr [rdi+7D0h], xmm0
0x180006a36  mov     [rdi+7E8h], r12d
0x180006a3d  call    cs:__imp_GetCurrentThreadId
0x180006a44  nop     dword ptr [rax+rax+00h]
0x180006a49  mov     [rdi+7C0h], eax
0x180006a4f  mov     rsi, [rsp+78h+arg_8]
0x180006a57  mov     eax, 1
0x180006a5c  add     rsp, 78h
0x180006a60  pop     r12
0x180006a62  pop     rdi
0x180006a63  pop     rbx
0x180006a64  pop     rbp
0x180006a65  retn
0x180006a67  mov     rcx, [r13+9]
0x180006a6b  add     r13, 9
0x180006a6f  mov     r14d, [rdi+1A4h]
0x180006a76  mov     rsi, rcx
0x180006a79  shr     rsi, 10h
0x180006a7d  mov     rax, rcx
0x180006a80  and     esi, 0FE0000h
0x180006a86  mov     edx, 0FF000000h
0x180006a8b  and     rax, rdx
0x180006a8e  or      rsi, rax
0x180006a91  mov     rax, rcx
0x180006a94  and     eax, 0FE0000h
0x180006a99  shr     rsi, 0Fh
0x180006a9d  or      rsi, rax
0x180006aa0  mov     rax, rcx
0x180006aa3  and     eax, 0Eh
0x180006aa6  shr     rsi, 2
0x180006aaa  shl     rax, 0Fh
0x180006aae  and     ecx, 0FF00h
0x180006ab4  or      rax, rcx
0x180006ab7  shl     rax, 0Eh
0x180006abb  or      rsi, rax
0x180006abe  lea     eax, [r14-0E0h]
0x180006ac5  mov     [rbp+arg_0], rsi
0x180006ac9  cmp     eax, 0Fh
0x180006acc  jbe     loc_180006CC3
0x180006ad2  mov     rbx, [rdi+218h]
0x180006ad9  mov     rax, [rbx]
0x180006adc  test    rax, rax
0x180006adf  jnz     loc_180006EDF
0x180006ae5  mov     rax, [rbx+21A8h]
0x180006aec  mov     rcx, [rax]
0x180006aef  cmp     dword ptr [rcx], 0
0x180006af2  jnz     loc_180006F1E
0x180006af8  mov     rcx, [rdi+220h]
0x180006aff  lea     rdx, [rbp+arg_18]
0x180006b03  mov     r9d, [rdi+1A4h]
0x180006b0a  mov     r8, [rdi+228h]
0x180006b11  mov     [rsp+78h+var_38], rdx
0x180006b16  lea     rdx, [rbp+var_20]
0x180006b1a  mov     rax, [rcx]
0x180006b1d  mov     [rsp+78h+var_40], rdx
0x180006b22  lea     rdx, [rbp+var_28]
0x180006b26  mov     qword ptr [rsp+78h+var_48], rdx
0x180006b2b  mov     edx, [rdi+29Ch]
0x180006b31  mov     rax, [rax+10h]
0x180006b35  mov     qword ptr [rsp+78h+var_50], r15
0x180006b3a  mov     qword ptr [rsp+78h+var_58], rsi
0x180006b3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b44  cmp     dword ptr [rdi+284h], 0
0x180006b4b  jnz     loc_180006CAA
0x180006b51  cmp     [rbp+var_28], 0FFFFFFFFFFFFFFFFh
0x180006b56  jz      loc_180006D18
0x180006b5c  cmp     [rbp+arg_18], 0
0x180006b60  jnz     loc_180006FBC
0x180006b66  mov     rax, [rdi]
0x180006b69  lea     r8, [rbp+var_20]
0x180006b6d  lea     rdx, [rbp+var_28]
0x180006b71  mov     rcx, rdi
0x180006b74  mov     rax, [rax+50h]
0x180006b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180006b84  test    rcx, rcx
0x180006b87  jz      loc_180006FDC
0x180006b8d  cmp     byte ptr [rcx+8], 0
0x180006b91  jz      short loc_180006BC2
0x180006b93  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180006b98  mov     ecx, [rax+7C4h]
0x180006b9e  cmp     ecx, [rax+7C8h]
0x180006ba4  jnb     short loc_180006BBC
0x180006ba6  add     rcx, rcx
0x180006ba9  lea     rdx, aCbuffersourcem_5; "CBufferSourceManager::SetTimestampNext"
0x180006bb0  mov     [rax+rcx*8], rdx
0x180006bb4  mov     dword ptr [rax+rcx*8+8], 26Eh
0x180006bbc  inc     dword ptr [rax+7C4h]
0x180006bc2  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180006bc9  jnb     loc_180006FED
0x180006bcf  mov     rax, [rbp+var_28]
0x180006bd3  mov     [rdi+50h], rax
0x180006bd7  mov     rax, [rbp+var_20]
0x180006bdb  mov     [rdi+58h], rax
0x180006bdf  mov     rax, [rdi+0A0h]
0x180006be6  mov     dword ptr [rdi+4Ch], 1
0x180006bed  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006bf1  jz      loc_180006D0C
0x180006bf7  mov     qword ptr [rdi+0A0h], 0FFFFFFFFFFFFFFFFh
0x180006c02  lea     rcx, [rbp+arg_0]; this
0x180006c06  mov     [rdi+0A8h], rax
0x180006c0d  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180006c12  cmp     cs:byte_1800EACCB, 8
0x180006c19  jb      loc_18000693D
0x180006c1f  mov     r9, [rbp+var_28]
0x180006c23  mov     rax, 346DC5D63886594Bh
0x180006c2d  imul    r9
0x180006c30  mov     r8, rdx
0x180006c33  sar     r8, 0Bh
0x180006c37  mov     rax, r8
0x180006c3a  shr     rax, 3Fh
0x180006c3e  add     r8, rax
0x180006c41  mov     rax, 2D82D82D82D82D83h
0x180006c4b  imul    rsi
0x180006c4e  mov     [rsp+78h+var_30], r8
0x180006c53  mov     [rsp+78h+var_38], r9
0x180006c58  mov     rcx, rdx
0x180006c5b  sar     rcx, 4
0x180006c5f  mov     edx, 49h ; 'I'
0x180006c64  mov     rax, rcx
0x180006c67  mov     [rsp+78h+var_40], r9
0x180006c6c  shr     rax, 3Fh
0x180006c70  mov     r9, rdi
0x180006c73  add     rcx, rax
0x180006c76  mov     eax, [rdi+1A4h]
0x180006c7c  mov     qword ptr [rsp+78h+var_48], rcx
0x180006c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c88  mov     qword ptr [rsp+78h+var_50], rsi
0x180006c8d  mov     [rsp+78h+var_58], eax
0x180006c91  mov     rcx, [rcx+88h]
0x180006c98  call    WPP_SF_qDiiiII
0x180006c9d  jmp     loc_18000693D
0x180006ca2  xor     r12d, r12d
0x180006ca5  jmp     loc_18000691A
0x180006caa  lea     rdx, [rbp+var_28]; __int64 *
0x180006cae  mov     rcx, rdi; this
0x180006cb1  call    ?CheckIfStartValid_@CMpeg2PESStreamParser@@IEAAHAEA_J@Z; CMpeg2PESStreamParser::CheckIfStartValid_(__int64 &)
0x180006cb6  test    eax, eax
0x180006cb8  jz      loc_18000699C
0x180006cbe  jmp     loc_180006B51
0x180006cc3  mov     rcx, [rdi+218h]; this
0x180006cca  lea     rdx, [rbp+arg_0]; __int64 *
0x180006cce  mov     r8d, r14d; unsigned int
0x180006cd1  call    ?VideoPESPTS@CMpeg2Stats@@QEAAXPEA_JK@Z; CMpeg2Stats::VideoPESPTS(__int64 *,ulong)
0x180006cd6  mov     rsi, [rbp+arg_0]
0x180006cda  jmp     loc_180006AF8
0x180006cdf  cmp     dword ptr [rbx], 16h
0x180006ce2  jl      loc_180006927
0x180006ce8  cmp     byte ptr [rsi], 8Eh
0x180006ceb  jnz     loc_180006927
0x180006cf1  mov     dword ptr [rdi+1ECh], 1
0x180006cfb  movups  xmm0, xmmword ptr [r13+0Fh]
0x180006d00  movups  xmmword ptr [rdi+1F0h], xmm0
0x180006d07  jmp     loc_180006927
0x180006d0c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180006d13  jmp     loc_180006C02
0x180006d18  cmp     cs:byte_1800EACCB, 4
0x180006d1f  jb      loc_18000693D
0x180006d25  mov     rax, 2D82D82D82D82D83h
0x180006d2f  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x180006d36  imul    rsi
0x180006d39  mov     r9, rdi
0x180006d3c  mov     rcx, rdx
0x180006d3f  mov     edx, 4Ah ; 'J'
0x180006d44  sar     rcx, 4
0x180006d48  mov     rax, rcx
0x180006d4b  shr     rax, 3Fh
0x180006d4f  add     rcx, rax
0x180006d52  mov     eax, [rdi+1A4h]
0x180006d58  mov     qword ptr [rsp+78h+var_48], rcx
0x180006d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d64  mov     qword ptr [rsp+78h+var_50], rsi
0x180006d69  mov     [rsp+78h+var_58], eax
0x180006d6d  mov     rcx, [rcx+88h]
0x180006d74  call    WPP_SF_qDqq
0x180006d79  jmp     loc_18000693D
0x180006d7e  call    cs:__imp_GetLastError
0x180006d85  nop     dword ptr [rax+rax+00h]
0x180006d8a  test    eax, eax
  ... truncated ...
```
