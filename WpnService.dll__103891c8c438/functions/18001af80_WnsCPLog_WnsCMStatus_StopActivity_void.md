# WnsCPLog::WnsCMStatus::StopActivity(void)

- ea: `0x18001af80`
- end: `0x18001b7d4`
- name: `?StopActivity@WnsCMStatus@WnsCPLog@@MEAAXXZ`
- size: `2132`
- prototype: `void __fastcall(WnsCPLog::WnsCMStatus *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000f270`
- `0x18001af80`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001aff1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b547`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001aff1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001b547`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b009`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b024`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b03e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b55f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b57a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b594`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b009`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b024`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b03e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b55f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b57a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b594`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b6d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b6d4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b7a3`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001b7a3`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001b135`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001b68b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001b135`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001b68b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001b11a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001b670`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001b11a`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001b670`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b06e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b5c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b06e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001b5c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b164`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b6ba`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b164`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001b6ba`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMStatus::StopActivity(WnsCPLog::WnsCMStatus *this)
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
  __int64 *v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+A8h] [rbp-58h]
  int v61; // [rsp+ACh] [rbp-54h]
  PSRWLOCK *v62; // [rsp+B0h] [rbp-50h]
  __int64 v63; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *v64; // [rsp+C0h] [rbp-40h]
  __int64 v65; // [rsp+C8h] [rbp-38h]
  PSRWLOCK *p_SRWLock; // [rsp+D0h] [rbp-30h]
  __int64 v67; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  int *v69; // [rsp+F0h] [rbp-10h]
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
        v69 = &dword_18003E47C;
        UserData.Reserved = 2;
        v70 = 314;
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
    v59 = qword_18003E430;
    v58.Reserved = 2;
    v60 = 64;
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
0x18001af80  push    rbp
0x18001af82  push    rbx
0x18001af83  push    rsi
0x18001af84  push    rdi
0x18001af85  push    r12
0x18001af87  push    r13
0x18001af89  push    r14
0x18001af8b  push    r15
0x18001af8d  lea     rbp, [rsp-148h]
0x18001af95  sub     rsp, 248h
0x18001af9c  mov     rax, cs:__security_cookie
0x18001afa3  xor     rax, rsp
0x18001afa6  mov     [rbp+180h+var_50], rax
0x18001afad  mov     rdi, [rcx+110h]
0x18001afb4  xor     r12d, r12d
0x18001afb7  mov     r14, rcx
0x18001afba  mov     eax, [rdi+48h]
0x18001afbd  test    eax, eax
0x18001afbf  jns     loc_18001B531
0x18001afc5  add     rdi, 50h ; 'P'
0x18001afc9  cmp     eax, [rdi+8]
0x18001afcc  jnz     loc_18001B531
0x18001afd2  mov     rbx, [rcx+118h]
0x18001afd9  test    rdi, rdi
0x18001afdc  jz      loc_18001B538
0x18001afe2  test    rbx, rbx
0x18001afe5  jz      short loc_18001B02C
0x18001afe7  add     rbx, 108h
0x18001afee  mov     rcx, rbx; SRWLock
0x18001aff1  call    cs:__imp_AcquireSRWLockExclusive
0x18001aff7  lea     rax, [rsp+280h+SRWLock]
0x18001affc  mov     [rax], r12
0x18001afff  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x18001b004  test    rcx, rcx
0x18001b007  jz      short loc_18001B00F
0x18001b009  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b00f  mov     rax, [r14+110h]
0x18001b016  mov     dword ptr [rax], 2
0x18001b01c  test    rbx, rbx
0x18001b01f  jz      short loc_18001B051
0x18001b021  mov     rcx, rbx; SRWLock
0x18001b024  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b02a  jmp     short loc_18001B051
0x18001b02c  lea     rax, [rsp+280h+var_238]
0x18001b031  mov     [rax], r12
0x18001b034  mov     rcx, [rsp+280h+var_238]; SRWLock
0x18001b039  test    rcx, rcx
0x18001b03c  jz      short loc_18001B044
0x18001b03e  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b044  mov     rax, [r14+110h]
0x18001b04b  mov     dword ptr [rax], 2
0x18001b051  lea     r9, [rsp+280h+SRWLock]; lpContext
0x18001b056  mov     [rsp+280h+SRWLock], r12
0x18001b05b  lea     r8, [rsp+280h+fPending]; fPending
0x18001b060  mov     [rsp+280h+fPending], r12d
0x18001b065  xor     edx, edx; dwFlags
0x18001b067  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18001b06e  call    cs:__imp_InitOnceBeginInitialize
0x18001b074  test    eax, eax
0x18001b076  jz      loc_18001B16A
0x18001b07c  cmp     [rsp+280h+fPending], r12d
0x18001b081  jz      loc_18001B16A
0x18001b087  lea     rsi, qword_18004A760
0x18001b08e  mov     cs:qword_18004A768, r12
0x18001b095  lea     rax, ??_7FeatureLogging@details@wil@@6B@
0x18001b09c  mov     [rsp+280h+SRWLock], rsi
0x18001b0a1  mov     cs:qword_18004A760, rax
0x18001b0a8  mov     cs:byte_18004A770, r12b
0x18001b0af  mov     cs:dword_18004A774, r12d
0x18001b0b6  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A
0x18001b0bd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x18001b0c4  mov     cs:CallbackContext, rax
0x18001b0cb  call    atexit
0x18001b0d0  mov     rbx, cs:CallbackContext
0x18001b0d7  mov     cs:qword_18004A768, rbx
0x18001b0de  mov     cs:byte_18004A770, 1
0x18001b0e5  mov     rax, [rbx+8]
0x18001b0e9  movups  xmm0, xmmword ptr [rax-10h]
0x18001b0ed  movups  xmmword ptr [rsp+280h+ProviderId.Data1], xmm0
0x18001b0f2  cmp     [rbx+20h], r12
0x18001b0f6  jz      short loc_18001B0FF
0x18001b0f8  mov     ecx, 5
0x18001b0fd  int     29h; Win8: RtlFailFast(ecx)
0x18001b0ff  lea     r9, [rbx+20h]; RegHandle
0x18001b103  mov     [rbx+28h], r12
0x18001b107  mov     r8, rbx; CallbackContext
0x18001b10a  mov     [rbx+30h], r12
0x18001b10e  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001b115  lea     rcx, [rsp+280h+ProviderId]; ProviderId
0x18001b11a  call    cs:__imp_EventRegister
0x18001b120  test    eax, eax
0x18001b122  jnz     short loc_18001B13B
0x18001b124  mov     r8, [rbx+8]
0x18001b128  mov     edx, 2
0x18001b12d  mov     rcx, [rbx+20h]
0x18001b131  movzx   r9d, word ptr [r8]
0x18001b135  call    cs:__imp_EventSetInformation
0x18001b13b  mov     rax, cs:qword_18004A760
0x18001b142  mov     rcx, rsi
0x18001b145  mov     cs:dword_18004A774, 1
0x18001b14f  mov     rax, [rax+8]
0x18001b153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b158  mov     r8, rsi; lpContext
0x18001b15b  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18001b162  xor     edx, edx; dwFlags
0x18001b164  call    cs:__imp_InitOnceComplete
0x18001b16a  mov     rax, [rsp+280h+SRWLock]
0x18001b16f  mov     r13, [rax+8]
0x18001b173  mov     eax, [r13+0]
0x18001b177  cmp     eax, 5
0x18001b17a  jbe     loc_18001B7A9
0x18001b180  mov     eax, [rdi+44h]
0x18001b183  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001b18a  mov     rdx, [rdi+30h]
0x18001b18e  mov     r8, [rdi+78h]
0x18001b192  mov     r9, [rdi+70h]
0x18001b196  mov     r10, [rdi+60h]
0x18001b19a  mov     r11, [rdi+58h]
0x18001b19e  mov     rbx, [rdi+48h]
0x18001b1a2  mov     rsi, [rdi+18h]
0x18001b1a6  mov     r15, [rdi+80h]
0x18001b1ad  mov     r12, [rdi+38h]
0x18001b1b1  mov     [rsp+280h+fPending], eax
0x18001b1b5  mov     eax, [rdi+10h]
0x18001b1b8  mov     [rsp+280h+var_228], eax
0x18001b1bc  mov     eax, [rdi+68h]
0x18001b1bf  mov     [rsp+280h+var_224], eax
0x18001b1c3  mov     eax, [rdi+50h]
0x18001b1c6  mov     [rsp+280h+var_220], eax
0x18001b1ca  mov     eax, [rdi+20h]
0x18001b1cd  mov     [rsp+280h+var_21C], eax
0x18001b1d1  mov     eax, [rdi]
0x18001b1d3  mov     [rsp+280h+var_218], eax
0x18001b1d7  mov     eax, [rdi+40h]
0x18001b1da  mov     [rsp+280h+var_240], eax
0x18001b1de  mov     eax, [rdi+8]
0x18001b1e1  mov     rdi, [r14+110h]
0x18001b1e8  mov     dword ptr [rsp+280h+var_238], eax
0x18001b1ec  mov     [rsp+280h+var_210], 1000000h
0x18001b1f5  mov     [rsp+280h+var_230], 0
0x18001b1fe  test    rdx, rdx
0x18001b201  jz      short loc_18001B213
0x18001b203  mov     rax, rcx
0x18001b206  inc     rax
0x18001b209  cmp     byte ptr [rdx+rax], 0
0x18001b20d  jnz     short loc_18001B206
0x18001b20f  inc     eax
0x18001b211  jmp     short loc_18001B21F
0x18001b213  lea     rdx, byte_18003A073
0x18001b21a  mov     eax, 1
0x18001b21f  mov     [rbp+180h+var_58], eax
0x18001b225  lea     rax, [rsp+280h+fPending]
0x18001b22a  mov     [rbp+180h+var_60], rdx
0x18001b231  xor     edx, edx
0x18001b233  mov     [rbp+180h+var_70], rax
0x18001b23a  lea     rax, [rsp+280h+var_228]
0x18001b23f  mov     [rbp+180h+var_80], rax
0x18001b246  mov     [rbp+180h+var_54], edx
0x18001b24c  mov     [rbp+180h+var_68], 4
0x18001b257  mov     [rbp+180h+var_78], 4
0x18001b262  test    r8, r8
0x18001b265  jz      short loc_18001B285
0x18001b267  mov     rax, rcx
0x18001b26a  nop     word ptr [rax+rax+00h]
0x18001b270  cmp     [r8+rax*2+2], dx
0x18001b276  lea     rax, [rax+1]
0x18001b27a  jnz     short loc_18001B270
0x18001b27c  lea     eax, ds:2[rax*2]
0x18001b283  jmp     short loc_18001B291
0x18001b285  lea     r8, dword_18003A074
0x18001b28c  mov     eax, 2
0x18001b291  mov     [rbp+180h+var_90], r8
0x18001b298  mov     [rbp+180h+var_88], eax
0x18001b29e  mov     [rbp+180h+var_84], edx
0x18001b2a4  test    r9, r9
0x18001b2a7  jz      short loc_18001B2BD
0x18001b2a9  mov     rax, rcx
0x18001b2ac  nop     dword ptr [rax+00h]
0x18001b2b0  inc     rax
0x18001b2b3  cmp     [r9+rax], dl
0x18001b2b7  jnz     short loc_18001B2B0
0x18001b2b9  inc     eax
0x18001b2bb  jmp     short loc_18001B2C9
0x18001b2bd  lea     r9, byte_18003A073
0x18001b2c4  mov     eax, 1
0x18001b2c9  mov     [rbp+180h+var_98], eax
0x18001b2cf  lea     rax, [rsp+280h+var_224]
0x18001b2d4  mov     [rbp+180h+var_B0], rax
0x18001b2db  mov     [rbp+180h+var_A0], r9
0x18001b2e2  mov     [rbp+180h+var_94], edx
0x18001b2e8  mov     [rbp+180h+var_A8], 4
0x18001b2f3  test    r10, r10
0x18001b2f6  jz      short loc_18001B315
0x18001b2f8  mov     rax, rcx
0x18001b2fb  nop     dword ptr [rax+rax+00h]
0x18001b300  cmp     [r10+rax*2+2], dx
0x18001b306  lea     rax, [rax+1]
0x18001b30a  jnz     short loc_18001B300
0x18001b30c  lea     eax, ds:2[rax*2]
0x18001b313  jmp     short loc_18001B321
0x18001b315  lea     r10, dword_18003A074
0x18001b31c  mov     eax, 2
0x18001b321  mov     [rbp+180h+var_C0], r10
0x18001b328  mov     [rbp+180h+var_B8], eax
0x18001b32e  mov     [rbp+180h+var_B4], edx
0x18001b334  test    r11, r11
0x18001b337  jz      short loc_18001B34D
0x18001b339  mov     rax, rcx
0x18001b33c  nop     dword ptr [rax+00h]
0x18001b340  inc     rax
0x18001b343  cmp     [r11+rax], dl
0x18001b347  jnz     short loc_18001B340
0x18001b349  inc     eax
0x18001b34b  jmp     short loc_18001B359
0x18001b34d  lea     r11, byte_18003A073
0x18001b354  mov     eax, 1
0x18001b359  mov     [rbp+180h+var_C8], eax
0x18001b35f  lea     rax, [rsp+280h+var_220]
0x18001b364  mov     [rbp+180h+var_E0], rax
0x18001b36b  mov     [rbp+180h+var_D0], r11
0x18001b372  mov     [rbp+180h+var_C4], edx
0x18001b378  mov     [rbp+180h+var_D8], 4
0x18001b383  test    rbx, rbx
0x18001b386  jz      short loc_18001B39C
0x18001b388  mov     rax, rcx
0x18001b38b  nop     dword ptr [rax+rax+00h]
0x18001b390  inc     rax
0x18001b393  cmp     [rbx+rax], dl
0x18001b396  jnz     short loc_18001B390
0x18001b398  inc     eax
0x18001b39a  jmp     short loc_18001B3A8
0x18001b39c  lea     rbx, byte_18003A073
0x18001b3a3  mov     eax, 1
0x18001b3a8  mov     [rbp+180h+var_E8], eax
0x18001b3ae  lea     rax, [rsp+280h+var_21C]
0x18001b3b3  mov     [rbp+180h+var_100], rax
0x18001b3ba  mov     [rbp+180h+var_F0], rbx
0x18001b3c1  mov     [rbp+180h+var_E4], edx
0x18001b3c7  mov     [rbp+180h+var_F8], 4
0x18001b3d2  test    rsi, rsi
0x18001b3d5  jz      short loc_18001B3F4
0x18001b3d7  mov     rax, rcx
0x18001b3da  nop     word ptr [rax+rax+00h]
0x18001b3e0  cmp     [rsi+rax*2+2], dx
0x18001b3e5  lea     rax, [rax+1]
0x18001b3e9  jnz     short loc_18001B3E0
0x18001b3eb  lea     eax, ds:2[rax*2]
0x18001b3f2  jmp     short loc_18001B400
0x18001b3f4  lea     rsi, dword_18003A074
0x18001b3fb  mov     eax, 2
0x18001b400  mov     [rbp+180h+var_108], eax
0x18001b403  lea     rax, [rsp+280h+var_218]
0x18001b408  mov     [rbp+180h+var_120], rax
0x18001b40c  mov     [rbp+180h+var_110], rsi
0x18001b410  mov     [rbp+180h+var_104], edx
0x18001b413  mov     [rbp+180h+var_118], 4
0x18001b41b  test    r15, r15
0x18001b41e  jz      short loc_18001B430
0x18001b420  mov     rax, rcx
0x18001b423  inc     rax
0x18001b426  cmp     [r15+rax], dl
0x18001b42a  jnz     short loc_18001B423
0x18001b42c  inc     eax
0x18001b42e  jmp     short loc_18001B43C
0x18001b430  lea     r15, byte_18003A073
0x18001b437  mov     eax, 1
0x18001b43c  mov     [rbp+180h+var_128], eax
0x18001b43f  lea     rax, [rsp+280h+var_240]
0x18001b444  mov     [rbp+180h+var_140], rax
0x18001b448  mov     [rbp+180h+var_130], r15
0x18001b44c  mov     [rbp+180h+var_124], edx
0x18001b44f  mov     [rbp+180h+var_138], 4
0x18001b457  test    r12, r12
0x18001b45a  jz      short loc_18001B46D
0x18001b45c  nop     dword ptr [rax+00h]
0x18001b460  inc     rcx
0x18001b463  cmp     [r12+rcx], dl
0x18001b467  jnz     short loc_18001B460
0x18001b469  inc     ecx
0x18001b46b  jmp     short loc_18001B479
0x18001b46d  lea     r12, byte_18003A073
0x18001b474  mov     ecx, 1
0x18001b479  mov     [rbp+180h+var_148], ecx
0x18001b47c  lea     rax, [rsp+280h+var_238]
0x18001b481  mov     [rbp+180h+var_160], rax
0x18001b485  lea     r8, [rdi+8]
0x18001b489  mov     [rbp+180h+var_144], edx
0x18001b48c  lea     rax, [rsp+280h+var_210]
0x18001b491  mov     [rbp+180h+var_170], rax
0x18001b495  lea     rax, [rsp+280h+var_230]
0x18001b49a  mov     [rbp+180h+var_180], rax
0x18001b49e  movzx   eax, cs:word_18003E472
0x18001b4a5  mov     dword ptr [rsp+280h+ProviderId.Data2], eax
0x18001b4a9  mov     rax, [r13+8]
0x18001b4ad  mov     [rbp+180h+var_1A0], rax
0x18001b4b1  mov     qword ptr [rbp+180h+ProviderId.Data4], rdx
0x18001b4b5  lea     rdx, _TraceLoggingMetadata
0x18001b4bc  mov     [rbp+180h+var_150], r12
0x18001b4c0  mov     [rbp+180h+var_158], 4
0x18001b4c8  mov     [rbp+180h+var_168], 8
  ... truncated ...
```
