# Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)

- ea: `0x18004c124`
- end: `0x18004c2c4`
- name: `?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z`
- size: `416`
- prototype: `void __fastcall(Synchronizer *__hidden this, struct SynchronizedObject *, int, void *, void *, void *)`
- caller_count: `21`
- callee_count: `11`
- tags: ``

## callers

- `0x180026830`
- `0x1800268a0`
- `0x1800268d0`
- `0x180026960`
- `0x180029200`
- `0x180029380`
- `0x18002953c`
- `0x180029fd0`
- `0x18002a090`
- `0x18002a148`
- `0x18002a270`
- `0x18002a534`
- `0x18002a718`
- `0x18002b240`
- `0x18002b2b8`
- `0x18002b374`
- `0x18002b440`
- `0x18002ba00`
- `0x180030560`
- `0x180030764`
- `0x180030ae4`

## callees

- `0x18000a91c`
- `0x18000abe8`
- `0x180031230`
- `0x18003123c`
- `0x18004bf6c`
- `0x18004c0f8`
- `0x18004c124`
- `0x18004c328`
- `0x18004c344`
- `0x18004c358`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c157`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c24c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c157`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c24c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c2a0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c217`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c2a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c20b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c20b`

## pseudocode

```c
void __fastcall Synchronizer::EnqueueEvent(
        Synchronizer *this,
        struct SynchronizedObject *a2,
        unsigned int a3,
        void *a4)
{
  struct SynchronizedObject *v7; // rsi
  __int64 v8; // r13
  unsigned __int64 v9; // rax
  char v10; // bp
  __int64 v11; // rsi
  __int64 v12; // r15
  size_t size_of; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rbp
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  unsigned int v21; // edx
  struct SynchronizedObject *v22; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-70h]
  void *v24; // [rsp+40h] [rbp-68h]
  __int128 v25; // [rsp+48h] [rbp-60h]

  v7 = a2;
  (*(void (__fastcall **)(struct SynchronizedObject *))(*(_QWORD *)a2 + 16LL))(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v8 = 0;
  if ( *((_BYTE *)this + 48) )
  {
    v9 = *((_QWORD *)this + 11) + 1LL;
    v22 = v7;
    v10 = 0;
    v23 = a3;
    v24 = a4;
    v25 = 0;
    if ( *((_QWORD *)this + 9) <= v9 )
      std::deque<Synchronizer::QueueRecord>::_Growmap((char *)this + 56);
    *((_QWORD *)this + 10) &= *((_QWORD *)this + 9) - 1LL;
    v11 = *((_QWORD *)this + 10) + *((_QWORD *)this + 11);
    v12 = std::deque<Synchronizer::QueueRecord>::_Getblock((char *)this + 56, v11);
    if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 8 * v12) )
    {
      size_of = std::_Get_size_of_n<40>(1);
      *(_QWORD *)(*((_QWORD *)this + 8) + 8 * v12) = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    }
    v14 = std::_Deque_val<std::_Deque_simple_types<Synchronizer::QueueRecord>>::_Address_subscript(
            (char *)this + 56,
            v11);
    std::_Default_allocator_traits<std::allocator<Synchronizer::QueueRecord>>::construct<Synchronizer::QueueRecord,Synchronizer::QueueRecord>(
      v15,
      v14,
      &v22);
    ++*((_QWORD *)this + 11);
  }
  else
  {
    v16 = 0;
    *((_BYTE *)this + 48) = 1;
    *((_DWORD *)this + 24) = GetCurrentThreadId();
    while ( 1 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      (*(void (__fastcall **)(struct SynchronizedObject *, _QWORD, void *, __int64, __int64))(*(_QWORD *)v7 + 8LL))(
        v7,
        a3,
        a4,
        v8,
        v16);
      (*(void (__fastcall **)(struct SynchronizedObject *))(*(_QWORD *)v7 + 24LL))(v7);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      if ( !*((_QWORD *)this + 11) )
        break;
      v7 = *(struct SynchronizedObject **)std::queue<std::vector<unsigned char>>::front((char *)this + 56);
      a3 = *(_DWORD *)(std::queue<std::vector<unsigned char>>::front(v17) + 8);
      a4 = *(void **)(std::queue<std::vector<unsigned char>>::front(v18) + 16);
      v8 = *(_QWORD *)(std::queue<std::vector<unsigned char>>::front(v19) + 24);
      v16 = *(_QWORD *)(std::queue<std::vector<unsigned char>>::front(v20) + 32);
      std::deque<std::vector<unsigned char> *,std::allocator<std::vector<unsigned char> *>>::pop_front();
    }
    v10 = *((_BYTE *)this + 49);
    *((_BYTE *)this + 48) = 0;
    *((_DWORD *)this + 24) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( v10 )
    Synchronizer::`scalar deleting destructor'(this, v21);
}

```

## disassembly

```asm
0x18004c124  push    rbx
0x18004c126  push    rbp
0x18004c127  push    rsi
0x18004c128  push    rdi
0x18004c129  push    r12
0x18004c12b  push    r13
0x18004c12d  push    r14
0x18004c12f  push    r15
0x18004c131  sub     rsp, 68h
0x18004c135  mov     rax, [rdx]
0x18004c138  mov     rdi, rcx
0x18004c13b  mov     rcx, rdx
0x18004c13e  mov     r15, r9
0x18004c141  mov     r12d, r8d
0x18004c144  mov     rsi, rdx
0x18004c147  mov     rax, [rax+10h]
0x18004c14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c150  lea     r14, [rdi+8]
0x18004c154  mov     rcx, r14; lpCriticalSection
0x18004c157  call    cs:__imp_EnterCriticalSection
0x18004c15d  xor     r13d, r13d
0x18004c160  lea     rbx, [rdi+38h]
0x18004c164  cmp     [rdi+30h], r13b
0x18004c168  jz      loc_18004C204
0x18004c16e  mov     rax, [rbx+20h]
0x18004c172  xorps   xmm0, xmm0
0x18004c175  inc     rax
0x18004c178  mov     [rsp+0A8h+var_78], rsi
0x18004c17d  mov     bpl, r13b
0x18004c180  mov     [rsp+0A8h+var_70], r12d
0x18004c185  mov     [rsp+0A8h+var_68], r15
0x18004c18a  movdqu  [rsp+0A8h+var_60], xmm0
0x18004c190  cmp     [rbx+10h], rax
0x18004c194  ja      short loc_18004C19E
0x18004c196  mov     rcx, rbx
0x18004c199  call    ?_Growmap@?$deque@UQueueRecord@Synchronizer@@V?$allocator@UQueueRecord@Synchronizer@@@std@@@std@@AEAAX_K@Z; std::deque<Synchronizer::QueueRecord>::_Growmap(unsigned __int64)
0x18004c19e  mov     rax, [rbx+10h]
0x18004c1a2  mov     rcx, rbx
0x18004c1a5  dec     rax
0x18004c1a8  and     [rbx+18h], rax
0x18004c1ac  mov     rsi, [rbx+20h]
0x18004c1b0  add     rsi, [rbx+18h]
0x18004c1b4  mov     rdx, rsi
0x18004c1b7  call    ?_Getblock@?$deque@UQueueRecord@Synchronizer@@V?$allocator@UQueueRecord@Synchronizer@@@std@@@std@@AEBA_J_K@Z; std::deque<Synchronizer::QueueRecord>::_Getblock(unsigned __int64)
0x18004c1bc  mov     rcx, [rbx+8]
0x18004c1c0  mov     r15, rax
0x18004c1c3  cmp     [rcx+rax*8], r13
0x18004c1c7  jnz     short loc_18004C1E3
0x18004c1c9  mov     ecx, 1
0x18004c1ce  call    ??$_Get_size_of_n@$0CI@@std@@YA_K_K@Z; std::_Get_size_of_n<40>(unsigned __int64)
0x18004c1d3  mov     rcx, rax
0x18004c1d6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18004c1db  mov     rcx, [rbx+8]
0x18004c1df  mov     [rcx+r15*8], rax
0x18004c1e3  mov     rdx, rsi
0x18004c1e6  mov     rcx, rbx
0x18004c1e9  call    ?_Address_subscript@?$_Deque_val@U?$_Deque_simple_types@UQueueRecord@Synchronizer@@@std@@@std@@QEAAPEAUQueueRecord@Synchronizer@@_K@Z; std::_Deque_val<std::_Deque_simple_types<Synchronizer::QueueRecord>>::_Address_subscript(unsigned __int64)
0x18004c1ee  lea     r8, [rsp+0A8h+var_78]
0x18004c1f3  mov     rdx, rax
0x18004c1f6  call    ??$construct@UQueueRecord@Synchronizer@@U12@@?$_Default_allocator_traits@V?$allocator@UQueueRecord@Synchronizer@@@std@@@std@@SAXAEAV?$allocator@UQueueRecord@Synchronizer@@@1@QEAUQueueRecord@Synchronizer@@$$QEAU34@@Z; std::_Default_allocator_traits<std::allocator<Synchronizer::QueueRecord>>::construct<Synchronizer::QueueRecord,Synchronizer::QueueRecord>(std::allocator<Synchronizer::QueueRecord> &,Synchronizer::QueueRecord * const,Synchronizer::QueueRecord &&)
0x18004c1fb  inc     qword ptr [rbx+20h]
0x18004c1ff  jmp     loc_18004C29D
0x18004c204  mov     rbp, r13
0x18004c207  mov     byte ptr [rdi+30h], 1
0x18004c20b  call    cs:__imp_GetCurrentThreadId
0x18004c211  mov     [rdi+60h], eax
0x18004c214  mov     rcx, r14; lpCriticalSection
0x18004c217  call    cs:__imp_LeaveCriticalSection
0x18004c21d  mov     rax, [rsi]
0x18004c220  mov     r9, r13
0x18004c223  mov     r8, r15
0x18004c226  mov     [rsp+0A8h+var_88], rbp
0x18004c22b  mov     edx, r12d
0x18004c22e  mov     rcx, rsi
0x18004c231  mov     rax, [rax+8]
0x18004c235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c23a  mov     rax, [rsi]
0x18004c23d  mov     rcx, rsi
0x18004c240  mov     rax, [rax+18h]
0x18004c244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c249  mov     rcx, r14; lpCriticalSection
0x18004c24c  call    cs:__imp_EnterCriticalSection
0x18004c252  xor     r13d, r13d
0x18004c255  cmp     [rbx+20h], r13
0x18004c259  jz      short loc_18004C291
0x18004c25b  mov     rcx, rbx
0x18004c25e  call    ?front@?$queue@V?$vector@EV?$allocator@E@std@@@std@@V?$deque@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@2@@std@@QEAAAEAV?$vector@EV?$allocator@E@std@@@2@XZ; std::queue<std::vector<uchar>>::front(void)
0x18004c263  mov     rsi, [rax]
0x18004c266  call    ?front@?$queue@V?$vector@EV?$allocator@E@std@@@std@@V?$deque@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@2@@std@@QEAAAEAV?$vector@EV?$allocator@E@std@@@2@XZ; std::queue<std::vector<uchar>>::front(void)
0x18004c26b  mov     r12d, [rax+8]
0x18004c26f  call    ?front@?$queue@V?$vector@EV?$allocator@E@std@@@std@@V?$deque@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@2@@std@@QEAAAEAV?$vector@EV?$allocator@E@std@@@2@XZ; std::queue<std::vector<uchar>>::front(void)
0x18004c274  mov     r15, [rax+10h]
0x18004c278  call    ?front@?$queue@V?$vector@EV?$allocator@E@std@@@std@@V?$deque@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@2@@std@@QEAAAEAV?$vector@EV?$allocator@E@std@@@2@XZ; std::queue<std::vector<uchar>>::front(void)
0x18004c27d  mov     r13, [rax+18h]
0x18004c281  call    ?front@?$queue@V?$vector@EV?$allocator@E@std@@@std@@V?$deque@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@2@@std@@QEAAAEAV?$vector@EV?$allocator@E@std@@@2@XZ; std::queue<std::vector<uchar>>::front(void)
0x18004c286  mov     rbp, [rax+20h]
0x18004c28a  call    ?pop_front@?$deque@PEAV?$vector@EV?$allocator@E@std@@@std@@V?$allocator@PEAV?$vector@EV?$allocator@E@std@@@std@@@2@@std@@QEAAXXZ; std::deque<std::vector<uchar> *,std::allocator<std::vector<uchar> *>>::pop_front(void)
0x18004c28f  jmp     short loc_18004C214
0x18004c291  mov     bpl, [rdi+31h]
0x18004c295  mov     [rdi+30h], r13b
0x18004c299  mov     [rdi+60h], r13d
0x18004c29d  mov     rcx, r14; lpCriticalSection
0x18004c2a0  call    cs:__imp_LeaveCriticalSection
0x18004c2a6  test    bpl, bpl
0x18004c2a9  jz      short loc_18004C2B3
0x18004c2ab  mov     rcx, rdi; this
0x18004c2ae  call    ??_GSynchronizer@@AEAAPEAXI@Z; Synchronizer::`scalar deleting destructor'(uint)
0x18004c2b3  add     rsp, 68h
0x18004c2b7  pop     r15
0x18004c2b9  pop     r14
0x18004c2bb  pop     r13
0x18004c2bd  pop     r12
0x18004c2bf  pop     rdi
0x18004c2c0  pop     rsi
0x18004c2c1  pop     rbp
0x18004c2c2  pop     rbx
0x18004c2c3  retn
```
