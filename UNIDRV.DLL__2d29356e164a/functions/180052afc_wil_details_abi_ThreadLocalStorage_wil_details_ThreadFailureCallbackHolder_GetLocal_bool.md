# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180052afc`
- end: `0x180052b52`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005245c`

## callees

- `0x180052afc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180052b09`
- `KERNEL32!GetCurrentThreadId` at `0x180052b09`

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
0x180052afc  push    rbx
0x180052afe  sub     rsp, 20h
0x180052b02  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180052b09  call    cs:__imp_GetCurrentThreadId
0x180052b0f  mov     r8d, eax
0x180052b12  mov     r9d, eax
0x180052b15  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180052b1f  shr     r8, 2
0x180052b23  mul     r8
0x180052b26  shr     rdx, 3
0x180052b2a  lea     rcx, [rdx+rdx*4]
0x180052b2e  add     rcx, rcx
0x180052b31  sub     r8, rcx
0x180052b34  mov     rax, [rbx+r8*8]
0x180052b38  test    rax, rax
0x180052b3b  jz      short loc_180052B4C
0x180052b3d  cmp     [rax], r9d
0x180052b40  jz      short loc_180052B48
0x180052b42  mov     rax, [rax+8]
0x180052b46  jmp     short loc_180052B38
0x180052b48  add     rax, 10h
0x180052b4c  add     rsp, 20h
0x180052b50  pop     rbx
0x180052b51  retn
```
