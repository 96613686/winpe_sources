# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400041fc`
- end: `0x140004252`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003d24`

## callees

- `0x1400041fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004209`

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
0x1400041fc  push    rbx
0x1400041fe  sub     rsp, 20h
0x140004202  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004209  call    cs:__imp_GetCurrentThreadId
0x14000420f  mov     r8d, eax
0x140004212  mov     r9d, eax
0x140004215  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000421f  shr     r8, 2
0x140004223  mul     r8
0x140004226  shr     rdx, 3
0x14000422a  lea     rcx, [rdx+rdx*4]
0x14000422e  add     rcx, rcx
0x140004231  sub     r8, rcx
0x140004234  mov     rax, [rbx+r8*8]
0x140004238  test    rax, rax
0x14000423b  jz      short loc_14000424C
0x14000423d  cmp     [rax], r9d
0x140004240  jz      short loc_140004248
0x140004242  mov     rax, [rax+8]
0x140004246  jmp     short loc_140004238
0x140004248  add     rax, 10h
0x14000424c  add     rsp, 20h
0x140004250  pop     rbx
0x140004251  retn
```
