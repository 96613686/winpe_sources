# CMPEG2DemuxInputPin::Receive(IMediaSample *)

- ea: `0x180015350`
- end: `0x1800158e4`
- name: `?Receive@CMPEG2DemuxInputPin@@UEAAJPEAUIMediaSample@@@Z`
- size: `1428`
- prototype: `__int64 __fastcall(CMPEG2DemuxInputPin *__hidden this, struct IMediaSample *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800b6150`

## callees

- `0x180015350`
- `0x1800158f0`
- `0x180015b30`
- `0x18002d514`
- `0x18004c0d0`
- `0x180051ce4`
- `0x18007c8e8`
- `0x1800a3738`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001547f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001547f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015413`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015413`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800153be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800155a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001557d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001565f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001557d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001565f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800155f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800155f7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800153a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001558e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800153a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001558e`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180015367`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180015434`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001548b`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180015367`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x180015434`
- `api-ms-win-mm-time-l1-1-0!timeGetTime` at `0x18001548b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800156e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015895`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800156e2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180015895`

## pseudocode

```c
__int64 __fastcall CMPEG2DemuxInputPin::Receive(CMPEG2DemuxInputPin *this, struct IMediaSample *a2)
{
  DWORD Time; // eax
  CallStackTracing *v5; // rdi
  DWORD v6; // r12d
  char *v7; // rbx
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  DWORD v13; // r15d
  int v14; // eax
  unsigned int v15; // ebp
  DWORD v16; // eax
  struct IMediaSampleVtbl *lpVtbl; // rcx
  __int64 v18; // rbx
  HRESULT (__stdcall *IsSyncPoint)(IMediaSample *); // rax
  BOOL v20; // esi
  BOOL v21; // r13d
  __int64 v22; // rdi
  _QWORD *v23; // rax
  _DWORD *v24; // rcx
  CallStackTracing *v25; // rbx
  GUID *v26; // rdi
  DWORD v27; // esi
  GUID *v28; // rax
  int v29; // eax
  int v30; // eax
  __int64 v32; // rdx
  CallStackTracing *v33; // rcx
  __int64 v34; // rax
  CallStackTracing *v35; // rcx
  __int64 v36; // rax
  CallStackTracing *v37; // rax
  unsigned int (__fastcall *v38)(_QWORD, _QWORD, _QWORD); // rax
  __int64 v39; // rdx
  CallStackTracing *v40; // rax
  int v41; // [rsp+90h] [rbp+8h]
  DWORD v42; // [rsp+98h] [rbp+10h]
  __int64 v43; // [rsp+A0h] [rbp+18h] BYREF
  __int64 v44; // [rsp+A8h] [rbp+20h] BYREF

  Time = timeGetTime();
  v5 = CallStackTracing::s_wpInstance;
  v6 = Time;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v5 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v5 + 8) )
  {
    v7 = (char *)v5 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v5 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v33 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
        {
          v33 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v33 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v34 = (**(__int64 (__fastcall ***)(CallStackTracing *))v33)(v33);
      if ( v34 )
        v7 = (char *)v34;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CMPEG2DemuxInputPin::Receive";
      *(_DWORD *)&v7[8 * v11 + 8] = 411;
    }
    ++*((_DWORD *)v7 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      25,
      WPP_96579accb7133bda536f4064251166a9_Traceguids,
      (char *)this - 216,
      a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this - 17) + 304LL));
  v12 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = v12 + 1;
  if ( !v12 )
  {
    ((void (__fastcall *)(struct IMediaSample *, __int64))a2->lpVtbl->SetDiscontinuity)(a2, 1);
    if ( (unsigned __int8)byte_1800EACCB >= 2u )
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        26,
        WPP_96579accb7133bda536f4064251166a9_Traceguids,
        (char *)this - 216);
  }
  v13 = timeGetTime();
  v14 = CBaseInputPin::Receive(this, a2);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( !byte_1800EACCB )
      goto LABEL_14;
    v32 = 28;
  }
  else
  {
    v14 = CMPEG2Demultiplexer::ProcessMediaSampleLocked(*((CMPEG2Demultiplexer **)this - 17), (struct IUnknown *)a2);
    v15 = v14;
    if ( v14 >= 0 || !byte_1800EACCB )
      goto LABEL_14;
    v32 = 27;
  }
  WPP_SF_qD(
    *((_QWORD *)WPP_GLOBAL_Control + 17),
    v32,
    WPP_96579accb7133bda536f4064251166a9_Traceguids,
    (char *)this - 216,
    v14);
LABEL_14:
  LeaveCriticalSection((LPCRITICAL_SECTION)(*((_QWORD *)this - 17) + 304LL));
  v16 = timeGetTime();
  lpVtbl = a2->lpVtbl;
  v18 = *((_QWORD *)this + 13);
  v42 = v16;
  v43 = 0;
  IsSyncPoint = lpVtbl->IsSyncPoint;
  v44 = 0;
  v20 = ((__int64 (__fastcall *)(struct IMediaSample *))IsSyncPoint)(a2) == 0;
  v21 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->IsDiscontinuity)(a2) == 0;
  v41 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->GetActualDataLength)(a2);
  if ( ((int (__fastcall *)(struct IMediaSample *, __int64 *, __int64 *))a2->lpVtbl->GetTime)(a2, &v43, &v44) < 0 )
    LODWORD(v22) = -1;
  else
    v22 = v43 / 10000;
  v23 = *(_QWORD **)(v18 + 9016);
  v24 = (_DWORD *)*v23;
  if ( *(_DWORD *)*v23 )
  {
    if ( *(_QWORD *)(v18 + 8992) )
    {
      v38 = *(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD))(v23[2] + 48LL);
      if ( v38 )
      {
        if ( v38((unsigned int)v24[1], *(unsigned int *)(v18 + 9000), *(unsigned __int8 *)(v18 + 9004)) )
        {
          v39 = *(_QWORD *)(v18 + 8992);
          *(_DWORD *)v39 = 0;
          *(_DWORD *)(v39 + 4) = v22;
          *(_DWORD *)(v39 + 8) = v20;
          *(_DWORD *)(v39 + 12) = v21;
          *(_DWORD *)(v39 + 16) = -1;
          *(_DWORD *)(v39 + 20) = v41;
          *(_QWORD *)(v39 + 24) = (v42 - v13) | ((unsigned __int64)(v42 - v6) << 32);
          Mpeg2DemuxTrace::CeHomeETWDLL::ehTraceEvent(
            *(Mpeg2DemuxTrace::CeHomeETWDLL **)(*(_QWORD *)(v18 + 9016) + 16LL),
            *(_DWORD *)(**(_QWORD **)(v18 + 9016) + 4LL),
            *(_DWORD *)(v18 + 9008),
            *(void **)(v18 + 8992),
            *(_DWORD *)(v18 + 9000),
            *(_BYTE *)(v18 + 9004),
            *(_BYTE *)(v18 + 9005));
        }
      }
    }
  }
  if ( *(_QWORD *)v18 )
    ++*(_QWORD *)(*(_QWORD *)v18 + 88LL);
  v25 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v26 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v27 = GetLastError();
    v28 = (GUID *)TlsGetValue(*((_DWORD *)v25 + 3));
    if ( v28 )
    {
      v26 = v28;
    }
    else if ( !GetLastError() )
    {
      v35 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v35 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v35 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v36 = (**(__int64 (__fastcall ***)(CallStackTracing *))v35)(v35);
      if ( v36 )
        v26 = (GUID *)v36;
    }
    SetLastError(v27);
    v29 = *(_DWORD *)&v26[124].Data2;
    if ( v29 )
    {
      v30 = v29 - 1;
      *(_DWORD *)&v26[124].Data2 = v30;
      if ( !v30 )
      {
        *(_DWORD *)&v26[124].Data2 = 0;
        *(_QWORD *)&v26[126].Data1 = 0;
        *(_DWORD *)&v26[124].Data4[4] = 0;
        v26[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v26[126].Data4 = 0;
        v26[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180015350  push    rbx
0x180015352  push    rbp
0x180015353  push    rsi
0x180015354  push    rdi
0x180015355  push    r12
0x180015357  push    r13
0x180015359  push    r14
0x18001535b  push    r15
0x18001535d  sub     rsp, 48h
0x180015361  mov     r14, rdx
0x180015364  mov     rsi, rcx
0x180015367  call    cs:__imp_timeGetTime
0x18001536e  nop     dword ptr [rax+rax+00h]
0x180015373  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001537a  mov     r12d, eax
0x18001537d  test    rdi, rdi
0x180015380  jz      loc_1800156D1
0x180015386  cmp     byte ptr [rdi+8], 0
0x18001538a  jz      short loc_1800153F4
0x18001538c  lea     rbx, [rdi+0D0h]
0x180015393  call    cs:__imp_GetLastError
0x18001539a  nop     dword ptr [rax+rax+00h]
0x18001539f  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x1800153a2  mov     ebp, eax
0x1800153a4  call    cs:__imp_TlsGetValue
0x1800153ab  nop     dword ptr [rax+rax+00h]
0x1800153b0  test    rax, rax
0x1800153b3  jz      loc_18001565F
0x1800153b9  mov     rbx, rax
0x1800153bc  mov     ecx, ebp; dwErrCode
0x1800153be  call    cs:__imp_SetLastError
0x1800153c5  nop     dword ptr [rax+rax+00h]
0x1800153ca  mov     eax, [rbx+7C4h]
0x1800153d0  cmp     eax, [rbx+7C8h]
0x1800153d6  jnb     short loc_1800153EE
0x1800153d8  add     rax, rax
0x1800153db  lea     rcx, aCmpeg2demuxinp_8; "CMPEG2DemuxInputPin::Receive"
0x1800153e2  mov     [rbx+rax*8], rcx
0x1800153e6  mov     dword ptr [rbx+rax*8+8], 19Bh
0x1800153ee  inc     dword ptr [rbx+7C4h]
0x1800153f4  cmp     cs:byte_1800EACCB, 20h ; ' '
0x1800153fb  lea     rbx, [rsi-0D8h]
0x180015402  jnb     loc_180015731
0x180015408  mov     rcx, [rbx+50h]
0x18001540c  add     rcx, 130h; lpCriticalSection
0x180015413  call    cs:__imp_EnterCriticalSection
0x18001541a  nop     dword ptr [rax+rax+00h]
0x18001541f  mov     rcx, [rsi+78h]
0x180015423  lea     rax, [rcx+1]
0x180015427  mov     [rsi+78h], rax
0x18001542b  test    rcx, rcx
0x18001542e  jz      loc_18001575D
0x180015434  call    cs:__imp_timeGetTime
0x18001543b  nop     dword ptr [rax+rax+00h]
0x180015440  mov     rdx, r14; struct IMediaSample *
0x180015443  mov     rcx, rsi; this
0x180015446  mov     r15d, eax
0x180015449  call    ?Receive@CBaseInputPin@@UEAAJPEAUIMediaSample@@@Z; CBaseInputPin::Receive(IMediaSample *)
0x18001544e  mov     ebp, eax
0x180015450  test    eax, eax
0x180015452  js      loc_180015627
0x180015458  mov     rcx, [rsi-88h]; this
0x18001545f  mov     rdx, r14; struct IMediaSample *
0x180015462  call    ?ProcessMediaSampleLocked@CMPEG2Demultiplexer@@QEAAJPEAUIMediaSample@@@Z; CMPEG2Demultiplexer::ProcessMediaSampleLocked(IMediaSample *)
0x180015467  mov     ebp, eax
0x180015469  test    eax, eax
0x18001546b  js      loc_1800157A8
0x180015471  mov     rcx, [rsi-88h]
0x180015478  add     rcx, 130h; lpCriticalSection
0x18001547f  call    cs:__imp_LeaveCriticalSection
0x180015486  nop     dword ptr [rax+rax+00h]
0x18001548b  call    cs:__imp_timeGetTime
0x180015492  nop     dword ptr [rax+rax+00h]
0x180015497  mov     rcx, [r14]
0x18001549a  xor     edi, edi
0x18001549c  mov     rbx, [rsi+68h]
0x1800154a0  mov     [rsp+88h+arg_8], eax
0x1800154a7  mov     [rsp+88h+arg_10], rdi
0x1800154af  mov     rax, [rcx+38h]
0x1800154b3  mov     rcx, r14
0x1800154b6  mov     [rsp+88h+arg_18], rdi
0x1800154be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154c3  test    eax, eax
0x1800154c5  mov     esi, edi
0x1800154c7  mov     rax, [r14]
0x1800154ca  mov     rcx, r14
0x1800154cd  setz    sil
0x1800154d1  mov     rax, [rax+78h]
0x1800154d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154da  test    eax, eax
0x1800154dc  mov     r13d, edi
0x1800154df  mov     rax, [r14]
0x1800154e2  mov     rcx, r14
0x1800154e5  setz    r13b
0x1800154e9  mov     rax, [rax+58h]
0x1800154ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154f2  mov     rcx, [r14]
0x1800154f5  lea     r8, [rsp+88h+arg_18]
0x1800154fd  mov     [rsp+88h+arg_0], eax
0x180015504  lea     rdx, [rsp+88h+arg_10]
0x18001550c  mov     rax, [rcx+28h]
0x180015510  mov     rcx, r14
0x180015513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015518  test    eax, eax
0x18001551a  js      loc_18001561D
0x180015520  mov     rax, 346DC5D63886594Bh
0x18001552a  imul    [rsp+88h+arg_10]
0x180015532  mov     rdi, rdx
0x180015535  sar     rdi, 0Bh
0x180015539  mov     rax, rdi
0x18001553c  shr     rax, 3Fh
0x180015540  add     rdi, rax
0x180015543  mov     rax, [rbx+2338h]
0x18001554a  mov     rcx, [rax]
0x18001554d  cmp     dword ptr [rcx], 0
0x180015550  jnz     loc_1800157BF
0x180015556  xor     r14d, r14d
0x180015559  mov     rax, [rbx]
0x18001555c  test    rax, rax
0x18001555f  jnz     loc_18001588C
0x180015565  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001556c  cmp     byte ptr [rbx+8], 0
0x180015570  jz      loc_180015609
0x180015576  lea     rdi, [rbx+0D0h]
0x18001557d  call    cs:__imp_GetLastError
0x180015584  nop     dword ptr [rax+rax+00h]
0x180015589  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001558c  mov     esi, eax
0x18001558e  call    cs:__imp_TlsGetValue
0x180015595  nop     dword ptr [rax+rax+00h]
0x18001559a  test    rax, rax
0x18001559d  jz      loc_180015696
0x1800155a3  mov     rdi, rax
0x1800155a6  mov     ecx, esi; dwErrCode
0x1800155a8  call    cs:__imp_SetLastError
0x1800155af  nop     dword ptr [rax+rax+00h]
0x1800155b4  mov     eax, [rdi+7C4h]
0x1800155ba  test    eax, eax
0x1800155bc  jz      short loc_180015609
0x1800155be  sub     eax, 1
0x1800155c1  mov     [rdi+7C4h], eax
0x1800155c7  jnz     short loc_180015609
0x1800155c9  mov     [rdi+7C4h], r14d
0x1800155d0  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800155d7  mov     qword ptr [rdi+7E0h], 0
0x1800155e2  mov     [rdi+7CCh], r14d
0x1800155e9  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800155f0  mov     [rdi+7E8h], r14d
0x1800155f7  call    cs:__imp_GetCurrentThreadId
0x1800155fe  nop     dword ptr [rax+rax+00h]
0x180015603  mov     [rdi+7C0h], eax
0x180015609  mov     eax, ebp
0x18001560b  add     rsp, 48h
0x18001560f  pop     r15
0x180015611  pop     r14
0x180015613  pop     r13
0x180015615  pop     r12
0x180015617  pop     rdi
0x180015618  pop     rsi
0x180015619  pop     rbp
0x18001561a  pop     rbx
0x18001561b  retn
0x18001561d  mov     edi, 0FFFFFFFFh
0x180015622  jmp     loc_180015543
0x180015627  cmp     cs:byte_1800EACCB, 1
0x18001562e  jb      loc_180015471
0x180015634  mov     edx, 1Ch
0x180015639  mov     rcx, cs:WPP_GLOBAL_Control
0x180015640  lea     r8, WPP_96579accb7133bda536f4064251166a9_Traceguids
0x180015647  mov     r9, rbx
0x18001564a  mov     [rsp+88h+var_68], eax
0x18001564e  mov     rcx, [rcx+88h]
0x180015655  call    WPP_SF_qD
0x18001565a  jmp     loc_180015471
0x18001565f  call    cs:__imp_GetLastError
0x180015666  nop     dword ptr [rax+rax+00h]
0x18001566b  test    eax, eax
0x18001566d  jnz     loc_1800153BC
0x180015673  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001567a  test    rcx, rcx
0x18001567d  jz      short loc_1800156E2
0x18001567f  mov     rax, [rcx]
0x180015682  mov     rax, [rax]
0x180015685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001568a  test    rax, rax
0x18001568d  cmovnz  rbx, rax
0x180015691  jmp     loc_1800153BC
0x180015696  call    cs:__imp_GetLastError
0x18001569d  nop     dword ptr [rax+rax+00h]
0x1800156a2  test    eax, eax
0x1800156a4  jnz     loc_1800155A6
0x1800156aa  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800156b1  test    rcx, rcx
0x1800156b4  jz      loc_180015895
0x1800156ba  mov     rax, [rcx]
0x1800156bd  mov     rax, [rax]
0x1800156c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156c5  test    rax, rax
0x1800156c8  cmovnz  rdi, rax
0x1800156cc  jmp     loc_1800155A6
0x1800156d1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800156d6  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800156dd  jmp     loc_180015386
0x1800156e2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800156e9  nop     dword ptr [rax+rax+00h]
0x1800156ee  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800156f5  mov     rcx, rax
0x1800156f8  test    rax, rax
0x1800156fb  jz      short loc_18001571E
0x1800156fd  mov     rax, [rax]
0x180015700  mov     edx, 7F0h
0x180015705  mov     rax, [rax+8]
0x180015709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001570e  test    eax, eax
0x180015710  jz      short loc_18001571E
0x180015712  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180015719  jmp     loc_18001567F
0x18001571e  lea     rcx, qword_1800EB130
0x180015725  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001572c  jmp     loc_18001567F
0x180015731  mov     rcx, cs:WPP_GLOBAL_Control
0x180015738  lea     r8, WPP_96579accb7133bda536f4064251166a9_Traceguids
0x18001573f  mov     edx, 19h
0x180015744  mov     qword ptr [rsp+88h+var_68], r14
0x180015749  mov     r9, rbx
0x18001574c  mov     rcx, [rcx+88h]
0x180015753  call    WPP_SF_qq
0x180015758  jmp     loc_180015408
0x18001575d  mov     rax, [r14]
0x180015760  mov     edx, 1
0x180015765  mov     rcx, r14
0x180015768  mov     rax, [rax+80h]
0x18001576f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015774  cmp     cs:byte_1800EACCB, 2
0x18001577b  jb      loc_180015434
0x180015781  mov     rcx, cs:WPP_GLOBAL_Control
0x180015788  lea     r8, WPP_96579accb7133bda536f4064251166a9_Traceguids
0x18001578f  mov     edx, 1Ah
0x180015794  mov     r9, rbx
0x180015797  mov     rcx, [rcx+88h]
0x18001579e  call    WPP_SF_q
0x1800157a3  jmp     loc_180015434
0x1800157a8  cmp     cs:byte_1800EACCB, 1
0x1800157af  jb      loc_180015471
0x1800157b5  mov     edx, 1Bh
0x1800157ba  jmp     loc_180015639
0x1800157bf  cmp     qword ptr [rbx+2320h], 0
0x1800157c7  jz      loc_180015556
0x1800157cd  mov     rax, [rax+10h]
0x1800157d1  mov     rax, [rax+30h]
0x1800157d5  test    rax, rax
0x1800157d8  jz      loc_180015556
0x1800157de  movzx   r8d, byte ptr [rbx+232Ch]
0x1800157e6  mov     edx, [rbx+2328h]
0x1800157ec  mov     ecx, [rcx+4]
0x1800157ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f4  xor     r14d, r14d
0x1800157f7  test    eax, eax
0x1800157f9  jz      loc_180015559
0x1800157ff  mov     rdx, [rbx+2320h]
0x180015806  mov     r8d, [rsp+88h+arg_8]
0x18001580e  mov     ecx, r8d
0x180015811  mov     eax, [rsp+88h+arg_0]
0x180015818  sub     ecx, r12d
0x18001581b  shl     rcx, 20h
0x18001581f  sub     r8d, r15d
0x180015822  mov     [rdx], r14d
0x180015825  mov     [rdx+4], edi
0x180015828  mov     [rdx+8], esi
0x18001582b  mov     [rdx+0Ch], r13d
0x18001582f  mov     dword ptr [rdx+10h], 0FFFFFFFFh
0x180015836  mov     [rdx+14h], eax
0x180015839  mov     eax, r8d
0x18001583c  or      rcx, rax
0x18001583f  mov     [rdx+18h], rcx
0x180015843  movzx   eax, byte ptr [rbx+232Dh]
0x18001584a  mov     rcx, [rbx+2338h]
0x180015851  mov     r9, [rbx+2320h]; void *
0x180015858  mov     r8d, [rbx+2330h]; unsigned int
0x18001585f  mov     [rsp+88h+var_58], al; char
0x180015863  mov     rdx, [rcx]
0x180015866  movzx   eax, byte ptr [rbx+232Ch]
0x18001586d  mov     rcx, [rcx+10h]; this
0x180015871  mov     [rsp+88h+var_60], al; char
0x180015875  mov     eax, [rbx+2328h]
0x18001587b  mov     edx, [rdx+4]; unsigned int
0x18001587e  mov     [rsp+88h+var_68], eax; unsigned int
0x180015882  call    ?ehTraceEvent@CeHomeETWDLL@Mpeg2DemuxTrace@@QEAAXKKPEAXKEE@Z; Mpeg2DemuxTrace::CeHomeETWDLL::ehTraceEvent(ulong,ulong,void *,ulong,uchar,uchar)
0x180015887  jmp     loc_180015559
0x18001588c  inc     qword ptr [rax+58h]
0x180015890  jmp     loc_180015565
0x180015895  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001589c  nop     dword ptr [rax+rax+00h]
0x1800158a1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800158a8  mov     rcx, rax
0x1800158ab  test    rax, rax
0x1800158ae  jz      short loc_1800158D1
0x1800158b0  mov     rax, [rax]
0x1800158b3  mov     edx, 7F0h
0x1800158b8  mov     rax, [rax+8]
  ... truncated ...
```
