# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007f8c`
- end: `0x180007fe2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007aa4`

## callees

- `0x180007f8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f99`

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
0x180007f8c  push    rbx
0x180007f8e  sub     rsp, 20h
0x180007f92  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007f99  call    cs:__imp_GetCurrentThreadId
0x180007f9f  mov     r8d, eax
0x180007fa2  mov     r9d, eax
0x180007fa5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007faf  shr     r8, 2
0x180007fb3  mul     r8
0x180007fb6  shr     rdx, 3
0x180007fba  lea     rcx, [rdx+rdx*4]
0x180007fbe  add     rcx, rcx
0x180007fc1  sub     r8, rcx
0x180007fc4  mov     rax, [rbx+r8*8]
0x180007fc8  test    rax, rax
0x180007fcb  jz      short loc_180007FDC
0x180007fcd  cmp     [rax], r9d
0x180007fd0  jz      short loc_180007FD8
0x180007fd2  mov     rax, [rax+8]
0x180007fd6  jmp     short loc_180007FC8
0x180007fd8  add     rax, 10h
0x180007fdc  add     rsp, 20h
0x180007fe0  pop     rbx
0x180007fe1  retn
```
