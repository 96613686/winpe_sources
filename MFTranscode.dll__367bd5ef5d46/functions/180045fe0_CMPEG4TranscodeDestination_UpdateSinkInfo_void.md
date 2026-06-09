# CMPEG4TranscodeDestination::UpdateSinkInfo(void)

- ea: `0x180045fe0`
- end: `0x1800461fc`
- name: `?UpdateSinkInfo@CMPEG4TranscodeDestination@@MEAAJXZ`
- size: `540`
- prototype: `__int64 __fastcall(CMPEG4TranscodeDestination *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000a420`

## callees

- `0x1800035c0`
- `0x180004a40`
- `0x180007000`
- `0x18000a3f4`
- `0x18001a330`
- `0x18001c280`
- `0x180045fe0`
- `0x180046204`
- `0x18004f410`
- `0x18005a010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004603e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046154`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004603e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180046154`

## string_xrefs

- `0x180045fed`: `CMPEG4TranscodeDestination::UpdateSinkInfo`
- `0x180046095`: `CMPEG4TranscodeDestination::UpdateSinkInfo`
- `0x1800461ab`: `CMPEG4TranscodeDestination::UpdateSinkInfo`

## pseudocode

```c
__int64 __fastcall CMPEG4TranscodeDestination::UpdateSinkInfo(CMPEG4TranscodeDestination *this)
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v3; // rdx
  int v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 *v12; // rcx
  CallStackTracing *v13; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v16; // [rsp+40h] [rbp+8h] BYREF
  __int64 v17; // [rsp+48h] [rbp+10h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&v16,
    "CMPEG4TranscodeDestination::UpdateSinkInfo",
    42);
  v2 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 7);
  v17 = 0;
  v4 = (**v2)(v2, &IID_IMFTranscodeSinkInfoProvider, &v17);
  if ( v4 >= 0 )
  {
    v9 = *(_QWORD *)(*((_QWORD *)this + 8) + 8LL);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *(_QWORD *)(*((_QWORD *)this + 8) + 8LL) = 0;
    }
    v10 = *(_QWORD *)(*((_QWORD *)this + 8) + 24LL);
    if ( v10 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      *(_QWORD *)(*((_QWORD *)this + 8) + 24LL) = 0;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 48LL))(v17, *((_QWORD *)this + 8));
    if ( v4 >= 0 )
    {
      CMPEG4TranscodeDestination::UpdateStreamID(this);
      goto LABEL_29;
    }
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
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMPEG4TranscodeDestination::UpdateSinkInfo", 52, v4);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 12;
      goto LABEL_12;
    }
  }
  else
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v3);
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_180069A90;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180069A90;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v7 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)v7 + 499) != v4 )
        CallStackContext::TraceFailure(v7, "CMPEG4TranscodeDestination::UpdateSinkInfo", 47, v4);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v8 = 11;
LABEL_12:
      WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, WPP_8500b975b1173f2b6163c20b6fddb525_Traceguids, this, v4);
    }
  }
LABEL_29:
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v17);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v16);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180045fe0  mov     [rsp+arg_10], rbx
0x180045fe5  push    rdi
0x180045fe6  sub     rsp, 30h
0x180045fea  mov     rdi, rcx
0x180045fed  lea     rdx, aCmpeg4transcod; "CMPEG4TranscodeDestination::UpdateSinkI"...
0x180045ff4  lea     rcx, [rsp+38h+arg_0]; this
0x180045ff9  mov     r8d, 2Ah ; '*'; int
0x180045fff  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180046004  mov     rcx, [rdi+38h]
0x180046008  lea     r8, [rsp+38h+arg_8]
0x18004600d  mov     [rsp+38h+arg_8], 0
0x180046016  lea     rdx, IID_IMFTranscodeSinkInfoProvider
0x18004601d  mov     rax, [rcx]
0x180046020  mov     rax, [rax]
0x180046023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046028  mov     ebx, eax
0x18004602a  test    eax, eax
0x18004602c  jns     loc_1800460DF
0x180046032  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046039  test    rcx, rcx
0x18004603c  jnz     short loc_18004607F
0x18004603e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180046044  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004604b  mov     rcx, rax
0x18004604e  test    rax, rax
0x180046051  jz      short loc_180046071
0x180046053  mov     rax, [rax]
0x180046056  mov     edx, 7F0h
0x18004605b  mov     rax, [rax+8]
0x18004605f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046064  test    eax, eax
0x180046066  jz      short loc_180046071
0x180046068  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004606f  jmp     short loc_18004607F
0x180046071  lea     rcx, qword_180069A90; this
0x180046078  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004607f  cmp     byte ptr [rcx+8], 0
0x180046083  jz      short loc_1800460AA
0x180046085  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004608a  cmp     [rax+7CCh], ebx
0x180046090  jz      short loc_1800460AA
0x180046092  mov     r9d, ebx; int
0x180046095  lea     rdx, aCmpeg4transcod; "CMPEG4TranscodeDestination::UpdateSinkI"...
0x18004609c  mov     r8d, 2Fh ; '/'; int
0x1800460a2  mov     rcx, rax; this
0x1800460a5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800460aa  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800460af  cmp     al, 1
0x1800460b1  jb      loc_1800461DB
0x1800460b7  mov     edx, 0Bh
0x1800460bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800460c3  lea     r8, WPP_8500b975b1173f2b6163c20b6fddb525_Traceguids
0x1800460ca  mov     r9, rdi
0x1800460cd  mov     [rsp+38h+var_18], ebx
0x1800460d1  mov     rcx, [rcx+10h]
0x1800460d5  call    WPP_SF_qd
0x1800460da  jmp     loc_1800461DB
0x1800460df  mov     rax, [rdi+40h]
0x1800460e3  mov     rcx, [rax+8]
0x1800460e7  test    rcx, rcx
0x1800460ea  jz      short loc_180046104
0x1800460ec  mov     rax, [rcx]
0x1800460ef  mov     rax, [rax+10h]
0x1800460f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800460f8  mov     rax, [rdi+40h]
0x1800460fc  mov     qword ptr [rax+8], 0
0x180046104  mov     rax, [rdi+40h]
0x180046108  mov     rcx, [rax+18h]
0x18004610c  test    rcx, rcx
0x18004610f  jz      short loc_180046129
0x180046111  mov     rax, [rcx]
0x180046114  mov     rax, [rax+10h]
0x180046118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004611d  mov     rax, [rdi+40h]
0x180046121  mov     qword ptr [rax+18h], 0
0x180046129  mov     rcx, [rsp+38h+arg_8]
0x18004612e  mov     rdx, [rdi+40h]
0x180046132  mov     rax, [rcx]
0x180046135  mov     rax, [rax+30h]
0x180046139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004613e  mov     ebx, eax
0x180046140  test    eax, eax
0x180046142  jns     loc_1800461D3
0x180046148  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004614f  test    rcx, rcx
0x180046152  jnz     short loc_180046195
0x180046154  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004615a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180046161  mov     rcx, rax
0x180046164  test    rax, rax
0x180046167  jz      short loc_180046187
0x180046169  mov     rax, [rax]
0x18004616c  mov     edx, 7F0h
0x180046171  mov     rax, [rax+8]
0x180046175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004617a  test    eax, eax
0x18004617c  jz      short loc_180046187
0x18004617e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180046185  jmp     short loc_180046195
0x180046187  lea     rcx, qword_180069A90; this
0x18004618e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180046195  cmp     byte ptr [rcx+8], 0
0x180046199  jz      short loc_1800461C0
0x18004619b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800461a0  cmp     [rax+7CCh], ebx
0x1800461a6  jz      short loc_1800461C0
0x1800461a8  mov     r9d, ebx; int
0x1800461ab  lea     rdx, aCmpeg4transcod; "CMPEG4TranscodeDestination::UpdateSinkI"...
0x1800461b2  mov     r8d, 34h ; '4'; int
0x1800461b8  mov     rcx, rax; this
0x1800461bb  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800461c0  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800461c5  cmp     al, 1
0x1800461c7  jb      short loc_1800461DB
0x1800461c9  mov     edx, 0Ch
0x1800461ce  jmp     loc_1800460BC
0x1800461d3  mov     rcx, rdi; this
0x1800461d6  call    ?UpdateStreamID@CMPEG4TranscodeDestination@@IEAAXXZ; CMPEG4TranscodeDestination::UpdateStreamID(void)
0x1800461db  lea     rcx, [rsp+38h+arg_8]
0x1800461e0  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800461e5  lea     rcx, [rsp+38h+arg_0]; this
0x1800461ea  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800461ef  mov     eax, ebx
0x1800461f1  mov     rbx, [rsp+38h+arg_10]
0x1800461f6  add     rsp, 30h
0x1800461fa  pop     rdi
0x1800461fb  retn
```
