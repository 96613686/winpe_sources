# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180052294`
- end: `0x1800522ea`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18005211c`

## callees

- `0x180052294`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800522a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800522a1`

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
0x180052294  push    rbx
0x180052296  sub     rsp, 20h
0x18005229a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800522a1  call    cs:__imp_GetCurrentThreadId
0x1800522a7  mov     r8d, eax
0x1800522aa  mov     r9d, eax
0x1800522ad  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800522b7  shr     r8, 2
0x1800522bb  mul     r8
0x1800522be  shr     rdx, 3
0x1800522c2  lea     rcx, [rdx+rdx*4]
0x1800522c6  add     rcx, rcx
0x1800522c9  sub     r8, rcx
0x1800522cc  mov     rax, [rbx+r8*8]
0x1800522d0  test    rax, rax
0x1800522d3  jz      short loc_1800522E4
0x1800522d5  cmp     [rax], r9d
0x1800522d8  jz      short loc_1800522E0
0x1800522da  mov     rax, [rax+8]
0x1800522de  jmp     short loc_1800522D0
0x1800522e0  add     rax, 10h
0x1800522e4  add     rsp, 20h
0x1800522e8  pop     rbx
0x1800522e9  retn
```
