# NetSetupTraceLogging::EvaluatePluginFilter::StopActivity(void)

- ea: `0x180048de0`
- end: `0x1800495e1`
- name: `?StopActivity@EvaluatePluginFilter@NetSetupTraceLogging@@MEAAXXZ`
- size: `2049`
- prototype: `void __fastcall(NetSetupTraceLogging::EvaluatePluginFilter *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x18000e580`
- `0x180048de0`
- `0x180064e14`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048ea7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049391`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800493ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800493c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048e8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180048ea7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049391`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800493ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800493c6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048e5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049379`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180048e5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049379`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800494d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800494d4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180048f7c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004949b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180048f7c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18004949b`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180048ed7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800493f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180048ed7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800493f6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800495a4`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800495a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NetSetupTraceLogging::EvaluatePluginFilter::StopActivity(
        NetSetupTraceLogging::EvaluatePluginFilter *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rbx
  RTL_SRWLOCK *v6; // rbx
  _QWORD *Ptr; // r13
  const wchar_t *v8; // rdx
  const WCHAR *v9; // r8
  const wchar_t *v10; // r9
  const WCHAR *v11; // r10
  const wchar_t *v12; // r11
  const wchar_t *v13; // rbx
  const WCHAR *v14; // r14
  const wchar_t *v15; // r15
  const wchar_t *v16; // r12
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  int v35; // ecx
  RTL_SRWLOCK *v36; // rbx
  _QWORD *v37; // rbx
  __int64 v38; // r8
  unsigned int v39; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK v40; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43; // [rsp+4Ch] [rbp-B4h] BYREF
  int v44; // [rsp+50h] [rbp-B0h] BYREF
  int v45; // [rsp+54h] [rbp-ACh] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  PSRWLOCK v47[2]; // [rsp+60h] [rbp-A0h] BYREF
  PSRWLOCK SRWLock; // [rsp+70h] [rbp-90h] BYREF
  WINBOOL fPending; // [rsp+78h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+80h] [rbp-80h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v51; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v52; // [rsp+A0h] [rbp-60h]
  int v53; // [rsp+A8h] [rbp-58h]
  int v54; // [rsp+ACh] [rbp-54h]
  PSRWLOCK *v55; // [rsp+B0h] [rbp-50h]
  __int64 v56; // [rsp+B8h] [rbp-48h]
  PSRWLOCK *v57; // [rsp+C0h] [rbp-40h]
  __int64 v58; // [rsp+C8h] [rbp-38h]
  PSRWLOCK *p_SRWLock; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+D8h] [rbp-28h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+E0h] [rbp-20h] BYREF
  char *v62; // [rsp+F0h] [rbp-10h]
  int v63; // [rsp+F8h] [rbp-8h]
  int v64; // [rsp+FCh] [rbp-4h]
  PSRWLOCK *v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  PSRWLOCK *v67; // [rsp+110h] [rbp+10h]
  __int64 v68; // [rsp+118h] [rbp+18h]
  PSRWLOCK *v69; // [rsp+120h] [rbp+20h]
  __int64 v70; // [rsp+128h] [rbp+28h]
  const wchar_t *v71; // [rsp+130h] [rbp+30h]
  int v72; // [rsp+138h] [rbp+38h]
  int v73; // [rsp+13Ch] [rbp+3Ch]
  unsigned int *v74; // [rsp+140h] [rbp+40h]
  __int64 v75; // [rsp+148h] [rbp+48h]
  const wchar_t *v76; // [rsp+150h] [rbp+50h]
  int v77; // [rsp+158h] [rbp+58h]
  int v78; // [rsp+15Ch] [rbp+5Ch]
  int *v79; // [rsp+160h] [rbp+60h]
  __int64 v80; // [rsp+168h] [rbp+68h]
  const WCHAR *v81; // [rsp+170h] [rbp+70h]
  int v82; // [rsp+178h] [rbp+78h]
  int v83; // [rsp+17Ch] [rbp+7Ch]
  int *v84; // [rsp+180h] [rbp+80h]
  __int64 v85; // [rsp+188h] [rbp+88h]
  const wchar_t *v86; // [rsp+190h] [rbp+90h]
  int v87; // [rsp+198h] [rbp+98h]
  int v88; // [rsp+19Ch] [rbp+9Ch]
  int *v89; // [rsp+1A0h] [rbp+A0h]
  __int64 v90; // [rsp+1A8h] [rbp+A8h]
  const wchar_t *v91; // [rsp+1B0h] [rbp+B0h]
  int v92; // [rsp+1B8h] [rbp+B8h]
  int v93; // [rsp+1BCh] [rbp+BCh]
  const WCHAR *v94; // [rsp+1C0h] [rbp+C0h]
  int v95; // [rsp+1C8h] [rbp+C8h]
  int v96; // [rsp+1CCh] [rbp+CCh]
  int *v97; // [rsp+1D0h] [rbp+D0h]
  __int64 v98; // [rsp+1D8h] [rbp+D8h]
  const wchar_t *v99; // [rsp+1E0h] [rbp+E0h]
  int v100; // [rsp+1E8h] [rbp+E8h]
  int v101; // [rsp+1ECh] [rbp+ECh]
  const WCHAR *v102; // [rsp+1F0h] [rbp+F0h]
  int v103; // [rsp+1F8h] [rbp+F8h]
  int v104; // [rsp+1FCh] [rbp+FCh]
  int *v105; // [rsp+200h] [rbp+100h]
  __int64 v106; // [rsp+208h] [rbp+108h]
  WINBOOL *p_fPending; // [rsp+210h] [rbp+110h]
  __int64 v108; // [rsp+218h] [rbp+118h]
  const wchar_t *v109; // [rsp+220h] [rbp+120h]
  int v110; // [rsp+228h] [rbp+128h]
  int v111; // [rsp+22Ch] [rbp+12Ch]

  v47[1] = (PSRWLOCK)-2LL;
  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) )
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
        v40 = 0;
        **((_DWORD **)this + 34) = 2;
      }
      SRWLock = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
        && fPending )
      {
        SRWLock = (PSRWLOCK)&qword_1800D4E78;
        qword_1800D4E80 = 0;
        byte_1800D4E88 = 0;
        dword_1800D4E8C = 0;
        qword_1800D4E78 = (__int64)&NetSetupTraceLogging::`vftable';
        CallbackContext = &`NetSetupTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_17d5a69de876e4b99dd4545a5408007a_::_lambda_invoker_cdecl_);
        qword_1800D4E80 = (__int64)CallbackContext;
        byte_1800D4E88 = 1;
        TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
        dword_1800D4E8C = 1;
        (*(void (__fastcall **)(__int64 *))(qword_1800D4E78 + 8))(&qword_1800D4E78);
        InitOnceComplete(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &qword_1800D4E78);
      }
      Ptr = SRWLock[1].Ptr;
      if ( *(_DWORD *)Ptr > 5u && (Ptr[2] & 2) != 0 && (Ptr[3] & 2LL) == Ptr[3] )
      {
        v8 = (const wchar_t *)*((_QWORD *)v4 + 6);
        fPending = v4[17];
        v42 = v4[4];
        v9 = (const WCHAR *)*((_QWORD *)v4 + 15);
        v10 = (const wchar_t *)*((_QWORD *)v4 + 14);
        v43 = v4[26];
        v11 = (const WCHAR *)*((_QWORD *)v4 + 12);
        v12 = (const wchar_t *)*((_QWORD *)v4 + 11);
        v44 = v4[20];
        v13 = (const wchar_t *)*((_QWORD *)v4 + 9);
        v45 = v4[8];
        v14 = (const WCHAR *)*((_QWORD *)v4 + 3);
        v46 = *v4;
        v15 = (const wchar_t *)*((_QWORD *)v4 + 16);
        v39 = v4[16];
        v16 = (const wchar_t *)*((_QWORD *)v4 + 7);
        LODWORD(v40) = v4[2];
        v47[0] = (PSRWLOCK)0x1000000;
        v41 = 0;
        v17 = *((_QWORD *)this + 34);
        v18 = -1;
        if ( v8 )
        {
          v19 = -1;
          do
            ++v19;
          while ( *((_BYTE *)v8 + v19) );
          v20 = v19 + 1;
        }
        else
        {
          v8 = &qword_1800A2F40;
          v20 = 1;
        }
        v109 = v8;
        v110 = v20;
        v111 = 0;
        p_fPending = &fPending;
        v108 = 4;
        v105 = &v42;
        v106 = 4;
        if ( v9 )
        {
          v21 = -1;
          do
            ++v21;
          while ( v9[v21] );
          v22 = 2 * v21 + 2;
        }
        else
        {
          v9 = &Data;
          v22 = 2;
        }
        v102 = v9;
        v103 = v22;
        v104 = 0;
        if ( v10 )
        {
          v23 = -1;
          do
            ++v23;
          while ( *((_BYTE *)v10 + v23) );
          v24 = v23 + 1;
        }
        else
        {
          v10 = &qword_1800A2F40;
          v24 = 1;
        }
        v99 = v10;
        v100 = v24;
        v101 = 0;
        v97 = &v43;
        v98 = 4;
        if ( v11 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v11[v25] );
          v26 = 2 * v25 + 2;
        }
        else
        {
          v11 = &Data;
          v26 = 2;
        }
        v94 = v11;
        v95 = v26;
        v96 = 0;
        if ( v12 )
        {
          v27 = -1;
          do
            ++v27;
          while ( *((_BYTE *)v12 + v27) );
          v28 = v27 + 1;
        }
        else
        {
          v12 = &qword_1800A2F40;
          v28 = 1;
        }
        v91 = v12;
        v92 = v28;
        v93 = 0;
        v89 = &v44;
        v90 = 4;
        if ( v13 )
        {
          v29 = -1;
          do
            ++v29;
          while ( *((_BYTE *)v13 + v29) );
          v30 = v29 + 1;
        }
        else
        {
          v13 = &qword_1800A2F40;
          v30 = 1;
        }
        v86 = v13;
        v87 = v30;
        v88 = 0;
        v84 = &v45;
        v85 = 4;
        if ( v14 )
        {
          v31 = -1;
          do
            ++v31;
          while ( v14[v31] );
          v32 = 2 * v31 + 2;
        }
        else
        {
          v14 = &Data;
          v32 = 2;
        }
        v81 = v14;
        v82 = v32;
        v83 = 0;
        v79 = &v46;
        v80 = 4;
        if ( v15 )
        {
          v33 = -1;
          do
            ++v33;
          while ( *((_BYTE *)v15 + v33) );
          v34 = v33 + 1;
        }
        else
        {
          v15 = &qword_1800A2F40;
          v34 = 1;
        }
        v76 = v15;
        v77 = v34;
        v78 = 0;
        v74 = &v39;
        v75 = 4;
        if ( v16 )
        {
          do
            ++v18;
          while ( *((_BYTE *)v16 + v18) );
          v35 = v18 + 1;
        }
        else
        {
          v16 = &qword_1800A2F40;
          v35 = 1;
        }
        v71 = v16;
        v72 = v35;
        v73 = 0;
        v69 = &v40;
        v70 = 4;
        v67 = v47;
        v68 = 8;
        v65 = &v41;
        v66 = 8;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 517;
        EventDescriptor.Keyword = 2;
        UserData.Ptr = Ptr[1];
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v62 = byte_1800B3FE1;
        v63 = 323;
        v64 = 1;
        LODWORD(SRWLock) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(Ptr[4], &EventDescriptor, (LPCGUID)(v17 + 8), 0, 0x15u, &UserData);
      }
      goto LABEL_71;
    }
  }
  else
  {
    v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 35);
  }
  if ( v5 )
  {
    v36 = v5 + 33;
    AcquireSRWLockExclusive(v36);
    v41 = 0;
    **((_DWORD **)this + 34) = 2;
    if ( v36 )
      ReleaseSRWLockExclusive(v36);
  }
  else
  {
    v47[0] = 0;
    **((_DWORD **)this + 34) = 2;
  }
  SRWLock = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&SRWLock)
    && fPending )
  {
    SRWLock = (PSRWLOCK)&qword_1800D4E78;
    qword_1800D4E80 = 0;
    byte_1800D4E88 = 0;
    dword_1800D4E8C = 0;
    qword_1800D4E78 = (__int64)&NetSetupTraceLogging::`vftable';
    CallbackContext = &`NetSetupTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_17d5a69de876e4b99dd4545a5408007a_::_lambda_invoker_cdecl_);
    qword_1800D4E80 = (__int64)CallbackContext;
    byte_1800D4E88 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_1800D4E8C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800D4E78 + 8))(&qword_1800D4E78);
    InitOnceComplete(&`NetSetupTraceLogging::Instance'::`2'::wrapper, 0, &qword_1800D4E78);
  }
  v37 = SRWLock[1].Ptr;
  if ( *(_DWORD *)v37 > 5u && (v37[2] & 2) != 0 && (v37[3] & 2LL) == v37[3] )
  {
    LODWORD(SRWLock) = GetCurrentThreadId();
    v38 = *((_QWORD *)this + 34);
    LODWORD(v40) = *(_DWORD *)(v38 + 72);
    v41 = 0;
    p_SRWLock = &SRWLock;
    v60 = 4;
    v57 = &v40;
    v58 = 4;
    v55 = &v41;
    v56 = 8;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 517;
    EventDescriptor.Keyword = 2;
    v51.Ptr = v37[1];
    v51.Size = *(unsigned __int16 *)v51.Ptr;
    v51.Reserved = 2;
    v52 = &word_1800B3F16;
    v53 = 73;
    v54 = 1;
    v39 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(v37[4], &EventDescriptor, (LPCGUID)(v38 + 8), 0, 5u, &v51);
  }
LABEL_71:
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((NetSetupTraceLogging::EvaluatePluginFilter *)((char *)this + 288));
}

```

## disassembly

```asm
0x180048de0  push    rbp
0x180048de2  push    rbx
0x180048de3  push    rsi
0x180048de4  push    rdi
0x180048de5  push    r12
0x180048de7  push    r13
0x180048de9  push    r14
0x180048deb  push    r15
0x180048ded  lea     rbp, [rsp-148h]
0x180048df5  sub     rsp, 248h
0x180048dfc  mov     [rsp+280h+var_218], 0FFFFFFFFFFFFFFFEh
0x180048e05  mov     rax, cs:__security_cookie
0x180048e0c  xor     rax, rsp
0x180048e0f  mov     [rbp+180h+var_50], rax
0x180048e16  mov     rsi, rcx
0x180048e19  xor     r14d, r14d
0x180048e1c  mov     rdi, [rcx+110h]
0x180048e23  mov     eax, [rdi+48h]
0x180048e26  test    eax, eax
0x180048e28  jns     loc_180049363
0x180048e2e  add     rdi, 50h ; 'P'
0x180048e32  cmp     eax, [rdi+8]
0x180048e35  jnz     loc_180049363
0x180048e3b  mov     rbx, [rcx+118h]
0x180048e42  test    rdi, rdi
0x180048e45  jz      loc_18004936A
0x180048e4b  test    rbx, rbx
0x180048e4e  jz      short loc_180048E95
0x180048e50  add     rbx, 108h
0x180048e57  mov     rcx, rbx; SRWLock
0x180048e5a  call    cs:__imp_AcquireSRWLockExclusive
0x180048e60  lea     rax, [rsp+280h+SRWLock]
0x180048e65  mov     [rax], r14
0x180048e68  mov     rcx, [rsp+280h+SRWLock]; SRWLock
0x180048e6d  test    rcx, rcx
0x180048e70  jz      short loc_180048E78
0x180048e72  call    cs:__imp_ReleaseSRWLockExclusive
0x180048e78  mov     rax, [rsi+110h]
0x180048e7f  mov     dword ptr [rax], 2
0x180048e85  test    rbx, rbx
0x180048e88  jz      short loc_180048EBA
0x180048e8a  mov     rcx, rbx; SRWLock
0x180048e8d  call    cs:__imp_ReleaseSRWLockExclusive
0x180048e93  jmp     short loc_180048EBA
0x180048e95  lea     rax, [rsp+280h+var_248]
0x180048e9a  mov     [rax], r14
0x180048e9d  mov     rcx, [rsp+280h+var_248]; SRWLock
0x180048ea2  test    rcx, rcx
0x180048ea5  jz      short loc_180048EAD
0x180048ea7  call    cs:__imp_ReleaseSRWLockExclusive
0x180048ead  mov     rax, [rsi+110h]
0x180048eb4  mov     dword ptr [rax], 2
0x180048eba  mov     [rsp+280h+SRWLock], r14
0x180048ebf  mov     [rsp+280h+fPending], r14d
0x180048ec4  lea     r9, [rsp+280h+SRWLock]; lpContext
0x180048ec9  lea     r8, [rsp+280h+fPending]; fPending
0x180048ece  xor     edx, edx; dwFlags
0x180048ed0  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x180048ed7  call    cs:__imp_InitOnceBeginInitialize
0x180048edd  test    eax, eax
0x180048edf  jz      loc_180048F82
0x180048ee5  cmp     [rsp+280h+fPending], r14d
0x180048eea  jz      loc_180048F82
0x180048ef0  lea     rbx, qword_1800D4E78
0x180048ef7  mov     [rsp+280h+SRWLock], rbx
0x180048efc  mov     cs:qword_1800D4E80, r14
0x180048f03  mov     cs:byte_1800D4E88, r14b
0x180048f0a  mov     cs:dword_1800D4E8C, r14d
0x180048f11  lea     rax, ??_7NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::`vftable'
0x180048f18  mov     cs:qword_1800D4E78, rax
0x180048f1f  lea     rax, ?__hInner@?1???0StaticHandle@NetSetupTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetSetupTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180048f26  mov     cs:CallbackContext, rax
0x180048f2d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_17d5a69de876e4b99dd4545a5408007a_@@CA@XZ; void (__cdecl *)()
0x180048f34  call    atexit
0x180048f39  mov     rcx, cs:CallbackContext; CallbackContext
0x180048f40  mov     cs:qword_1800D4E80, rcx
0x180048f47  mov     cs:byte_1800D4E88, 1
0x180048f4e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180048f53  mov     cs:dword_1800D4E8C, 1
0x180048f5d  mov     rax, cs:qword_1800D4E78
0x180048f64  mov     rcx, rbx
0x180048f67  mov     rax, [rax+8]
0x180048f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f70  mov     r8, rbx; lpContext
0x180048f73  xor     edx, edx; dwFlags
0x180048f75  lea     rcx, ?wrapper@?1??Instance@NetSetupTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VNetSetupTraceLogging@@@details@wil@@A; lpInitOnce
0x180048f7c  call    cs:__imp_InitOnceComplete
0x180048f82  mov     rax, [rsp+280h+SRWLock]
0x180048f87  mov     r13, [rax+8]
0x180048f8b  mov     eax, [r13+0]
0x180048f8f  cmp     eax, 5
0x180048f92  jbe     loc_1800495AB
0x180048f98  mov     rcx, [r13+18h]
0x180048f9c  mov     rax, [r13+10h]
0x180048fa0  test    al, 2
0x180048fa2  jz      loc_1800495AB
0x180048fa8  mov     rax, rcx
0x180048fab  and     eax, 2
0x180048fae  cmp     rax, rcx
0x180048fb1  jnz     loc_1800495AB
0x180048fb7  mov     rdx, [rdi+30h]
0x180048fbb  mov     eax, [rdi+44h]
0x180048fbe  mov     [rsp+280h+fPending], eax
0x180048fc2  mov     eax, [rdi+10h]
0x180048fc5  mov     [rsp+280h+var_238], eax
0x180048fc9  mov     r8, [rdi+78h]
0x180048fcd  mov     r9, [rdi+70h]
0x180048fd1  mov     eax, [rdi+68h]
0x180048fd4  mov     [rsp+280h+var_234], eax
0x180048fd8  mov     r10, [rdi+60h]
0x180048fdc  mov     r11, [rdi+58h]
0x180048fe0  mov     eax, [rdi+50h]
0x180048fe3  mov     [rsp+280h+var_230], eax
0x180048fe7  mov     rbx, [rdi+48h]
0x180048feb  mov     eax, [rdi+20h]
0x180048fee  mov     [rsp+280h+var_22C], eax
0x180048ff2  mov     r14, [rdi+18h]
0x180048ff6  mov     eax, [rdi]
0x180048ff8  mov     [rsp+280h+var_228], eax
0x180048ffc  mov     r15, [rdi+80h]
0x180049003  mov     eax, [rdi+40h]
0x180049006  mov     [rsp+280h+var_250], eax
0x18004900a  mov     r12, [rdi+38h]
0x18004900e  mov     eax, [rdi+8]
0x180049011  mov     dword ptr [rsp+280h+var_248], eax
0x180049015  mov     [rsp+280h+var_220], 1000000h
0x18004901e  mov     [rsp+280h+var_240], 0
0x180049027  mov     rdi, [rsi+110h]
0x18004902e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180049035  test    rdx, rdx
0x180049038  jz      short loc_18004904D
0x18004903a  mov     rax, rcx
0x18004903d  nop     dword ptr [rax]
0x180049040  inc     rax
0x180049043  cmp     byte ptr [rdx+rax], 0
0x180049047  jnz     short loc_180049040
0x180049049  inc     eax
0x18004904b  jmp     short loc_180049059
0x18004904d  lea     rdx, qword_1800A2F40
0x180049054  mov     eax, 1
0x180049059  mov     [rbp+180h+var_60], rdx
0x180049060  mov     [rbp+180h+var_58], eax
0x180049066  xor     edx, edx
0x180049068  mov     [rbp+180h+var_54], edx
0x18004906e  lea     rax, [rsp+280h+fPending]
0x180049073  mov     [rbp+180h+var_70], rax
0x18004907a  mov     [rbp+180h+var_68], 4
0x180049085  lea     rax, [rsp+280h+var_238]
0x18004908a  mov     [rbp+180h+var_80], rax
0x180049091  mov     [rbp+180h+var_78], 4
0x18004909c  test    r8, r8
0x18004909f  jz      short loc_1800490B8
0x1800490a1  mov     rax, rcx
0x1800490a4  lea     rax, [rax+1]
0x1800490a8  cmp     [r8+rax*2], dx
0x1800490ad  jnz     short loc_1800490A4
0x1800490af  lea     eax, ds:2[rax*2]
0x1800490b6  jmp     short loc_1800490C4
0x1800490b8  lea     r8, Data
0x1800490bf  mov     eax, 2
0x1800490c4  mov     [rbp+180h+var_90], r8
0x1800490cb  mov     [rbp+180h+var_88], eax
0x1800490d1  mov     [rbp+180h+var_84], edx
0x1800490d7  test    r9, r9
0x1800490da  jz      short loc_1800490ED
0x1800490dc  mov     rax, rcx
0x1800490df  nop
0x1800490e0  inc     rax
0x1800490e3  cmp     [r9+rax], dl
0x1800490e7  jnz     short loc_1800490E0
0x1800490e9  inc     eax
0x1800490eb  jmp     short loc_1800490F9
0x1800490ed  lea     r9, qword_1800A2F40
0x1800490f4  mov     eax, 1
0x1800490f9  mov     [rbp+180h+var_A0], r9
0x180049100  mov     [rbp+180h+var_98], eax
0x180049106  mov     [rbp+180h+var_94], edx
0x18004910c  lea     rax, [rsp+280h+var_234]
0x180049111  mov     [rbp+180h+var_B0], rax
0x180049118  mov     [rbp+180h+var_A8], 4
0x180049123  test    r10, r10
0x180049126  jz      short loc_180049144
0x180049128  mov     rax, rcx
0x18004912b  nop     dword ptr [rax+rax+00h]
0x180049130  lea     rax, [rax+1]
0x180049134  cmp     [r10+rax*2], dx
0x180049139  jnz     short loc_180049130
0x18004913b  lea     eax, ds:2[rax*2]
0x180049142  jmp     short loc_180049150
0x180049144  lea     r10, Data
0x18004914b  mov     eax, 2
0x180049150  mov     [rbp+180h+var_C0], r10
0x180049157  mov     [rbp+180h+var_B8], eax
0x18004915d  mov     [rbp+180h+var_B4], edx
0x180049163  test    r11, r11
0x180049166  jz      short loc_18004917D
0x180049168  mov     rax, rcx
0x18004916b  nop     dword ptr [rax+rax+00h]
0x180049170  inc     rax
0x180049173  cmp     [r11+rax], dl
0x180049177  jnz     short loc_180049170
0x180049179  inc     eax
0x18004917b  jmp     short loc_180049189
0x18004917d  lea     r11, qword_1800A2F40
0x180049184  mov     eax, 1
0x180049189  mov     [rbp+180h+var_D0], r11
0x180049190  mov     [rbp+180h+var_C8], eax
0x180049196  mov     [rbp+180h+var_C4], edx
0x18004919c  lea     rax, [rsp+280h+var_230]
0x1800491a1  mov     [rbp+180h+var_E0], rax
0x1800491a8  mov     [rbp+180h+var_D8], 4
0x1800491b3  test    rbx, rbx
0x1800491b6  jz      short loc_1800491CC
0x1800491b8  mov     rax, rcx
0x1800491bb  nop     dword ptr [rax+rax+00h]
0x1800491c0  inc     rax
0x1800491c3  cmp     [rbx+rax], dl
0x1800491c6  jnz     short loc_1800491C0
0x1800491c8  inc     eax
0x1800491ca  jmp     short loc_1800491D8
0x1800491cc  lea     rbx, qword_1800A2F40
0x1800491d3  mov     eax, 1
0x1800491d8  mov     [rbp+180h+var_F0], rbx
0x1800491df  mov     [rbp+180h+var_E8], eax
0x1800491e5  mov     [rbp+180h+var_E4], edx
0x1800491eb  lea     rax, [rsp+280h+var_22C]
0x1800491f0  mov     [rbp+180h+var_100], rax
0x1800491f7  mov     [rbp+180h+var_F8], 4
0x180049202  test    r14, r14
0x180049205  jz      short loc_180049224
0x180049207  mov     rax, rcx
0x18004920a  nop     word ptr [rax+rax+00h]
0x180049210  lea     rax, [rax+1]
0x180049214  cmp     [r14+rax*2], dx
0x180049219  jnz     short loc_180049210
0x18004921b  lea     eax, ds:2[rax*2]
0x180049222  jmp     short loc_180049230
0x180049224  lea     r14, Data
0x18004922b  mov     eax, 2
0x180049230  mov     [rbp+180h+var_110], r14
0x180049234  mov     [rbp+180h+var_108], eax
0x180049237  mov     [rbp+180h+var_104], edx
0x18004923a  lea     rax, [rsp+280h+var_228]
0x18004923f  mov     [rbp+180h+var_120], rax
0x180049243  mov     [rbp+180h+var_118], 4
0x18004924b  test    r15, r15
0x18004924e  jz      short loc_180049260
0x180049250  mov     rax, rcx
0x180049253  inc     rax
0x180049256  cmp     [r15+rax], dl
0x18004925a  jnz     short loc_180049253
0x18004925c  inc     eax
0x18004925e  jmp     short loc_18004926C
0x180049260  lea     r15, qword_1800A2F40
0x180049267  mov     eax, 1
0x18004926c  mov     [rbp+180h+var_130], r15
0x180049270  mov     [rbp+180h+var_128], eax
0x180049273  mov     [rbp+180h+var_124], edx
0x180049276  lea     rax, [rsp+280h+var_250]
0x18004927b  mov     [rbp+180h+var_140], rax
0x18004927f  mov     [rbp+180h+var_138], 4
0x180049287  test    r12, r12
0x18004928a  jz      short loc_18004929D
0x18004928c  nop     dword ptr [rax+00h]
0x180049290  inc     rcx
0x180049293  cmp     [r12+rcx], dl
0x180049297  jnz     short loc_180049290
0x180049299  inc     ecx
0x18004929b  jmp     short loc_1800492A9
0x18004929d  lea     r12, qword_1800A2F40
0x1800492a4  mov     ecx, 1
0x1800492a9  mov     [rbp+180h+var_150], r12
0x1800492ad  mov     [rbp+180h+var_148], ecx
0x1800492b0  mov     [rbp+180h+var_144], edx
0x1800492b3  lea     rax, [rsp+280h+var_248]
0x1800492b8  mov     [rbp+180h+var_160], rax
0x1800492bc  mov     [rbp+180h+var_158], 4
0x1800492c4  lea     rax, [rsp+280h+var_220]
0x1800492c9  mov     [rbp+180h+var_170], rax
0x1800492cd  mov     [rbp+180h+var_168], 8
0x1800492d5  lea     rax, [rsp+280h+var_240]
0x1800492da  mov     [rbp+180h+var_180], rax
0x1800492de  mov     [rbp+180h+var_178], 8
0x1800492e6  mov     dword ptr [rbp+180h+EventDescriptor.Id], 0B000000h
0x1800492ed  movzx   eax, cs:word_1800B3FD7
0x1800492f4  mov     dword ptr [rbp+180h+EventDescriptor.Level], eax
0x1800492f7  mov     [rbp+180h+EventDescriptor.Keyword], 2
0x1800492ff  mov     rax, [r13+8]
0x180049303  mov     [rbp+180h+var_1A0], rax
0x180049307  movzx   eax, word ptr [rax]
0x18004930a  mov     [rbp+180h+var_198], eax
0x18004930d  mov     [rbp+180h+var_194], 2
0x180049314  lea     rax, byte_1800B3FE1
0x18004931b  mov     [rbp+180h+var_190], rax
0x18004931f  mov     [rbp+180h+var_188], 143h
0x180049326  mov     [rbp+180h+var_184], 1
0x18004932d  lea     rax, _TraceLoggingMetadataEnd
0x180049334  lea     rdx, _TraceLoggingMetadata
0x18004933b  sub     eax, edx
0x18004933d  mov     dword ptr [rsp+280h+SRWLock], eax
  ... truncated ...
```
