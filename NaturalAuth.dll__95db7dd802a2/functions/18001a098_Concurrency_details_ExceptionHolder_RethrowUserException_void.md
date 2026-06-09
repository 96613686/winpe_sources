# Concurrency::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x18001a098`
- end: `0x18001a0da`
- name: `?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall __noreturn(Concurrency::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001acd0`
- `0x180043184`

## callees

- `0x18001a098`
- `0x18001b74c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001a0d3`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001a0d3`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001a0be`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001a0be`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn Concurrency::details::_ExceptionHolder::_RethrowUserException(
        Concurrency::details::_ExceptionHolder *this)
{
  volatile __int32 *v1; // rcx
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned int)std::_Atomic_storage<enum NA_RULE_STATE,4>::load(this) )
    _InterlockedExchange(v1, 1);
  v2 = 0;
  __ExceptionPtrCopy(&v2, (const void *)(v1 + 2));
  __ExceptionPtrRethrow(&v2);
  JUMPOUT(0x18001A0D9LL);
}

```

## disassembly

```asm
0x18001a098  sub     rsp, 38h
0x18001a09c  call    ?load@?$_Atomic_storage@W4NA_RULE_STATE@@$03@std@@QEBA?AW4NA_RULE_STATE@@W4memory_order@2@@Z; std::_Atomic_storage<NA_RULE_STATE,4>::load(std::memory_order)
0x18001a0a1  test    eax, eax
0x18001a0a3  jnz     short loc_18001A0AC
0x18001a0a5  mov     eax, 1
0x18001a0aa  xchg    eax, [rcx]
0x18001a0ac  xorps   xmm0, xmm0
0x18001a0af  movdqu  [rsp+38h+var_18], xmm0
0x18001a0b5  lea     rdx, [rcx+8]
0x18001a0b9  lea     rcx, [rsp+38h+var_18]
0x18001a0be  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001a0c4  lea     rax, [rsp+38h+var_18]
0x18001a0c9  mov     [rsp+38h+arg_0], rax
0x18001a0ce  lea     rcx, [rsp+38h+var_18]
0x18001a0d3  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
