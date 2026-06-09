# ServiceMain(ulong,ushort * * const)

- ea: `0x180153e00`
- end: `0x180154098`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `664`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000a320`
- `0x180153e00`
- `0x1801540f0`
- `0x180154248`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180153eb5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180153eb5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180153f2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180153f60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180153fa7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180153f2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180153f60`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180153fa7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154054`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015406f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154081`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154054`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18015406f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154081`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154005`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180153eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154005`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180153fef`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180153fef`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180153e6b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180153e6b`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, LPCWSTR *a2)
{
  __int64 v2; // rsi
  __int64 v4; // rdx
  LPVOID v5; // rbx
  HANDLE v6; // rcx
  LPVOID v7; // rax
  unsigned int i; // edi
  __int64 v9; // rax
  SIZE_T v10; // r15
  unsigned __int16 *v11; // rcx
  __int64 v12; // rdx
  unsigned int j; // edi
  void *v14; // r8

  v2 = a1;
  if ( !a1 )
    return;
  qword_1801D4100 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_AudioTrace;
  qword_1801D40F8 = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  sshStatusHandle = RegisterServiceCtrlHandlerExW(*a2, ServiceCtrl, 0);
  if ( !sshStatusHandle )
    return;
  ssStatus = 32;
  dword_1801D40B8 = 0;
  if ( !(unsigned int)ReportStatusToSCMgr(2, 0, 5000) )
    return;
  hEventShutdown = CreateEventW(0, 1, 0, 0);
  if ( !hEventShutdown )
  {
    dword_1801D40B8 = GetLastError();
    v4 = (unsigned int)dword_1801D40B8;
LABEL_6:
    ReportStatusToSCMgr(1, v4, 0);
    return;
  }
  dword_1801D40B8 = (*((__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))gpSvchostSharedGlobals
                     + 24))(
                      &hEventShutdownWait,
                      *a2,
                      hEventShutdown,
                      OnServiceShutdown,
                      0,
                      8);
  v5 = HeapAlloc(g_hHeap, 0, 0x18u);
  v4 = 8;
  if ( !v5 )
  {
    dword_1801D40B8 = 8;
    goto LABEL_6;
  }
  v6 = g_hHeap;
  *(_QWORD *)v5 = sshStatusHandle;
  *((_DWORD *)v5 + 2) = v2;
  v7 = HeapAlloc(v6, 8u, 8 * v2);
  *((_QWORD *)v5 + 2) = v7;
  if ( !v7 )
  {
LABEL_19:
    dword_1801D40B8 = 8;
    v12 = 8;
    goto LABEL_20;
  }
  for ( i = 0; i < (unsigned int)v2; ++i )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[i][v9] );
    v10 = (unsigned int)(2 * v9 + 2);
    *(_QWORD *)(*((_QWORD *)v5 + 2) + 8LL * i) = HeapAlloc(g_hHeap, 8u, v10);
    v11 = *(unsigned __int16 **)(*((_QWORD *)v5 + 2) + 8LL * i);
    if ( !v11 || (int)StringCbCopyW(v11, (unsigned int)v10, a2[i]) < 0 )
      goto LABEL_19;
  }
  hServiceStartThread = CreateThread(0, 0, AudioSrvStartupThread, v5, 0, 0);
  if ( !hServiceStartThread )
  {
    dword_1801D40B8 = GetLastError();
    v12 = (unsigned int)dword_1801D40B8;
LABEL_20:
    ReportStatusToSCMgr(1, v12, 0);
    if ( *((_QWORD *)v5 + 2) )
    {
      for ( j = 0; j < *((_DWORD *)v5 + 2); ++j )
      {
        v14 = *(void **)(*((_QWORD *)v5 + 2) + 8LL * j);
        if ( v14 )
          HeapFree(g_hHeap, 0, v14);
      }
      HeapFree(g_hHeap, 0, *((LPVOID *)v5 + 2));
    }
    HeapFree(g_hHeap, 0, v5);
  }
}

```

## disassembly

```asm
0x180153e00  push    rbx
0x180153e02  push    rbp
0x180153e03  push    rsi
0x180153e04  push    rdi
0x180153e05  push    r12
0x180153e07  push    r13
0x180153e09  push    r14
0x180153e0b  push    r15
0x180153e0d  sub     rsp, 48h
0x180153e11  mov     r13d, 1
0x180153e17  mov     esi, ecx
0x180153e19  mov     r14, rdx
0x180153e1c  cmp     ecx, r13d
0x180153e1f  jb      loc_180154087
0x180153e25  lea     rax, WPP_ThisDir_CTLGUID_AudioTrace
0x180153e2c  mov     cs:qword_1801D4100, r13
0x180153e33  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180153e3a  xor     r12d, r12d
0x180153e3d  lea     rax, WPP_MAIN_CB
0x180153e44  mov     cs:qword_1801D40F8, r12
0x180153e4b  mov     cs:WPP_GLOBAL_Control, rax
0x180153e52  mov     cs:WPP_MAIN_CB, r12
0x180153e59  call    WppInitUm
0x180153e5e  mov     rcx, [r14]; lpServiceName
0x180153e61  lea     rdx, ?ServiceCtrl@@YAKKKPEAX0@Z; lpHandlerProc
0x180153e68  xor     r8d, r8d; lpContext
0x180153e6b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180153e71  mov     cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x180153e78  test    rax, rax
0x180153e7b  jz      loc_180154087
0x180153e81  xor     edx, edx
0x180153e83  mov     cs:ssStatus, 20h ; ' '
0x180153e8d  mov     r8d, 1388h
0x180153e93  mov     cs:dword_1801D40B8, r12d
0x180153e9a  lea     ecx, [rdx+2]
0x180153e9d  call    ReportStatusToSCMgr
0x180153ea2  test    eax, eax
0x180153ea4  jz      loc_180154087
0x180153eaa  xor     r9d, r9d; lpName
0x180153ead  xor     r8d, r8d; bInitialState
0x180153eb0  mov     edx, r13d; bManualReset
0x180153eb3  xor     ecx, ecx; lpEventAttributes
0x180153eb5  call    cs:__imp_CreateEventW
0x180153ebb  mov     cs:?hEventShutdown@@3PEAXEA, rax; void * hEventShutdown
0x180153ec2  mov     r8, rax
0x180153ec5  test    rax, rax
0x180153ec8  jnz     short loc_180153EE8
0x180153eca  call    cs:__imp_GetLastError
0x180153ed0  mov     cs:dword_1801D40B8, eax
0x180153ed6  mov     edx, eax
0x180153ed8  xor     r8d, r8d
0x180153edb  mov     ecx, r13d
0x180153ede  call    ReportStatusToSCMgr
0x180153ee3  jmp     loc_180154087
0x180153ee8  mov     rax, cs:?gpSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * gpSvchostSharedGlobals
0x180153eef  lea     r9, ?OnServiceShutdown@@YAXPEAXE@Z; OnServiceShutdown(void *,uchar)
0x180153ef6  mov     rdx, [r14]
0x180153ef9  lea     rcx, ?hEventShutdownWait@@3PEAXEA; void * hEventShutdownWait
0x180153f00  mov     edi, 8
0x180153f05  mov     dword ptr [rsp+88h+lpThreadId], edi
0x180153f09  mov     rax, [rax+0C0h]
0x180153f10  mov     qword ptr [rsp+88h+dwCreationFlags], r12
0x180153f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180153f1a  mov     rcx, cs:g_hHeap; hHeap
0x180153f21  lea     r8d, [rdi+10h]; dwBytes
0x180153f25  xor     edx, edx; dwFlags
0x180153f27  mov     cs:dword_1801D40B8, eax
0x180153f2d  call    cs:__imp_HeapAlloc
0x180153f33  mov     rbx, rax
0x180153f36  mov     edx, edi; dwFlags
0x180153f38  test    rax, rax
0x180153f3b  jnz     short loc_180153F45
0x180153f3d  mov     cs:dword_1801D40B8, edi
0x180153f43  jmp     short loc_180153ED8
0x180153f45  mov     rax, cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x180153f4c  mov     r8, rsi
0x180153f4f  mov     rcx, cs:g_hHeap; hHeap
0x180153f56  shl     r8, 3; dwBytes
0x180153f5a  mov     [rbx], rax
0x180153f5d  mov     [rbx+8], esi
0x180153f60  call    cs:__imp_HeapAlloc
0x180153f66  mov     [rbx+10h], rax
0x180153f6a  test    rax, rax
0x180153f6d  jz      loc_18015401A
0x180153f73  mov     edi, r12d
0x180153f76  cmp     edi, esi
0x180153f78  jnb     short loc_180153FD7
0x180153f7a  mov     ebp, edi
0x180153f7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180153f80  mov     rcx, [r14+rbp*8]
0x180153f84  inc     rax
0x180153f87  cmp     [rcx+rax*2], r12w
0x180153f8c  jnz     short loc_180153F84
0x180153f8e  mov     rcx, cs:g_hHeap; hHeap
0x180153f95  lea     eax, ds:2[rax*2]
0x180153f9c  mov     r8d, eax; dwBytes
0x180153f9f  mov     edx, 8; dwFlags
0x180153fa4  mov     r15d, eax
0x180153fa7  call    cs:__imp_HeapAlloc
0x180153fad  mov     rcx, [rbx+10h]
0x180153fb1  mov     [rcx+rbp*8], rax
0x180153fb5  mov     rax, [rbx+10h]
0x180153fb9  mov     rcx, [rax+rbp*8]; unsigned __int16 *
0x180153fbd  test    rcx, rcx
0x180153fc0  jz      short loc_180154015
0x180153fc2  mov     r8, [r14+rbp*8]; unsigned __int16 *
0x180153fc6  mov     edx, r15d; unsigned __int64
0x180153fc9  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180153fce  test    eax, eax
0x180153fd0  js      short loc_180154015
0x180153fd2  add     edi, r13d
0x180153fd5  jmp     short loc_180153F76
0x180153fd7  mov     [rsp+88h+lpThreadId], r12; lpThreadId
0x180153fdc  lea     r8, ?AudioSrvStartupThread@@YAKPEAX@Z; lpStartAddress
0x180153fe3  mov     r9, rbx; lpParameter
0x180153fe6  mov     [rsp+88h+dwCreationFlags], r12d; dwCreationFlags
0x180153feb  xor     edx, edx; dwStackSize
0x180153fed  xor     ecx, ecx; lpThreadAttributes
0x180153fef  call    cs:__imp_CreateThread
0x180153ff5  mov     cs:?hServiceStartThread@@3PEAXEA, rax; void * hServiceStartThread
0x180153ffc  test    rax, rax
0x180153fff  jnz     loc_180154087
0x180154005  call    cs:__imp_GetLastError
0x18015400b  mov     cs:dword_1801D40B8, eax
0x180154011  mov     edx, eax
0x180154013  jmp     short loc_180154022
0x180154015  mov     edi, 8
0x18015401a  mov     cs:dword_1801D40B8, edi
0x180154020  mov     edx, edi
0x180154022  xor     r8d, r8d
0x180154025  mov     ecx, r13d
0x180154028  call    ReportStatusToSCMgr
0x18015402d  cmp     [rbx+10h], r12
0x180154031  jz      short loc_180154075
0x180154033  mov     edi, r12d
0x180154036  cmp     [rbx+8], r12d
0x18015403a  jbe     short loc_180154062
0x18015403c  mov     rax, [rbx+10h]
0x180154040  mov     ecx, edi
0x180154042  mov     r8, [rax+rcx*8]; lpMem
0x180154046  test    r8, r8
0x180154049  jz      short loc_18015405A
0x18015404b  mov     rcx, cs:g_hHeap; hHeap
0x180154052  xor     edx, edx; dwFlags
0x180154054  call    cs:__imp_HeapFree
0x18015405a  add     edi, r13d
0x18015405d  cmp     edi, [rbx+8]
0x180154060  jb      short loc_18015403C
0x180154062  mov     r8, [rbx+10h]; lpMem
0x180154066  xor     edx, edx; dwFlags
0x180154068  mov     rcx, cs:g_hHeap; hHeap
0x18015406f  call    cs:__imp_HeapFree
0x180154075  mov     rcx, cs:g_hHeap; hHeap
0x18015407c  mov     r8, rbx; lpMem
0x18015407f  xor     edx, edx; dwFlags
0x180154081  call    cs:__imp_HeapFree
0x180154087  add     rsp, 48h
0x18015408b  pop     r15
0x18015408d  pop     r14
0x18015408f  pop     r13
0x180154091  pop     r12
0x180154093  pop     rdi
0x180154094  pop     rsi
0x180154095  pop     rbp
0x180154096  pop     rbx
0x180154097  retn
```
