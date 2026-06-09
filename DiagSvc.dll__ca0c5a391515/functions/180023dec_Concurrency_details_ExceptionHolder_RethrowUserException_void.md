# Concurrency::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x180023dec`
- end: `0x180023e2e`
- name: `?_RethrowUserException@_ExceptionHolder@details@Concurrency@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall __noreturn(Concurrency::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800244b0`
- `0x180026db2`

## callees

- `0x180023dec`
- `0x180024828`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180023e27`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180023e27`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023e12`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180023e12`

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
  JUMPOUT(0x180023E2DLL);
}

```

## disassembly

```asm
0x180023dec  sub     rsp, 38h
0x180023df0  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x180023df5  test    eax, eax
0x180023df7  jnz     short loc_180023E00
0x180023df9  mov     eax, 1
0x180023dfe  xchg    eax, [rcx]
0x180023e00  xorps   xmm0, xmm0
0x180023e03  movdqu  [rsp+38h+var_18], xmm0
0x180023e09  lea     rdx, [rcx+8]
0x180023e0d  lea     rcx, [rsp+38h+var_18]
0x180023e12  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180023e18  lea     rax, [rsp+38h+var_18]
0x180023e1d  mov     [rsp+38h+arg_0], rax
0x180023e22  lea     rcx, [rsp+38h+var_18]
0x180023e27  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
