# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180014c4c`
- end: `0x180014ca2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800147f8`

## callees

- `0x180014c4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014c59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014c59`

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
0x180014c4c  push    rbx
0x180014c4e  sub     rsp, 20h
0x180014c52  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180014c59  call    cs:__imp_GetCurrentThreadId
0x180014c5f  mov     r8d, eax
0x180014c62  mov     r9d, eax
0x180014c65  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180014c6f  shr     r8, 2
0x180014c73  mul     r8
0x180014c76  shr     rdx, 3
0x180014c7a  lea     rcx, [rdx+rdx*4]
0x180014c7e  add     rcx, rcx
0x180014c81  sub     r8, rcx
0x180014c84  mov     rax, [rbx+r8*8]
0x180014c88  test    rax, rax
0x180014c8b  jz      short loc_180014C9C
0x180014c8d  cmp     [rax], r9d
0x180014c90  jz      short loc_180014C98
0x180014c92  mov     rax, [rax+8]
0x180014c96  jmp     short loc_180014C88
0x180014c98  add     rax, 10h
0x180014c9c  add     rsp, 20h
0x180014ca0  pop     rbx
0x180014ca1  retn
```
