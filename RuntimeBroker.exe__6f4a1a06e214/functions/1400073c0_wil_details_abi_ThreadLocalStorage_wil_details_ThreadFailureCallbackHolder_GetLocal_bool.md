# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400073c0`
- end: `0x140007418`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140007184`

## callees

- `0x1400073c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400073cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400073cd`

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
0x1400073c0  push    rbx
0x1400073c2  sub     rsp, 20h
0x1400073c6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400073cd  call    cs:__imp_GetCurrentThreadId
0x1400073d3  mov     r8d, eax
0x1400073d6  mov     r9d, eax
0x1400073d9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400073e3  shr     r8, 2
0x1400073e7  mul     r8
0x1400073ea  shr     rdx, 3
0x1400073ee  lea     rcx, [rdx+rdx*4]
0x1400073f2  add     rcx, rcx
0x1400073f5  sub     r8, rcx
0x1400073f8  mov     rax, [rbx+r8*8]
0x1400073fc  test    rax, rax
0x1400073ff  jnz     short loc_140007407
0x140007401  add     rsp, 20h
0x140007405  pop     rbx
0x140007406  retn
0x140007407  cmp     [rax], r9d
0x14000740a  jz      short loc_140007412
0x14000740c  mov     rax, [rax+8]
0x140007410  jmp     short loc_1400073FC
0x140007412  add     rax, 10h
0x140007416  jmp     short loc_140007401
```
