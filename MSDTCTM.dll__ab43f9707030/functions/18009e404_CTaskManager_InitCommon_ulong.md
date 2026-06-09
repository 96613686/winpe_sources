# CTaskManager::InitCommon(ulong)

- ea: `0x18009e404`
- end: `0x18009e6ff`
- name: `?InitCommon@CTaskManager@@AEAAXK@Z`
- size: `763`
- prototype: `void __fastcall(CTaskManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000ea50`

## callees

- `0x1800240fc`
- `0x1800249ec`
- `0x1800849ac`
- `0x18009e404`
- `0x1800a0540`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18009e42f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18009e42f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e607`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e65c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e6a2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e607`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e65c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18009e6a2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e4d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e4ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e505`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e51d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e534`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e54c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e5b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e4d2`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e4ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e505`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e51d`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e534`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e54c`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18009e5b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e67d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e6c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e628`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e67d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009e6c3`

## string_xrefs

- `0x18009e6d0`: `XaMultiThreaded`
- `0x18009e4a5`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTaskManager::InitCommon(CTaskManager *this)
{
  unsigned __int64 v1; // rdi
  __int64 v2; // rax
  bool v3; // cf
  size_t v4; // rax
  _QWORD *v5; // rax
  struct CThreadParams *v6; // rbx
  HANDLE EventA; // rax
  unsigned int i; // ebx
  HANDLE v9; // rax
  __int64 v10; // rdi
  struct CThreadParams *v11; // rcx
  HANDLE Thread; // rax
  HANDLE v13; // rax
  HANDLE v14; // rax
  const unsigned __int16 *v15; // rcx
  unsigned int v16; // r8d
  struct _SYSTEM_INFO v17; // [rsp+30h] [rbp-48h] BYREF

  memset(&v17, 0, sizeof(v17));
  GetSystemInfo(&v17);
  CTaskManager::m_cbThreadPool = 3 * v17.dwNumberOfProcessors;
  v1 = 3 * v17.dwNumberOfProcessors;
  v2 = 88 * v1;
  if ( !is_mul_ok(v1, 0x58u) )
    v2 = -1;
  v3 = __CFADD__(v2, 8);
  v4 = v2 + 8;
  if ( v3 )
    v4 = -1;
  v5 = operator new[](v4);
  if ( v5 )
  {
    *v5 = v1;
    v6 = (struct CThreadParams *)(v5 + 1);
    `eh vector constructor iterator'(
      v5 + 1,
      0x58u,
      (unsigned int)v1,
      (void (*)(void *))CThreadParams::CThreadParams,
      (void (*)(void *))CThreadParams::~CThreadParams);
  }
  else
  {
    v6 = 0;
  }
  CTaskManager::m_rgbThreadPool = v6;
  if ( !v6 )
    XA_TRACE_FATAL(0xC000110B, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 138);
  CTaskManager::m_rghPendingWorkEvents = (void * near *)CreateEventA(0, 0, 0, 0);
  *(&CTaskManager::m_rghPendingWorkEvents + 1) = (void * near *)CreateEventA(0, 1, 0, 0);
  CTaskManager::m_rghPendingSerialWorkEvents = CreateEventA(0, 0, 0, 0);
  qword_1801548F8 = CreateEventA(0, 1, 0, 0);
  CTaskManager::m_rghPendingValidateWorkEvents = CreateEventA(0, 0, 0, 0);
  EventA = CreateEventA(0, 1, 0, 0);
  qword_1801548E8 = EventA;
  if ( !CTaskManager::m_rghPendingWorkEvents
    || !*(&CTaskManager::m_rghPendingWorkEvents + 1)
    || !CTaskManager::m_rghPendingSerialWorkEvents
    || !qword_1801548F8
    || !CTaskManager::m_rghPendingValidateWorkEvents
    || !EventA )
  {
    XA_TRACE_FATAL(0xC000110B, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 167);
  }
  for ( i = 0; i < CTaskManager::m_cbThreadPool; ++i )
  {
    v9 = CreateEventA(0, 0, 0, 0);
    v10 = 88LL * i;
    v11 = CTaskManager::m_rgbThreadPool;
    *(_QWORD *)((char *)CTaskManager::m_rgbThreadPool + v10 + 8) = v9;
    if ( !v9 )
    {
      XA_TRACE_FATAL(0xC000110B, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 179);
      v11 = CTaskManager::m_rgbThreadPool;
    }
    Thread = CreateThread(0, 0, CTaskManager::ThreadRoutine, (char *)v11 + v10, 1u, (LPDWORD)((char *)v11 + v10));
    if ( Thread )
      CloseHandle(Thread);
    else
      XA_TRACE_FATAL(0xC000110B, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 194);
  }
  v13 = CreateThread(0, 0, CTaskManager::SerialThreadRoutine, 0, 1u, &CTaskManager::m_dwSerialThread);
  if ( v13 )
    CloseHandle(v13);
  else
    XA_TRACE_FATAL(0xC000110B, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 213);
  v14 = CreateThread(0, 0, CTaskManager::ValidateThreadRoutine, 0, 1u, &CTaskManager::m_dwValidateThread);
  if ( v14 )
    CloseHandle(v14);
  else
    XA_TRACE_FATAL(0xC000110B, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 231);
  CTaskManager::m_taskClock = 1;
  CTaskManager::m_bDoTaskClock = GetLocalDTCProfileIntExW(v15, L"XaMultiThreaded", v16) != 0;
}

```

## disassembly

```asm
0x18009e404  mov     rax, rsp
0x18009e407  mov     [rax+10h], rbx
0x18009e40b  mov     [rax+18h], rbp
0x18009e40f  mov     [rax+8], rcx
0x18009e413  push    rdi
0x18009e414  push    r14
0x18009e416  push    r15
0x18009e418  sub     rsp, 60h
0x18009e41c  xorps   xmm0, xmm0
0x18009e41f  movups  xmmword ptr [rax-48h], xmm0
0x18009e423  movups  xmmword ptr [rax-38h], xmm0
0x18009e427  movups  xmmword ptr [rax-28h], xmm0
0x18009e42b  lea     rcx, [rax-48h]; lpSystemInfo
0x18009e42f  call    cs:__imp_GetSystemInfo
0x18009e435  mov     eax, [rsp+78h+var_28]
0x18009e439  lea     ecx, [rax+rax*2]
0x18009e43c  mov     cs:?m_cbThreadPool@CTaskManager@@0KA, ecx; ulong CTaskManager::m_cbThreadPool
0x18009e442  mov     edi, ecx
0x18009e444  mov     ebp, 58h ; 'X'
0x18009e449  mov     eax, ebp
0x18009e44b  mul     rdi
0x18009e44e  lea     rcx, [rbp-59h]
0x18009e452  cmovb   rax, rcx
0x18009e456  add     rax, 8
0x18009e45a  cmovb   rax, rcx
0x18009e45e  mov     rcx, rax; unsigned __int64
0x18009e461  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18009e466  mov     [rsp+78h+arg_0], rax
0x18009e46e  test    rax, rax
0x18009e471  jz      short loc_18009E49C
0x18009e473  mov     [rax], rdi
0x18009e476  lea     rbx, [rax+8]
0x18009e47a  lea     rax, ??1CThreadParams@@QEAA@XZ; CThreadParams::~CThreadParams(void)
0x18009e481  mov     qword ptr [rsp+78h+dwCreationFlags], rax; void (*)(void *)
0x18009e486  lea     r9, ??0CThreadParams@@QEAA@XZ; void (*)(void *)
0x18009e48d  mov     r8d, edi; unsigned __int64
0x18009e490  mov     edx, ebp; unsigned __int64
0x18009e492  mov     rcx, rbx; void *
0x18009e495  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18009e49a  jmp     short loc_18009E49E
0x18009e49c  xor     ebx, ebx
0x18009e49e  mov     cs:?m_rgbThreadPool@CTaskManager@@0PEAVCThreadParams@@EA, rbx; CThreadParams * CTaskManager::m_rgbThreadPool
0x18009e4a5  lea     rbp, aComComplusDtcD_81; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009e4ac  mov     r14d, 0C000110Bh
0x18009e4b2  test    rbx, rbx
0x18009e4b5  jnz     short loc_18009E4C8
0x18009e4b7  mov     r8d, 8Ah; int
0x18009e4bd  mov     rdx, rbp; char *
0x18009e4c0  mov     ecx, r14d; unsigned int
0x18009e4c3  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x18009e4c8  xor     r9d, r9d; lpName
0x18009e4cb  xor     r8d, r8d; bInitialState
0x18009e4ce  xor     edx, edx; bManualReset
0x18009e4d0  xor     ecx, ecx; lpEventAttributes
0x18009e4d2  call    cs:__imp_CreateEventA
0x18009e4d8  mov     qword ptr cs:?m_rghPendingWorkEvents@CTaskManager@@0PAPEAXA, rax; void * near * CTaskManager::m_rghPendingWorkEvents
0x18009e4df  xor     r9d, r9d; lpName
0x18009e4e2  xor     r8d, r8d; bInitialState
0x18009e4e5  lea     r15d, [r9+1]
0x18009e4e9  mov     edx, r15d; bManualReset
0x18009e4ec  xor     ecx, ecx; lpEventAttributes
0x18009e4ee  call    cs:__imp_CreateEventA
0x18009e4f4  mov     qword ptr cs:?m_rghPendingWorkEvents@CTaskManager@@0PAPEAXA+8, rax; void * near * CTaskManager::m_rghPendingWorkEvents
0x18009e4fb  xor     r9d, r9d; lpName
0x18009e4fe  xor     r8d, r8d; bInitialState
0x18009e501  xor     edx, edx; bManualReset
0x18009e503  xor     ecx, ecx; lpEventAttributes
0x18009e505  call    cs:__imp_CreateEventA
0x18009e50b  mov     cs:?m_rghPendingSerialWorkEvents@CTaskManager@@0PAPEAXA, rax; void * near * CTaskManager::m_rghPendingSerialWorkEvents
0x18009e512  xor     r9d, r9d; lpName
0x18009e515  xor     r8d, r8d; bInitialState
0x18009e518  mov     edx, r15d; bManualReset
0x18009e51b  xor     ecx, ecx; lpEventAttributes
0x18009e51d  call    cs:__imp_CreateEventA
0x18009e523  mov     cs:qword_1801548F8, rax
0x18009e52a  xor     r9d, r9d; lpName
0x18009e52d  xor     r8d, r8d; bInitialState
0x18009e530  xor     edx, edx; bManualReset
0x18009e532  xor     ecx, ecx; lpEventAttributes
0x18009e534  call    cs:__imp_CreateEventA
0x18009e53a  mov     cs:?m_rghPendingValidateWorkEvents@CTaskManager@@0PAPEAXA, rax; void * near * CTaskManager::m_rghPendingValidateWorkEvents
0x18009e541  xor     r9d, r9d; lpName
0x18009e544  xor     r8d, r8d; bInitialState
0x18009e547  mov     edx, r15d; bManualReset
0x18009e54a  xor     ecx, ecx; lpEventAttributes
0x18009e54c  call    cs:__imp_CreateEventA
0x18009e552  mov     cs:qword_1801548E8, rax
0x18009e559  cmp     qword ptr cs:?m_rghPendingWorkEvents@CTaskManager@@0PAPEAXA, 0; void * near * CTaskManager::m_rghPendingWorkEvents
0x18009e561  jz      short loc_18009E590
0x18009e563  cmp     qword ptr cs:?m_rghPendingWorkEvents@CTaskManager@@0PAPEAXA+8, 0; void * near * CTaskManager::m_rghPendingWorkEvents
0x18009e56b  jz      short loc_18009E590
0x18009e56d  cmp     cs:?m_rghPendingSerialWorkEvents@CTaskManager@@0PAPEAXA, 0; void * near * CTaskManager::m_rghPendingSerialWorkEvents
0x18009e575  jz      short loc_18009E590
0x18009e577  cmp     cs:qword_1801548F8, 0
0x18009e57f  jz      short loc_18009E590
0x18009e581  cmp     cs:?m_rghPendingValidateWorkEvents@CTaskManager@@0PAPEAXA, 0; void * near * CTaskManager::m_rghPendingValidateWorkEvents
0x18009e589  jz      short loc_18009E590
0x18009e58b  test    rax, rax
0x18009e58e  jnz     short loc_18009E5A1
0x18009e590  mov     r8d, 0A7h; int
0x18009e596  mov     rdx, rbp; char *
0x18009e599  mov     ecx, r14d; unsigned int
0x18009e59c  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x18009e5a1  xor     ebx, ebx
0x18009e5a3  cmp     cs:?m_cbThreadPool@CTaskManager@@0KA, ebx; ulong CTaskManager::m_cbThreadPool
0x18009e5a9  jbe     loc_18009E63D
0x18009e5af  xor     r9d, r9d; lpName
0x18009e5b2  xor     r8d, r8d; bInitialState
0x18009e5b5  xor     edx, edx; bManualReset
0x18009e5b7  xor     ecx, ecx; lpEventAttributes
0x18009e5b9  call    cs:__imp_CreateEventA
0x18009e5bf  mov     ecx, ebx
0x18009e5c1  imul    rdi, rcx, 58h ; 'X'
0x18009e5c5  mov     rcx, cs:?m_rgbThreadPool@CTaskManager@@0PEAVCThreadParams@@EA; CThreadParams * CTaskManager::m_rgbThreadPool
0x18009e5cc  mov     [rdi+rcx+8], rax
0x18009e5d1  test    rax, rax
0x18009e5d4  jnz     short loc_18009E5EE
0x18009e5d6  mov     r8d, 0B3h; int
0x18009e5dc  mov     rdx, rbp; char *
0x18009e5df  mov     ecx, r14d; unsigned int
0x18009e5e2  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x18009e5e7  mov     rcx, cs:?m_rgbThreadPool@CTaskManager@@0PEAVCThreadParams@@EA; CThreadParams * CTaskManager::m_rgbThreadPool
0x18009e5ee  lea     r9, [rdi+rcx]; lpParameter
0x18009e5f2  mov     [rsp+78h+lpThreadId], r9; lpThreadId
0x18009e5f7  mov     [rsp+78h+dwCreationFlags], r15d; dwCreationFlags
0x18009e5fc  lea     r8, ?ThreadRoutine@CTaskManager@@SAKPEAX@Z; lpStartAddress
0x18009e603  xor     edx, edx; dwStackSize
0x18009e605  xor     ecx, ecx; lpThreadAttributes
0x18009e607  call    cs:__imp_CreateThread
0x18009e60d  test    rax, rax
0x18009e610  jnz     short loc_18009E625
0x18009e612  mov     r8d, 0C2h; int
0x18009e618  mov     rdx, rbp; char *
0x18009e61b  mov     ecx, r14d; unsigned int
0x18009e61e  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x18009e623  jmp     short loc_18009E62E
0x18009e625  mov     rcx, rax; hObject
0x18009e628  call    cs:__imp_CloseHandle
0x18009e62e  add     ebx, r15d
0x18009e631  cmp     ebx, cs:?m_cbThreadPool@CTaskManager@@0KA; ulong CTaskManager::m_cbThreadPool
0x18009e637  jb      loc_18009E5AF
0x18009e63d  lea     rax, ?m_dwSerialThread@CTaskManager@@0KA; ulong CTaskManager::m_dwSerialThread
0x18009e644  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18009e649  mov     [rsp+78h+dwCreationFlags], r15d; dwCreationFlags
0x18009e64e  xor     r9d, r9d; lpParameter
0x18009e651  lea     r8, ?SerialThreadRoutine@CTaskManager@@SAKPEAX@Z; lpStartAddress
0x18009e658  xor     edx, edx; dwStackSize
0x18009e65a  xor     ecx, ecx; lpThreadAttributes
0x18009e65c  call    cs:__imp_CreateThread
0x18009e662  test    rax, rax
0x18009e665  jnz     short loc_18009E67A
0x18009e667  mov     r8d, 0D5h; int
0x18009e66d  mov     rdx, rbp; char *
0x18009e670  mov     ecx, r14d; unsigned int
0x18009e673  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x18009e678  jmp     short loc_18009E683
0x18009e67a  mov     rcx, rax; hObject
0x18009e67d  call    cs:__imp_CloseHandle
0x18009e683  lea     rax, ?m_dwValidateThread@CTaskManager@@0KA; ulong CTaskManager::m_dwValidateThread
0x18009e68a  mov     [rsp+78h+lpThreadId], rax; lpThreadId
0x18009e68f  mov     [rsp+78h+dwCreationFlags], r15d; dwCreationFlags
0x18009e694  xor     r9d, r9d; lpParameter
0x18009e697  lea     r8, ?ValidateThreadRoutine@CTaskManager@@SAKPEAX@Z; lpStartAddress
0x18009e69e  xor     edx, edx; dwStackSize
0x18009e6a0  xor     ecx, ecx; lpThreadAttributes
0x18009e6a2  call    cs:__imp_CreateThread
0x18009e6a8  test    rax, rax
0x18009e6ab  jnz     short loc_18009E6C0
0x18009e6ad  mov     r8d, 0E7h; int
0x18009e6b3  mov     rdx, rbp; char *
0x18009e6b6  mov     ecx, r14d; unsigned int
0x18009e6b9  call    ?XA_TRACE_FATAL@@YAXKPEADH@Z; XA_TRACE_FATAL(ulong,char *,int)
0x18009e6be  jmp     short loc_18009E6C9
0x18009e6c0  mov     rcx, rax; hObject
0x18009e6c3  call    cs:__imp_CloseHandle
0x18009e6c9  mov     cs:?m_taskClock@CTaskManager@@0_KA, r15; unsigned __int64 CTaskManager::m_taskClock
0x18009e6d0  lea     rdx, aXamultithreade; "XaMultiThreaded"
0x18009e6d7  call    ?GetLocalDTCProfileIntExW@@YAKPEBG0K@Z; GetLocalDTCProfileIntExW(ushort const *,ushort const *,ulong)
0x18009e6dc  xor     ecx, ecx
0x18009e6de  test    eax, eax
0x18009e6e0  setnz   cl
0x18009e6e3  mov     cs:?m_bDoTaskClock@CTaskManager@@0HA, ecx; int CTaskManager::m_bDoTaskClock
0x18009e6e9  lea     r11, [rsp+78h+var_18]
0x18009e6ee  mov     rbx, [r11+28h]
0x18009e6f2  mov     rbp, [r11+30h]
0x18009e6f6  mov     rsp, r11
0x18009e6f9  pop     r15
0x18009e6fb  pop     r14
0x18009e6fd  pop     rdi
0x18009e6fe  retn
```
