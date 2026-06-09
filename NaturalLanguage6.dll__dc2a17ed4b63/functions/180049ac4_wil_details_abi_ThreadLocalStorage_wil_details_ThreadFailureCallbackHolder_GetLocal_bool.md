# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180049ac4`
- end: `0x180049b23`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180049790`

## callees

- `0x180049ac4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049ada`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049ada`

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
0x180049ac4  push    rbx
0x180049ac6  sub     rsp, 30h
0x180049aca  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180049ad3  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180049ada  call    cs:__imp_GetCurrentThreadId
0x180049ae0  mov     r9d, eax
0x180049ae3  mov     r8d, eax
0x180049ae6  shr     r8, 2
0x180049aea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180049af4  mul     r8
0x180049af7  shr     rdx, 3
0x180049afb  lea     rcx, [rdx+rdx*4]
0x180049aff  add     rcx, rcx
0x180049b02  sub     r8, rcx
0x180049b05  mov     rax, [rbx+r8*8]
0x180049b09  test    rax, rax
0x180049b0c  jz      short loc_180049B1D
0x180049b0e  cmp     [rax], r9d
0x180049b11  jz      short loc_180049B19
0x180049b13  mov     rax, [rax+8]
0x180049b17  jmp     short loc_180049B09
0x180049b19  add     rax, 10h
0x180049b1d  add     rsp, 30h
0x180049b21  pop     rbx
0x180049b22  retn
```
