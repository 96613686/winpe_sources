# Concurrency::details::_CancellationTokenRegistration::_Invoke(void)

- ea: `0x18008dce8`
- end: `0x18008dd5d`
- name: `?_Invoke@_CancellationTokenRegistration@details@Concurrency@@AEAAXXZ`
- size: `117`
- prototype: `void __fastcall(Concurrency::details::_CancellationTokenRegistration *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18008a07c`
- `0x18008e92c`

## callees

- `0x180014a00`
- `0x180014e58`
- `0x18008dce8`
- `0x18008eb48`
- `0x1800d9a10`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008dcf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008dcf5`

## pseudocode

```c
void __fastcall Concurrency::details::_CancellationTokenRegistration::_Invoke(
        Concurrency::details::_CancellationTokenRegistration *this)
{
  DWORD CurrentThreadId; // ebx
  signed __int32 v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 4, CurrentThreadId, 0) )
  {
    (*(void (__fastcall **)(Concurrency::details::_CancellationTokenRegistration *))(*(_QWORD *)this + 16LL))(this);
    v3 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 3, CurrentThreadId);
    if ( CurrentThreadId != v3 )
      CurrentThreadId = v3;
    if ( CurrentThreadId == 2 )
    {
      std::_Mutex_base::lock((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 96));
      *((_BYTE *)this + 176) = 1;
      std::_Mutex_base::unlock((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 96));
      Cnd_broadcast((Concurrency::details::_CancellationTokenRegistration *)((char *)this + 24));
    }
  }
  Concurrency::details::_RefCounter::_Release(this);
}

```

## disassembly

```asm
0x18008dce8  mov     [rsp+arg_8], rbx
0x18008dced  push    rdi
0x18008dcee  sub     rsp, 20h
0x18008dcf2  mov     rdi, rcx
0x18008dcf5  call    cs:__imp_GetCurrentThreadId
0x18008dcfb  mov     ebx, eax
0x18008dcfd  xor     eax, eax
0x18008dcff  lock cmpxchg [rdi+10h], ebx
0x18008dd04  jnz     short loc_18008DD4B
0x18008dd06  mov     rax, [rdi]
0x18008dd09  mov     rcx, rdi
0x18008dd0c  mov     rax, [rax+10h]
0x18008dd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dd15  mov     ecx, 3
0x18008dd1a  mov     eax, ebx
0x18008dd1c  lock cmpxchg [rdi+10h], ecx
0x18008dd21  cmovnz  ebx, eax
0x18008dd24  cmp     ebx, 2
0x18008dd27  jnz     short loc_18008DD4B
0x18008dd29  lea     rcx, [rdi+60h]; this
0x18008dd2d  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18008dd32  lea     rcx, [rdi+60h]; this
0x18008dd36  mov     byte ptr [rdi+0B0h], 1
0x18008dd3d  call    ?unlock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::unlock(void)
0x18008dd42  lea     rcx, [rdi+18h]; _Cnd_t
0x18008dd46  call    _Cnd_broadcast
0x18008dd4b  mov     rcx, rdi; this
0x18008dd4e  mov     rbx, [rsp+28h+arg_8]
0x18008dd53  add     rsp, 20h
0x18008dd57  pop     rdi
0x18008dd58  jmp     ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
```
