# CMPEG2PushClock::NewPCRValue(ulong,__int64,int,int,CTStickyVal<int> *)

- ea: `0x180012860`
- end: `0x1800130b8`
- name: `?NewPCRValue@CMPEG2PushClock@@UEAAJK_JHHPEAV?$CTStickyVal@H@@@Z`
- size: `2136`
- prototype: `__int64 __fastcall(__int64, __int16, __int64, int, int, _DWORD *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x180012860`
- `0x1800140b0`
- `0x180016620`
- `0x18001a29c`
- `0x18002d514`
- `0x180036418`
- `0x1800560e8`
- `0x18007c8e8`
- `0x18008775c`
- `0x1800a3738`
- `0x1800b3544`
- `0x1800b37f0`
- `0x1800b3b48`
- `0x1800b3c98`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012b46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012b46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012aa3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012aa3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800129f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800129f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800129c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012cbe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012a43`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800129d9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800129d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012ac6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012ac6`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180012c0e`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180012c0e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012ee6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180012ee6`

## pseudocode

```c
__int64 __fastcall CMPEG2PushClock::NewPCRValue(__int64 a1, __int16 a2, __int64 a3, int a4, int a5, _DWORD *a6)
{
  __int64 v7; // rbx
  _QWORD *v11; // rax
  _DWORD *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdx
  __int64 v16; // rbx
  _DWORD *v17; // r12
  _BOOL8 v18; // r8
  __int64 v19; // rdi
  unsigned __int64 v20; // rbx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  CallStackTracing *v24; // rdi
  GUID *v25; // rsi
  DWORD LastError; // r14d
  GUID *Value; // rax
  int v28; // eax
  int v29; // eax
  int v30; // r13d
  __int64 v31; // rbp
  DWORD TickCount; // eax
  DWORD v33; // r10d
  int v34; // ecx
  struct CallStackContext *v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  struct CallStackContext *v38; // rax
  int v39; // ecx
  int v40; // ecx
  DWORD v42; // esi
  int v43; // edi
  int v44; // edx
  __int64 v45; // rcx
  CallStackTracing *v46; // rcx
  __int64 v47; // rax
  _QWORD *v48; // rcx
  unsigned int (__fastcall *v49)(_QWORD, _QWORD, _QWORD); // rax
  unsigned __int64 v50; // rax
  CallStackTracing *v51; // rax
  unsigned int v52; // r10d
  double v53; // xmm0_8
  __int64 v54; // rcx
  int v55; // edx
  __int64 v56; // r8
  _QWORD v57[11]; // [rsp+50h] [rbp-58h] BYREF
  __int64 v58; // [rsp+B0h] [rbp+8h]
  DWORD v59; // [rsp+B8h] [rbp+10h] BYREF
  __int64 v60; // [rsp+C0h] [rbp+18h]

  v7 = *(_QWORD *)(a1 - 8 + 280);
  v60 = a1 - 8;
  if ( *(_QWORD *)v7 )
  {
    *(_QWORD *)(*(_QWORD *)v7 + 176LL) = a3;
    ++*(_QWORD *)(*(_QWORD *)v7 + 184LL);
  }
  v11 = *(_QWORD **)(v7 + 8576);
  v12 = (_DWORD *)*v11;
  if ( *(_DWORD *)*v11 )
  {
    if ( *(_QWORD *)(v7 + 8552) )
    {
      v49 = *(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(v11[2] + 48LL);
      if ( v49 )
      {
        if ( v49((unsigned int)v12[1], *(unsigned int *)(v7 + 8560), *(unsigned __int8 *)(v7 + 8564)) )
        {
          **(_QWORD **)(v7 + 8552) = a3 & 0x3FFFFFFFFFFLL | ((unsigned __int64)(a2 & 0x1FFF) << 43);
          Mpeg2DemuxTrace::CeHomeETWDLL::ehTraceEvent(
            *(Mpeg2DemuxTrace::CeHomeETWDLL **)(*(_QWORD *)(v7 + 8576) + 16LL),
            *(_DWORD *)(**(_QWORD **)(v7 + 8576) + 4LL),
            *(_DWORD *)(v7 + 8568),
            *(void **)(v7 + 8552),
            *(_DWORD *)(v7 + 8560),
            *(_BYTE *)(v7 + 8564),
            *(_BYTE *)(v7 + 8565));
        }
      }
    }
  }
  v13 = *(_QWORD *)(a1 + 656);
  if ( v13 == -1 )
  {
    *(_QWORD *)(a1 + 656) = a3;
    v13 = a3;
  }
  if ( *(_QWORD *)(a1 + 664) == -1 )
  {
    v48 = *(_QWORD **)(a1 + 680);
    *(_QWORD *)(a1 + 664) = a3;
    if ( *v48 )
      *(_QWORD *)(*v48 + 168LL) = a3;
    v48[1189] = a3;
    CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v59, "CMpeg2Time::GetElapsedPCRTime", 790);
    if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 17, &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids, a1 + 616);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v59);
    v13 = *(_QWORD *)(a1 + 656);
  }
  v14 = a3 - *(_QWORD *)(a1 + 664);
  if ( (unsigned __int64)v14 > 0x258000000D3LL )
  {
    v50 = 0x258000000D4LL;
    if ( v14 > 0 )
      v50 = 0xFFFFFDA7FFFFFF2EuLL;
    v14 += v50;
  }
  v15 = *(_QWORD *)(a1 + 624);
  v16 = 2 * v14;
  v17 = 0;
  if ( a3 < v13 )
  {
    if ( v13 - a3 <= v15 )
    {
      v18 = 0;
      goto LABEL_10;
    }
    v19 = 1;
  }
  else
  {
    v18 = a3 - v13 > v15;
    v19 = v18;
    if ( a3 - v13 <= v15 )
      goto LABEL_10;
  }
  v57[1] = v13;
  v45 = *(_QWORD *)(a1 + 680) + 8504LL;
  v57[0] = 3;
  v57[2] = a3;
  Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(v45, v57);
  v18 = v19;
LABEL_10:
  v20 = v18 | (++*(_QWORD *)(a1 + 672) << 43) | v16 & 0x7FFFFFFFFFELL;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v22 = *((unsigned int *)ThreadRelativeContext + 497);
    if ( (unsigned int)v22 < *((_DWORD *)ThreadRelativeContext + 498) )
    {
      v23 = 2 * v22;
      *((_QWORD *)ThreadRelativeContext + v23) = "CMpeg2Time::GetElapsedPCRTime";
      *((_DWORD *)ThreadRelativeContext + 2 * v23 + 2) = 799;
    }
    ++*((_DWORD *)ThreadRelativeContext + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qqqq(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      18,
      &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids,
      a1 + 616,
      a3 / 27000,
      *(_QWORD *)(a1 + 656) / 27000LL,
      *(_QWORD *)(a1 + 664) / 27000LL);
  v24 = CallStackTracing::s_wpInstance;
  *(_QWORD *)(a1 + 656) = a3;
  if ( *((_BYTE *)v24 + 8) )
  {
    v25 = (GUID *)((char *)v24 + 208);
    LastError = GetLastError();
    Value = (GUID *)TlsGetValue(*((_DWORD *)v24 + 3));
    if ( Value )
    {
      v25 = Value;
    }
    else if ( !GetLastError() )
    {
      v46 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v51 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
        CallStackTracing::s_wpInstance = v51;
        if ( v51 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v51 + 8LL))(v51, 2032) )
        {
          v46 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v47 = (**(__int64 (__fastcall ***)(CallStackTracing *))v46)(v46);
      if ( v47 )
        v25 = (GUID *)v47;
    }
    SetLastError(LastError);
    v28 = *(_DWORD *)&v25[124].Data2;
    if ( v28 )
    {
      v29 = v28 - 1;
      *(_DWORD *)&v25[124].Data2 = v29;
      if ( !v29 )
      {
        *(_DWORD *)&v25[124].Data2 = 0;
        *(_QWORD *)&v25[126].Data1 = 0;
        *(_DWORD *)&v25[124].Data4[4] = 0;
        v25[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v25[126].Data4 = 0;
        v25[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  if ( v20 >> 43 > 1 && a4 && !*(_DWORD *)(a1 + 688) )
  {
    v44 = 1;
    if ( a6[1] == *a6 )
      v44 = a6[1];
    a6[1] = v44;
    return 0;
  }
  v30 = v20 & 1;
  if ( (v20 & 1) != 0 )
  {
    if ( a6 && !*(_DWORD *)(a1 + 688) )
    {
      v55 = 1;
      if ( a6[1] == *a6 )
        v55 = a6[1];
      a6[1] = v55;
    }
    goto LABEL_33;
  }
  if ( *(_DWORD *)(a1 + 700) != v30 )
  {
    v42 = *(_DWORD *)(a1 + 704);
    v43 = *(_DWORD *)(a1 + 696);
    if ( timeGetTime() - v43 >= v42 )
    {
      *(_DWORD *)(a1 + 700) = 0;
      CTClockSubordinate<__int64,__int64>::OnMasterTime(a1 + 24, (v20 >> 1) & 0x3FFFFFFFFFFLL);
    }
    goto LABEL_33;
  }
  v31 = a1 + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)(v31 + 160));
  v58 = (***(__int64 (__fastcall ****)(_QWORD))(v31 + 96))(*(_QWORD *)(v31 + 96));
  TickCount = GetTickCount();
  v33 = TickCount;
  v59 = TickCount;
  if ( *(_DWORD *)(v31 + 32) != v30 )
  {
LABEL_29:
    v34 = *(_DWORD *)(v31 + 32);
    if ( v34 > 0 )
      v17 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v31 + 8)
                                   + 8LL
                                   * ((v34 - 1 + *(_DWORD *)(v31 + 36))
                                    % (*(_DWORD *)(v31 + 20) * *(_DWORD *)(v31 + 24))
                                    / *(_DWORD *)(v31 + 24)))
                       + 8LL
                       * ((v34 - 1 + *(_DWORD *)(v31 + 36))
                        % (*(_DWORD *)(v31 + 20) * *(_DWORD *)(v31 + 24))
                        % *(_DWORD *)(v31 + 24)));
    *(_QWORD *)(v31 + 216) = v58;
    *(_QWORD *)(v31 + 208) = (v20 >> 1) & 0x3FFFFFFFFFFLL;
    if ( v33 - *v17 < *(_DWORD *)(v31 + 128) )
      goto LABEL_32;
    v53 = CTClockSubordinate<__int64,__int64>::ObservedTailScalingVal_(v31);
    if ( v53 < *(double *)(v31 + 136) || *(double *)(v31 + 144) < v53 )
    {
      v54 = *(_QWORD *)(v31 + 152);
      if ( *(_QWORD *)v54 )
      {
        ++*(_WORD *)(*(_QWORD *)v54 + 122LL);
        goto LABEL_84;
      }
    }
    else
    {
      v54 = *(_QWORD *)(v31 + 152);
      if ( *(_QWORD *)v54 )
      {
        ++*(_WORD *)(*(_QWORD *)v54 + 120LL);
LABEL_84:
        *(double *)(*(_QWORD *)v54 + 152LL) = v53;
      }
    }
    CTClockSubordinate<__int64,__int64>::TrimQueue_(v31, v52);
    CTClockSubordinate<__int64,__int64>::QueueNewBracket_(v31, (v20 >> 1) & 0x3FFFFFFFFFFLL, v58, v59);
    CTClockSubordinate<__int64,__int64>::ComputeNewScalingVal_(v31);
    goto LABEL_32;
  }
  if ( !(unsigned int)CTClockSubordinate<__int64,__int64>::QueueNewBracket_(
                        v31,
                        (v20 >> 1) & 0x3FFFFFFFFFFLL,
                        v58,
                        TickCount) )
  {
    v33 = v59;
    goto LABEL_29;
  }
LABEL_32:
  LeaveCriticalSection((LPCRITICAL_SECTION)(v31 + 160));
LABEL_33:
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v35 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v36 = *((unsigned int *)v35 + 497);
    if ( (unsigned int)v36 < *((_DWORD *)v35 + 498) )
    {
      v37 = 2 * v36;
      *((_QWORD *)v35 + v37) = "CMPEG2PushClock::NewPCRValue";
      *((_DWORD *)v35 + 2 * v37 + 2) = 1795;
    }
    ++*((_DWORD *)v35 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 8u )
  {
    if ( (v20 & 1) != 0 )
      v56 = -1;
    else
      v56 = (__int64)((v20 >> 1) & 0x3FFFFFFFFFFLL) / 27000;
    WPP_SF_qDDiii(*((_QWORD *)WPP_GLOBAL_Control + 17), a3 / 27000, v56, v60, v20 >> 43, v20 & 1, a3, a3 / 27000, v56);
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v38 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v39 = *((_DWORD *)v38 + 497);
    if ( v39 )
    {
      v40 = v39 - 1;
      *((_DWORD *)v38 + 497) = v40;
      if ( !v40 )
        CallStackContext::ClearState(v38);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012860  push    rbx
0x180012862  push    rbp
0x180012863  push    rsi
0x180012864  push    rdi
0x180012865  push    r13
0x180012867  push    r14
0x180012869  push    r15
0x18001286b  sub     rsp, 70h
0x18001286f  lea     rax, [rcx-8]
0x180012873  mov     r13d, r9d
0x180012876  mov     rbx, [rax+118h]
0x18001287d  mov     r15, r8
0x180012880  mov     [rsp+0A8h+arg_10], rax
0x180012888  mov     edi, edx
0x18001288a  mov     rbp, rcx
0x18001288d  mov     rax, [rbx]
0x180012890  test    rax, rax
0x180012893  jnz     loc_180012D6E
0x180012899  mov     rax, [rbx+2180h]
0x1800128a0  mov     rsi, 3FFFFFFFFFFh
0x1800128aa  mov     rcx, [rax]
0x1800128ad  cmp     dword ptr [rcx], 0
0x1800128b0  jnz     loc_180012D84
0x1800128b6  lea     rsi, [rbp+268h]
0x1800128bd  mov     rcx, [rsi+28h]
0x1800128c1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800128c5  jz      loc_180012E29
0x1800128cb  cmp     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFFh
0x1800128d0  lea     r14, aCmpeg2timeGete; "CMpeg2Time::GetElapsedPCRTime"
0x1800128d7  jz      loc_180012CF9
0x1800128dd  mov     rbx, r15
0x1800128e0  mov     rax, 258000000D3h
0x1800128ea  sub     rbx, [rsi+30h]
0x1800128ee  cmp     rbx, rax
0x1800128f1  ja      loc_180012E35
0x1800128f7  mov     rdx, [rsi+8]
0x1800128fb  add     rbx, rbx
0x1800128fe  mov     [rsp+0A8h+arg_18], r12
0x180012906  xor     r12d, r12d
0x180012909  cmp     r15, rcx
0x18001290c  jl      loc_180012C76
0x180012912  mov     rax, r15
0x180012915  mov     r8d, r12d
0x180012918  sub     rax, rcx
0x18001291b  mov     edi, r12d
0x18001291e  cmp     rax, rdx
0x180012921  setnle  r8b
0x180012925  setnle  dil
0x180012929  jg      loc_180012C8E
0x18001292f  inc     qword ptr [rsi+38h]
0x180012933  mov     rcx, 7FFFFFFFFFEh
0x18001293d  mov     rax, [rsi+38h]
0x180012941  and     rbx, rcx
0x180012944  shl     rax, 2Bh
0x180012948  or      rbx, rax
0x18001294b  or      rbx, r8
0x18001294e  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180012956  jz      loc_180012E56
0x18001295c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012963  cmp     byte ptr [rdi+8], 0
0x180012967  jz      short loc_180012994
0x180012969  mov     rcx, rdi; this
0x18001296c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012971  mov     ecx, [rax+7C4h]
0x180012977  cmp     ecx, [rax+7C8h]
0x18001297d  jnb     short loc_18001298E
0x18001297f  add     rcx, rcx
0x180012982  mov     [rax+rcx*8], r14
0x180012986  mov     dword ptr [rax+rcx*8+8], 31Fh
0x18001298e  inc     dword ptr [rax+7C4h]
0x180012994  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18001299b  mov     r8, 9B5837385BA10893h
0x1800129a5  jnb     loc_180012E60
0x1800129ab  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800129b2  mov     [rsi+28h], r15
0x1800129b6  cmp     byte ptr [rdi+8], 0
0x1800129ba  jz      loc_180012A55
0x1800129c0  lea     rsi, [rdi+0D0h]
0x1800129c7  call    cs:__imp_GetLastError
0x1800129ce  nop     dword ptr [rax+rax+00h]
0x1800129d3  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800129d6  mov     r14d, eax
0x1800129d9  call    cs:__imp_TlsGetValue
0x1800129e0  nop     dword ptr [rax+rax+00h]
0x1800129e5  test    rax, rax
0x1800129e8  jz      loc_180012CBE
0x1800129ee  mov     rsi, rax
0x1800129f1  mov     ecx, r14d; dwErrCode
0x1800129f4  call    cs:__imp_SetLastError
0x1800129fb  nop     dword ptr [rax+rax+00h]
0x180012a00  mov     eax, [rsi+7C4h]
0x180012a06  test    eax, eax
0x180012a08  jz      short loc_180012A55
0x180012a0a  sub     eax, 1
0x180012a0d  mov     [rsi+7C4h], eax
0x180012a13  jnz     short loc_180012A55
0x180012a15  mov     [rsi+7C4h], r12d
0x180012a1c  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180012a23  mov     qword ptr [rsi+7E0h], 0
0x180012a2e  mov     [rsi+7CCh], r12d
0x180012a35  movups  xmmword ptr [rsi+7D0h], xmm0
0x180012a3c  mov     [rsi+7E8h], r12d
0x180012a43  call    cs:__imp_GetCurrentThreadId
0x180012a4a  nop     dword ptr [rax+rax+00h]
0x180012a4f  mov     [rsi+7C0h], eax
0x180012a55  mov     r14, rbx
0x180012a58  shr     r14, 2Bh
0x180012a5c  cmp     r14, 1
0x180012a60  jbe     short loc_180012A6B
0x180012a62  test    r13d, r13d
0x180012a65  jnz     loc_180012C4C
0x180012a6b  mov     r13, rbx
0x180012a6e  and     r13d, 1
0x180012a72  jnz     loc_180012FE6
0x180012a78  cmp     [rbp+2BCh], r13d
0x180012a7f  jnz     loc_180012C02
0x180012a85  mov     rax, 3FFFFFFFFFFh
0x180012a8f  add     rbp, 18h
0x180012a93  mov     rdi, rbx
0x180012a96  shr     rdi, 1
0x180012a99  and     rdi, rax
0x180012a9c  lea     rcx, [rbp+0A0h]; lpCriticalSection
0x180012aa3  call    cs:__imp_EnterCriticalSection
0x180012aaa  nop     dword ptr [rax+rax+00h]
0x180012aaf  mov     rcx, [rbp+60h]
0x180012ab3  mov     rax, [rcx]
0x180012ab6  mov     rax, [rax]
0x180012ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012abe  mov     [rsp+0A8h+arg_0], rax
0x180012ac6  call    cs:__imp_GetTickCount
0x180012acd  nop     dword ptr [rax+rax+00h]
0x180012ad2  mov     r10d, eax
0x180012ad5  mov     [rsp+0A8h+arg_8], eax
0x180012adc  cmp     [rbp+20h], r13d
0x180012ae0  jz      loc_180012F35
0x180012ae6  mov     ecx, [rbp+20h]
0x180012ae9  test    ecx, ecx
0x180012aeb  jle     short loc_180012B16
0x180012aed  mov     eax, [rbp+24h]
0x180012af0  dec     ecx
0x180012af2  add     eax, ecx
0x180012af4  mov     ecx, [rbp+18h]
0x180012af7  imul    ecx, [rbp+14h]
0x180012afb  cdq
0x180012afc  idiv    ecx
0x180012afe  mov     eax, edx
0x180012b00  cdq
0x180012b01  idiv    dword ptr [rbp+18h]
0x180012b04  movsxd  r8, eax
0x180012b07  mov     rax, [rbp+8]
0x180012b0b  movsxd  rcx, edx
0x180012b0e  mov     rax, [rax+r8*8]
0x180012b12  mov     r12, [rax+rcx*8]
0x180012b16  mov     rax, [rsp+0A8h+arg_0]
0x180012b1e  mov     [rbp+0D8h], rax
0x180012b25  mov     eax, r10d
0x180012b28  mov     [rbp+0D0h], rdi
0x180012b2f  sub     eax, [r12]
0x180012b33  cmp     eax, [rbp+80h]
0x180012b39  jnb     loc_180012F60
0x180012b3f  lea     rcx, [rbp+0A0h]; lpCriticalSection
0x180012b46  call    cs:__imp_LeaveCriticalSection
0x180012b4d  nop     dword ptr [rax+rax+00h]
0x180012b52  mov     rsi, 3FFFFFFFFFFh
0x180012b5c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b64  jz      loc_180013023
0x180012b6a  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012b71  cmp     byte ptr [rdi+8], 0
0x180012b75  jz      short loc_180012BA9
0x180012b77  mov     rcx, rdi; this
0x180012b7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012b7f  mov     ecx, [rax+7C4h]
0x180012b85  cmp     ecx, [rax+7C8h]
0x180012b8b  jnb     short loc_180012BA3
0x180012b8d  add     rcx, rcx
0x180012b90  lea     rdx, aCmpeg2pushcloc_11; "CMPEG2PushClock::NewPCRValue"
0x180012b97  mov     [rax+rcx*8], rdx
0x180012b9b  mov     dword ptr [rax+rcx*8+8], 703h
0x180012ba3  inc     dword ptr [rax+7C4h]
0x180012ba9  cmp     cs:byte_1800EACCB, 8
0x180012bb0  jnb     loc_18001302D
0x180012bb6  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012bbd  cmp     byte ptr [rdi+8], 0
0x180012bc1  jz      short loc_180012BE8
0x180012bc3  mov     rcx, rdi; this
0x180012bc6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012bcb  mov     ecx, [rax+7C4h]
0x180012bd1  test    ecx, ecx
0x180012bd3  jz      short loc_180012BE8
0x180012bd5  sub     ecx, 1
0x180012bd8  mov     [rax+7C4h], ecx
0x180012bde  jnz     short loc_180012BE8
0x180012be0  mov     rcx, rax; this
0x180012be3  call    ?ClearState@CallStackContext@@QEAAXXZ; CallStackContext::ClearState(void)
0x180012be8  mov     r12, [rsp+0A8h+arg_18]
0x180012bf0  xor     eax, eax
0x180012bf2  add     rsp, 70h
0x180012bf6  pop     r15
0x180012bf8  pop     r14
0x180012bfa  pop     r13
0x180012bfc  pop     rdi
0x180012bfd  pop     rsi
0x180012bfe  pop     rbp
0x180012bff  pop     rbx
0x180012c00  retn
0x180012c02  mov     esi, [rbp+2C0h]
0x180012c08  mov     edi, [rbp+2B8h]
0x180012c0e  call    cs:__imp_timeGetTime
0x180012c15  nop     dword ptr [rax+rax+00h]
0x180012c1a  sub     eax, edi
0x180012c1c  cmp     eax, esi
0x180012c1e  mov     rsi, 3FFFFFFFFFFh
0x180012c28  jb      loc_180012B5C
0x180012c2e  mov     rdx, rbx
0x180012c31  mov     [rbp+2BCh], r12d
0x180012c38  shr     rdx, 1
0x180012c3b  lea     rcx, [rbp+18h]
0x180012c3f  and     rdx, rsi
0x180012c42  call    ?OnMasterTime@?$CTClockSubordinate@_J_J@@QEAAX_J@Z; CTClockSubordinate<__int64,__int64>::OnMasterTime(__int64)
0x180012c47  jmp     loc_180012B5C
0x180012c4c  cmp     dword ptr [rbp+2B0h], 0
0x180012c53  jnz     loc_180012A6B
0x180012c59  mov     rcx, [rsp+0A8h+arg_28]
0x180012c61  mov     edx, 1
0x180012c66  mov     eax, [rcx+4]
0x180012c69  cmp     eax, [rcx]
0x180012c6b  cmovz   edx, eax
0x180012c6e  mov     [rcx+4], edx
0x180012c71  jmp     loc_180012BE8
0x180012c76  mov     rax, rcx
0x180012c79  sub     rax, r15
0x180012c7c  cmp     rax, rdx
0x180012c7f  jg      short loc_180012C89
0x180012c81  mov     r8, r12
0x180012c84  jmp     loc_18001292F
0x180012c89  mov     edi, 1
0x180012c8e  mov     [rsp+0A8h+var_50], rcx
0x180012c93  lea     rdx, [rsp+0A8h+var_58]
0x180012c98  mov     rcx, [rsi+40h]
0x180012c9c  add     rcx, 2138h
0x180012ca3  mov     [rsp+0A8h+var_58], 3
0x180012cac  mov     [rsp+0A8h+var_48], r15
0x180012cb1  call    ?TraceEvent@?$CTeHomeETWEvent@UEH_MPEG2_ERROR_EVENT@@@Mpeg2DemuxTrace@@QEAAXPEAUEH_MPEG2_ERROR_EVENT@@@Z; Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(EH_MPEG2_ERROR_EVENT *)
0x180012cb6  mov     r8, rdi
0x180012cb9  jmp     loc_18001292F
0x180012cbe  call    cs:__imp_GetLastError
0x180012cc5  nop     dword ptr [rax+rax+00h]
0x180012cca  test    eax, eax
0x180012ccc  jnz     loc_1800129F1
0x180012cd2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180012cd9  test    rcx, rcx
0x180012cdc  jz      loc_180012EE6
0x180012ce2  mov     rax, [rcx]
0x180012ce5  mov     rax, [rax]
0x180012ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ced  test    rax, rax
0x180012cf0  cmovnz  rsi, rax
0x180012cf4  jmp     loc_1800129F1
0x180012cf9  mov     rcx, [rsi+40h]
0x180012cfd  mov     [rsi+30h], r15
0x180012d01  mov     rax, [rcx]
0x180012d04  test    rax, rax
0x180012d07  jz      short loc_180012D10
0x180012d09  mov     [rax+0A8h], r15
0x180012d10  mov     [rcx+2528h], r15
0x180012d17  mov     r8d, 316h; int
0x180012d1d  lea     rcx, [rsp+0A8h+arg_8]; this
0x180012d25  mov     rdx, r14; char *
0x180012d28  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012d2d  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180012d34  jb      short loc_180012D58
0x180012d36  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d3d  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x180012d44  mov     edx, 11h
0x180012d49  mov     r9, rsi
0x180012d4c  mov     rcx, [rcx+88h]
0x180012d53  call    WPP_SF_q
0x180012d58  lea     rcx, [rsp+0A8h+arg_8]; this
0x180012d60  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180012d65  mov     rcx, [rsi+28h]
0x180012d69  jmp     loc_1800128DD
0x180012d6e  mov     [rax+0B0h], r15
0x180012d75  mov     rax, [rbx]
0x180012d78  inc     qword ptr [rax+0B8h]
0x180012d7f  jmp     loc_180012899
0x180012d84  cmp     qword ptr [rbx+2168h], 0
0x180012d8c  jz      loc_1800128B6
0x180012d92  mov     rax, [rax+10h]
0x180012d96  mov     rax, [rax+30h]
0x180012d9a  test    rax, rax
0x180012d9d  jz      loc_1800128B6
0x180012da3  movzx   r8d, byte ptr [rbx+2174h]
0x180012dab  mov     edx, [rbx+2170h]
0x180012db1  mov     ecx, [rcx+4]
0x180012db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012db9  test    eax, eax
0x180012dbb  jz      loc_1800128B6
0x180012dc1  mov     ecx, edi
0x180012dc3  mov     rax, r15
0x180012dc6  and     rax, rsi
  ... truncated ...
```
