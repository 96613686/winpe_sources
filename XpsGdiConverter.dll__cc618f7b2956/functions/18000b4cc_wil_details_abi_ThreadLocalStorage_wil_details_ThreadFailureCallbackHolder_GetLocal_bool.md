# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000b4cc`
- end: `0x18000b522`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aff4`

## callees

- `0x18000b4cc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000b4d9`
- `KERNEL32!GetCurrentThreadId` at `0x18000b4d9`

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
0x18000b4cc  push    rbx
0x18000b4ce  sub     rsp, 20h
0x18000b4d2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b4d9  call    cs:__imp_GetCurrentThreadId
0x18000b4df  mov     r8d, eax
0x18000b4e2  mov     r9d, eax
0x18000b4e5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b4ef  shr     r8, 2
0x18000b4f3  mul     r8
0x18000b4f6  shr     rdx, 3
0x18000b4fa  lea     rcx, [rdx+rdx*4]
0x18000b4fe  add     rcx, rcx
0x18000b501  sub     r8, rcx
0x18000b504  mov     rax, [rbx+r8*8]
0x18000b508  test    rax, rax
0x18000b50b  jz      short loc_18000B51C
0x18000b50d  cmp     [rax], r9d
0x18000b510  jz      short loc_18000B518
0x18000b512  mov     rax, [rax+8]
0x18000b516  jmp     short loc_18000B508
0x18000b518  add     rax, 10h
0x18000b51c  add     rsp, 20h
0x18000b520  pop     rbx
0x18000b521  retn
```
