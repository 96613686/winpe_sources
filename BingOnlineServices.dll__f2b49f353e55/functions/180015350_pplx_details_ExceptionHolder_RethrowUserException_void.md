# pplx::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x180015350`
- end: `0x180015392`
- name: `?_RethrowUserException@_ExceptionHolder@details@pplx@@QEAAXXZ`
- size: `66`
- prototype: `void __fastcall __noreturn(pplx::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001588c`
- `0x18005a16c`

## callees

- `0x180015350`
- `0x180015bb0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001538b`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18001538b`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015376`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180015376`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn pplx::details::_ExceptionHolder::_RethrowUserException(
        pplx::details::_ExceptionHolder *this)
{
  volatile __int32 *v1; // rcx
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned int)std::_Atomic_storage<long,4>::load(this) )
    _InterlockedExchange(v1, 1);
  v2 = 0;
  __ExceptionPtrCopy(&v2, (const void *)(v1 + 2));
  __ExceptionPtrRethrow(&v2);
  JUMPOUT(0x180015391LL);
}

```

## disassembly

```asm
0x180015350  sub     rsp, 38h
0x180015354  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x180015359  test    eax, eax
0x18001535b  jnz     short loc_180015364
0x18001535d  mov     eax, 1
0x180015362  xchg    eax, [rcx]
0x180015364  xorps   xmm0, xmm0
0x180015367  movdqu  [rsp+38h+var_18], xmm0
0x18001536d  lea     rdx, [rcx+8]
0x180015371  lea     rcx, [rsp+38h+var_18]
0x180015376  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18001537c  lea     rax, [rsp+38h+var_18]
0x180015381  mov     [rsp+38h+arg_0], rax
0x180015386  lea     rcx, [rsp+38h+var_18]
0x18001538b  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
```
