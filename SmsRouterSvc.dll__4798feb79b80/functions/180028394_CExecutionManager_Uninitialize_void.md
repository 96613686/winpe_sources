# CExecutionManager::Uninitialize(void)

- ea: `0x180028394`
- end: `0x1800284df`
- name: `?Uninitialize@CExecutionManager@@QEAAJXZ`
- size: `331`
- prototype: `__int64 __fastcall(CExecutionManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180011a18`
- `0x1800426a0`

## callees

- `0x180003f50`
- `0x18000e8c0`
- `0x1800279b8`
- `0x180028394`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002844e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002844e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180028462`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180028462`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180028473`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x180028473`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180028405`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180028405`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CExecutionManager::Uninitialize(CExecutionManager *this)
{
  char *v2; // rbx
  void *v3; // r15
  void *v4; // rbp
  void *v5; // r14
  void *v6; // rsi
  __int64 v7; // rdx
  char *v9; // r14
  _QWORD *v10; // rdi
  _QWORD *v11; // rsi
  void *v12; // rbx
  _QWORD *v13; // rcx
  __int64 v14; // rdx

  v2 = (char *)this + 8;
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  v3 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  v4 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  v5 = (void *)*((_QWORD *)this + 10);
  *((_QWORD *)this + 10) = 0;
  v6 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))(v2);
  if ( v3 )
    UnregisterWaitEx(v3, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  while ( *((_QWORD *)this + 16) )
  {
    CSmsWorkItem::~CSmsWorkItem(
      *(CSmsWorkItem **)(*((_QWORD *)this + 13) + 8 * (*((_QWORD *)this + 15) & (*((_QWORD *)this + 14) - 1LL))),
      v7);
    if ( (*((_QWORD *)this + 16))-- == 1 )
      *((_QWORD *)this + 15) = 0;
    else
      ++*((_QWORD *)this + 15);
  }
  if ( v4 )
    CloseHandle(v4);
  if ( v5 )
    DeleteTimerQueueTimer(v6, v5, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( v6 )
    DeleteTimerQueueEx(v6, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  v9 = (char *)this + 136;
  v10 = (_QWORD *)*((_QWORD *)this + 17);
  v11 = (_QWORD *)v10[1];
  while ( !*((_BYTE *)v11 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<CSmsTimerItem>>::_Erase_tree<std::allocator<std::_Tree_node<CSmsTimerItem,void *>>>(
      v9,
      v9,
      v11[2]);
    v12 = v11;
    v13 = v11;
    v11 = (_QWORD *)*v11;
    CSmsWorkItem::~CSmsWorkItem((CSmsWorkItem *)(v13 + 5), v14);
    operator delete(v12);
  }
  v10[1] = v10;
  *v10 = v10;
  v10[2] = v10;
  *((_QWORD *)v9 + 1) = 0;
  return 0;
}

```

## disassembly

```asm
0x180028394  push    rbx
0x180028396  push    rbp
0x180028397  push    rsi
0x180028398  push    rdi
0x180028399  push    r14
0x18002839b  push    r15
0x18002839d  sub     rsp, 28h
0x1800283a1  mov     rdi, rcx
0x1800283a4  lea     rbx, [rcx+8]
0x1800283a8  mov     rax, [rbx]
0x1800283ab  mov     rcx, rbx
0x1800283ae  mov     rax, [rax]
0x1800283b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283b6  mov     r15, [rdi+40h]
0x1800283ba  mov     qword ptr [rdi+40h], 0
0x1800283c2  mov     rbp, [rdi+38h]
0x1800283c6  mov     qword ptr [rdi+38h], 0
0x1800283ce  mov     r14, [rdi+50h]
0x1800283d2  mov     qword ptr [rdi+50h], 0
0x1800283da  mov     rsi, [rdi+48h]
0x1800283de  mov     qword ptr [rdi+48h], 0
0x1800283e6  mov     rax, [rbx]
0x1800283e9  mov     rcx, rbx
0x1800283ec  mov     rax, [rax+8]
0x1800283f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283f5  nop
0x1800283f6  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800283fa  test    r15, r15
0x1800283fd  jz      short loc_18002840B
0x1800283ff  mov     rdx, rbx; CompletionEvent
0x180028402  mov     rcx, r15; WaitHandle
0x180028405  call    cs:__imp_UnregisterWaitEx
0x18002840b  cmp     qword ptr [rdi+80h], 0
0x180028413  jz      short loc_180028446
0x180028415  mov     rax, [rdi+70h]
0x180028419  dec     rax
0x18002841c  and     rax, [rdi+78h]
0x180028420  mov     rcx, [rdi+68h]
0x180028424  mov     rcx, [rcx+rax*8]; this
0x180028428  call    ??1CSmsWorkItem@@QEAA@XZ; CSmsWorkItem::~CSmsWorkItem(void)
0x18002842d  add     [rdi+80h], rbx
0x180028434  jnz     short loc_180028440
0x180028436  mov     qword ptr [rdi+78h], 0
0x18002843e  jmp     short loc_18002840B
0x180028440  inc     qword ptr [rdi+78h]
0x180028444  jmp     short loc_18002840B
0x180028446  test    rbp, rbp
0x180028449  jz      short loc_180028454
0x18002844b  mov     rcx, rbp; hObject
0x18002844e  call    cs:__imp_CloseHandle
0x180028454  test    r14, r14
0x180028457  jz      short loc_180028468
0x180028459  mov     r8, rbx; CompletionEvent
0x18002845c  mov     rdx, r14; Timer
0x18002845f  mov     rcx, rsi; TimerQueue
0x180028462  call    cs:__imp_DeleteTimerQueueTimer
0x180028468  test    rsi, rsi
0x18002846b  jz      short loc_180028479
0x18002846d  mov     rdx, rbx; CompletionEvent
0x180028470  mov     rcx, rsi; TimerQueue
0x180028473  call    cs:__imp_DeleteTimerQueueEx
0x180028479  lea     r14, [rdi+88h]
0x180028480  mov     rdi, [r14]
0x180028483  mov     rsi, [rdi+8]
0x180028487  jmp     short loc_1800284B7
0x180028489  mov     r8, [rsi+10h]
0x18002848d  mov     rdx, r14
0x180028490  mov     rcx, r14
0x180028493  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@VCSmsTimerItem@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@VCSmsTimerItem@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@VCSmsTimerItem@@PEAX@std@@@1@PEAU?$_Tree_node@VCSmsTimerItem@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<CSmsTimerItem>>::_Erase_tree<std::allocator<std::_Tree_node<CSmsTimerItem,void *>>>(std::allocator<std::_Tree_node<CSmsTimerItem,void *>> &,std::_Tree_node<CSmsTimerItem,void *> *)
0x180028498  mov     rbx, rsi
0x18002849b  mov     rcx, rsi
0x18002849e  mov     rsi, [rsi]
0x1800284a1  add     rcx, 28h ; '('; this
0x1800284a5  call    ??1CSmsWorkItem@@QEAA@XZ; CSmsWorkItem::~CSmsWorkItem(void)
0x1800284aa  mov     edx, 78h ; 'x'
0x1800284af  mov     rcx, rbx; Block
0x1800284b2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800284b7  cmp     byte ptr [rsi+19h], 0
0x1800284bb  jz      short loc_180028489
0x1800284bd  mov     [rdi+8], rdi
0x1800284c1  mov     [rdi], rdi
0x1800284c4  mov     [rdi+10h], rdi
0x1800284c8  mov     qword ptr [r14+8], 0
0x1800284d0  xor     eax, eax
0x1800284d2  add     rsp, 28h
0x1800284d6  pop     r15
0x1800284d8  pop     r14
0x1800284da  pop     rdi
0x1800284db  pop     rsi
0x1800284dc  pop     rbp
0x1800284dd  pop     rbx
0x1800284de  retn
```
