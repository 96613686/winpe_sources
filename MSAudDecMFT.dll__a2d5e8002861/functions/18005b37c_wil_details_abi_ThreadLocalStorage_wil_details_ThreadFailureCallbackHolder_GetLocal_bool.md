# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18005b37c`
- end: `0x18005b3d9`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005ab64`

## callees

- `0x18005b37c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b389`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b389`

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
0x18005b37c  push    rbx
0x18005b37e  sub     rsp, 20h
0x18005b382  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18005b389  call    cs:__imp_GetCurrentThreadId
0x18005b390  nop     dword ptr [rax+rax+00h]
0x18005b395  mov     r9d, eax
0x18005b398  mov     r8d, eax
0x18005b39b  shr     r8, 2
0x18005b39f  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18005b3a9  mul     r8
0x18005b3ac  shr     rdx, 3
0x18005b3b0  lea     rcx, [rdx+rdx*4]
0x18005b3b4  add     rcx, rcx
0x18005b3b7  sub     r8, rcx
0x18005b3ba  mov     rax, [rbx+r8*8]
0x18005b3be  test    rax, rax
0x18005b3c1  jz      short loc_18005B3D2
0x18005b3c3  cmp     [rax], r9d
0x18005b3c6  jz      short loc_18005B3CE
0x18005b3c8  mov     rax, [rax+8]
0x18005b3cc  jmp     short loc_18005B3BE
0x18005b3ce  add     rax, 10h
0x18005b3d2  add     rsp, 20h
0x18005b3d6  pop     rbx
0x18005b3d7  retn
```
