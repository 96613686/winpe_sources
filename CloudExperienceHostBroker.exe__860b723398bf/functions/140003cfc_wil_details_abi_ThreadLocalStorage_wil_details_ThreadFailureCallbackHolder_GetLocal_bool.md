# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140003cfc`
- end: `0x140003d52`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003824`

## callees

- `0x140003cfc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003d09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003d09`

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
0x140003cfc  push    rbx
0x140003cfe  sub     rsp, 20h
0x140003d02  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003d09  call    cs:__imp_GetCurrentThreadId
0x140003d0f  mov     r8d, eax
0x140003d12  mov     r9d, eax
0x140003d15  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003d1f  shr     r8, 2
0x140003d23  mul     r8
0x140003d26  shr     rdx, 3
0x140003d2a  lea     rcx, [rdx+rdx*4]
0x140003d2e  add     rcx, rcx
0x140003d31  sub     r8, rcx
0x140003d34  mov     rax, [rbx+r8*8]
0x140003d38  test    rax, rax
0x140003d3b  jz      short loc_140003D4C
0x140003d3d  cmp     [rax], r9d
0x140003d40  jz      short loc_140003D48
0x140003d42  mov     rax, [rax+8]
0x140003d46  jmp     short loc_140003D38
0x140003d48  add     rax, 10h
0x140003d4c  add     rsp, 20h
0x140003d50  pop     rbx
0x140003d51  retn
```
