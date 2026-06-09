# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800114cc`
- end: `0x180011522`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010ff4`

## callees

- `0x1800114cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800114d9`

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
0x1800114cc  push    rbx
0x1800114ce  sub     rsp, 20h
0x1800114d2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800114d9  call    cs:__imp_GetCurrentThreadId
0x1800114df  mov     r8d, eax
0x1800114e2  mov     r9d, eax
0x1800114e5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800114ef  shr     r8, 2
0x1800114f3  mul     r8
0x1800114f6  shr     rdx, 3
0x1800114fa  lea     rcx, [rdx+rdx*4]
0x1800114fe  add     rcx, rcx
0x180011501  sub     r8, rcx
0x180011504  mov     rax, [rbx+r8*8]
0x180011508  test    rax, rax
0x18001150b  jz      short loc_18001151C
0x18001150d  cmp     [rax], r9d
0x180011510  jz      short loc_180011518
0x180011512  mov     rax, [rax+8]
0x180011516  jmp     short loc_180011508
0x180011518  add     rax, 10h
0x18001151c  add     rsp, 20h
0x180011520  pop     rbx
0x180011521  retn
```
