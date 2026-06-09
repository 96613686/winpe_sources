# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000574c`
- end: `0x1800057a2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005280`

## callees

- `0x18000574c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005759`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005759`

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
0x18000574c  push    rbx
0x18000574e  sub     rsp, 20h
0x180005752  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005759  call    cs:__imp_GetCurrentThreadId
0x18000575f  mov     r8d, eax
0x180005762  mov     r9d, eax
0x180005765  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000576f  shr     r8, 2
0x180005773  mul     r8
0x180005776  shr     rdx, 3
0x18000577a  lea     rcx, [rdx+rdx*4]
0x18000577e  add     rcx, rcx
0x180005781  sub     r8, rcx
0x180005784  mov     rax, [rbx+r8*8]
0x180005788  test    rax, rax
0x18000578b  jz      short loc_18000579C
0x18000578d  cmp     [rax], r9d
0x180005790  jz      short loc_180005798
0x180005792  mov     rax, [rax+8]
0x180005796  jmp     short loc_180005788
0x180005798  add     rax, 10h
0x18000579c  add     rsp, 20h
0x1800057a0  pop     rbx
0x1800057a1  retn
```
