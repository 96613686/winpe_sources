# CAudEngineStream::CMFPump::Start(int)

- ea: `0x1800d44e0`
- end: `0x1800d49e2`
- name: `?Start@CMFPump@CAudEngineStream@@QEAAJH@Z`
- size: `1282`
- prototype: `__int64 __fastcall(CAudEngineStream::CMFPump *__hidden this, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800d362c`
- `0x1801cfe08`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180045dbc`
- `0x18004d118`
- `0x180050d6c`
- `0x180063f00`
- `0x18007e198`
- `0x18007ff74`
- `0x1800d44e0`
- `0x1800ec0e0`
- `0x1802debc4`
- `0x180344d40`

## import_xrefs

- `MFPlat!MFScheduleWorkItem` at `0x1800d48a8`
- `MFPlat!MFScheduleWorkItem` at `0x1800d48a8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d46ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d4799`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d4854`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d48ca`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d46ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d4799`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d4854`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800d48ca`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800d4777`
- `MFPlat!MFPutWaitingWorkItem` at `0x1800d4777`
- `MFPlat!MFCreateAsyncResult` at `0x1800d4590`
- `MFPlat!MFCreateAsyncResult` at `0x1800d4698`
- `MFPlat!MFCreateAsyncResult` at `0x1800d4590`
- `MFPlat!MFCreateAsyncResult` at `0x1800d4698`

## pseudocode

```c
__int64 __fastcall CAudEngineStream::CMFPump::Start(IMFAsyncCallback *this, int a2)
{
  CAudEngineStream **v4; // rdi
  int v5; // ecx
  IMFAsyncResult **v6; // r9
  HRESULT updated; // ebx
  CallStackTracing *v8; // rcx
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v10; // rdx
  CallStackTracing *v11; // rcx
  struct CallStackContext *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 *v21; // rcx
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 *v26; // rcx
  CallStackTracing *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 *v30; // rcx
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  struct CallStackContext *v33; // rax
  IMFAsyncResult *ppAsyncResult; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)&ppAsyncResult,
    "CAudEngineStream::CMFPump::Start",
    3126);
  v4 = (CAudEngineStream **)&this[10];
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
  {
    if ( *v4 )
      v5 = *((_DWORD *)*v4 + 100);
    else
      v5 = 0;
    McTemplateU0pdt_EventWriteTransfer(v5, (unsigned int)&AudEngineStream_CMFPump_Start_Enter, (_DWORD)this, a2, v5);
  }
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 175, &WPP_e3f49d9e8cae38d0170890cbbde54fb5_Traceguids, this, *v4);
  v6 = (IMFAsyncResult **)((char *)*v4 + 440);
  if ( !*v6 )
  {
    updated = MFCreateAsyncResult(0, (IMFAsyncCallback *)*v4 + 65, 0, v6);
    if ( updated < 0 )
    {
      v8 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v8 = CallStackTracing::s_wpInstance;
      }
      if ( *((_BYTE *)v8 + 8) )
      {
        ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(v8);
        if ( *((_DWORD *)ThreadRelativeContext + 499) != updated )
          CallStackContext::TraceFailure(ThreadRelativeContext, "CAudEngineStream::CMFPump::Start", 3139, updated);
      }
      if ( g_wppLevels )
      {
        v10 = 176;
LABEL_74:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          &WPP_e3f49d9e8cae38d0170890cbbde54fb5_Traceguids,
          this,
          updated);
        goto LABEL_75;
      }
      goto LABEL_75;
    }
  }
  LODWORD(this[2].lpVtbl) = 0;
  if ( !a2 || (updated = CAudEngineStream::FillRenderBuffer(*v4, 1, 0), updated >= 0) )
  {
    if ( *((_DWORD *)*v4 + 100) )
    {
      ppAsyncResult = 0;
      updated = MFCreateAsyncResult(0, this + 12, 0, &ppAsyncResult);
      if ( updated < 0 )
      {
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v13, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( *((_DWORD *)v17 + 499) != updated )
            CallStackContext::TraceFailure(v17, "CAudEngineStream::CMFPump::Start", 3153, updated);
        }
        if ( !g_wppLevels )
          goto LABEL_39;
        v18 = 178;
LABEL_38:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          &WPP_e3f49d9e8cae38d0170890cbbde54fb5_Traceguids,
          this,
          updated);
LABEL_39:
        ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppAsyncResult);
        goto LABEL_75;
      }
      updated = MFPutWaitingWorkItem(*((HANDLE *)*v4 + 49), 1, ppAsyncResult, (MFWORKITEM_KEY *)this);
      if ( updated < 0 )
      {
        v21 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20);
          CallStackTracing::s_wpInstance = v22;
          if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
          {
            v21 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v21 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v21 + 8) )
        {
          v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v21);
          if ( *((_DWORD *)v23 + 499) != updated )
            CallStackContext::TraceFailure(v23, "CAudEngineStream::CMFPump::Start", 3154, updated);
        }
        if ( !g_wppLevels )
          goto LABEL_39;
        v18 = 179;
        goto LABEL_38;
      }
      ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&ppAsyncResult);
    }
    else
    {
      updated = MFScheduleWorkItem(this + 12, 0, -(__int64)*((unsigned int *)*v4 + 40), (MFWORKITEM_KEY *)this);
      if ( updated < 0 )
      {
        v30 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v28, v29);
          CallStackTracing::s_wpInstance = v31;
          if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
          {
            v30 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v30 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v30 + 8) )
        {
          v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v30);
          if ( *((_DWORD *)v32 + 499) != updated )
            CallStackContext::TraceFailure(v32, "CAudEngineStream::CMFPump::Start", 3158, updated);
        }
        if ( g_wppLevels )
        {
          v10 = 180;
          goto LABEL_74;
        }
        goto LABEL_75;
      }
    }
    updated = CAudEngineStream::CMFPump::UpdateDeadline_Relative(
                (CAudEngineStream::CMFPump *)this,
                *((_DWORD *)*v4 + 40));
    if ( updated < 0 )
    {
      v26 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v24, v25);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v26 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v26 + 8) )
      {
        v33 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v26);
        if ( *((_DWORD *)v33 + 499) != updated )
          CallStackContext::TraceFailure(v33, "CAudEngineStream::CMFPump::Start", 3160, updated);
      }
      if ( g_wppLevels )
      {
        v10 = 181;
        goto LABEL_74;
      }
    }
    goto LABEL_75;
  }
  v11 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v11 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v12 = CallStackTracing::GetThreadRelativeContext(v11);
    if ( *((_DWORD *)v12 + 499) != updated )
      CallStackContext::TraceFailure(v12, "CAudEngineStream::CMFPump::Start", 3146, updated);
  }
  if ( g_wppLevels )
  {
    v10 = 177;
    goto LABEL_74;
  }
LABEL_75:
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudEngineStream_CMFPump_Start_Exit,
      this,
      (unsigned int)updated);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&ppAsyncResult);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800d44e0  push    rbx
0x1800d44e2  push    rbp
0x1800d44e3  push    rsi
0x1800d44e4  push    rdi
0x1800d44e5  push    r12
0x1800d44e7  push    r13
0x1800d44e9  sub     rsp, 38h
0x1800d44ed  mov     ebp, edx
0x1800d44ef  lea     r13, aCaudenginestre_1; "CAudEngineStream::CMFPump::Start"
0x1800d44f6  mov     rsi, rcx
0x1800d44f9  mov     rdx, r13; char *
0x1800d44fc  mov     r8d, 0C36h; int
0x1800d4502  lea     rcx, [rsp+68h+ppAsyncResult]; this
0x1800d4507  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800d450c  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x1800d4513  lea     rdi, [rsi+50h]
0x1800d4517  jz      short loc_1800D4541
0x1800d4519  mov     rax, [rdi]
0x1800d451c  test    rax, rax
0x1800d451f  jz      short loc_1800D4529
0x1800d4521  mov     ecx, [rax+190h]
0x1800d4527  jmp     short loc_1800D452B
0x1800d4529  xor     ecx, ecx
0x1800d452b  mov     r9d, ebp
0x1800d452e  mov     dword ptr [rsp+68h+var_48], ecx
0x1800d4532  mov     r8, rsi
0x1800d4535  lea     rdx, AudEngineStream_CMFPump_Start_Enter
0x1800d453c  call    McTemplateU0pdt_EventWriteTransfer
0x1800d4541  cmp     cs:byte_1803CECE9, 10h
0x1800d4548  lea     r12, WPP_e3f49d9e8cae38d0170890cbbde54fb5_Traceguids
0x1800d454f  jb      short loc_1800D4574
0x1800d4551  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4558  mov     edx, 0AFh
0x1800d455d  mov     rax, [rdi]
0x1800d4560  mov     r9, rsi
0x1800d4563  mov     r8, r12
0x1800d4566  mov     [rsp+68h+var_48], rax
0x1800d456b  mov     rcx, [rcx+38h]
0x1800d456f  call    WPP_SF_qq
0x1800d4574  mov     rdx, [rdi]
0x1800d4577  lea     r9, [rdx+1B8h]; ppAsyncResult
0x1800d457e  cmp     qword ptr [r9], 0
0x1800d4582  jnz     short loc_1800D45F8
0x1800d4584  add     rdx, 208h; pCallback
0x1800d458b  xor     r8d, r8d; punkState
0x1800d458e  xor     ecx, ecx; punkObject
0x1800d4590  call    cs:__imp_MFCreateAsyncResult
0x1800d4597  nop     dword ptr [rax+rax+00h]
0x1800d459c  mov     ebx, eax
0x1800d459e  test    eax, eax
0x1800d45a0  jns     short loc_1800D45F8
0x1800d45a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d45a9  test    rcx, rcx
0x1800d45ac  jnz     short loc_1800D45BA
0x1800d45ae  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800d45b3  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d45ba  cmp     byte ptr [rcx+8], 0
0x1800d45be  jz      short loc_1800D45E1
0x1800d45c0  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d45c5  cmp     [rax+7CCh], ebx
0x1800d45cb  jz      short loc_1800D45E1
0x1800d45cd  mov     r9d, ebx; int
0x1800d45d0  mov     r8d, 0C43h; int
0x1800d45d6  mov     rdx, r13; char *
0x1800d45d9  mov     rcx, rax; this
0x1800d45dc  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d45e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d45e8  jb      loc_1800D49A6
0x1800d45ee  mov     edx, 0B0h
0x1800d45f3  jmp     loc_1800D498C
0x1800d45f8  mov     dword ptr [rsi+10h], 0
0x1800d45ff  test    ebp, ebp
0x1800d4601  jz      short loc_1800D466E
0x1800d4603  mov     rcx, [rdi]; this
0x1800d4606  xor     r8d, r8d; int *
0x1800d4609  lea     edx, [r8+1]; int
0x1800d460d  call    ?FillRenderBuffer@CAudEngineStream@@QEAAJHPEAJ@Z; CAudEngineStream::FillRenderBuffer(int,long *)
0x1800d4612  mov     ebx, eax
0x1800d4614  test    eax, eax
0x1800d4616  jns     short loc_1800D466E
0x1800d4618  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d461f  test    rcx, rcx
0x1800d4622  jnz     short loc_1800D4630
0x1800d4624  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800d4629  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800d4630  cmp     byte ptr [rcx+8], 0
0x1800d4634  jz      short loc_1800D4657
0x1800d4636  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d463b  cmp     [rax+7CCh], ebx
0x1800d4641  jz      short loc_1800D4657
0x1800d4643  mov     r9d, ebx; int
0x1800d4646  mov     r8d, 0C4Ah; int
0x1800d464c  mov     rdx, r13; char *
0x1800d464f  mov     rcx, rax; this
0x1800d4652  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d4657  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d465e  jb      loc_1800D49A6
0x1800d4664  mov     edx, 0B1h
0x1800d4669  jmp     loc_1800D498C
0x1800d466e  mov     rax, [rdi]
0x1800d4671  lea     rcx, [rsi+60h]; pCallback
0x1800d4675  cmp     dword ptr [rax+190h], 0
0x1800d467c  jz      loc_1800D4899
0x1800d4682  mov     rdx, rcx; pCallback
0x1800d4685  mov     [rsp+68h+ppAsyncResult], 0
0x1800d468e  xor     ecx, ecx; punkObject
0x1800d4690  lea     r9, [rsp+68h+ppAsyncResult]; ppAsyncResult
0x1800d4695  xor     r8d, r8d; punkState
0x1800d4698  call    cs:__imp_MFCreateAsyncResult
0x1800d469f  nop     dword ptr [rax+rax+00h]
0x1800d46a4  mov     ebx, eax
0x1800d46a6  test    eax, eax
0x1800d46a8  jns     loc_1800D4760
0x1800d46ae  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d46b5  test    rcx, rcx
0x1800d46b8  jnz     short loc_1800D4702
0x1800d46ba  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d46c1  nop     dword ptr [rax+rax+00h]
0x1800d46c6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d46cd  mov     rcx, rax
0x1800d46d0  test    rax, rax
0x1800d46d3  jz      short loc_1800D46F4
0x1800d46d5  mov     rax, [rax]
0x1800d46d8  mov     edx, 7F0h
0x1800d46dd  mov     rax, [rax+8]
0x1800d46e1  call    cs:__guard_dispatch_icall_fptr
0x1800d46e7  test    eax, eax
0x1800d46e9  jz      short loc_1800D46F4
0x1800d46eb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d46f2  jmp     short loc_1800D4702
0x1800d46f4  lea     rcx, qword_1803CE250; this
0x1800d46fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d4702  cmp     byte ptr [rcx+8], 0
0x1800d4706  jz      short loc_1800D4729
0x1800d4708  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d470d  cmp     [rax+7CCh], ebx
0x1800d4713  jz      short loc_1800D4729
0x1800d4715  mov     r9d, ebx; int
0x1800d4718  mov     r8d, 0C51h; int
0x1800d471e  mov     rdx, r13; char *
0x1800d4721  mov     rcx, rax; this
0x1800d4724  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d4729  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d4730  jb      short loc_1800D4751
0x1800d4732  mov     edx, 0B2h
0x1800d4737  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d473e  mov     r9, rsi
0x1800d4741  mov     r8, r12
0x1800d4744  mov     dword ptr [rsp+68h+var_48], ebx
0x1800d4748  mov     rcx, [rcx+10h]
0x1800d474c  call    WPP_SF_qD
0x1800d4751  lea     rcx, [rsp+68h+ppAsyncResult]
0x1800d4756  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800d475b  jmp     loc_1800D49A6
0x1800d4760  mov     rcx, [rdi]
0x1800d4763  mov     r9, rsi; pKey
0x1800d4766  mov     r8, [rsp+68h+ppAsyncResult]; pResult
0x1800d476b  mov     edx, 1; Priority
0x1800d4770  mov     rcx, [rcx+188h]; hEvent
0x1800d4777  call    cs:__imp_MFPutWaitingWorkItem
0x1800d477e  nop     dword ptr [rax+rax+00h]
0x1800d4783  mov     ebx, eax
0x1800d4785  test    eax, eax
0x1800d4787  jns     loc_1800D481F
0x1800d478d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d4794  test    rcx, rcx
0x1800d4797  jnz     short loc_1800D47E1
0x1800d4799  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d47a0  nop     dword ptr [rax+rax+00h]
0x1800d47a5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d47ac  mov     rcx, rax
0x1800d47af  test    rax, rax
0x1800d47b2  jz      short loc_1800D47D3
0x1800d47b4  mov     rax, [rax]
0x1800d47b7  mov     edx, 7F0h
0x1800d47bc  mov     rax, [rax+8]
0x1800d47c0  call    cs:__guard_dispatch_icall_fptr
0x1800d47c6  test    eax, eax
0x1800d47c8  jz      short loc_1800D47D3
0x1800d47ca  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d47d1  jmp     short loc_1800D47E1
0x1800d47d3  lea     rcx, qword_1803CE250; this
0x1800d47da  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d47e1  cmp     byte ptr [rcx+8], 0
0x1800d47e5  jz      short loc_1800D4808
0x1800d47e7  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d47ec  cmp     [rax+7CCh], ebx
0x1800d47f2  jz      short loc_1800D4808
0x1800d47f4  mov     r9d, ebx; int
0x1800d47f7  mov     r8d, 0C52h; int
0x1800d47fd  mov     rdx, r13; char *
0x1800d4800  mov     rcx, rax; this
0x1800d4803  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d4808  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d480f  jb      loc_1800D4751
0x1800d4815  mov     edx, 0B3h
0x1800d481a  jmp     loc_1800D4737
0x1800d481f  lea     rcx, [rsp+68h+ppAsyncResult]
0x1800d4824  call    ??1?$ComSmartPtr@UIMFTransform@@@@QEAA@XZ; ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(void)
0x1800d4829  mov     rdx, [rdi]
0x1800d482c  mov     rcx, rsi; this
0x1800d482f  mov     edx, [rdx+0A0h]; int
0x1800d4835  call    ?UpdateDeadline_Relative@CMFPump@CAudEngineStream@@QEAAJJ@Z; CAudEngineStream::CMFPump::UpdateDeadline_Relative(long)
0x1800d483a  mov     ebx, eax
0x1800d483c  test    eax, eax
0x1800d483e  jns     loc_1800D49A6
0x1800d4844  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d484b  test    rcx, rcx
0x1800d484e  jnz     loc_1800D4957
0x1800d4854  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d485b  nop     dword ptr [rax+rax+00h]
0x1800d4860  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d4867  mov     rcx, rax
0x1800d486a  test    rax, rax
0x1800d486d  jz      loc_1800D4949
0x1800d4873  mov     rax, [rax]
0x1800d4876  mov     edx, 7F0h
0x1800d487b  mov     rax, [rax+8]
0x1800d487f  call    cs:__guard_dispatch_icall_fptr
0x1800d4885  test    eax, eax
0x1800d4887  jz      loc_1800D4949
0x1800d488d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d4894  jmp     loc_1800D4957
0x1800d4899  mov     r8d, [rax+0A0h]
0x1800d48a0  mov     r9, rsi; pKey
0x1800d48a3  neg     r8; Timeout
0x1800d48a6  xor     edx, edx; pState
0x1800d48a8  call    cs:__imp_MFScheduleWorkItem
0x1800d48af  nop     dword ptr [rax+rax+00h]
0x1800d48b4  mov     ebx, eax
0x1800d48b6  test    eax, eax
0x1800d48b8  jns     loc_1800D4829
0x1800d48be  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d48c5  test    rcx, rcx
0x1800d48c8  jnz     short loc_1800D4912
0x1800d48ca  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800d48d1  nop     dword ptr [rax+rax+00h]
0x1800d48d6  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d48dd  mov     rcx, rax
0x1800d48e0  test    rax, rax
0x1800d48e3  jz      short loc_1800D4904
0x1800d48e5  mov     rax, [rax]
0x1800d48e8  mov     edx, 7F0h
0x1800d48ed  mov     rax, [rax+8]
0x1800d48f1  call    cs:__guard_dispatch_icall_fptr
0x1800d48f7  test    eax, eax
0x1800d48f9  jz      short loc_1800D4904
0x1800d48fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d4902  jmp     short loc_1800D4912
0x1800d4904  lea     rcx, qword_1803CE250; this
0x1800d490b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d4912  cmp     byte ptr [rcx+8], 0
0x1800d4916  jz      short loc_1800D4939
0x1800d4918  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d491d  cmp     [rax+7CCh], ebx
0x1800d4923  jz      short loc_1800D4939
0x1800d4925  mov     r9d, ebx; int
0x1800d4928  mov     r8d, 0C56h; int
0x1800d492e  mov     rdx, r13; char *
0x1800d4931  mov     rcx, rax; this
0x1800d4934  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d4939  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d4940  jb      short loc_1800D49A6
0x1800d4942  mov     edx, 0B4h
0x1800d4947  jmp     short loc_1800D498C
0x1800d4949  lea     rcx, qword_1803CE250; this
0x1800d4950  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800d4957  cmp     byte ptr [rcx+8], 0
0x1800d495b  jz      short loc_1800D497E
0x1800d495d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800d4962  cmp     [rax+7CCh], ebx
0x1800d4968  jz      short loc_1800D497E
0x1800d496a  mov     r9d, ebx; int
0x1800d496d  mov     r8d, 0C58h; int
0x1800d4973  mov     rdx, r13; char *
0x1800d4976  mov     rcx, rax; this
0x1800d4979  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800d497e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800d4985  jb      short loc_1800D49A6
0x1800d4987  mov     edx, 0B5h
0x1800d498c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d4993  mov     r9, rsi
0x1800d4996  mov     r8, r12
0x1800d4999  mov     dword ptr [rsp+68h+var_48], ebx
0x1800d499d  mov     rcx, [rcx+10h]
0x1800d49a1  call    WPP_SF_qD
0x1800d49a6  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x1800d49ad  jz      short loc_1800D49C8
0x1800d49af  mov     r9d, ebx
0x1800d49b2  lea     rdx, AudEngineStream_CMFPump_Start_Exit
0x1800d49b9  mov     r8, rsi
0x1800d49bc  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x1800d49c3  call    McTemplateU0pq_EventWriteTransfer
0x1800d49c8  lea     rcx, [rsp+68h+ppAsyncResult]; this
0x1800d49cd  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800d49d2  mov     eax, ebx
0x1800d49d4  add     rsp, 38h
0x1800d49d8  pop     r13
0x1800d49da  pop     r12
0x1800d49dc  pop     rdi
  ... truncated ...
```
