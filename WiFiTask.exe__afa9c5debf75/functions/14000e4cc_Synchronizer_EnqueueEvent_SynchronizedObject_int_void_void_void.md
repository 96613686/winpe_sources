# Synchronizer::EnqueueEvent(SynchronizedObject *,int,void *,void *,void *)

- ea: `0x14000e4cc`
- end: `0x14000e68b`
- name: `?EnqueueEvent@Synchronizer@@AEAAXPEAVSynchronizedObject@@HPEAX11@Z`
- size: `447`
- prototype: `void __fastcall(Synchronizer *this, struct SynchronizedObject *, unsigned int, void *, void *)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x140009994`
- `0x14000a6b4`
- `0x14000d490`
- `0x14000d820`
- `0x14000dee0`

## callees

- `0x1400016c4`
- `0x1400016d0`
- `0x14000e44c`
- `0x14000e4cc`
- `0x14000e694`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e503`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e5f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e503`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14000e5f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000e5c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000e65a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000e5c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000e65a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e5af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e5af`

## pseudocode

```c
void __fastcall Synchronizer::EnqueueEvent(
        Synchronizer *this,
        struct SynchronizedObject *a2,
        unsigned int a3,
        void *a4,
        void *a5)
{
  unsigned int v7; // edi
  struct SynchronizedObject *v8; // rsi
  char v9; // bp
  __int64 v10; // rdx
  __int64 v11; // r12
  __int64 v12; // rdx
  __int64 v13; // rbp
  void *v14; // r14
  __int64 v15; // r10
  __int64 v16; // r9
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // [rsp+3Ch] [rbp-6Ch]

  v7 = a3;
  v8 = a2;
  (*(void (__fastcall **)(struct SynchronizedObject *))(*(_QWORD *)a2 + 16LL))(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( *((_BYTE *)this + 48) )
  {
    v9 = 0;
    if ( *((_QWORD *)this + 9) <= (unsigned __int64)(*((_QWORD *)this + 11) + 1LL) )
      std::deque<Synchronizer::QueueRecord>::_Growmap((char *)this + 56);
    v10 = *((_QWORD *)this + 9) - 1LL;
    *((_QWORD *)this + 10) &= v10;
    v11 = *((_QWORD *)this + 11) + *((_QWORD *)this + 10);
    if ( !*(_QWORD *)(*((_QWORD *)this + 8) + 8 * (v10 & v11)) )
      *(_QWORD *)(*((_QWORD *)this + 8) + 8 * (v10 & v11)) = operator new(0x28u);
    v12 = *(_QWORD *)(*((_QWORD *)this + 8) + 8 * (v11 & (*((_QWORD *)this + 9) - 1LL)));
    *(_DWORD *)(v12 + 8) = a3;
    *(_DWORD *)(v12 + 12) = v19;
    *(_QWORD *)(v12 + 24) = a5;
    *(_QWORD *)v12 = v8;
    *(_QWORD *)(v12 + 16) = a4;
    *(_QWORD *)(v12 + 32) = 0;
    ++*((_QWORD *)this + 11);
  }
  else
  {
    v13 = 0;
    *((_BYTE *)this + 48) = 1;
    v14 = a5;
    *((_DWORD *)this + 24) = GetCurrentThreadId();
    while ( 1 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      (*(void (__fastcall **)(struct SynchronizedObject *, _QWORD, void *, void *, __int64))(*(_QWORD *)v8 + 8LL))(
        v8,
        v7,
        a4,
        v14,
        v13);
      (*(void (__fastcall **)(struct SynchronizedObject *))(*(_QWORD *)v8 + 24LL))(v8);
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
      v15 = *((_QWORD *)this + 11);
      if ( !v15 )
        break;
      v16 = *((_QWORD *)this + 10);
      v17 = *(_QWORD *)(*((_QWORD *)this + 8) + 8 * (v16 & (*((_QWORD *)this + 9) - 1LL)));
      v18 = v15 - 1;
      v8 = *(struct SynchronizedObject **)v17;
      v7 = *(_DWORD *)(v17 + 8);
      a4 = *(void **)(v17 + 16);
      v14 = *(void **)(v17 + 24);
      v13 = *(_QWORD *)(v17 + 32);
      *((_QWORD *)this + 11) = v15 - 1;
      if ( v15 != 1 )
        v18 = v16 + 1;
      *((_QWORD *)this + 10) = v18;
    }
    v9 = *((_BYTE *)this + 49);
    *((_BYTE *)this + 48) = 0;
    *((_DWORD *)this + 24) = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( v9 )
  {
    Synchronizer::~Synchronizer(this);
    operator delete(this);
  }
}

```

## disassembly

```asm
0x14000e4cc  mov     [rsp+arg_10], r8d
0x14000e4d1  push    rbx
0x14000e4d2  push    rbp
0x14000e4d3  push    rsi
0x14000e4d4  push    rdi
0x14000e4d5  push    r12
0x14000e4d7  push    r13
0x14000e4d9  push    r14
0x14000e4db  push    r15
0x14000e4dd  sub     rsp, 68h
0x14000e4e1  mov     rax, [rdx]
0x14000e4e4  mov     rbx, rcx
0x14000e4e7  mov     rcx, rdx
0x14000e4ea  mov     r13, r9
0x14000e4ed  mov     edi, r8d
0x14000e4f0  mov     rsi, rdx
0x14000e4f3  mov     rax, [rax+10h]
0x14000e4f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4fc  lea     r15, [rbx+8]
0x14000e500  mov     rcx, r15; lpCriticalSection
0x14000e503  call    cs:__imp_EnterCriticalSection
0x14000e509  cmp     byte ptr [rbx+30h], 0
0x14000e50d  jz      loc_14000E5A9
0x14000e513  mov     rax, [rbx+58h]
0x14000e517  xor     bpl, bpl
0x14000e51a  inc     rax
0x14000e51d  cmp     [rbx+48h], rax
0x14000e521  ja      short loc_14000E52C
0x14000e523  lea     rcx, [rbx+38h]
0x14000e527  call    ?_Growmap@?$deque@UQueueRecord@Synchronizer@@V?$allocator@UQueueRecord@Synchronizer@@@std@@@std@@AEAAX_K@Z; std::deque<Synchronizer::QueueRecord>::_Growmap(unsigned __int64)
0x14000e52c  mov     rdx, [rbx+48h]
0x14000e530  dec     rdx
0x14000e533  and     [rbx+50h], rdx
0x14000e537  mov     r12, [rbx+50h]
0x14000e53b  add     r12, [rbx+58h]
0x14000e53f  mov     rax, [rbx+40h]
0x14000e543  mov     r14, r12
0x14000e546  and     r14, rdx
0x14000e549  cmp     qword ptr [rax+r14*8], 0
0x14000e54e  jnz     short loc_14000E562
0x14000e550  mov     ecx, 28h ; '('; Size
0x14000e555  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e55a  mov     rcx, [rbx+40h]
0x14000e55e  mov     [rcx+r14*8], rax
0x14000e562  mov     rax, [rbx+40h]
0x14000e566  mov     rcx, [rbx+48h]
0x14000e56a  dec     rcx
0x14000e56d  and     rcx, r12
0x14000e570  mov     rdx, [rax+rcx*8]
0x14000e574  mov     eax, [rsp+0A8h+arg_10]
0x14000e57b  mov     [rdx+8], eax
0x14000e57e  mov     eax, [rsp+0A8h+var_6C]
0x14000e582  mov     [rdx+0Ch], eax
0x14000e585  mov     rax, [rsp+0A8h+arg_20]
0x14000e58d  mov     [rdx+18h], rax
0x14000e591  mov     [rdx], rsi
0x14000e594  mov     [rdx+10h], r13
0x14000e598  mov     qword ptr [rdx+20h], 0
0x14000e5a0  inc     qword ptr [rbx+58h]
0x14000e5a4  jmp     loc_14000E657
0x14000e5a9  xor     ebp, ebp
0x14000e5ab  mov     byte ptr [rbx+30h], 1
0x14000e5af  call    cs:__imp_GetCurrentThreadId
0x14000e5b5  mov     r14, [rsp+0A8h+arg_20]
0x14000e5bd  mov     [rbx+60h], eax
0x14000e5c0  mov     rcx, r15; lpCriticalSection
0x14000e5c3  call    cs:__imp_LeaveCriticalSection
0x14000e5c9  mov     rax, [rsi]
0x14000e5cc  mov     r9, r14
0x14000e5cf  mov     r8, r13
0x14000e5d2  mov     [rsp+0A8h+var_88], rbp
0x14000e5d7  mov     edx, edi
0x14000e5d9  mov     rcx, rsi
0x14000e5dc  mov     rax, [rax+8]
0x14000e5e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5e5  mov     rax, [rsi]
0x14000e5e8  mov     rcx, rsi
0x14000e5eb  mov     rax, [rax+18h]
0x14000e5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5f4  mov     rcx, r15; lpCriticalSection
0x14000e5f7  call    cs:__imp_EnterCriticalSection
0x14000e5fd  mov     r10, [rbx+58h]
0x14000e601  test    r10, r10
0x14000e604  jz      short loc_14000E648
0x14000e606  mov     rax, [rbx+40h]
0x14000e60a  mov     rcx, [rbx+48h]
0x14000e60e  mov     r9, [rbx+50h]
0x14000e612  dec     rcx
0x14000e615  and     rcx, r9
0x14000e618  mov     rdx, [rax+rcx*8]
0x14000e61c  lea     rax, [r10-1]
0x14000e620  mov     rsi, [rdx]
0x14000e623  mov     edi, [rdx+8]
0x14000e626  mov     r13, [rdx+10h]
0x14000e62a  mov     r14, [rdx+18h]
0x14000e62e  mov     rbp, [rdx+20h]
0x14000e632  mov     [rbx+58h], rax
0x14000e636  test    rax, rax
0x14000e639  jz      short loc_14000E63F
0x14000e63b  lea     rax, [r9+1]
0x14000e63f  mov     [rbx+50h], rax
0x14000e643  jmp     loc_14000E5C0
0x14000e648  mov     bpl, [rbx+31h]
0x14000e64c  mov     byte ptr [rbx+30h], 0
0x14000e650  mov     dword ptr [rbx+60h], 0
0x14000e657  mov     rcx, r15; lpCriticalSection
0x14000e65a  call    cs:__imp_LeaveCriticalSection
0x14000e660  test    bpl, bpl
0x14000e663  jz      short loc_14000E67A
0x14000e665  mov     rcx, rbx; this
0x14000e668  call    ??1Synchronizer@@AEAA@XZ; Synchronizer::~Synchronizer(void)
0x14000e66d  mov     edx, 68h ; 'h'
0x14000e672  mov     rcx, rbx; Block
0x14000e675  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e67a  add     rsp, 68h
0x14000e67e  pop     r15
0x14000e680  pop     r14
0x14000e682  pop     r13
0x14000e684  pop     r12
0x14000e686  pop     rdi
0x14000e687  pop     rsi
0x14000e688  pop     rbp
0x14000e689  pop     rbx
0x14000e68a  retn
```
