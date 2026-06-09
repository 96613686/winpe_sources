# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000a6b4`
- end: `0x18000a711`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a328`

## callees

- `0x18000a6b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a6c1`

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
0x18000a6b4  push    rbx
0x18000a6b6  sub     rsp, 20h
0x18000a6ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000a6c1  call    cs:__imp_GetCurrentThreadId
0x18000a6c8  nop     dword ptr [rax+rax+00h]
0x18000a6cd  mov     r8d, eax
0x18000a6d0  mov     r9d, eax
0x18000a6d3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000a6dd  shr     r8, 2
0x18000a6e1  mul     r8
0x18000a6e4  shr     rdx, 3
0x18000a6e8  lea     rcx, [rdx+rdx*4]
0x18000a6ec  add     rcx, rcx
0x18000a6ef  sub     r8, rcx
0x18000a6f2  mov     rax, [rbx+r8*8]
0x18000a6f6  test    rax, rax
0x18000a6f9  jz      short loc_18000A70A
0x18000a6fb  cmp     [rax], r9d
0x18000a6fe  jz      short loc_18000A706
0x18000a700  mov     rax, [rax+8]
0x18000a704  jmp     short loc_18000A6F6
0x18000a706  add     rax, 10h
0x18000a70a  add     rsp, 20h
0x18000a70e  pop     rbx
0x18000a70f  retn
```
