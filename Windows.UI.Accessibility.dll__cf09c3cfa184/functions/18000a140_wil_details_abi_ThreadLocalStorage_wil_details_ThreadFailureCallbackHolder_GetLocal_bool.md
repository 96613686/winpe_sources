# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000a140`
- end: `0x18000a196`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009f28`

## callees

- `0x18000a140`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a14d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a14d`

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
0x18000a140  push    rbx
0x18000a142  sub     rsp, 20h
0x18000a146  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a14d  call    cs:__imp_GetCurrentThreadId
0x18000a153  mov     r8d, eax
0x18000a156  mov     r9d, eax
0x18000a159  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a163  shr     r8, 2
0x18000a167  mul     r8
0x18000a16a  shr     rdx, 3
0x18000a16e  lea     rcx, [rdx+rdx*4]
0x18000a172  add     rcx, rcx
0x18000a175  sub     r8, rcx
0x18000a178  mov     rax, [rbx+r8*8]
0x18000a17c  test    rax, rax
0x18000a17f  jz      short loc_18000A190
0x18000a181  cmp     [rax], r9d
0x18000a184  jz      short loc_18000A18C
0x18000a186  mov     rax, [rax+8]
0x18000a18a  jmp     short loc_18000A17C
0x18000a18c  add     rax, 10h
0x18000a190  add     rsp, 20h
0x18000a194  pop     rbx
0x18000a195  retn
```
