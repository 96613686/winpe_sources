# CSceneAnalysisMFT::remove_SceneAnalyzed(EventRegistrationToken)

- ea: `0x1800b1220`
- end: `0x1800b133a`
- name: `?remove_SceneAnalyzed@CSceneAnalysisMFT@@UEAAJUEventRegistrationToken@@@Z`
- size: `282`
- prototype: `__int64 __fastcall(CSceneAnalysisMFT *__hidden this, struct EventRegistrationToken)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180009784`
- `0x18000b490`
- `0x18000c0f8`
- `0x180017784`
- `0x18002a9bc`
- `0x18002ae0c`
- `0x18002afd0`
- `0x1800b1220`
- `0x18012f850`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1327`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800b1327`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1277`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800b1277`

## string_xrefs

- `0x1800b1244`: `CSceneAnalysisMFT::remove_SceneAnalyzed`
- `0x1800b12ce`: `CSceneAnalysisMFT::remove_SceneAnalyzed`

## pseudocode

```c
__int64 __fastcall CSceneAnalysisMFT::remove_SceneAnalyzed(CSceneAnalysisMFT *this, struct EventRegistrationToken a2)
{
  int v4; // ebx
  __int64 *v5; // rcx
  CallStackTracing *v6; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v9; // [rsp+40h] [rbp+8h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+18h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 48);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v9, "CSceneAnalysisMFT::remove_SceneAnalyzed", 174);
  v4 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Core::FaceDetectionEffect *,Windows::Media::Core::FaceDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::Remove(
         (char *)this + 88,
         a2.value);
  if ( v4 < 0 )
  {
    v5 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v6 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v6;
      if ( v6 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v6 + 8LL))(v6, 2032) )
      {
        v5 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v5 = &qword_18015FF10;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18015FF10;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v5);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v4 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CSceneAnalysisMFT::remove_SceneAnalyzed", 175, v4);
    }
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        &WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids,
        (char *)this - 312,
        v4);
  }
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v9);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b1220  mov     [rsp+arg_8], rbx
0x1800b1225  push    rdi
0x1800b1226  sub     rsp, 30h
0x1800b122a  mov     rbx, rdx
0x1800b122d  mov     rdi, rcx
0x1800b1230  lea     rdx, [rcx+30h]
0x1800b1234  lea     rcx, [rsp+38h+SRWLock]
0x1800b1239  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800b123e  mov     r8d, 0AEh; int
0x1800b1244  lea     rdx, aCsceneanalysis_21; "CSceneAnalysisMFT::remove_SceneAnalyzed"
0x1800b124b  lea     rcx, [rsp+38h+arg_0]; this
0x1800b1250  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800b1255  lea     rcx, [rdi+58h]
0x1800b1259  mov     rdx, rbx
0x1800b125c  call    ?Remove@?$EventSource@U?$ITypedEventHandler@PEAVFaceDetectionEffect@Core@Media@Windows@@PEAVFaceDetectedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Media::Core::FaceDetectionEffect *,Windows::Media::Core::FaceDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::Remove(EventRegistrationToken)
0x1800b1261  mov     ebx, eax
0x1800b1263  test    eax, eax
0x1800b1265  jns     loc_1800B1313
0x1800b126b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1272  test    rcx, rcx
0x1800b1275  jnz     short loc_1800B12B8
0x1800b1277  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800b127d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b1284  mov     rcx, rax
0x1800b1287  test    rax, rax
0x1800b128a  jz      short loc_1800B12AA
0x1800b128c  mov     rax, [rax]
0x1800b128f  mov     edx, 7F0h
0x1800b1294  mov     rax, [rax+8]
0x1800b1298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b129d  test    eax, eax
0x1800b129f  jz      short loc_1800B12AA
0x1800b12a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b12a8  jmp     short loc_1800B12B8
0x1800b12aa  lea     rcx, qword_18015FF10; this
0x1800b12b1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800b12b8  cmp     byte ptr [rcx+8], 0
0x1800b12bc  jz      short loc_1800B12E3
0x1800b12be  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800b12c3  cmp     [rax+7CCh], ebx
0x1800b12c9  jz      short loc_1800B12E3
0x1800b12cb  mov     r9d, ebx; int
0x1800b12ce  lea     rdx, aCsceneanalysis_21; "CSceneAnalysisMFT::remove_SceneAnalyzed"
0x1800b12d5  mov     r8d, 0AFh; int
0x1800b12db  mov     rcx, rax; this
0x1800b12de  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800b12e3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800b12e8  cmp     al, 1
0x1800b12ea  jb      short loc_1800B1313
0x1800b12ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b12f3  lea     r9, [rdi-138h]
0x1800b12fa  mov     edx, 21h ; '!'
0x1800b12ff  mov     [rsp+38h+var_18], ebx
0x1800b1303  lea     r8, WPP_a042ef2f2a7a38ff6a18b622801eb737_Traceguids
0x1800b130a  mov     rcx, [rcx+10h]
0x1800b130e  call    WPP_SF_qD
0x1800b1313  lea     rcx, [rsp+38h+arg_0]; this
0x1800b1318  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800b131d  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800b1322  test    rcx, rcx
0x1800b1325  jz      short loc_1800B132D
0x1800b1327  call    cs:__imp_ReleaseSRWLockExclusive
0x1800b132d  mov     eax, ebx
0x1800b132f  mov     rbx, [rsp+38h+arg_8]
0x1800b1334  add     rsp, 30h
0x1800b1338  pop     rdi
0x1800b1339  retn
```
