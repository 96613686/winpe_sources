# CDShowTransInputPinInt::Receive(IMediaSample *)

- ea: `0x18001c0e0`
- end: `0x18001c58f`
- name: `?Receive@CDShowTransInputPinInt@@UEAAJPEAUIMediaSample@@@Z`
- size: `1199`
- prototype: `int(CDShowTransInputPinInt *__hidden this, struct IMediaSample *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800140b0`
- `0x18001c0e0`
- `0x18001c5a0`
- `0x180032a50`
- `0x18004c0d0`
- `0x180051ce4`
- `0x180053dc0`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c1d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001c1d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c285`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001c285`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c24b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c366`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c24b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c366`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c205`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c205`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c150`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c2d5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c150`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001c2d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c2aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c401`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c1bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c268`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c320`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c1bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c268`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c320`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001c136`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001c2bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001c136`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001c2bb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c382`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c470`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c540`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c382`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c470`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001c540`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDShowTransInputPinInt::Receive(CDShowTransInputPinInt *this, struct IMFSampleVtbl *a2)
{
  int v4; // r14d
  CallStackTracing *v5; // rbx
  char *v6; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbp
  __int64 v13; // rbp
  __int64 v14; // rdi
  __int64 v15; // rdi
  struct _RTL_CRITICAL_SECTION *v16; // rbp
  __int64 v17; // rbx
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v19; // rcx
  CallStackTracing *v20; // rbx
  GUID *v21; // rdi
  DWORD v22; // esi
  GUID *v23; // rax
  int v24; // eax
  int v25; // eax
  int v27; // edi
  CallStackTracing *v28; // rcx
  CallStackTracing *v29; // rax
  CallStackTracing *v30; // rcx
  __int64 v31; // rax
  CallStackTracing *v32; // rcx
  __int64 v33; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v35; // rax
  CallStackTracing *v36; // rax

  v4 = 0;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v5 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v6 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v5 + 3));
    if ( Value )
    {
      v6 = Value;
    }
    else if ( !GetLastError() )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v30 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v30 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v31 = (**(__int64 (__fastcall ***)(CallStackTracing *))v30)(v30);
      if ( v31 )
        v6 = (char *)v31;
    }
    SetLastError(LastError);
    v9 = *((unsigned int *)v6 + 497);
    if ( (unsigned int)v9 < *((_DWORD *)v6 + 498) )
    {
      v10 = 2 * v9;
      *(_QWORD *)&v6[8 * v10] = "CDShowTransInputPinInt::Receive";
      *(_DWORD *)&v6[8 * v10 + 8] = 1457;
    }
    ++*((_DWORD *)v6 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      59,
      &WPP_e67ca36682193615575df34b6326caef_Traceguids,
      (char *)this - 40,
      a2);
  v11 = *((_QWORD *)this - 3);
  if ( (*(_DWORD *)(v11 + 16) & 0xFFFFFFFD) == 0 )
  {
    CDShowTransInputPin::QueueOutputSample((RTL_SRWLOCK *)v11, a2);
    v12 = *((_QWORD *)this - 3);
    if ( *(_DWORD *)(v12 + 8) == 1 )
    {
      v13 = *(_QWORD *)(v12 + 48);
      if ( *(_DWORD *)(v13 + 88) == GetCurrentThreadId() )
        ++*(_DWORD *)(v13 + 92);
      else
        AcquireSRWLockShared((PSRWLOCK)(v13 + 80));
      v14 = *(_QWORD *)(v13 + 72);
      if ( v14 )
      {
        v15 = *(_QWORD *)(v14 + 24);
        if ( !*(_DWORD *)(v15 + 272) )
          goto LABEL_19;
        v16 = (struct _RTL_CRITICAL_SECTION *)(v15 + 104);
        EnterCriticalSection((LPCRITICAL_SECTION)(v15 + 104));
        if ( *(_DWORD *)(v15 + 152) )
        {
          v4 = -1072873851;
          v27 = -1072873851;
          LeaveCriticalSection(v16);
        }
        else
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, _QWORD, _QWORD))(**(_QWORD **)(v15 + 144) + 56LL))(
                 *(_QWORD *)(v15 + 144),
                 602,
                 &GUID_00000000_0000_0000_0000_000000000000,
                 0,
                 0);
          LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 104));
          if ( v4 >= 0 )
          {
LABEL_19:
            v17 = *(_QWORD *)(*((_QWORD *)this - 3) + 48LL);
            CurrentThreadId = GetCurrentThreadId();
            v19 = (CMFSRWLock *)(v17 + 80);
            if ( *(_DWORD *)(v17 + 88) == CurrentThreadId )
              CMFSRWLock::UnlockExclusive(v19);
            else
              ReleaseSRWLockShared((PSRWLOCK)v19);
            goto LABEL_21;
          }
          v27 = v4;
        }
        v28 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v29 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v29;
          if ( v29 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v29 + 8LL))(v29, 2032) )
          {
            v28 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v28 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v28 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v28);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v27 )
            CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransInputPinInt::Receive", 1467, v27);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            60,
            &WPP_e67ca36682193615575df34b6326caef_Traceguids,
            (char *)this - 40,
            v27);
        goto LABEL_19;
      }
    }
  }
LABEL_21:
  v20 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v21 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v22 = GetLastError();
    v23 = (GUID *)TlsGetValue(*((_DWORD *)v20 + 3));
    if ( v23 )
    {
      v21 = v23;
    }
    else if ( !GetLastError() )
    {
      v32 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v32 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v32 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v33 = (**(__int64 (__fastcall ***)(CallStackTracing *))v32)(v32);
      if ( v33 )
        v21 = (GUID *)v33;
    }
    SetLastError(v22);
    v24 = *(_DWORD *)&v21[124].Data2;
    if ( v24 )
    {
      v25 = v24 - 1;
      *(_DWORD *)&v21[124].Data2 = v25;
      if ( !v25 )
      {
        *(_DWORD *)&v21[124].Data2 = 0;
        v21[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_QWORD *)&v21[126].Data1 = 0;
        *(_DWORD *)&v21[124].Data4[4] = 0;
        *(_DWORD *)v21[126].Data4 = 0;
        v21[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c0e0  push    rbx
0x18001c0e2  push    rbp
0x18001c0e3  push    rsi
0x18001c0e4  push    rdi
0x18001c0e5  push    r12
0x18001c0e7  push    r13
0x18001c0e9  push    r14
0x18001c0eb  push    r15
0x18001c0ed  sub     rsp, 48h
0x18001c0f1  mov     r15, rdx
0x18001c0f4  mov     rsi, rcx
0x18001c0f7  xor     r12d, r12d
0x18001c0fa  mov     r14d, r12d
0x18001c0fd  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c104  jz      loc_18001C466
0x18001c10a  lea     r13, aCdshowtransinp; "CDShowTransInputPinInt::Receive"
0x18001c111  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c118  cmp     [rbx+8], r12b
0x18001c11c  jz      short loc_18001C17F
0x18001c11e  lea     rdi, [rbx+0D0h]
0x18001c125  call    cs:__imp_GetLastError
0x18001c12c  nop     dword ptr [rax+rax+00h]
0x18001c131  mov     ebp, eax
0x18001c133  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001c136  call    cs:__imp_TlsGetValue
0x18001c13d  nop     dword ptr [rax+rax+00h]
0x18001c142  test    rax, rax
0x18001c145  jz      loc_18001C3C6
0x18001c14b  mov     rdi, rax
0x18001c14e  mov     ecx, ebp; dwErrCode
0x18001c150  call    cs:__imp_SetLastError
0x18001c157  nop     dword ptr [rax+rax+00h]
0x18001c15c  mov     eax, [rdi+7C4h]
0x18001c162  cmp     eax, [rdi+7C8h]
0x18001c168  jnb     short loc_18001C179
0x18001c16a  add     rax, rax
0x18001c16d  mov     [rdi+rax*8], r13
0x18001c171  mov     dword ptr [rdi+rax*8+8], 5B1h
0x18001c179  inc     dword ptr [rdi+7C4h]
0x18001c17f  lea     rbx, [rsi-28h]
0x18001c183  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18001c18a  jnb     loc_18001C4BF
0x18001c190  mov     rcx, [rbx+10h]; this
0x18001c194  test    dword ptr [rcx+10h], 0FFFFFFFDh
0x18001c19b  jnz     loc_18001C292
0x18001c1a1  mov     rdx, r15; struct IMediaSample *
0x18001c1a4  call    ?QueueOutputSample@CDShowTransInputPin@@QEAAJPEAUIMediaSample@@@Z; CDShowTransInputPin::QueueOutputSample(IMediaSample *)
0x18001c1a9  mov     rbp, [rsi-18h]
0x18001c1ad  cmp     dword ptr [rbp+8], 1
0x18001c1b1  jnz     loc_18001C292
0x18001c1b7  mov     rbp, [rbp+30h]
0x18001c1bb  call    cs:__imp_GetCurrentThreadId
0x18001c1c2  nop     dword ptr [rax+rax+00h]
0x18001c1c7  mov     ecx, eax
0x18001c1c9  mov     eax, [rbp+58h]
0x18001c1cc  cmp     eax, ecx
0x18001c1ce  jz      loc_18001C352
0x18001c1d4  lea     rcx, [rbp+50h]; SRWLock
0x18001c1d8  call    cs:__imp_AcquireSRWLockShared
0x18001c1df  nop     dword ptr [rax+rax+00h]
0x18001c1e4  mov     rdi, [rbp+48h]
0x18001c1e8  test    rdi, rdi
0x18001c1eb  jz      loc_18001C292
0x18001c1f1  mov     rdi, [rdi+18h]
0x18001c1f5  cmp     dword ptr [rdi+110h], 0
0x18001c1fc  jz      short loc_18001C260
0x18001c1fe  lea     rbp, [rdi+68h]
0x18001c202  mov     rcx, rbp; lpCriticalSection
0x18001c205  call    cs:__imp_EnterCriticalSection
0x18001c20c  nop     dword ptr [rax+rax+00h]
0x18001c211  cmp     dword ptr [rdi+98h], 0
0x18001c218  jnz     loc_18001C35A
0x18001c21e  mov     rcx, [rdi+90h]
0x18001c225  mov     rax, [rcx]
0x18001c228  mov     [rsp+88h+var_68], r12
0x18001c22d  xor     r9d, r9d
0x18001c230  lea     r8, _GUID_00000000_0000_0000_0000_000000000000
0x18001c237  mov     edx, 25Ah
0x18001c23c  mov     rax, [rax+38h]
0x18001c240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c245  mov     r14d, eax
0x18001c248  mov     rcx, rbp; lpCriticalSection
0x18001c24b  call    cs:__imp_LeaveCriticalSection
0x18001c252  nop     dword ptr [rax+rax+00h]
0x18001c257  test    r14d, r14d
0x18001c25a  js      loc_18001C4EB
0x18001c260  mov     rax, [rsi-18h]
0x18001c264  mov     rbx, [rax+30h]
0x18001c268  call    cs:__imp_GetCurrentThreadId
0x18001c26f  nop     dword ptr [rax+rax+00h]
0x18001c274  mov     edx, eax
0x18001c276  mov     eax, [rbx+58h]
0x18001c279  lea     rcx, [rbx+50h]; this
0x18001c27d  cmp     eax, edx
0x18001c27f  jz      loc_18001C347
0x18001c285  call    cs:__imp_ReleaseSRWLockShared
0x18001c28c  nop     dword ptr [rax+rax+00h]
0x18001c291  nop
0x18001c292  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c299  cmp     byte ptr [rbx+8], 0
0x18001c29d  jz      loc_18001C332
0x18001c2a3  lea     rdi, [rbx+0D0h]
0x18001c2aa  call    cs:__imp_GetLastError
0x18001c2b1  nop     dword ptr [rax+rax+00h]
0x18001c2b6  mov     esi, eax
0x18001c2b8  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001c2bb  call    cs:__imp_TlsGetValue
0x18001c2c2  nop     dword ptr [rax+rax+00h]
0x18001c2c7  test    rax, rax
0x18001c2ca  jz      loc_18001C401
0x18001c2d0  mov     rdi, rax
0x18001c2d3  mov     ecx, esi; dwErrCode
0x18001c2d5  call    cs:__imp_SetLastError
0x18001c2dc  nop     dword ptr [rax+rax+00h]
0x18001c2e1  mov     eax, [rdi+7C4h]
0x18001c2e7  test    eax, eax
0x18001c2e9  jz      short loc_18001C332
0x18001c2eb  sub     eax, 1
0x18001c2ee  mov     [rdi+7C4h], eax
0x18001c2f4  jnz     short loc_18001C332
0x18001c2f6  mov     [rdi+7C4h], r12d
0x18001c2fd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001c304  movups  xmmword ptr [rdi+7D0h], xmm0
0x18001c30b  mov     [rdi+7E0h], r12
0x18001c312  mov     [rdi+7CCh], r12d
0x18001c319  mov     [rdi+7E8h], r12d
0x18001c320  call    cs:__imp_GetCurrentThreadId
0x18001c327  nop     dword ptr [rax+rax+00h]
0x18001c32c  mov     [rdi+7C0h], eax
0x18001c332  mov     eax, r14d
0x18001c335  add     rsp, 48h
0x18001c339  pop     r15
0x18001c33b  pop     r14
0x18001c33d  pop     r13
0x18001c33f  pop     r12
0x18001c341  pop     rdi
0x18001c342  pop     rsi
0x18001c343  pop     rbp
0x18001c344  pop     rbx
0x18001c345  retn
0x18001c347  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x18001c34c  nop
0x18001c34d  jmp     loc_18001C292
0x18001c352  inc     dword ptr [rbp+5Ch]
0x18001c355  jmp     loc_18001C1E4
0x18001c35a  mov     r14d, 0C00D3E85h
0x18001c360  mov     edi, r14d
0x18001c363  mov     rcx, rbp; lpCriticalSection
0x18001c366  call    cs:__imp_LeaveCriticalSection
0x18001c36d  nop     dword ptr [rax+rax+00h]
0x18001c372  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c379  test    rcx, rcx
0x18001c37c  jnz     loc_18001C501
0x18001c382  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c389  nop     dword ptr [rax+rax+00h]
0x18001c38e  mov     rcx, rax
0x18001c391  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c398  test    rax, rax
0x18001c39b  jz      loc_18001C4F3
0x18001c3a1  mov     rax, [rax]
0x18001c3a4  mov     edx, 7F0h
0x18001c3a9  mov     rax, [rax+8]
0x18001c3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3b2  test    eax, eax
0x18001c3b4  jz      loc_18001C4F3
0x18001c3ba  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c3c1  jmp     loc_18001C501
0x18001c3c6  call    cs:__imp_GetLastError
0x18001c3cd  nop     dword ptr [rax+rax+00h]
0x18001c3d2  test    eax, eax
0x18001c3d4  jnz     loc_18001C14E
0x18001c3da  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c3e1  test    rcx, rcx
0x18001c3e4  jz      loc_18001C470
0x18001c3ea  mov     rax, [rcx]
0x18001c3ed  mov     rax, [rax]
0x18001c3f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3f5  test    rax, rax
0x18001c3f8  cmovnz  rdi, rax
0x18001c3fc  jmp     loc_18001C14E
0x18001c401  call    cs:__imp_GetLastError
0x18001c408  nop     dword ptr [rax+rax+00h]
0x18001c40d  test    eax, eax
0x18001c40f  jnz     loc_18001C2D3
0x18001c415  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c41c  test    rcx, rcx
0x18001c41f  jz      loc_18001C540
0x18001c425  mov     rax, [rcx]
0x18001c428  mov     rax, [rax]
0x18001c42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c430  test    rax, rax
0x18001c433  cmovnz  rdi, rax
0x18001c437  jmp     loc_18001C2D3
0x18001c43c  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001c441  cmp     [rax+7CCh], edi
0x18001c447  jz      loc_18001C50B
0x18001c44d  mov     r9d, edi; int
0x18001c450  mov     r8d, 5BBh; int
0x18001c456  mov     rdx, r13; char *
0x18001c459  mov     rcx, rax; this
0x18001c45c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001c461  jmp     loc_18001C50B
0x18001c466  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001c46b  jmp     loc_18001C10A
0x18001c470  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c477  nop     dword ptr [rax+rax+00h]
0x18001c47c  mov     rcx, rax
0x18001c47f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c486  test    rax, rax
0x18001c489  jz      short loc_18001C4AC
0x18001c48b  mov     rax, [rax]
0x18001c48e  mov     edx, 7F0h
0x18001c493  mov     rax, [rax+8]
0x18001c497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c49c  test    eax, eax
0x18001c49e  jz      short loc_18001C4AC
0x18001c4a0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c4a7  jmp     loc_18001C3EA
0x18001c4ac  lea     rcx, qword_1800EB130
0x18001c4b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c4ba  jmp     loc_18001C3EA
0x18001c4bf  mov     edx, 3Bh ; ';'
0x18001c4c4  mov     [rsp+88h+var_68], r15
0x18001c4c9  mov     r9, rbx
0x18001c4cc  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x18001c4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4da  mov     rcx, [rcx+88h]
0x18001c4e1  call    WPP_SF_qq
0x18001c4e6  jmp     loc_18001C190
0x18001c4eb  mov     edi, r14d
0x18001c4ee  jmp     loc_18001C372
0x18001c4f3  lea     rcx, qword_1800EB130; this
0x18001c4fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c501  cmp     byte ptr [rcx+8], 0
0x18001c505  jnz     loc_18001C43C
0x18001c50b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001c512  jb      loc_18001C260
0x18001c518  mov     edx, 3Ch ; '<'
0x18001c51d  mov     dword ptr [rsp+88h+var_68], edi
0x18001c521  mov     r9, rbx
0x18001c524  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x18001c52b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c532  mov     rcx, [rcx+10h]
0x18001c536  call    WPP_SF_qD
0x18001c53b  jmp     loc_18001C260
0x18001c540  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001c547  nop     dword ptr [rax+rax+00h]
0x18001c54c  mov     rcx, rax
0x18001c54f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c556  test    rax, rax
0x18001c559  jz      short loc_18001C57C
0x18001c55b  mov     rax, [rax]
0x18001c55e  mov     edx, 7F0h
0x18001c563  mov     rax, [rax+8]
0x18001c567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c56c  test    eax, eax
0x18001c56e  jz      short loc_18001C57C
0x18001c570  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c577  jmp     loc_18001C425
0x18001c57c  lea     rcx, qword_1800EB130
0x18001c583  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001c58a  jmp     loc_18001C425
```
