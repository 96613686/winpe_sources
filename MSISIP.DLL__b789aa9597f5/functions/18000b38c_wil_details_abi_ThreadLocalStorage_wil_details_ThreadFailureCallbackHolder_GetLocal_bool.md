# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000b38c`
- end: `0x18000b3e2`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009474`

## callees

- `0x18000b38c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b399`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b399`

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
0x18000b38c  push    rbx
0x18000b38e  sub     rsp, 20h
0x18000b392  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000b399  call    cs:__imp_GetCurrentThreadId
0x18000b39f  mov     r8d, eax
0x18000b3a2  mov     r9d, eax
0x18000b3a5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000b3af  shr     r8, 2
0x18000b3b3  mul     r8
0x18000b3b6  shr     rdx, 3
0x18000b3ba  lea     rcx, [rdx+rdx*4]
0x18000b3be  add     rcx, rcx
0x18000b3c1  sub     r8, rcx
0x18000b3c4  mov     rax, [rbx+r8*8]
0x18000b3c8  test    rax, rax
0x18000b3cb  jz      short loc_18000B3DC
0x18000b3cd  cmp     [rax], r9d
0x18000b3d0  jz      short loc_18000B3D8
0x18000b3d2  mov     rax, [rax+8]
0x18000b3d6  jmp     short loc_18000B3C8
0x18000b3d8  add     rax, 10h
0x18000b3dc  add     rsp, 20h
0x18000b3e0  pop     rbx
0x18000b3e1  retn
```
