# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800275e0`
- end: `0x180027636`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800273c8`

## callees

- `0x1800275e0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800275ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800275ed`

## pseudocode

```c
__int64 wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal()
{
  __int64 v0; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 result; // rax

  v0 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(v0 + 8 * (((unsigned __int64)CurrentThreadId >> 2) % 0xA));
        result;
        result = *(_QWORD *)(result + 8) )
  {
    if ( *(_DWORD *)result == CurrentThreadId )
    {
      result += 16;
      return result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800275e0  push    rbx
0x1800275e2  sub     rsp, 20h
0x1800275e6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800275ed  call    cs:__imp_GetCurrentThreadId
0x1800275f3  mov     r8d, eax
0x1800275f6  mov     r9d, eax
0x1800275f9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180027603  shr     r8, 2
0x180027607  mul     r8
0x18002760a  shr     rdx, 3
0x18002760e  lea     rcx, [rdx+rdx*4]
0x180027612  add     rcx, rcx
0x180027615  sub     r8, rcx
0x180027618  mov     rax, [rbx+r8*8]
0x18002761c  test    rax, rax
0x18002761f  jz      short loc_180027630
0x180027621  cmp     [rax], r9d
0x180027624  jz      short loc_18002762C
0x180027626  mov     rax, [rax+8]
0x18002762a  jmp     short loc_18002761C
0x18002762c  add     rax, 10h
0x180027630  add     rsp, 20h
0x180027634  pop     rbx
0x180027635  retn
```
