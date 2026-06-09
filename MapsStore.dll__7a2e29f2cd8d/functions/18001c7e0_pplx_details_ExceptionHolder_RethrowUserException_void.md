# pplx::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x18001c7e0`
- end: `0x18001c822`
- name: `?_RethrowUserException@_ExceptionHolder@details@pplx@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall __noreturn(pplx::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d040`
- `0x18008e515`

## callees

- `0x18001c7e0`
- `0x18001d594`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001c81b`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001c81b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c806`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18001c806`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn pplx::details::_ExceptionHolder::_RethrowUserException(
        pplx::details::_ExceptionHolder *this)
{
  volatile __int32 *v1; // rcx
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned int)std::_Atomic_storage<enum MapControl::NetworkUsagePolicy,4>::load(this) )
    _InterlockedExchange(v1, 1);
  v2 = 0;
  __ExceptionPtrCopy(&v2, (const void *)(v1 + 2));
  __ExceptionPtrRethrow(&v2);
  JUMPOUT(0x18001C821LL);
}

```

## disassembly

```asm
0x18001c7e0  sub     rsp, 38h
0x18001c7e4  call    ?load@?$_Atomic_storage@W4NetworkUsagePolicy@MapControl@@$03@std@@QEBA?AW4NetworkUsagePolicy@MapControl@@W4memory_order@2@@Z; std::_Atomic_storage<MapControl::NetworkUsagePolicy,4>::load(std::memory_order)
0x18001c7e9  test    eax, eax
0x18001c7eb  jnz     short loc_18001C7F4
0x18001c7ed  mov     eax, 1
0x18001c7f2  xchg    eax, [rcx]
0x18001c7f4  xorps   xmm0, xmm0
0x18001c7f7  movdqu  [rsp+38h+var_18], xmm0
0x18001c7fd  lea     rdx, [rcx+8]
0x18001c801  lea     rcx, [rsp+38h+var_18]
0x18001c806  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001c80c  lea     rax, [rsp+38h+var_18]
0x18001c811  mov     [rsp+38h+arg_0], rax
0x18001c816  lea     rcx, [rsp+38h+var_18]
0x18001c81b  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
