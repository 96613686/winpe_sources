# CDShowTransform::Init(void)

- ea: `0x180027a88`
- end: `0x180027dca`
- name: `?Init@CDShowTransform@@QEAAJXZ`
- size: `834`
- prototype: `__int64 __fastcall(CDShowTransform *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000d768`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800140b0`
- `0x180027a88`
- `0x180027e1c`
- `0x180028ccc`
- `0x180028fb0`
- `0x180032a50`
- `0x180051ce4`
- `0x1800c9010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027afb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027ba6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027c51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027d07`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027afb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027ba6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027c51`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180027d07`
- `MFPlat!MFCreateEventQueue` at `0x180027ce4`
- `MFPlat!MFCreateEventQueue` at `0x180027ce4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDShowTransform::Init(IMFMediaEventQueue **this)
{
  CallStackTracing *v2; // rcx
  CallStackTracing *v3; // rax
  struct CallStackContext *v4; // rax
  __int64 v5; // rdx
  CallStackTracing *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *v8; // rax
  CallStackTracing *v9; // rcx
  CallStackTracing *v10; // rax
  struct CallStackContext *v11; // rax
  CallStackTracing *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  unsigned int v15; // ebx
  char v17; // [rsp+50h] [rbp+10h] BYREF
  int updated; // [rsp+58h] [rbp+18h]

  updated = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v17, "CDShowTransform::Init", 700);
  updated = CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetUINT32(this + 2, &MF_TRANSFORM_ASYNC, 1);
  if ( updated >= 0 )
  {
    updated = CDShowTransform::UpdateInputPins((CDShowTransform *)this);
    if ( updated >= 0 )
    {
      updated = CDShowTransform::UpdateOutputPins((CDShowTransform *)this);
      if ( updated >= 0 )
      {
        updated = MFCreateEventQueue(this + 18);
        if ( updated < 0 )
        {
          v12 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
            CallStackTracing::s_wpInstance = v13;
            if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
            {
              v12 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v12 = (CallStackTracing *)&qword_1800EB130;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
            }
          }
          if ( *((_BYTE *)v12 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v12);
            if ( updated < 0 && *((_DWORD *)ThreadRelativeContext + 499) != updated )
              CallStackContext::TraceFailure(ThreadRelativeContext, "CDShowTransform::Init", 714, updated);
          }
          if ( g_wppLevels )
          {
            v5 = 50;
            goto LABEL_49;
          }
        }
      }
      else
      {
        v9 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v10 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v10;
          if ( v10 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v10 + 8LL))(v10, 2032) )
          {
            v9 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v9 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        if ( *((_BYTE *)v9 + 8) )
        {
          v11 = CallStackTracing::GetThreadRelativeContext(v9);
          if ( updated < 0 && *((_DWORD *)v11 + 499) != updated )
            CallStackContext::TraceFailure(v11, "CDShowTransform::Init", 708, updated);
        }
        if ( g_wppLevels )
        {
          v5 = 49;
          goto LABEL_49;
        }
      }
    }
    else
    {
      v6 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v7;
        if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
        {
          v6 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v6 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      if ( *((_BYTE *)v6 + 8) )
      {
        v8 = CallStackTracing::GetThreadRelativeContext(v6);
        if ( updated < 0 && *((_DWORD *)v8 + 499) != updated )
          CallStackContext::TraceFailure(v8, "CDShowTransform::Init", 707, updated);
      }
      if ( g_wppLevels )
      {
        v5 = 48;
        goto LABEL_49;
      }
    }
  }
  else
  {
    v2 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v3 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
      CallStackTracing::s_wpInstance = v3;
      if ( v3 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v3 + 8LL))(v3, 2032) )
      {
        v2 = CallStackTracing::s_wpInstance;
      }
      else
      {
        v2 = (CallStackTracing *)&qword_1800EB130;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
      }
    }
    if ( *((_BYTE *)v2 + 8) )
    {
      v4 = CallStackTracing::GetThreadRelativeContext(v2);
      if ( updated < 0 && *((_DWORD *)v4 + 499) != updated )
        CallStackContext::TraceFailure(v4, "CDShowTransform::Init", 705, updated);
    }
    if ( g_wppLevels )
    {
      v5 = 47;
LABEL_49:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v5,
        &WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids,
        this,
        updated);
    }
  }
  v15 = updated;
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v17);
  return v15;
}

```

## disassembly

```asm
0x180027a88  mov     [rsp-8+arg_10], rbx
0x180027a8d  mov     [rsp-8+arg_18], r14
0x180027a92  push    rbp
0x180027a93  mov     rbp, rsp
0x180027a96  sub     rsp, 40h
0x180027a9a  mov     rbx, rcx
0x180027a9d  mov     [rbp+arg_8], 0
0x180027aa4  mov     r8d, 2BCh; int
0x180027aaa  lea     r14, aCdshowtransfor_22; "CDShowTransform::Init"
0x180027ab1  mov     rdx, r14; char *
0x180027ab4  lea     rcx, [rbp+arg_0]; this
0x180027ab8  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180027abd  nop
0x180027abe  mov     [rbp+var_10], 0
0x180027ac6  lea     rax, [rbp+arg_8]
0x180027aca  mov     [rbp+var_8], rax
0x180027ace  lea     rcx, [rbx+10h]
0x180027ad2  mov     r8d, 1
0x180027ad8  lea     rdx, MF_TRANSFORM_ASYNC
0x180027adf  call    ?SetUINT32@?$CMFAttributesImpl@UIMFAttributes@@VCWin32AttributeLock@@@@UEAAJAEBU_GUID@@I@Z; CMFAttributesImpl<IMFAttributes,CWin32AttributeLock>::SetUINT32(_GUID const &,uint)
0x180027ae4  mov     [rbp+arg_8], eax
0x180027ae7  test    eax, eax
0x180027ae9  jns     loc_180027B87
0x180027aef  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027af6  test    rcx, rcx
0x180027af9  jnz     short loc_180027B42
0x180027afb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027b02  nop     dword ptr [rax+rax+00h]
0x180027b07  mov     rcx, rax
0x180027b0a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027b11  test    rax, rax
0x180027b14  jz      short loc_180027B34
0x180027b16  mov     rax, [rax]
0x180027b19  mov     edx, 7F0h
0x180027b1e  mov     rax, [rax+8]
0x180027b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b27  test    eax, eax
0x180027b29  jz      short loc_180027B34
0x180027b2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027b32  jmp     short loc_180027B42
0x180027b34  lea     rcx, qword_1800EB130; this
0x180027b3b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027b42  cmp     byte ptr [rcx+8], 0
0x180027b46  jz      short loc_180027B70
0x180027b48  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027b4d  mov     r9d, [rbp+arg_8]; int
0x180027b51  test    r9d, r9d
0x180027b54  jns     short loc_180027B70
0x180027b56  cmp     [rax+7CCh], r9d
0x180027b5d  jz      short loc_180027B70
0x180027b5f  mov     r8d, 2C1h; int
0x180027b65  mov     rdx, r14; char *
0x180027b68  mov     rcx, rax; this
0x180027b6b  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027b70  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027b77  jb      loc_180027DAB
0x180027b7d  mov     edx, 2Fh ; '/'
0x180027b82  jmp     loc_180027D8A
0x180027b87  mov     rcx, rbx; this
0x180027b8a  call    ?UpdateInputPins@CDShowTransform@@IEAAJXZ; CDShowTransform::UpdateInputPins(void)
0x180027b8f  mov     [rbp+arg_8], eax
0x180027b92  test    eax, eax
0x180027b94  jns     loc_180027C32
0x180027b9a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027ba1  test    rcx, rcx
0x180027ba4  jnz     short loc_180027BED
0x180027ba6  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027bad  nop     dword ptr [rax+rax+00h]
0x180027bb2  mov     rcx, rax
0x180027bb5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027bbc  test    rax, rax
0x180027bbf  jz      short loc_180027BDF
0x180027bc1  mov     rax, [rax]
0x180027bc4  mov     edx, 7F0h
0x180027bc9  mov     rax, [rax+8]
0x180027bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027bd2  test    eax, eax
0x180027bd4  jz      short loc_180027BDF
0x180027bd6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027bdd  jmp     short loc_180027BED
0x180027bdf  lea     rcx, qword_1800EB130; this
0x180027be6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027bed  cmp     byte ptr [rcx+8], 0
0x180027bf1  jz      short loc_180027C1B
0x180027bf3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027bf8  mov     r9d, [rbp+arg_8]; int
0x180027bfc  test    r9d, r9d
0x180027bff  jns     short loc_180027C1B
0x180027c01  cmp     [rax+7CCh], r9d
0x180027c08  jz      short loc_180027C1B
0x180027c0a  mov     r8d, 2C3h; int
0x180027c10  mov     rdx, r14; char *
0x180027c13  mov     rcx, rax; this
0x180027c16  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027c1b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027c22  jb      loc_180027DAB
0x180027c28  mov     edx, 30h ; '0'
0x180027c2d  jmp     loc_180027D8A
0x180027c32  mov     rcx, rbx; this
0x180027c35  call    ?UpdateOutputPins@CDShowTransform@@IEAAJXZ; CDShowTransform::UpdateOutputPins(void)
0x180027c3a  mov     [rbp+arg_8], eax
0x180027c3d  test    eax, eax
0x180027c3f  jns     loc_180027CDD
0x180027c45  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027c4c  test    rcx, rcx
0x180027c4f  jnz     short loc_180027C98
0x180027c51  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027c58  nop     dword ptr [rax+rax+00h]
0x180027c5d  mov     rcx, rax
0x180027c60  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027c67  test    rax, rax
0x180027c6a  jz      short loc_180027C8A
0x180027c6c  mov     rax, [rax]
0x180027c6f  mov     edx, 7F0h
0x180027c74  mov     rax, [rax+8]
0x180027c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c7d  test    eax, eax
0x180027c7f  jz      short loc_180027C8A
0x180027c81  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027c88  jmp     short loc_180027C98
0x180027c8a  lea     rcx, qword_1800EB130; this
0x180027c91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027c98  cmp     byte ptr [rcx+8], 0
0x180027c9c  jz      short loc_180027CC6
0x180027c9e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027ca3  mov     r9d, [rbp+arg_8]; int
0x180027ca7  test    r9d, r9d
0x180027caa  jns     short loc_180027CC6
0x180027cac  cmp     [rax+7CCh], r9d
0x180027cb3  jz      short loc_180027CC6
0x180027cb5  mov     r8d, 2C4h; int
0x180027cbb  mov     rdx, r14; char *
0x180027cbe  mov     rcx, rax; this
0x180027cc1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027cc6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027ccd  jb      loc_180027DAB
0x180027cd3  mov     edx, 31h ; '1'
0x180027cd8  jmp     loc_180027D8A
0x180027cdd  lea     rcx, [rbx+90h]; ppMediaEventQueue
0x180027ce4  call    cs:__imp_MFCreateEventQueue
0x180027ceb  nop     dword ptr [rax+rax+00h]
0x180027cf0  mov     [rbp+arg_8], eax
0x180027cf3  test    eax, eax
0x180027cf5  jns     loc_180027DAB
0x180027cfb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027d02  test    rcx, rcx
0x180027d05  jnz     short loc_180027D4E
0x180027d07  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180027d0e  nop     dword ptr [rax+rax+00h]
0x180027d13  mov     rcx, rax
0x180027d16  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180027d1d  test    rax, rax
0x180027d20  jz      short loc_180027D40
0x180027d22  mov     rax, [rax]
0x180027d25  mov     edx, 7F0h
0x180027d2a  mov     rax, [rax+8]
0x180027d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d33  test    eax, eax
0x180027d35  jz      short loc_180027D40
0x180027d37  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180027d3e  jmp     short loc_180027D4E
0x180027d40  lea     rcx, qword_1800EB130; this
0x180027d47  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180027d4e  cmp     byte ptr [rcx+8], 0
0x180027d52  jz      short loc_180027D7C
0x180027d54  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180027d59  mov     r9d, [rbp+arg_8]; int
0x180027d5d  test    r9d, r9d
0x180027d60  jns     short loc_180027D7C
0x180027d62  cmp     [rax+7CCh], r9d
0x180027d69  jz      short loc_180027D7C
0x180027d6b  mov     r8d, 2CAh; int
0x180027d71  mov     rdx, r14; char *
0x180027d74  mov     rcx, rax; this
0x180027d77  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180027d7c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027d83  jb      short loc_180027DAB
0x180027d85  mov     edx, 32h ; '2'
0x180027d8a  mov     eax, [rbp+arg_8]
0x180027d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d94  mov     [rsp+40h+var_20], eax
0x180027d98  mov     r9, rbx
0x180027d9b  lea     r8, WPP_4424637dafd93ac8aa68a350a9714af2_Traceguids
0x180027da2  mov     rcx, [rcx+10h]
0x180027da6  call    WPP_SF_qD
0x180027dab  mov     ebx, [rbp+arg_8]
0x180027dae  lea     rcx, [rbp+arg_0]; this
0x180027db2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180027db7  mov     eax, ebx
0x180027db9  mov     rbx, [rsp+40h+arg_10]
0x180027dbe  mov     r14, [rsp+40h+arg_18]
0x180027dc3  add     rsp, 40h
0x180027dc7  pop     rbp
0x180027dc8  retn
```
