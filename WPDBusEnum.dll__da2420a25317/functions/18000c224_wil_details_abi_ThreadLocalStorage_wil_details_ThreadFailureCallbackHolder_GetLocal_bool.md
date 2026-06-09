# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000c224`
- end: `0x18000c27a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bdd8`

## callees

- `0x18000c224`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c231`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c231`

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
0x18000c224  push    rbx
0x18000c226  sub     rsp, 20h
0x18000c22a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c231  call    cs:__imp_GetCurrentThreadId
0x18000c237  mov     r8d, eax
0x18000c23a  mov     r9d, eax
0x18000c23d  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c247  shr     r8, 2
0x18000c24b  mul     r8
0x18000c24e  shr     rdx, 3
0x18000c252  lea     rcx, [rdx+rdx*4]
0x18000c256  add     rcx, rcx
0x18000c259  sub     r8, rcx
0x18000c25c  mov     rax, [rbx+r8*8]
0x18000c260  test    rax, rax
0x18000c263  jz      short loc_18000C274
0x18000c265  cmp     [rax], r9d
0x18000c268  jz      short loc_18000C270
0x18000c26a  mov     rax, [rax+8]
0x18000c26e  jmp     short loc_18000C260
0x18000c270  add     rax, 10h
0x18000c274  add     rsp, 20h
0x18000c278  pop     rbx
0x18000c279  retn
```
