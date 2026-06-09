# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180024f84`
- end: `0x180024fdd`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024a60`

## callees

- `0x180024f84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f91`

## pseudocode

```c
__int64 wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal()
{
  __int64 v0; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 result; // rax

  v0 = wil::details::g_pThreadFailureCallbacks;
  CurrentThreadId = GetCurrentThreadId();
  for ( result = *(_QWORD *)(v0 + 8 * (CurrentThreadId % 0xAuLL)); result; result = *(_QWORD *)(result + 8) )
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
0x180024f84  push    rbx
0x180024f86  sub     rsp, 20h
0x180024f8a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180024f91  call    cs:__imp_GetCurrentThreadId
0x180024f98  nop     dword ptr [rax+rax+00h]
0x180024f9d  mov     r8d, eax
0x180024fa0  mov     r9d, eax
0x180024fa3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180024fad  mul     r9
0x180024fb0  shr     rdx, 3
0x180024fb4  lea     rcx, [rdx+rdx*4]
0x180024fb8  add     rcx, rcx
0x180024fbb  sub     r8, rcx
0x180024fbe  mov     rax, [rbx+r8*8]
0x180024fc2  test    rax, rax
0x180024fc5  jz      short loc_180024FD6
0x180024fc7  cmp     [rax], r9d
0x180024fca  jz      short loc_180024FD2
0x180024fcc  mov     rax, [rax+8]
0x180024fd0  jmp     short loc_180024FC2
0x180024fd2  add     rax, 10h
0x180024fd6  add     rsp, 20h
0x180024fda  pop     rbx
0x180024fdb  retn
```
