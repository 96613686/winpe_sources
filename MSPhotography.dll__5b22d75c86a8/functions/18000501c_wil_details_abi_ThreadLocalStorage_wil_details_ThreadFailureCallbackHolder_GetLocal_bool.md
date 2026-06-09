# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000501c`
- end: `0x180005072`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b44`

## callees

- `0x18000501c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005029`

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
0x18000501c  push    rbx
0x18000501e  sub     rsp, 20h
0x180005022  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005029  call    cs:__imp_GetCurrentThreadId
0x18000502f  mov     r8d, eax
0x180005032  mov     r9d, eax
0x180005035  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000503f  shr     r8, 2
0x180005043  mul     r8
0x180005046  shr     rdx, 3
0x18000504a  lea     rcx, [rdx+rdx*4]
0x18000504e  add     rcx, rcx
0x180005051  sub     r8, rcx
0x180005054  mov     rax, [rbx+r8*8]
0x180005058  test    rax, rax
0x18000505b  jz      short loc_18000506C
0x18000505d  cmp     [rax], r9d
0x180005060  jz      short loc_180005068
0x180005062  mov     rax, [rax+8]
0x180005066  jmp     short loc_180005058
0x180005068  add     rax, 10h
0x18000506c  add     rsp, 20h
0x180005070  pop     rbx
0x180005071  retn
```
