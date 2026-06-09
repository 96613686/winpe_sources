# Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_]::_OnCancel

- ea: `0x14001c5f0`
- end: `0x14001c738`
- name: `Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::[Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1_]::_OnCancel`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x14001c5cc`
- `0x14001c740`

## callees

- `0x14001a340`
- `0x14001c5f0`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001c6cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001c6fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001c6cc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14001c6fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c675`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001c675`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001c63d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001c63d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c68d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c68d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001c714`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001c725`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001c714`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001c725`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Concurrency::details::_AsyncTaskThunk_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0___::_Concurrency::details::_AsyncInfoBase_Concurrency::details::_AsyncAttributes__lambda_012995b310defc0ef83a366488a71671__void_void_Concurrency::details::_TaskTypeTraits_void_0__0_0__1__::_OnCancel(
        __int64 a1)
{
  __int64 v1; // rbp
  _QWORD *v2; // rbx
  _QWORD *v3; // rdx
  _QWORD *v4; // rax
  __int64 v5; // rax
  _QWORD *i; // rdi
  volatile signed __int32 *v7; // rsi
  DWORD CurrentThreadId; // r15d
  signed __int32 v9; // eax
  _QWORD *v10; // rcx
  _QWORD *v11; // rdi
  __int128 v12; // [rsp+28h] [rbp-50h] BYREF

  v1 = *(_QWORD *)(a1 + 136);
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(v1 + 16), 1, 0) )
  {
    v12 = 0u;
    v2 = (_QWORD *)std::_List_alloc<0,std::_List_base_types<pplx::details::_CancellationTokenRegistration *>>::_Buynode0(
                     1,
                     0,
                     0);
    *(_QWORD *)&v12 = v2;
    EnterCriticalSection((LPCRITICAL_SECTION)(v1 + 32));
    v3 = (_QWORD *)(v1 + 96);
    if ( (__int128 *)(v1 + 96) != &v12 )
    {
      v4 = (_QWORD *)*v3;
      *v3 = v2;
      v2 = v4;
      *(_QWORD *)&v12 = v4;
      v5 = *(_QWORD *)(v1 + 104);
      *(_QWORD *)(v1 + 104) = 0;
      *((_QWORD *)&v12 + 1) = v5;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v1 + 32));
    for ( i = (_QWORD *)*v2; i != v2; i = (_QWORD *)*i )
    {
      v7 = (volatile signed __int32 *)i[2];
      CurrentThreadId = GetCurrentThreadId();
      if ( !_InterlockedCompareExchange(v7 + 4, CurrentThreadId, 0) )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 16LL))(v7);
        v9 = _InterlockedCompareExchange(v7 + 4, 3, CurrentThreadId);
        if ( CurrentThreadId != v9 )
          CurrentThreadId = v9;
        if ( CurrentThreadId == 2 )
          SetEvent(**((HANDLE **)v7 + 3));
      }
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    _InterlockedExchange((volatile __int32 *)(v1 + 16), 2);
    SetEvent(*(HANDLE *)(v1 + 24));
    v10 = (_QWORD *)*v2;
    *v2 = v2;
    v2[1] = v2;
    if ( v10 != v2 )
    {
      do
      {
        v11 = (_QWORD *)*v10;
        operator delete(v10);
        v10 = v11;
      }
      while ( v11 != v2 );
    }
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x14001c5f0  push    rbx
0x14001c5f2  push    rbp
0x14001c5f3  push    rsi
0x14001c5f4  push    rdi
0x14001c5f5  push    r14
0x14001c5f7  push    r15
0x14001c5f9  sub     rsp, 48h
0x14001c5fd  mov     rbp, [rcx+88h]
0x14001c604  mov     ecx, 1
0x14001c609  xor     eax, eax
0x14001c60b  lock cmpxchg [rbp+10h], ecx
0x14001c610  jnz     loc_14001C72B
0x14001c616  xorps   xmm0, xmm0
0x14001c619  movups  [rsp+78h+var_50], xmm0
0x14001c61e  mov     qword ptr [rsp+78h+var_50+8], 0
0x14001c627  xor     r8d, r8d
0x14001c62a  xor     edx, edx
0x14001c62c  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAV_CancellationTokenRegistration@details@pplx@@V?$allocator@PEAV_CancellationTokenRegistration@details@pplx@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAV_CancellationTokenRegistration@details@pplx@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<pplx::details::_CancellationTokenRegistration *>>::_Buynode0(std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *,std::_List_node<pplx::details::_CancellationTokenRegistration *,void *> *)
0x14001c631  mov     rbx, rax
0x14001c634  mov     qword ptr [rsp+78h+var_50], rax
0x14001c639  lea     rcx, [rbp+20h]; lpCriticalSection
0x14001c63d  call    cs:__imp_EnterCriticalSection
0x14001c643  nop
0x14001c644  lea     rdx, [rbp+60h]
0x14001c648  lea     rax, [rsp+78h+var_50]
0x14001c64d  cmp     rdx, rax
0x14001c650  jz      short loc_14001C671
0x14001c652  mov     rax, [rdx]
0x14001c655  mov     [rdx], rbx
0x14001c658  mov     rbx, rax
0x14001c65b  mov     qword ptr [rsp+78h+var_50], rax
0x14001c660  mov     rax, [rdx+8]
0x14001c664  mov     qword ptr [rdx+8], 0
0x14001c66c  mov     qword ptr [rsp+78h+var_50+8], rax
0x14001c671  lea     rcx, [rbp+20h]; lpCriticalSection
0x14001c675  call    cs:__imp_LeaveCriticalSection
0x14001c67b  mov     rdi, [rbx]
0x14001c67e  mov     r14d, 2
0x14001c684  cmp     rdi, rbx
0x14001c687  jz      short loc_14001C6F3
0x14001c689  mov     rsi, [rdi+10h]
0x14001c68d  call    cs:__imp_GetCurrentThreadId
0x14001c693  mov     r15d, eax
0x14001c696  xor     eax, eax
0x14001c698  lock cmpxchg [rsi+10h], r15d
0x14001c69e  jnz     short loc_14001C6D2
0x14001c6a0  mov     rcx, [rsi]
0x14001c6a3  mov     rax, [rcx+10h]
0x14001c6a7  mov     rcx, rsi
0x14001c6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c6af  mov     ecx, 3
0x14001c6b4  mov     eax, r15d
0x14001c6b7  lock cmpxchg [rsi+10h], ecx
0x14001c6bc  cmovnz  r15d, eax
0x14001c6c0  cmp     r15d, r14d
0x14001c6c3  jnz     short loc_14001C6D2
0x14001c6c5  mov     rcx, [rsi+18h]
0x14001c6c9  mov     rcx, [rcx]; hEvent
0x14001c6cc  call    cs:__imp_SetEvent
0x14001c6d2  or      eax, 0FFFFFFFFh
0x14001c6d5  lock xadd [rsi+8], eax
0x14001c6da  cmp     eax, 1
0x14001c6dd  jnz     short loc_14001C6EE
0x14001c6df  mov     rax, [rsi]
0x14001c6e2  mov     rcx, rsi
0x14001c6e5  mov     rax, [rax+8]
0x14001c6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c6ee  mov     rdi, [rdi]
0x14001c6f1  jmp     short loc_14001C684
0x14001c6f3  xchg    r14d, [rbp+10h]
0x14001c6f7  mov     rcx, [rbp+18h]; hEvent
0x14001c6fb  call    cs:__imp_SetEvent
0x14001c701  nop
0x14001c702  mov     rcx, [rbx]
0x14001c705  mov     [rbx], rbx
0x14001c708  mov     [rbx+8], rbx
0x14001c70c  cmp     rcx, rbx
0x14001c70f  jz      short loc_14001C722
0x14001c711  mov     rdi, [rcx]
0x14001c714  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14001c71a  mov     rcx, rdi
0x14001c71d  cmp     rdi, rbx
0x14001c720  jnz     short loc_14001C711
0x14001c722  mov     rcx, rbx
0x14001c725  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14001c72b  add     rsp, 48h
0x14001c72f  pop     r15
0x14001c731  pop     r14
0x14001c733  pop     rdi
0x14001c734  pop     rsi
0x14001c735  pop     rbp
0x14001c736  pop     rbx
0x14001c737  retn
```
