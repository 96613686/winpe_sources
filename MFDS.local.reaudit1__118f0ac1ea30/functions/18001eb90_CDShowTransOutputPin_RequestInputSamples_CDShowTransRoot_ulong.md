# CDShowTransOutputPin::RequestInputSamples(CDShowTransRoot *,ulong)

- ea: `0x18001eb90`
- end: `0x18001f25b`
- name: `?RequestInputSamples@CDShowTransOutputPin@@QEAAJPEAVCDShowTransRoot@@K@Z`
- size: `1739`
- prototype: `__int64 __fastcall(CDShowTransOutputPin *__hidden this, struct CDShowTransRoot *, unsigned int)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18001d964`
- `0x18001e210`
- `0x18002dfcc`

## callees

- `0x1800140b0`
- `0x18001eb90`
- `0x180032a50`
- `0x180051ce4`
- `0x180053dc0`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001ebeb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001ebeb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ef31`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001ef31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed5d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ed95`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed22`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ed22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ec4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ec4c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ee42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f01c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f01c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ebd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ebd0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ee91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ef16`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ec31`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ee27`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ec31`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ee27`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f160`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f20c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f160`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f20c`
- `MFPlat!MFCreateMediaEvent` at `0x18001ecd3`
- `MFPlat!MFCreateMediaEvent` at `0x18001ecd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDShowTransOutputPin::RequestInputSamples(
        CDShowTransOutputPin *this,
        struct CDShowTransRoot *a2,
        unsigned int a3)
{
  __int64 v5; // rdi
  struct CDShowTransRoot *v6; // rsi
  CallStackTracing *v7; // rdi
  char *v8; // rbx
  DWORD LastError; // r14d
  char *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned int i; // ebx
  __int64 v14; // rdi
  int v15; // r14d
  __int64 v16; // rcx
  CallStackTracing *v17; // rdi
  GUID *v18; // rbx
  DWORD v19; // r14d
  GUID *v20; // rax
  int v21; // eax
  int v22; // eax
  __int64 v24; // rbx
  DWORD CurrentThreadId; // eax
  CMFSRWLock *v26; // rcx
  __int64 v27; // rdx
  CallStackTracing *v28; // rcx
  __int64 v29; // rax
  CallStackTracing *v30; // rcx
  __int64 v31; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  struct CallStackContext *v34; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v36; // rax
  CallStackTracing *v37; // rax
  IMFMediaEvent *v38; // [rsp+30h] [rbp-20h]
  HRESULT v40; // [rsp+A0h] [rbp+50h]
  IMFMediaEvent *ppEvent; // [rsp+A8h] [rbp+58h] BYREF

  v40 = 0;
  if ( a2 )
  {
    v6 = a2;
  }
  else if ( *((_DWORD *)this + 2) == 1 )
  {
    v5 = *((_QWORD *)this + 6);
    if ( *(_DWORD *)(v5 + 88) == GetCurrentThreadId() )
      ++*(_DWORD *)(v5 + 92);
    else
      AcquireSRWLockShared((PSRWLOCK)(v5 + 80));
    v6 = *(struct CDShowTransRoot **)(v5 + 72);
  }
  else
  {
    v6 = 0;
  }
  v7 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v7 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v7 + 8) )
  {
    v8 = (char *)v7 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v7 + 3));
    if ( Value )
    {
      v8 = Value;
    }
    else if ( !GetLastError() )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v28 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v29 = (**(__int64 (__fastcall ***)(CallStackTracing *))v28)(v28);
      if ( v29 )
        v8 = (char *)v29;
    }
    SetLastError(LastError);
    v11 = *((unsigned int *)v8 + 497);
    if ( (unsigned int)v11 < *((_DWORD *)v8 + 498) )
    {
      v12 = 2 * v11;
      *(_QWORD *)&v8[8 * v12] = "CDShowTransOutputPin::RequestInputSamples";
      *(_DWORD *)&v8[8 * v12 + 8] = 1307;
    }
    ++*((_DWORD *)v8 + 497);
  }
  for ( i = 0; i < a3; ++i )
  {
    if ( !v6 )
      goto LABEL_37;
    ppEvent = 0;
    if ( !*(_DWORD *)(*((_QWORD *)v6 + 3) + 272LL) )
    {
      v40 = -1072873854;
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072873854 )
          CallStackContext::TraceFailure(
            ThreadRelativeContext,
            "CDShowTransOutputPin::RequestInputSamples",
            1334,
            -1072873854);
      }
      if ( g_wppLevels )
      {
        v27 = 46;
        goto LABEL_59;
      }
LABEL_49:
      if ( ppEvent )
        ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
      goto LABEL_51;
    }
    v40 = MFCreateMediaEvent(0x259u, &GUID_00000000_0000_0000_0000_000000000000, 0, 0, &ppEvent);
    if ( v40 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v34 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v40 < 0 && *((_DWORD *)v34 + 499) != v40 )
          CallStackContext::TraceFailure(v34, "CDShowTransOutputPin::RequestInputSamples", 1325, v40);
      }
      if ( !g_wppLevels )
        goto LABEL_49;
      v27 = 43;
LABEL_59:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this, v40);
      goto LABEL_49;
    }
    v40 = ((__int64 (__fastcall *)(IMFMediaEvent *, const GUID *, _QWORD))ppEvent->lpVtbl->SetUINT32)(
            ppEvent,
            &MF_EVENT_MFT_INPUT_STREAM_ID,
            0);
    if ( v40 < 0 )
    {
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v40 < 0 && *((_DWORD *)v33 + 499) != v40 )
          CallStackContext::TraceFailure(v33, "CDShowTransOutputPin::RequestInputSamples", 1327, v40);
      }
      if ( !g_wppLevels )
        goto LABEL_49;
      v27 = 44;
      goto LABEL_59;
    }
    v14 = *((_QWORD *)v6 + 3);
    v38 = ppEvent;
    EnterCriticalSection((LPCRITICAL_SECTION)(v14 + 104));
    if ( *(_DWORD *)(v14 + 152) )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 104));
      v40 = -1072873851;
LABEL_28:
      if ( !CallStackTracing::s_wpInstance )
        CallStackTracing::InitInstance();
      if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
        if ( v40 < 0 && *((_DWORD *)v32 + 499) != v40 )
          CallStackContext::TraceFailure(v32, "CDShowTransOutputPin::RequestInputSamples", 1329, v40);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_e67ca36682193615575df34b6326caef_Traceguids, this, v40);
      if ( ppEvent )
        ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
      goto LABEL_51;
    }
    v15 = 0;
    v16 = *(_QWORD *)(v14 + 144);
    if ( v16 )
      v15 = (*(__int64 (__fastcall **)(__int64, IMFMediaEvent *))(*(_QWORD *)v16 + 48LL))(v16, v38);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 104));
    v40 = v15;
    if ( v15 < 0 )
      goto LABEL_28;
    if ( ppEvent )
      ((void (__fastcall *)(IMFMediaEvent *))ppEvent->lpVtbl->Release)(ppEvent);
  }
  if ( !v6 )
    goto LABEL_37;
LABEL_51:
  if ( !a2 )
  {
    v24 = *((_QWORD *)this + 6);
    CurrentThreadId = GetCurrentThreadId();
    v26 = (CMFSRWLock *)(v24 + 80);
    if ( *(_DWORD *)(v24 + 88) == CurrentThreadId )
      CMFSRWLock::UnlockExclusive(v26);
    else
      ReleaseSRWLockShared((PSRWLOCK)v26);
  }
LABEL_37:
  v17 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v18 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v19 = GetLastError();
    v20 = (GUID *)TlsGetValue(*((_DWORD *)v17 + 3));
    if ( v20 )
    {
      v18 = v20;
    }
    else if ( !GetLastError() )
    {
      v30 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v37 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v37;
        if ( v37 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v37 + 8LL))(v37, 2032) )
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
        v18 = (GUID *)v31;
    }
    SetLastError(v19);
    v21 = *(_DWORD *)&v18[124].Data2;
    if ( v21 )
    {
      v22 = v21 - 1;
      *(_DWORD *)&v18[124].Data2 = v22;
      if ( !v22 )
      {
        *(_DWORD *)&v18[124].Data2 = 0;
        v18[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_QWORD *)&v18[126].Data1 = 0;
        *(_DWORD *)&v18[124].Data4[4] = 0;
        *(_DWORD *)v18[126].Data4 = 0;
        v18[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v40;
}

```

## disassembly

```asm
0x18001eb90  mov     [rsp-38h+arg_0], rbx
0x18001eb95  mov     [rsp-38h+arg_8], rdx
0x18001eb9a  push    rbp
0x18001eb9b  push    rsi
0x18001eb9c  push    rdi
0x18001eb9d  push    r12
0x18001eb9f  push    r13
0x18001eba1  push    r14
0x18001eba3  push    r15
0x18001eba5  mov     rbp, rsp
0x18001eba8  sub     rsp, 50h
0x18001ebac  mov     r15d, r8d
0x18001ebaf  mov     r13, rcx
0x18001ebb2  xor     r12d, r12d
0x18001ebb5  mov     [rbp+arg_10], r12d
0x18001ebb9  test    rdx, rdx
0x18001ebbc  jnz     loc_18001EEBE
0x18001ebc2  cmp     dword ptr [rcx+8], 1
0x18001ebc6  jnz     loc_18001F147
0x18001ebcc  mov     rdi, [rcx+30h]
0x18001ebd0  call    cs:__imp_GetCurrentThreadId
0x18001ebd7  nop     dword ptr [rax+rax+00h]
0x18001ebdc  mov     ecx, [rdi+58h]
0x18001ebdf  cmp     ecx, eax
0x18001ebe1  jz      loc_18001EFCF
0x18001ebe7  lea     rcx, [rdi+50h]; SRWLock
0x18001ebeb  call    cs:__imp_AcquireSRWLockShared
0x18001ebf2  nop     dword ptr [rax+rax+00h]
0x18001ebf7  mov     rsi, [rdi+48h]
0x18001ebfb  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ec02  test    rdi, rdi
0x18001ec05  jz      loc_18001F14F
0x18001ec0b  lea     r14, aCdshowtransout_2; "CDShowTransOutputPin::RequestInputSampl"...
0x18001ec12  cmp     [rdi+8], r12b
0x18001ec16  jz      short loc_18001EC82
0x18001ec18  lea     rbx, [rdi+0D0h]
0x18001ec1f  call    cs:__imp_GetLastError
0x18001ec26  nop     dword ptr [rax+rax+00h]
0x18001ec2b  mov     r14d, eax
0x18001ec2e  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18001ec31  call    cs:__imp_TlsGetValue
0x18001ec38  nop     dword ptr [rax+rax+00h]
0x18001ec3d  test    rax, rax
0x18001ec40  jz      loc_18001EFE1
0x18001ec46  mov     rbx, rax
0x18001ec49  mov     ecx, r14d; dwErrCode
0x18001ec4c  call    cs:__imp_SetLastError
0x18001ec53  nop     dword ptr [rax+rax+00h]
0x18001ec58  lea     r14, aCdshowtransout_2; "CDShowTransOutputPin::RequestInputSampl"...
0x18001ec5f  mov     eax, [rbx+7C4h]
0x18001ec65  cmp     eax, [rbx+7C8h]
0x18001ec6b  jnb     short loc_18001EC7C
0x18001ec6d  add     rax, rax
0x18001ec70  mov     [rbx+rax*8], r14
0x18001ec74  mov     dword ptr [rbx+rax*8+8], 51Bh
0x18001ec7c  inc     dword ptr [rbx+7C4h]
0x18001ec82  mov     [rbp+var_18], r12
0x18001ec86  lea     rax, [rbp+arg_10]
0x18001ec8a  mov     [rbp+var_10], rax
0x18001ec8e  mov     ebx, r12d
0x18001ec91  cmp     ebx, r15d
0x18001ec94  jnb     loc_18001EDF1
0x18001ec9a  test    rsi, rsi
0x18001ec9d  jz      loc_18001EDFA
0x18001eca3  mov     [rbp+arg_18], r12
0x18001eca7  mov     rax, [rsi+18h]
0x18001ecab  cmp     dword ptr [rax+110h], 0
0x18001ecb2  jz      loc_18001EF42
0x18001ecb8  lea     rax, [rbp+arg_18]
0x18001ecbc  mov     [rsp+50h+ppEvent], rax; ppEvent
0x18001ecc1  xor     r9d, r9d; pvValue
0x18001ecc4  xor     r8d, r8d; hrStatus
0x18001ecc7  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; guidExtendedType
0x18001ecce  mov     ecx, 259h; met
0x18001ecd3  call    cs:__imp_MFCreateMediaEvent
0x18001ecda  nop     dword ptr [rax+rax+00h]
0x18001ecdf  mov     [rbp+arg_10], eax
0x18001ece2  test    eax, eax
0x18001ece4  js      loc_18001EEC6
0x18001ecea  mov     rcx, [rbp+arg_18]
0x18001ecee  mov     rax, [rcx]
0x18001ecf1  xor     r8d, r8d
0x18001ecf4  lea     rdx, MF_EVENT_MFT_INPUT_STREAM_ID
0x18001ecfb  mov     rax, [rax+0A8h]
0x18001ed02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed07  mov     [rbp+arg_10], eax
0x18001ed0a  test    eax, eax
0x18001ed0c  js      loc_18001EF9C
0x18001ed12  mov     rdi, [rsi+18h]
0x18001ed16  mov     rax, [rbp+arg_18]
0x18001ed1a  mov     [rbp+var_20], rax
0x18001ed1e  lea     rcx, [rdi+68h]; lpCriticalSection
0x18001ed22  call    cs:__imp_EnterCriticalSection
0x18001ed29  nop     dword ptr [rax+rax+00h]
0x18001ed2e  cmp     dword ptr [rdi+98h], 0
0x18001ed35  jnz     short loc_18001ED91
0x18001ed37  xor     r14d, r14d
0x18001ed3a  mov     rcx, [rdi+90h]
0x18001ed41  test    rcx, rcx
0x18001ed44  jz      short loc_18001ED59
0x18001ed46  mov     rax, [rcx]
0x18001ed49  mov     rdx, [rbp+var_20]
0x18001ed4d  mov     rax, [rax+30h]
0x18001ed51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed56  mov     r14d, eax
0x18001ed59  lea     rcx, [rdi+68h]; lpCriticalSection
0x18001ed5d  call    cs:__imp_LeaveCriticalSection
0x18001ed64  nop     dword ptr [rax+rax+00h]
0x18001ed69  mov     [rbp+arg_10], r14d
0x18001ed6d  test    r14d, r14d
0x18001ed70  js      short loc_18001EDA8
0x18001ed72  mov     rcx, [rbp+arg_18]
0x18001ed76  test    rcx, rcx
0x18001ed79  jz      short loc_18001ED87
0x18001ed7b  mov     rax, [rcx]
0x18001ed7e  mov     rax, [rax+10h]
0x18001ed82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed87  inc     ebx
0x18001ed89  xor     r12d, r12d
0x18001ed8c  jmp     loc_18001EC91
0x18001ed91  lea     rcx, [rdi+68h]; lpCriticalSection
0x18001ed95  call    cs:__imp_LeaveCriticalSection
0x18001ed9c  nop     dword ptr [rax+rax+00h]
0x18001eda1  mov     [rbp+arg_10], 0C00D3E85h
0x18001eda8  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001edb0  jz      loc_18001F1AF
0x18001edb6  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001edbd  cmp     byte ptr [rdi+8], 0
0x18001edc1  jnz     loc_18001F057
0x18001edc7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001edce  jnb     loc_18001F1B9
0x18001edd4  mov     rcx, [rbp+arg_18]
0x18001edd8  test    rcx, rcx
0x18001eddb  jz      short loc_18001EDE9
0x18001eddd  mov     rax, [rcx]
0x18001ede0  mov     rax, [rax+10h]
0x18001ede4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ede9  xor     r12d, r12d
0x18001edec  jmp     loc_18001EF07
0x18001edf1  test    rsi, rsi
0x18001edf4  jnz     loc_18001EF07
0x18001edfa  mov     esi, [rbp+arg_10]
0x18001edfd  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ee04  cmp     byte ptr [rdi+8], 0
0x18001ee08  jz      loc_18001EEA3
0x18001ee0e  lea     rbx, [rdi+0D0h]
0x18001ee15  call    cs:__imp_GetLastError
0x18001ee1c  nop     dword ptr [rax+rax+00h]
0x18001ee21  mov     r14d, eax
0x18001ee24  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18001ee27  call    cs:__imp_TlsGetValue
0x18001ee2e  nop     dword ptr [rax+rax+00h]
0x18001ee33  test    rax, rax
0x18001ee36  jz      loc_18001F01C
0x18001ee3c  mov     rbx, rax
0x18001ee3f  mov     ecx, r14d; dwErrCode
0x18001ee42  call    cs:__imp_SetLastError
0x18001ee49  nop     dword ptr [rax+rax+00h]
0x18001ee4e  mov     eax, [rbx+7C4h]
0x18001ee54  test    eax, eax
0x18001ee56  jz      short loc_18001EEA3
0x18001ee58  sub     eax, 1
0x18001ee5b  mov     [rbx+7C4h], eax
0x18001ee61  jnz     short loc_18001EEA3
0x18001ee63  mov     [rbx+7C4h], r12d
0x18001ee6a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001ee71  movups  xmmword ptr [rbx+7D0h], xmm0
0x18001ee78  mov     qword ptr [rbx+7E0h], 0
0x18001ee83  mov     [rbx+7CCh], r12d
0x18001ee8a  mov     [rbx+7E8h], r12d
0x18001ee91  call    cs:__imp_GetCurrentThreadId
0x18001ee98  nop     dword ptr [rax+rax+00h]
0x18001ee9d  mov     [rbx+7C0h], eax
0x18001eea3  mov     eax, esi
0x18001eea5  mov     rbx, [rsp+50h+arg_0]
0x18001eead  add     rsp, 50h
0x18001eeb1  pop     r15
0x18001eeb3  pop     r14
0x18001eeb5  pop     r13
0x18001eeb7  pop     r12
0x18001eeb9  pop     rdi
0x18001eeba  pop     rsi
0x18001eebb  pop     rbp
0x18001eebc  retn
0x18001eebe  mov     rsi, rdx
0x18001eec1  jmp     loc_18001EBFB
0x18001eec6  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eece  jz      loc_18001F1EE
0x18001eed4  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001eedb  cmp     byte ptr [rdi+8], 0
0x18001eedf  jnz     loc_18001F0CF
0x18001eee5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001eeec  jnb     loc_18001F1F8
0x18001eef2  mov     rcx, [rbp+arg_18]
0x18001eef6  test    rcx, rcx
0x18001eef9  jz      short loc_18001EF07
0x18001eefb  mov     rax, [rcx]
0x18001eefe  mov     rax, [rax+10h]
0x18001ef02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef07  cmp     [rbp+arg_8], 0
0x18001ef0c  jnz     loc_18001EDFA
0x18001ef12  mov     rbx, [r13+30h]
0x18001ef16  call    cs:__imp_GetCurrentThreadId
0x18001ef1d  nop     dword ptr [rax+rax+00h]
0x18001ef22  mov     edx, [rbx+58h]
0x18001ef25  lea     rcx, [rbx+50h]; this
0x18001ef29  cmp     edx, eax
0x18001ef2b  jz      loc_18001EFD7
0x18001ef31  call    cs:__imp_ReleaseSRWLockShared
0x18001ef38  nop     dword ptr [rax+rax+00h]
0x18001ef3d  jmp     loc_18001EDFA
0x18001ef42  mov     [rbp+arg_10], 0C00D3E82h
0x18001ef49  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ef51  jz      loc_18001F202
0x18001ef57  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ef5e  cmp     byte ptr [rdi+8], 0
0x18001ef62  jnz     loc_18001F10B
0x18001ef68  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ef6f  jb      short loc_18001EEF2
0x18001ef71  mov     edx, 2Eh ; '.'
0x18001ef76  mov     eax, [rbp+arg_10]
0x18001ef79  mov     dword ptr [rsp+50h+ppEvent], eax
0x18001ef7d  mov     r9, r13
0x18001ef80  lea     r8, WPP_e67ca36682193615575df34b6326caef_Traceguids
0x18001ef87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef8e  mov     rcx, [rcx+10h]
0x18001ef92  call    WPP_SF_qD
0x18001ef97  jmp     loc_18001EEF2
0x18001ef9c  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001efa4  jz      loc_18001F1E4
0x18001efaa  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001efb1  cmp     byte ptr [rdi+8], 0
0x18001efb5  jnz     loc_18001F093
0x18001efbb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001efc2  jb      loc_18001EEF2
0x18001efc8  mov     edx, 2Ch ; ','
0x18001efcd  jmp     short loc_18001EF76
0x18001efcf  inc     dword ptr [rdi+5Ch]
0x18001efd2  jmp     loc_18001EBF7
0x18001efd7  call    ?UnlockExclusive@CMFSRWLock@@QEAAXXZ; CMFSRWLock::UnlockExclusive(void)
0x18001efdc  jmp     loc_18001EDFA
0x18001efe1  call    cs:__imp_GetLastError
0x18001efe8  nop     dword ptr [rax+rax+00h]
0x18001efed  test    eax, eax
0x18001efef  jnz     loc_18001EC49
0x18001eff5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001effc  test    rcx, rcx
0x18001efff  jz      loc_18001F160
0x18001f005  mov     rax, [rcx]
0x18001f008  mov     rax, [rax]
0x18001f00b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f010  test    rax, rax
0x18001f013  cmovnz  rbx, rax
0x18001f017  jmp     loc_18001EC49
0x18001f01c  call    cs:__imp_GetLastError
0x18001f023  nop     dword ptr [rax+rax+00h]
0x18001f028  test    eax, eax
0x18001f02a  jnz     loc_18001EE3F
0x18001f030  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f037  test    rcx, rcx
0x18001f03a  jz      loc_18001F20C
0x18001f040  mov     rax, [rcx]
0x18001f043  mov     rax, [rax]
0x18001f046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f04b  test    rax, rax
0x18001f04e  cmovnz  rbx, rax
0x18001f052  jmp     loc_18001EE3F
0x18001f057  mov     rcx, rdi; this
0x18001f05a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001f05f  mov     r9d, [rbp+arg_10]; int
0x18001f063  test    r9d, r9d
0x18001f066  jns     loc_18001EDC7
0x18001f06c  cmp     [rax+7CCh], r9d
0x18001f073  jz      loc_18001EDC7
0x18001f079  mov     r8d, 531h; int
0x18001f07f  lea     rdx, aCdshowtransout_2; "CDShowTransOutputPin::RequestInputSampl"...
0x18001f086  mov     rcx, rax; this
0x18001f089  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001f08e  jmp     loc_18001EDC7
0x18001f093  mov     rcx, rdi; this
0x18001f096  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001f09b  mov     r9d, [rbp+arg_10]; int
0x18001f09f  test    r9d, r9d
0x18001f0a2  jns     loc_18001EFBB
0x18001f0a8  cmp     [rax+7CCh], r9d
0x18001f0af  jz      loc_18001EFBB
0x18001f0b5  mov     r8d, 52Fh; int
0x18001f0bb  lea     rdx, aCdshowtransout_2; "CDShowTransOutputPin::RequestInputSampl"...
0x18001f0c2  mov     rcx, rax; this
0x18001f0c5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001f0ca  jmp     loc_18001EFBB
0x18001f0cf  mov     rcx, rdi; this
0x18001f0d2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001f0d7  mov     r9d, [rbp+arg_10]; int
0x18001f0db  test    r9d, r9d
0x18001f0de  jns     loc_18001EEE5
0x18001f0e4  cmp     [rax+7CCh], r9d
0x18001f0eb  jz      loc_18001EEE5
0x18001f0f1  mov     r8d, 52Dh; int
0x18001f0f7  lea     rdx, aCdshowtransout_2; "CDShowTransOutputPin::RequestInputSampl"...
  ... truncated ...
```
