# Concurrency::details::_TaskCollectionBaseImpl::_Wait(void)

- ea: `0x18002c6a4`
- end: `0x18002c77b`
- name: `?_Wait@_TaskCollectionBaseImpl@details@Concurrency@@QEAAXXZ`
- size: `215`
- prototype: `void __fastcall(Concurrency::details::_TaskCollectionBaseImpl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18002c7ec`

## callees

- `0x18002c6a4`
- `0x180036d78`
- `0x180036ed8`
- `0x1800563c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c73f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c73f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c703`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002c6f9`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18002c6f9`

## pseudocode

```c
void __fastcall Concurrency::details::_TaskCollectionBaseImpl::_Wait(
        Concurrency::details::_TaskCollectionBaseImpl *this)
{
  int v2; // eax
  int v3; // eax

  if ( (unsigned int)mtx_do_lock((char *)this + 72) )
    std::_Throw_Cpp_error(5);
  v2 = *((_DWORD *)this + 37);
  if ( v2 == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 37) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  while ( *((int *)this + 44) < 2 )
  {
    --*((_DWORD *)this + 37);
    *((_DWORD *)this + 36) = -1;
    if ( !SleepConditionVariableSRW((PCONDITION_VARIABLE)this + 1, (PSRWLOCK)this + 11, 0xFFFFFFFF, 0) )
      abort();
    *((_DWORD *)this + 36) = GetCurrentThreadId();
    v2 = *((_DWORD *)this + 37) + 1;
    *((_DWORD *)this + 37) = v2;
  }
  v3 = v2 - 1;
  *((_DWORD *)this + 37) = v3;
  if ( !v3 )
  {
    *((_DWORD *)this + 36) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)this + 11);
  }
}

```

## disassembly

```asm
0x18002c6a4  mov     [rsp+arg_8], rbx
0x18002c6a9  mov     [rsp+arg_10], rsi
0x18002c6ae  push    rdi
0x18002c6af  sub     rsp, 20h
0x18002c6b3  mov     rbx, rcx
0x18002c6b6  add     rcx, 48h ; 'H'
0x18002c6ba  call    mtx_do_lock
0x18002c6bf  test    eax, eax
0x18002c6c1  jnz     loc_18002C755
0x18002c6c7  mov     eax, [rbx+94h]
0x18002c6cd  cmp     eax, 7FFFFFFFh
0x18002c6d2  jz      loc_18002C760
0x18002c6d8  jmp     short loc_18002C71D
0x18002c6da  dec     dword ptr [rbx+94h]
0x18002c6e0  lea     rdx, [rbx+58h]; SRWLock
0x18002c6e4  xor     r9d, r9d; Flags
0x18002c6e7  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x18002c6f1  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18002c6f5  lea     rcx, [rbx+8]; ConditionVariable
0x18002c6f9  call    cs:__imp_SleepConditionVariableSRW
0x18002c6ff  test    eax, eax
0x18002c701  jz      short loc_18002C775
0x18002c703  call    cs:__imp_GetCurrentThreadId
0x18002c709  mov     [rbx+90h], eax
0x18002c70f  mov     eax, [rbx+94h]
0x18002c715  inc     eax
0x18002c717  mov     [rbx+94h], eax
0x18002c71d  cmp     dword ptr [rbx+0B0h], 2
0x18002c724  jl      short loc_18002C6DA
0x18002c726  sub     eax, 1
0x18002c729  mov     [rbx+94h], eax
0x18002c72f  jnz     short loc_18002C745
0x18002c731  lea     rcx, [rbx+58h]; SRWLock
0x18002c735  mov     dword ptr [rbx+90h], 0FFFFFFFFh
0x18002c73f  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c745  mov     rbx, [rsp+28h+arg_8]
0x18002c74a  mov     rsi, [rsp+28h+arg_10]
0x18002c74f  add     rsp, 20h
0x18002c753  pop     rdi
0x18002c754  retn
0x18002c755  mov     ecx, 5; int
0x18002c75a  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002c760  mov     ecx, 6; int
0x18002c765  mov     dword ptr [rbx+94h], 7FFFFFFEh
0x18002c76f  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18002c775  call    abort
```
