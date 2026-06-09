# RefCountNetworkIsolationContainers

- ea: `0x180027c00`
- end: `0x180028032`
- name: `RefCountNetworkIsolationContainers`
- size: `1074`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180010520`
- `0x180020dc0`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180027c00`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180027ec6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180027ec6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027fc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027f7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180027e81`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180027e9d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180027e81`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180027e9d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027f9d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180027f9d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027fac`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180027fac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027f12`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180027f12`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180027e65`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180027e65`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180027d81`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180027d81`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180027c92`
- `api-ms-win-service-winsvc-l1-1-0!OpenSCManagerA` at `0x180027c92`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180027d10`
- `api-ms-win-service-winsvc-l1-1-0!OpenServiceA` at `0x180027d10`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027f34`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027f42`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027f34`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180027f42`

## string_xrefs

- `0x180027c8b`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall RefCountNetworkIsolationContainers(int a1)
{
  DWORD LastError; // ebx
  int v3; // eax
  SC_HANDLE v4; // rdi
  SC_HANDLE v5; // r14
  PTP_WAIT ThreadpoolWait; // rsi
  HANDLE EventA; // rbp
  SC_HANDLE v8; // rax
  DWORD v9; // eax
  HANDLE v10; // r12
  void *v11; // r15
  SC_HANDLE v12; // rax
  struct _LIST_ENTRY *v13; // rcx
  __int64 v14; // rdx
  HANDLE Thread; // rax
  struct _TP_WAIT *v16; // rcx
  HANDLE v17; // rdx
  _SERVICE_STATUS ServiceStatus; // [rsp+38h] [rbp-60h] BYREF

  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 191, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids);
  }
  LastError = 0;
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !a1 )
  {
    if ( !--g_dwNetworkIsolationRefCount && g_hServiceChangeThread )
    {
      SetEvent(g_hExitServiceChangeThread);
      WaitForSingleObject(g_hServiceChangeThread, 0xFFFFFFFF);
      CloseHandle(g_hExitServiceChangeThread);
      CloseHandle(g_hServiceChangeThread);
      g_hServiceChangeThread = 0;
      g_hExitServiceChangeThread = 0;
    }
    goto LABEL_59;
  }
  v3 = g_dwNetworkIsolationRefCount;
  v4 = 0;
  v5 = 0;
  ThreadpoolWait = 0;
  EventA = 0;
  if ( g_dwNetworkIsolationRefCount )
    goto LABEL_44;
  v8 = OpenSCManagerA(0, "ServicesActive", 1u);
  v4 = v8;
  if ( v8 )
  {
    v10 = 0;
    v11 = 0;
    v12 = OpenServiceA(v8, "MPSSVC", 4u);
    v5 = v12;
    if ( !v12 )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_45;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_45;
      }
      v14 = 193;
      goto LABEL_19;
    }
    if ( !QueryServiceStatus(v12, &ServiceStatus) )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_45;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_45;
      }
      v14 = 194;
      goto LABEL_19;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 5u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control[1].Flink,
        195,
        WPP_67e2654e294337027f216ee3b31a23ff_Traceguids,
        ServiceStatus.dwCurrentState);
      v13 = WPP_GLOBAL_Control;
    }
    if ( ServiceStatus.dwCurrentState != 4 )
    {
      LastError = 1062;
      if ( v13 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(v13[1].Blink) & 0x2000) == 0
        || BYTE1(v13[1].Blink) < 2u )
      {
        goto LABEL_45;
      }
      v14 = 196;
LABEL_19:
      WPP_SF_d(v13[1].Flink, v14, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
      goto LABEL_45;
    }
    if ( !g_hangUpThreadPool )
    {
      ThreadpoolWait = CreateThreadpoolWait(HangUpThread, 0, 0);
      if ( !ThreadpoolWait )
        goto LABEL_45;
      EventA = CreateEventA(0, 0, 0, 0);
      if ( !EventA )
        goto LABEL_45;
    }
    v10 = CreateEventA(0, 0, 0, 0);
    if ( !v10 )
      goto LABEL_45;
    Thread = CreateThread(0, 0, ServiceChangeProc, 0, 0, 0);
    v11 = Thread;
    if ( !Thread )
      goto LABEL_45;
    v16 = g_hangUpThreadPool;
    if ( g_hangUpThreadPool )
    {
      v17 = g_hangUpEvent;
    }
    else
    {
      v17 = EventA;
      v16 = ThreadpoolWait;
      EventA = 0;
      g_hangUpEvent = v17;
      ThreadpoolWait = 0;
      g_hangUpThreadPool = v16;
    }
    g_hExitServiceChangeThread = v10;
    g_hServiceChangeThread = Thread;
    SetThreadpoolWait(v16, v17, 0);
    v3 = g_dwNetworkIsolationRefCount;
LABEL_44:
    g_dwNetworkIsolationRefCount = v3 + 1;
    v10 = 0;
    v11 = 0;
    if ( !v4 )
    {
LABEL_46:
      if ( v5 )
        CloseServiceHandle(v5);
      if ( EventA )
        CloseHandle(EventA);
      if ( ThreadpoolWait )
        CloseHandle(ThreadpoolWait);
      if ( v10 )
        CloseHandle(v10);
      if ( v11 )
        CloseHandle(v11);
      goto LABEL_59;
    }
LABEL_45:
    CloseServiceHandle(v4);
    goto LABEL_46;
  }
  v9 = GetLastError();
  LastError = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      return LastError;
    if ( (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0 && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 192, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, v9);
  }
LABEL_59:
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 197, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x180027c00  push    rbx
0x180027c02  push    rbp
0x180027c03  push    rsi
0x180027c04  push    rdi
0x180027c05  push    r12
0x180027c07  push    r14
0x180027c09  push    r15
0x180027c0b  sub     rsp, 60h
0x180027c0f  mov     rax, cs:__security_cookie
0x180027c16  xor     rax, rsp
0x180027c19  mov     [rsp+98h+var_40], rax
0x180027c1e  mov     edi, ecx
0x180027c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180027c27  lea     rax, WPP_GLOBAL_Control
0x180027c2e  cmp     rcx, rax
0x180027c31  jz      short loc_180027C57
0x180027c33  test    dword ptr [rcx+1Ch], 2000h
0x180027c3a  jz      short loc_180027C57
0x180027c3c  cmp     byte ptr [rcx+19h], 6
0x180027c40  jb      short loc_180027C57
0x180027c42  mov     rcx, [rcx+10h]
0x180027c46  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180027c4d  mov     edx, 0BFh
0x180027c52  call    WPP_SF_
0x180027c57  xorps   xmm0, xmm0
0x180027c5a  xor     ebx, ebx
0x180027c5c  movups  xmmword ptr [rsp+98h+ServiceStatus.dwServiceType], xmm0
0x180027c61  movups  xmmword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], xmm0
0x180027c66  test    edi, edi
0x180027c68  jz      loc_180027F82
0x180027c6e  mov     eax, cs:g_dwNetworkIsolationRefCount
0x180027c74  xor     edi, edi
0x180027c76  xor     r14d, r14d
0x180027c79  xor     esi, esi
0x180027c7b  xor     ebp, ebp
0x180027c7d  test    eax, eax
0x180027c7f  jnz     loc_180027F1E
0x180027c85  lea     r8d, [rbx+1]; dwDesiredAccess
0x180027c89  xor     ecx, ecx; lpMachineName
0x180027c8b  lea     rdx, DatabaseName; "ServicesActive"
0x180027c92  call    cs:__imp_OpenSCManagerA
0x180027c98  mov     rdi, rax
0x180027c9b  test    rax, rax
0x180027c9e  jnz     short loc_180027CFB
0x180027ca0  call    cs:__imp_GetLastError
0x180027ca6  mov     ebx, eax
0x180027ca8  test    eax, eax
0x180027caa  jz      loc_180027FDA
0x180027cb0  mov     rcx, cs:WPP_GLOBAL_Control
0x180027cb7  lea     rdi, WPP_GLOBAL_Control
0x180027cbe  cmp     rcx, rdi
0x180027cc1  jz      loc_180028014
0x180027cc7  test    dword ptr [rcx+1Ch], 2000h
0x180027cce  jz      loc_180027FE1
0x180027cd4  cmp     byte ptr [rcx+19h], 2
0x180027cd8  jb      loc_180027FE1
0x180027cde  mov     rcx, [rcx+10h]
0x180027ce2  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180027ce9  mov     edx, 0C0h
0x180027cee  mov     r9d, eax
0x180027cf1  call    WPP_SF_d
0x180027cf6  jmp     loc_180027FE1
0x180027cfb  xor     r12d, r12d
0x180027cfe  lea     rdx, ServiceName; "MPSSVC"
0x180027d05  mov     rcx, rax; hSCManager
0x180027d08  xor     r15d, r15d
0x180027d0b  lea     r8d, [r12+4]; dwDesiredAccess
0x180027d10  call    cs:__imp_OpenServiceA
0x180027d16  mov     r14, rax
0x180027d19  test    rax, rax
0x180027d1c  jnz     short loc_180027D79
0x180027d1e  call    cs:__imp_GetLastError
0x180027d24  mov     ebx, eax
0x180027d26  test    eax, eax
0x180027d28  jz      loc_180027F31
0x180027d2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d35  lea     rax, WPP_GLOBAL_Control
0x180027d3c  cmp     rcx, rax
0x180027d3f  jz      loc_180027F31
0x180027d45  test    dword ptr [rcx+1Ch], 2000h
0x180027d4c  jz      loc_180027F31
0x180027d52  cmp     byte ptr [rcx+19h], 2
0x180027d56  jb      loc_180027F31
0x180027d5c  mov     edx, 0C1h
0x180027d61  mov     rcx, [rcx+10h]
0x180027d65  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180027d6c  mov     r9d, ebx
0x180027d6f  call    WPP_SF_d
0x180027d74  jmp     loc_180027F31
0x180027d79  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x180027d7e  mov     rcx, rax; hService
0x180027d81  call    cs:__imp_QueryServiceStatus
0x180027d87  test    eax, eax
0x180027d89  jnz     short loc_180027DD0
0x180027d8b  call    cs:__imp_GetLastError
0x180027d91  mov     ebx, eax
0x180027d93  test    eax, eax
0x180027d95  jz      loc_180027F31
0x180027d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180027da2  lea     rax, WPP_GLOBAL_Control
0x180027da9  cmp     rcx, rax
0x180027dac  jz      loc_180027F31
0x180027db2  test    dword ptr [rcx+1Ch], 2000h
0x180027db9  jz      loc_180027F31
0x180027dbf  cmp     byte ptr [rcx+19h], 2
0x180027dc3  jb      loc_180027F31
0x180027dc9  mov     edx, 0C2h
0x180027dce  jmp     short loc_180027D61
0x180027dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180027dd7  lea     rax, WPP_GLOBAL_Control
0x180027dde  cmp     rcx, rax
0x180027de1  jz      short loc_180027E1A
0x180027de3  test    dword ptr [rcx+1Ch], 2000h
0x180027dea  jz      short loc_180027E1A
0x180027dec  cmp     byte ptr [rcx+19h], 5
0x180027df0  jb      short loc_180027E1A
0x180027df2  mov     r9d, [rsp+98h+ServiceStatus.dwCurrentState]
0x180027df7  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180027dfe  mov     rcx, [rcx+10h]
0x180027e02  mov     edx, 0C3h
0x180027e07  call    WPP_SF_d
0x180027e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e13  lea     rax, WPP_GLOBAL_Control
0x180027e1a  cmp     [rsp+98h+ServiceStatus.dwCurrentState], 4
0x180027e1f  jz      short loc_180027E50
0x180027e21  mov     ebx, 426h
0x180027e26  cmp     rcx, rax
0x180027e29  jz      loc_180027F31
0x180027e2f  test    dword ptr [rcx+1Ch], 2000h
0x180027e36  jz      loc_180027F31
0x180027e3c  cmp     byte ptr [rcx+19h], 2
0x180027e40  jb      loc_180027F31
0x180027e46  mov     edx, 0C4h
0x180027e4b  jmp     loc_180027D61
0x180027e50  cmp     cs:g_hangUpThreadPool, rbx
0x180027e57  jnz     short loc_180027E93
0x180027e59  xor     r8d, r8d; pcbe
0x180027e5c  lea     rcx, HangUpThread; pfnwa
0x180027e63  xor     edx, edx; pv
0x180027e65  call    cs:__imp_CreateThreadpoolWait
0x180027e6b  mov     rsi, rax
0x180027e6e  test    rax, rax
0x180027e71  jz      loc_180027F31
0x180027e77  xor     r9d, r9d; lpName
0x180027e7a  xor     r8d, r8d; bInitialState
0x180027e7d  xor     edx, edx; bManualReset
0x180027e7f  xor     ecx, ecx; lpEventAttributes
0x180027e81  call    cs:__imp_CreateEventA
0x180027e87  mov     rbp, rax
0x180027e8a  test    rax, rax
0x180027e8d  jz      loc_180027F31
0x180027e93  xor     r9d, r9d; lpName
0x180027e96  xor     r8d, r8d; bInitialState
0x180027e99  xor     edx, edx; bManualReset
0x180027e9b  xor     ecx, ecx; lpEventAttributes
0x180027e9d  call    cs:__imp_CreateEventA
0x180027ea3  mov     r12, rax
0x180027ea6  test    rax, rax
0x180027ea9  jz      loc_180027F31
0x180027eaf  mov     [rsp+98h+lpThreadId], rbx; lpThreadId
0x180027eb4  lea     r8, ServiceChangeProc; lpStartAddress
0x180027ebb  xor     r9d, r9d; lpParameter
0x180027ebe  mov     [rsp+98h+dwCreationFlags], ebx; dwCreationFlags
0x180027ec2  xor     edx, edx; dwStackSize
0x180027ec4  xor     ecx, ecx; lpThreadAttributes
0x180027ec6  call    cs:__imp_CreateThread
0x180027ecc  mov     r15, rax
0x180027ecf  test    rax, rax
0x180027ed2  jz      short loc_180027F31
0x180027ed4  mov     rcx, cs:g_hangUpThreadPool; pwa
0x180027edb  test    rcx, rcx
0x180027ede  jnz     short loc_180027EFA
0x180027ee0  mov     rdx, rbp
0x180027ee3  mov     rcx, rsi
0x180027ee6  xor     ebp, ebp
0x180027ee8  mov     cs:g_hangUpEvent, rdx
0x180027eef  xor     esi, esi
0x180027ef1  mov     cs:g_hangUpThreadPool, rcx
0x180027ef8  jmp     short loc_180027F01
0x180027efa  mov     rdx, cs:g_hangUpEvent; h
0x180027f01  xor     r8d, r8d; pftTimeout
0x180027f04  mov     cs:g_hExitServiceChangeThread, r12
0x180027f0b  mov     cs:g_hServiceChangeThread, rax
0x180027f12  call    cs:__imp_SetThreadpoolWait
0x180027f18  mov     eax, cs:g_dwNetworkIsolationRefCount
0x180027f1e  inc     eax
0x180027f20  mov     cs:g_dwNetworkIsolationRefCount, eax
0x180027f26  xor     r12d, r12d
0x180027f29  xor     r15d, r15d
0x180027f2c  test    rdi, rdi
0x180027f2f  jz      short loc_180027F3A
0x180027f31  mov     rcx, rdi; hSCObject
0x180027f34  call    cs:__imp_CloseServiceHandle
0x180027f3a  test    r14, r14
0x180027f3d  jz      short loc_180027F48
0x180027f3f  mov     rcx, r14; hSCObject
0x180027f42  call    cs:__imp_CloseServiceHandle
0x180027f48  test    rbp, rbp
0x180027f4b  jz      short loc_180027F56
0x180027f4d  mov     rcx, rbp; hObject
0x180027f50  call    cs:__imp_CloseHandle
0x180027f56  test    rsi, rsi
0x180027f59  jz      short loc_180027F64
0x180027f5b  mov     rcx, rsi; hObject
0x180027f5e  call    cs:__imp_CloseHandle
0x180027f64  test    r12, r12
0x180027f67  jz      short loc_180027F72
0x180027f69  mov     rcx, r12; hObject
0x180027f6c  call    cs:__imp_CloseHandle
0x180027f72  test    r15, r15
0x180027f75  jz      short loc_180027FDA
0x180027f77  mov     rcx, r15; hObject
0x180027f7a  call    cs:__imp_CloseHandle
0x180027f80  jmp     short loc_180027FDA
0x180027f82  or      edi, 0FFFFFFFFh
0x180027f85  add     cs:g_dwNetworkIsolationRefCount, edi
0x180027f8b  jnz     short loc_180027FDA
0x180027f8d  cmp     cs:g_hServiceChangeThread, rbx
0x180027f94  jz      short loc_180027FDA
0x180027f96  mov     rcx, cs:g_hExitServiceChangeThread; hEvent
0x180027f9d  call    cs:__imp_SetEvent
0x180027fa3  mov     rcx, cs:g_hServiceChangeThread; hHandle
0x180027faa  mov     edx, edi; dwMilliseconds
0x180027fac  call    cs:__imp_WaitForSingleObject
0x180027fb2  mov     rcx, cs:g_hExitServiceChangeThread; hObject
0x180027fb9  call    cs:__imp_CloseHandle
0x180027fbf  mov     rcx, cs:g_hServiceChangeThread; hObject
0x180027fc6  call    cs:__imp_CloseHandle
0x180027fcc  mov     cs:g_hServiceChangeThread, rbx
0x180027fd3  mov     cs:g_hExitServiceChangeThread, rbx
0x180027fda  lea     rdi, WPP_GLOBAL_Control
0x180027fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fe8  cmp     rcx, rdi
0x180027feb  jz      short loc_180028014
0x180027fed  test    dword ptr [rcx+1Ch], 2000h
0x180027ff4  jz      short loc_180028014
0x180027ff6  cmp     byte ptr [rcx+19h], 6
0x180027ffa  jb      short loc_180028014
0x180027ffc  mov     rcx, [rcx+10h]
0x180028000  lea     r8, WPP_67e2654e294337027f216ee3b31a23ff_Traceguids
0x180028007  mov     edx, 0C5h
0x18002800c  mov     r9d, ebx
0x18002800f  call    WPP_SF_d
0x180028014  mov     eax, ebx
0x180028016  mov     rcx, [rsp+98h+var_40]
0x18002801b  xor     rcx, rsp; StackCookie
0x18002801e  call    __security_check_cookie
0x180028023  add     rsp, 60h
0x180028027  pop     r15
0x180028029  pop     r14
0x18002802b  pop     r12
0x18002802d  pop     rdi
0x18002802e  pop     rsi
0x18002802f  pop     rbp
0x180028030  pop     rbx
0x180028031  retn
```
