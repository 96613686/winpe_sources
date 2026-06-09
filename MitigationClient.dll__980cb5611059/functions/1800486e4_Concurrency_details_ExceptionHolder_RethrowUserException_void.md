# Concurrency::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x1800486e4`
- end: `0x180048726`
- name: `?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall __noreturn(Concurrency::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180048c20`
- `0x180059e45`

## callees

- `0x1800486e4`
- `0x180048e94`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004870a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18004870a`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004871f`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18004871f`

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
  JUMPOUT(0x180048725LL);
}

```

## disassembly

```asm
0x1800486e4  sub     rsp, 38h
0x1800486e8  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x1800486ed  test    eax, eax
0x1800486ef  jnz     short loc_1800486F8
0x1800486f1  mov     eax, 1
0x1800486f6  xchg    eax, [rcx]
0x1800486f8  xorps   xmm0, xmm0
0x1800486fb  movdqu  [rsp+38h+var_18], xmm0
0x180048701  lea     rdx, [rcx+8]
0x180048705  lea     rcx, [rsp+38h+var_18]
0x18004870a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180048710  lea     rax, [rsp+38h+var_18]
0x180048715  mov     [rsp+38h+arg_0], rax
0x18004871a  lea     rcx, [rsp+38h+var_18]
0x18004871f  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
