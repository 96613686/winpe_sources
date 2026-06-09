# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180009e00`
- end: `0x180009e5d`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800098e8`

## callees

- `0x180009e00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e0d`

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
0x180009e00  push    rbx
0x180009e02  sub     rsp, 20h
0x180009e06  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009e0d  call    cs:__imp_GetCurrentThreadId
0x180009e14  nop     dword ptr [rax+rax+00h]
0x180009e19  mov     r8d, eax
0x180009e1c  mov     r9d, eax
0x180009e1f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009e29  shr     r8, 2
0x180009e2d  mul     r8
0x180009e30  shr     rdx, 3
0x180009e34  lea     rcx, [rdx+rdx*4]
0x180009e38  add     rcx, rcx
0x180009e3b  sub     r8, rcx
0x180009e3e  mov     rax, [rbx+r8*8]
0x180009e42  test    rax, rax
0x180009e45  jz      short loc_180009E56
0x180009e47  cmp     [rax], r9d
0x180009e4a  jz      short loc_180009E52
0x180009e4c  mov     rax, [rax+8]
0x180009e50  jmp     short loc_180009E42
0x180009e52  add     rax, 10h
0x180009e56  add     rsp, 20h
0x180009e5a  pop     rbx
0x180009e5b  retn
```
