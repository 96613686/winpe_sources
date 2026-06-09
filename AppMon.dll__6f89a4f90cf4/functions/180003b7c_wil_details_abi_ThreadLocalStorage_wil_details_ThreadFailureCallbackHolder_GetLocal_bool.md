# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180003b7c`
- end: `0x180003bd2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036a8`

## callees

- `0x180003b7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b89`

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
0x180003b7c  push    rbx
0x180003b7e  sub     rsp, 20h
0x180003b82  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003b89  call    cs:__imp_GetCurrentThreadId
0x180003b8f  mov     r8d, eax
0x180003b92  mov     r9d, eax
0x180003b95  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003b9f  shr     r8, 2
0x180003ba3  mul     r8
0x180003ba6  shr     rdx, 3
0x180003baa  lea     rcx, [rdx+rdx*4]
0x180003bae  add     rcx, rcx
0x180003bb1  sub     r8, rcx
0x180003bb4  mov     rax, [rbx+r8*8]
0x180003bb8  test    rax, rax
0x180003bbb  jz      short loc_180003BCC
0x180003bbd  cmp     [rax], r9d
0x180003bc0  jz      short loc_180003BC8
0x180003bc2  mov     rax, [rax+8]
0x180003bc6  jmp     short loc_180003BB8
0x180003bc8  add     rax, 10h
0x180003bcc  add     rsp, 20h
0x180003bd0  pop     rbx
0x180003bd1  retn
```
