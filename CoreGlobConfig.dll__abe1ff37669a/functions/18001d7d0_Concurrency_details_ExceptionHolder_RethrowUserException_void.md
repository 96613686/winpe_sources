# Concurrency::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x18001d7d0`
- end: `0x18001d812`
- name: `?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall __noreturn(Concurrency::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001df18`
- `0x1800241f2`

## callees

- `0x18001d7d0`
- `0x18001e880`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001d80b`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001d80b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001d7f6`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001d7f6`

## pseudocode

```c
void __fastcall __noreturn Concurrency::details::_ExceptionHolder::_RethrowUserException(
        Concurrency::details::_ExceptionHolder *this)
{
  volatile __int32 *v1; // rcx
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned int)std::_Atomic_storage<long,4>::load(this) )
    _InterlockedExchange(v1, 1);
  v2 = 0;
  __ExceptionPtrCopy(&v2, (const void *)(v1 + 2));
  __ExceptionPtrRethrow(&v2);
  JUMPOUT(0x18001D811LL);
}

```

## disassembly

```asm
0x18001d7d0  sub     rsp, 38h
0x18001d7d4  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18001d7d9  test    eax, eax
0x18001d7db  jnz     short loc_18001D7E4
0x18001d7dd  mov     eax, 1
0x18001d7e2  xchg    eax, [rcx]
0x18001d7e4  xorps   xmm0, xmm0
0x18001d7e7  movdqu  [rsp+38h+var_18], xmm0
0x18001d7ed  lea     rdx, [rcx+8]
0x18001d7f1  lea     rcx, [rsp+38h+var_18]
0x18001d7f6  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001d7fc  lea     rax, [rsp+38h+var_18]
0x18001d801  mov     [rsp+38h+arg_0], rax
0x18001d806  lea     rcx, [rsp+38h+var_18]
0x18001d80b  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
