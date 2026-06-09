# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800570d0`
- end: `0x180057126`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180056ae4`

## callees

- `0x1800570d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800570dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800570dd`

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
0x1800570d0  push    rbx
0x1800570d2  sub     rsp, 20h
0x1800570d6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800570dd  call    cs:__imp_GetCurrentThreadId
0x1800570e3  mov     r8d, eax
0x1800570e6  mov     r9d, eax
0x1800570e9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800570f3  shr     r8, 2
0x1800570f7  mul     r8
0x1800570fa  shr     rdx, 3
0x1800570fe  lea     rcx, [rdx+rdx*4]
0x180057102  add     rcx, rcx
0x180057105  sub     r8, rcx
0x180057108  mov     rax, [rbx+r8*8]
0x18005710c  test    rax, rax
0x18005710f  jz      short loc_180057120
0x180057111  cmp     [rax], r9d
0x180057114  jz      short loc_18005711C
0x180057116  mov     rax, [rax+8]
0x18005711a  jmp     short loc_18005710C
0x18005711c  add     rax, 10h
0x180057120  add     rsp, 20h
0x180057124  pop     rbx
0x180057125  retn
```
