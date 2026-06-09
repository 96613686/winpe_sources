# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800aa68c`
- end: `0x1800aa6e2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a9e8c`

## callees

- `0x1800aa68c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa699`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa699`

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
0x1800aa68c  push    rbx
0x1800aa68e  sub     rsp, 20h
0x1800aa692  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800aa699  call    cs:__imp_GetCurrentThreadId
0x1800aa69f  mov     r9d, eax
0x1800aa6a2  mov     r8d, eax
0x1800aa6a5  shr     r8, 2
0x1800aa6a9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800aa6b3  mul     r8
0x1800aa6b6  shr     rdx, 3
0x1800aa6ba  lea     rcx, [rdx+rdx*4]
0x1800aa6be  add     rcx, rcx
0x1800aa6c1  sub     r8, rcx
0x1800aa6c4  mov     rax, [rbx+r8*8]
0x1800aa6c8  test    rax, rax
0x1800aa6cb  jz      short loc_1800AA6DC
0x1800aa6cd  cmp     [rax], r9d
0x1800aa6d0  jz      short loc_1800AA6D8
0x1800aa6d2  mov     rax, [rax+8]
0x1800aa6d6  jmp     short loc_1800AA6C8
0x1800aa6d8  add     rax, 10h
0x1800aa6dc  add     rsp, 20h
0x1800aa6e0  pop     rbx
0x1800aa6e1  retn
```
