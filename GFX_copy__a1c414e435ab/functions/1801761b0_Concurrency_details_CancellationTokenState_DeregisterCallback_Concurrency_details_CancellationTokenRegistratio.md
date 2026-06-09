# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x1801761b0`
- end: `0x1801762d0`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `288`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800fb634`

## callees

- `0x18001ffb4`
- `0x1800795a0`
- `0x18015a340`
- `0x18015e034`
- `0x1801761b0`
- `0x1801762d0`

## import_xrefs

- `MSVCP140!_Cnd_wait` at `0x18017629e`
- `MSVCP140!_Cnd_wait` at `0x18017629e`
- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180176273`
- `MSVCP140!?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ` at `0x180176273`
- `MSVCP140!_Mtx_unlock` at `0x180176243`
- `MSVCP140!_Mtx_unlock` at `0x180176243`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char v4; // r14
  struct _Mtx_internal_imp_t *v5; // rbx
  struct Concurrency::details::_CancellationTokenRegistration **v6; // rcx
  struct Concurrency::details::_CancellationTokenRegistration **v7; // rax
  struct Concurrency::details::_CancellationTokenRegistration ***v8; // rdx
  struct Concurrency::details::_CancellationTokenRegistration **v9; // r8
  signed __int32 v10; // eax
  unsigned int v11; // ebx
  Concurrency::details::platform *v12; // rcx
  _Mtx_t v13[5]; // [rsp+20h] [rbp-28h] BYREF

  v4 = 0;
  v5 = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  v6 = (struct Concurrency::details::_CancellationTokenRegistration **)*((_QWORD *)this + 13);
  if ( v6 )
  {
    v7 = 0;
    while ( v6 )
    {
      v8 = (struct Concurrency::details::_CancellationTokenRegistration ***)(v6 + 1);
      if ( *v6 == a2 )
      {
        v9 = *v8;
        if ( v7 )
          v7[1] = (struct Concurrency::details::_CancellationTokenRegistration *)v9;
        else
          *((_QWORD *)this + 13) = v9;
        if ( !*v8 )
          *((_QWORD *)this + 14) = v7;
        operator delete(v6);
        break;
      }
      v7 = v6;
      v6 = *v8;
    }
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    Concurrency::details::_RefCounter::_Release(a2);
  }
  else
  {
    v4 = 1;
  }
  _Mtx_unlock(v5);
  if ( v4 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    v11 = 0;
    if ( v10 )
      v11 = v10;
    if ( v11 >= 2 )
    {
      v12 = (Concurrency::details::platform *)(v11 - 2);
      if ( (unsigned int)v12 >= 2
        && v11 != Concurrency::details::platform::GetCurrentThreadId(v12)
        && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
      {
        std::unique_lock<std::mutex>::unique_lock<std::mutex>(v13, (char *)a2 + 96);
        while ( !*((_BYTE *)a2 + 176) )
          _Cnd_wait((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24), v13[0]);
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v13);
      }
    }
  }
}

```

## disassembly

```asm
0x1801761b0  mov     rax, rsp
0x1801761b3  mov     [rax+10h], rbx
0x1801761b7  mov     [rax+18h], rbp
0x1801761bb  mov     [rax+20h], rsi
0x1801761bf  push    rdi
0x1801761c0  push    r12
0x1801761c2  push    r14
0x1801761c4  sub     rsp, 30h
0x1801761c8  mov     rdi, rdx
0x1801761cb  mov     rbp, rcx
0x1801761ce  xor     r14b, r14b
0x1801761d1  lea     rbx, [rcx+18h]
0x1801761d5  mov     [rax+8], rbx
0x1801761d9  mov     rcx, rbx; this
0x1801761dc  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801761e1  mov     rcx, [rbp+68h]; void *
0x1801761e5  mov     esi, 2
0x1801761ea  lea     r12d, [rsi-1]
0x1801761ee  test    rcx, rcx
0x1801761f1  jnz     short loc_1801761F8
0x1801761f3  mov     r14b, r12b
0x1801761f6  jmp     short loc_180176240
0x1801761f8  xor     eax, eax
0x1801761fa  test    rcx, rcx
0x1801761fd  jz      short loc_180176231
0x1801761ff  lea     rdx, [rcx+8]
0x180176203  cmp     [rcx], rdi
0x180176206  jz      short loc_180176210
0x180176208  mov     rax, rcx
0x18017620b  mov     rcx, [rdx]
0x18017620e  jmp     short loc_1801761FA
0x180176210  mov     r8, [rdx]
0x180176213  test    rax, rax
0x180176216  jnz     short loc_18017621E
0x180176218  mov     [rbp+68h], r8
0x18017621c  jmp     short loc_180176222
0x18017621e  mov     [rax+8], r8
0x180176222  cmp     qword ptr [rdx], 0
0x180176226  jnz     short loc_18017622C
0x180176228  mov     [rbp+70h], rax
0x18017622c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180176231  mov     eax, esi
0x180176233  xchg    eax, [rdi+10h]
0x180176236  mov     rcx, rdi; this
0x180176239  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18017623e  nop
0x18017623f  nop
0x180176240  mov     rcx, rbx; _Mtx_t
0x180176243  call    cs:__imp__Mtx_unlock
0x180176249  test    r14b, r14b
0x18017624c  jz      short loc_1801762B7
0x18017624e  xor     eax, eax
0x180176250  lock cmpxchg [rdi+10h], r12d
0x180176256  mov     ebx, 0
0x18017625b  cmovnz  ebx, eax
0x18017625e  mov     ecx, ebx
0x180176260  test    ebx, ebx
0x180176262  jz      short loc_1801762B7
0x180176264  sub     ecx, 1
0x180176267  jz      short loc_1801762B7
0x180176269  sub     ecx, 1
0x18017626c  jz      short loc_1801762B7
0x18017626e  cmp     ecx, 1
0x180176271  jz      short loc_1801762B7
0x180176273  call    cs:__imp_?GetCurrentThreadId@platform@details@Concurrency@@YAJXZ; Concurrency::details::platform::GetCurrentThreadId(void)
0x180176279  cmp     ebx, eax
0x18017627b  jz      short loc_1801762B7
0x18017627d  xchg    esi, [rdi+10h]
0x180176280  cmp     esi, 3
0x180176283  jz      short loc_1801762B7
0x180176285  lea     rdx, [rdi+60h]
0x180176289  lea     rcx, [rsp+48h+var_28]
0x18017628e  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180176293  jmp     short loc_1801762A4
0x180176295  mov     rdx, [rsp+48h+var_28]; _Mtx_t
0x18017629a  lea     rcx, [rdi+18h]; _Cnd_t
0x18017629e  call    cs:__imp__Cnd_wait
0x1801762a4  cmp     byte ptr [rdi+0B0h], 0
0x1801762ab  jz      short loc_180176295
0x1801762ad  lea     rcx, [rsp+48h+var_28]
0x1801762b2  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801762b7  mov     rbx, [rsp+48h+arg_8]
0x1801762bc  mov     rbp, [rsp+48h+arg_10]
0x1801762c1  mov     rsi, [rsp+48h+arg_18]
0x1801762c6  add     rsp, 30h
0x1801762ca  pop     r14
0x1801762cc  pop     r12
0x1801762ce  pop     rdi
0x1801762cf  retn
```
