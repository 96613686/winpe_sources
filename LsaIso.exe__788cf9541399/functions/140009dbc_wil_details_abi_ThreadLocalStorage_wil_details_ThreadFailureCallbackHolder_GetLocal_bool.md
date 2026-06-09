# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x140009dbc`
- end: `0x140009e12`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400098f0`

## callees

- `0x140009dbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009dc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009dc9`

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
0x140009dbc  push    rbx
0x140009dbe  sub     rsp, 20h
0x140009dc2  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140009dc9  call    cs:__imp_GetCurrentThreadId
0x140009dcf  mov     r8d, eax
0x140009dd2  mov     r9d, eax
0x140009dd5  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140009ddf  shr     r8, 2
0x140009de3  mul     r8
0x140009de6  shr     rdx, 3
0x140009dea  lea     rcx, [rdx+rdx*4]
0x140009dee  add     rcx, rcx
0x140009df1  sub     r8, rcx
0x140009df4  mov     rax, [rbx+r8*8]
0x140009df8  test    rax, rax
0x140009dfb  jz      short loc_140009E0C
0x140009dfd  cmp     [rax], r9d
0x140009e00  jz      short loc_140009E08
0x140009e02  mov     rax, [rax+8]
0x140009e06  jmp     short loc_140009DF8
0x140009e08  add     rax, 10h
0x140009e0c  add     rsp, 20h
0x140009e10  pop     rbx
0x140009e11  retn
```
