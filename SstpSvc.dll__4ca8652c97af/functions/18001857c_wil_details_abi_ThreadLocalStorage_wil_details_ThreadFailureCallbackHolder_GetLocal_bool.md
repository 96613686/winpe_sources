# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x18001857c`
- end: `0x1800185d4`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800180a4`

## callees

- `0x18001857c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018589`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018589`

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
0x18001857c  push    rbx
0x18001857e  sub     rsp, 20h
0x180018582  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180018589  call    cs:__imp_GetCurrentThreadId
0x18001858f  mov     r8d, eax
0x180018592  mov     r9d, eax
0x180018595  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18001859f  shr     r8, 2
0x1800185a3  mul     r8
0x1800185a6  shr     rdx, 3
0x1800185aa  lea     rcx, [rdx+rdx*4]
0x1800185ae  add     rcx, rcx
0x1800185b1  sub     r8, rcx
0x1800185b4  mov     rax, [rbx+r8*8]
0x1800185b8  jmp     short loc_1800185C3
0x1800185ba  cmp     [rax], r9d
0x1800185bd  jz      short loc_1800185CE
0x1800185bf  mov     rax, [rax+8]
0x1800185c3  test    rax, rax
0x1800185c6  jnz     short loc_1800185BA
0x1800185c8  add     rsp, 20h
0x1800185cc  pop     rbx
0x1800185cd  retn
0x1800185ce  add     rax, 10h
0x1800185d2  jmp     short loc_1800185C8
```
