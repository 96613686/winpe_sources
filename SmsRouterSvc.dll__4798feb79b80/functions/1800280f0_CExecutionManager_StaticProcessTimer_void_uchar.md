# CExecutionManager::StaticProcessTimer(void *,uchar)

- ea: `0x1800280f0`
- end: `0x180028242`
- name: `?StaticProcessTimer@CExecutionManager@@SAXPEAXE@Z`
- size: `338`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003a60`
- `0x180003f50`
- `0x18000e8c0`
- `0x180012344`
- `0x180027d40`
- `0x180027f4c`
- `0x1800280f0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180028166`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x180028166`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180028203`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180028203`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CExecutionManager::StaticProcessTimer(char *a1)
{
  char *v2; // rdi
  __int64 v3; // rdx
  _QWORD *v4; // rbx
  __int64 v5; // rdx
  void *v6; // rdx
  __int64 v7; // rdx
  __time64_t Time[4]; // [rsp+20h] [rbp-59h] BYREF
  __time64_t v9; // [rsp+40h] [rbp-39h]
  _QWORD v10[11]; // [rsp+48h] [rbp-31h] BYREF

  v10[0] = 0;
  v10[1] = 0;
  v10[9] = 0;
  Time[0] = 0;
  v2 = a1 + 8;
  while ( 1 )
  {
    Time[1] = (__time64_t)&Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
    Time[2] = (__time64_t)v2;
    (**(void (__fastcall ***)(char *))v2)(v2);
    if ( !*((_QWORD *)a1 + 18) )
      break;
    _time64(Time);
    v3 = **((_QWORD **)a1 + 17);
    v9 = *(_QWORD *)(v3 + 32);
    CSmsWorkItem::operator=(v10, v3 + 40);
    if ( Time[0] < v9 )
      goto LABEL_8;
    v4 = std::_Tree_val<std::_Tree_simple_types<std::pair<SmsUid const,std::shared_ptr<SmsStoreMessage>>>>::_Extract(
           (_QWORD *)a1 + 17,
           **((_QWORD ***)a1 + 17));
    CSmsWorkItem::~CSmsWorkItem((CSmsWorkItem *)(v4 + 5), v5);
    operator delete(v4);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
    CExecutionManager::ScheduleWorkItem((CExecutionManager *)a1, (struct CSmsWorkItem *)v10);
  }
  v6 = (void *)*((_QWORD *)a1 + 10);
  if ( v6 )
  {
    DeleteTimerQueueTimer(*((HANDLE *)a1 + 9), v6, 0);
    *((_QWORD *)a1 + 10) = 0;
  }
LABEL_8:
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  CSmsWorkItem::~CSmsWorkItem((CSmsWorkItem *)v10, v7);
}

```

## disassembly

```asm
0x1800280f0  push    rbp
0x1800280f2  push    rbx
0x1800280f3  push    rsi
0x1800280f4  push    rdi
0x1800280f5  lea     rbp, [rsp-3Fh]
0x1800280fa  sub     rsp, 0B8h
0x180028101  mov     rax, cs:__security_cookie
0x180028108  xor     rax, rsp
0x18002810b  mov     [rbp+57h+var_30], rax
0x18002810f  mov     rsi, rcx
0x180028112  mov     [rbp+57h+var_88], 0
0x18002811a  mov     [rbp+57h+var_80], 0
0x180028122  mov     [rbp+57h+var_40], 0
0x18002812a  mov     [rbp+57h+Time], 0
0x180028132  lea     rdi, [rcx+8]
0x180028136  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18002813d  mov     [rbp+57h+var_A8], rax
0x180028141  mov     [rbp+57h+var_A0], rdi
0x180028145  mov     rax, [rdi]
0x180028148  mov     rcx, rdi
0x18002814b  mov     rax, [rax]
0x18002814e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028153  nop
0x180028154  cmp     qword ptr [rsi+90h], 0
0x18002815c  jz      loc_1800281F3
0x180028162  lea     rcx, [rbp+57h+Time]; Time
0x180028166  call    cs:__imp__time64
0x18002816c  lea     rbx, [rsi+88h]
0x180028173  mov     rax, [rbx]
0x180028176  mov     rdx, [rax]
0x180028179  mov     rax, [rdx+20h]
0x18002817d  mov     [rbp+57h+var_90], rax
0x180028181  add     rdx, 28h ; '('
0x180028185  lea     rcx, [rbp+57h+var_88]
0x180028189  call    ??4CSmsWorkItem@@QEAAAEAV0@AEBV0@@Z; CSmsWorkItem::operator=(CSmsWorkItem const &)
0x18002818e  mov     rax, [rbp+57h+var_90]
0x180028192  cmp     [rbp+57h+Time], rax
0x180028196  jl      short loc_1800281E1
0x180028198  mov     rdx, [rbx]
0x18002819b  mov     rdx, [rdx]
0x18002819e  mov     rcx, rbx
0x1800281a1  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUSmsUid@@V?$shared_ptr@USmsStoreMessage@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUSmsUid@@V?$shared_ptr@USmsStoreMessage@@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUSmsUid@@V?$shared_ptr@USmsStoreMessage@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<SmsUid const,std::shared_ptr<SmsStoreMessage>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<SmsUid const,std::shared_ptr<SmsStoreMessage>>>>,std::_Iterator_base0>)
0x1800281a6  mov     rbx, rax
0x1800281a9  lea     rcx, [rax+28h]; this
0x1800281ad  call    ??1CSmsWorkItem@@QEAA@XZ; CSmsWorkItem::~CSmsWorkItem(void)
0x1800281b2  mov     edx, 78h ; 'x'
0x1800281b7  mov     rcx, rbx; Block
0x1800281ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800281bf  nop
0x1800281c0  mov     rax, [rdi]
0x1800281c3  mov     rcx, rdi
0x1800281c6  mov     rax, [rax+8]
0x1800281ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281cf  nop
0x1800281d0  lea     rdx, [rbp+57h+var_88]; struct CSmsWorkItem *
0x1800281d4  mov     rcx, rsi; this
0x1800281d7  call    ?ScheduleWorkItem@CExecutionManager@@QEAAJAEAVCSmsWorkItem@@@Z; CExecutionManager::ScheduleWorkItem(CSmsWorkItem &)
0x1800281dc  jmp     loc_180028136
0x1800281e1  mov     rax, [rdi]
0x1800281e4  mov     rcx, rdi
0x1800281e7  mov     rax, [rax+8]
0x1800281eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281f0  nop
0x1800281f1  jmp     short loc_180028221
0x1800281f3  mov     rdx, [rsi+50h]; Timer
0x1800281f7  test    rdx, rdx
0x1800281fa  jz      short loc_180028211
0x1800281fc  xor     r8d, r8d; CompletionEvent
0x1800281ff  mov     rcx, [rsi+48h]; TimerQueue
0x180028203  call    cs:__imp_DeleteTimerQueueTimer
0x180028209  mov     qword ptr [rsi+50h], 0
0x180028211  mov     rax, [rdi]
0x180028214  mov     rcx, rdi
0x180028217  mov     rax, [rax+8]
0x18002821b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028220  nop
0x180028221  lea     rcx, [rbp+57h+var_88]; this
0x180028225  call    ??1CSmsWorkItem@@QEAA@XZ; CSmsWorkItem::~CSmsWorkItem(void)
0x18002822a  mov     rcx, [rbp+57h+var_30]
0x18002822e  xor     rcx, rsp; StackCookie
0x180028231  call    __security_check_cookie
0x180028236  add     rsp, 0B8h
0x18002823d  pop     rdi
0x18002823e  pop     rsi
0x18002823f  pop     rbx
0x180028240  pop     rbp
0x180028241  retn
```
