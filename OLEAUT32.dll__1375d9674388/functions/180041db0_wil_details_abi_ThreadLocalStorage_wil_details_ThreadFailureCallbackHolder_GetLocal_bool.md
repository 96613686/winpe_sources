# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x180041db0`
- end: `0x180041e08`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180038d84`

## callees

- `0x180041db0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041dbd`

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
0x180041db0  push    rbx
0x180041db2  sub     rsp, 20h
0x180041db6  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180041dbd  call    cs:__imp_GetCurrentThreadId
0x180041dc3  mov     r8d, eax
0x180041dc6  mov     r9d, eax
0x180041dc9  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180041dd3  shr     r8, 2
0x180041dd7  mul     r8
0x180041dda  shr     rdx, 3
0x180041dde  lea     rcx, [rdx+rdx*4]
0x180041de2  add     rcx, rcx
0x180041de5  sub     r8, rcx
0x180041de8  mov     rax, [rbx+r8*8]
0x180041dec  test    rax, rax
0x180041def  jnz     short loc_180041DF7
0x180041df1  add     rsp, 20h
0x180041df5  pop     rbx
0x180041df6  retn
0x180041df7  cmp     [rax], r9d
0x180041dfa  jz      short loc_180041E02
0x180041dfc  mov     rax, [rax+8]
0x180041e00  jmp     short loc_180041DEC
0x180041e02  add     rax, 10h
0x180041e06  jmp     short loc_180041DF1
```
