# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800103b8`
- end: `0x18001040e`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ffc8`

## callees

- `0x1800103b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103c5`

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
0x1800103b8  push    rbx
0x1800103ba  sub     rsp, 20h
0x1800103be  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800103c5  call    cs:__imp_GetCurrentThreadId
0x1800103cb  mov     r8d, eax
0x1800103ce  mov     r9d, eax
0x1800103d1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800103db  shr     r8, 2
0x1800103df  mul     r8
0x1800103e2  shr     rdx, 3
0x1800103e6  lea     rcx, [rdx+rdx*4]
0x1800103ea  add     rcx, rcx
0x1800103ed  sub     r8, rcx
0x1800103f0  mov     rax, [rbx+r8*8]
0x1800103f4  test    rax, rax
0x1800103f7  jz      short loc_180010408
0x1800103f9  cmp     [rax], r9d
0x1800103fc  jz      short loc_180010404
0x1800103fe  mov     rax, [rax+8]
0x180010402  jmp     short loc_1800103F4
0x180010404  add     rax, 10h
0x180010408  add     rsp, 20h
0x18001040c  pop     rbx
0x18001040d  retn
```
