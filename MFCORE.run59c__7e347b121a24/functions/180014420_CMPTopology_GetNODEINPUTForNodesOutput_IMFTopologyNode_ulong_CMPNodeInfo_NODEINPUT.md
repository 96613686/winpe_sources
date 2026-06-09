# CMPTopology::GetNODEINPUTForNodesOutput(IMFTopologyNode *,ulong,CMPNodeInfo::NODEINPUT * *)

- ea: `0x180014420`
- end: `0x180014afa`
- name: `?GetNODEINPUTForNodesOutput@CMPTopology@@SAJPEAUIMFTopologyNode@@KPEAPEAVNODEINPUT@CMPNodeInfo@@@Z`
- size: `1754`
- prototype: `__int64 __fastcall(struct IMFTopologyNode *, unsigned int, struct CMPNodeInfo::NODEINPUT **)`
- caller_count: `10`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f01c`
- `0x180013dd4`
- `0x180015a60`
- `0x18003d1b8`
- `0x180041eb0`
- `0x1800a19bc`
- `0x1801380e4`
- `0x1801d3c7c`
- `0x18022c6a4`
- `0x180286ee4`

## callees

- `0x180014420`
- `0x18001616c`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001460c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001483f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014877`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014474`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001454b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001460c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800147c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014803`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001483f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014877`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001449f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014639`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800146fa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001449f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014576`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014639`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800146fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180014485`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001455c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001461e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800146e0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180014485`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001455c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001461e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800146e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014795`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014757`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014795`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800148fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014986`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014a4c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800148fb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014986`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180014a4c`

## pseudocode

```c
__int64 __fastcall CMPTopology::GetNODEINPUTForNodesOutput(
        struct IMFTopologyNode *a1,
        unsigned int a2,
        struct CMPNodeInfo::NODEINPUT **a3)
{
  CallStackTracing *v3; // rdi
  char *v7; // rbx
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  struct IMFTopologyNodeVtbl *lpVtbl; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rsi
  CallStackTracing *v17; // rbx
  char *v18; // rdi
  DWORD v19; // ebp
  char *v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  _QWORD *v23; // rcx
  int v24; // esi
  _QWORD *v25; // rdi
  CallStackTracing *v26; // rbx
  GUID *v27; // rbp
  DWORD v28; // r15d
  GUID *v29; // rax
  int v30; // eax
  int v31; // eax
  CallStackTracing *v32; // rbx
  GUID *v33; // rdi
  DWORD v34; // ebp
  GUID *v35; // rax
  int v36; // eax
  int v37; // eax
  CallStackTracing *v39; // rcx
  __int64 v40; // rax
  CallStackTracing *v41; // rcx
  __int64 v42; // rax
  CallStackTracing *v43; // rcx
  __int64 v44; // rax
  CallStackTracing *v45; // rcx
  __int64 v46; // rax
  CallStackTracing *v47; // rax
  __int64 v48; // rdx
  struct CallStackContext *ThreadRelativeContext; // rax
  CallStackTracing *v50; // rax
  struct CallStackContext *v51; // rax
  CallStackTracing *v52; // rax
  struct CallStackContext *v53; // rax
  unsigned int v54; // [rsp+70h] [rbp+8h] BYREF
  __int64 v55; // [rsp+80h] [rbp+18h] BYREF
  _QWORD *v56; // [rsp+88h] [rbp+20h] BYREF

  v3 = CallStackTracing::s_wpInstance;
  v55 = 0;
  *a3 = 0;
  v54 = 0;
  if ( !v3 )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v7 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v39 = CallStackTracing::s_wpInstance;
      }
      v40 = (**(__int64 (__fastcall ***)(CallStackTracing *))v39)(v39);
      if ( v40 )
        v7 = (char *)v40;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CMPTopology::GetNODEINPUTForNodesOutput";
      *(_DWORD *)&v7[8 * v11 + 8] = 358;
    }
    ++*((_DWORD *)v7 + 497);
  }
  lpVtbl = a1->lpVtbl;
  v55 = 0;
  ((void (__fastcall *)(struct IMFTopologyNode *, _QWORD, __int64 *, unsigned int *))lpVtbl->GetOutput)(
    a1,
    a2,
    &v55,
    &v54);
  if ( !v55 )
  {
    v24 = 1;
    goto LABEL_34;
  }
  v16 = v55;
  v56 = 0;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v17 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v18 = (char *)CallStackTracing::s_wpInstance + 208;
    v19 = GetLastError();
    v20 = (char *)TlsGetValue(*((_DWORD *)v17 + 3));
    if ( v20 )
    {
      v18 = v20;
    }
    else if ( !GetLastError() )
    {
      v41 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v41 = CallStackTracing::s_wpInstance;
      }
      v42 = (**(__int64 (__fastcall ***)(CallStackTracing *))v41)(v41);
      if ( v42 )
        v18 = (char *)v42;
    }
    SetLastError(v19);
    v21 = *((unsigned int *)v18 + 497);
    if ( (unsigned int)v21 < *((_DWORD *)v18 + 498) )
    {
      v22 = 2 * v21;
      *(_QWORD *)&v18[8 * v22] = "CMPTopology::GetNodeInfo";
      *(_DWORD *)&v18[8 * v22 + 8] = 42;
    }
    ++*((_DWORD *)v18 + 497);
  }
  if ( !v16 )
  {
    v24 = -1072875845;
    if ( !CallStackTracing::s_wpInstance )
    {
      v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v14, v13, v15);
      CallStackTracing::s_wpInstance = v47;
      if ( !v47 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875845 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CMPTopology::GetNodeInfo", 42, -1072875845);
    }
    if ( !g_wppLevels )
      goto LABEL_82;
    v48 = 10;
    goto LABEL_81;
  }
  v24 = (*(__int64 (__fastcall **)(__int64, void *, GUID *, _QWORD **))(*(_QWORD *)v16 + 136LL))(
          v16,
          &unk_180361318,
          &IID_IUnknown,
          &v56);
  if ( v24 >= 0 )
  {
    v25 = v56;
    goto LABEL_21;
  }
  if ( !CallStackTracing::s_wpInstance )
  {
    v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v13, v15);
    CallStackTracing::s_wpInstance = v50;
    if ( !v50 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
  }
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v51 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    if ( *((_DWORD *)v51 + 499) != v24 )
      CallStackContext::TraceFailure(v51, "CMPTopology::GetNodeInfo", 46, v24);
  }
  if ( g_wppLevels )
  {
    v48 = 11;
LABEL_81:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, &WPP_29aaa605fb293c19ae3c305ffcfb96cb_Traceguids, 0, v24);
  }
LABEL_82:
  v23 = v56;
  v25 = 0;
  if ( !v56 )
    goto LABEL_22;
  (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
LABEL_21:
  v56 = 0;
LABEL_22:
  v26 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v27 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v28 = GetLastError();
    v29 = (GUID *)TlsGetValue(*((_DWORD *)v26 + 3));
    if ( v29 )
    {
      v27 = v29;
    }
    else if ( !GetLastError() )
    {
      v43 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v43 = CallStackTracing::s_wpInstance;
      }
      v44 = (**(__int64 (__fastcall ***)(CallStackTracing *))v43)(v43);
      if ( v44 )
        v27 = (GUID *)v44;
    }
    SetLastError(v28);
    v30 = *(_DWORD *)&v27[124].Data2;
    if ( v30 )
    {
      v31 = v30 - 1;
      *(_DWORD *)&v27[124].Data2 = v31;
      if ( !v31 )
      {
        *(_DWORD *)&v27[124].Data2 = 0;
        *(_QWORD *)&v27[126].Data1 = 0;
        *(_DWORD *)&v27[124].Data4[4] = 0;
        v27[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v27[126].Data4 = 0;
        v27[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  if ( v24 < 0 )
  {
    if ( !CallStackTracing::s_wpInstance )
    {
      v52 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v23, v13, v15);
      CallStackTracing::s_wpInstance = v52;
      if ( !v52 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v53 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      if ( *((_DWORD *)v53 + 499) != v24 )
        CallStackContext::TraceFailure(v53, "CMPTopology::GetNODEINPUTForNodesOutput", 366, v24);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_d12fa83e0e473261b9e1d6804a342fea_Traceguids, 0, v24);
  }
  else
  {
    *a3 = *(struct CMPNodeInfo::NODEINPUT **)(v25[3] + 8LL * v54);
  }
  if ( v55 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
    v55 = 0;
  }
  if ( v25 )
    (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
LABEL_34:
  v32 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v33 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v34 = GetLastError();
    v35 = (GUID *)TlsGetValue(*((_DWORD *)v32 + 3));
    if ( v35 )
    {
      v33 = v35;
    }
    else if ( !GetLastError() )
    {
      v45 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v45 = CallStackTracing::s_wpInstance;
      }
      v46 = (**(__int64 (__fastcall ***)(CallStackTracing *))v45)(v45);
      if ( v46 )
        v33 = (GUID *)v46;
    }
    SetLastError(v34);
    v36 = *(_DWORD *)&v33[124].Data2;
    if ( v36 )
    {
      v37 = v36 - 1;
      *(_DWORD *)&v33[124].Data2 = v37;
      if ( !v37 )
      {
        *(_DWORD *)&v33[124].Data2 = 0;
        *(_QWORD *)&v33[126].Data1 = 0;
        *(_DWORD *)&v33[124].Data4[4] = 0;
        v33[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v33[126].Data4 = 0;
        v33[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x180014420  mov     rax, rsp
0x180014423  push    rbx
0x180014424  push    rsi
0x180014425  push    rdi
0x180014426  push    r12
0x180014428  sub     rsp, 48h
0x18001442c  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014433  xor     r12d, r12d
0x180014436  mov     [rax-30h], r14
0x18001443a  mov     r14, r8
0x18001443d  mov     [rax-38h], r15
0x180014441  mov     r15d, edx
0x180014444  mov     [rax+18h], r12
0x180014448  mov     rsi, rcx
0x18001444b  mov     [r8], r12
0x18001444e  mov     [rax+8], r12d
0x180014452  test    rdi, rdi
0x180014455  jz      loc_1800147AC
0x18001445b  lea     rcx, aCmptopologyGet_5; "CMPTopology::GetNODEINPUTForNodesOutput"
0x180014462  mov     [rsp+68h+arg_8], rbp
0x180014467  cmp     [rdi+8], r12b
0x18001446b  jz      short loc_1800144D5
0x18001446d  lea     rbx, [rdi+0D0h]
0x180014474  call    cs:__imp_GetLastError
0x18001447b  nop     dword ptr [rax+rax+00h]
0x180014480  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180014483  mov     ebp, eax
0x180014485  call    cs:__imp_TlsGetValue
0x18001448c  nop     dword ptr [rax+rax+00h]
0x180014491  test    rax, rax
0x180014494  jz      loc_1800147C7
0x18001449a  mov     rbx, rax
0x18001449d  mov     ecx, ebp; dwErrCode
0x18001449f  call    cs:__imp_SetLastError
0x1800144a6  nop     dword ptr [rax+rax+00h]
0x1800144ab  mov     eax, [rbx+7C4h]
0x1800144b1  lea     rcx, aCmptopologyGet_5; "CMPTopology::GetNODEINPUTForNodesOutput"
0x1800144b8  cmp     eax, [rbx+7C8h]
0x1800144be  jnb     short loc_1800144CF
0x1800144c0  add     rax, rax
0x1800144c3  mov     [rbx+rax*8], rcx
0x1800144c7  mov     dword ptr [rbx+rax*8+8], 166h
0x1800144cf  inc     dword ptr [rbx+7C4h]
0x1800144d5  mov     rax, [rsi]
0x1800144d8  lea     r9, [rsp+68h+arg_0]
0x1800144dd  lea     r8, [rsp+68h+arg_10]
0x1800144e5  mov     [rsp+68h+arg_10], r12
0x1800144ed  mov     edx, r15d
0x1800144f0  mov     rcx, rsi
0x1800144f3  mov     rax, [rax+158h]
0x1800144fa  call    cs:__guard_dispatch_icall_fptr
0x180014500  cmp     [rsp+68h+arg_10], r12
0x180014508  jz      loc_180014AF0
0x18001450e  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180014515  mov     rsi, [rsp+68h+arg_10]
0x18001451d  mov     [rsp+68h+var_28], r13
0x180014522  mov     [rsp+68h+arg_18], r12
0x18001452a  jz      loc_1800147BD
0x180014530  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014537  lea     r15, aCmptopologyGet_7; "CMPTopology::GetNodeInfo"
0x18001453e  cmp     [rbx+8], r12b
0x180014542  jz      short loc_1800145A5
0x180014544  lea     rdi, [rbx+0D0h]
0x18001454b  call    cs:__imp_GetLastError
0x180014552  nop     dword ptr [rax+rax+00h]
0x180014557  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001455a  mov     ebp, eax
0x18001455c  call    cs:__imp_TlsGetValue
0x180014563  nop     dword ptr [rax+rax+00h]
0x180014568  test    rax, rax
0x18001456b  jz      loc_180014803
0x180014571  mov     rdi, rax
0x180014574  mov     ecx, ebp; dwErrCode
0x180014576  call    cs:__imp_SetLastError
0x18001457d  nop     dword ptr [rax+rax+00h]
0x180014582  mov     eax, [rdi+7C4h]
0x180014588  cmp     eax, [rdi+7C8h]
0x18001458e  jnb     short loc_18001459F
0x180014590  add     rax, rax
0x180014593  mov     [rdi+rax*8], r15
0x180014597  mov     dword ptr [rdi+rax*8+8], 2Ah ; '*'
0x18001459f  inc     dword ptr [rdi+7C4h]
0x1800145a5  lea     r13, qword_1803CE250
0x1800145ac  test    rsi, rsi
0x1800145af  jz      loc_1800148ED
0x1800145b5  mov     rax, [rsi]
0x1800145b8  lea     r9, [rsp+68h+arg_18]
0x1800145c0  lea     r8, IID_IUnknown
0x1800145c7  mov     rcx, rsi
0x1800145ca  lea     rdx, unk_180361318
0x1800145d1  mov     rax, [rax+88h]
0x1800145d8  call    cs:__guard_dispatch_icall_fptr
0x1800145de  mov     esi, eax
0x1800145e0  test    eax, eax
0x1800145e2  js      loc_18001497D
0x1800145e8  mov     rdi, [rsp+68h+arg_18]
0x1800145f0  mov     [rsp+68h+arg_18], r12
0x1800145f8  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800145ff  cmp     [rbx+8], r12b
0x180014603  jz      short loc_18001465E
0x180014605  lea     rbp, [rbx+0D0h]
0x18001460c  call    cs:__imp_GetLastError
0x180014613  nop     dword ptr [rax+rax+00h]
0x180014618  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001461b  mov     r15d, eax
0x18001461e  call    cs:__imp_TlsGetValue
0x180014625  nop     dword ptr [rax+rax+00h]
0x18001462a  test    rax, rax
0x18001462d  jz      loc_18001483F
0x180014633  mov     rbp, rax
0x180014636  mov     ecx, r15d; dwErrCode
0x180014639  call    cs:__imp_SetLastError
0x180014640  nop     dword ptr [rax+rax+00h]
0x180014645  mov     eax, [rbp+7C4h]
0x18001464b  test    eax, eax
0x18001464d  jz      short loc_18001465E
0x18001464f  sub     eax, 1
0x180014652  mov     [rbp+7C4h], eax
0x180014658  jz      loc_18001476B
0x18001465e  test    esi, esi
0x180014660  js      loc_180014A43
0x180014666  mov     ecx, [rsp+68h+arg_0]
0x18001466a  mov     rax, [rdi+18h]
0x18001466e  mov     rcx, [rax+rcx*8]
0x180014672  mov     [r14], rcx
0x180014675  mov     rcx, [rsp+68h+arg_10]
0x18001467d  mov     r13, [rsp+68h+var_28]
0x180014682  test    rcx, rcx
0x180014685  jz      short loc_18001469C
0x180014687  mov     rax, [rcx]
0x18001468a  mov     rax, [rax+10h]
0x18001468e  call    cs:__guard_dispatch_icall_fptr
0x180014694  mov     [rsp+68h+arg_10], r12
0x18001469c  test    rdi, rdi
0x18001469f  jz      short loc_1800146B1
0x1800146a1  mov     rax, [rdi]
0x1800146a4  mov     rcx, rdi
0x1800146a7  mov     rax, [rax+10h]
0x1800146ab  call    cs:__guard_dispatch_icall_fptr
0x1800146b1  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800146b8  mov     r15, [rsp+68h+var_38]
0x1800146bd  mov     r14, [rsp+68h+var_30]
0x1800146c2  cmp     [rbx+8], r12b
0x1800146c6  jz      short loc_18001471B
0x1800146c8  lea     rdi, [rbx+0D0h]
0x1800146cf  call    cs:__imp_GetLastError
0x1800146d6  nop     dword ptr [rax+rax+00h]
0x1800146db  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800146de  mov     ebp, eax
0x1800146e0  call    cs:__imp_TlsGetValue
0x1800146e7  nop     dword ptr [rax+rax+00h]
0x1800146ec  test    rax, rax
0x1800146ef  jz      loc_180014877
0x1800146f5  mov     rdi, rax
0x1800146f8  mov     ecx, ebp; dwErrCode
0x1800146fa  call    cs:__imp_SetLastError
0x180014701  nop     dword ptr [rax+rax+00h]
0x180014706  mov     eax, [rdi+7C4h]
0x18001470c  test    eax, eax
0x18001470e  jz      short loc_18001471B
0x180014710  sub     eax, 1
0x180014713  mov     [rdi+7C4h], eax
0x180014719  jz      short loc_18001472D
0x18001471b  mov     rbp, [rsp+68h+arg_8]
0x180014720  mov     eax, esi
0x180014722  add     rsp, 48h
0x180014726  pop     r12
0x180014728  pop     rdi
0x180014729  pop     rsi
0x18001472a  pop     rbx
0x18001472b  retn
0x18001472d  mov     [rdi+7C4h], r12d
0x180014734  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001473b  mov     [rdi+7E0h], r12
0x180014742  mov     [rdi+7CCh], r12d
0x180014749  movups  xmmword ptr [rdi+7D0h], xmm0
0x180014750  mov     [rdi+7E8h], r12d
0x180014757  call    cs:__imp_GetCurrentThreadId
0x18001475e  nop     dword ptr [rax+rax+00h]
0x180014763  mov     [rdi+7C0h], eax
0x180014769  jmp     short loc_18001471B
0x18001476b  mov     [rbp+7C4h], r12d
0x180014772  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180014779  mov     [rbp+7E0h], r12
0x180014780  mov     [rbp+7CCh], r12d
0x180014787  movups  xmmword ptr [rbp+7D0h], xmm0
0x18001478e  mov     [rbp+7E8h], r12d
0x180014795  call    cs:__imp_GetCurrentThreadId
0x18001479c  nop     dword ptr [rax+rax+00h]
0x1800147a1  mov     [rbp+7C0h], eax
0x1800147a7  jmp     loc_18001465E
0x1800147ac  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800147b1  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800147b8  jmp     loc_18001445B
0x1800147bd  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800147c2  jmp     loc_180014530
0x1800147c7  call    cs:__imp_GetLastError
0x1800147ce  nop     dword ptr [rax+rax+00h]
0x1800147d3  test    eax, eax
0x1800147d5  jnz     loc_18001449D
0x1800147db  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800147e2  test    rcx, rcx
0x1800147e5  jz      loc_1800148AF
0x1800147eb  mov     rax, [rcx]
0x1800147ee  mov     rax, [rax]
0x1800147f1  call    cs:__guard_dispatch_icall_fptr
0x1800147f7  test    rax, rax
0x1800147fa  cmovnz  rbx, rax
0x1800147fe  jmp     loc_18001449D
0x180014803  call    cs:__imp_GetLastError
0x18001480a  nop     dword ptr [rax+rax+00h]
0x18001480f  test    eax, eax
0x180014811  jnz     loc_180014574
0x180014817  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001481e  test    rcx, rcx
0x180014821  jz      loc_1800148C0
0x180014827  mov     rax, [rcx]
0x18001482a  mov     rax, [rax]
0x18001482d  call    cs:__guard_dispatch_icall_fptr
0x180014833  test    rax, rax
0x180014836  cmovnz  rdi, rax
0x18001483a  jmp     loc_180014574
0x18001483f  call    cs:__imp_GetLastError
0x180014846  nop     dword ptr [rax+rax+00h]
0x18001484b  test    eax, eax
0x18001484d  jnz     loc_180014636
0x180014853  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001485a  test    rcx, rcx
0x18001485d  jz      short loc_1800148D1
0x18001485f  mov     rax, [rcx]
0x180014862  mov     rax, [rax]
0x180014865  call    cs:__guard_dispatch_icall_fptr
0x18001486b  test    rax, rax
0x18001486e  cmovnz  rbp, rax
0x180014872  jmp     loc_180014636
0x180014877  call    cs:__imp_GetLastError
0x18001487e  nop     dword ptr [rax+rax+00h]
0x180014883  test    eax, eax
0x180014885  jnz     loc_1800146F8
0x18001488b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180014892  test    rcx, rcx
0x180014895  jz      short loc_1800148DF
0x180014897  mov     rax, [rcx]
0x18001489a  mov     rax, [rax]
0x18001489d  call    cs:__guard_dispatch_icall_fptr
0x1800148a3  test    rax, rax
0x1800148a6  cmovnz  rdi, rax
0x1800148aa  jmp     loc_1800146F8
0x1800148af  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800148b4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800148bb  jmp     loc_1800147EB
0x1800148c0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800148c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800148cc  jmp     loc_180014827
0x1800148d1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800148d6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800148dd  jmp     short loc_18001485F
0x1800148df  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1800148e4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800148eb  jmp     short loc_180014897
0x1800148ed  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x1800148f4  mov     esi, 0C00D36BBh
0x1800148f9  jnz     short loc_180014933
0x1800148fb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180014902  nop     dword ptr [rax+rax+00h]
0x180014907  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001490e  mov     rcx, rax
0x180014911  test    rax, rax
0x180014914  jz      short loc_18001492C
0x180014916  mov     rax, [rax]
0x180014919  mov     edx, 7F0h
0x18001491e  mov     rax, [rax+8]
0x180014922  call    cs:__guard_dispatch_icall_fptr
0x180014928  test    eax, eax
0x18001492a  jnz     short loc_180014933
0x18001492c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x180014933  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001493a  cmp     [rbx+8], r12b
0x18001493e  jnz     short loc_180014957
0x180014940  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014947  jb      loc_1800149F7
0x18001494d  mov     edx, 0Ah
0x180014952  jmp     loc_1800149D9
0x180014957  mov     rcx, rbx; this
0x18001495a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001495f  cmp     [rax+7CCh], esi
0x180014965  jz      short loc_180014940
0x180014967  mov     r9d, esi; int
0x18001496a  mov     r8d, 2Ah ; '*'; int
0x180014970  mov     rdx, r15; char *
0x180014973  mov     rcx, rax; this
0x180014976  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001497b  jmp     short loc_180014940
0x18001497d  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r12; CallStackTracing * CallStackTracing::s_wpInstance
0x180014984  jnz     short loc_1800149BE
0x180014986  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001498d  nop     dword ptr [rax+rax+00h]
0x180014992  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180014999  mov     rcx, rax
0x18001499c  test    rax, rax
  ... truncated ...
```
