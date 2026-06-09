# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000b548`
- end: `0x18000b59e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000affc`

## callees

- `0x18000b548`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b555`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b555`

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
0x18000b548  push    rbx
0x18000b54a  sub     rsp, 20h
0x18000b54e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b555  call    cs:__imp_GetCurrentThreadId
0x18000b55b  mov     r8d, eax
0x18000b55e  mov     r9d, eax
0x18000b561  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b56b  shr     r8, 2
0x18000b56f  mul     r8
0x18000b572  shr     rdx, 3
0x18000b576  lea     rcx, [rdx+rdx*4]
0x18000b57a  add     rcx, rcx
0x18000b57d  sub     r8, rcx
0x18000b580  mov     rax, [rbx+r8*8]
0x18000b584  test    rax, rax
0x18000b587  jz      short loc_18000B598
0x18000b589  cmp     [rax], r9d
0x18000b58c  jz      short loc_18000B594
0x18000b58e  mov     rax, [rax+8]
0x18000b592  jmp     short loc_18000B584
0x18000b594  add     rax, 10h
0x18000b598  add     rsp, 20h
0x18000b59c  pop     rbx
0x18000b59d  retn
```
