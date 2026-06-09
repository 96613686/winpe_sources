# EdpWriteAppLearningLog

- ea: `0x1800493e0`
- end: `0x180049542`
- name: `EdpWriteAppLearningLog`
- size: `354`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800492dc`

## callees

- `0x180004f86`
- `0x1800493e0`
- `0x1800dc698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049422`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004949a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049422`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004949a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049438`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800494da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004952b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049438`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800494da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004952b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049503`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800494f5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800494f5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049512`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049512`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004951b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004951b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049468`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049468`

## pseudocode

```c
__int64 __fastcall EdpWriteAppLearningLog(void *Src, char a2, int a3)
{
  int v5; // ebx
  DWORD LastError; // ebx
  size_t v7; // rsi
  struct _LIST_ENTRY *v8; // rax
  struct _LIST_ENTRY *v9; // rdi
  struct _LIST_ENTRY *Flink; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v12; // rdi
  size_t Size; // [rsp+60h] [rbp+8h] BYREF

  Size = 0;
  v5 = (a2 != 0) + 5;
  if ( !g_WorkQueueInitialized )
    return 50;
  AcquireSRWLockExclusive(&g_AuditAppWorkLock);
  if ( g_AuditAppWorkItem >= 0x14 )
  {
    ReleaseSRWLockExclusive(&g_AuditAppWorkLock);
    return 0;
  }
  ReleaseSRWLockExclusive(&g_AuditAppWorkLock);
  if ( (int)EdpGetInfoSize(Src, &Size) < 0 )
    return 87;
  v7 = Size;
  if ( Size >= 0xFFFFFFFFFFFFFFE0uLL )
    return 87;
  v8 = (struct _LIST_ENTRY *)CoTaskMemAlloc(Size + 32);
  v9 = v8;
  if ( !v8 )
    return 8;
  LODWORD(v8->Blink) = v5;
  v8->Flink = v8 + 2;
  HIDWORD(v8->Blink) = a3;
  memcpy_0(&v8[2], Src, v7);
  AcquireSRWLockExclusive(&g_AuditAppWorkLock);
  Flink = g_AuditAppWork.Flink;
  if ( g_AuditAppWork.Flink->Blink != &g_AuditAppWork )
    __fastfail(3u);
  ++g_AuditAppWorkItem;
  v9[1].Flink = g_AuditAppWork.Flink;
  v9[1].Blink = &g_AuditAppWork;
  Flink->Blink = v9 + 1;
  g_AuditAppWork.Flink = v9 + 1;
  ReleaseSRWLockExclusive(&g_AuditAppWorkLock);
  if ( Flink != &g_AuditAppWork )
    return 0;
  ThreadpoolWork = CreateThreadpoolWork(EdpAppLearningCallBack, 0, &g_callBackEnviron);
  v12 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    LastError = 0;
    SubmitThreadpoolWork(ThreadpoolWork);
    CloseThreadpoolWork(v12);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError == 1223 )
    return 0;
  return LastError;
}

```

## disassembly

```asm
0x1800493e0  push    rbx
0x1800493e2  push    rbp
0x1800493e3  push    rsi
0x1800493e4  push    rdi
0x1800493e5  push    r14
0x1800493e7  push    r15
0x1800493e9  sub     rsp, 28h
0x1800493ed  neg     dl
0x1800493ef  mov     [rsp+58h+Size], 0
0x1800493f8  mov     r14d, r8d
0x1800493fb  mov     rbp, rcx
0x1800493fe  sbb     ebx, ebx
0x180049400  neg     ebx
0x180049402  add     ebx, 5
0x180049405  cmp     cs:?g_WorkQueueInitialized@@3EA, 0; uchar g_WorkQueueInitialized
0x18004940c  jnz     short loc_180049418
0x18004940e  mov     ebx, 32h ; '2'
0x180049413  jmp     loc_180049533
0x180049418  lea     r15, ?g_AuditAppWorkLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_AuditAppWorkLock
0x18004941f  mov     rcx, r15; SRWLock
0x180049422  call    cs:__imp_AcquireSRWLockExclusive
0x180049428  cmp     cs:?g_AuditAppWorkItem@@3KA, 14h; ulong g_AuditAppWorkItem
0x18004942f  mov     rcx, r15; SRWLock
0x180049432  jnb     loc_18004952B
0x180049438  call    cs:__imp_ReleaseSRWLockExclusive
0x18004943e  lea     rdx, [rsp+58h+Size]
0x180049443  mov     rcx, rbp
0x180049446  call    EdpGetInfoSize
0x18004944b  test    eax, eax
0x18004944d  jns     short loc_180049459
0x18004944f  mov     ebx, 57h ; 'W'
0x180049454  jmp     loc_180049533
0x180049459  mov     rsi, [rsp+58h+Size]
0x18004945e  lea     rcx, [rsi+20h]; cb
0x180049462  cmp     rcx, 20h ; ' '
0x180049466  jb      short loc_18004944F
0x180049468  call    cs:__imp_CoTaskMemAlloc
0x18004946e  mov     rdi, rax
0x180049471  test    rax, rax
0x180049474  jnz     short loc_18004947E
0x180049476  lea     ebx, [rax+8]
0x180049479  jmp     loc_180049533
0x18004947e  lea     rcx, [rax+20h]; void *
0x180049482  mov     [rax+8], ebx
0x180049485  mov     r8, rsi; Size
0x180049488  mov     [rax], rcx
0x18004948b  mov     rdx, rbp; Src
0x18004948e  mov     [rax+0Ch], r14d
0x180049492  call    memcpy_0
0x180049497  mov     rcx, r15; SRWLock
0x18004949a  call    cs:__imp_AcquireSRWLockExclusive
0x1800494a0  mov     rbx, cs:?g_AuditAppWork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_AuditAppWork
0x1800494a7  lea     rsi, ?g_AuditAppWork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_AuditAppWork
0x1800494ae  cmp     [rbx+8], rsi
0x1800494b2  jz      short loc_1800494BB
0x1800494b4  mov     ecx, 3
0x1800494b9  int     29h; Win8: RtlFailFast(ecx)
0x1800494bb  inc     cs:?g_AuditAppWorkItem@@3KA; ulong g_AuditAppWorkItem
0x1800494c1  lea     rax, [rdi+10h]
0x1800494c5  mov     [rax], rbx
0x1800494c8  mov     rcx, r15; SRWLock
0x1800494cb  mov     [rax+8], rsi
0x1800494cf  mov     [rbx+8], rax
0x1800494d3  mov     cs:?g_AuditAppWork@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_AuditAppWork
0x1800494da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800494e0  cmp     rbx, rsi
0x1800494e3  jnz     short loc_180049531
0x1800494e5  lea     r8, ?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x1800494ec  xor     edx, edx; pv
0x1800494ee  lea     rcx, ?EdpAppLearningCallBack@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800494f5  call    cs:__imp_CreateThreadpoolWork
0x1800494fb  mov     rdi, rax
0x1800494fe  test    rax, rax
0x180049501  jnz     short loc_18004950D
0x180049503  call    cs:__imp_GetLastError
0x180049509  mov     ebx, eax
0x18004950b  jmp     short loc_180049521
0x18004950d  mov     rcx, rdi; pwk
0x180049510  xor     ebx, ebx
0x180049512  call    cs:__imp_SubmitThreadpoolWork
0x180049518  mov     rcx, rdi; pwk
0x18004951b  call    cs:__imp_CloseThreadpoolWork
0x180049521  cmp     ebx, 4C7h
0x180049527  jz      short loc_180049531
0x180049529  jmp     short loc_180049533
0x18004952b  call    cs:__imp_ReleaseSRWLockExclusive
0x180049531  xor     ebx, ebx
0x180049533  mov     eax, ebx
0x180049535  add     rsp, 28h
0x180049539  pop     r15
0x18004953b  pop     r14
0x18004953d  pop     rdi
0x18004953e  pop     rsi
0x18004953f  pop     rbp
0x180049540  pop     rbx
0x180049541  retn
```
