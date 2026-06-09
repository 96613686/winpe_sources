# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180016670`
- end: `0x1800166c6`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001623c`

## callees

- `0x180016670`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001667d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001667d`

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
0x180016670  push    rbx
0x180016672  sub     rsp, 20h
0x180016676  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18001667d  call    cs:__imp_GetCurrentThreadId
0x180016683  mov     r8d, eax
0x180016686  mov     r9d, eax
0x180016689  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180016693  shr     r8, 2
0x180016697  mul     r8
0x18001669a  shr     rdx, 3
0x18001669e  lea     rcx, [rdx+rdx*4]
0x1800166a2  add     rcx, rcx
0x1800166a5  sub     r8, rcx
0x1800166a8  mov     rax, [rbx+r8*8]
0x1800166ac  test    rax, rax
0x1800166af  jz      short loc_1800166C0
0x1800166b1  cmp     [rax], r9d
0x1800166b4  jz      short loc_1800166BC
0x1800166b6  mov     rax, [rax+8]
0x1800166ba  jmp     short loc_1800166AC
0x1800166bc  add     rax, 10h
0x1800166c0  add     rsp, 20h
0x1800166c4  pop     rbx
0x1800166c5  retn
```
