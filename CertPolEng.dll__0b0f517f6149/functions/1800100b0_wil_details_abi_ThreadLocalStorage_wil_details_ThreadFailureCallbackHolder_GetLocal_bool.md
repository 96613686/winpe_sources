# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800100b0`
- end: `0x180010106`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fc78`

## callees

- `0x1800100b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800100bd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800100bd`

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
0x1800100b0  push    rbx
0x1800100b2  sub     rsp, 20h
0x1800100b6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800100bd  call    cs:__imp_GetCurrentThreadId
0x1800100c3  mov     r8d, eax
0x1800100c6  mov     r9d, eax
0x1800100c9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800100d3  shr     r8, 2
0x1800100d7  mul     r8
0x1800100da  shr     rdx, 3
0x1800100de  lea     rcx, [rdx+rdx*4]
0x1800100e2  add     rcx, rcx
0x1800100e5  sub     r8, rcx
0x1800100e8  mov     rax, [rbx+r8*8]
0x1800100ec  test    rax, rax
0x1800100ef  jz      short loc_180010100
0x1800100f1  cmp     [rax], r9d
0x1800100f4  jz      short loc_1800100FC
0x1800100f6  mov     rax, [rax+8]
0x1800100fa  jmp     short loc_1800100EC
0x1800100fc  add     rax, 10h
0x180010100  add     rsp, 20h
0x180010104  pop     rbx
0x180010105  retn
```
