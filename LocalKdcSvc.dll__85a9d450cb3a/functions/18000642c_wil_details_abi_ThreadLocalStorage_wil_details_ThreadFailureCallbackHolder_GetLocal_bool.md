# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000642c`
- end: `0x180006482`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005f54`

## callees

- `0x18000642c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006439`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006439`

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
0x18000642c  push    rbx
0x18000642e  sub     rsp, 20h
0x180006432  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006439  call    cs:__imp_GetCurrentThreadId
0x18000643f  mov     r8d, eax
0x180006442  mov     r9d, eax
0x180006445  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000644f  shr     r8, 2
0x180006453  mul     r8
0x180006456  shr     rdx, 3
0x18000645a  lea     rcx, [rdx+rdx*4]
0x18000645e  add     rcx, rcx
0x180006461  sub     r8, rcx
0x180006464  mov     rax, [rbx+r8*8]
0x180006468  test    rax, rax
0x18000646b  jz      short loc_18000647C
0x18000646d  cmp     [rax], r9d
0x180006470  jz      short loc_180006478
0x180006472  mov     rax, [rax+8]
0x180006476  jmp     short loc_180006468
0x180006478  add     rax, 10h
0x18000647c  add     rsp, 20h
0x180006480  pop     rbx
0x180006481  retn
```
