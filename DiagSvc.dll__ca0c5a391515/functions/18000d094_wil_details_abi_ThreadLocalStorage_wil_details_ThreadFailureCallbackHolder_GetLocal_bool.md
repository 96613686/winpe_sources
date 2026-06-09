# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000d094`
- end: `0x18000d0ea`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c004`

## callees

- `0x18000d094`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d0a1`

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
0x18000d094  push    rbx
0x18000d096  sub     rsp, 20h
0x18000d09a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000d0a1  call    cs:__imp_GetCurrentThreadId
0x18000d0a7  mov     r8d, eax
0x18000d0aa  mov     r9d, eax
0x18000d0ad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000d0b7  shr     r8, 2
0x18000d0bb  mul     r8
0x18000d0be  shr     rdx, 3
0x18000d0c2  lea     rcx, [rdx+rdx*4]
0x18000d0c6  add     rcx, rcx
0x18000d0c9  sub     r8, rcx
0x18000d0cc  mov     rax, [rbx+r8*8]
0x18000d0d0  test    rax, rax
0x18000d0d3  jz      short loc_18000D0E4
0x18000d0d5  cmp     [rax], r9d
0x18000d0d8  jz      short loc_18000D0E0
0x18000d0da  mov     rax, [rax+8]
0x18000d0de  jmp     short loc_18000D0D0
0x18000d0e0  add     rax, 10h
0x18000d0e4  add     rsp, 20h
0x18000d0e8  pop     rbx
0x18000d0e9  retn
```
