# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800278c0`
- end: `0x180027916`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180027488`

## callees

- `0x1800278c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800278cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800278cd`

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
0x1800278c0  push    rbx
0x1800278c2  sub     rsp, 20h
0x1800278c6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800278cd  call    cs:__imp_GetCurrentThreadId
0x1800278d3  mov     r8d, eax
0x1800278d6  mov     r9d, eax
0x1800278d9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800278e3  shr     r8, 2
0x1800278e7  mul     r8
0x1800278ea  shr     rdx, 3
0x1800278ee  lea     rcx, [rdx+rdx*4]
0x1800278f2  add     rcx, rcx
0x1800278f5  sub     r8, rcx
0x1800278f8  mov     rax, [rbx+r8*8]
0x1800278fc  test    rax, rax
0x1800278ff  jz      short loc_180027910
0x180027901  cmp     [rax], r9d
0x180027904  jz      short loc_18002790C
0x180027906  mov     rax, [rax+8]
0x18002790a  jmp     short loc_1800278FC
0x18002790c  add     rax, 10h
0x180027910  add     rsp, 20h
0x180027914  pop     rbx
0x180027915  retn
```
