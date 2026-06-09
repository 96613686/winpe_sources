# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180007d6c`
- end: `0x180007dc2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007874`

## callees

- `0x180007d6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d79`

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
0x180007d6c  push    rbx
0x180007d6e  sub     rsp, 20h
0x180007d72  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007d79  call    cs:__imp_GetCurrentThreadId
0x180007d7f  mov     r8d, eax
0x180007d82  mov     r9d, eax
0x180007d85  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007d8f  shr     r8, 2
0x180007d93  mul     r8
0x180007d96  shr     rdx, 3
0x180007d9a  lea     rcx, [rdx+rdx*4]
0x180007d9e  add     rcx, rcx
0x180007da1  sub     r8, rcx
0x180007da4  mov     rax, [rbx+r8*8]
0x180007da8  test    rax, rax
0x180007dab  jz      short loc_180007DBC
0x180007dad  cmp     [rax], r9d
0x180007db0  jz      short loc_180007DB8
0x180007db2  mov     rax, [rax+8]
0x180007db6  jmp     short loc_180007DA8
0x180007db8  add     rax, 10h
0x180007dbc  add     rsp, 20h
0x180007dc0  pop     rbx
0x180007dc1  retn
```
