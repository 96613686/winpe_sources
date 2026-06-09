# ThreadPool::Shutdown(void)

- ea: `0x18003f6b0`
- end: `0x18003f7b1`
- name: `?Shutdown@ThreadPool@@QEAAXXZ`
- size: `257`
- prototype: `void __fastcall(ThreadPool *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x18003c04c`
- `0x18003dcec`
- `0x18003fc30`

## callees

- `0x180013360`
- `0x18003f3a8`
- `0x18003f6b0`
- `0x18003f7b8`
- `0x18003f7f0`
- `0x18003ffb4`
- `0x180040110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f6d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f703`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f6d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003f703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f6f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f724`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f6f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003f724`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003f76e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18003f76e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003f777`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18003f777`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadPool::Shutdown(ThreadPool *this)
{
  struct _TP_WORK *v2; // rbx
  _QWORD **v3; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  _OWORD v9[3]; // [rsp+20h] [rbp-38h] BYREF

  v9[0] = 0;
  std::list<std::unique_ptr<WorkItem>>::_Alloc_sentinel_and_proxy(v9);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *((_BYTE *)this + 80) = 1;
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( this != (ThreadPool *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(v2);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (_QWORD **)((char *)this + 16);
  if ( v9 == (_OWORD *)((char *)this + 16) )
  {
    v4 = *(_QWORD **)&v9[0];
  }
  else
  {
    std::list<std::unique_ptr<WorkItem>>::clear(v9);
    v7 = *(_QWORD **)&v9[0];
    v4 = *v3;
    *(_QWORD *)&v9[0] = *v3;
    *v3 = v7;
    v8 = *((_QWORD *)&v9[0] + 1);
    *((_QWORD *)&v9[0] + 1) = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v8;
  }
  if ( this != (ThreadPool *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  ThreadPool::WriteTelemetry(this);
  ThreadPool::WriteTelemetryDetailed(this);
  std::_List_node<std::unique_ptr<WorkItem>,void *>::_Free_non_head<std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>>>(
    v5,
    (__int64)v4);
  *v4 = v4;
  v4[1] = v4;
  std::_List_node<std::unique_ptr<WorkItem>,void *>::_Free_non_head<std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>>>(
    v6,
    (__int64)v4);
  std::_Deallocate<16>(v4, 0x18u);
}

```

## disassembly

```asm
0x18003f6b0  push    rbx
0x18003f6b2  push    rbp
0x18003f6b3  push    rsi
0x18003f6b4  push    rdi
0x18003f6b5  sub     rsp, 38h
0x18003f6b9  mov     rbp, rcx
0x18003f6bc  xorps   xmm0, xmm0
0x18003f6bf  movdqu  [rsp+58h+var_38], xmm0
0x18003f6c5  lea     rcx, [rsp+58h+var_38]
0x18003f6ca  call    ?_Alloc_sentinel_and_proxy@?$list@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@V?$allocator@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::unique_ptr<WorkItem>>::_Alloc_sentinel_and_proxy(void)
0x18003f6cf  nop
0x18003f6d0  lea     rdi, [rbp+20h]
0x18003f6d4  mov     rcx, rdi; lpCriticalSection
0x18003f6d7  call    cs:__imp_EnterCriticalSection
0x18003f6dd  mov     byte ptr [rbp+50h], 1
0x18003f6e1  mov     rbx, [rbp+48h]
0x18003f6e5  mov     qword ptr [rbp+48h], 0
0x18003f6ed  test    rdi, rdi
0x18003f6f0  jz      short loc_18003F6FB
0x18003f6f2  mov     rcx, rdi; lpCriticalSection
0x18003f6f5  call    cs:__imp_LeaveCriticalSection
0x18003f6fb  test    rbx, rbx
0x18003f6fe  jnz     short loc_18003F766
0x18003f700  mov     rcx, rdi; lpCriticalSection
0x18003f703  call    cs:__imp_EnterCriticalSection
0x18003f709  lea     rsi, [rbp+10h]
0x18003f70d  lea     rax, [rsp+58h+var_38]
0x18003f712  cmp     rax, rsi
0x18003f715  jnz     short loc_18003F77F
0x18003f717  mov     rbx, qword ptr [rsp+58h+var_38]
0x18003f71c  test    rdi, rdi
0x18003f71f  jz      short loc_18003F72A
0x18003f721  mov     rcx, rdi; lpCriticalSection
0x18003f724  call    cs:__imp_LeaveCriticalSection
0x18003f72a  mov     rcx, rbp; this
0x18003f72d  call    ?WriteTelemetry@ThreadPool@@AEAAXXZ; ThreadPool::WriteTelemetry(void)
0x18003f732  mov     rcx, rbp; this
0x18003f735  call    ?WriteTelemetryDetailed@ThreadPool@@AEAAXXZ; ThreadPool::WriteTelemetryDetailed(void)
0x18003f73a  mov     rdx, rbx
0x18003f73d  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::unique_ptr<WorkItem>,void *>::_Free_non_head<std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>>>(std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>> &,std::_List_node<std::unique_ptr<WorkItem>,void *> *)
0x18003f742  mov     [rbx], rbx
0x18003f745  mov     [rbx+8], rbx
0x18003f749  mov     rdx, rbx
0x18003f74c  call    ??$_Free_non_head@V?$allocator@U?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@@std@@@?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::unique_ptr<WorkItem>,void *>::_Free_non_head<std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>>>(std::allocator<std::_List_node<std::unique_ptr<WorkItem>,void *>> &,std::_List_node<std::unique_ptr<WorkItem>,void *> *)
0x18003f751  mov     edx, 18h
0x18003f756  mov     rcx, rbx
0x18003f759  add     rsp, 38h
0x18003f75d  pop     rdi
0x18003f75e  pop     rsi
0x18003f75f  pop     rbp
0x18003f760  pop     rbx
0x18003f761  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003f766  mov     edx, 1; fCancelPendingCallbacks
0x18003f76b  mov     rcx, rbx; pwk
0x18003f76e  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18003f774  mov     rcx, rbx; pwk
0x18003f777  call    cs:__imp_CloseThreadpoolWork
0x18003f77d  jmp     short loc_18003F700
0x18003f77f  lea     rcx, [rsp+58h+var_38]
0x18003f784  call    ?clear@?$list@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@V?$allocator@V?$unique_ptr@VWorkItem@@U?$default_delete@VWorkItem@@@std@@@std@@@2@@std@@QEAAXXZ; std::list<std::unique_ptr<WorkItem>>::clear(void)
0x18003f789  mov     rax, qword ptr [rsp+58h+var_38]
0x18003f78e  mov     rbx, [rsi]
0x18003f791  mov     qword ptr [rsp+58h+var_38], rbx
0x18003f796  mov     [rsi], rax
0x18003f799  mov     rcx, qword ptr [rsp+58h+var_38+8]
0x18003f79e  mov     rax, [rsi+8]
0x18003f7a2  mov     qword ptr [rsp+58h+var_38+8], rax
0x18003f7a7  mov     [rsi+8], rcx
0x18003f7ab  jmp     loc_18003F71C
```
