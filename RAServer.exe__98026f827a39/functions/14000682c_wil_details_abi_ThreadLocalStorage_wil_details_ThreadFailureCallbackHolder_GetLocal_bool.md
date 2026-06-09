# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x14000682c`
- end: `0x140006882`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000625c`

## callees

- `0x14000682c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006839`
- `KERNEL32!GetCurrentThreadId` at `0x140006839`

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
0x14000682c  push    rbx
0x14000682e  sub     rsp, 20h
0x140006832  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140006839  call    cs:__imp_GetCurrentThreadId
0x14000683f  mov     r8d, eax
0x140006842  mov     r9d, eax
0x140006845  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000684f  shr     r8, 2
0x140006853  mul     r8
0x140006856  shr     rdx, 3
0x14000685a  lea     rcx, [rdx+rdx*4]
0x14000685e  add     rcx, rcx
0x140006861  sub     r8, rcx
0x140006864  mov     rax, [rbx+r8*8]
0x140006868  test    rax, rax
0x14000686b  jz      short loc_14000687C
0x14000686d  cmp     [rax], r9d
0x140006870  jz      short loc_140006878
0x140006872  mov     rax, [rax+8]
0x140006876  jmp     short loc_140006868
0x140006878  add     rax, 10h
0x14000687c  add     rsp, 20h
0x140006880  pop     rbx
0x140006881  retn
```
