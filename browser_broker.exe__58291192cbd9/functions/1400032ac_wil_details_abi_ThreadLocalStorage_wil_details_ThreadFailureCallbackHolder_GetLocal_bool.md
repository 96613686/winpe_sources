# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1400032ac`
- end: `0x140003302`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002dd4`

## callees

- `0x1400032ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400032b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400032b9`

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
0x1400032ac  push    rbx
0x1400032ae  sub     rsp, 20h
0x1400032b2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400032b9  call    cs:__imp_GetCurrentThreadId
0x1400032bf  mov     r8d, eax
0x1400032c2  mov     r9d, eax
0x1400032c5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400032cf  shr     r8, 2
0x1400032d3  mul     r8
0x1400032d6  shr     rdx, 3
0x1400032da  lea     rcx, [rdx+rdx*4]
0x1400032de  add     rcx, rcx
0x1400032e1  sub     r8, rcx
0x1400032e4  mov     rax, [rbx+r8*8]
0x1400032e8  test    rax, rax
0x1400032eb  jz      short loc_1400032FC
0x1400032ed  cmp     [rax], r9d
0x1400032f0  jz      short loc_1400032F8
0x1400032f2  mov     rax, [rax+8]
0x1400032f6  jmp     short loc_1400032E8
0x1400032f8  add     rax, 10h
0x1400032fc  add     rsp, 20h
0x140003300  pop     rbx
0x140003301  retn
```
