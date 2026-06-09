# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18004abd0`
- end: `0x18004ac28`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18004a958`

## callees

- `0x18004abd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004abdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004abdd`

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
0x18004abd0  push    rbx
0x18004abd2  sub     rsp, 20h
0x18004abd6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18004abdd  call    cs:__imp_GetCurrentThreadId
0x18004abe3  mov     r8d, eax
0x18004abe6  mov     r9d, eax
0x18004abe9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18004abf3  shr     r8, 2
0x18004abf7  mul     r8
0x18004abfa  shr     rdx, 3
0x18004abfe  lea     rcx, [rdx+rdx*4]
0x18004ac02  add     rcx, rcx
0x18004ac05  sub     r8, rcx
0x18004ac08  mov     rax, [rbx+r8*8]
0x18004ac0c  jmp     short loc_18004AC17
0x18004ac0e  cmp     [rax], r9d
0x18004ac11  jz      short loc_18004AC22
0x18004ac13  mov     rax, [rax+8]
0x18004ac17  test    rax, rax
0x18004ac1a  jnz     short loc_18004AC0E
0x18004ac1c  add     rsp, 20h
0x18004ac20  pop     rbx
0x18004ac21  retn
0x18004ac22  add     rax, 10h
0x18004ac26  jmp     short loc_18004AC1C
```
