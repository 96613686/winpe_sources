# WnsCPLog::WnsCPTSetModeForUser::StopActivity(void)

- ea: `0x18001b7f0`
- end: `0x18001c044`
- name: `?StopActivity@WnsCPTSetModeForUser@WnsCPLog@@MEAAXXZ`
- size: `2132`
- prototype: `void __fastcall(WnsCPLog::WnsCPTSetModeForUser *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000f270`
- `0x18001b7f0`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b861`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bdb7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b861`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001bdb7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b879`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b894`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b8ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bdcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bdea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be04`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b879`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b894`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b8ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bdcf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bdea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001be04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf44`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c013`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001c013`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001b9a5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001befb`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001b9a5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001befb`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001b98a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001bee0`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001b98a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001bee0`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b8de`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001be34`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b8de`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001be34`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b9d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001bf2a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b9d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001bf2a`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCPTSetModeForUser::StopActivity(WnsCPLog::WnsCPTSetModeForUser *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  _QWORD *v7; // rbx
  ULONGLONG *v8; // r9
  _QWORD *Ptr; // r13
  __int64 v10; // rcx
  const unsigned __int16 *v11; // rdx
  int *v12; // r8
  const unsigned __int16 *v13; // r9
  int *v14; // r10
  const unsigned __int16 *v15; // r11
  const unsigned __int16 *v16; // rbx
  int *v17; // rsi
  const unsigned __int16 *v18; // r15
  const unsigned __int16 *v19; // r12
  int v20; // eax
  __int64 v21; // rdi
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  bool v25; // zf
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  int v38; // eax
  int v39; // ecx
  RTL_SRWLOCK *v40; // rbx
  _QWORD *v41; // rbx
  ULONGLONG *v42; // r9
  _QWORD *v43; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v45; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v48; // [rsp+40h] [rbp-C0h] BYREF
  PSRWLOCK v49; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK v50; // [rsp+50h] [rbp-B0h] BYREF
  int v51; // [rsp+58h] [rbp-A8h] BYREF
  int v52; // [rsp+5Ch] [rbp-A4h] BYREF
  int v53; // [rsp+60h] [rbp-A0h] BYREF
  int v54; // [rsp+64h] [rbp-9Ch] BYREF
  int v55; // [rsp+68h] [rbp-98h] BYREF
  PSRWLOCK v56; // [rsp+70h] [rbp-90h] BYREF
  GUID ProviderId; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v58; // [rsp+90h] [rbp-70h] BYREF
  void *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  PSRWLOCK *v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  PSRWLOCK *p_SRWLock; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  char *v69; // [rsp+F0h] [rbp-10h]
  int v70; // [rsp+F8h] [rbp-8h]
  int v71; // [rsp+FCh] [rbp-4h]
  PSRWLOCK *v72; // [rsp+100h] [rbp+0h]
  __int64 v73; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v74; // [rsp+110h] [rbp+10h]
  __int64 v75; // [rsp+118h] [rbp+18h]
  PSRWLOCK *v76; // [rsp+120h] [rbp+20h]
  __int64 v77; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v78; // [rsp+130h] [rbp+30h]
  int v79; // [rsp+138h] [rbp+38h]
  int v80; // [rsp+13Ch] [rbp+3Ch]
  unsigned int *v81; // [rsp+140h] [rbp+40h]
  __int64 v82; // [rsp+148h] [rbp+48h]
  const unsigned __int16 *v83; // [rsp+150h] [rbp+50h]
  int v84; // [rsp+158h] [rbp+58h]
  int v85; // [rsp+15Ch] [rbp+5Ch]
  int *v86; // [rsp+160h] [rbp+60h]
  __int64 v87; // [rsp+168h] [rbp+68h]
  int *v88; // [rsp+170h] [rbp+70h]
  int v89; // [rsp+178h] [rbp+78h]
  int v90; // [rsp+17Ch] [rbp+7Ch]
  int *v91; // [rsp+180h] [rbp+80h]
  __int64 v92; // [rsp+188h] [rbp+88h]
  const unsigned __int16 *v93; // [rsp+190h] [rbp+90h]
  int v94; // [rsp+198h] [rbp+98h]
  int v95; // [rsp+19Ch] [rbp+9Ch]
  int *v96; // [rsp+1A0h] [rbp+A0h]
  __int64 v97; // [rsp+1A8h] [rbp+A8h]
  const unsigned __int16 *v98; // [rsp+1B0h] [rbp+B0h]
  int v99; // [rsp+1B8h] [rbp+B8h]
  int v100; // [rsp+1BCh] [rbp+BCh]
  int *v101; // [rsp+1C0h] [rbp+C0h]
  int v102; // [rsp+1C8h] [rbp+C8h]
  int v103; // [rsp+1CCh] [rbp+CCh]
  int *v104; // [rsp+1D0h] [rbp+D0h]
  __int64 v105; // [rsp+1D8h] [rbp+D8h]
  const unsigned __int16 *v106; // [rsp+1E0h] [rbp+E0h]
  int v107; // [rsp+1E8h] [rbp+E8h]
  int v108; // [rsp+1ECh] [rbp+ECh]
  int *v109; // [rsp+1F0h] [rbp+F0h]
  int v110; // [rsp+1F8h] [rbp+F8h]
  int v111; // [rsp+1FCh] [rbp+FCh]
  int *v112; // [rsp+200h] [rbp+100h]
  __int64 v113; // [rsp+208h] [rbp+108h]
  WINBOOL *p_fPending; // [rsp+210h] [rbp+110h]
  __int64 v115; // [rsp+218h] [rbp+118h]
  const unsigned __int16 *v116; // [rsp+220h] [rbp+120h]
  int v117; // [rsp+228h] [rbp+128h]
  int v118; // [rsp+22Ch] [rbp+12Ch]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) )
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
    if ( v4 )
    {
      if ( v5 )
      {
        v6 = v5 + 33;
        AcquireSRWLockExclusive(v6);
        SRWLock = 0;
        **((_DWORD **)this + 34) = 2;
        if ( v6 )
          ReleaseSRWLockExclusive(v6);
      }
      else
      {
        v49 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      SRWLock = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
        && fPending )
      {
        qword_18004A768 = 0;
        SRWLock = (PSRWLOCK)&qword_18004A760;
        qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
        byte_18004A770 = 0;
        dword_18004A774 = 0;
        CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
        v7 = CallbackContext;
        qword_18004A768 = (__int64)CallbackContext;
        byte_18004A770 = 1;
        ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
        if ( *((_QWORD *)CallbackContext + 4) )
          __fastfail(5u);
        v8 = (ULONGLONG *)((char *)CallbackContext + 32);
        *((_QWORD *)CallbackContext + 5) = 0;
        v7[6] = 0;
        if ( !EventRegister(&ProviderId, tlgEnableCallback, v7, v8) )
          EventSetInformation(v7[4], 2, v7[1], *(unsigned __int16 *)v7[1]);
        dword_18004A774 = 1;
        (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
        InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
      }
      Ptr = SRWLock[1].Ptr;
      if ( *(_DWORD *)Ptr > 5u )
      {
        v10 = -1;
        v11 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
        v12 = (int *)*((_QWORD *)v4 + 15);
        v13 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v14 = (int *)*((_QWORD *)v4 + 12);
        v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v16 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v17 = (int *)*((_QWORD *)v4 + 3);
        v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        fPending = v4[17];
        v51 = v4[4];
        v52 = v4[26];
        v53 = v4[20];
        v54 = v4[8];
        v55 = *v4;
        v48 = v4[16];
        v20 = v4[2];
        v21 = *((_QWORD *)this + 34);
        LODWORD(v49) = v20;
        v56 = (PSRWLOCK)0x1000000;
        v50 = 0;
        if ( v11 )
        {
          v22 = -1;
          do
            ++v22;
          while ( *((_BYTE *)v11 + v22) );
          v23 = v22 + 1;
        }
        else
        {
          v11 = &byte_18003A073;
          v23 = 1;
        }
        v117 = v23;
        v116 = v11;
        p_fPending = &fPending;
        v112 = &v51;
        v118 = 0;
        v115 = 4;
        v113 = 4;
        if ( v12 )
        {
          v24 = -1;
          do
            v25 = *((_WORD *)v12 + ++v24) == 0;
          while ( !v25 );
          v26 = 2 * v24 + 2;
        }
        else
        {
          v12 = &dword_18003A074;
          v26 = 2;
        }
        v109 = v12;
        v110 = v26;
        v111 = 0;
        if ( v13 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *((_BYTE *)v13 + v27) );
          v28 = v27 + 1;
        }
        else
        {
          v13 = &byte_18003A073;
          v28 = 1;
        }
        v107 = v28;
        v104 = &v52;
        v106 = v13;
        v108 = 0;
        v105 = 4;
        if ( v14 )
        {
          v29 = -1;
          do
            v25 = *((_WORD *)v14 + ++v29) == 0;
          while ( !v25 );
          v30 = 2 * v29 + 2;
        }
        else
        {
          v14 = &dword_18003A074;
          v30 = 2;
        }
        v101 = v14;
        v102 = v30;
        v103 = 0;
        if ( v15 )
        {
          v31 = -1;
          do
            ++v31;
          while ( *((_BYTE *)v15 + v31) );
          v32 = v31 + 1;
        }
        else
        {
          v15 = &byte_18003A073;
          v32 = 1;
        }
        v99 = v32;
        v96 = &v53;
        v98 = v15;
        v100 = 0;
        v97 = 4;
        if ( v16 )
        {
          v33 = -1;
          do
            ++v33;
          while ( *((_BYTE *)v16 + v33) );
          v34 = v33 + 1;
        }
        else
        {
          v16 = &byte_18003A073;
          v34 = 1;
        }
        v94 = v34;
        v91 = &v54;
        v93 = v16;
        v95 = 0;
        v92 = 4;
        if ( v17 )
        {
          v35 = -1;
          do
            v25 = *((_WORD *)v17 + ++v35) == 0;
          while ( !v25 );
          v36 = 2 * v35 + 2;
        }
        else
        {
          v17 = &dword_18003A074;
          v36 = 2;
        }
        v89 = v36;
        v86 = &v55;
        v88 = v17;
        v90 = 0;
        v87 = 4;
        if ( v18 )
        {
          v37 = -1;
          do
            ++v37;
          while ( *((_BYTE *)v18 + v37) );
          v38 = v37 + 1;
        }
        else
        {
          v18 = &byte_18003A073;
          v38 = 1;
        }
        v84 = v38;
        v81 = &v48;
        v83 = v18;
        v85 = 0;
        v82 = 4;
        if ( v19 )
        {
          do
            ++v10;
          while ( *((_BYTE *)v19 + v10) );
          v39 = v10 + 1;
        }
        else
        {
          v19 = &byte_18003A073;
          v39 = 1;
        }
        v79 = v39;
        v76 = &v49;
        v80 = 0;
        v74 = &v56;
        v72 = &v50;
        *(_DWORD *)&ProviderId.Data2 = 517;
        UserData.Ptr = Ptr[1];
        *(_QWORD *)ProviderId.Data4 = 0;
        v78 = v19;
        v77 = 4;
        v75 = 8;
        v73 = 8;
        ProviderId.Data1 = 184549376;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v69 = byte_180040AED;
        UserData.Reserved = 2;
        v70 = 323;
        v71 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(Ptr[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v21 + 8), 0, 0x15u, &UserData);
      }
      goto LABEL_75;
    }
  }
  else
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v5 )
  {
    v40 = v5 + 33;
    AcquireSRWLockExclusive(v40);
    v50 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v40 )
      ReleaseSRWLockExclusive(v40);
  }
  else
  {
    v56 = 0;
    **((_DWORD **)this + 34) = 2;
  }
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    qword_18004A768 = 0;
    SRWLock = (PSRWLOCK)&qword_18004A760;
    qword_18004A760 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_18004A770 = 0;
    dword_18004A774 = 0;
    CallbackContext = &`WnsCPTracelogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_633a74d489e420a2ff0e92495a1626f6_::_lambda_invoker_cdecl_);
    v41 = CallbackContext;
    qword_18004A768 = (__int64)CallbackContext;
    byte_18004A770 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v42 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v41[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v41, v42) )
      EventSetInformation(v41[4], 2, v41[1], *(unsigned __int16 *)v41[1]);
    dword_18004A774 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004A760 + 8))(&qword_18004A760);
    InitOnceComplete(&`WnsCPTracelogger::Instance'::`2'::wrapper, 0, &qword_18004A760);
  }
  v43 = SRWLock[1].Ptr;
  if ( *(_DWORD *)v43 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v45 = *((_QWORD *)this + 34);
    LODWORD(SRWLock) = CurrentThreadId;
    v67 = 4;
    v65 = 4;
    LODWORD(v49) = *(_DWORD *)(v45 + 72);
    p_SRWLock = &SRWLock;
    v64 = &v49;
    v62 = &v50;
    *(_DWORD *)&ProviderId.Data2 = 517;
    v58.Ptr = v43[1];
    v50 = 0;
    v63 = 8;
    ProviderId.Data1 = 184549376;
    *(_QWORD *)ProviderId.Data4 = 0;
    v58.Size = *(unsigned __int16 *)v58.Ptr;
    v59 = &unk_180040A98;
    v58.Reserved = 2;
    v60 = 73;
    v61 = 1;
    v48 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(v43[4], (PCEVENT_DESCRIPTOR)&ProviderId, (LPCGUID)(v45 + 8), 0, 5u, &v58);
  }
LABEL_75:
  wil::ActivityBase<WnsCPTracelogger,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18001b7f0  push    rbp
0x18001b7f2  push    rbx
0x18001b7f3  push    rsi
0x18001b7f4  push    rdi
0x18001b7f5  push    r12
0x18001b7f7  push    r13
0x18001b7f9  push    r14
0x18001b7fb  push    r15
0x18001b7fd  lea     rbp, [rsp-148h]
0x18001b805  sub     rsp, 248h
0x18001b80c  mov     rax, cs:__security_cookie
0x18001b813  xor     rax, rsp
0x18001b816  mov     [rbp+180h+var_50], rax
0x18001b81d  mov     rdi, [rcx+110h]
0x18001b824  xor     r12d, r12d
0x18001b827  mov     r14, rcx
0x18001b82a  mov     eax, [rdi+48h]
0x18001b82d  test    eax, eax
0x18001b82f  jns     loc_18001BDA1
0x18001b835  add     rdi, 50h ; 'P'
0x18001b839  cmp     eax, [rdi+8]
0x18001b83c  jnz     loc_18001BDA1
0x18001b842  mov     rbx, [rcx+118h]
0x18001b849  test    rdi, rdi
0x18001b84c  jz      loc_18001BDA8
0x18001b852  test    rbx, rbx
0x18001b855  jz      short loc_18001B89C
0x18001b857  add     rbx, 108h
0x18001b85e  mov     rcx, rbx; SRWLock
0x18001b861  call    cs:__imp_AcquireSRWLockExclusive
0x18001b867  lea     rax, [rsp+280h+SRWLock]
0x18001b86c  mov     [rax], r12
0x18001b86f  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x18001b874  test    rcx, rcx
0x18001b877  jz      short loc_18001B87F
0x18001b879  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b87f  mov     rax, [r14+110h]
0x18001b886  mov     dword ptr [rax], 2
0x18001b88c  test    rbx, rbx
0x18001b88f  jz      short loc_18001B8C1
0x18001b891  mov     rcx, rbx; SRWLock
0x18001b894  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b89a  jmp     short loc_18001B8C1
0x18001b89c  lea     rax, [rsp+280h+var_238]
0x18001b8a1  mov     [rax], r12
0x18001b8a4  mov     rcx, [rsp+280h+var_238]; SRWLock
0x18001b8a9  test    rcx, rcx
0x18001b8ac  jz      short loc_18001B8B4
0x18001b8ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b8b4  mov     rax, [r14+110h]
0x18001b8bb  mov     dword ptr [rax], 2
0x18001b8c1  lea     r9, [rsp+280h+SRWLock]; lpContext
0x18001b8c6  mov     [rsp+280h+SRWLock], r12
0x18001b8cb  lea     r8, [rsp+280h+fPending]; fPending
0x18001b8d0  mov     [rsp+280h+fPending], r12d
0x18001b8d5  xor     edx, edx; dwFlags
0x18001b8d7  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18001b8de  call    cs:__imp_InitOnceBeginInitialize
0x18001b8e4  test    eax, eax
0x18001b8e6  jz      loc_18001B9DA
0x18001b8ec  cmp     [rsp+280h+fPending], r12d
0x18001b8f1  jz      loc_18001B9DA
0x18001b8f7  lea     rsi, qword_18004A760
0x18001b8fe  mov     cs:qword_18004A768, r12
0x18001b905  lea     rax, ??_7FeatureLogging@details@wil@@6B@
0x18001b90c  mov     [rsp+280h+SRWLock], rsi
0x18001b911  mov     cs:qword_18004A760, rax
0x18001b918  mov     cs:byte_18004A770, r12b
0x18001b91f  mov     cs:dword_18004A774, r12d
0x18001b926  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A
0x18001b92d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18001b934  mov     cs:CallbackContext, rax
0x18001b93b  call    atexit
0x18001b940  mov     rbx, cs:CallbackContext
0x18001b947  mov     cs:qword_18004A768, rbx
0x18001b94e  mov     cs:byte_18004A770, 1
0x18001b955  mov     rax, [rbx+8]
0x18001b959  movups  xmm0, xmmword ptr [rax-10h]
0x18001b95d  movups  xmmword ptr [rsp+280h+ProviderId.Data1], xmm0
0x18001b962  cmp     [rbx+20h], r12
0x18001b966  jz      short loc_18001B96F
0x18001b968  mov     ecx, 5
0x18001b96d  int     29h; Win8: RtlFailFast(ecx)
0x18001b96f  lea     r9, [rbx+20h]; RegHandle
0x18001b973  mov     [rbx+28h], r12
0x18001b977  mov     r8, rbx; CallbackContext
0x18001b97a  mov     [rbx+30h], r12
0x18001b97e  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001b985  lea     rcx, [rsp+280h+ProviderId]; ProviderId
0x18001b98a  call    cs:__imp_EventRegister
0x18001b990  test    eax, eax
0x18001b992  jnz     short loc_18001B9AB
0x18001b994  mov     r8, [rbx+8]
0x18001b998  mov     edx, 2
0x18001b99d  mov     rcx, [rbx+20h]
0x18001b9a1  movzx   r9d, word ptr [r8]
0x18001b9a5  call    cs:__imp_EventSetInformation
0x18001b9ab  mov     rax, cs:qword_18004A760
0x18001b9b2  mov     rcx, rsi
0x18001b9b5  mov     cs:dword_18004A774, 1
0x18001b9bf  mov     rax, [rax+8]
0x18001b9c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9c8  mov     r8, rsi; lpContext
0x18001b9cb  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18001b9d2  xor     edx, edx; dwFlags
0x18001b9d4  call    cs:__imp_InitOnceComplete
0x18001b9da  mov     rax, [rsp+280h+SRWLock]
0x18001b9df  mov     r13, [rax+8]
0x18001b9e3  mov     eax, [r13+0]
0x18001b9e7  cmp     eax, 5
0x18001b9ea  jbe     loc_18001C019
0x18001b9f0  mov     eax, [rdi+44h]
0x18001b9f3  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b9fa  mov     rdx, [rdi+30h]
0x18001b9fe  mov     r8, [rdi+78h]
0x18001ba02  mov     r9, [rdi+70h]
0x18001ba06  mov     r10, [rdi+60h]
0x18001ba0a  mov     r11, [rdi+58h]
0x18001ba0e  mov     rbx, [rdi+48h]
0x18001ba12  mov     rsi, [rdi+18h]
0x18001ba16  mov     r15, [rdi+80h]
0x18001ba1d  mov     r12, [rdi+38h]
0x18001ba21  mov     [rsp+280h+fPending], eax
0x18001ba25  mov     eax, [rdi+10h]
0x18001ba28  mov     [rsp+280h+var_228], eax
0x18001ba2c  mov     eax, [rdi+68h]
0x18001ba2f  mov     [rsp+280h+var_224], eax
0x18001ba33  mov     eax, [rdi+50h]
0x18001ba36  mov     [rsp+280h+var_220], eax
0x18001ba3a  mov     eax, [rdi+20h]
0x18001ba3d  mov     [rsp+280h+var_21C], eax
0x18001ba41  mov     eax, [rdi]
0x18001ba43  mov     [rsp+280h+var_218], eax
0x18001ba47  mov     eax, [rdi+40h]
0x18001ba4a  mov     [rsp+280h+var_240], eax
0x18001ba4e  mov     eax, [rdi+8]
0x18001ba51  mov     rdi, [r14+110h]
0x18001ba58  mov     dword ptr [rsp+280h+var_238], eax
0x18001ba5c  mov     [rsp+280h+var_210], 1000000h
0x18001ba65  mov     [rsp+280h+var_230], 0
0x18001ba6e  test    rdx, rdx
0x18001ba71  jz      short loc_18001BA83
0x18001ba73  mov     rax, rcx
0x18001ba76  inc     rax
0x18001ba79  cmp     byte ptr [rdx+rax], 0
0x18001ba7d  jnz     short loc_18001BA76
0x18001ba7f  inc     eax
0x18001ba81  jmp     short loc_18001BA8F
0x18001ba83  lea     rdx, byte_18003A073
0x18001ba8a  mov     eax, 1
0x18001ba8f  mov     [rbp+180h+var_58], eax
0x18001ba95  lea     rax, [rsp+280h+fPending]
0x18001ba9a  mov     [rbp+180h+var_60], rdx
0x18001baa1  xor     edx, edx
0x18001baa3  mov     [rbp+180h+var_70], rax
0x18001baaa  lea     rax, [rsp+280h+var_228]
0x18001baaf  mov     [rbp+180h+var_80], rax
0x18001bab6  mov     [rbp+180h+var_54], edx
0x18001babc  mov     [rbp+180h+var_68], 4
0x18001bac7  mov     [rbp+180h+var_78], 4
0x18001bad2  test    r8, r8
0x18001bad5  jz      short loc_18001BAF5
0x18001bad7  mov     rax, rcx
0x18001bada  nop     word ptr [rax+rax+00h]
0x18001bae0  cmp     [r8+rax*2+2], dx
0x18001bae6  lea     rax, [rax+1]
0x18001baea  jnz     short loc_18001BAE0
0x18001baec  lea     eax, ds:2[rax*2]
0x18001baf3  jmp     short loc_18001BB01
0x18001baf5  lea     r8, dword_18003A074
0x18001bafc  mov     eax, 2
0x18001bb01  mov     [rbp+180h+var_90], r8
0x18001bb08  mov     [rbp+180h+var_88], eax
0x18001bb0e  mov     [rbp+180h+var_84], edx
0x18001bb14  test    r9, r9
0x18001bb17  jz      short loc_18001BB2D
0x18001bb19  mov     rax, rcx
0x18001bb1c  nop     dword ptr [rax+00h]
0x18001bb20  inc     rax
0x18001bb23  cmp     [r9+rax], dl
0x18001bb27  jnz     short loc_18001BB20
0x18001bb29  inc     eax
0x18001bb2b  jmp     short loc_18001BB39
0x18001bb2d  lea     r9, byte_18003A073
0x18001bb34  mov     eax, 1
0x18001bb39  mov     [rbp+180h+var_98], eax
0x18001bb3f  lea     rax, [rsp+280h+var_224]
0x18001bb44  mov     [rbp+180h+var_B0], rax
0x18001bb4b  mov     [rbp+180h+var_A0], r9
0x18001bb52  mov     [rbp+180h+var_94], edx
0x18001bb58  mov     [rbp+180h+var_A8], 4
0x18001bb63  test    r10, r10
0x18001bb66  jz      short loc_18001BB85
0x18001bb68  mov     rax, rcx
0x18001bb6b  nop     dword ptr [rax+rax+00h]
0x18001bb70  cmp     [r10+rax*2+2], dx
0x18001bb76  lea     rax, [rax+1]
0x18001bb7a  jnz     short loc_18001BB70
0x18001bb7c  lea     eax, ds:2[rax*2]
0x18001bb83  jmp     short loc_18001BB91
0x18001bb85  lea     r10, dword_18003A074
0x18001bb8c  mov     eax, 2
0x18001bb91  mov     [rbp+180h+var_C0], r10
0x18001bb98  mov     [rbp+180h+var_B8], eax
0x18001bb9e  mov     [rbp+180h+var_B4], edx
0x18001bba4  test    r11, r11
0x18001bba7  jz      short loc_18001BBBD
0x18001bba9  mov     rax, rcx
0x18001bbac  nop     dword ptr [rax+00h]
0x18001bbb0  inc     rax
0x18001bbb3  cmp     [r11+rax], dl
0x18001bbb7  jnz     short loc_18001BBB0
0x18001bbb9  inc     eax
0x18001bbbb  jmp     short loc_18001BBC9
0x18001bbbd  lea     r11, byte_18003A073
0x18001bbc4  mov     eax, 1
0x18001bbc9  mov     [rbp+180h+var_C8], eax
0x18001bbcf  lea     rax, [rsp+280h+var_220]
0x18001bbd4  mov     [rbp+180h+var_E0], rax
0x18001bbdb  mov     [rbp+180h+var_D0], r11
0x18001bbe2  mov     [rbp+180h+var_C4], edx
0x18001bbe8  mov     [rbp+180h+var_D8], 4
0x18001bbf3  test    rbx, rbx
0x18001bbf6  jz      short loc_18001BC0C
0x18001bbf8  mov     rax, rcx
0x18001bbfb  nop     dword ptr [rax+rax+00h]
0x18001bc00  inc     rax
0x18001bc03  cmp     [rbx+rax], dl
0x18001bc06  jnz     short loc_18001BC00
0x18001bc08  inc     eax
0x18001bc0a  jmp     short loc_18001BC18
0x18001bc0c  lea     rbx, byte_18003A073
0x18001bc13  mov     eax, 1
0x18001bc18  mov     [rbp+180h+var_E8], eax
0x18001bc1e  lea     rax, [rsp+280h+var_21C]
0x18001bc23  mov     [rbp+180h+var_100], rax
0x18001bc2a  mov     [rbp+180h+var_F0], rbx
0x18001bc31  mov     [rbp+180h+var_E4], edx
0x18001bc37  mov     [rbp+180h+var_F8], 4
0x18001bc42  test    rsi, rsi
0x18001bc45  jz      short loc_18001BC64
0x18001bc47  mov     rax, rcx
0x18001bc4a  nop     word ptr [rax+rax+00h]
0x18001bc50  cmp     [rsi+rax*2+2], dx
0x18001bc55  lea     rax, [rax+1]
0x18001bc59  jnz     short loc_18001BC50
0x18001bc5b  lea     eax, ds:2[rax*2]
0x18001bc62  jmp     short loc_18001BC70
0x18001bc64  lea     rsi, dword_18003A074
0x18001bc6b  mov     eax, 2
0x18001bc70  mov     [rbp+180h+var_108], eax
0x18001bc73  lea     rax, [rsp+280h+var_218]
0x18001bc78  mov     [rbp+180h+var_120], rax
0x18001bc7c  mov     [rbp+180h+var_110], rsi
0x18001bc80  mov     [rbp+180h+var_104], edx
0x18001bc83  mov     [rbp+180h+var_118], 4
0x18001bc8b  test    r15, r15
0x18001bc8e  jz      short loc_18001BCA0
0x18001bc90  mov     rax, rcx
0x18001bc93  inc     rax
0x18001bc96  cmp     [r15+rax], dl
0x18001bc9a  jnz     short loc_18001BC93
0x18001bc9c  inc     eax
0x18001bc9e  jmp     short loc_18001BCAC
0x18001bca0  lea     r15, byte_18003A073
0x18001bca7  mov     eax, 1
0x18001bcac  mov     [rbp+180h+var_128], eax
0x18001bcaf  lea     rax, [rsp+280h+var_240]
0x18001bcb4  mov     [rbp+180h+var_140], rax
0x18001bcb8  mov     [rbp+180h+var_130], r15
0x18001bcbc  mov     [rbp+180h+var_124], edx
0x18001bcbf  mov     [rbp+180h+var_138], 4
0x18001bcc7  test    r12, r12
0x18001bcca  jz      short loc_18001BCDD
0x18001bccc  nop     dword ptr [rax+00h]
0x18001bcd0  inc     rcx
0x18001bcd3  cmp     [r12+rcx], dl
0x18001bcd7  jnz     short loc_18001BCD0
0x18001bcd9  inc     ecx
0x18001bcdb  jmp     short loc_18001BCE9
0x18001bcdd  lea     r12, byte_18003A073
0x18001bce4  mov     ecx, 1
0x18001bce9  mov     [rbp+180h+var_148], ecx
0x18001bcec  lea     rax, [rsp+280h+var_238]
0x18001bcf1  mov     [rbp+180h+var_160], rax
0x18001bcf5  lea     r8, [rdi+8]
0x18001bcf9  mov     [rbp+180h+var_144], edx
0x18001bcfc  lea     rax, [rsp+280h+var_210]
0x18001bd01  mov     [rbp+180h+var_170], rax
0x18001bd05  lea     rax, [rsp+280h+var_230]
0x18001bd0a  mov     [rbp+180h+var_180], rax
0x18001bd0e  movzx   eax, cs:word_180040AE3
0x18001bd15  mov     dword ptr [rsp+280h+ProviderId.Data2], eax
0x18001bd19  mov     rax, [r13+8]
0x18001bd1d  mov     [rbp+180h+var_1A0], rax
0x18001bd21  mov     qword ptr [rbp+180h+ProviderId.Data4], rdx
0x18001bd25  lea     rdx, _TraceLoggingMetadata
0x18001bd2c  mov     [rbp+180h+var_150], r12
0x18001bd30  mov     [rbp+180h+var_158], 4
0x18001bd38  mov     [rbp+180h+var_168], 8
  ... truncated ...
```
