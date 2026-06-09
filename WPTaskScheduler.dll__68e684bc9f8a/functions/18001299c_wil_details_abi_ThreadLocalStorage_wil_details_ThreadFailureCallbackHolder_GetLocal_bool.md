# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001299c`
- end: `0x1800129f4`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800124c4`

## callees

- `0x18001299c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800129a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800129a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001299c  push    rbx
0x18001299e  sub     rsp, 20h
0x1800129a2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800129a9  call    cs:__imp_GetCurrentThreadId
0x1800129af  mov     r8d, eax
0x1800129b2  mov     r9d, eax
0x1800129b5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800129bf  shr     r8, 2
0x1800129c3  mul     r8
0x1800129c6  shr     rdx, 3
0x1800129ca  lea     rcx, [rdx+rdx*4]
0x1800129ce  add     rcx, rcx
0x1800129d1  sub     r8, rcx
0x1800129d4  mov     rax, [rbx+r8*8]
0x1800129d8  jmp     short loc_1800129E3
0x1800129da  cmp     [rax], r9d
0x1800129dd  jz      short loc_1800129EE
0x1800129df  mov     rax, [rax+8]
0x1800129e3  test    rax, rax
0x1800129e6  jnz     short loc_1800129DA
0x1800129e8  add     rsp, 20h
0x1800129ec  pop     rbx
0x1800129ed  retn
0x1800129ee  add     rax, 10h
0x1800129f2  jmp     short loc_1800129E8
```
