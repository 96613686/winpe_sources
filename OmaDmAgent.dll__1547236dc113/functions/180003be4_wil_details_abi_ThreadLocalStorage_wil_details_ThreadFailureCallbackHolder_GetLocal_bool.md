# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180003be4`
- end: `0x180003c41`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036e4`

## callees

- `0x180003be4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180003bf1`
- `KERNEL32!GetCurrentThreadId` at `0x180003bf1`

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
0x180003be4  push    rbx
0x180003be6  sub     rsp, 20h
0x180003bea  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003bf1  call    cs:__imp_GetCurrentThreadId
0x180003bf8  nop     dword ptr [rax+rax+00h]
0x180003bfd  mov     r8d, eax
0x180003c00  mov     r9d, eax
0x180003c03  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003c0d  shr     r8, 2
0x180003c11  mul     r8
0x180003c14  shr     rdx, 3
0x180003c18  lea     rcx, [rdx+rdx*4]
0x180003c1c  add     rcx, rcx
0x180003c1f  sub     r8, rcx
0x180003c22  mov     rax, [rbx+r8*8]
0x180003c26  test    rax, rax
0x180003c29  jz      short loc_180003C3A
0x180003c2b  cmp     [rax], r9d
0x180003c2e  jz      short loc_180003C36
0x180003c30  mov     rax, [rax+8]
0x180003c34  jmp     short loc_180003C26
0x180003c36  add     rax, 10h
0x180003c3a  add     rsp, 20h
0x180003c3e  pop     rbx
0x180003c3f  retn
```
