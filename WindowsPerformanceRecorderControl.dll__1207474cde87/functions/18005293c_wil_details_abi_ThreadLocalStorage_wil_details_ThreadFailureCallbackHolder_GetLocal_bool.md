# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18005293c`
- end: `0x180052992`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800521dc`

## callees

- `0x18005293c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052949`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052949`

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
0x18005293c  push    rbx
0x18005293e  sub     rsp, 20h
0x180052942  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180052949  call    cs:__imp_GetCurrentThreadId
0x18005294f  mov     r8d, eax
0x180052952  mov     r9d, eax
0x180052955  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18005295f  shr     r8, 2
0x180052963  mul     r8
0x180052966  shr     rdx, 3
0x18005296a  lea     rcx, [rdx+rdx*4]
0x18005296e  add     rcx, rcx
0x180052971  sub     r8, rcx
0x180052974  mov     rax, [rbx+r8*8]
0x180052978  test    rax, rax
0x18005297b  jz      short loc_18005298C
0x18005297d  cmp     [rax], r9d
0x180052980  jz      short loc_180052988
0x180052982  mov     rax, [rax+8]
0x180052986  jmp     short loc_180052978
0x180052988  add     rax, 10h
0x18005298c  add     rsp, 20h
0x180052990  pop     rbx
0x180052991  retn
```
