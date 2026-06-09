# CTranscodeProfileAdjuster::AdjustSourceRotation(IMFStreamDescriptor *,IMFAttributes *)

- ea: `0x18003b58c`
- end: `0x18003b8c5`
- name: `?AdjustSourceRotation@CTranscodeProfileAdjuster@@IEAAJPEAUIMFStreamDescriptor@@PEAUIMFAttributes@@@Z`
- size: `825`
- prototype: `__int64 __fastcall(CTranscodeProfileAdjuster *__hidden this, struct IMFStreamDescriptor *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180039a70`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x18003b58c`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b604`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b6cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b7db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b604`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b6cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003b7db`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster::AdjustSourceRotation(
        CTranscodeProfileAdjuster *this,
        struct IMFStreamDescriptor *a2,
        struct IMFAttributes *a3)
{
  __int64 v6; // rdx
  int v7; // ebx
  __int64 *v8; // rcx
  CallStackTracing *v9; // rax
  struct CallStackContext *v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  struct CallStackContext *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rcx
  CallStackTracing *v18; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  int v21; // [rsp+30h] [rbp-20h] BYREF
  __int64 v22; // [rsp+38h] [rbp-18h] BYREF
  __int64 v23; // [rsp+40h] [rbp-10h] BYREF
  char v24; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v25; // [rsp+88h] [rbp+38h] BYREF

  v23 = 0;
  v22 = 0;
  v25 = 0;
  v21 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v24,
    "CTranscodeProfileAdjuster::AdjustSourceRotation",
    745);
  v7 = ((__int64 (__fastcall *)(struct IMFStreamDescriptor *, __int64 *))a2->lpVtbl->GetMediaTypeHandler)(a2, &v23);
  if ( v7 >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 56LL))(v23, &v22) >= 0
      || (v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 40LL))(v23, 0, &v22), v7 >= 0) )
    {
      (*(void (__fastcall **)(__int64, __int128 *, unsigned int *))(*(_QWORD *)v22 + 56LL))(
        v22,
        &MF_MT_VIDEO_ROTATION,
        &v25);
      ((void (__fastcall *)(struct IMFAttributes *, __int128 *, int *))a3->lpVtbl->GetUINT32)(
        a3,
        &MF_MT_VIDEO_ROTATION,
        &v21);
      v25 = (v25 - v21) % 0x168;
      v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v22 + 168LL))(v22, &MF_MT_VIDEO_ROTATION);
      if ( v7 < 0 )
      {
        v17 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v16);
          CallStackTracing::s_wpInstance = v18;
          if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
          {
            v17 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v17 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v17 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v17);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CTranscodeProfileAdjuster::AdjustSourceRotation",
              759,
              v7);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v11 = 125;
          goto LABEL_35;
        }
      }
    }
    else
    {
      v13 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12);
        CallStackTracing::s_wpInstance = v14;
        if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
        {
          v13 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v13 = &qword_180069A90;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
        }
      }
      if ( *((_BYTE *)v13 + 8) )
      {
        v15 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
        if ( *((_DWORD *)v15 + 499) != v7 )
          CallStackContext::TraceFailure(v15, "CTranscodeProfileAdjuster::AdjustSourceRotation", 750, v7);
      }
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v11 = 124;
        goto LABEL_35;
      }
    }
  }
  else
  {
    v8 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v9 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v6);
      CallStackTracing::s_wpInstance = v9;
      if ( v9 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v9 + 8LL))(v9, 2032) )
      {
        v8 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v8 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v8 + 8) )
    {
      v10 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v8);
      if ( *((_DWORD *)v10 + 499) != v7 )
        CallStackContext::TraceFailure(v10, "CTranscodeProfileAdjuster::AdjustSourceRotation", 745, v7);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v11 = 123;
LABEL_35:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, this, v7);
    }
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v24);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003b58c  mov     [rsp-18h+arg_0], rbx
0x18003b591  push    rbp
0x18003b592  push    rsi
0x18003b593  push    rdi
0x18003b594  mov     rbp, rsp
0x18003b597  sub     rsp, 50h
0x18003b59b  mov     rsi, r8
0x18003b59e  mov     [rbp+var_10], 0
0x18003b5a6  mov     rbx, rdx
0x18003b5a9  mov     [rbp+var_18], 0
0x18003b5b1  mov     rdi, rcx
0x18003b5b4  mov     [rbp+arg_18], 0
0x18003b5bb  mov     r8d, 2E9h; int
0x18003b5c1  mov     [rbp+var_20], 0
0x18003b5c8  lea     rdx, aCtranscodeprof_15; "CTranscodeProfileAdjuster::AdjustSource"...
0x18003b5cf  lea     rcx, [rbp+arg_8]; this
0x18003b5d3  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18003b5d8  mov     rax, [rbx]
0x18003b5db  lea     rdx, [rbp+var_10]
0x18003b5df  mov     rcx, rbx
0x18003b5e2  mov     rax, [rax+110h]
0x18003b5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5ee  mov     ebx, eax
0x18003b5f0  test    eax, eax
0x18003b5f2  jns     loc_18003B687
0x18003b5f8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b5ff  test    rcx, rcx
0x18003b602  jnz     short loc_18003B645
0x18003b604  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b60a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b611  mov     rcx, rax
0x18003b614  test    rax, rax
0x18003b617  jz      short loc_18003B637
0x18003b619  mov     rax, [rax]
0x18003b61c  mov     edx, 7F0h
0x18003b621  mov     rax, [rax+8]
0x18003b625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b62a  test    eax, eax
0x18003b62c  jz      short loc_18003B637
0x18003b62e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b635  jmp     short loc_18003B645
0x18003b637  lea     rcx, qword_180069A90; this
0x18003b63e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b645  cmp     byte ptr [rcx+8], 0
0x18003b649  jz      short loc_18003B670
0x18003b64b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b650  cmp     [rax+7CCh], ebx
0x18003b656  jz      short loc_18003B670
0x18003b658  mov     r9d, ebx; int
0x18003b65b  lea     rdx, aCtranscodeprof_15; "CTranscodeProfileAdjuster::AdjustSource"...
0x18003b662  mov     r8d, 2E9h; int
0x18003b668  mov     rcx, rax; this
0x18003b66b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b670  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b675  cmp     al, 1
0x18003b677  jb      loc_18003B873
0x18003b67d  mov     edx, 7Bh ; '{'
0x18003b682  jmp     loc_18003B855
0x18003b687  mov     rcx, [rbp+var_10]
0x18003b68b  lea     rdx, [rbp+var_18]
0x18003b68f  mov     rax, [rcx]
0x18003b692  mov     rax, [rax+38h]
0x18003b696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b69b  test    eax, eax
0x18003b69d  jns     loc_18003B752
0x18003b6a3  mov     rcx, [rbp+var_10]
0x18003b6a7  lea     r8, [rbp+var_18]
0x18003b6ab  xor     edx, edx
0x18003b6ad  mov     rax, [rcx]
0x18003b6b0  mov     rax, [rax+28h]
0x18003b6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6b9  mov     ebx, eax
0x18003b6bb  test    eax, eax
0x18003b6bd  jns     loc_18003B752
0x18003b6c3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b6ca  test    rcx, rcx
0x18003b6cd  jnz     short loc_18003B710
0x18003b6cf  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b6d5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b6dc  mov     rcx, rax
0x18003b6df  test    rax, rax
0x18003b6e2  jz      short loc_18003B702
0x18003b6e4  mov     rax, [rax]
0x18003b6e7  mov     edx, 7F0h
0x18003b6ec  mov     rax, [rax+8]
0x18003b6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6f5  test    eax, eax
0x18003b6f7  jz      short loc_18003B702
0x18003b6f9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b700  jmp     short loc_18003B710
0x18003b702  lea     rcx, qword_180069A90; this
0x18003b709  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b710  cmp     byte ptr [rcx+8], 0
0x18003b714  jz      short loc_18003B73B
0x18003b716  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b71b  cmp     [rax+7CCh], ebx
0x18003b721  jz      short loc_18003B73B
0x18003b723  mov     r9d, ebx; int
0x18003b726  lea     rdx, aCtranscodeprof_15; "CTranscodeProfileAdjuster::AdjustSource"...
0x18003b72d  mov     r8d, 2EEh; int
0x18003b733  mov     rcx, rax; this
0x18003b736  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b73b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b740  cmp     al, 1
0x18003b742  jb      loc_18003B873
0x18003b748  mov     edx, 7Ch ; '|'
0x18003b74d  jmp     loc_18003B855
0x18003b752  mov     rcx, [rbp+var_18]
0x18003b756  lea     rbx, MF_MT_VIDEO_ROTATION
0x18003b75d  lea     r8, [rbp+arg_18]
0x18003b761  mov     rdx, rbx
0x18003b764  mov     rax, [rcx]
0x18003b767  mov     rax, [rax+38h]
0x18003b76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b770  mov     rax, [rsi]
0x18003b773  lea     r8, [rbp+var_20]
0x18003b777  mov     rdx, rbx
0x18003b77a  mov     rcx, rsi
0x18003b77d  mov     rax, [rax+38h]
0x18003b781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b786  mov     r8d, [rbp+arg_18]
0x18003b78a  mov     eax, 6C16C16Dh
0x18003b78f  sub     r8d, [rbp+var_20]
0x18003b793  mov     rcx, [rbp+var_18]
0x18003b797  mul     r8d
0x18003b79a  mov     eax, r8d
0x18003b79d  sub     eax, edx
0x18003b79f  shr     eax, 1
0x18003b7a1  add     eax, edx
0x18003b7a3  mov     rdx, rbx
0x18003b7a6  shr     eax, 8
0x18003b7a9  imul    eax, 168h
0x18003b7af  sub     r8d, eax
0x18003b7b2  mov     [rbp+arg_18], r8d
0x18003b7b6  mov     rax, [rcx]
0x18003b7b9  mov     rax, [rax+0A8h]
0x18003b7c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7c5  mov     ebx, eax
0x18003b7c7  test    eax, eax
0x18003b7c9  jns     loc_18003B873
0x18003b7cf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b7d6  test    rcx, rcx
0x18003b7d9  jnz     short loc_18003B81C
0x18003b7db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003b7e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b7e8  mov     rcx, rax
0x18003b7eb  test    rax, rax
0x18003b7ee  jz      short loc_18003B80E
0x18003b7f0  mov     rax, [rax]
0x18003b7f3  mov     edx, 7F0h
0x18003b7f8  mov     rax, [rax+8]
0x18003b7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b801  test    eax, eax
0x18003b803  jz      short loc_18003B80E
0x18003b805  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b80c  jmp     short loc_18003B81C
0x18003b80e  lea     rcx, qword_180069A90; this
0x18003b815  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003b81c  cmp     byte ptr [rcx+8], 0
0x18003b820  jz      short loc_18003B847
0x18003b822  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003b827  cmp     [rax+7CCh], ebx
0x18003b82d  jz      short loc_18003B847
0x18003b82f  mov     r9d, ebx; int
0x18003b832  lea     rdx, aCtranscodeprof_15; "CTranscodeProfileAdjuster::AdjustSource"...
0x18003b839  mov     r8d, 2F7h; int
0x18003b83f  mov     rcx, rax; this
0x18003b842  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003b847  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003b84c  cmp     al, 1
0x18003b84e  jb      short loc_18003B873
0x18003b850  mov     edx, 7Dh ; '}'
0x18003b855  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b85c  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003b863  mov     r9, rdi
0x18003b866  mov     [rsp+50h+var_30], ebx
0x18003b86a  mov     rcx, [rcx+10h]
0x18003b86e  call    WPP_SF_qd
0x18003b873  mov     rcx, [rbp+var_10]
0x18003b877  test    rcx, rcx
0x18003b87a  jz      short loc_18003B890
0x18003b87c  mov     rax, [rcx]
0x18003b87f  mov     rax, [rax+10h]
0x18003b883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b888  mov     [rbp+var_10], 0
0x18003b890  mov     rcx, [rbp+var_18]
0x18003b894  test    rcx, rcx
0x18003b897  jz      short loc_18003B8AD
0x18003b899  mov     rax, [rcx]
0x18003b89c  mov     rax, [rax+10h]
0x18003b8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8a5  mov     [rbp+var_18], 0
0x18003b8ad  lea     rcx, [rbp+arg_8]; this
0x18003b8b1  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18003b8b6  mov     eax, ebx
0x18003b8b8  mov     rbx, [rsp+50h+arg_0]
0x18003b8bd  add     rsp, 50h
0x18003b8c1  pop     rdi
0x18003b8c2  pop     rsi
0x18003b8c3  pop     rbp
0x18003b8c4  retn
```
