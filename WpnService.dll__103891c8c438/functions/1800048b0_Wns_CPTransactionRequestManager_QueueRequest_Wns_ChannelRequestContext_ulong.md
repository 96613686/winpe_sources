# Wns::CPTransactionRequestManager::QueueRequest(Wns::ChannelRequestContext,ulong)

- ea: `0x1800048b0`
- end: `0x180004a43`
- name: `?QueueRequest@CPTransactionRequestManager@Wns@@AEAAJUChannelRequestContext@2@K@Z`
- size: `403`
- prototype: `__int64 __fastcall(__int64, __int64, DWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000453c`

## callees

- `0x180003bb8`
- `0x1800048b0`
- `0x180016280`
- `0x18001664c`
- `0x180023300`
- `0x180026adc`
- `0x18002f640`
- `0x18002fa88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800048d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049d5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800048d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800049d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004967`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a22`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004967`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004a22`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004994`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180004994`

## pseudocode

```c
__int64 __fastcall Wns::CPTransactionRequestManager::QueueRequest(__int64 a1, __int64 a2, DWORD a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  _QWORD *v7; // rax
  unsigned int v8; // ebx
  _QWORD *v9; // rdx
  void **v10; // rdi
  unsigned int TimerQueueTimer; // eax
  __int64 v12; // rdi
  _QWORD *v13; // rax
  __int64 v14; // rdi
  const char *Period; // [rsp+28h] [rbp-60h]
  char *v17; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v18[3]; // [rsp+48h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 240);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 240));
  v18[2] = v6;
  LODWORD(v17) = ++*(_DWORD *)a1;
  std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::emplace<long &,Wns::ChannelRequestContext &>(
    a1 + 8,
    v18,
    &v17,
    a2);
  v7 = operator new(0x20u);
  v18[0] = v7;
  *v7 = &Wns::CPTransactionRequestManager::TimerContext::`vftable';
  v7[1] = a1;
  v8 = (unsigned int)v17;
  *((_DWORD *)v7 + 4) = (_DWORD)v17;
  v7[3] = -1;
  v17 = (char *)v7;
  v9 = *(_QWORD **)(a1 + 88);
  if ( v9 == *(_QWORD **)(a1 + 96) )
  {
    std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>::_Emplace_reallocate<Wns::CPTransactionRequestManager::TimerContext *>(
      a1 + 80,
      v9,
      &v17);
  }
  else
  {
    *v9 = v7;
    *(_QWORD *)(a1 + 88) += 8LL;
  }
  v10 = *(void ***)(*(_QWORD *)(a1 + 88) - 8LL);
  if ( v6 )
    LeaveCriticalSection(v6);
  TimerQueueTimer = CreateTimerQueueTimer(v10 + 3, *(HANDLE *)(a1 + 72), Wns::TimeoutHandler, v10, a3, 0, 8u);
  LODWORD(Period) = v8;
  if ( !(unsigned int)wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
                        retaddr,
                        (void *)0x198,
                        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\cptransactionrequestmanager.cpp",
                        (const char *)TimerQueueTimer,
                        (int)"Failed to queue timer for transactionId: %d",
                        Period) )
  {
    v10[3] = (void *)-1LL;
    EnterCriticalSection(v6);
    v12 = *(_QWORD *)(a1 + 88);
    v13 = (_QWORD *)std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::unique_ptr_Wns::CPTransactionRequestManager::TimerContext_std::default_delete_Wns::CPTransactionRequestManager::TimerContext___________lambda_030f659afdb6fc1c77419263130569a6___(
                      v18,
                      *(_QWORD *)(a1 + 80),
                      v12,
                      v8);
    if ( *v13 != v12 )
    {
      v14 = std::_Move_unchecked<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *>(
              v12,
              *(_QWORD *)(a1 + 88),
              *v13);
      std::_Destroy_range<std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(
        v14,
        *(_QWORD *)(a1 + 88));
      *(_QWORD *)(a1 + 88) = v14;
    }
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  return v8;
}

```

## disassembly

```asm
0x1800048b0  mov     [rsp+arg_8], rbx
0x1800048b5  mov     [rsp+arg_18], rbp
0x1800048ba  push    rsi
0x1800048bb  push    rdi
0x1800048bc  push    r12
0x1800048be  push    r14
0x1800048c0  push    r15
0x1800048c2  sub     rsp, 60h
0x1800048c6  mov     r12d, r8d
0x1800048c9  mov     rbx, rdx
0x1800048cc  mov     r15, rcx
0x1800048cf  lea     rsi, [rcx+0F0h]
0x1800048d6  mov     rcx, rsi; lpCriticalSection
0x1800048d9  call    cs:__imp_EnterCriticalSection
0x1800048df  mov     [rsp+88h+var_30], rsi
0x1800048e4  inc     dword ptr [r15]
0x1800048e7  mov     eax, [r15]
0x1800048ea  mov     dword ptr [rsp+88h+var_48], eax
0x1800048ee  lea     rcx, [r15+8]
0x1800048f2  mov     r9, rbx
0x1800048f5  lea     r8, [rsp+88h+var_48]
0x1800048fa  lea     rdx, [rsp+88h+var_40]
0x1800048ff  call    ??$emplace@AEAJAEAUChannelRequestContext@Wns@@@?$_Hash@V?$_Umap_traits@JUChannelRequestContext@Wns@@V?$_Uhash_compare@JU?$hash@J@std@@U?$equal_to@J@2@@std@@V?$allocator@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBJUChannelRequestContext@Wns@@@std@@@std@@@std@@@std@@_N@1@AEAJAEAUChannelRequestContext@Wns@@@Z; std::_Hash<std::_Umap_traits<long,Wns::ChannelRequestContext,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<std::pair<long const,Wns::ChannelRequestContext>>,0>>::emplace<long &,Wns::ChannelRequestContext &>(long &,Wns::ChannelRequestContext &)
0x180004904  mov     ecx, 20h ; ' '; Size
0x180004909  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000490e  mov     [rsp+88h+var_40], rax
0x180004913  lea     rcx, ??_7TimerContext@CPTransactionRequestManager@Wns@@6B@; const Wns::CPTransactionRequestManager::TimerContext::`vftable'
0x18000491a  mov     [rax], rcx
0x18000491d  mov     [rax+8], r15
0x180004921  mov     ebx, dword ptr [rsp+88h+var_48]
0x180004925  mov     [rax+10h], ebx
0x180004928  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x180004930  mov     [rsp+88h+var_48], rax
0x180004935  mov     rdx, [r15+58h]
0x180004939  cmp     rdx, [r15+60h]
0x18000493d  jz      short loc_180004949
0x18000493f  mov     [rdx], rax
0x180004942  add     qword ptr [r15+58h], 8
0x180004947  jmp     short loc_180004957
0x180004949  lea     r8, [rsp+88h+var_48]
0x18000494e  lea     rcx, [r15+50h]
0x180004952  call    ??$_Emplace_reallocate@PEAVTimerContext@CPTransactionRequestManager@Wns@@@?$vector@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@1@QEAV21@$$QEAPEAVTimerContext@CPTransactionRequestManager@Wns@@@Z; std::vector<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>::_Emplace_reallocate<Wns::CPTransactionRequestManager::TimerContext *>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,Wns::CPTransactionRequestManager::TimerContext * &&)
0x180004957  mov     rax, [r15+58h]
0x18000495b  mov     rdi, [rax-8]
0x18000495f  test    rsi, rsi
0x180004962  jz      short loc_18000496D
0x180004964  mov     rcx, rsi; lpCriticalSection
0x180004967  call    cs:__imp_LeaveCriticalSection
0x18000496d  mov     [rsp+88h+Flags], 8; Flags
0x180004975  mov     dword ptr [rsp+88h+Period], 0; Period
0x18000497d  mov     [rsp+88h+DueTime], r12d; DueTime
0x180004982  mov     r9, rdi; Parameter
0x180004985  lea     r8, ?TimeoutHandler@Wns@@YAXPEAXE@Z; Callback
0x18000498c  mov     rdx, [r15+48h]; TimerQueue
0x180004990  lea     rcx, [rdi+18h]; phNewTimer
0x180004994  call    cs:__imp_CreateTimerQueueTimer
0x18000499a  mov     rcx, [rsp+88h]; this
0x1800049a2  mov     dword ptr [rsp+88h+Period], ebx; char *
0x1800049a6  lea     rdx, aFailedToQueueT; "Failed to queue timer for transactionId"...
0x1800049ad  mov     qword ptr [rsp+88h+DueTime], rdx; int
0x1800049b2  mov     r9d, eax; char *
0x1800049b5  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800049bc  mov     edx, 198h; void *
0x1800049c1  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800049c6  test    eax, eax
0x1800049c8  jnz     short loc_180004A28
0x1800049ca  mov     qword ptr [rdi+18h], 0FFFFFFFFFFFFFFFFh
0x1800049d2  mov     rcx, rsi; lpCriticalSection
0x1800049d5  call    cs:__imp_EnterCriticalSection
0x1800049db  mov     rdi, [r15+58h]
0x1800049df  mov     r9d, ebx
0x1800049e2  mov     r8, rdi
0x1800049e5  mov     rdx, [r15+50h]
0x1800049e9  lea     rcx, [rsp+88h+var_40]
0x1800049ee  call    std__remove_if_std___Vector_iterator_std___Vector_val_std___Simple_types_std__unique_ptr_Wns__CPTransactionRequestManager__TimerContext_std__default_delete_Wns__CPTransactionRequestManager__TimerContext___________lambda_030f659afdb6fc1c77419263130569a6___
0x1800049f3  cmp     [rax], rdi
0x1800049f6  jz      short loc_180004A1A
0x1800049f8  mov     r8, [rax]
0x1800049fb  mov     rdx, [r15+58h]
0x1800049ff  mov     rcx, rdi
0x180004a02  call    ??$_Move_unchecked@PEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@PEAV12@@std@@YAPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@0@PEAV10@00@Z; std::_Move_unchecked<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *)
0x180004a07  mov     rdi, rax
0x180004a0a  mov     rdx, [r15+58h]
0x180004a0e  mov     rcx, rax
0x180004a11  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VTimerContext@CPTransactionRequestManager@Wns@@U?$default_delete@VTimerContext@CPTransactionRequestManager@Wns@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>>>(std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> *,std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext> * const,std::allocator<std::unique_ptr<Wns::CPTransactionRequestManager::TimerContext>> &)
0x180004a16  mov     [r15+58h], rdi
0x180004a1a  test    rsi, rsi
0x180004a1d  jz      short loc_180004A28
0x180004a1f  mov     rcx, rsi; lpCriticalSection
0x180004a22  call    cs:__imp_LeaveCriticalSection
0x180004a28  mov     eax, ebx
0x180004a2a  lea     r11, [rsp+88h+var_28]
0x180004a2f  mov     rbx, [r11+38h]
0x180004a33  mov     rbp, [r11+48h]
0x180004a37  mov     rsp, r11
0x180004a3a  pop     r15
0x180004a3c  pop     r14
0x180004a3e  pop     r12
0x180004a40  pop     rdi
0x180004a41  pop     rsi
0x180004a42  retn
```
