# Concurrency::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x18002ff04`
- end: `0x18002ff46`
- name: `?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall __noreturn(Concurrency::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180031070`
- `0x180057ee0`

## callees

- `0x18002ff04`
- `0x180031468`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002ff2a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18002ff2a`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002ff3f`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18002ff3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  JUMPOUT(0x18002FF45LL);
}

```

## disassembly

```asm
0x18002ff04  sub     rsp, 38h
0x18002ff08  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18002ff0d  test    eax, eax
0x18002ff0f  jnz     short loc_18002FF18
0x18002ff11  mov     eax, 1
0x18002ff16  xchg    eax, [rcx]
0x18002ff18  xorps   xmm0, xmm0
0x18002ff1b  movdqu  [rsp+38h+var_18], xmm0
0x18002ff21  lea     rdx, [rcx+8]
0x18002ff25  lea     rcx, [rsp+38h+var_18]
0x18002ff2a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18002ff30  lea     rax, [rsp+38h+var_18]
0x18002ff35  mov     [rsp+38h+arg_0], rax
0x18002ff3a  lea     rcx, [rsp+38h+var_18]
0x18002ff3f  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
