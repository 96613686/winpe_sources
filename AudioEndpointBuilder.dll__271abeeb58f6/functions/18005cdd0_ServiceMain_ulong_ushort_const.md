# ServiceMain(ulong,ushort * * const)

- ea: `0x18005cdd0`
- end: `0x18005d068`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `664`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callees

- `0x18001f230`
- `0x18005cdd0`
- `0x18005d0c0`
- `0x18005d184`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ce85`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005ce85`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d03f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d051`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d03f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005d051`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cefd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cf30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cf77`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cefd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cf30`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005cf77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cfd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ce9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cfd5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005cfbf`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005cfbf`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18005ce3b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18005ce3b`

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
  qword_180086690 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_AudioTrace;
  qword_180086688 = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WPP_MAIN_CB = 0;
  WppInitUm();
  sshStatusHandle = RegisterServiceCtrlHandlerExW(*a2, ServiceCtrl, 0);
  if ( !sshStatusHandle )
    return;
  ssStatus = 32;
  dword_180086660 = 0;
  if ( !(unsigned int)ReportStatusToSCMgr(2, 0, 5000) )
    return;
  hEventShutdown = CreateEventW(0, 1, 0, 0);
  if ( !hEventShutdown )
  {
    dword_180086660 = GetLastError();
    v4 = (unsigned int)dword_180086660;
LABEL_6:
    ReportStatusToSCMgr(1, v4, 0);
    return;
  }
  dword_180086660 = (*((__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))gpSvchostSharedGlobals
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
    dword_180086660 = 8;
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
    dword_180086660 = 8;
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
    dword_180086660 = GetLastError();
    v12 = (unsigned int)dword_180086660;
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
0x18005cdd0  push    rbx
0x18005cdd2  push    rbp
0x18005cdd3  push    rsi
0x18005cdd4  push    rdi
0x18005cdd5  push    r12
0x18005cdd7  push    r13
0x18005cdd9  push    r14
0x18005cddb  push    r15
0x18005cddd  sub     rsp, 48h
0x18005cde1  mov     r13d, 1
0x18005cde7  mov     esi, ecx
0x18005cde9  mov     r14, rdx
0x18005cdec  cmp     ecx, r13d
0x18005cdef  jb      loc_18005D057
0x18005cdf5  lea     rax, WPP_ThisDir_CTLGUID_AudioTrace
0x18005cdfc  mov     cs:qword_180086690, r13
0x18005ce03  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18005ce0a  xor     r12d, r12d
0x18005ce0d  lea     rax, WPP_MAIN_CB
0x18005ce14  mov     cs:qword_180086688, r12
0x18005ce1b  mov     cs:WPP_GLOBAL_Control, rax
0x18005ce22  mov     cs:WPP_MAIN_CB, r12
0x18005ce29  call    WppInitUm
0x18005ce2e  mov     rcx, [r14]; lpServiceName
0x18005ce31  lea     rdx, ?ServiceCtrl@@YAKKKPEAX0@Z; lpHandlerProc
0x18005ce38  xor     r8d, r8d; lpContext
0x18005ce3b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18005ce41  mov     cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x18005ce48  test    rax, rax
0x18005ce4b  jz      loc_18005D057
0x18005ce51  xor     edx, edx
0x18005ce53  mov     cs:ssStatus, 20h ; ' '
0x18005ce5d  mov     r8d, 1388h
0x18005ce63  mov     cs:dword_180086660, r12d
0x18005ce6a  lea     ecx, [rdx+2]
0x18005ce6d  call    ReportStatusToSCMgr
0x18005ce72  test    eax, eax
0x18005ce74  jz      loc_18005D057
0x18005ce7a  xor     r9d, r9d; lpName
0x18005ce7d  xor     r8d, r8d; bInitialState
0x18005ce80  mov     edx, r13d; bManualReset
0x18005ce83  xor     ecx, ecx; lpEventAttributes
0x18005ce85  call    cs:__imp_CreateEventW
0x18005ce8b  mov     cs:?hEventShutdown@@3PEAXEA, rax; void * hEventShutdown
0x18005ce92  mov     r8, rax
0x18005ce95  test    rax, rax
0x18005ce98  jnz     short loc_18005CEB8
0x18005ce9a  call    cs:__imp_GetLastError
0x18005cea0  mov     cs:dword_180086660, eax
0x18005cea6  mov     edx, eax
0x18005cea8  xor     r8d, r8d
0x18005ceab  mov     ecx, r13d
0x18005ceae  call    ReportStatusToSCMgr
0x18005ceb3  jmp     loc_18005D057
0x18005ceb8  mov     rax, cs:?gpSvchostSharedGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * gpSvchostSharedGlobals
0x18005cebf  lea     r9, ?OnServiceShutdown@@YAXPEAXE@Z; OnServiceShutdown(void *,uchar)
0x18005cec6  mov     rdx, [r14]
0x18005cec9  lea     rcx, ?hEventShutdownWait@@3PEAXEA; void * hEventShutdownWait
0x18005ced0  mov     edi, 8
0x18005ced5  mov     dword ptr [rsp+88h+lpThreadId], edi
0x18005ced9  mov     rax, [rax+0C0h]
0x18005cee0  mov     qword ptr [rsp+88h+dwCreationFlags], r12
0x18005cee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ceea  mov     rcx, cs:g_hHeap; hHeap
0x18005cef1  lea     r8d, [rdi+10h]; dwBytes
0x18005cef5  xor     edx, edx; dwFlags
0x18005cef7  mov     cs:dword_180086660, eax
0x18005cefd  call    cs:__imp_HeapAlloc
0x18005cf03  mov     rbx, rax
0x18005cf06  mov     edx, edi; dwFlags
0x18005cf08  test    rax, rax
0x18005cf0b  jnz     short loc_18005CF15
0x18005cf0d  mov     cs:dword_180086660, edi
0x18005cf13  jmp     short loc_18005CEA8
0x18005cf15  mov     rax, cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x18005cf1c  mov     r8, rsi
0x18005cf1f  mov     rcx, cs:g_hHeap; hHeap
0x18005cf26  shl     r8, 3; dwBytes
0x18005cf2a  mov     [rbx], rax
0x18005cf2d  mov     [rbx+8], esi
0x18005cf30  call    cs:__imp_HeapAlloc
0x18005cf36  mov     [rbx+10h], rax
0x18005cf3a  test    rax, rax
0x18005cf3d  jz      loc_18005CFEA
0x18005cf43  mov     edi, r12d
0x18005cf46  cmp     edi, esi
0x18005cf48  jnb     short loc_18005CFA7
0x18005cf4a  mov     ebp, edi
0x18005cf4c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005cf50  mov     rcx, [r14+rbp*8]
0x18005cf54  inc     rax
0x18005cf57  cmp     [rcx+rax*2], r12w
0x18005cf5c  jnz     short loc_18005CF54
0x18005cf5e  mov     rcx, cs:g_hHeap; hHeap
0x18005cf65  lea     eax, ds:2[rax*2]
0x18005cf6c  mov     r8d, eax; dwBytes
0x18005cf6f  mov     edx, 8; dwFlags
0x18005cf74  mov     r15d, eax
0x18005cf77  call    cs:__imp_HeapAlloc
0x18005cf7d  mov     rcx, [rbx+10h]
0x18005cf81  mov     [rcx+rbp*8], rax
0x18005cf85  mov     rax, [rbx+10h]
0x18005cf89  mov     rcx, [rax+rbp*8]; unsigned __int16 *
0x18005cf8d  test    rcx, rcx
0x18005cf90  jz      short loc_18005CFE5
0x18005cf92  mov     r8, [r14+rbp*8]; unsigned __int16 *
0x18005cf96  mov     edx, r15d; unsigned __int64
0x18005cf99  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18005cf9e  test    eax, eax
0x18005cfa0  js      short loc_18005CFE5
0x18005cfa2  add     edi, r13d
0x18005cfa5  jmp     short loc_18005CF46
0x18005cfa7  mov     [rsp+88h+lpThreadId], r12; lpThreadId
0x18005cfac  lea     r8, ?AudioSrvStartupThread@@YAKPEAX@Z; lpStartAddress
0x18005cfb3  mov     r9, rbx; lpParameter
0x18005cfb6  mov     [rsp+88h+dwCreationFlags], r12d; dwCreationFlags
0x18005cfbb  xor     edx, edx; dwStackSize
0x18005cfbd  xor     ecx, ecx; lpThreadAttributes
0x18005cfbf  call    cs:__imp_CreateThread
0x18005cfc5  mov     cs:?hServiceStartThread@@3PEAXEA, rax; void * hServiceStartThread
0x18005cfcc  test    rax, rax
0x18005cfcf  jnz     loc_18005D057
0x18005cfd5  call    cs:__imp_GetLastError
0x18005cfdb  mov     cs:dword_180086660, eax
0x18005cfe1  mov     edx, eax
0x18005cfe3  jmp     short loc_18005CFF2
0x18005cfe5  mov     edi, 8
0x18005cfea  mov     cs:dword_180086660, edi
0x18005cff0  mov     edx, edi
0x18005cff2  xor     r8d, r8d
0x18005cff5  mov     ecx, r13d
0x18005cff8  call    ReportStatusToSCMgr
0x18005cffd  cmp     [rbx+10h], r12
0x18005d001  jz      short loc_18005D045
0x18005d003  mov     edi, r12d
0x18005d006  cmp     [rbx+8], r12d
0x18005d00a  jbe     short loc_18005D032
0x18005d00c  mov     rax, [rbx+10h]
0x18005d010  mov     ecx, edi
0x18005d012  mov     r8, [rax+rcx*8]; lpMem
0x18005d016  test    r8, r8
0x18005d019  jz      short loc_18005D02A
0x18005d01b  mov     rcx, cs:g_hHeap; hHeap
0x18005d022  xor     edx, edx; dwFlags
0x18005d024  call    cs:__imp_HeapFree
0x18005d02a  add     edi, r13d
0x18005d02d  cmp     edi, [rbx+8]
0x18005d030  jb      short loc_18005D00C
0x18005d032  mov     r8, [rbx+10h]; lpMem
0x18005d036  xor     edx, edx; dwFlags
0x18005d038  mov     rcx, cs:g_hHeap; hHeap
0x18005d03f  call    cs:__imp_HeapFree
0x18005d045  mov     rcx, cs:g_hHeap; hHeap
0x18005d04c  mov     r8, rbx; lpMem
0x18005d04f  xor     edx, edx; dwFlags
0x18005d051  call    cs:__imp_HeapFree
0x18005d057  add     rsp, 48h
0x18005d05b  pop     r15
0x18005d05d  pop     r14
0x18005d05f  pop     r13
0x18005d061  pop     r12
0x18005d063  pop     rdi
0x18005d064  pop     rsi
0x18005d065  pop     rbp
0x18005d066  pop     rbx
0x18005d067  retn
```
