# pplx::details::_ExceptionHolder::_RethrowUserException(void)

- ea: `0x18009066c`
- end: `0x1800906b3`
- name: `?_RethrowUserException@_ExceptionHolder@details@pplx@@QEAAXXZ`
- size: `71`
- prototype: `void __fastcall __noreturn(pplx::details::_ExceptionHolder *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180090fe0`
- `0x1800ba1fe`

## callees

- `0x18009066c`
- `0x18009367c`
- `0x1800941b8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009069c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009069c`

## pseudocode

```c
void __fastcall __noreturn pplx::details::_ExceptionHolder::_RethrowUserException(
        pplx::details::_ExceptionHolder *this)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF

  if ( !(unsigned int)std::_Atomic_storage<long,4>::load(this, 5) )
    _InterlockedExchange((volatile __int32 *)this, 1);
  v2 = 0;
  __ExceptionPtrCopy(&v2, (char *)this + 8);
  std::rethrow_exception(&v2);
  JUMPOUT(0x1800906B2LL);
}

```

## disassembly

```asm
0x18009066c  push    rbx
0x18009066e  sub     rsp, 30h
0x180090672  mov     edx, 5
0x180090677  mov     rbx, rcx
0x18009067a  call    ?load@?$_Atomic_storage@J$03@std@@QEBAJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::load(std::memory_order)
0x18009067f  test    eax, eax
0x180090681  jnz     short loc_18009068A
0x180090683  mov     eax, 1
0x180090688  xchg    eax, [rbx]
0x18009068a  xorps   xmm0, xmm0
0x18009068d  lea     rdx, [rbx+8]
0x180090691  lea     rcx, [rsp+38h+var_18]
0x180090696  movdqu  [rsp+38h+var_18], xmm0
0x18009069c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800906a3  nop     dword ptr [rax+rax+00h]
0x1800906a8  lea     rcx, [rsp+38h+var_18]
0x1800906ad  call    ?rethrow_exception@std@@YAXVexception_ptr@1@@Z; std::rethrow_exception(std::exception_ptr)
```
