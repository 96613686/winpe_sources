# EfsMdmSetupHandler

- ea: `0x18004207c`
- end: `0x1800422a9`
- name: `EfsMdmSetupHandler`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028d3c`

## callees

- `0x18004207c`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004209f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18004209f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042089`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042286`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042089`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180042286`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042294`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180042294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042141`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042179`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180042272`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180042272`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180042132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x180042132`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004216a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18004216a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180042268`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180042268`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800421cf`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800421cf`
- `ntdll!RtlNtStatusToDosError` at `0x1800421fe`
- `ntdll!RtlNtStatusToDosError` at `0x1800421fe`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180042246`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180042246`
- `ntdll!RtlDeleteCriticalSection` at `0x180042280`
- `ntdll!RtlDeleteCriticalSection` at `0x180042280`
- `ntdll!RtlInitializeCriticalSection` at `0x1800420f4`
- `ntdll!RtlInitializeCriticalSection` at `0x1800420f4`

## pseudocode

```c
__int64 EfsMdmSetupHandler()
{
  HANDLE ProcessHeap; // rax
  unsigned int v1; // edi
  char *v2; // rbx
  int v3; // eax
  char v4; // r14
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax
  ULONG LastError; // eax
  PTP_TIMER ThreadpoolTimer; // rax
  unsigned __int64 j; // rsi
  unsigned __int64 i; // rsi
  struct _TP_CLEANUP_GROUP *v10; // rcx
  HANDLE v11; // rax
  char v13; // [rsp+20h] [rbp-58h]

  ProcessHeap = GetProcessHeap();
  v1 = 8;
  v2 = (char *)HeapAlloc(ProcessHeap, 8u, 0xA8u);
  if ( !v2 )
  {
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, 8, 32, 41);
    return v1;
  }
  *((_QWORD *)v2 + 16) = EfsMdmPolicyUpdateHandler;
  *((_QWORD *)v2 + 17) = 3;
  v3 = RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)v2);
  if ( v3 < 0 )
  {
    v4 = 0;
    LastError = RtlNtStatusToDosError(v3);
    v13 = 55;
    goto LABEL_14;
  }
  v4 = 1;
  *((_DWORD *)v2 + 10) = 3;
  *((_QWORD *)v2 + 6) = 0;
  *((_QWORD *)v2 + 7) = 0;
  *((_QWORD *)v2 + 8) = 0;
  *((_QWORD *)v2 + 9) = 0;
  *((_QWORD *)v2 + 10) = 0;
  *((_QWORD *)v2 + 11) = 0;
  *((_DWORD *)v2 + 24) = 0;
  *((_DWORD *)v2 + 25) = 1;
  *((_DWORD *)v2 + 26) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *((_QWORD *)v2 + 14) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    LastError = GetLastError();
    v13 = 68;
LABEL_14:
    v1 = LastError;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, LastError, 32, v13);
    for ( i = 0; i < *((_QWORD *)v2 + 17); ++i )
    {
      if ( *(_QWORD *)&v2[8 * i + 144] )
        RtlUnsubscribeWnfNotificationWaitForCompletion();
    }
    v10 = (struct _TP_CLEANUP_GROUP *)*((_QWORD *)v2 + 14);
    if ( v10 )
    {
      CloseThreadpoolCleanupGroupMembers(v10, 1, 0);
      CloseThreadpoolCleanupGroup(*((PTP_CLEANUP_GROUP *)v2 + 14));
    }
    if ( v4 )
      RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)v2);
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v2);
    return v1;
  }
  *((_QWORD *)v2 + 7) = ThreadpoolCleanupGroup;
  *((_QWORD *)v2 + 8) = 0;
  ThreadpoolTimer = CreateThreadpoolTimer(EfspMdmTimerCallback, v2, (PTP_CALLBACK_ENVIRON)(v2 + 40));
  *((_QWORD *)v2 + 15) = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    LastError = GetLastError();
    v13 = 84;
    goto LABEL_14;
  }
  v1 = 0;
  for ( j = 0; j < *((_QWORD *)v2 + 17); ++j )
  {
    if ( (int)RtlSubscribeWnfStateChangeNotification(
                &v2[8 * j + 144],
                qword_180116110[j],
                0,
                &EfspMdmWnfCallback,
                v2,
                0,
                0,
                0) < 0 )
      *(_QWORD *)&v2[8 * j + 144] = 0;
  }
  pEfsMdmContext = (PRTL_CRITICAL_SECTION)v2;
  return v1;
}

```

## disassembly

```asm
0x18004207c  push    rbx
0x18004207e  push    rbp
0x18004207f  push    rsi
0x180042080  push    rdi
0x180042081  push    r14
0x180042083  push    r15
0x180042085  sub     rsp, 48h
0x180042089  call    cs:__imp_GetProcessHeap
0x18004208f  mov     edi, 8
0x180042094  mov     r8d, 0A8h; dwBytes
0x18004209a  mov     rcx, rax; hHeap
0x18004209d  mov     edx, edi; dwFlags
0x18004209f  call    cs:__imp_HeapAlloc
0x1800420a5  xor     r15d, r15d
0x1800420a8  mov     rbx, rax
0x1800420ab  test    rax, rax
0x1800420ae  jnz     short loc_1800420D7
0x1800420b0  mov     rcx, cs:g_hPublisher
0x1800420b7  lea     r9d, [rdi+18h]
0x1800420bb  mov     r8d, edi
0x1800420be  mov     dword ptr [rsp+78h+var_58], 129h
0x1800420c6  lea     rdx, EFS_TRACE_ERROR
0x1800420cd  call    fnEfsLogTrace1
0x1800420d2  jmp     loc_18004229A
0x1800420d7  lea     rax, EfsMdmPolicyUpdateHandler
0x1800420de  mov     esi, 3
0x1800420e3  mov     rcx, rbx; CriticalSection
0x1800420e6  mov     [rbx+80h], rax
0x1800420ed  mov     [rbx+88h], rsi
0x1800420f4  call    cs:__imp_RtlInitializeCriticalSection
0x1800420fa  test    eax, eax
0x1800420fc  js      loc_1800421F9
0x180042102  mov     r14b, 1
0x180042105  mov     [rbx+28h], esi
0x180042108  mov     [rbx+30h], r15
0x18004210c  mov     [rbx+38h], r15
0x180042110  mov     [rbx+40h], r15
0x180042114  mov     [rbx+48h], r15
0x180042118  mov     [rbx+50h], r15
0x18004211c  mov     [rbx+58h], r15
0x180042120  mov     [rbx+60h], r15d
0x180042124  mov     dword ptr [rbx+64h], 1
0x18004212b  mov     dword ptr [rbx+68h], 48h ; 'H'
0x180042132  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180042138  mov     [rbx+70h], rax
0x18004213c  test    rax, rax
0x18004213f  jnz     short loc_180042154
0x180042141  call    cs:__imp_GetLastError
0x180042147  mov     dword ptr [rsp+78h+var_58], 144h
0x18004214f  jmp     loc_18004220C
0x180042154  lea     r8, [rbx+28h]; pcbe
0x180042158  mov     [rbx+38h], rax
0x18004215c  mov     rdx, rbx; pv
0x18004215f  mov     [rbx+40h], r15
0x180042163  lea     rcx, ?EfspMdmTimerCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18004216a  call    cs:__imp_CreateThreadpoolTimer
0x180042170  mov     [rbx+78h], rax
0x180042174  test    rax, rax
0x180042177  jnz     short loc_18004218C
0x180042179  call    cs:__imp_GetLastError
0x18004217f  mov     dword ptr [rsp+78h+var_58], 154h
0x180042187  jmp     loc_18004220C
0x18004218c  mov     edi, r15d
0x18004218f  mov     rsi, r15
0x180042192  cmp     [rbx+88h], r15
0x180042199  jbe     short loc_1800421ED
0x18004219b  mov     [rsp+78h+var_40], r15d
0x1800421a0  lea     rdx, qword_180116110
0x1800421a7  mov     rdx, [rdx+rsi*8]
0x1800421ab  lea     rcx, [rbx+90h]
0x1800421b2  mov     [rsp+78h+var_48], r15d
0x1800421b7  lea     rcx, [rcx+rsi*8]
0x1800421bb  mov     [rsp+78h+var_50], r15
0x1800421c0  lea     r9, EfspMdmWnfCallback
0x1800421c7  xor     r8d, r8d
0x1800421ca  mov     [rsp+78h+var_58], rbx
0x1800421cf  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800421d5  test    eax, eax
0x1800421d7  jns     short loc_1800421E1
0x1800421d9  mov     [rbx+rsi*8+90h], r15
0x1800421e1  inc     rsi
0x1800421e4  cmp     rsi, [rbx+88h]
0x1800421eb  jb      short loc_18004219B
0x1800421ed  mov     cs:pEfsMdmContext, rbx
0x1800421f4  jmp     loc_18004229A
0x1800421f9  mov     ecx, eax; Status
0x1800421fb  mov     r14b, r15b
0x1800421fe  call    cs:__imp_RtlNtStatusToDosError
0x180042204  mov     dword ptr [rsp+78h+var_58], 137h
0x18004220c  mov     rcx, cs:g_hPublisher
0x180042213  lea     rdx, EFS_TRACE_ERROR
0x18004221a  mov     r9d, 20h ; ' '
0x180042220  mov     r8d, eax
0x180042223  mov     edi, eax
0x180042225  call    fnEfsLogTrace1
0x18004222a  mov     rbp, rbx
0x18004222d  mov     rsi, r15
0x180042230  cmp     [rbx+88h], r15
0x180042237  jbe     short loc_180042258
0x180042239  mov     rcx, [rbp+rsi*8+90h]
0x180042241  test    rcx, rcx
0x180042244  jz      short loc_18004224C
0x180042246  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18004224c  inc     rsi
0x18004224f  cmp     rsi, [rbx+88h]
0x180042256  jb      short loc_180042239
0x180042258  mov     rcx, [rbx+70h]; ptpcg
0x18004225c  test    rcx, rcx
0x18004225f  jz      short loc_180042278
0x180042261  xor     r8d, r8d; pvCleanupContext
0x180042264  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180042268  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18004226e  mov     rcx, [rbx+70h]; ptpcg
0x180042272  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180042278  test    r14b, r14b
0x18004227b  jz      short loc_180042286
0x18004227d  mov     rcx, rbx; CriticalSection
0x180042280  call    cs:__imp_RtlDeleteCriticalSection
0x180042286  call    cs:__imp_GetProcessHeap
0x18004228c  mov     r8, rbx; lpMem
0x18004228f  xor     edx, edx; dwFlags
0x180042291  mov     rcx, rax; hHeap
0x180042294  call    cs:__imp_HeapFree
0x18004229a  mov     eax, edi
0x18004229c  add     rsp, 48h
0x1800422a0  pop     r15
0x1800422a2  pop     r14
0x1800422a4  pop     rdi
0x1800422a5  pop     rsi
0x1800422a6  pop     rbp
0x1800422a7  pop     rbx
0x1800422a8  retn
```
