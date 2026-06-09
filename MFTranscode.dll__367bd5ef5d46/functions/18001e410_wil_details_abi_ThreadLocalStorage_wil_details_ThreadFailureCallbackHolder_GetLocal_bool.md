# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001e410`
- end: `0x18001e466`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dfd4`

## callees

- `0x18001e410`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e41d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e41d`

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
0x18001e410  push    rbx
0x18001e412  sub     rsp, 20h
0x18001e416  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001e41d  call    cs:__imp_GetCurrentThreadId
0x18001e423  mov     r8d, eax
0x18001e426  mov     r9d, eax
0x18001e429  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001e433  shr     r8, 2
0x18001e437  mul     r8
0x18001e43a  shr     rdx, 3
0x18001e43e  lea     rcx, [rdx+rdx*4]
0x18001e442  add     rcx, rcx
0x18001e445  sub     r8, rcx
0x18001e448  mov     rax, [rbx+r8*8]
0x18001e44c  test    rax, rax
0x18001e44f  jz      short loc_18001E460
0x18001e451  cmp     [rax], r9d
0x18001e454  jz      short loc_18001E45C
0x18001e456  mov     rax, [rax+8]
0x18001e45a  jmp     short loc_18001E44C
0x18001e45c  add     rax, 10h
0x18001e460  add     rsp, 20h
0x18001e464  pop     rbx
0x18001e465  retn
```
