# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180003c64`
- end: `0x180003cc1`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003764`

## callees

- `0x180003c64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c71`

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
0x180003c64  push    rbx
0x180003c66  sub     rsp, 20h
0x180003c6a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003c71  call    cs:__imp_GetCurrentThreadId
0x180003c78  nop     dword ptr [rax+rax+00h]
0x180003c7d  mov     r8d, eax
0x180003c80  mov     r9d, eax
0x180003c83  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003c8d  shr     r8, 2
0x180003c91  mul     r8
0x180003c94  shr     rdx, 3
0x180003c98  lea     rcx, [rdx+rdx*4]
0x180003c9c  add     rcx, rcx
0x180003c9f  sub     r8, rcx
0x180003ca2  mov     rax, [rbx+r8*8]
0x180003ca6  test    rax, rax
0x180003ca9  jz      short loc_180003CBA
0x180003cab  cmp     [rax], r9d
0x180003cae  jz      short loc_180003CB6
0x180003cb0  mov     rax, [rax+8]
0x180003cb4  jmp     short loc_180003CA6
0x180003cb6  add     rax, 10h
0x180003cba  add     rsp, 20h
0x180003cbe  pop     rbx
0x180003cbf  retn
```
