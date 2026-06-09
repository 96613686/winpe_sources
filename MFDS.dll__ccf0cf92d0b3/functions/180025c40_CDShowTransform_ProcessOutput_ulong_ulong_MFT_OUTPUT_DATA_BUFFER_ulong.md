# CDShowTransform::ProcessOutput(ulong,ulong,_MFT_OUTPUT_DATA_BUFFER *,ulong *)

- ea: `0x180025c40`
- end: `0x180026143`
- name: `?ProcessOutput@CDShowTransform@@UEAAJKKPEAU_MFT_OUTPUT_DATA_BUFFER@@PEAK@Z`
- size: `1283`
- prototype: `__int64 __fastcall(CDShowTransform *__hidden this, unsigned int, unsigned int, struct _MFT_OUTPUT_DATA_BUFFER *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180025c40`
- `0x180026208`
- `0x180026288`
- `0x180051550`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025d33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025edf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025f2f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025d33`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025edf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180025f2f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025d47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025ef3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025f3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025d47`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025ef3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180025f3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025e1b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025fa3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025fa3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025f54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025f54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025c66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025cc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025dbb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025cc6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180025dbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025d8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e06`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025cac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025da0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025cac`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180025da0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800260a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800260f3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800260a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800260f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDShowTransform::ProcessOutput(
        CDShowTransform *this,
        __int64 a2,
        __int64 a3,
        struct _MFT_OUTPUT_DATA_BUFFER *a4)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  CallStackTracing *v7; // rsi
  char *v8; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned int v13; // r14d
  RTL_SRWLOCK *v14; // rbp
  PVOID Ptr; // rsi
  unsigned int v16; // ebp
  CallStackTracing *v17; // rdi
  GUID *v18; // rsi
  DWORD v19; // r14d
  GUID *v20; // rax
  int v21; // eax
  int v22; // eax
  CallStackTracing *v24; // rcx
  __int64 v25; // rax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  RTL_SRWLOCK *v28; // rbp
  PVOID v29; // rsi
  RTL_SRWLOCK *v30; // rsi
  PVOID *v31; // rdx
  IMFSample *v32; // rbp
  _QWORD *v33; // rax
  __int64 v35; // rdx
  struct _MFT_OUTPUT_DATA_BUFFER *v36; // rsi
  IMFSample *pSample; // rcx
  CallStackTracing *v38; // rax
  CallStackTracing *v39; // rax
  int v40; // [rsp+20h] [rbp-78h] BYREF
  char *v41; // [rsp+28h] [rbp-70h]
  RTL_SRWLOCK *v42; // [rsp+30h] [rbp-68h]
  __int64 v43; // [rsp+38h] [rbp-60h]
  unsigned int *v44; // [rsp+40h] [rbp-58h]
  unsigned int v45; // [rsp+A0h] [rbp+8h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 232);
  v41 = (char *)this + 232;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  v45 = 0;
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
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v38;
        if ( v38 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v25 = (**(__int64 (__fastcall ***)(CallStackTracing *))v24)(v24);
      if ( v25 )
        v8 = (char *)v25;
    }
    SetLastError(LastError);
    v11 = *((unsigned int *)v8 + 497);
    if ( (unsigned int)v11 < *((_DWORD *)v8 + 498) )
    {
      v12 = 2 * v11;
      *(_QWORD *)&v8[8 * v12] = "CDShowTransform::ProcessOutput";
      *(_DWORD *)&v8[8 * v12 + 8] = 560;
    }
    ++*((_DWORD *)v8 + 497);
  }
  v43 = 0;
  v44 = &v45;
  v13 = 0;
  while ( (unsigned __int64)v13 < *((_QWORD *)this + 25) )
  {
    _mm_lfence();
    v14 = *(RTL_SRWLOCK **)(*(_QWORD *)(*((_QWORD *)this + 24) + 8LL * v13) + 56LL);
    AcquireSRWLockShared(v14 + 11);
    Ptr = v14[14].Ptr;
    ReleaseSRWLockShared(v14 + 11);
    if ( !Ptr )
    {
      a4[v13].dwStatus |= 0x300u;
      goto LABEL_13;
    }
    if ( (unsigned __int64)v13 >= *((_QWORD *)this + 25) )
      goto LABEL_22;
    _mm_lfence();
    v28 = *(RTL_SRWLOCK **)(*(_QWORD *)(*((_QWORD *)this + 24) + 8LL * v13) + 56LL);
    AcquireSRWLockShared(v28 + 11);
    v29 = v28[14].Ptr;
    ReleaseSRWLockShared(v28 + 11);
    if ( v29 )
    {
      if ( (unsigned __int64)v13 >= *((_QWORD *)this + 25) )
        goto LABEL_22;
      _mm_lfence();
      v30 = (RTL_SRWLOCK *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 24) + 8LL * v13) + 56LL) + 88LL);
      AcquireSRWLockShared(v30);
      ReleaseSRWLockShared(v30);
      v42 = v30;
      AcquireSRWLockExclusive(v30);
      v31 = (PVOID *)v30[1].Ptr;
      if ( !v31 )
        ATL::AtlThrowImpl(-2147467259);
      v32 = (IMFSample *)v31[2];
      v33 = *v31;
      v30[1].Ptr = *v31;
      if ( v33 )
        v33[1] = 0;
      else
        v30[2].Ptr = 0;
      *v31 = v30[5].Ptr;
      v30[5].Ptr = v31;
      if ( v30[3].Ptr-- == (PVOID)1 )
        ATL::CAtlList<IMFSample *,ATL::CElementTraits<IMFSample *>>::RemoveAll();
      ReleaseSRWLockExclusive(v30);
      v35 = v13;
      a4[v35].pSample = v32;
      v45 = 0;
    }
    else
    {
      v35 = v13;
    }
    if ( (unsigned __int64)v13 >= *((_QWORD *)this + 25) )
LABEL_22:
      ATL::AtlThrowImpl(-2147024809);
    if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 24) + 8LL * v13) + 56LL) + 12LL) != 2 )
      goto LABEL_13;
    v40 = 0;
    v36 = &a4[v35];
    if ( ((int (__fastcall *)(IMFSample *, __int64 *, int *))a4[v35].pSample->lpVtbl->GetUINT32)(
           a4[v35].pSample,
           MFSampleExtension_EOS,
           &v40) < 0
      || !v40 )
    {
      goto LABEL_13;
    }
    if ( (unsigned __int64)v13 >= *((_QWORD *)this + 25) )
      ATL::AtlThrowImpl(-2147024809);
    CDShowTransPin::PostDrainCompleteMsg(*(CDShowTransPin **)(*(_QWORD *)(*((_QWORD *)this + 24) + 8LL * v13) + 56LL));
    v36->dwStatus |= 0x300u;
    pSample = v36->pSample;
    if ( pSample )
    {
      ((void (__fastcall *)(IMFSample *))pSample->lpVtbl->Release)(pSample);
      v36->pSample = 0;
      ++v13;
    }
    else
    {
LABEL_13:
      ++v13;
    }
  }
  v16 = v45;
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
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v39;
        if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
      if ( v27 )
        v18 = (GUID *)v27;
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
  LeaveCriticalSection(v6);
  return v16;
}

```

## disassembly

```asm
0x180025c40  push    rbx
0x180025c42  push    rbp
0x180025c43  push    rsi
0x180025c44  push    rdi
0x180025c45  push    r12
0x180025c47  push    r13
0x180025c49  push    r14
0x180025c4b  push    r15
0x180025c4d  sub     rsp, 58h
0x180025c51  mov     r12, r9
0x180025c54  mov     r15, rcx
0x180025c57  lea     rbx, [rcx+0E8h]
0x180025c5e  mov     [rsp+98h+var_70], rbx
0x180025c63  mov     rcx, rbx; lpCriticalSection
0x180025c66  call    cs:__imp_EnterCriticalSection
0x180025c6d  nop     dword ptr [rax+rax+00h]
0x180025c72  nop
0x180025c73  xor     r13d, r13d
0x180025c76  mov     [rsp+98h+arg_0], r13d
0x180025c7e  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180025c85  test    rsi, rsi
0x180025c88  jz      loc_180026093
0x180025c8e  cmp     [rsi+8], r13b
0x180025c92  jz      short loc_180025CFC
0x180025c94  lea     rdi, [rsi+0D0h]
0x180025c9b  call    cs:__imp_GetLastError
0x180025ca2  nop     dword ptr [rax+rax+00h]
0x180025ca7  mov     ebp, eax
0x180025ca9  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180025cac  call    cs:__imp_TlsGetValue
0x180025cb3  nop     dword ptr [rax+rax+00h]
0x180025cb8  test    rax, rax
0x180025cbb  jz      loc_180025E53
0x180025cc1  mov     rdi, rax
0x180025cc4  mov     ecx, ebp; dwErrCode
0x180025cc6  call    cs:__imp_SetLastError
0x180025ccd  nop     dword ptr [rax+rax+00h]
0x180025cd2  mov     eax, [rdi+7C4h]
0x180025cd8  cmp     eax, [rdi+7C8h]
0x180025cde  jnb     short loc_180025CF6
0x180025ce0  add     rax, rax
0x180025ce3  lea     rcx, aCdshowtransfor_7
0x180025cea  mov     [rdi+rax*8], rcx
0x180025cee  mov     dword ptr [rdi+rax*8+8], 230h
0x180025cf6  inc     dword ptr [rdi+7C4h]
0x180025cfc  mov     [rsp+98h+var_60], r13
0x180025d01  lea     rax, [rsp+98h+arg_0]
0x180025d09  mov     [rsp+98h+var_58], rax
0x180025d0e  mov     r14d, r13d
0x180025d11  mov     edi, r14d
0x180025d14  cmp     rdi, [r15+0C8h]
0x180025d1b  jnb     short loc_180025D6F
0x180025d1d  lfence
0x180025d20  mov     rax, [r15+0C0h]
0x180025d27  mov     rcx, [rax+rdi*8]
0x180025d2b  mov     rbp, [rcx+38h]
0x180025d2f  lea     rcx, [rbp+58h]; SRWLock
0x180025d33  call    cs:__imp_AcquireSRWLockShared
0x180025d3a  nop     dword ptr [rax+rax+00h]
0x180025d3f  mov     rsi, [rbp+70h]
0x180025d43  lea     rcx, [rbp+58h]; SRWLock
0x180025d47  call    cs:__imp_ReleaseSRWLockShared
0x180025d4e  nop     dword ptr [rax+rax+00h]
0x180025d53  nop
0x180025d54  test    rsi, rsi
0x180025d57  jnz     loc_180025E3B
0x180025d5d  shl     rdi, 5
0x180025d61  or      dword ptr [rdi+r12+10h], 300h
0x180025d6a  inc     r14d
0x180025d6d  jmp     short loc_180025D11
0x180025d6f  mov     ebp, [rsp+98h+arg_0]
0x180025d76  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180025d7d  cmp     byte ptr [rdi+8], 0
0x180025d81  jz      loc_180025E18
0x180025d87  lea     rsi, [rdi+0D0h]
0x180025d8e  call    cs:__imp_GetLastError
0x180025d95  nop     dword ptr [rax+rax+00h]
0x180025d9a  mov     r14d, eax
0x180025d9d  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180025da0  call    cs:__imp_TlsGetValue
0x180025da7  nop     dword ptr [rax+rax+00h]
0x180025dac  test    rax, rax
0x180025daf  jz      loc_180025E8E
0x180025db5  mov     rsi, rax
0x180025db8  mov     ecx, r14d; dwErrCode
0x180025dbb  call    cs:__imp_SetLastError
0x180025dc2  nop     dword ptr [rax+rax+00h]
0x180025dc7  mov     eax, [rsi+7C4h]
0x180025dcd  test    eax, eax
0x180025dcf  jz      short loc_180025E18
0x180025dd1  sub     eax, 1
0x180025dd4  mov     [rsi+7C4h], eax
0x180025dda  jnz     short loc_180025E18
0x180025ddc  mov     [rsi+7C4h], r13d
0x180025de3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180025dea  movups  xmmword ptr [rsi+7D0h], xmm0
0x180025df1  mov     [rsi+7E0h], r13
0x180025df8  mov     [rsi+7CCh], r13d
0x180025dff  mov     [rsi+7E8h], r13d
0x180025e06  call    cs:__imp_GetCurrentThreadId
0x180025e0d  nop     dword ptr [rax+rax+00h]
0x180025e12  mov     [rsi+7C0h], eax
0x180025e18  mov     rcx, rbx; lpCriticalSection
0x180025e1b  call    cs:__imp_LeaveCriticalSection
0x180025e22  nop     dword ptr [rax+rax+00h]
0x180025e27  mov     eax, ebp
0x180025e29  add     rsp, 58h
0x180025e2d  pop     r15
0x180025e2f  pop     r14
0x180025e31  pop     r13
0x180025e33  pop     r12
0x180025e35  pop     rdi
0x180025e36  pop     rsi
0x180025e37  pop     rbp
0x180025e38  pop     rbx
0x180025e39  retn
0x180025e3b  cmp     rdi, [r15+0C8h]
0x180025e42  jb      loc_180025EC9
0x180025e48  mov     ecx, 80070057h; int
0x180025e4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x180025e53  call    cs:__imp_GetLastError
0x180025e5a  nop     dword ptr [rax+rax+00h]
0x180025e5f  test    eax, eax
0x180025e61  jnz     loc_180025CC4
0x180025e67  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180025e6e  test    rcx, rcx
0x180025e71  jz      loc_1800260A4
0x180025e77  mov     rax, [rcx]
0x180025e7a  mov     rax, [rax]
0x180025e7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e82  test    rax, rax
0x180025e85  cmovnz  rdi, rax
0x180025e89  jmp     loc_180025CC4
0x180025e8e  call    cs:__imp_GetLastError
0x180025e95  nop     dword ptr [rax+rax+00h]
0x180025e9a  test    eax, eax
0x180025e9c  jnz     loc_180025DB8
0x180025ea2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x180025ea9  test    rcx, rcx
0x180025eac  jz      loc_1800260F3
0x180025eb2  mov     rax, [rcx]
0x180025eb5  mov     rax, [rax]
0x180025eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ebd  test    rax, rax
0x180025ec0  cmovnz  rsi, rax
0x180025ec4  jmp     loc_180025DB8
0x180025ec9  lfence
0x180025ecc  mov     rax, [r15+0C0h]
0x180025ed3  mov     rcx, [rax+rdi*8]
0x180025ed7  mov     rbp, [rcx+38h]
0x180025edb  lea     rcx, [rbp+58h]; SRWLock
0x180025edf  call    cs:__imp_AcquireSRWLockShared
0x180025ee6  nop     dword ptr [rax+rax+00h]
0x180025eeb  mov     rsi, [rbp+70h]
0x180025eef  lea     rcx, [rbp+58h]; SRWLock
0x180025ef3  call    cs:__imp_ReleaseSRWLockShared
0x180025efa  nop     dword ptr [rax+rax+00h]
0x180025eff  nop
0x180025f00  test    rsi, rsi
0x180025f03  jz      loc_180025FC6
0x180025f09  cmp     rdi, [r15+0C8h]
0x180025f10  jnb     loc_180025E48
0x180025f16  lfence
0x180025f19  mov     rax, [r15+0C0h]
0x180025f20  mov     rcx, [rax+rdi*8]
0x180025f24  mov     rsi, [rcx+38h]
0x180025f28  add     rsi, 58h ; 'X'
0x180025f2c  mov     rcx, rsi; SRWLock
0x180025f2f  call    cs:__imp_AcquireSRWLockShared
0x180025f36  nop     dword ptr [rax+rax+00h]
0x180025f3b  nop
0x180025f3c  mov     rcx, rsi; SRWLock
0x180025f3f  call    cs:__imp_ReleaseSRWLockShared
0x180025f46  nop     dword ptr [rax+rax+00h]
0x180025f4b  nop
0x180025f4c  mov     [rsp+98h+var_68], rsi
0x180025f51  mov     rcx, rsi; SRWLock
0x180025f54  call    cs:__imp_AcquireSRWLockExclusive
0x180025f5b  nop     dword ptr [rax+rax+00h]
0x180025f60  nop
0x180025f61  lea     rcx, [rsi+8]
0x180025f65  mov     rdx, [rcx]
0x180025f68  test    rdx, rdx
0x180025f6b  jz      loc_18002603F
0x180025f71  mov     rbp, [rdx+10h]
0x180025f75  mov     rax, [rdx]
0x180025f78  mov     [rcx], rax
0x180025f7b  test    rax, rax
0x180025f7e  jnz     loc_18002604A
0x180025f84  mov     [rcx+8], r13
0x180025f88  mov     rax, [rcx+20h]
0x180025f8c  mov     [rdx], rax
0x180025f8f  mov     [rcx+20h], rdx
0x180025f93  sub     qword ptr [rcx+10h], 1
0x180025f98  jnz     short loc_180025FA0
0x180025f9a  call    ?RemoveAll@?$CAtlList@PEAUIMFSample@@V?$CElementTraits@PEAUIMFSample@@@ATL@@@ATL@@QEAAXXZ
0x180025f9f  nop
0x180025fa0  mov     rcx, rsi; SRWLock
0x180025fa3  call    cs:__imp_ReleaseSRWLockExclusive
0x180025faa  nop     dword ptr [rax+rax+00h]
0x180025faf  nop
0x180025fb0  mov     rdx, rdi
0x180025fb3  shl     rdx, 5
0x180025fb7  mov     [rdx+r12+8], rbp
0x180025fbc  mov     [rsp+98h+arg_0], r13d
0x180025fc4  jmp     short loc_180025FCD
0x180025fc6  mov     rdx, rdi
0x180025fc9  shl     rdx, 5
0x180025fcd  cmp     rdi, [r15+0C8h]
0x180025fd4  jnb     loc_180025E48
0x180025fda  mov     rax, [r15+0C0h]
0x180025fe1  mov     rcx, [rax+rdi*8]
0x180025fe5  mov     rax, [rcx+38h]
0x180025fe9  cmp     dword ptr [rax+0Ch], 2
0x180025fed  jnz     loc_180025D6A
0x180025ff3  mov     [rsp+98h+var_78], r13d
0x180025ff8  lea     rsi, [r12+rdx]
0x180025ffc  mov     rcx, [rsi+8]
0x180026000  mov     rax, [rcx]
0x180026003  lea     r8, [rsp+98h+var_78]
0x180026008  lea     rdx, MFSampleExtension_EOS
0x18002600f  mov     rax, [rax+38h]
0x180026013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026018  test    eax, eax
0x18002601a  js      loc_180025D6A
0x180026020  cmp     [rsp+98h+var_78], 0
0x180026025  jz      loc_180025D6A
0x18002602b  cmp     rdi, [r15+0C8h]
0x180026032  jb      short loc_180026053
0x180026034  mov     ecx, 80070057h; int
0x180026039  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x18002603f  mov     ecx, 80004005h; int
0x180026044  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x18002604a  mov     [rax+8], r13
0x18002604e  jmp     loc_180025F88
0x180026053  mov     rax, [r15+0C0h]
0x18002605a  mov     rcx, [rax+rdi*8]
0x18002605e  mov     rcx, [rcx+38h]; this
0x180026062  call    ?PostDrainCompleteMsg@CDShowTransPin@@QEAAJXZ
0x180026067  or      dword ptr [rsi+10h], 300h
0x18002606e  mov     rcx, [rsi+8]
0x180026072  test    rcx, rcx
0x180026075  jz      loc_180025D6A
0x18002607b  mov     rax, [rcx]
0x18002607e  mov     rax, [rax+10h]
0x180026082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026087  mov     [rsi+8], r13
0x18002608b  inc     r14d
0x18002608e  jmp     loc_180025D11
0x180026093  call    ?InitInstance@CallStackTracing@@KAXXZ
0x180026098  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002609f  jmp     loc_180025C8E
0x1800260a4  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800260ab  nop     dword ptr [rax+rax+00h]
0x1800260b0  mov     rcx, rax
0x1800260b3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x1800260ba  test    rax, rax
0x1800260bd  jz      short loc_1800260E0
0x1800260bf  mov     rax, [rax]
0x1800260c2  mov     edx, 7F0h
0x1800260c7  mov     rax, [rax+8]
0x1800260cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260d0  test    eax, eax
0x1800260d2  jz      short loc_1800260E0
0x1800260d4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x1800260db  jmp     loc_180025E77
0x1800260e0  lea     rcx, qword_1800EB130
0x1800260e7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x1800260ee  jmp     loc_180025E77
0x1800260f3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800260fa  nop     dword ptr [rax+rax+00h]
0x1800260ff  mov     rcx, rax
0x180026102  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax
0x180026109  test    rax, rax
0x18002610c  jz      short loc_18002612F
0x18002610e  mov     rax, [rax]
0x180026111  mov     edx, 7F0h
0x180026116  mov     rax, [rax+8]
0x18002611a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002611f  test    eax, eax
0x180026121  jz      short loc_18002612F
0x180026123  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA
0x18002612a  jmp     loc_180025EB2
0x18002612f  lea     rcx, qword_1800EB130
0x180026136  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx
0x18002613d  jmp     loc_180025EB2
```
