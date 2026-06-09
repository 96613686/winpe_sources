# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800062ec`
- end: `0x180006342`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e14`

## callees

- `0x1800062ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062f9`

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
0x1800062ec  push    rbx
0x1800062ee  sub     rsp, 20h
0x1800062f2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800062f9  call    cs:__imp_GetCurrentThreadId
0x1800062ff  mov     r8d, eax
0x180006302  mov     r9d, eax
0x180006305  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000630f  shr     r8, 2
0x180006313  mul     r8
0x180006316  shr     rdx, 3
0x18000631a  lea     rcx, [rdx+rdx*4]
0x18000631e  add     rcx, rcx
0x180006321  sub     r8, rcx
0x180006324  mov     rax, [rbx+r8*8]
0x180006328  test    rax, rax
0x18000632b  jz      short loc_18000633C
0x18000632d  cmp     [rax], r9d
0x180006330  jz      short loc_180006338
0x180006332  mov     rax, [rax+8]
0x180006336  jmp     short loc_180006328
0x180006338  add     rax, 10h
0x18000633c  add     rsp, 20h
0x180006340  pop     rbx
0x180006341  retn
```
