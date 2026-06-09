# s_RPC_SCardEstablishContext

- ea: `0x18000dca0`
- end: `0x18000e4a6`
- name: `s_RPC_SCardEstablishContext`
- size: `2054`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, LPVOID **)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006030`
- `0x18000dca0`
- `0x18000e4b0`
- `0x18000e550`
- `0x18000ec00`
- `0x180014180`
- `0x18001c330`
- `0x18001c370`
- `0x180023168`
- `0x180023174`
- `0x180023282`
- `0x180028b78`
- `0x18002ac04`
- `0x18003261b`
- `0x1800326d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ddb0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ddcc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ddb0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ddcc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de6f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de6f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e238`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e243`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e2cf`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dffd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e014`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000dffd`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000e014`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dcd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e099`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dcd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000de52`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000de12`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18000de12`
- `RPCRT4!RpcRaiseException` at `0x18000e49f`
- `RPCRT4!RpcRaiseException` at `0x18000e49f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_RPC_SCardEstablishContext(RPC_BINDING_HANDLE BindingHandle, LPVOID **a2)
{
  DWORD CurrentThreadId; // eax
  char *v4; // rcx
  DWORD v5; // r9d
  unsigned __int64 *v6; // rdx
  int v7; // edi
  int v8; // r10d
  HANDLE v9; // r12
  int v10; // ebx
  int v11; // esi
  void *v12; // r15
  HANDLE EventW; // r14
  RPC_STATUS FilteringSid; // eax
  ulong v15; // r13d
  HANDLE ProcessHeap; // rax
  int v17; // r8d
  unsigned int i; // eax
  bool v19; // zf
  int v20; // edx
  LPVOID *v21; // rsi
  void *v22; // rcx
  void *v23; // r13
  DWORD LastError; // eax
  DWORD v25; // eax
  struct CCriticalSectionObject *v26; // rbx
  __int64 v27; // r14
  _QWORD *v28; // r12
  __int64 j; // rcx
  int v30; // r15d
  DWORD v31; // eax
  unsigned __int64 v32; // rdx
  int v33; // esi
  int v34; // ebx
  char *v35; // rcx
  __int64 v36; // rax
  char *v37; // r8
  __int64 v38; // r8
  const char *v39; // r9
  __int64 v40; // rdx
  char *v41; // r11
  char v42; // al
  char *v43; // rax
  __int64 v44; // rdx
  unsigned int k; // ecx
  bool v47; // zf
  __int64 v48; // r8
  int m; // r13d
  ulong pExceptionObject; // [rsp+30h] [rbp-89h] BYREF
  void *v51; // [rsp+38h] [rbp-81h]
  LPVOID **v52; // [rsp+40h] [rbp-79h]
  _OWORD RpcCallAttributes[8]; // [rsp+50h] [rbp-69h] BYREF

  v52 = a2;
  CurrentThreadId = GetCurrentThreadId();
  v5 = CurrentThreadId;
  v6 = &`WppTraceIndent'::`2'::ThreadTable;
  v7 = -1;
  v8 = `WppTraceIndent'::`2'::idxCurrentThread;
  v9 = 0;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v8 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
    dword_18004BD54 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
    {
      v17 = -1;
      for ( i = 0; ; ++i )
      {
        v19 = i == 32;
        if ( i >= 0x20 )
          break;
        v4 = (char *)(int)i;
        v20 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
        if ( v20 == v5 )
        {
          v8 = i;
          `WppTraceIndent'::`2'::idxCurrentThread = i;
          v6 = &`WppTraceIndent'::`2'::ThreadTable;
          v19 = i == 32;
          break;
        }
        if ( v17 == -1 && !v20 )
          v17 = i;
        v6 = &`WppTraceIndent'::`2'::ThreadTable;
      }
      if ( v19 )
      {
        if ( v17 == -1 )
        {
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_30;
        }
        v8 = v17;
        `WppTraceIndent'::`2'::idxCurrentThread = v17;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v17) = v5;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v17 + 1) = 0;
      }
    }
    if ( v8 < 0 )
    {
LABEL_30:
      v10 = 0;
      goto LABEL_6;
    }
  }
  v10 = ++*((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v8 + 1);
LABEL_6:
  `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
  v11 = 1;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v10 >= 1 )
  {
    do
    {
      if ( (unsigned int)StringCbCatA(v4, (unsigned __int64)v6, "..") )
        break;
      ++v11;
    }
    while ( v11 <= v10 );
  }
  StringCbCatA(v4, (unsigned __int64)v6, ">");
  WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_6cb68c4060583735bafc290ec605627b_Traceguids,
      `WppTraceIndent'::`2'::szIndentPrefix);
  }
  memset(RpcCallAttributes, 0, 120);
  v12 = 0;
  v51 = 0;
  _InterlockedExchange(&g_fExtendShutdownTimer, 1);
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW || (v9 = CreateEventW(0, 0, 0, 0)) == 0 )
  {
    pExceptionObject = GetLastError();
    v15 = pExceptionObject;
    if ( !pExceptionObject )
      goto LABEL_54;
    if ( !EventW )
      goto LABEL_15;
    goto LABEL_14;
  }
  memset((char *)RpcCallAttributes + 8, 0, 112);
  *(_QWORD *)&RpcCallAttributes[0] = 0x1000000003LL;
  FilteringSid = RpcServerInqCallAttributesW(BindingHandle, RpcCallAttributes);
  pExceptionObject = FilteringSid;
  if ( FilteringSid )
    goto LABEL_13;
  FilteringSid = GetFilteringSid(BindingHandle);
  pExceptionObject = FilteringSid;
  if ( FilteringSid )
  {
    v12 = v51;
LABEL_13:
    v15 = FilteringSid;
LABEL_14:
    CloseHandle(EventW);
LABEL_15:
    if ( v9 )
      CloseHandle(v9);
    if ( v12 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    goto LABEL_54;
  }
  v21 = (LPVOID *)operator new(0xB8u);
  if ( !v21 )
  {
    v21 = 0;
    v12 = v51;
LABEL_117:
    v15 = -2146435066;
    pExceptionObject = -2146435066;
    if ( v21 )
    {
      CServiceThread::~CServiceThread((CServiceThread *)v21);
      operator delete(v21);
    }
    goto LABEL_14;
  }
  v22 = (void *)_InterlockedIncrement(&dword_18004BF90);
  v23 = *(void **)&RpcCallAttributes[4];
  *v21 = 0;
  *((_DWORD *)v21 + 2) = 0;
  v21[2] = 0;
  *((_DWORD *)v21 + 6) = 0;
  v21[4] = 0;
  *((_DWORD *)v21 + 10) = 0;
  v21[6] = &CDynamicArray<CServiceThread>::`vftable';
  v21[7] = 0;
  v21[8] = 0;
  v21[9] = v22;
  CMutex::CMutex((CMutex *)(v21 + 10));
  v12 = v51;
  v21[22] = v51;
  if ( EventW == (HANDLE)-1LL )
    LastError = GetLastError();
  else
    LastError = 0;
  *((_DWORD *)v21 + 2) = LastError;
  if ( (char *)*v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CHandleObject::Close((CHandleObject *)v21);
  *v21 = EventW;
  if ( v9 == (HANDLE)-1LL )
    v25 = GetLastError();
  else
    v25 = 0;
  *((_DWORD *)v21 + 6) = v25;
  if ( (char *)v21[2] - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CHandleObject::Close((CHandleObject *)(v21 + 2));
  v21[2] = v9;
  v21[21] = v23;
  if ( (*((unsigned int (__fastcall **)(LPVOID *))v21[10] + 2))(v21 + 10) )
    goto LABEL_117;
  if ( !TlsSetValue(dwTlsIndex, v21[9]) || !TlsSetValue(dword_18004B240, *v21) )
    GetLastError();
  v26 = qword_18004BA60;
  (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))qword_18004BA60)(qword_18004BA60, 0, 0);
  v27 = 0;
  v28 = Block;
  j = HIDWORD(qword_18004B0A8);
  while ( HIDWORD(qword_18004B0A8) > (unsigned int)v27 && *((_QWORD *)Block + (int)v27) )
    v27 = (unsigned int)(v27 + 1);
  v30 = qword_18004B0A8;
  if ( (unsigned int)v27 >= (unsigned int)qword_18004B0A8 )
  {
    if ( !(_DWORD)qword_18004B0A8 )
      v30 = 4;
    for ( ; (int)v27 >= v30; v30 *= 2 )
      ;
    v28 = operator new[](saturated_mul(v30, 8u));
    if ( !v28 )
    {
      pExceptionObject = 14;
      throw &pExceptionObject;
    }
    v48 = 0;
    for ( j = HIDWORD(qword_18004B0A8); (unsigned int)v48 < HIDWORD(qword_18004B0A8); j = HIDWORD(qword_18004B0A8) )
    {
      v28[v48] = *((_QWORD *)Block + v48);
      v48 = (unsigned int)(v48 + 1);
    }
    if ( Block )
    {
      operator delete[](Block);
      j = HIDWORD(qword_18004B0A8);
    }
    Block = v28;
    LODWORD(qword_18004B0A8) = v30;
  }
  if ( (unsigned int)v27 >= (unsigned int)j )
  {
    if ( (unsigned int)v27 > (unsigned int)j )
    {
      memset_0(&v28[j], 0, 8LL * (unsigned int)(v27 - j));
      v28 = Block;
    }
    HIDWORD(qword_18004B0A8) = v27 + 1;
  }
  v28[v27] = v21;
  (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v26 + 8LL))(v26);
  *v52 = v21;
  v15 = pExceptionObject;
LABEL_54:
  v31 = GetCurrentThreadId();
  v33 = `WppTraceIndent'::`2'::idxCurrentThread;
  if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
  {
    v33 = 0;
    `WppTraceIndent'::`2'::idxCurrentThread = 0;
    LODWORD(`WppTraceIndent'::`2'::ThreadTable) = v31;
    dword_18004BD54 = 0;
  }
  else
  {
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
      || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != v31 )
    {
      for ( k = 0; ; ++k )
      {
        v47 = k == 32;
        if ( k >= 0x20 )
          break;
        v32 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)k);
        if ( (_DWORD)v32 == v31 )
        {
          v33 = k;
          `WppTraceIndent'::`2'::idxCurrentThread = k;
          v47 = k == 32;
          break;
        }
        if ( v7 == -1 && !(_DWORD)v32 )
          v7 = k;
      }
      if ( v47 )
      {
        if ( v7 == -1 )
        {
          v33 = -2;
          `WppTraceIndent'::`2'::idxCurrentThread = -2;
          goto LABEL_88;
        }
        v33 = v7;
        `WppTraceIndent'::`2'::idxCurrentThread = v7;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v7) = v31;
        *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v7 + 1) = 0;
      }
    }
    if ( v33 < 0 )
    {
LABEL_88:
      v34 = 0;
      goto LABEL_59;
    }
  }
  v34 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v33 + 1);
LABEL_59:
  `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
  v35 = (char *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u && v34 >= 1 )
  {
    for ( m = 1; m <= v34; ++m )
    {
      if ( (unsigned int)StringCbCatA(v35, v32, "..") )
        break;
    }
    v35 = (char *)WPP_GLOBAL_Control;
    v33 = `WppTraceIndent'::`2'::idxCurrentThread;
    v15 = pExceptionObject;
  }
  v36 = 256;
  v37 = `WppTraceIndent'::`2'::szIndentPrefix;
  do
  {
    if ( !*v37 )
      break;
    ++v37;
    --v36;
  }
  while ( v36 );
  if ( v36 )
  {
    v38 = 2147483646;
    v39 = "<";
    v40 = v36;
    v41 = &`WppTraceIndent'::`2'::szIndentPrefix[256 - v36];
    do
    {
      if ( !v38 )
        break;
      v42 = *v39;
      if ( !*v39 )
        break;
      ++v39;
      *v41++ = v42;
      --v38;
      --v40;
    }
    while ( v40 );
    v43 = v41 - 1;
    if ( v40 )
      v43 = v41;
    *v43 = 0;
  }
  if ( v33 >= 0 )
  {
    v44 = 8LL * v33;
    v19 = (*(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v44 + 4))-- == 1;
    if ( v19 )
      *(_DWORD *)((char *)&`WppTraceIndent'::`2'::ThreadTable + v44) = 0;
  }
  WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
  if ( v35 != (char *)&WPP_GLOBAL_Control && (v35[28] & 0x20) != 0 && (unsigned __int8)v35[25] >= 4u )
    WPP_SF_sd(*((_QWORD *)v35 + 2), 23, (unsigned int)WPP_6cb68c4060583735bafc290ec605627b_Traceguids, 0, v15);
  if ( v15 )
    RpcRaiseException(v15);
  return 0;
}

```

## disassembly

```asm
0x18000dca0  mov     [rsp-8+arg_10], rbx
0x18000dca5  push    rbp
0x18000dca6  push    rsi
0x18000dca7  push    rdi
0x18000dca8  push    r12
0x18000dcaa  push    r13
0x18000dcac  push    r14
0x18000dcae  push    r15
0x18000dcb0  lea     rbp, [rsp-27h]
0x18000dcb5  sub     rsp, 0E0h
0x18000dcbc  mov     rax, cs:__security_cookie
0x18000dcc3  xor     rax, rsp
0x18000dcc6  mov     [rbp+57h+var_40], rax
0x18000dcca  mov     [rbp+57h+var_D0], rdx
0x18000dcce  mov     r13, rcx
0x18000dcd1  call    cs:__imp_GetCurrentThreadId
0x18000dcd7  mov     r9d, eax
0x18000dcda  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; unsigned __int64
0x18000dce1  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000dce8  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000dcef  xor     r12d, r12d
0x18000dcf2  cmp     r10d, edi
0x18000dcf5  jz      loc_18000E268
0x18000dcfb  cmp     r10d, 0FFFFFFFEh
0x18000dcff  jz      loc_18000DE7A
0x18000dd05  cmp     [rdx+r10*8], eax
0x18000dd09  jnz     loc_18000DE7A
0x18000dd0f  test    r10d, r10d
0x18000dd12  js      loc_18000DECE
0x18000dd18  movsxd  rax, r10d
0x18000dd1b  inc     dword ptr [rdx+rax*8+4]
0x18000dd1f  mov     ebx, [rdx+rax*8+4]
0x18000dd23  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000dd2a  mov     rax, cs:WPP_GLOBAL_Control
0x18000dd31  mov     esi, 1
0x18000dd36  test    byte ptr [rax+1Ch], 2
0x18000dd3a  jnz     loc_18000E285
0x18000dd40  lea     r8, pszSrc; ">"
0x18000dd47  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000dd4c  lea     rax, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000dd53  mov     cs:?WPP_pszIndent@@3PEADEA, rax; char * WPP_pszIndent
0x18000dd5a  lea     rdx, WPP_GLOBAL_Control
0x18000dd61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dd68  cmp     rcx, rdx
0x18000dd6b  jnz     loc_18000DED6
0x18000dd71  xorps   xmm0, xmm0
0x18000dd74  xor     eax, eax
0x18000dd76  movups  [rbp+57h+RpcCallAttributes], xmm0
0x18000dd7a  movups  [rbp+57h+var_B0], xmm0
0x18000dd7e  movups  [rbp+57h+var_A0], xmm0
0x18000dd82  movups  [rbp+57h+var_90], xmm0
0x18000dd86  movups  [rbp+57h+var_80], xmm0
0x18000dd8a  movups  [rbp+57h+var_70], xmm0
0x18000dd8e  movups  [rbp+57h+var_60], xmm0
0x18000dd92  mov     [rbp+57h+var_50], rax
0x18000dd96  mov     r15, r12
0x18000dd99  mov     [rsp+110h+var_D8], r12
0x18000dd9e  mov     eax, esi
0x18000dda0  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x18000dda6  xor     r9d, r9d; lpName
0x18000dda9  xor     r8d, r8d; bInitialState
0x18000ddac  xor     edx, edx; bManualReset
0x18000ddae  xor     ecx, ecx; lpEventAttributes
0x18000ddb0  call    cs:__imp_CreateEventW
0x18000ddb6  mov     r14, rax
0x18000ddb9  test    rax, rax
0x18000ddbc  jz      loc_18000E243
0x18000ddc2  xor     r9d, r9d; lpName
0x18000ddc5  xor     r8d, r8d; bInitialState
0x18000ddc8  xor     edx, edx; bManualReset
0x18000ddca  xor     ecx, ecx; lpEventAttributes
0x18000ddcc  call    cs:__imp_CreateEventW
0x18000ddd2  mov     r12, rax
0x18000ddd5  test    rax, rax
0x18000ddd8  jz      loc_18000E243
0x18000ddde  xorps   xmm0, xmm0
0x18000dde1  movups  [rbp+57h+RpcCallAttributes+8], xmm0
0x18000dde5  movups  [rbp+57h+var_B0+8], xmm0
0x18000dde9  movups  [rbp+57h+var_A0+8], xmm0
0x18000dded  movups  [rbp+57h+var_90+8], xmm0
0x18000ddf1  movups  [rbp+57h+var_80+8], xmm0
0x18000ddf5  movups  [rbp+57h+var_70+8], xmm0
0x18000ddf9  movups  [rbp+57h+var_60+8], xmm0
0x18000ddfd  mov     dword ptr [rbp+57h+RpcCallAttributes], 3
0x18000de04  mov     dword ptr [rbp+57h+RpcCallAttributes+4], 10h
0x18000de0b  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x18000de0f  mov     rcx, r13; ClientBinding
0x18000de12  call    cs:__imp_RpcServerInqCallAttributesW
0x18000de18  mov     [rsp+110h+pExceptionObject], eax
0x18000de1c  test    eax, eax
0x18000de1e  jnz     short loc_18000DE3E
0x18000de20  lea     rdx, [rsp+110h+var_D8]
0x18000de25  mov     rcx, r13; BindingHandle
0x18000de28  call    GetFilteringSid
0x18000de2d  mov     [rsp+110h+pExceptionObject], eax
0x18000de31  test    eax, eax
0x18000de33  jz      loc_18000DF22
0x18000de39  mov     r15, [rsp+110h+var_D8]
0x18000de3e  mov     r13d, eax
0x18000de41  mov     rcx, r14; hObject
0x18000de44  call    cs:__imp_CloseHandle
0x18000de4a  test    r12, r12
0x18000de4d  jz      short loc_18000DE58
0x18000de4f  mov     rcx, r12; hObject
0x18000de52  call    cs:__imp_CloseHandle
0x18000de58  test    r15, r15
0x18000de5b  jz      loc_18000E099
0x18000de61  call    cs:__imp_GetProcessHeap
0x18000de67  mov     r8, r15; lpMem
0x18000de6a  xor     edx, edx; dwFlags
0x18000de6c  mov     rcx, rax; hHeap
0x18000de6f  call    cs:__imp_HeapFree
0x18000de75  jmp     loc_18000E099
0x18000de7a  mov     r8d, edi
0x18000de7d  mov     eax, r12d
0x18000de80  cmp     eax, 20h ; ' '
0x18000de83  jnb     short loc_18000DEB9
0x18000de85  movsxd  rcx, eax
0x18000de88  mov     edx, [rdx+rcx*8]
0x18000de8b  cmp     edx, r9d
0x18000de8e  jz      short loc_18000DEA6
0x18000de90  cmp     r8d, edi
0x18000de93  jnz     short loc_18000DE9B
0x18000de95  test    edx, edx
0x18000de97  cmovz   r8d, eax
0x18000de9b  inc     eax
0x18000de9d  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000dea4  jmp     short loc_18000DE80
0x18000dea6  mov     r10d, eax
0x18000dea9  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000deaf  lea     rdx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000deb6  cmp     eax, 20h ; ' '
0x18000deb9  jnz     loc_18000DD0F
0x18000debf  cmp     r8d, edi
0x18000dec2  jnz     short loc_18000DF07
0x18000dec4  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000dece  mov     ebx, r12d
0x18000ded1  jmp     loc_18000DD23
0x18000ded6  test    byte ptr [rcx+1Ch], 20h
0x18000deda  jz      loc_18000DD71
0x18000dee0  cmp     byte ptr [rcx+19h], 4
0x18000dee4  jb      loc_18000DD71
0x18000deea  mov     edx, 16h
0x18000deef  mov     r9, rax
0x18000def2  lea     r8, WPP_6cb68c4060583735bafc290ec605627b_Traceguids
0x18000def9  mov     rcx, [rcx+10h]
0x18000defd  call    WPP_SF_s
0x18000df02  jmp     loc_18000DD71
0x18000df07  mov     r10d, r8d
0x18000df0a  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000df11  movsxd  rax, r8d
0x18000df14  mov     [rdx+rax*8], r9d
0x18000df18  mov     [rdx+rax*8+4], r12d
0x18000df1d  jmp     loc_18000DD0F
0x18000df22  mov     ecx, 0B8h; Size
0x18000df27  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000df2c  mov     rsi, rax
0x18000df2f  test    rax, rax
0x18000df32  jz      loc_18000E3C6
0x18000df38  mov     eax, 1
0x18000df3d  lock xadd cs:dword_18004BF90, eax
0x18000df45  inc     eax
0x18000df47  movsxd  rcx, eax
0x18000df4a  mov     r13, qword ptr [rbp+57h+var_80]
0x18000df4e  xor     eax, eax
0x18000df50  mov     [rsi], rax
0x18000df53  mov     [rsi+8], eax
0x18000df56  mov     [rsi+10h], rax
0x18000df5a  mov     [rsi+18h], eax
0x18000df5d  mov     [rsi+20h], rax
0x18000df61  mov     [rsi+28h], eax
0x18000df64  lea     rdx, ??_7?$CDynamicArray@VCServiceThread@@@@6B@; const CDynamicArray<CServiceThread>::`vftable'
0x18000df6b  mov     [rsi+30h], rdx
0x18000df6f  mov     [rsi+38h], rax
0x18000df73  mov     [rsi+40h], rax
0x18000df77  mov     [rsi+48h], rcx
0x18000df7b  lea     rcx, [rsi+50h]; this
0x18000df7f  call    ??0CMutex@@QEAA@XZ; CMutex::CMutex(void)
0x18000df84  mov     r15, [rsp+110h+var_D8]
0x18000df89  mov     [rsi+0B0h], r15
0x18000df90  cmp     r14, rdi
0x18000df93  jz      loc_18000E2B7
0x18000df99  xor     eax, eax
0x18000df9b  mov     [rsi+8], eax
0x18000df9e  mov     rax, [rsi]
0x18000dfa1  dec     rax
0x18000dfa4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dfa8  jbe     loc_18000E2C2
0x18000dfae  mov     [rsi], r14
0x18000dfb1  cmp     r12, rdi
0x18000dfb4  jz      loc_18000E2CF
0x18000dfba  xor     eax, eax
0x18000dfbc  mov     [rsi+18h], eax
0x18000dfbf  mov     rax, [rsi+10h]
0x18000dfc3  dec     rax
0x18000dfc6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dfca  jbe     loc_18000E2DA
0x18000dfd0  mov     [rsi+10h], r12
0x18000dfd4  mov     [rsi+0A8h], r13
0x18000dfdb  lea     rcx, [rsi+50h]
0x18000dfdf  mov     rax, [rcx]
0x18000dfe2  mov     rax, [rax+10h]
0x18000dfe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfeb  test    eax, eax
0x18000dfed  jnz     loc_18000E3CD
0x18000dff3  mov     rdx, [rsi+48h]; lpTlsValue
0x18000dff7  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000dffd  call    cs:__imp_TlsSetValue
0x18000e003  test    eax, eax
0x18000e005  jz      loc_18000E238
0x18000e00b  mov     rdx, [rsi]; lpTlsValue
0x18000e00e  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000e014  call    cs:__imp_TlsSetValue
0x18000e01a  test    eax, eax
0x18000e01c  jz      loc_18000E238
0x18000e022  mov     rbx, cs:qword_18004BA60
0x18000e029  mov     rax, [rbx]
0x18000e02c  xor     r8d, r8d
0x18000e02f  xor     edx, edx
0x18000e031  mov     rcx, rbx
0x18000e034  mov     rax, [rax]
0x18000e037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e03c  xor     r14d, r14d
0x18000e03f  mov     r12, cs:Block
0x18000e046  mov     ecx, dword ptr cs:qword_18004B0A8+4
0x18000e04c  cmp     ecx, r14d
0x18000e04f  jbe     short loc_18000E060
0x18000e051  movsxd  rax, r14d
0x18000e054  cmp     qword ptr [r12+rax*8], 0
0x18000e059  jz      short loc_18000E060
0x18000e05b  inc     r14d
0x18000e05e  jmp     short loc_18000E04C
0x18000e060  mov     r15d, dword ptr cs:qword_18004B0A8
0x18000e067  cmp     r14d, r15d
0x18000e06a  jnb     loc_18000E2E8
0x18000e070  cmp     r14d, ecx
0x18000e073  jnb     loc_18000E399
0x18000e079  mov     [r12+r14*8], rsi
0x18000e07d  mov     rax, [rbx]
0x18000e080  mov     rcx, rbx
0x18000e083  mov     rax, [rax+8]
0x18000e087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e08c  nop
0x18000e08d  mov     rax, [rbp+57h+var_D0]
0x18000e091  mov     [rax], rsi
0x18000e094  mov     r13d, [rsp+110h+pExceptionObject]
0x18000e099  call    cs:__imp_GetCurrentThreadId
0x18000e09f  mov     r8d, eax
0x18000e0a2  movsxd  rsi, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000e0a9  lea     r14, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000e0b0  cmp     esi, 0FFFFFFFFh
0x18000e0b3  jz      loc_18000E3F6
0x18000e0b9  cmp     esi, 0FFFFFFFEh
0x18000e0bc  jz      loc_18000E1D1
0x18000e0c2  cmp     [r14+rsi*8], eax
0x18000e0c6  jnz     loc_18000E1D1
0x18000e0cc  xor     r9d, r9d
0x18000e0cf  test    esi, esi
0x18000e0d1  js      loc_18000E217
0x18000e0d7  movsxd  rax, esi
0x18000e0da  mov     ebx, [r14+rax*8+4]
0x18000e0df  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, 0; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000e0e6  mov     rcx, cs:WPP_GLOBAL_Control; char *
0x18000e0ed  test    byte ptr [rcx+1Ch], 2
0x18000e0f1  jnz     loc_18000E416
0x18000e0f7  mov     edx, 100h
0x18000e0fc  mov     eax, edx
0x18000e0fe  lea     rbx, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000e105  mov     r8, rbx
0x18000e108  cmp     byte ptr [r8], 0
0x18000e10c  jnz     loc_18000E461
0x18000e112  mov     r10, rdx
0x18000e115  sub     r10, rax
0x18000e118  test    rax, rax
0x18000e11b  cmovz   r10, r9
0x18000e11f  jz      short loc_18000E167
0x18000e121  mov     r8d, 7FFFFFFEh
0x18000e127  lea     r9, asc_18003BC58; "<"
0x18000e12e  sub     rdx, r10
0x18000e131  lea     r11, [r10+rbx]
0x18000e135  jz      short loc_18000E156
0x18000e137  test    r8, r8
0x18000e13a  jz      short loc_18000E156
0x18000e13c  movzx   eax, byte ptr [r9]
0x18000e140  test    al, al
0x18000e142  jz      short loc_18000E156
0x18000e144  inc     r9
0x18000e147  mov     [r11], al
0x18000e14a  inc     r11
0x18000e14d  dec     r8
0x18000e150  sub     rdx, 1
0x18000e154  jnz     short loc_18000E137
0x18000e156  lea     rax, [r11-1]
0x18000e15a  test    rdx, rdx
0x18000e15d  cmovnz  rax, r11
0x18000e161  mov     byte ptr [rax], 0
0x18000e164  xor     r9d, r9d
0x18000e167  test    esi, esi
0x18000e169  js      short loc_18000E182
0x18000e16b  movsxd  rax, esi
  ... truncated ...
```
