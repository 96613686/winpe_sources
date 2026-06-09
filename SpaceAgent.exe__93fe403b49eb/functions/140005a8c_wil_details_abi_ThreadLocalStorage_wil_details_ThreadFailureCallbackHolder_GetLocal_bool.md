# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140005a8c`
- end: `0x140005ae2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400055b4`

## callees

- `0x140005a8c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005a99`
- `KERNEL32!GetCurrentThreadId` at `0x140005a99`

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
0x140005a8c  push    rbx
0x140005a8e  sub     rsp, 20h
0x140005a92  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140005a99  call    cs:__imp_GetCurrentThreadId
0x140005a9f  mov     r8d, eax
0x140005aa2  mov     r9d, eax
0x140005aa5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005aaf  shr     r8, 2
0x140005ab3  mul     r8
0x140005ab6  shr     rdx, 3
0x140005aba  lea     rcx, [rdx+rdx*4]
0x140005abe  add     rcx, rcx
0x140005ac1  sub     r8, rcx
0x140005ac4  mov     rax, [rbx+r8*8]
0x140005ac8  test    rax, rax
0x140005acb  jz      short loc_140005ADC
0x140005acd  cmp     [rax], r9d
0x140005ad0  jz      short loc_140005AD8
0x140005ad2  mov     rax, [rax+8]
0x140005ad6  jmp     short loc_140005AC8
0x140005ad8  add     rax, 10h
0x140005adc  add     rsp, 20h
0x140005ae0  pop     rbx
0x140005ae1  retn
```
