# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18005447c`
- end: `0x1800544d9`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180053da4`

## callees

- `0x18005447c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180054489`
- `KERNEL32!GetCurrentThreadId` at `0x180054489`

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
0x18005447c  push    rbx
0x18005447e  sub     rsp, 20h
0x180054482  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180054489  call    cs:__imp_GetCurrentThreadId
0x180054490  nop     dword ptr [rax+rax+00h]
0x180054495  mov     r8d, eax
0x180054498  mov     r9d, eax
0x18005449b  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800544a5  shr     r8, 2
0x1800544a9  mul     r8
0x1800544ac  shr     rdx, 3
0x1800544b0  lea     rcx, [rdx+rdx*4]
0x1800544b4  add     rcx, rcx
0x1800544b7  sub     r8, rcx
0x1800544ba  mov     rax, [rbx+r8*8]
0x1800544be  test    rax, rax
0x1800544c1  jz      short loc_1800544D2
0x1800544c3  cmp     [rax], r9d
0x1800544c6  jz      short loc_1800544CE
0x1800544c8  mov     rax, [rax+8]
0x1800544cc  jmp     short loc_1800544BE
0x1800544ce  add     rax, 10h
0x1800544d2  add     rsp, 20h
0x1800544d6  pop     rbx
0x1800544d7  retn
```
