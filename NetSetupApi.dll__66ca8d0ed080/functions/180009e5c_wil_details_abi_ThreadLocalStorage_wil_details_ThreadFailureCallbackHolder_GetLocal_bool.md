# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180009e5c`
- end: `0x180009eb2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009a0c`

## callees

- `0x180009e5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e69`

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
0x180009e5c  push    rbx
0x180009e5e  sub     rsp, 20h
0x180009e62  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009e69  call    cs:__imp_GetCurrentThreadId
0x180009e6f  mov     r8d, eax
0x180009e72  mov     r9d, eax
0x180009e75  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009e7f  shr     r8, 2
0x180009e83  mul     r8
0x180009e86  shr     rdx, 3
0x180009e8a  lea     rcx, [rdx+rdx*4]
0x180009e8e  add     rcx, rcx
0x180009e91  sub     r8, rcx
0x180009e94  mov     rax, [rbx+r8*8]
0x180009e98  test    rax, rax
0x180009e9b  jz      short loc_180009EAC
0x180009e9d  cmp     [rax], r9d
0x180009ea0  jz      short loc_180009EA8
0x180009ea2  mov     rax, [rax+8]
0x180009ea6  jmp     short loc_180009E98
0x180009ea8  add     rax, 10h
0x180009eac  add     rsp, 20h
0x180009eb0  pop     rbx
0x180009eb1  retn
```
