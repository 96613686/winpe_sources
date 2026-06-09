# CSmartRemuxEngine::_UpdateValidFrameRate(void)

- ea: `0x18002b638`
- end: `0x18002b9f4`
- name: `?_UpdateValidFrameRate@CSmartRemuxEngine@@IEAAJXZ`
- size: `956`
- prototype: `__int64 __fastcall(CSmartRemuxEngine *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x18001eed8`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x1800153ac`
- `0x18001a330`
- `0x18001c280`
- `0x18002b638`
- `0x18002bb4c`
- `0x180037f48`
- `0x1800380b8`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b6b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b765`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b81c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b94b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b6b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b765`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b81c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002b94b`

## string_xrefs

- `0x18002b64f`: `CSmartRemuxEngine::_UpdateValidFrameRate`

## pseudocode

```c
__int64 __fastcall CSmartRemuxEngine::_UpdateValidFrameRate(CSmartRemuxEngine *this)
{
  __int64 v2; // rdx
  int v3; // ebx
  __int64 *v4; // rcx
  CallStackTracing *v5; // rax
  struct CallStackContext *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 *v14; // rcx
  CallStackTracing *v15; // rax
  struct CallStackContext *v16; // rax
  signed int v17; // edx
  signed int v18; // ecx
  __int64 v19; // rdx
  __int64 *v20; // rcx
  CallStackTracing *v21; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v24; // [rsp+30h] [rbp-18h] BYREF
  int v25[5]; // [rsp+34h] [rbp-14h] BYREF
  unsigned int v26; // [rsp+70h] [rbp+28h] BYREF
  unsigned int v27; // [rsp+78h] [rbp+30h] BYREF
  unsigned int v28; // [rsp+80h] [rbp+38h] BYREF
  unsigned int v29; // [rsp+88h] [rbp+40h] BYREF

  v29 = 0;
  v28 = 0;
  v27 = 0;
  v24 = 0;
  v25[0] = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v26,
    "CSmartRemuxEngine::_UpdateValidFrameRate",
    2347);
  v3 = MFGetAttribute2UINT32asUINT64(*((_QWORD *)this + 19), &MF_MT_FRAME_RATE, &v24, v25);
  if ( v3 >= 0 )
  {
    v3 = MFGetAttribute2UINT32asUINT64(*((_QWORD *)this + 19), &MF_MT_FRAME_SIZE, &v28, &v27);
    if ( v3 >= 0 )
    {
      v12 = MFGetAttributeUINT32(*((_QWORD *)this + 19), &MF_MT_MPEG2_LEVEL, 0xFFFFFFFFLL);
      v3 = ConvertMFLevelToAvcLevel(v12, &v29);
      if ( v3 >= 0 )
      {
        v17 = (v28 >> 4) * (v27 >> 4);
        v18 = *((_DWORD *)&g_uiMaxMBPerSec + v29);
        if ( (double)v24 / (double)v25[0] > (double)v18 / (double)v17 )
        {
          v26 = 0;
          v27 = 0;
          ReduceToLowestTerms(v18, v17, &v26, &v27);
          v3 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, unsigned __int64))(**((_QWORD **)this + 19) + 176LL))(
                 *((_QWORD *)this + 19),
                 &MF_MT_FRAME_RATE,
                 v27 | ((unsigned __int64)v26 << 32));
          if ( v3 < 0 )
          {
            v20 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19);
              CallStackTracing::s_wpInstance = v21;
              if ( v21
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
              {
                v20 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v20 = &qword_180069A90;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
              }
            }
            if ( *((_BYTE *)v20 + 8) )
            {
              ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v20);
              if ( *((_DWORD *)ThreadRelativeContext + 499) != v3 )
                CallStackContext::TraceFailure(
                  ThreadRelativeContext,
                  "CSmartRemuxEngine::_UpdateValidFrameRate",
                  2362,
                  v3);
            }
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v7 = 307;
              goto LABEL_46;
            }
          }
        }
      }
      else
      {
        v14 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v15 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13);
          CallStackTracing::s_wpInstance = v15;
          if ( v15 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 2032) )
          {
            v14 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v14 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v14 + 8) )
        {
          v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v14);
          if ( *((_DWORD *)v16 + 499) != v3 )
            CallStackContext::TraceFailure(v16, "CSmartRemuxEngine::_UpdateValidFrameRate", 2353, v3);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v7 = 306;
          goto LABEL_46;
        }
      }
    }
    else
    {
      v9 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8);
        CallStackTracing::s_wpInstance = v10;
        if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
        {
          v9 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v9 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v9 + 8) )
      {
        v11 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v9);
        if ( *((_DWORD *)v11 + 499) != v3 )
          CallStackContext::TraceFailure(v11, "CSmartRemuxEngine::_UpdateValidFrameRate", 2350, v3);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v7 = 305;
        goto LABEL_46;
      }
    }
  }
  else
  {
    v4 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v5 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v2);
      CallStackTracing::s_wpInstance = v5;
      if ( v5 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v5 + 8LL))(v5, 2032) )
      {
        v4 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v4 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v4 + 8) )
    {
      v6 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v4);
      if ( *((_DWORD *)v6 + 499) != v3 )
        CallStackContext::TraceFailure(v6, "CSmartRemuxEngine::_UpdateValidFrameRate", 2347, v3);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v7 = 304;
LABEL_46:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids, this, v3);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18002b638  push    rbp
0x18002b63a  push    rbx
0x18002b63b  push    rdi
0x18002b63c  push    r14
0x18002b63e  mov     rbp, rsp
0x18002b641  sub     rsp, 48h
0x18002b645  mov     rdi, rcx
0x18002b648  mov     [rbp+arg_18], 0
0x18002b64f  lea     r14, aCsmartremuxeng_14; "CSmartRemuxEngine::_UpdateValidFrameRat"...
0x18002b656  mov     [rbp+arg_10], 0
0x18002b65d  mov     rdx, r14; char *
0x18002b660  mov     [rbp+arg_8], 0
0x18002b667  mov     r8d, 92Bh; int
0x18002b66d  mov     [rbp+var_18], 0
0x18002b674  lea     rcx, [rbp+arg_0]; this
0x18002b678  mov     [rbp+var_14], 0
0x18002b67f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18002b684  mov     rcx, [rdi+98h]
0x18002b68b  lea     r9, [rbp+var_14]
0x18002b68f  lea     r8, [rbp+var_18]
0x18002b693  lea     rdx, MF_MT_FRAME_RATE
0x18002b69a  call    MFGetAttribute2UINT32asUINT64
0x18002b69f  mov     ebx, eax
0x18002b6a1  test    eax, eax
0x18002b6a3  jns     loc_18002B734
0x18002b6a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b6b0  test    rcx, rcx
0x18002b6b3  jnz     short loc_18002B6F6
0x18002b6b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002b6bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b6c2  mov     rcx, rax
0x18002b6c5  test    rax, rax
0x18002b6c8  jz      short loc_18002B6E8
0x18002b6ca  mov     rax, [rax]
0x18002b6cd  mov     edx, 7F0h
0x18002b6d2  mov     rax, [rax+8]
0x18002b6d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6db  test    eax, eax
0x18002b6dd  jz      short loc_18002B6E8
0x18002b6df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b6e6  jmp     short loc_18002B6F6
0x18002b6e8  lea     rcx, qword_180069A90; this
0x18002b6ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b6f6  cmp     byte ptr [rcx+8], 0
0x18002b6fa  jz      short loc_18002B71D
0x18002b6fc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002b701  cmp     [rax+7CCh], ebx
0x18002b707  jz      short loc_18002B71D
0x18002b709  mov     r9d, ebx; int
0x18002b70c  mov     r8d, 92Bh; int
0x18002b712  mov     rdx, r14; char *
0x18002b715  mov     rcx, rax; this
0x18002b718  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002b71d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002b722  cmp     al, 1
0x18002b724  jb      loc_18002B9DF
0x18002b72a  mov     edx, 130h
0x18002b72f  jmp     loc_18002B9C1
0x18002b734  mov     rcx, [rdi+98h]
0x18002b73b  lea     r9, [rbp+arg_8]
0x18002b73f  lea     r8, [rbp+arg_10]
0x18002b743  lea     rdx, MF_MT_FRAME_SIZE
0x18002b74a  call    MFGetAttribute2UINT32asUINT64
0x18002b74f  mov     ebx, eax
0x18002b751  test    eax, eax
0x18002b753  jns     loc_18002B7E4
0x18002b759  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b760  test    rcx, rcx
0x18002b763  jnz     short loc_18002B7A6
0x18002b765  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002b76b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b772  mov     rcx, rax
0x18002b775  test    rax, rax
0x18002b778  jz      short loc_18002B798
0x18002b77a  mov     rax, [rax]
0x18002b77d  mov     edx, 7F0h
0x18002b782  mov     rax, [rax+8]
0x18002b786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b78b  test    eax, eax
0x18002b78d  jz      short loc_18002B798
0x18002b78f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b796  jmp     short loc_18002B7A6
0x18002b798  lea     rcx, qword_180069A90; this
0x18002b79f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b7a6  cmp     byte ptr [rcx+8], 0
0x18002b7aa  jz      short loc_18002B7CD
0x18002b7ac  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002b7b1  cmp     [rax+7CCh], ebx
0x18002b7b7  jz      short loc_18002B7CD
0x18002b7b9  mov     r9d, ebx; int
0x18002b7bc  mov     r8d, 92Eh; int
0x18002b7c2  mov     rdx, r14; char *
0x18002b7c5  mov     rcx, rax; this
0x18002b7c8  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002b7cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002b7d2  cmp     al, 1
0x18002b7d4  jb      loc_18002B9DF
0x18002b7da  mov     edx, 131h
0x18002b7df  jmp     loc_18002B9C1
0x18002b7e4  mov     rcx, [rdi+98h]
0x18002b7eb  lea     rdx, MF_MT_MPEG2_LEVEL
0x18002b7f2  or      r8d, 0FFFFFFFFh
0x18002b7f6  call    MFGetAttributeUINT32
0x18002b7fb  lea     rdx, [rbp+arg_18]; unsigned int *
0x18002b7ff  mov     ecx, eax; unsigned int
0x18002b801  call    ?ConvertMFLevelToAvcLevel@@YAJKPEAI@Z; ConvertMFLevelToAvcLevel(ulong,uint *)
0x18002b806  mov     ebx, eax
0x18002b808  test    eax, eax
0x18002b80a  jns     loc_18002B89B
0x18002b810  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b817  test    rcx, rcx
0x18002b81a  jnz     short loc_18002B85D
0x18002b81c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002b822  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b829  mov     rcx, rax
0x18002b82c  test    rax, rax
0x18002b82f  jz      short loc_18002B84F
0x18002b831  mov     rax, [rax]
0x18002b834  mov     edx, 7F0h
0x18002b839  mov     rax, [rax+8]
0x18002b83d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b842  test    eax, eax
0x18002b844  jz      short loc_18002B84F
0x18002b846  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b84d  jmp     short loc_18002B85D
0x18002b84f  lea     rcx, qword_180069A90; this
0x18002b856  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b85d  cmp     byte ptr [rcx+8], 0
0x18002b861  jz      short loc_18002B884
0x18002b863  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002b868  cmp     [rax+7CCh], ebx
0x18002b86e  jz      short loc_18002B884
0x18002b870  mov     r9d, ebx; int
0x18002b873  mov     r8d, 931h; int
0x18002b879  mov     rdx, r14; char *
0x18002b87c  mov     rcx, rax; this
0x18002b87f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002b884  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002b889  cmp     al, 1
0x18002b88b  jb      loc_18002B9DF
0x18002b891  mov     edx, 132h
0x18002b896  jmp     loc_18002B9C1
0x18002b89b  mov     edx, [rbp+arg_8]
0x18002b89e  lea     rcx, ?g_uiMaxMBPerSec@@3QBIB; uint const near * const g_uiMaxMBPerSec
0x18002b8a5  mov     eax, [rbp+arg_10]
0x18002b8a8  xorps   xmm0, xmm0
0x18002b8ab  shr     eax, 4
0x18002b8ae  xorps   xmm2, xmm2
0x18002b8b1  shr     edx, 4
0x18002b8b4  xorps   xmm1, xmm1
0x18002b8b7  imul    edx, eax; unsigned int
0x18002b8ba  mov     eax, [rbp+arg_18]
0x18002b8bd  mov     ecx, [rcx+rax*4]; unsigned int
0x18002b8c0  mov     eax, [rbp+var_18]
0x18002b8c3  cvtsi2sd xmm1, rcx
0x18002b8c8  cvtsi2sd xmm2, rax
0x18002b8cd  mov     eax, [rbp+var_14]
0x18002b8d0  cvtsi2sd xmm0, rax
0x18002b8d5  divsd   xmm2, xmm0
0x18002b8d9  xorps   xmm0, xmm0
0x18002b8dc  cvtsi2sd xmm0, rdx
0x18002b8e1  divsd   xmm1, xmm0
0x18002b8e5  comisd  xmm2, xmm1
0x18002b8e9  jbe     loc_18002B9DF
0x18002b8ef  lea     r9, [rbp+arg_8]; unsigned int *
0x18002b8f3  mov     [rbp+arg_0], 0
0x18002b8fa  lea     r8, [rbp+arg_0]; unsigned int *
0x18002b8fe  mov     [rbp+arg_8], 0
0x18002b905  call    ?ReduceToLowestTerms@@YAXIIPEAI0@Z; ReduceToLowestTerms(uint,uint,uint *,uint *)
0x18002b90a  mov     rcx, [rdi+98h]
0x18002b911  lea     rdx, MF_MT_FRAME_RATE
0x18002b918  mov     eax, [rbp+arg_8]
0x18002b91b  mov     r8d, [rbp+arg_0]
0x18002b91f  shl     r8, 20h
0x18002b923  mov     r9, [rcx]
0x18002b926  or      r8, rax
0x18002b929  mov     rax, [r9+0B0h]
0x18002b930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b935  mov     ebx, eax
0x18002b937  test    eax, eax
0x18002b939  jns     loc_18002B9DF
0x18002b93f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b946  test    rcx, rcx
0x18002b949  jnz     short loc_18002B98C
0x18002b94b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002b951  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b958  mov     rcx, rax
0x18002b95b  test    rax, rax
0x18002b95e  jz      short loc_18002B97E
0x18002b960  mov     rax, [rax]
0x18002b963  mov     edx, 7F0h
0x18002b968  mov     rax, [rax+8]
0x18002b96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b971  test    eax, eax
0x18002b973  jz      short loc_18002B97E
0x18002b975  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b97c  jmp     short loc_18002B98C
0x18002b97e  lea     rcx, qword_180069A90; this
0x18002b985  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002b98c  cmp     byte ptr [rcx+8], 0
0x18002b990  jz      short loc_18002B9B3
0x18002b992  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18002b997  cmp     [rax+7CCh], ebx
0x18002b99d  jz      short loc_18002B9B3
0x18002b99f  mov     r9d, ebx; int
0x18002b9a2  mov     r8d, 93Ah; int
0x18002b9a8  mov     rdx, r14; char *
0x18002b9ab  mov     rcx, rax; this
0x18002b9ae  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18002b9b3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18002b9b8  cmp     al, 1
0x18002b9ba  jb      short loc_18002B9DF
0x18002b9bc  mov     edx, 133h
0x18002b9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9c8  lea     r8, WPP_14b006652b8137ad6e40de3d71db1d47_Traceguids
0x18002b9cf  mov     r9, rdi
0x18002b9d2  mov     [rsp+48h+var_28], ebx
0x18002b9d6  mov     rcx, [rcx+10h]
0x18002b9da  call    WPP_SF_qd
0x18002b9df  lea     rcx, [rbp+arg_0]; this
0x18002b9e3  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18002b9e8  mov     eax, ebx
0x18002b9ea  add     rsp, 48h
0x18002b9ee  pop     r14
0x18002b9f0  pop     rdi
0x18002b9f1  pop     rbx
0x18002b9f2  pop     rbp
0x18002b9f3  retn
```
