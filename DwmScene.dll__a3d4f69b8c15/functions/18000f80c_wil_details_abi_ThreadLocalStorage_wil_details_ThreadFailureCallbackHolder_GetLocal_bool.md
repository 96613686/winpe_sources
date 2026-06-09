# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000f80c`
- end: `0x18000f862`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f334`

## callees

- `0x18000f80c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f819`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f819`

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
0x18000f80c  push    rbx
0x18000f80e  sub     rsp, 20h
0x18000f812  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000f819  call    cs:__imp_GetCurrentThreadId
0x18000f81f  mov     r8d, eax
0x18000f822  mov     r9d, eax
0x18000f825  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000f82f  shr     r8, 2
0x18000f833  mul     r8
0x18000f836  shr     rdx, 3
0x18000f83a  lea     rcx, [rdx+rdx*4]
0x18000f83e  add     rcx, rcx
0x18000f841  sub     r8, rcx
0x18000f844  mov     rax, [rbx+r8*8]
0x18000f848  test    rax, rax
0x18000f84b  jz      short loc_18000F85C
0x18000f84d  cmp     [rax], r9d
0x18000f850  jz      short loc_18000F858
0x18000f852  mov     rax, [rax+8]
0x18000f856  jmp     short loc_18000F848
0x18000f858  add     rax, 10h
0x18000f85c  add     rsp, 20h
0x18000f860  pop     rbx
0x18000f861  retn
```
