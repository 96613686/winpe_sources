# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000680c`
- end: `0x180006862`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b54`

## callees

- `0x18000680c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006819`

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
0x18000680c  push    rbx
0x18000680e  sub     rsp, 20h
0x180006812  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006819  call    cs:__imp_GetCurrentThreadId
0x18000681f  mov     r8d, eax
0x180006822  mov     r9d, eax
0x180006825  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000682f  shr     r8, 2
0x180006833  mul     r8
0x180006836  shr     rdx, 3
0x18000683a  lea     rcx, [rdx+rdx*4]
0x18000683e  add     rcx, rcx
0x180006841  sub     r8, rcx
0x180006844  mov     rax, [rbx+r8*8]
0x180006848  test    rax, rax
0x18000684b  jz      short loc_18000685C
0x18000684d  cmp     [rax], r9d
0x180006850  jz      short loc_180006858
0x180006852  mov     rax, [rax+8]
0x180006856  jmp     short loc_180006848
0x180006858  add     rax, 10h
0x18000685c  add     rsp, 20h
0x180006860  pop     rbx
0x180006861  retn
```
