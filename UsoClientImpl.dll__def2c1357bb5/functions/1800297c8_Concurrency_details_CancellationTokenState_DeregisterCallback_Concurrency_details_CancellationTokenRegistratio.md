# Concurrency::details::_CancellationTokenState::_DeregisterCallback(Concurrency::details::_CancellationTokenRegistration *)

- ea: `0x1800297c8`
- end: `0x1800299c0`
- name: `?_DeregisterCallback@_CancellationTokenState@details@Concurrency@@QEAAXPEAV_CancellationTokenRegistration@23@@Z`
- size: `504`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenState *__hidden this, struct Concurrency::details::_CancellationTokenRegistration *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800299c8`

## callees

- `0x1800297c8`
- `0x180036d78`
- `0x180036ed8`
- `0x1800563c8`
- `0x180056a08`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002989b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002997d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002989b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002997d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800298df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029944`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800298df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029944`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002993a`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002993a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback(
        Concurrency::details::_CancellationTokenState *this,
        struct Concurrency::details::_CancellationTokenRegistration *a2)
{
  char v4; // r14
  char *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rdx
  unsigned __int32 v10; // eax
  int v11; // eax
  int v12; // eax

  v4 = 0;
  v5 = (char *)this + 24;
  if ( (unsigned int)mtx_do_lock((char *)this + 24) )
    goto LABEL_37;
  if ( *((_DWORD *)v5 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v5 + 19) = 2147483646;
    goto LABEL_36;
  }
  v6 = (_QWORD *)*((_QWORD *)this + 13);
  if ( v6 )
  {
    v7 = 0;
    while ( 1 )
    {
      v8 = v6[1];
      if ( (struct Concurrency::details::_CancellationTokenRegistration *)*v6 == a2 )
        break;
      v7 = v6;
      v6 = (_QWORD *)v6[1];
      if ( !v8 )
        goto LABEL_15;
    }
    if ( v7 )
      v7[1] = v8;
    else
      *((_QWORD *)this + 13) = v8;
    if ( !v6[1] )
      *((_QWORD *)this + 14) = v7;
    operator delete(v6);
LABEL_15:
    _InterlockedExchange((volatile __int32 *)a2 + 4, 2);
    if ( !_InterlockedDecrement((volatile signed __int32 *)a2 + 2) )
      (*(void (__fastcall **)(struct Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  else
  {
    v4 = 1;
  }
  if ( (*((_DWORD *)v5 + 19))-- == 1 )
  {
    *((_DWORD *)v5 + 18) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)v5 + 2);
  }
  if ( v4 )
  {
    v10 = _InterlockedCompareExchange((volatile signed __int32 *)a2 + 4, 1, 0);
    if ( v10 >= 2
      && v10 - 2 >= 2
      && v10 != GetCurrentThreadId()
      && _InterlockedExchange((volatile __int32 *)a2 + 4, 2) != 3 )
    {
      if ( !(unsigned int)mtx_do_lock((char *)a2 + 96) )
      {
        v11 = *((_DWORD *)a2 + 43);
        if ( v11 == 0x7FFFFFFF )
        {
          *((_DWORD *)a2 + 43) = 2147483646;
LABEL_36:
          std::_Throw_Cpp_error(6);
        }
        while ( !*((_BYTE *)a2 + 176) )
        {
          *((_DWORD *)a2 + 42) = -1;
          --*((_DWORD *)a2 + 43);
          if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)a2 + 4, (PSRWLOCK)a2 + 14, 0xFFFFFFFF, 0) )
            abort();
          *((_DWORD *)a2 + 42) = GetCurrentThreadId();
          v11 = *((_DWORD *)a2 + 43) + 1;
          *((_DWORD *)a2 + 43) = v11;
        }
        v12 = v11 - 1;
        *((_DWORD *)a2 + 43) = v12;
        if ( !v12 )
        {
          *((_DWORD *)a2 + 42) = -1;
          ReleaseSRWLockExclusive((PSRWLOCK)a2 + 14);
        }
        return;
      }
LABEL_37:
      std::_Throw_Cpp_error(5);
    }
  }
}

```

## disassembly

```asm
0x1800297c8  mov     [rsp+arg_10], rbx
0x1800297cd  mov     [rsp+arg_18], rbp
0x1800297d2  push    rsi
0x1800297d3  push    rdi
0x1800297d4  push    r12
0x1800297d6  push    r13
0x1800297d8  push    r14
0x1800297da  sub     rsp, 30h
0x1800297de  mov     rdi, rdx
0x1800297e1  mov     rsi, rcx
0x1800297e4  xor     r14b, r14b
0x1800297e7  lea     rbx, [rcx+18h]
0x1800297eb  mov     [rsp+58h+var_30], rbx
0x1800297f0  mov     rcx, rbx
0x1800297f3  call    mtx_do_lock
0x1800297f8  test    eax, eax
0x1800297fa  jnz     loc_1800299B5
0x180029800  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x180029807  jnz     short loc_180029815
0x180029809  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x180029810  jmp     loc_1800299AA
0x180029815  mov     rcx, [rsi+68h]; Block
0x180029819  mov     ebp, 2
0x18002981e  lea     r13d, [rbp-1]
0x180029822  or      r12d, 0FFFFFFFFh
0x180029826  test    rcx, rcx
0x180029829  jz      short loc_18002988A
0x18002982b  xor     eax, eax
0x18002982d  mov     rdx, [rcx+8]
0x180029831  cmp     [rcx], rdi
0x180029834  jz      short loc_180029843
0x180029836  mov     rax, rcx
0x180029839  mov     rcx, rdx
0x18002983c  test    rdx, rdx
0x18002983f  jnz     short loc_18002982D
0x180029841  jmp     short loc_180029867
0x180029843  test    rax, rax
0x180029846  jnz     short loc_18002984E
0x180029848  mov     [rsi+68h], rdx
0x18002984c  jmp     short loc_180029852
0x18002984e  mov     [rax+8], rdx
0x180029852  cmp     qword ptr [rcx+8], 0
0x180029857  jnz     short loc_18002985D
0x180029859  mov     [rsi+70h], rax
0x18002985d  mov     edx, 10h
0x180029862  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029867  mov     eax, ebp
0x180029869  xchg    eax, [rdi+10h]
0x18002986c  mov     eax, r12d
0x18002986f  lock xadd [rdi+8], eax
0x180029874  add     eax, r12d
0x180029877  jnz     short loc_18002988D
0x180029879  mov     rax, [rdi]
0x18002987c  mov     rcx, rdi
0x18002987f  mov     rax, [rax+8]
0x180029883  call    _guard_dispatch_icall
0x180029888  jmp     short loc_18002988D
0x18002988a  mov     r14b, r13b
0x18002988d  add     [rbx+4Ch], r12d
0x180029891  jnz     short loc_1800298A1
0x180029893  mov     [rbx+48h], r12d
0x180029897  lea     rcx, [rbx+10h]; SRWLock
0x18002989b  call    cs:__imp_ReleaseSRWLockExclusive
0x1800298a1  test    r14b, r14b
0x1800298a4  jz      loc_180029983
0x1800298aa  xor     eax, eax
0x1800298ac  lock cmpxchg [rdi+10h], r13d
0x1800298b2  mov     ebx, eax
0x1800298b4  jz      loc_180029983
0x1800298ba  mov     edx, eax
0x1800298bc  test    eax, eax
0x1800298be  jz      loc_180029983
0x1800298c4  sub     edx, 1
0x1800298c7  jz      loc_180029983
0x1800298cd  sub     edx, 1
0x1800298d0  jz      loc_180029983
0x1800298d6  cmp     edx, 1
0x1800298d9  jz      loc_180029983
0x1800298df  call    cs:__imp_GetCurrentThreadId
0x1800298e5  cmp     ebx, eax
0x1800298e7  jz      loc_180029983
0x1800298ed  xchg    ebp, [rdi+10h]
0x1800298f0  cmp     ebp, 3
0x1800298f3  jz      loc_180029983
0x1800298f9  lea     rcx, [rdi+60h]
0x1800298fd  call    mtx_do_lock
0x180029902  test    eax, eax
0x180029904  jnz     loc_1800299B5
0x18002990a  mov     eax, [rdi+0ACh]
0x180029910  cmp     eax, 7FFFFFFFh
0x180029915  jz      loc_1800299A0
0x18002991b  jmp     short loc_18002995E
0x18002991d  mov     [rdi+0A8h], r12d
0x180029924  add     [rdi+0ACh], r12d
0x18002992b  xor     r9d, r9d; Flags
0x18002992e  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180029932  lea     rdx, [rdi+70h]; SRWLock
0x180029936  lea     rcx, [rdi+20h]; ConditionVariable
0x18002993a  call    cs:__imp_SleepConditionVariableSRW
0x180029940  test    eax, eax
0x180029942  jz      short loc_18002999A
0x180029944  call    cs:__imp_GetCurrentThreadId
0x18002994a  mov     [rdi+0A8h], eax
0x180029950  mov     eax, [rdi+0ACh]
0x180029956  inc     eax
0x180029958  mov     [rdi+0ACh], eax
0x18002995e  cmp     byte ptr [rdi+0B0h], 0
0x180029965  jz      short loc_18002991D
0x180029967  sub     eax, 1
0x18002996a  mov     [rdi+0ACh], eax
0x180029970  jnz     short loc_180029983
0x180029972  mov     [rdi+0A8h], r12d
0x180029979  lea     rcx, [rdi+70h]; SRWLock
0x18002997d  call    cs:__imp_ReleaseSRWLockExclusive
0x180029983  mov     rbx, [rsp+58h+arg_10]
0x180029988  mov     rbp, [rsp+58h+arg_18]
0x18002998d  add     rsp, 30h
0x180029991  pop     r14
0x180029993  pop     r13
0x180029995  pop     r12
0x180029997  pop     rdi
0x180029998  pop     rsi
0x180029999  retn
0x18002999a  call    abort
0x1800299a0  mov     dword ptr [rdi+0ACh], 7FFFFFFEh
0x1800299aa  mov     ecx, 6; int
0x1800299af  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x1800299b5  mov     ecx, 5; int
0x1800299ba  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
