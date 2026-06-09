# pplx::details::_CancellationTokenRegistration::_Invoke(void)

- ea: `0x18001501c`
- end: `0x18001507c`
- name: `?_Invoke@_CancellationTokenRegistration@details@pplx@@AEAAXXZ`
- size: `96`
- prototype: `void __fastcall(pplx::details::_CancellationTokenRegistration *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800150ec`
- `0x18001c308`

## callees

- `0x18001501c`
- `0x180015320`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015064`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015064`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015029`

## pseudocode

```c
void __fastcall pplx::details::_CancellationTokenRegistration::_Invoke(
        pplx::details::_CancellationTokenRegistration *this)
{
  DWORD CurrentThreadId; // edi
  signed __int32 v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 4, CurrentThreadId, 0) )
  {
    (*(void (__fastcall **)(pplx::details::_CancellationTokenRegistration *))(*(_QWORD *)this + 16LL))(this);
    v3 = _InterlockedCompareExchange((volatile signed __int32 *)this + 4, 3, CurrentThreadId);
    if ( CurrentThreadId != v3 )
      CurrentThreadId = v3;
    if ( CurrentThreadId == 2 )
      SetEvent(**((HANDLE **)this + 3));
  }
  pplx::details::_RefCounter::_Release(this);
}

```

## disassembly

```asm
0x18001501c  mov     [rsp+arg_8], rbx
0x180015021  push    rdi
0x180015022  sub     rsp, 20h
0x180015026  mov     rbx, rcx
0x180015029  call    cs:__imp_GetCurrentThreadId
0x18001502f  mov     edi, eax
0x180015031  xor     eax, eax
0x180015033  lock cmpxchg [rbx+10h], edi
0x180015038  jnz     short loc_18001506A
0x18001503a  mov     rax, [rbx]
0x18001503d  mov     rcx, rbx
0x180015040  mov     rax, [rax+10h]
0x180015044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015049  mov     ecx, 3
0x18001504e  mov     eax, edi
0x180015050  lock cmpxchg [rbx+10h], ecx
0x180015055  cmovnz  edi, eax
0x180015058  cmp     edi, 2
0x18001505b  jnz     short loc_18001506A
0x18001505d  mov     rcx, [rbx+18h]
0x180015061  mov     rcx, [rcx]; hEvent
0x180015064  call    cs:__imp_SetEvent
0x18001506a  mov     rcx, rbx; this
0x18001506d  mov     rbx, [rsp+28h+arg_8]
0x180015072  add     rsp, 20h
0x180015076  pop     rdi
0x180015077  jmp     ?_Release@_RefCounter@details@pplx@@QEAAJXZ; pplx::details::_RefCounter::_Release(void)
```
