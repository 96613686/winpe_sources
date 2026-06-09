# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000992c`
- end: `0x180009982`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009454`

## callees

- `0x18000992c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009939`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009939`

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
0x18000992c  push    rbx
0x18000992e  sub     rsp, 20h
0x180009932  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009939  call    cs:__imp_GetCurrentThreadId
0x18000993f  mov     r8d, eax
0x180009942  mov     r9d, eax
0x180009945  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000994f  shr     r8, 2
0x180009953  mul     r8
0x180009956  shr     rdx, 3
0x18000995a  lea     rcx, [rdx+rdx*4]
0x18000995e  add     rcx, rcx
0x180009961  sub     r8, rcx
0x180009964  mov     rax, [rbx+r8*8]
0x180009968  test    rax, rax
0x18000996b  jz      short loc_18000997C
0x18000996d  cmp     [rax], r9d
0x180009970  jz      short loc_180009978
0x180009972  mov     rax, [rax+8]
0x180009976  jmp     short loc_180009968
0x180009978  add     rax, 10h
0x18000997c  add     rsp, 20h
0x180009980  pop     rbx
0x180009981  retn
```
