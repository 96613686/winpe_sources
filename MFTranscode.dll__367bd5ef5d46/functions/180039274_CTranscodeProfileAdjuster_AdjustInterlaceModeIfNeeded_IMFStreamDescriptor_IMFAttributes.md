# CTranscodeProfileAdjuster::AdjustInterlaceModeIfNeeded(IMFStreamDescriptor *,IMFAttributes *)

- ea: `0x180039274`
- end: `0x180039449`
- name: `?AdjustInterlaceModeIfNeeded@CTranscodeProfileAdjuster@@IEAAJPEAUIMFStreamDescriptor@@PEAUIMFAttributes@@@Z`
- size: `469`
- prototype: `__int64 __fastcall(CTranscodeProfileAdjuster *__hidden this, struct IMFStreamDescriptor *, struct IMFAttributes *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180039a70`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18001a330`
- `0x18001c280`
- `0x180039274`
- `0x18003dbf0`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800392d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039395`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800392d2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180039395`

## pseudocode

```c
__int64 __fastcall CTranscodeProfileAdjuster::AdjustInterlaceModeIfNeeded(
        CTranscodeProfileAdjuster *this,
        struct IMFStreamDescriptor *a2,
        struct IMFAttributes *a3)
{
  __int64 v5; // rdx
  int v6; // ebx
  __int64 *v7; // rcx
  CallStackTracing *v8; // rax
  struct CallStackContext *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct IMFStreamDescriptor *v16; // [rsp+48h] [rbp+10h] BYREF

  v16 = a2;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v16,
    "CTranscodeProfileAdjuster::AdjustInterlaceModeIfNeeded",
    830);
  LODWORD(v16) = 0;
  v6 = CTranscodeProfileAdjuster::CheckIfInterlaceModeSet(this, a3, (int *)&v16);
  if ( v6 >= 0 )
  {
    if ( !(_DWORD)v16 )
    {
      v6 = ((__int64 (__fastcall *)(struct IMFAttributes *, const GUID *, __int64))a3->lpVtbl->SetUINT32)(
             a3,
             &MF_MT_INTERLACE_MODE,
             2);
      if ( v6 < 0 )
      {
        v12 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v11);
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v12 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v12 = &qword_180069A90;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
          }
        }
        if ( *((_BYTE *)v12 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v12);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CTranscodeProfileAdjuster::AdjustInterlaceModeIfNeeded",
              839,
              v6);
        }
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v10 = 133;
          goto LABEL_24;
        }
      }
    }
  }
  else
  {
    v7 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v8 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v5);
      CallStackTracing::s_wpInstance = v8;
      if ( v8 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v8 + 8LL))(v8, 2032) )
      {
        v7 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v7 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v7 + 8) )
    {
      v9 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v7);
      if ( *((_DWORD *)v9 + 499) != v6 )
        CallStackContext::TraceFailure(v9, "CTranscodeProfileAdjuster::AdjustInterlaceModeIfNeeded", 835, v6);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v10 = 132;
LABEL_24:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids, this, v6);
    }
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180039274  mov     rax, rsp
0x180039277  mov     [rax+8], rbx
0x18003927b  mov     [rax+18h], rsi
0x18003927f  mov     [rax+10h], rdx
0x180039283  push    rdi
0x180039284  sub     rsp, 30h
0x180039288  mov     rdi, r8
0x18003928b  lea     rdx, aCtranscodeprof_11; "CTranscodeProfileAdjuster::AdjustInterl"...
0x180039292  mov     rsi, rcx
0x180039295  mov     r8d, 33Eh; int
0x18003929b  lea     rcx, [rax+10h]; this
0x18003929f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800392a4  lea     r8, [rsp+38h+arg_8]; int *
0x1800392a9  mov     dword ptr [rsp+38h+arg_8], 0
0x1800392b1  mov     rdx, rdi; struct IMFAttributes *
0x1800392b4  mov     rcx, rsi; this
0x1800392b7  call    ?CheckIfInterlaceModeSet@CTranscodeProfileAdjuster@@IEAAJPEAUIMFAttributes@@PEAH@Z; CTranscodeProfileAdjuster::CheckIfInterlaceModeSet(IMFAttributes *,int *)
0x1800392bc  mov     ebx, eax
0x1800392be  test    eax, eax
0x1800392c0  jns     loc_180039355
0x1800392c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800392cd  test    rcx, rcx
0x1800392d0  jnz     short loc_180039313
0x1800392d2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800392d8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800392df  mov     rcx, rax
0x1800392e2  test    rax, rax
0x1800392e5  jz      short loc_180039305
0x1800392e7  mov     rax, [rax]
0x1800392ea  mov     edx, 7F0h
0x1800392ef  mov     rax, [rax+8]
0x1800392f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800392f8  test    eax, eax
0x1800392fa  jz      short loc_180039305
0x1800392fc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039303  jmp     short loc_180039313
0x180039305  lea     rcx, qword_180069A90; this
0x18003930c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180039313  cmp     byte ptr [rcx+8], 0
0x180039317  jz      short loc_18003933E
0x180039319  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003931e  cmp     [rax+7CCh], ebx
0x180039324  jz      short loc_18003933E
0x180039326  mov     r9d, ebx; int
0x180039329  lea     rdx, aCtranscodeprof_11; "CTranscodeProfileAdjuster::AdjustInterl"...
0x180039330  mov     r8d, 343h; int
0x180039336  mov     rcx, rax; this
0x180039339  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003933e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039343  cmp     al, 1
0x180039345  jb      loc_18003942D
0x18003934b  mov     edx, 84h
0x180039350  jmp     loc_18003940F
0x180039355  cmp     dword ptr [rsp+38h+arg_8], 0
0x18003935a  jnz     loc_18003942D
0x180039360  mov     rax, [rdi]
0x180039363  lea     rdx, MF_MT_INTERLACE_MODE
0x18003936a  mov     r8d, 2
0x180039370  mov     rcx, rdi
0x180039373  mov     rax, [rax+0A8h]
0x18003937a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003937f  mov     ebx, eax
0x180039381  test    eax, eax
0x180039383  jns     loc_18003942D
0x180039389  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180039390  test    rcx, rcx
0x180039393  jnz     short loc_1800393D6
0x180039395  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003939b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800393a2  mov     rcx, rax
0x1800393a5  test    rax, rax
0x1800393a8  jz      short loc_1800393C8
0x1800393aa  mov     rax, [rax]
0x1800393ad  mov     edx, 7F0h
0x1800393b2  mov     rax, [rax+8]
0x1800393b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393bb  test    eax, eax
0x1800393bd  jz      short loc_1800393C8
0x1800393bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800393c6  jmp     short loc_1800393D6
0x1800393c8  lea     rcx, qword_180069A90; this
0x1800393cf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800393d6  cmp     byte ptr [rcx+8], 0
0x1800393da  jz      short loc_180039401
0x1800393dc  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800393e1  cmp     [rax+7CCh], ebx
0x1800393e7  jz      short loc_180039401
0x1800393e9  mov     r9d, ebx; int
0x1800393ec  lea     rdx, aCtranscodeprof_11; "CTranscodeProfileAdjuster::AdjustInterl"...
0x1800393f3  mov     r8d, 347h; int
0x1800393f9  mov     rcx, rax; this
0x1800393fc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180039401  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180039406  cmp     al, 1
0x180039408  jb      short loc_18003942D
0x18003940a  mov     edx, 85h
0x18003940f  mov     rcx, cs:WPP_GLOBAL_Control
0x180039416  lea     r8, WPP_7323fa1d205d3639363ffe4ea0f1152b_Traceguids
0x18003941d  mov     r9, rsi
0x180039420  mov     [rsp+38h+var_18], ebx
0x180039424  mov     rcx, [rcx+10h]
0x180039428  call    WPP_SF_qd
0x18003942d  lea     rcx, [rsp+38h+arg_8]; this
0x180039432  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180039437  mov     rsi, [rsp+38h+arg_10]
0x18003943c  mov     eax, ebx
0x18003943e  mov     rbx, [rsp+38h+arg_0]
0x180039443  add     rsp, 30h
0x180039447  pop     rdi
0x180039448  retn
```
