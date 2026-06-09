# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x18008cf08`
- end: `0x18008d019`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `273`
- prototype: `void(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008d020`

## callees

- `0x180014a00`
- `0x180014e58`
- `0x180080ed0`
- `0x180082750`
- `0x18008cf08`
- `0x18008eb48`
- `0x1800d9660`
- `0x1800d9a2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008cfbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008cfbd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  std::_Mutex_base *v4; // rbx
  struct Concurrency::details::_CancellationTokenRegistration **v5; // rcx
  char v6; // r14
  struct Concurrency::details::_CancellationTokenRegistration **v7; // rax
  struct Concurrency::details::_CancellationTokenRegistration *v8; // rdx
  unsigned __int32 v9; // eax
  _Mtx_t v10[7]; // [rsp+20h] [rbp-38h] BYREF

  v4 = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  v10[0] = (Concurrency::details::_CancellationTokenState *)((char *)this + 24);
  std::_Mutex_base::lock((Concurrency::details::_CancellationTokenState *)((char *)this + 24));
  v5 = (struct Concurrency::details::_CancellationTokenRegistration **)*((_QWORD *)this + 13);
  if ( v5 )
  {
    v6 = 0;
    v7 = 0;
    while ( v5 )
    {
      v8 = v5[1];
      if ( *v5 == a2 )
      {
        if ( v7 )
          v7[1] = v8;
        else
          *((_QWORD *)this + 13) = v8;
        if ( !v5[1] )
          *((_QWORD *)this + 14) = v7;
        operator delete(v5);
        break;
      }
      v7 = v5;
      v5 = (struct Concurrency::details::_CancellationTokenRegistration **)v5[1];
    }
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    Concurrency::details::_RefCounter::_Release(a2);
  }
  else
  {
    v6 = 1;
  }
  std::_Mutex_base::unlock(v4);
  if ( v6 )
  {
    v9 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v9 >= 2
      && v9 - 2 >= 2
      && v9 != GetCurrentThreadId()
      && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
    {
      *(_OWORD *)v10 = 0;
      std::unique_lock<std::mutex>::unique_lock<std::mutex>(v10, (char *)a2 + 96);
      while ( !*((_BYTE *)a2 + 176) )
        Cnd_wait((struct Concurrency::details::_CancellationTokenRegistration *)((char *)a2 + 24), v10[0]);
      std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v10);
    }
  }
}

```

## disassembly

```asm
0x18008cf08  mov     [rsp+arg_10], rbx
0x18008cf0d  push    rbp
0x18008cf0e  push    rsi
0x18008cf0f  push    rdi
0x18008cf10  push    r12
0x18008cf12  push    r14
0x18008cf14  sub     rsp, 30h
0x18008cf18  mov     rdi, rdx
0x18008cf1b  mov     rbp, rcx
0x18008cf1e  lea     rbx, [rcx+18h]
0x18008cf22  mov     [rsp+58h+var_38], rbx
0x18008cf27  mov     rcx, rbx; this
0x18008cf2a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18008cf2f  nop
0x18008cf30  mov     rcx, [rbp+68h]; Block
0x18008cf34  mov     esi, 2
0x18008cf39  lea     r12d, [rsi-1]
0x18008cf3d  test    rcx, rcx
0x18008cf40  jnz     short loc_18008CF47
0x18008cf42  mov     r14b, r12b
0x18008cf45  jmp     short loc_18008CF8F
0x18008cf47  xor     r14b, r14b
0x18008cf4a  xor     eax, eax
0x18008cf4c  test    rcx, rcx
0x18008cf4f  jz      short loc_18008CF81
0x18008cf51  mov     rdx, [rcx+8]
0x18008cf55  cmp     [rcx], rdi
0x18008cf58  jz      short loc_18008CF62
0x18008cf5a  mov     rax, rcx
0x18008cf5d  mov     rcx, rdx
0x18008cf60  jmp     short loc_18008CF4C
0x18008cf62  test    rax, rax
0x18008cf65  jnz     short loc_18008CF6D
0x18008cf67  mov     [rbp+68h], rdx
0x18008cf6b  jmp     short loc_18008CF71
0x18008cf6d  mov     [rax+8], rdx
0x18008cf71  cmp     qword ptr [rcx+8], 0
0x18008cf76  jnz     short loc_18008CF7C
0x18008cf78  mov     [rbp+70h], rax
0x18008cf7c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008cf81  mov     eax, esi
0x18008cf83  xchg    eax, [rdi+10h]
0x18008cf86  mov     rcx, rdi; this
0x18008cf89  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18008cf8e  nop
0x18008cf8f  mov     rcx, rbx; this
0x18008cf92  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x18008cf97  test    r14b, r14b
0x18008cf9a  jz      short loc_18008D008
0x18008cf9c  xor     eax, eax
0x18008cf9e  lock cmpxchg [rdi+10h], r12d
0x18008cfa4  mov     ebx, eax
0x18008cfa6  jz      short loc_18008D008
0x18008cfa8  mov     edx, eax
0x18008cfaa  test    eax, eax
0x18008cfac  jz      short loc_18008D008
0x18008cfae  sub     edx, 1
0x18008cfb1  jz      short loc_18008D008
0x18008cfb3  sub     edx, 1
0x18008cfb6  jz      short loc_18008D008
0x18008cfb8  cmp     edx, 1
0x18008cfbb  jz      short loc_18008D008
0x18008cfbd  call    cs:__imp_GetCurrentThreadId
0x18008cfc3  cmp     ebx, eax
0x18008cfc5  jz      short loc_18008D008
0x18008cfc7  xchg    esi, [rdi+10h]
0x18008cfca  cmp     esi, 3
0x18008cfcd  jz      short loc_18008D008
0x18008cfcf  xorps   xmm0, xmm0
0x18008cfd2  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18008cfd7  lea     rdx, [rdi+60h]
0x18008cfdb  lea     rcx, [rsp+58h+var_38]
0x18008cfe0  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18008cfe5  jmp     short loc_18008CFF5
0x18008cfe7  mov     rdx, [rsp+58h+var_38]; _Mtx_t
0x18008cfec  lea     rcx, [rdi+18h]; _Cnd_t
0x18008cff0  call    _Cnd_wait
0x18008cff5  cmp     byte ptr [rdi+0B0h], 0
0x18008cffc  jz      short loc_18008CFE7
0x18008cffe  lea     rcx, [rsp+58h+var_38]
0x18008d003  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18008d008  mov     rbx, [rsp+58h+arg_10]
0x18008d00d  add     rsp, 30h
0x18008d011  pop     r14
0x18008d013  pop     r12
0x18008d015  pop     rdi
0x18008d016  pop     rsi
0x18008d017  pop     rbp
0x18008d018  retn
```
