# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400045ec`
- end: `0x140004642`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004114`

## callees

- `0x1400045ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400045f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400045f9`

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
0x1400045ec  push    rbx
0x1400045ee  sub     rsp, 20h
0x1400045f2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400045f9  call    cs:__imp_GetCurrentThreadId
0x1400045ff  mov     r8d, eax
0x140004602  mov     r9d, eax
0x140004605  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000460f  shr     r8, 2
0x140004613  mul     r8
0x140004616  shr     rdx, 3
0x14000461a  lea     rcx, [rdx+rdx*4]
0x14000461e  add     rcx, rcx
0x140004621  sub     r8, rcx
0x140004624  mov     rax, [rbx+r8*8]
0x140004628  test    rax, rax
0x14000462b  jz      short loc_14000463C
0x14000462d  cmp     [rax], r9d
0x140004630  jz      short loc_140004638
0x140004632  mov     rax, [rax+8]
0x140004636  jmp     short loc_140004628
0x140004638  add     rax, 10h
0x14000463c  add     rsp, 20h
0x140004640  pop     rbx
0x140004641  retn
```
