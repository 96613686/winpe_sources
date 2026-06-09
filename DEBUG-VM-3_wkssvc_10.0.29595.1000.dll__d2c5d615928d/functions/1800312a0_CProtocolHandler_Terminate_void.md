# CProtocolHandler::Terminate(void)

- ea: `0x1800312a0`
- end: `0x180031534`
- name: `?Terminate@CProtocolHandler@@QEAAKXZ`
- size: `660`
- prototype: `unsigned int __fastcall(CProtocolHandler *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ce80`

## callees

- `0x18001c82c`
- `0x180022b7c`
- `0x180030eac`
- `0x1800312a0`
- `0x1800315b8`
- `0x180032324`

## import_xrefs

- `ntdll!NtClose` at `0x180031511`
- `ntdll!NtClose` at `0x180031511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003144e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800313a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003144e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031382`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180031382`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031392`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031444`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031392`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180031444`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800312c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800312c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003148a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003149d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003148a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003149d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800314d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800314d2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800314dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800314dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800314c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800314c4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800314f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x1800314f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180031502`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180031502`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800313f6`
- `api-ms-win-core-io-l1-1-0!PostQueuedCompletionStatus` at `0x1800313f6`

## pseudocode

```c
__int64 __fastcall CProtocolHandler::Terminate(CProtocolHandler *this)
{
  CProtocolHandler *v1; // rbx
  DWORD v2; // ebp
  _QWORD *v3; // r14
  CClusterConnection **v4; // rax
  CClusterConnection *v5; // rdi
  _QWORD *v6; // rdi
  CClusterConnection **v7; // rax
  CClusterConnection *v8; // rsi
  struct _RTL_CRITICAL_SECTION *v9; // rcx
  DWORD LastError; // eax
  void *v11; // rcx
  DWORD v12; // eax
  void *v13; // rcx
  DWORD v14; // eax
  void *v15; // rcx
  PTP_CLEANUP_GROUP *v16; // rdi
  __int64 i; // rsi
  struct _TP_TIMER *v18; // rcx
  void *v19; // rcx
  CProtocolHandler *v21; // [rsp+40h] [rbp+8h] BYREF

  v21 = this;
  v1 = WitnessProtocolHandler;
  v2 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)WitnessProtocolHandler + 10));
  v3 = (_QWORD *)((char *)v1 + 24);
  v4 = (CClusterConnection **)**((_QWORD **)v1 + 3);
  v21 = (CProtocolHandler *)v4;
  while ( v4 != (CClusterConnection **)*v3 )
  {
    v5 = v4[8];
    if ( !CClusterConnection::ReleaseRegisterReference(v5) )
      CClusterConnection::Terminate(v5);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(&v21);
    v4 = (CClusterConnection **)v21;
  }
  v6 = (_QWORD *)((char *)v1 + 40);
  v7 = (CClusterConnection **)**((_QWORD **)v1 + 5);
  v21 = (CProtocolHandler *)v7;
  while ( v7 != (CClusterConnection **)*v6 )
  {
    v8 = v7[8];
    if ( !CClusterConnection::ReleaseRegisterReference(v8) )
      CClusterConnection::Terminate(v8);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(&v21);
    v7 = (CClusterConnection **)v21;
  }
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    (char *)v1 + 8,
    **((_QWORD **)v1 + 1),
    *((_QWORD *)v1 + 1));
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    (char *)v1 + 24,
    *(_QWORD *)*v3,
    *v3);
  std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(
    (char *)v1 + 40,
    *(_QWORD *)*v6,
    *v6);
  v9 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)v1 + 10);
  *((_DWORD *)v1 + 32) = 0;
  LeaveCriticalSection(v9);
  if ( WaitForSingleObject(*((HANDLE *)v1 + 17), 0xFFFFFFFF) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_witness_GLOBAL_Control + 2),
        25,
        &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids,
        LastError);
    }
  }
  v11 = (void *)*((_QWORD *)v1 + 8);
  if ( v11 != (void *)-1LL && !PostQueuedCompletionStatus(v11, 0, 4u, 0) )
  {
    v12 = GetLastError();
    v2 = v12;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 26, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v12);
    }
  }
  v13 = (void *)*((_QWORD *)v1 + 9);
  if ( v13 != (void *)-1LL )
  {
    if ( WaitForSingleObject(v13, 0x2710u) )
    {
      v14 = GetLastError();
      v2 = v14;
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 27, &WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids, v14);
      }
    }
    CloseHandle(*((HANDLE *)v1 + 9));
    *((_QWORD *)v1 + 9) = -1;
  }
  v15 = (void *)*((_QWORD *)v1 + 8);
  if ( v15 != (void *)-1LL )
  {
    CloseHandle(v15);
    *((_QWORD *)v1 + 8) = -1;
  }
  v16 = (PTP_CLEANUP_GROUP *)*((_QWORD *)v1 + 7);
  if ( v16 )
  {
    for ( i = 0; i != 3; ++i )
    {
      v18 = v16[i + 10];
      if ( v18 )
      {
        SetThreadpoolTimer(v18, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v16[i + 10], 1);
        CloseThreadpoolTimer(v16[i + 10]);
      }
    }
    if ( *v16 )
    {
      CloseThreadpoolCleanupGroupMembers(*v16, 0, 0);
      CloseThreadpoolCleanupGroup(*v16);
    }
  }
  v19 = (void *)*((_QWORD *)v1 + 11);
  if ( v19 )
  {
    NtClose(v19);
    *((_QWORD *)v1 + 11) = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800312a0  mov     [rsp+arg_8], rbx
0x1800312a5  mov     [rsp+arg_10], rbp
0x1800312aa  mov     [rsp+arg_0], rcx
0x1800312af  push    rsi
0x1800312b0  push    rdi
0x1800312b1  push    r14
0x1800312b3  sub     rsp, 20h
0x1800312b7  mov     rbx, cs:?WitnessProtocolHandler@@3PEAVCProtocolHandler@@EA; CProtocolHandler * WitnessProtocolHandler
0x1800312be  xor     ebp, ebp
0x1800312c0  mov     rcx, [rbx+50h]; lpCriticalSection
0x1800312c4  call    cs:__imp_EnterCriticalSection
0x1800312ca  lea     r14, [rbx+18h]
0x1800312ce  mov     rax, [r14]
0x1800312d1  mov     rax, [rax]
0x1800312d4  mov     [rsp+38h+arg_0], rax
0x1800312d9  cmp     rax, [r14]
0x1800312dc  jz      short loc_180031307
0x1800312de  mov     rdi, [rax+40h]
0x1800312e2  mov     rcx, rdi; this
0x1800312e5  call    ?ReleaseRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::ReleaseRegisterReference(void)
0x1800312ea  test    eax, eax
0x1800312ec  jnz     short loc_1800312F6
0x1800312ee  mov     rcx, rdi; this
0x1800312f1  call    ?Terminate@CClusterConnection@@QEAAXXZ; CClusterConnection::Terminate(void)
0x1800312f6  lea     rcx, [rsp+38h+arg_0]
0x1800312fb  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(void)
0x180031300  mov     rax, [rsp+38h+arg_0]
0x180031305  jmp     short loc_1800312D9
0x180031307  lea     rdi, [rbx+28h]
0x18003130b  mov     rax, [rdi]
0x18003130e  mov     rax, [rax]
0x180031311  mov     [rsp+38h+arg_0], rax
0x180031316  cmp     rax, [rdi]
0x180031319  jz      short loc_180031344
0x18003131b  mov     rsi, [rax+40h]
0x18003131f  mov     rcx, rsi; this
0x180031322  call    ?ReleaseRegisterReference@CClusterConnection@@QEAAKXZ; CClusterConnection::ReleaseRegisterReference(void)
0x180031327  test    eax, eax
0x180031329  jnz     short loc_180031333
0x18003132b  mov     rcx, rsi; this
0x18003132e  call    ?Terminate@CClusterConnection@@QEAAXXZ; CClusterConnection::Terminate(void)
0x180031333  lea     rcx, [rsp+38h+arg_0]
0x180031338  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>::operator++(void)
0x18003133d  mov     rax, [rsp+38h+arg_0]
0x180031342  jmp     short loc_180031316
0x180031344  lea     rcx, [rbx+8]
0x180031348  mov     rdx, [rcx]
0x18003134b  mov     r8, rdx
0x18003134e  mov     rdx, [rdx]
0x180031351  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x180031356  mov     rdx, [r14]
0x180031359  mov     rcx, r14
0x18003135c  mov     r8, rdx
0x18003135f  mov     rdx, [rdx]
0x180031362  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x180031367  mov     rdx, [rdi]
0x18003136a  mov     rcx, rdi
0x18003136d  mov     r8, rdx
0x180031370  mov     rdx, [rdx]
0x180031373  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@UCase_Insensitive@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCClusterConnection@@@std@@@std@@@std@@U_Iterator_base0@2@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,CClusterConnection *,Case_Insensitive,std::allocator<std::pair<std::wstring const,CClusterConnection *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CClusterConnection *>>>,std::_Iterator_base0>)
0x180031378  mov     rcx, [rbx+50h]; lpCriticalSection
0x18003137c  mov     [rbx+80h], ebp
0x180031382  call    cs:__imp_LeaveCriticalSection
0x180031388  mov     rcx, [rbx+88h]; hHandle
0x18003138f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180031392  call    cs:__imp_WaitForSingleObject
0x180031398  mov     r14d, 1
0x18003139e  lea     rsi, WPP_witness_GLOBAL_Control
0x1800313a5  test    eax, eax
0x1800313a7  jz      short loc_1800313E0
0x1800313a9  call    cs:__imp_GetLastError
0x1800313af  mov     ebp, eax
0x1800313b1  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800313b8  cmp     rcx, rsi
0x1800313bb  jz      short loc_1800313E0
0x1800313bd  test    [rcx+1Ch], r14b
0x1800313c1  jz      short loc_1800313E0
0x1800313c3  cmp     [rcx+19h], r14b
0x1800313c7  jb      short loc_1800313E0
0x1800313c9  mov     rcx, [rcx+10h]
0x1800313cd  lea     edx, [r14+18h]
0x1800313d1  mov     r9d, eax
0x1800313d4  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x1800313db  call    WPP_SF_d
0x1800313e0  mov     rcx, [rbx+40h]; CompletionPort
0x1800313e4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800313e8  cmp     rcx, rdi
0x1800313eb  jz      short loc_180031436
0x1800313ed  xor     r9d, r9d; lpOverlapped
0x1800313f0  lea     r8d, [rdi+5]; dwCompletionKey
0x1800313f4  xor     edx, edx; dwNumberOfBytesTransferred
0x1800313f6  call    cs:__imp_PostQueuedCompletionStatus
0x1800313fc  test    eax, eax
0x1800313fe  jnz     short loc_180031436
0x180031400  call    cs:__imp_GetLastError
0x180031406  mov     ebp, eax
0x180031408  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18003140f  cmp     rcx, rsi
0x180031412  jz      short loc_180031436
0x180031414  test    [rcx+1Ch], r14b
0x180031418  jz      short loc_180031436
0x18003141a  cmp     [rcx+19h], r14b
0x18003141e  jb      short loc_180031436
0x180031420  mov     rcx, [rcx+10h]
0x180031424  lea     edx, [rdi+1Bh]
0x180031427  mov     r9d, eax
0x18003142a  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x180031431  call    WPP_SF_d
0x180031436  mov     rcx, [rbx+48h]; hHandle
0x18003143a  cmp     rcx, rdi
0x18003143d  jz      short loc_180031494
0x18003143f  mov     edx, 2710h; dwMilliseconds
0x180031444  call    cs:__imp_WaitForSingleObject
0x18003144a  test    eax, eax
0x18003144c  jz      short loc_180031486
0x18003144e  call    cs:__imp_GetLastError
0x180031454  mov     ebp, eax
0x180031456  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18003145d  cmp     rcx, rsi
0x180031460  jz      short loc_180031486
0x180031462  test    [rcx+1Ch], r14b
0x180031466  jz      short loc_180031486
0x180031468  cmp     [rcx+19h], r14b
0x18003146c  jb      short loc_180031486
0x18003146e  mov     rcx, [rcx+10h]
0x180031472  lea     r8, WPP_8c6a6f45ef833141536139e9b45518e8_Traceguids
0x180031479  mov     edx, 1Bh
0x18003147e  mov     r9d, eax
0x180031481  call    WPP_SF_d
0x180031486  mov     rcx, [rbx+48h]; hObject
0x18003148a  call    cs:__imp_CloseHandle
0x180031490  mov     [rbx+48h], rdi
0x180031494  mov     rcx, [rbx+40h]; hObject
0x180031498  cmp     rcx, rdi
0x18003149b  jz      short loc_1800314A7
0x18003149d  call    cs:__imp_CloseHandle
0x1800314a3  mov     [rbx+40h], rdi
0x1800314a7  mov     rdi, [rbx+38h]
0x1800314ab  test    rdi, rdi
0x1800314ae  jz      short loc_180031508
0x1800314b0  xor     esi, esi
0x1800314b2  mov     rcx, [rdi+rsi*8+50h]; pti
0x1800314b7  test    rcx, rcx
0x1800314ba  jz      short loc_1800314E3
0x1800314bc  xor     r9d, r9d; msWindowLength
0x1800314bf  xor     r8d, r8d; msPeriod
0x1800314c2  xor     edx, edx; pftDueTime
0x1800314c4  call    cs:__imp_SetThreadpoolTimer
0x1800314ca  mov     rcx, [rdi+rsi*8+50h]; pti
0x1800314cf  mov     edx, r14d; fCancelPendingCallbacks
0x1800314d2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800314d8  mov     rcx, [rdi+rsi*8+50h]; pti
0x1800314dd  call    cs:__imp_CloseThreadpoolTimer
0x1800314e3  add     rsi, r14
0x1800314e6  cmp     rsi, 3
0x1800314ea  jnz     short loc_1800314B2
0x1800314ec  mov     rcx, [rdi]; ptpcg
0x1800314ef  test    rcx, rcx
0x1800314f2  jz      short loc_180031508
0x1800314f4  xor     r8d, r8d; pvCleanupContext
0x1800314f7  xor     edx, edx; fCancelPendingCallbacks
0x1800314f9  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x1800314ff  mov     rcx, [rdi]; ptpcg
0x180031502  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180031508  mov     rcx, [rbx+58h]; Handle
0x18003150c  test    rcx, rcx
0x18003150f  jz      short loc_18003151F
0x180031511  call    cs:__imp_NtClose
0x180031517  mov     qword ptr [rbx+58h], 0
0x18003151f  mov     rbx, [rsp+38h+arg_8]
0x180031524  mov     eax, ebp
0x180031526  mov     rbp, [rsp+38h+arg_10]
0x18003152b  add     rsp, 20h
0x18003152f  pop     r14
0x180031531  pop     rdi
0x180031532  pop     rsi
0x180031533  retn
```
