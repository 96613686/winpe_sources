# CalaisStop(void)

- ea: `0x18002a7e4`
- end: `0x18002a96a`
- name: `?CalaisStop@@YAXXZ`
- size: `390`
- prototype: `void __fastcall(__int64, __int64, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x180024710`

## callees

- `0x180002680`
- `0x180012380`
- `0x1800123a0`
- `0x180017b44`
- `0x18002438c`
- `0x18002a7e4`
- `0x18002ef4c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a7f5`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002a7f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a8eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a8eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a915`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002a899`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18002a899`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002a88c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18002a88c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002a8fd`

## pseudocode

```c
void __fastcall CalaisStop(__int64 a1, __int64 a2, const unsigned __int8 *a3, const unsigned __int8 *a4)
{
  int v4; // ebx
  const unsigned __int8 *v5; // r8
  const unsigned __int8 *v6; // r9
  unsigned int v7; // edx
  __int64 i; // rbx
  CCriticalSectionObject *v9; // rcx
  char v10; // [rsp+30h] [rbp+8h] BYREF

  while ( _InterlockedExchange((volatile __int32 *)&g_fBlockServiceHandler, 1) )
    Sleep(0x64u);
  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v10, g_pcsControlLocks, a3, a4);
  v4 = HIDWORD(qword_18004B0C8);
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v10);
  while ( v4 )
    CalaisRemoveReader(--v4);
  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v10, qword_18004BA68, v5, v6);
  while ( l_dwReaderActionsInProgress )
    (*(void (__fastcall **)(struct CCriticalSectionObject *, RTL_CONDITION_VARIABLE *))(*(_QWORD *)qword_18004BA68 + 24LL))(
      qword_18004BA68,
      &l_cvReaderAsyncActionFinished);
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v10);
  if ( ptpcg )
  {
    CloseThreadpoolCleanupGroupMembers(ptpcg, 0, 0);
    CloseThreadpoolCleanupGroup(ptpcg);
    ptpcg = 0;
  }
  dword_18004BF6C = 0;
  if ( !CloseHandle(g_hCalaisShutdown) )
    GetLastError();
  g_hCalaisShutdown = 0;
  CPowerSupport::CleanUp();
  if ( dword_18004BF0C )
  {
    EnterCriticalSection(&stru_18004BAD0);
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    LeaveCriticalSection(&stru_18004BAD0);
  }
  if ( g_phReaderChangeEvent )
  {
    CMultiEvent::`scalar deleting destructor'(g_phReaderChangeEvent, v7);
    g_phReaderChangeEvent = 0;
  }
  for ( i = 0; i != 4; ++i )
  {
    v9 = *(&g_pcsControlLocks + i);
    if ( v9 )
      CCriticalSectionObject::`scalar deleting destructor'(v9, v7);
    *(&g_pcsControlLocks + i) = 0;
  }
}

```

## disassembly

```asm
0x18002a7e4  mov     [rsp+arg_8], rbx
0x18002a7e9  push    rsi
0x18002a7ea  sub     rsp, 20h
0x18002a7ee  jmp     short loc_18002A7FB
0x18002a7f0  mov     ecx, 64h ; 'd'; dwMilliseconds
0x18002a7f5  call    cs:__imp_Sleep
0x18002a7fb  mov     eax, 1
0x18002a800  xchg    eax, cs:?g_fBlockServiceHandler@@3KA; ulong g_fBlockServiceHandler
0x18002a806  test    eax, eax
0x18002a808  jnz     short loc_18002A7F0
0x18002a80a  mov     rdx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; struct CCriticalSectionObject *
0x18002a811  lea     rcx, [rsp+28h+arg_0]; this
0x18002a816  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002a81b  mov     ebx, dword ptr cs:qword_18004B0C8+4
0x18002a821  lea     rcx, [rsp+28h+arg_0]; this
0x18002a826  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002a82b  jmp     short loc_18002A836
0x18002a82d  dec     ebx
0x18002a82f  mov     ecx, ebx; unsigned int
0x18002a831  call    ?CalaisRemoveReader@@YAKK@Z; CalaisRemoveReader(ulong)
0x18002a836  test    ebx, ebx
0x18002a838  jnz     short loc_18002A82D
0x18002a83a  mov     rdx, cs:qword_18004BA68; struct CCriticalSectionObject *
0x18002a841  lea     rcx, [rsp+28h+arg_0]; this
0x18002a846  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x18002a84b  nop
0x18002a84c  jmp     short loc_18002A868
0x18002a84e  mov     rcx, cs:qword_18004BA68
0x18002a855  mov     rax, [rcx]
0x18002a858  lea     rdx, ?l_cvReaderAsyncActionFinished@@3U_RTL_CONDITION_VARIABLE@@A; _RTL_CONDITION_VARIABLE l_cvReaderAsyncActionFinished
0x18002a85f  mov     rax, [rax+18h]
0x18002a863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a868  cmp     cs:?l_dwReaderActionsInProgress@@3KA, 0; ulong l_dwReaderActionsInProgress
0x18002a86f  ja      short loc_18002A84E
0x18002a871  lea     rcx, [rsp+28h+arg_0]; this
0x18002a876  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x18002a87b  mov     rcx, cs:ptpcg; ptpcg
0x18002a882  test    rcx, rcx
0x18002a885  jz      short loc_18002A8AA
0x18002a887  xor     r8d, r8d; pvCleanupContext
0x18002a88a  xor     edx, edx; fCancelPendingCallbacks
0x18002a88c  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18002a892  mov     rcx, cs:ptpcg; ptpcg
0x18002a899  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18002a89f  mov     cs:ptpcg, 0
0x18002a8aa  mov     cs:dword_18004BF6C, 0
0x18002a8b4  mov     rcx, cs:?g_hCalaisShutdown@@3PEAXEA; hObject
0x18002a8bb  call    cs:__imp_CloseHandle
0x18002a8c1  test    eax, eax
0x18002a8c3  jnz     short loc_18002A8CB
0x18002a8c5  call    cs:__imp_GetLastError
0x18002a8cb  mov     cs:?g_hCalaisShutdown@@3PEAXEA, 0; void * g_hCalaisShutdown
0x18002a8d6  call    ?CleanUp@CPowerSupport@@SAXXZ; CPowerSupport::CleanUp(void)
0x18002a8db  cmp     cs:dword_18004BF0C, 0
0x18002a8e2  jz      short loc_18002A91B
0x18002a8e4  lea     rcx, stru_18004BAD0; lpCriticalSection
0x18002a8eb  call    cs:__imp_EnterCriticalSection
0x18002a8f1  mov     rcx, cs:hObject; hObject
0x18002a8f8  test    rcx, rcx
0x18002a8fb  jz      short loc_18002A90E
0x18002a8fd  call    cs:__imp_CloseHandle
0x18002a903  mov     cs:hObject, 0
0x18002a90e  lea     rcx, stru_18004BAD0; lpCriticalSection
0x18002a915  call    cs:__imp_LeaveCriticalSection
0x18002a91b  mov     rcx, cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA; this
0x18002a922  test    rcx, rcx
0x18002a925  jz      short loc_18002A937
0x18002a927  call    ??_GCMultiEvent@@QEAAPEAXI@Z; CMultiEvent::`scalar deleting destructor'(uint)
0x18002a92c  mov     cs:?g_phReaderChangeEvent@@3PEAVCMultiEvent@@EA, 0; CMultiEvent * g_phReaderChangeEvent
0x18002a937  xor     ebx, ebx
0x18002a939  lea     rsi, ?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; CCriticalSectionObject * near * g_pcsControlLocks
0x18002a940  mov     rcx, [rsi+rbx*8]; this
0x18002a944  test    rcx, rcx
0x18002a947  jz      short loc_18002A94E
0x18002a949  call    ??_GCCriticalSectionObject@@QEAAPEAXI@Z; CCriticalSectionObject::`scalar deleting destructor'(uint)
0x18002a94e  mov     qword ptr [rsi+rbx*8], 0
0x18002a956  inc     rbx
0x18002a959  cmp     rbx, 4
0x18002a95d  jnz     short loc_18002A939
0x18002a95f  mov     rbx, [rsp+28h+arg_8]
0x18002a964  add     rsp, 20h
0x18002a968  pop     rsi
0x18002a969  retn
```
