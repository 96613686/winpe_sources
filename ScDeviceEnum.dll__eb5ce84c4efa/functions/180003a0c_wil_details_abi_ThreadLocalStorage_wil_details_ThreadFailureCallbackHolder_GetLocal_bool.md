# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180003a0c`
- end: `0x180003a62`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003538`

## callees

- `0x180003a0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a19`

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
0x180003a0c  push    rbx
0x180003a0e  sub     rsp, 20h
0x180003a12  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003a19  call    cs:__imp_GetCurrentThreadId
0x180003a1f  mov     r8d, eax
0x180003a22  mov     r9d, eax
0x180003a25  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003a2f  shr     r8, 2
0x180003a33  mul     r8
0x180003a36  shr     rdx, 3
0x180003a3a  lea     rcx, [rdx+rdx*4]
0x180003a3e  add     rcx, rcx
0x180003a41  sub     r8, rcx
0x180003a44  mov     rax, [rbx+r8*8]
0x180003a48  test    rax, rax
0x180003a4b  jz      short loc_180003A5C
0x180003a4d  cmp     [rax], r9d
0x180003a50  jz      short loc_180003A58
0x180003a52  mov     rax, [rax+8]
0x180003a56  jmp     short loc_180003A48
0x180003a58  add     rax, 10h
0x180003a5c  add     rsp, 20h
0x180003a60  pop     rbx
0x180003a61  retn
```
