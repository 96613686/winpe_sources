# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18000f8e4`
- end: `0x18000f93a`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f2f4`

## callees

- `0x18000f8e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f8f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f8f1`

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
0x18000f8e4  push    rbx
0x18000f8e6  sub     rsp, 20h
0x18000f8ea  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000f8f1  call    cs:__imp_GetCurrentThreadId
0x18000f8f7  mov     r8d, eax
0x18000f8fa  mov     r9d, eax
0x18000f8fd  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000f907  shr     r8, 2
0x18000f90b  mul     r8
0x18000f90e  shr     rdx, 3
0x18000f912  lea     rcx, [rdx+rdx*4]
0x18000f916  add     rcx, rcx
0x18000f919  sub     r8, rcx
0x18000f91c  mov     rax, [rbx+r8*8]
0x18000f920  test    rax, rax
0x18000f923  jz      short loc_18000F934
0x18000f925  cmp     [rax], r9d
0x18000f928  jz      short loc_18000F930
0x18000f92a  mov     rax, [rax+8]
0x18000f92e  jmp     short loc_18000F920
0x18000f930  add     rax, 10h
0x18000f934  add     rsp, 20h
0x18000f938  pop     rbx
0x18000f939  retn
```
