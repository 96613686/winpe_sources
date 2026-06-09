# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800a6bb8`
- end: `0x1800a6c10`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a69f0`

## callees

- `0x1800a6bb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a6bc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a6bc5`

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
0x1800a6bb8  push    rbx
0x1800a6bba  sub     rsp, 20h
0x1800a6bbe  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800a6bc5  call    cs:__imp_GetCurrentThreadId
0x1800a6bcb  mov     r8d, eax
0x1800a6bce  mov     r9d, eax
0x1800a6bd1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800a6bdb  shr     r8, 2
0x1800a6bdf  mul     r8
0x1800a6be2  shr     rdx, 3
0x1800a6be6  lea     rcx, [rdx+rdx*4]
0x1800a6bea  add     rcx, rcx
0x1800a6bed  sub     r8, rcx
0x1800a6bf0  mov     rax, [rbx+r8*8]
0x1800a6bf4  jmp     short loc_1800A6BFF
0x1800a6bf6  cmp     [rax], r9d
0x1800a6bf9  jz      short loc_1800A6C0A
0x1800a6bfb  mov     rax, [rax+8]
0x1800a6bff  test    rax, rax
0x1800a6c02  jnz     short loc_1800A6BF6
0x1800a6c04  add     rsp, 20h
0x1800a6c08  pop     rbx
0x1800a6c09  retn
0x1800a6c0a  add     rax, 10h
0x1800a6c0e  jmp     short loc_1800A6C04
```
