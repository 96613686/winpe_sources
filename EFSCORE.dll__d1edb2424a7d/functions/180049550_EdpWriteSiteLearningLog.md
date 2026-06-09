# EdpWriteSiteLearningLog

- ea: `0x180049550`
- end: `0x1800496a5`
- name: `EdpWriteSiteLearningLog`
- size: `341`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004f86`
- `0x1800102f0`
- `0x180049550`
- `0x1800dc698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004958f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049601`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004958f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049601`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800495a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049641`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049692`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800495a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049641`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004966a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004966a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004965c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18004965c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049679`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180049679`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049682`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180049682`

## pseudocode

```c
__int64 __fastcall EdpWriteSiteLearningLog(void *Src)
{
  DWORD LastError; // ebx
  size_t v4; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rdi
  struct _LIST_ENTRY *Flink; // rbx
  struct _TP_WORK *ThreadpoolWork; // rax
  struct _TP_WORK *v9; // rdi
  size_t Size; // [rsp+50h] [rbp+8h] BYREF

  if ( !Src )
    return 13;
  Size = 0;
  if ( g_SiteWorkQueueInitialized )
  {
    AcquireSRWLockExclusive(&g_AuditSiteWorkLock);
    if ( g_AuditSiteWorkItem >= 0x1E )
    {
      ReleaseSRWLockExclusive(&g_AuditSiteWorkLock);
    }
    else
    {
      ReleaseSRWLockExclusive(&g_AuditSiteWorkLock);
      if ( (int)EdpGetInfoSize(Src, &Size) < 0 )
        return 87;
      v4 = Size;
      if ( Size >= 0xFFFFFFFFFFFFFFE8uLL )
        return 87;
      v5 = wil::details::heap_allocator::allocate((unsigned int)(Size + 24));
      v6 = v5;
      if ( !v5 )
        return 8;
      *v5 = v5 + 3;
      memcpy_0(v5 + 3, Src, v4);
      AcquireSRWLockExclusive(&g_AuditSiteWorkLock);
      Flink = g_AuditSiteWork.Flink;
      if ( g_AuditSiteWork.Flink->Blink != &g_AuditSiteWork )
        __fastfail(3u);
      ++g_AuditSiteWorkItem;
      v6[1] = g_AuditSiteWork.Flink;
      v6[2] = &g_AuditSiteWork;
      Flink->Blink = (struct _LIST_ENTRY *)(v6 + 1);
      g_AuditSiteWork.Flink = (struct _LIST_ENTRY *)(v6 + 1);
      ReleaseSRWLockExclusive(&g_AuditSiteWorkLock);
      if ( Flink == &g_AuditSiteWork )
      {
        ThreadpoolWork = CreateThreadpoolWork(EdppSiteLearningCallBack, 0, &g_callBackEnviron);
        v9 = ThreadpoolWork;
        if ( ThreadpoolWork )
        {
          LastError = 0;
          SubmitThreadpoolWork(ThreadpoolWork);
          CloseThreadpoolWork(v9);
        }
        else
        {
          LastError = GetLastError();
        }
        if ( LastError != 1223 )
          return LastError;
      }
    }
    return 0;
  }
  return 50;
}

```

## disassembly

```asm
0x180049550  push    rbx
0x180049552  push    rbp
0x180049553  push    rsi
0x180049554  push    rdi
0x180049555  sub     rsp, 28h
0x180049559  mov     rbx, rcx
0x18004955c  test    rcx, rcx
0x18004955f  jnz     short loc_180049569
0x180049561  lea     eax, [rcx+0Dh]
0x180049564  jmp     loc_18004969C
0x180049569  cmp     cs:?g_SiteWorkQueueInitialized@@3EA, 0; uchar g_SiteWorkQueueInitialized
0x180049570  mov     [rsp+48h+Size], 0
0x180049579  jnz     short loc_180049585
0x18004957b  mov     ebx, 32h ; '2'
0x180049580  jmp     loc_18004969A
0x180049585  lea     rbp, ?g_AuditSiteWorkLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK g_AuditSiteWorkLock
0x18004958c  mov     rcx, rbp; SRWLock
0x18004958f  call    cs:__imp_AcquireSRWLockExclusive
0x180049595  cmp     cs:?g_AuditSiteWorkItem@@3KA, 1Eh; ulong g_AuditSiteWorkItem
0x18004959c  mov     rcx, rbp; SRWLock
0x18004959f  jnb     loc_180049692
0x1800495a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800495ab  lea     rdx, [rsp+48h+Size]
0x1800495b0  mov     rcx, rbx
0x1800495b3  call    EdpGetInfoSize
0x1800495b8  test    eax, eax
0x1800495ba  jns     short loc_1800495C6
0x1800495bc  mov     ebx, 57h ; 'W'
0x1800495c1  jmp     loc_18004969A
0x1800495c6  mov     rsi, [rsp+48h+Size]
0x1800495cb  lea     rax, [rsi+18h]
0x1800495cf  cmp     rax, 18h
0x1800495d3  jb      short loc_1800495BC
0x1800495d5  mov     ecx, eax; unsigned __int64
0x1800495d7  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x1800495dc  mov     rdi, rax
0x1800495df  test    rax, rax
0x1800495e2  jnz     short loc_1800495EC
0x1800495e4  lea     ebx, [rax+8]
0x1800495e7  jmp     loc_18004969A
0x1800495ec  lea     rcx, [rax+18h]; void *
0x1800495f0  mov     r8, rsi; Size
0x1800495f3  mov     rdx, rbx; Src
0x1800495f6  mov     [rax], rcx
0x1800495f9  call    memcpy_0
0x1800495fe  mov     rcx, rbp; SRWLock
0x180049601  call    cs:__imp_AcquireSRWLockExclusive
0x180049607  mov     rbx, cs:?g_AuditSiteWork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_AuditSiteWork
0x18004960e  lea     rsi, ?g_AuditSiteWork@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_AuditSiteWork
0x180049615  cmp     [rbx+8], rsi
0x180049619  jz      short loc_180049622
0x18004961b  mov     ecx, 3
0x180049620  int     29h; Win8: RtlFailFast(ecx)
0x180049622  inc     cs:?g_AuditSiteWorkItem@@3KA; ulong g_AuditSiteWorkItem
0x180049628  lea     rax, [rdi+8]
0x18004962c  mov     [rax], rbx
0x18004962f  mov     rcx, rbp; SRWLock
0x180049632  mov     [rax+8], rsi
0x180049636  mov     [rbx+8], rax
0x18004963a  mov     cs:?g_AuditSiteWork@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY g_AuditSiteWork
0x180049641  call    cs:__imp_ReleaseSRWLockExclusive
0x180049647  cmp     rbx, rsi
0x18004964a  jnz     short loc_180049698
0x18004964c  lea     r8, ?g_callBackEnviron@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x180049653  xor     edx, edx; pv
0x180049655  lea     rcx, EdppSiteLearningCallBack; pfnwk
0x18004965c  call    cs:__imp_CreateThreadpoolWork
0x180049662  mov     rdi, rax
0x180049665  test    rax, rax
0x180049668  jnz     short loc_180049674
0x18004966a  call    cs:__imp_GetLastError
0x180049670  mov     ebx, eax
0x180049672  jmp     short loc_180049688
0x180049674  mov     rcx, rdi; pwk
0x180049677  xor     ebx, ebx
0x180049679  call    cs:__imp_SubmitThreadpoolWork
0x18004967f  mov     rcx, rdi; pwk
0x180049682  call    cs:__imp_CloseThreadpoolWork
0x180049688  cmp     ebx, 4C7h
0x18004968e  jz      short loc_180049698
0x180049690  jmp     short loc_18004969A
0x180049692  call    cs:__imp_ReleaseSRWLockExclusive
0x180049698  xor     ebx, ebx
0x18004969a  mov     eax, ebx
0x18004969c  add     rsp, 28h
0x1800496a0  pop     rdi
0x1800496a1  pop     rsi
0x1800496a2  pop     rbp
0x1800496a3  pop     rbx
0x1800496a4  retn
```
