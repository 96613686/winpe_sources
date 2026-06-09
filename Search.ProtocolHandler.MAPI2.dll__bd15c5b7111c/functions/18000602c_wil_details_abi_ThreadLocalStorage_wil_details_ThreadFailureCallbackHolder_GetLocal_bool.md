# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000602c`
- end: `0x180006082`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b54`

## callees

- `0x18000602c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006039`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006039`

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
0x18000602c  push    rbx
0x18000602e  sub     rsp, 20h
0x180006032  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006039  call    cs:__imp_GetCurrentThreadId
0x18000603f  mov     r8d, eax
0x180006042  mov     r9d, eax
0x180006045  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000604f  shr     r8, 2
0x180006053  mul     r8
0x180006056  shr     rdx, 3
0x18000605a  lea     rcx, [rdx+rdx*4]
0x18000605e  add     rcx, rcx
0x180006061  sub     r8, rcx
0x180006064  mov     rax, [rbx+r8*8]
0x180006068  test    rax, rax
0x18000606b  jz      short loc_18000607C
0x18000606d  cmp     [rax], r9d
0x180006070  jz      short loc_180006078
0x180006072  mov     rax, [rax+8]
0x180006076  jmp     short loc_180006068
0x180006078  add     rax, 10h
0x18000607c  add     rsp, 20h
0x180006080  pop     rbx
0x180006081  retn
```
