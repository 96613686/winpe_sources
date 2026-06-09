# WnsCPLog::WnsCMConfigureBatching::StopActivity(void)

- ea: `0x180019520`
- end: `0x180019d74`
- name: `?StopActivity@WnsCMConfigureBatching@WnsCPLog@@MEAAXXZ`
- size: `2132`
- prototype: `void __fastcall(WnsCPLog::WnsCMConfigureBatching *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f270`
- `0x180019520`
- `0x180026200`
- `0x1800265b0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019591`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019ae7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019591`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019ae7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019aff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b34`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195c4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019aff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b1a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019b34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c74`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019d43`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180019d43`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800196d5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019c2b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x1800196d5`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180019c2b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800196ba`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019c10`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x1800196ba`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180019c10`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001960e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019b64`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001960e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019b64`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019704`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019c5a`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019704`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019c5a`

## pseudocode

```c
void __fastcall WnsCPLog::WnsCMConfigureBatching::StopActivity(WnsCPLog::WnsCMConfigureBatching *this)
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
  __int16 *v59; // [rsp+A0h] [rbp-60h]
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
        v69 = byte_18003F531;
        UserData.Reserved = 2;
        v70 = 325;
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
    v59 = word_18003F4DA;
    v58.Reserved = 2;
    v60 = 75;
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
0x180019520  push    rbp
0x180019522  push    rbx
0x180019523  push    rsi
0x180019524  push    rdi
0x180019525  push    r12
0x180019527  push    r13
0x180019529  push    r14
0x18001952b  push    r15
0x18001952d  lea     rbp, [rsp-148h]
0x180019535  sub     rsp, 248h
0x18001953c  mov     rax, cs:__security_cookie
0x180019543  xor     rax, rsp
0x180019546  mov     [rbp+180h+var_50], rax
0x18001954d  mov     rdi, [rcx+110h]
0x180019554  xor     r12d, r12d
0x180019557  mov     r14, rcx
0x18001955a  mov     eax, [rdi+48h]
0x18001955d  test    eax, eax
0x18001955f  jns     loc_180019AD1
0x180019565  add     rdi, 50h ; 'P'
0x180019569  cmp     eax, [rdi+8]
0x18001956c  jnz     loc_180019AD1
0x180019572  mov     rbx, [rcx+118h]
0x180019579  test    rdi, rdi
0x18001957c  jz      loc_180019AD8
0x180019582  test    rbx, rbx
0x180019585  jz      short loc_1800195CC
0x180019587  add     rbx, 108h
0x18001958e  mov     rcx, rbx; SRWLock
0x180019591  call    cs:__imp_AcquireSRWLockExclusive
0x180019597  lea     rax, [rsp+280h+SRWLock]
0x18001959c  mov     [rax], r12
0x18001959f  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x1800195a4  test    rcx, rcx
0x1800195a7  jz      short loc_1800195AF
0x1800195a9  call    cs:__imp_ReleaseSRWLockExclusive
0x1800195af  mov     rax, [r14+110h]
0x1800195b6  mov     dword ptr [rax], 2
0x1800195bc  test    rbx, rbx
0x1800195bf  jz      short loc_1800195F1
0x1800195c1  mov     rcx, rbx; SRWLock
0x1800195c4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800195ca  jmp     short loc_1800195F1
0x1800195cc  lea     rax, [rsp+280h+var_238]
0x1800195d1  mov     [rax], r12
0x1800195d4  mov     rcx, [rsp+280h+var_238]; SRWLock
0x1800195d9  test    rcx, rcx
0x1800195dc  jz      short loc_1800195E4
0x1800195de  call    cs:__imp_ReleaseSRWLockExclusive
0x1800195e4  mov     rax, [r14+110h]
0x1800195eb  mov     dword ptr [rax], 2
0x1800195f1  lea     r9, [rsp+280h+SRWLock]; lpContext
0x1800195f6  mov     [rsp+280h+SRWLock], r12
0x1800195fb  lea     r8, [rsp+280h+fPending]; fPending
0x180019600  mov     [rsp+280h+fPending], r12d
0x180019605  xor     edx, edx; dwFlags
0x180019607  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x18001960e  call    cs:__imp_InitOnceBeginInitialize
0x180019614  test    eax, eax
0x180019616  jz      loc_18001970A
0x18001961c  cmp     [rsp+280h+fPending], r12d
0x180019621  jz      loc_18001970A
0x180019627  lea     rsi, qword_18004A760
0x18001962e  mov     cs:qword_18004A768, r12
0x180019635  lea     rax, ??_7FeatureLogging@details@wil@@6B@
0x18001963c  mov     [rsp+280h+SRWLock], rsi
0x180019641  mov     cs:qword_18004A760, rax
0x180019648  mov     cs:byte_18004A770, r12b
0x18001964f  mov     cs:dword_18004A774, r12d
0x180019656  lea     rax, ?__hInner@?1???0StaticHandle@WnsCPTracelogger@@QEAA@XZ@4U_tlgProvider_t@@A
0x18001965d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_633a74d489e420a2ff0e92495a1626f6_@@CA@XZ; void (__cdecl *)()
0x180019664  mov     cs:CallbackContext, rax
0x18001966b  call    atexit
0x180019670  mov     rbx, cs:CallbackContext
0x180019677  mov     cs:qword_18004A768, rbx
0x18001967e  mov     cs:byte_18004A770, 1
0x180019685  mov     rax, [rbx+8]
0x180019689  movups  xmm0, xmmword ptr [rax-10h]
0x18001968d  movups  xmmword ptr [rsp+280h+ProviderId.Data1], xmm0
0x180019692  cmp     [rbx+20h], r12
0x180019696  jz      short loc_18001969F
0x180019698  mov     ecx, 5
0x18001969d  int     29h; Win8: RtlFailFast(ecx)
0x18001969f  lea     r9, [rbx+20h]; RegHandle
0x1800196a3  mov     [rbx+28h], r12
0x1800196a7  mov     r8, rbx; CallbackContext
0x1800196aa  mov     [rbx+30h], r12
0x1800196ae  lea     rdx, _tlgEnableCallback; EnableCallback
0x1800196b5  lea     rcx, [rsp+280h+ProviderId]; ProviderId
0x1800196ba  call    cs:__imp_EventRegister
0x1800196c0  test    eax, eax
0x1800196c2  jnz     short loc_1800196DB
0x1800196c4  mov     r8, [rbx+8]
0x1800196c8  mov     edx, 2
0x1800196cd  mov     rcx, [rbx+20h]
0x1800196d1  movzx   r9d, word ptr [r8]
0x1800196d5  call    cs:__imp_EventSetInformation
0x1800196db  mov     rax, cs:qword_18004A760
0x1800196e2  mov     rcx, rsi
0x1800196e5  mov     cs:dword_18004A774, 1
0x1800196ef  mov     rax, [rax+8]
0x1800196f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f8  mov     r8, rsi; lpContext
0x1800196fb  lea     rcx, ?wrapper@?1??Instance@WnsCPTracelogger@@KAPEAV2@XZ@4V?$static_lazy@VWnsCPTracelogger@@@details@wil@@A; lpInitOnce
0x180019702  xor     edx, edx; dwFlags
0x180019704  call    cs:__imp_InitOnceComplete
0x18001970a  mov     rax, [rsp+280h+SRWLock]
0x18001970f  mov     r13, [rax+8]
0x180019713  mov     eax, [r13+0]
0x180019717  cmp     eax, 5
0x18001971a  jbe     loc_180019D49
0x180019720  mov     eax, [rdi+44h]
0x180019723  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001972a  mov     rdx, [rdi+30h]
0x18001972e  mov     r8, [rdi+78h]
0x180019732  mov     r9, [rdi+70h]
0x180019736  mov     r10, [rdi+60h]
0x18001973a  mov     r11, [rdi+58h]
0x18001973e  mov     rbx, [rdi+48h]
0x180019742  mov     rsi, [rdi+18h]
0x180019746  mov     r15, [rdi+80h]
0x18001974d  mov     r12, [rdi+38h]
0x180019751  mov     [rsp+280h+fPending], eax
0x180019755  mov     eax, [rdi+10h]
0x180019758  mov     [rsp+280h+var_228], eax
0x18001975c  mov     eax, [rdi+68h]
0x18001975f  mov     [rsp+280h+var_224], eax
0x180019763  mov     eax, [rdi+50h]
0x180019766  mov     [rsp+280h+var_220], eax
0x18001976a  mov     eax, [rdi+20h]
0x18001976d  mov     [rsp+280h+var_21C], eax
0x180019771  mov     eax, [rdi]
0x180019773  mov     [rsp+280h+var_218], eax
0x180019777  mov     eax, [rdi+40h]
0x18001977a  mov     [rsp+280h+var_240], eax
0x18001977e  mov     eax, [rdi+8]
0x180019781  mov     rdi, [r14+110h]
0x180019788  mov     dword ptr [rsp+280h+var_238], eax
0x18001978c  mov     [rsp+280h+var_210], 1000000h
0x180019795  mov     [rsp+280h+var_230], 0
0x18001979e  test    rdx, rdx
0x1800197a1  jz      short loc_1800197B3
0x1800197a3  mov     rax, rcx
0x1800197a6  inc     rax
0x1800197a9  cmp     byte ptr [rdx+rax], 0
0x1800197ad  jnz     short loc_1800197A6
0x1800197af  inc     eax
0x1800197b1  jmp     short loc_1800197BF
0x1800197b3  lea     rdx, byte_18003A073
0x1800197ba  mov     eax, 1
0x1800197bf  mov     [rbp+180h+var_58], eax
0x1800197c5  lea     rax, [rsp+280h+fPending]
0x1800197ca  mov     [rbp+180h+var_60], rdx
0x1800197d1  xor     edx, edx
0x1800197d3  mov     [rbp+180h+var_70], rax
0x1800197da  lea     rax, [rsp+280h+var_228]
0x1800197df  mov     [rbp+180h+var_80], rax
0x1800197e6  mov     [rbp+180h+var_54], edx
0x1800197ec  mov     [rbp+180h+var_68], 4
0x1800197f7  mov     [rbp+180h+var_78], 4
0x180019802  test    r8, r8
0x180019805  jz      short loc_180019825
0x180019807  mov     rax, rcx
0x18001980a  nop     word ptr [rax+rax+00h]
0x180019810  cmp     [r8+rax*2+2], dx
0x180019816  lea     rax, [rax+1]
0x18001981a  jnz     short loc_180019810
0x18001981c  lea     eax, ds:2[rax*2]
0x180019823  jmp     short loc_180019831
0x180019825  lea     r8, dword_18003A074
0x18001982c  mov     eax, 2
0x180019831  mov     [rbp+180h+var_90], r8
0x180019838  mov     [rbp+180h+var_88], eax
0x18001983e  mov     [rbp+180h+var_84], edx
0x180019844  test    r9, r9
0x180019847  jz      short loc_18001985D
0x180019849  mov     rax, rcx
0x18001984c  nop     dword ptr [rax+00h]
0x180019850  inc     rax
0x180019853  cmp     [r9+rax], dl
0x180019857  jnz     short loc_180019850
0x180019859  inc     eax
0x18001985b  jmp     short loc_180019869
0x18001985d  lea     r9, byte_18003A073
0x180019864  mov     eax, 1
0x180019869  mov     [rbp+180h+var_98], eax
0x18001986f  lea     rax, [rsp+280h+var_224]
0x180019874  mov     [rbp+180h+var_B0], rax
0x18001987b  mov     [rbp+180h+var_A0], r9
0x180019882  mov     [rbp+180h+var_94], edx
0x180019888  mov     [rbp+180h+var_A8], 4
0x180019893  test    r10, r10
0x180019896  jz      short loc_1800198B5
0x180019898  mov     rax, rcx
0x18001989b  nop     dword ptr [rax+rax+00h]
0x1800198a0  cmp     [r10+rax*2+2], dx
0x1800198a6  lea     rax, [rax+1]
0x1800198aa  jnz     short loc_1800198A0
0x1800198ac  lea     eax, ds:2[rax*2]
0x1800198b3  jmp     short loc_1800198C1
0x1800198b5  lea     r10, dword_18003A074
0x1800198bc  mov     eax, 2
0x1800198c1  mov     [rbp+180h+var_C0], r10
0x1800198c8  mov     [rbp+180h+var_B8], eax
0x1800198ce  mov     [rbp+180h+var_B4], edx
0x1800198d4  test    r11, r11
0x1800198d7  jz      short loc_1800198ED
0x1800198d9  mov     rax, rcx
0x1800198dc  nop     dword ptr [rax+00h]
0x1800198e0  inc     rax
0x1800198e3  cmp     [r11+rax], dl
0x1800198e7  jnz     short loc_1800198E0
0x1800198e9  inc     eax
0x1800198eb  jmp     short loc_1800198F9
0x1800198ed  lea     r11, byte_18003A073
0x1800198f4  mov     eax, 1
0x1800198f9  mov     [rbp+180h+var_C8], eax
0x1800198ff  lea     rax, [rsp+280h+var_220]
0x180019904  mov     [rbp+180h+var_E0], rax
0x18001990b  mov     [rbp+180h+var_D0], r11
0x180019912  mov     [rbp+180h+var_C4], edx
0x180019918  mov     [rbp+180h+var_D8], 4
0x180019923  test    rbx, rbx
0x180019926  jz      short loc_18001993C
0x180019928  mov     rax, rcx
0x18001992b  nop     dword ptr [rax+rax+00h]
0x180019930  inc     rax
0x180019933  cmp     [rbx+rax], dl
0x180019936  jnz     short loc_180019930
0x180019938  inc     eax
0x18001993a  jmp     short loc_180019948
0x18001993c  lea     rbx, byte_18003A073
0x180019943  mov     eax, 1
0x180019948  mov     [rbp+180h+var_E8], eax
0x18001994e  lea     rax, [rsp+280h+var_21C]
0x180019953  mov     [rbp+180h+var_100], rax
0x18001995a  mov     [rbp+180h+var_F0], rbx
0x180019961  mov     [rbp+180h+var_E4], edx
0x180019967  mov     [rbp+180h+var_F8], 4
0x180019972  test    rsi, rsi
0x180019975  jz      short loc_180019994
0x180019977  mov     rax, rcx
0x18001997a  nop     word ptr [rax+rax+00h]
0x180019980  cmp     [rsi+rax*2+2], dx
0x180019985  lea     rax, [rax+1]
0x180019989  jnz     short loc_180019980
0x18001998b  lea     eax, ds:2[rax*2]
0x180019992  jmp     short loc_1800199A0
0x180019994  lea     rsi, dword_18003A074
0x18001999b  mov     eax, 2
0x1800199a0  mov     [rbp+180h+var_108], eax
0x1800199a3  lea     rax, [rsp+280h+var_218]
0x1800199a8  mov     [rbp+180h+var_120], rax
0x1800199ac  mov     [rbp+180h+var_110], rsi
0x1800199b0  mov     [rbp+180h+var_104], edx
0x1800199b3  mov     [rbp+180h+var_118], 4
0x1800199bb  test    r15, r15
0x1800199be  jz      short loc_1800199D0
0x1800199c0  mov     rax, rcx
0x1800199c3  inc     rax
0x1800199c6  cmp     [r15+rax], dl
0x1800199ca  jnz     short loc_1800199C3
0x1800199cc  inc     eax
0x1800199ce  jmp     short loc_1800199DC
0x1800199d0  lea     r15, byte_18003A073
0x1800199d7  mov     eax, 1
0x1800199dc  mov     [rbp+180h+var_128], eax
0x1800199df  lea     rax, [rsp+280h+var_240]
0x1800199e4  mov     [rbp+180h+var_140], rax
0x1800199e8  mov     [rbp+180h+var_130], r15
0x1800199ec  mov     [rbp+180h+var_124], edx
0x1800199ef  mov     [rbp+180h+var_138], 4
0x1800199f7  test    r12, r12
0x1800199fa  jz      short loc_180019A0D
0x1800199fc  nop     dword ptr [rax+00h]
0x180019a00  inc     rcx
0x180019a03  cmp     [r12+rcx], dl
0x180019a07  jnz     short loc_180019A00
0x180019a09  inc     ecx
0x180019a0b  jmp     short loc_180019A19
0x180019a0d  lea     r12, byte_18003A073
0x180019a14  mov     ecx, 1
0x180019a19  mov     [rbp+180h+var_148], ecx
0x180019a1c  lea     rax, [rsp+280h+var_238]
0x180019a21  mov     [rbp+180h+var_160], rax
0x180019a25  lea     r8, [rdi+8]
0x180019a29  mov     [rbp+180h+var_144], edx
0x180019a2c  lea     rax, [rsp+280h+var_210]
0x180019a31  mov     [rbp+180h+var_170], rax
0x180019a35  lea     rax, [rsp+280h+var_230]
0x180019a3a  mov     [rbp+180h+var_180], rax
0x180019a3e  movzx   eax, cs:word_18003F527
0x180019a45  mov     dword ptr [rsp+280h+ProviderId.Data2], eax
0x180019a49  mov     rax, [r13+8]
0x180019a4d  mov     [rbp+180h+var_1A0], rax
0x180019a51  mov     qword ptr [rbp+180h+ProviderId.Data4], rdx
0x180019a55  lea     rdx, _TraceLoggingMetadata
0x180019a5c  mov     [rbp+180h+var_150], r12
0x180019a60  mov     [rbp+180h+var_158], 4
0x180019a68  mov     [rbp+180h+var_168], 8
  ... truncated ...
```
