# _lambda_25492e723f3fb512063019ab9c6aa90a_::operator()(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x18001e74c`
- end: `0x18001e823`
- name: `??R_lambda_25492e723f3fb512063019ab9c6aa90a_@@QEBAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001db70`

## callees

- `0x180001b60`
- `0x18001e6c8`
- `0x18001e74c`
- `0x180037010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001e78a`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18001e78a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e77b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e77b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e7bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e765`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e79f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e765`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e79f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e7d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e7d0`

## pseudocode

```c
void __fastcall _lambda_25492e723f3fb512063019ab9c6aa90a_::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  RTL_SRWLOCK *v4; // rdi
  char v5; // si
  __int64 v6; // rcx
  __int64 v7; // rdx
  const char *v8; // r9
  bool v9; // zf
  struct _TP_TIMER *v10; // rcx
  __int64 v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (RTL_SRWLOCK *)(a3 + 88);
  AcquireSRWLockExclusive((PSRWLOCK)(a3 + 88));
  v5 = 1;
  ++*(_DWORD *)(a3 + 96);
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  try
  {
    v6 = *(_QWORD *)(a3 + 72);
    if ( !v6 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    AcquireSRWLockExclusive(v4);
    v9 = (*(_DWORD *)(a3 + 96))-- == 1;
    if ( !v9 || !*(_BYTE *)(a3 + 100) )
      v5 = 0;
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    if ( v5 )
    {
      v10 = *(struct _TP_TIMER **)(a3 + 80);
      if ( v10 )
        CloseThreadpoolTimer(v10);
      v11 = *(_QWORD *)(a3 + 72);
      if ( v11 )
      {
        LOBYTE(v7) = v11 != a3 + 16;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 32LL))(v11, v7);
        *(_QWORD *)(a3 + 72) = 0;
      }
      wil::details::threadpool_object_context::~threadpool_object_context((wil::details::threadpool_object_context *)a3);
      operator delete((void *)a3, (const struct std::nothrow_t *)0x68);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x180,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      v8);
  }
}

```

## disassembly

```asm
0x18001e74c  mov     [rsp+arg_0], rbx
0x18001e751  mov     [rsp+arg_8], rsi
0x18001e756  push    rdi
0x18001e757  sub     rsp, 20h
0x18001e75b  mov     rbx, r8
0x18001e75e  lea     rdi, [r8+58h]
0x18001e762  mov     rcx, rdi; SRWLock
0x18001e765  call    cs:__imp_AcquireSRWLockExclusive
0x18001e76b  mov     esi, 1
0x18001e770  add     [rbx+60h], esi
0x18001e773  test    rdi, rdi
0x18001e776  jz      short loc_18001E781
0x18001e778  mov     rcx, rdi; SRWLock
0x18001e77b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e781  mov     rcx, [rbx+48h]
0x18001e785  test    rcx, rcx
0x18001e788  jnz     short loc_18001E790
0x18001e78a  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18001e790  mov     rax, [rcx]
0x18001e793  mov     rax, [rax+10h]
0x18001e797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e79c  mov     rcx, rdi; SRWLock
0x18001e79f  call    cs:__imp_AcquireSRWLockExclusive
0x18001e7a5  add     dword ptr [rbx+60h], 0FFFFFFFFh
0x18001e7a9  jnz     short loc_18001E7B1
0x18001e7ab  cmp     byte ptr [rbx+64h], 0
0x18001e7af  jnz     short loc_18001E7B4
0x18001e7b1  xor     sil, sil
0x18001e7b4  test    rdi, rdi
0x18001e7b7  jz      short loc_18001E7C2
0x18001e7b9  mov     rcx, rdi; SRWLock
0x18001e7bc  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e7c2  test    sil, sil
0x18001e7c5  jz      short loc_18001E813
0x18001e7c7  mov     rcx, [rbx+50h]; pti
0x18001e7cb  test    rcx, rcx
0x18001e7ce  jz      short loc_18001E7D6
0x18001e7d0  call    cs:__imp_CloseThreadpoolTimer
0x18001e7d6  lea     rdi, [rbx+10h]
0x18001e7da  mov     rcx, [rdi+38h]
0x18001e7de  test    rcx, rcx
0x18001e7e1  jz      short loc_18001E7FD
0x18001e7e3  mov     rax, [rcx]
0x18001e7e6  cmp     rcx, rdi
0x18001e7e9  setnz   dl
0x18001e7ec  mov     rax, [rax+20h]
0x18001e7f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7f5  mov     qword ptr [rdi+38h], 0
0x18001e7fd  mov     rcx, rbx; this
0x18001e800  call    ??1threadpool_object_context@details@wil@@QEAA@XZ; wil::details::threadpool_object_context::~threadpool_object_context(void)
0x18001e805  mov     edx, 68h ; 'h'; struct std::nothrow_t *
0x18001e80a  mov     rcx, rbx; void *
0x18001e80d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001e812  nop
0x18001e813  mov     rbx, [rsp+28h+arg_0]
0x18001e818  mov     rsi, [rsp+28h+arg_8]
0x18001e81d  add     rsp, 20h
0x18001e821  pop     rdi
0x18001e822  retn
```
