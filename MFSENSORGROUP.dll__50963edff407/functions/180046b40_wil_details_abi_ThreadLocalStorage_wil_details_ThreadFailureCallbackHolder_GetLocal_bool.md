# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180046b40`
- end: `0x180046b96`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180046710`

## callees

- `0x180046b40`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046b4d`

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
0x180046b40  push    rbx
0x180046b42  sub     rsp, 20h
0x180046b46  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180046b4d  call    cs:__imp_GetCurrentThreadId
0x180046b53  mov     r8d, eax
0x180046b56  mov     r9d, eax
0x180046b59  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180046b63  shr     r8, 2
0x180046b67  mul     r8
0x180046b6a  shr     rdx, 3
0x180046b6e  lea     rcx, [rdx+rdx*4]
0x180046b72  add     rcx, rcx
0x180046b75  sub     r8, rcx
0x180046b78  mov     rax, [rbx+r8*8]
0x180046b7c  test    rax, rax
0x180046b7f  jz      short loc_180046B90
0x180046b81  cmp     [rax], r9d
0x180046b84  jz      short loc_180046B8C
0x180046b86  mov     rax, [rax+8]
0x180046b8a  jmp     short loc_180046B7C
0x180046b8c  add     rax, 10h
0x180046b90  add     rsp, 20h
0x180046b94  pop     rbx
0x180046b95  retn
```
