# ServiceMain(ulong,ushort * * const)

- ea: `0x180154b10`
- end: `0x180154da8`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `664`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18000a470`
- `0x180154b10`
- `0x180154e00`
- `0x180154f58`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180154bc5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180154bc5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180154c3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180154c70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180154cb7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180154c3d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180154c70`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180154cb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154d91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154d64`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154d7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180154d91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154d15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154d15`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180154cff`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180154cff`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180154b7b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180154b7b`

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
  qword_1801D5140 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_AudioTrace;
  qword_1801D5138 = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  sshStatusHandle = RegisterServiceCtrlHandlerExW(*a2, ServiceCtrl, 0);
  if ( !sshStatusHandle )
    return;
  ssStatus = 32;
  dword_1801D5100 = 0;
  if ( !(unsigned int)ReportStatusToSCMgr(2, 0, 5000) )
    return;
  hEventShutdown = CreateEventW(0, 1, 0, 0);
  if ( !hEventShutdown )
  {
    dword_1801D5100 = GetLastError();
    v4 = (unsigned int)dword_1801D5100;
LABEL_6:
    ReportStatusToSCMgr(1, v4, 0);
    return;
  }
  dword_1801D5100 = (*((__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))gpSvchostSharedGlobals
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
    dword_1801D5100 = 8;
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
    dword_1801D5100 = 8;
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
    dword_1801D5100 = GetLastError();
    v12 = (unsigned int)dword_1801D5100;
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
0x180154b10  push    rbx
0x180154b12  push    rbp
0x180154b13  push    rsi
0x180154b14  push    rdi
0x180154b15  push    r12
0x180154b17  push    r13
0x180154b19  push    r14
0x180154b1b  push    r15
0x180154b1d  sub     rsp, 48h
0x180154b21  mov     r13d, 1
0x180154b27  mov     esi, ecx
0x180154b29  mov     r14, rdx
0x180154b2c  cmp     ecx, r13d
0x180154b2f  jb      loc_180154D97
0x180154b35  lea     rax, WPP_ThisDir_CTLGUID_AudioTrace
0x180154b3c  mov     cs:qword_1801D5140, r13
0x180154b43  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180154b4a  xor     r12d, r12d
0x180154b4d  lea     rax, WPP_MAIN_CB
0x180154b54  mov     cs:qword_1801D5138, r12
0x180154b5b  mov     cs:WPP_GLOBAL_Control, rax
0x180154b62  mov     cs:WPP_MAIN_CB, r12
0x180154b69  call    WppInitUm
0x180154b6e  mov     rcx, [r14]; lpServiceName
0x180154b71  lea     rdx, ?ServiceCtrl@@YAKKKPEAX0@Z; lpHandlerProc
0x180154b78  xor     r8d, r8d; lpContext
0x180154b7b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180154b81  mov     cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x180154b88  test    rax, rax
0x180154b8b  jz      loc_180154D97
0x180154b91  xor     edx, edx
0x180154b93  mov     cs:ssStatus, 20h ; ' '
0x180154b9d  mov     r8d, 1388h
0x180154ba3  mov     cs:dword_1801D5100, r12d
0x180154baa  lea     ecx, [rdx+2]
0x180154bad  call    ReportStatusToSCMgr
0x180154bb2  test    eax, eax
0x180154bb4  jz      loc_180154D97
0x180154bba  xor     r9d, r9d; lpName
0x180154bbd  xor     r8d, r8d; bInitialState
0x180154bc0  mov     edx, r13d; bManualReset
0x180154bc3  xor     ecx, ecx; lpEventAttributes
0x180154bc5  call    cs:__imp_CreateEventW
0x180154bcb  mov     cs:?hEventShutdown@@3PEAXEA, rax; void * hEventShutdown
0x180154bd2  mov     r8, rax
0x180154bd5  test    rax, rax
0x180154bd8  jnz     short loc_180154BF8
0x180154bda  call    cs:__imp_GetLastError
0x180154be0  mov     cs:dword_1801D5100, eax
0x180154be6  mov     edx, eax
0x180154be8  xor     r8d, r8d
0x180154beb  mov     ecx, r13d
0x180154bee  call    ReportStatusToSCMgr
0x180154bf3  jmp     loc_180154D97
0x180154bf8  mov     rax, cs:?gpSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * gpSvchostSharedGlobals
0x180154bff  lea     r9, ?OnServiceShutdown@@YAXPEAXE@Z; OnServiceShutdown(void *,uchar)
0x180154c06  mov     rdx, [r14]
0x180154c09  lea     rcx, ?hEventShutdownWait@@3PEAXEA; void * hEventShutdownWait
0x180154c10  mov     edi, 8
0x180154c15  mov     dword ptr [rsp+88h+lpThreadId], edi
0x180154c19  mov     rax, [rax+0C0h]
0x180154c20  mov     qword ptr [rsp+88h+dwCreationFlags], r12
0x180154c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154c2a  mov     rcx, cs:g_hHeap; hHeap
0x180154c31  lea     r8d, [rdi+10h]; dwBytes
0x180154c35  xor     edx, edx; dwFlags
0x180154c37  mov     cs:dword_1801D5100, eax
0x180154c3d  call    cs:__imp_HeapAlloc
0x180154c43  mov     rbx, rax
0x180154c46  mov     edx, edi; dwFlags
0x180154c48  test    rax, rax
0x180154c4b  jnz     short loc_180154C55
0x180154c4d  mov     cs:dword_1801D5100, edi
0x180154c53  jmp     short loc_180154BE8
0x180154c55  mov     rax, cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x180154c5c  mov     r8, rsi
0x180154c5f  mov     rcx, cs:g_hHeap; hHeap
0x180154c66  shl     r8, 3; dwBytes
0x180154c6a  mov     [rbx], rax
0x180154c6d  mov     [rbx+8], esi
0x180154c70  call    cs:__imp_HeapAlloc
0x180154c76  mov     [rbx+10h], rax
0x180154c7a  test    rax, rax
0x180154c7d  jz      loc_180154D2A
0x180154c83  mov     edi, r12d
0x180154c86  cmp     edi, esi
0x180154c88  jnb     short loc_180154CE7
0x180154c8a  mov     ebp, edi
0x180154c8c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180154c90  mov     rcx, [r14+rbp*8]
0x180154c94  inc     rax
0x180154c97  cmp     [rcx+rax*2], r12w
0x180154c9c  jnz     short loc_180154C94
0x180154c9e  mov     rcx, cs:g_hHeap; hHeap
0x180154ca5  lea     eax, ds:2[rax*2]
0x180154cac  mov     r8d, eax; dwBytes
0x180154caf  mov     edx, 8; dwFlags
0x180154cb4  mov     r15d, eax
0x180154cb7  call    cs:__imp_HeapAlloc
0x180154cbd  mov     rcx, [rbx+10h]
0x180154cc1  mov     [rcx+rbp*8], rax
0x180154cc5  mov     rax, [rbx+10h]
0x180154cc9  mov     rcx, [rax+rbp*8]; unsigned __int16 *
0x180154ccd  test    rcx, rcx
0x180154cd0  jz      short loc_180154D25
0x180154cd2  mov     r8, [r14+rbp*8]; unsigned __int16 *
0x180154cd6  mov     edx, r15d; unsigned __int64
0x180154cd9  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180154cde  test    eax, eax
0x180154ce0  js      short loc_180154D25
0x180154ce2  add     edi, r13d
0x180154ce5  jmp     short loc_180154C86
0x180154ce7  mov     [rsp+88h+lpThreadId], r12; lpThreadId
0x180154cec  lea     r8, ?AudioSrvStartupThread@@YAKPEAX@Z; lpStartAddress
0x180154cf3  mov     r9, rbx; lpParameter
0x180154cf6  mov     [rsp+88h+dwCreationFlags], r12d; dwCreationFlags
0x180154cfb  xor     edx, edx; dwStackSize
0x180154cfd  xor     ecx, ecx; lpThreadAttributes
0x180154cff  call    cs:__imp_CreateThread
0x180154d05  mov     cs:?hServiceStartThread@@3PEAXEA, rax; void * hServiceStartThread
0x180154d0c  test    rax, rax
0x180154d0f  jnz     loc_180154D97
0x180154d15  call    cs:__imp_GetLastError
0x180154d1b  mov     cs:dword_1801D5100, eax
0x180154d21  mov     edx, eax
0x180154d23  jmp     short loc_180154D32
0x180154d25  mov     edi, 8
0x180154d2a  mov     cs:dword_1801D5100, edi
0x180154d30  mov     edx, edi
0x180154d32  xor     r8d, r8d
0x180154d35  mov     ecx, r13d
0x180154d38  call    ReportStatusToSCMgr
0x180154d3d  cmp     [rbx+10h], r12
0x180154d41  jz      short loc_180154D85
0x180154d43  mov     edi, r12d
0x180154d46  cmp     [rbx+8], r12d
0x180154d4a  jbe     short loc_180154D72
0x180154d4c  mov     rax, [rbx+10h]
0x180154d50  mov     ecx, edi
0x180154d52  mov     r8, [rax+rcx*8]; lpMem
0x180154d56  test    r8, r8
0x180154d59  jz      short loc_180154D6A
0x180154d5b  mov     rcx, cs:g_hHeap; hHeap
0x180154d62  xor     edx, edx; dwFlags
0x180154d64  call    cs:__imp_HeapFree
0x180154d6a  add     edi, r13d
0x180154d6d  cmp     edi, [rbx+8]
0x180154d70  jb      short loc_180154D4C
0x180154d72  mov     r8, [rbx+10h]; lpMem
0x180154d76  xor     edx, edx; dwFlags
0x180154d78  mov     rcx, cs:g_hHeap; hHeap
0x180154d7f  call    cs:__imp_HeapFree
0x180154d85  mov     rcx, cs:g_hHeap; hHeap
0x180154d8c  mov     r8, rbx; lpMem
0x180154d8f  xor     edx, edx; dwFlags
0x180154d91  call    cs:__imp_HeapFree
0x180154d97  add     rsp, 48h
0x180154d9b  pop     r15
0x180154d9d  pop     r14
0x180154d9f  pop     r13
0x180154da1  pop     r12
0x180154da3  pop     rdi
0x180154da4  pop     rsi
0x180154da5  pop     rbp
0x180154da6  pop     rbx
0x180154da7  retn
```
