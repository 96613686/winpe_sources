# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140006388`
- end: `0x1400063de`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005f2c`

## callees

- `0x140006388`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006395`

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
0x140006388  push    rbx
0x14000638a  sub     rsp, 20h
0x14000638e  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140006395  call    cs:__imp_GetCurrentThreadId
0x14000639b  mov     r8d, eax
0x14000639e  mov     r9d, eax
0x1400063a1  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400063ab  shr     r8, 2
0x1400063af  mul     r8
0x1400063b2  shr     rdx, 3
0x1400063b6  lea     rcx, [rdx+rdx*4]
0x1400063ba  add     rcx, rcx
0x1400063bd  sub     r8, rcx
0x1400063c0  mov     rax, [rbx+r8*8]
0x1400063c4  test    rax, rax
0x1400063c7  jz      short loc_1400063D8
0x1400063c9  cmp     [rax], r9d
0x1400063cc  jz      short loc_1400063D4
0x1400063ce  mov     rax, [rax+8]
0x1400063d2  jmp     short loc_1400063C4
0x1400063d4  add     rax, 10h
0x1400063d8  add     rsp, 20h
0x1400063dc  pop     rbx
0x1400063dd  retn
```
