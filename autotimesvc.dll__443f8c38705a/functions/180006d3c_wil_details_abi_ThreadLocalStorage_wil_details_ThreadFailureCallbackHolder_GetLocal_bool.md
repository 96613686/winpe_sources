# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180006d3c`
- end: `0x180006d92`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006864`

## callees

- `0x180006d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d49`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d49`

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
0x180006d3c  push    rbx
0x180006d3e  sub     rsp, 20h
0x180006d42  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006d49  call    cs:__imp_GetCurrentThreadId
0x180006d4f  mov     r8d, eax
0x180006d52  mov     r9d, eax
0x180006d55  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006d5f  shr     r8, 2
0x180006d63  mul     r8
0x180006d66  shr     rdx, 3
0x180006d6a  lea     rcx, [rdx+rdx*4]
0x180006d6e  add     rcx, rcx
0x180006d71  sub     r8, rcx
0x180006d74  mov     rax, [rbx+r8*8]
0x180006d78  test    rax, rax
0x180006d7b  jz      short loc_180006D8C
0x180006d7d  cmp     [rax], r9d
0x180006d80  jz      short loc_180006D88
0x180006d82  mov     rax, [rax+8]
0x180006d86  jmp     short loc_180006D78
0x180006d88  add     rax, 10h
0x180006d8c  add     rsp, 20h
0x180006d90  pop     rbx
0x180006d91  retn
```
