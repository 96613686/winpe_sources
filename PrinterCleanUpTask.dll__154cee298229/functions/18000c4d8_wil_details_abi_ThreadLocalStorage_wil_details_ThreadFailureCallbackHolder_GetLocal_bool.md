# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000c4d8`
- end: `0x18000c52e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c1f0`

## callees

- `0x18000c4d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c4e5`

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
0x18000c4d8  push    rbx
0x18000c4da  sub     rsp, 20h
0x18000c4de  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c4e5  call    cs:__imp_GetCurrentThreadId
0x18000c4eb  mov     r8d, eax
0x18000c4ee  mov     r9d, eax
0x18000c4f1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c4fb  shr     r8, 2
0x18000c4ff  mul     r8
0x18000c502  shr     rdx, 3
0x18000c506  lea     rcx, [rdx+rdx*4]
0x18000c50a  add     rcx, rcx
0x18000c50d  sub     r8, rcx
0x18000c510  mov     rax, [rbx+r8*8]
0x18000c514  test    rax, rax
0x18000c517  jz      short loc_18000C528
0x18000c519  cmp     [rax], r9d
0x18000c51c  jz      short loc_18000C524
0x18000c51e  mov     rax, [rax+8]
0x18000c522  jmp     short loc_18000C514
0x18000c524  add     rax, 10h
0x18000c528  add     rsp, 20h
0x18000c52c  pop     rbx
0x18000c52d  retn
```
