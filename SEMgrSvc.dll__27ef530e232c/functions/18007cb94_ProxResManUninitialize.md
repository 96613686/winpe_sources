# ProxResManUninitialize

- ea: `0x18007cb94`
- end: `0x18007ce4c`
- name: `ProxResManUninitialize`
- size: `696`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180035110`

## callees

- `0x180004460`
- `0x1800049c4`
- `0x18000584c`
- `0x18007bd48`
- `0x18007cb94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cde9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ce3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cde9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ce3b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cd23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cbec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cd23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ccdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cc9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ccdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce10`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ccbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007cd0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ce23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ccbf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007cd0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007ce23`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007ccae`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18007ccae`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007ccec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18007ccec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18007cd03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18007cd03`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007ccb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18007ccb7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18007ccfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18007ccfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ce1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007ce1b`
- `RMCLIENT!RmReleaseResources` at `0x18007cdcb`
- `RMCLIENT!RmReleaseResources` at `0x18007cdcb`

## pseudocode

```c
__int64 __fastcall ProxResManUninitialize(unsigned __int16 a1)
{
  __int64 trivial_2; // rax
  _WORD *v3; // r9
  _QWORD *v4; // rcx
  _WORD *v5; // rdx
  _WORD *v6; // r8
  __int64 v7; // rcx
  _QWORD *v8; // rax
  _QWORD *v9; // rbx
  struct _TP_WORK *v10; // rdi
  DWORD LastError; // ebx
  struct _TP_WAIT *v12; // rdi
  DWORD v13; // ebx
  __int64 v14; // rbx
  __int64 v15; // rax
  _QWORD *v16; // rcx
  _QWORD *v17; // r8
  _QWORD *v18; // rdx
  _QWORD *v19; // r9
  _QWORD *v20; // rcx
  _QWORD *v21; // rax
  _QWORD *v22; // rdi
  HANDLE v23; // rdi
  DWORD v24; // ebx
  void *Block; // [rsp+28h] [rbp-20h] BYREF
  void **p_Block; // [rsp+30h] [rbp-18h]
  char v28; // [rsp+78h] [rbp+30h] BYREF

  EnterCriticalSection(&g_resManInitializationLock);
  trivial_2 = _std_find_trivial_2(g_resManInitializationTokens, qword_180133298, a1);
  memmove_0((void *)trivial_2, (const void *)(trivial_2 + 2), qword_180133298 - (trivial_2 + 2));
  qword_180133298 -= 2;
  EnterCriticalSection(&g_resManPendingStartsLock);
  v3 = g_resManPendingStarts;
  v4 = 0;
  p_Block = &Block;
  Block = 0;
  v5 = *(_WORD **)g_resManPendingStarts;
  if ( *(void **)g_resManPendingStarts != g_resManPendingStarts )
  {
    do
    {
      v6 = *(_WORD **)v5;
      if ( v5[20] == a1 )
      {
        --qword_180132F50;
        v7 = *(_QWORD *)v5;
        *(_QWORD *)v5 = 0;
        v8 = (_QWORD *)*((_QWORD *)v5 + 1);
        *v8 = v7;
        *(_QWORD *)(v7 + 8) = v8;
        *p_Block = v5;
        p_Block = (void **)v5;
      }
      v5 = v6;
    }
    while ( v6 != v3 );
    v4 = Block;
  }
  if ( v4 )
  {
    do
    {
      v9 = (_QWORD *)*v4;
      operator delete(v4);
      v4 = v9;
    }
    while ( v9 );
  }
  LeaveCriticalSection(&g_resManPendingStartsLock);
  if ( g_resManInitializationTokens == (void *)qword_180133298 )
  {
    v10 = g_threadpoolStartMonitor;
    if ( g_threadpoolStartMonitor )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v10, 1);
      CloseThreadpoolWork(v10);
      SetLastError(LastError);
    }
    v12 = g_threadpoolResourceManagerNotification;
    g_threadpoolStartMonitor = 0;
    if ( g_threadpoolResourceManagerNotification )
    {
      v13 = GetLastError();
      SetThreadpoolWait(v12, 0, 0);
      WaitForThreadpoolWaitCallbacks(v12, 1);
      CloseThreadpoolWait(v12);
      SetLastError(v13);
    }
    g_threadpoolResourceManagerNotification = 0;
  }
  EnterCriticalSection(&g_resManMonitorsLock);
  while ( 1 )
  {
    v14 = *(_QWORD *)g_resManMonitors;
    if ( *(void **)g_resManMonitors == g_resManMonitors )
      break;
    v15 = v14 + 56;
    v16 = 0;
    v17 = *(_QWORD **)(v14 + 56);
    Block = 0;
    p_Block = &Block;
    v18 = (_QWORD *)*v17;
    if ( (_QWORD *)*v17 != v17 )
    {
      do
      {
        v19 = (_QWORD *)*v18;
        if ( *((_WORD *)v18 + 16) == a1 )
        {
          --*(_QWORD *)(v15 + 8);
          v20 = (_QWORD *)*v18;
          *v18 = 0;
          v21 = (_QWORD *)v18[1];
          *v21 = v20;
          v20[1] = v21;
          *p_Block = v18;
          v15 = v14 + 56;
          p_Block = (void **)v18;
        }
        v18 = v19;
      }
      while ( v19 != v17 );
      v16 = Block;
    }
    if ( v16 )
    {
      do
      {
        v22 = (_QWORD *)*v16;
        operator delete(v16);
        v16 = v22;
      }
      while ( v22 );
    }
    if ( (*(_BYTE *)(v14 + 40) || *(_BYTE *)(v14 + 41)) && !*(_QWORD *)(v14 + 64) )
      RmReleaseResources(*(_QWORD *)(v14 + 48));
    std::_Tree<std::_Tmap_traits<unsigned long,_PROXRESMAN_MONITOR_ENTRY,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,_PROXRESMAN_MONITOR_ENTRY>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,_PROXRESMAN_MONITOR_ENTRY>>>>,0>(
      v16,
      &v28,
      v14);
  }
  LeaveCriticalSection(&g_resManMonitorsLock);
  if ( g_resManInitializationTokens == (void *)qword_180133298 )
  {
    v23 = g_hResourceManagerNotification;
    if ( (char *)g_hResourceManagerNotification - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v24 = GetLastError();
      CloseHandle(v23);
      SetLastError(v24);
    }
    g_hResourceManagerNotification = 0;
  }
  LeaveCriticalSection(&g_resManInitializationLock);
  return 0;
}

```

## disassembly

```asm
0x18007cb94  push    rbp
0x18007cb96  push    rbx
0x18007cb97  push    rsi
0x18007cb98  push    rdi
0x18007cb99  mov     rbp, rsp
0x18007cb9c  sub     rsp, 48h
0x18007cba0  movzx   esi, cx
0x18007cba3  lea     rcx, ?g_resManInitializationLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18007cbaa  call    cs:__imp_EnterCriticalSection
0x18007cbb0  mov     rdx, cs:qword_180133298
0x18007cbb7  movzx   r8d, si
0x18007cbbb  mov     rcx, cs:?g_resManInitializationTokens@@3V?$vector@GV?$allocator@G@std@@@std@@A; std::vector<ushort> g_resManInitializationTokens
0x18007cbc2  call    __std_find_trivial_2
0x18007cbc7  mov     r8, cs:qword_180133298
0x18007cbce  mov     rcx, rax; void *
0x18007cbd1  lea     rdx, [rax+2]; Src
0x18007cbd5  sub     r8, rdx; Size
0x18007cbd8  call    memmove_0
0x18007cbdd  sub     cs:qword_180133298, 2
0x18007cbe5  lea     rcx, ?g_resManPendingStartsLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18007cbec  call    cs:__imp_EnterCriticalSection
0x18007cbf2  mov     r9, cs:?g_resManPendingStarts@@3V?$list@U_PROXRESMAN_PENDING_START@@V?$allocator@U_PROXRESMAN_PENDING_START@@@std@@@std@@A; std::list<_PROXRESMAN_PENDING_START> g_resManPendingStarts
0x18007cbf9  lea     rdx, [rbp+Block]
0x18007cbfd  xor     ecx, ecx
0x18007cbff  mov     [rbp+var_18], rdx
0x18007cc03  lea     rax, ?g_resManPendingStarts@@3V?$list@U_PROXRESMAN_PENDING_START@@V?$allocator@U_PROXRESMAN_PENDING_START@@@std@@@std@@A; std::list<_PROXRESMAN_PENDING_START> g_resManPendingStarts
0x18007cc0a  mov     [rbp+Block], rcx
0x18007cc0e  mov     [rbp+var_28], rax
0x18007cc12  mov     rdx, [r9]
0x18007cc15  cmp     rdx, r9
0x18007cc18  jz      short loc_18007CC57
0x18007cc1a  mov     r8, [rdx]
0x18007cc1d  cmp     [rdx+28h], si
0x18007cc21  jnz     short loc_18007CC4B
0x18007cc23  dec     qword ptr [rax+8]
0x18007cc27  mov     rcx, [rdx]
0x18007cc2a  mov     qword ptr [rdx], 0
0x18007cc31  mov     rax, [rdx+8]
0x18007cc35  mov     [rax], rcx
0x18007cc38  mov     [rcx+8], rax
0x18007cc3c  mov     rax, [rbp+var_18]
0x18007cc40  mov     [rax], rdx
0x18007cc43  mov     rax, [rbp+var_28]
0x18007cc47  mov     [rbp+var_18], rdx
0x18007cc4b  mov     rdx, r8
0x18007cc4e  cmp     r8, r9
0x18007cc51  jnz     short loc_18007CC1A
0x18007cc53  mov     rcx, [rbp+Block]; Block
0x18007cc57  test    rcx, rcx
0x18007cc5a  jz      short loc_18007CC71
0x18007cc5c  mov     rbx, [rcx]
0x18007cc5f  mov     edx, 30h ; '0'
0x18007cc64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007cc69  mov     rcx, rbx
0x18007cc6c  test    rbx, rbx
0x18007cc6f  jnz     short loc_18007CC5C
0x18007cc71  lea     rcx, ?g_resManPendingStartsLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18007cc78  call    cs:__imp_LeaveCriticalSection
0x18007cc7e  mov     rax, cs:qword_180133298
0x18007cc85  cmp     cs:?g_resManInitializationTokens@@3V?$vector@GV?$allocator@G@std@@@std@@A, rax; std::vector<ushort> g_resManInitializationTokens
0x18007cc8c  jnz     loc_18007CD1C
0x18007cc92  mov     rdi, cs:?g_threadpoolStartMonitor@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> g_threadpoolStartMonitor
0x18007cc99  test    rdi, rdi
0x18007cc9c  jz      short loc_18007CCC5
0x18007cc9e  call    cs:__imp_GetLastError
0x18007cca4  mov     edx, 1; fCancelPendingCallbacks
0x18007cca9  mov     rcx, rdi; pwk
0x18007ccac  mov     ebx, eax
0x18007ccae  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18007ccb4  mov     rcx, rdi; pwk
0x18007ccb7  call    cs:__imp_CloseThreadpoolWork
0x18007ccbd  mov     ecx, ebx; dwErrCode
0x18007ccbf  call    cs:__imp_SetLastError
0x18007ccc5  mov     rdi, cs:?g_threadpoolResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>> g_threadpoolResourceManagerNotification
0x18007cccc  mov     cs:?g_threadpoolStartMonitor@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>> g_threadpoolStartMonitor
0x18007ccd7  test    rdi, rdi
0x18007ccda  jz      short loc_18007CD11
0x18007ccdc  call    cs:__imp_GetLastError
0x18007cce2  xor     r8d, r8d; pftTimeout
0x18007cce5  xor     edx, edx; h
0x18007cce7  mov     rcx, rdi; pwa
0x18007ccea  mov     ebx, eax
0x18007ccec  call    cs:__imp_SetThreadpoolWait
0x18007ccf2  mov     edx, 1; fCancelPendingCallbacks
0x18007ccf7  mov     rcx, rdi; pwa
0x18007ccfa  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18007cd00  mov     rcx, rdi; pwa
0x18007cd03  call    cs:__imp_CloseThreadpoolWait
0x18007cd09  mov     ecx, ebx; dwErrCode
0x18007cd0b  call    cs:__imp_SetLastError
0x18007cd11  mov     cs:?g_threadpoolResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>> g_threadpoolResourceManagerNotification
0x18007cd1c  lea     rcx, ?g_resManMonitorsLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18007cd23  call    cs:__imp_EnterCriticalSection
0x18007cd29  mov     rax, cs:?g_resManMonitors@@3V?$multimap@KU_PROXRESMAN_MONITOR_ENTRY@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_PROXRESMAN_MONITOR_ENTRY@@@std@@@3@@std@@A; std::multimap<ulong,_PROXRESMAN_MONITOR_ENTRY> g_resManMonitors
0x18007cd30  mov     rbx, [rax]
0x18007cd33  cmp     rbx, rax
0x18007cd36  jz      loc_18007CDE2
0x18007cd3c  lea     rax, [rbx+38h]
0x18007cd40  xor     ecx, ecx
0x18007cd42  mov     r8, [rax]
0x18007cd45  lea     rdx, [rbp+Block]
0x18007cd49  mov     [rbp+var_28], rax
0x18007cd4d  mov     [rbp+Block], rcx
0x18007cd51  mov     [rbp+var_18], rdx
0x18007cd55  mov     rdx, [r8]
0x18007cd58  cmp     rdx, r8
0x18007cd5b  jz      short loc_18007CD9A
0x18007cd5d  mov     r9, [rdx]
0x18007cd60  cmp     [rdx+20h], si
0x18007cd64  jnz     short loc_18007CD8E
0x18007cd66  dec     qword ptr [rax+8]
0x18007cd6a  mov     rcx, [rdx]
0x18007cd6d  mov     qword ptr [rdx], 0
0x18007cd74  mov     rax, [rdx+8]
0x18007cd78  mov     [rax], rcx
0x18007cd7b  mov     [rcx+8], rax
0x18007cd7f  mov     rax, [rbp+var_18]
0x18007cd83  mov     [rax], rdx
0x18007cd86  mov     rax, [rbp+var_28]
0x18007cd8a  mov     [rbp+var_18], rdx
0x18007cd8e  mov     rdx, r9
0x18007cd91  cmp     r9, r8
0x18007cd94  jnz     short loc_18007CD5D
0x18007cd96  mov     rcx, [rbp+Block]; Block
0x18007cd9a  test    rcx, rcx
0x18007cd9d  jz      short loc_18007CDB4
0x18007cd9f  mov     rdi, [rcx]
0x18007cda2  mov     edx, 28h ; '('
0x18007cda7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007cdac  mov     rcx, rdi
0x18007cdaf  test    rdi, rdi
0x18007cdb2  jnz     short loc_18007CD9F
0x18007cdb4  cmp     byte ptr [rbx+28h], 0
0x18007cdb8  jnz     short loc_18007CDC0
0x18007cdba  cmp     byte ptr [rbx+29h], 0
0x18007cdbe  jz      short loc_18007CDD1
0x18007cdc0  cmp     qword ptr [rbx+40h], 0
0x18007cdc5  jnz     short loc_18007CDD1
0x18007cdc7  mov     rcx, [rbx+30h]
0x18007cdcb  call    cs:__imp_RmReleaseResources
0x18007cdd1  mov     r8, rbx
0x18007cdd4  lea     rdx, [rbp+arg_8]
0x18007cdd8  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKU_PROXRESMAN_MONITOR_ENTRY@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@KU_PROXRESMAN_MONITOR_ENTRY@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKU_PROXRESMAN_MONITOR_ENTRY@@@std@@@3@$00@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKU_PROXRESMAN_MONITOR_ENTRY@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<ulong,_PROXRESMAN_MONITOR_ENTRY,std::less<ulong>,std::allocator<std::pair<ulong const,_PROXRESMAN_MONITOR_ENTRY>>,1>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,_PROXRESMAN_MONITOR_ENTRY>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,_PROXRESMAN_MONITOR_ENTRY>>>>)
0x18007cddd  jmp     loc_18007CD29
0x18007cde2  lea     rcx, ?g_resManMonitorsLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18007cde9  call    cs:__imp_LeaveCriticalSection
0x18007cdef  mov     rax, cs:qword_180133298
0x18007cdf6  cmp     cs:?g_resManInitializationTokens@@3V?$vector@GV?$allocator@G@std@@@std@@A, rax; std::vector<ushort> g_resManInitializationTokens
0x18007cdfd  jnz     short loc_18007CE34
0x18007cdff  mov     rdi, cs:?g_hResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hResourceManagerNotification
0x18007ce06  lea     rax, [rdi-1]
0x18007ce0a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18007ce0e  ja      short loc_18007CE29
0x18007ce10  call    cs:__imp_GetLastError
0x18007ce16  mov     rcx, rdi; hObject
0x18007ce19  mov     ebx, eax
0x18007ce1b  call    cs:__imp_CloseHandle
0x18007ce21  mov     ecx, ebx; dwErrCode
0x18007ce23  call    cs:__imp_SetLastError
0x18007ce29  mov     cs:?g_hResourceManagerNotification@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> g_hResourceManagerNotification
0x18007ce34  lea     rcx, ?g_resManInitializationLock@@3Vcritical_section@wil@@A; lpCriticalSection
0x18007ce3b  call    cs:__imp_LeaveCriticalSection
0x18007ce41  xor     eax, eax
0x18007ce43  add     rsp, 48h
0x18007ce47  pop     rdi
0x18007ce48  pop     rsi
0x18007ce49  pop     rbx
0x18007ce4a  pop     rbp
0x18007ce4b  retn
```
