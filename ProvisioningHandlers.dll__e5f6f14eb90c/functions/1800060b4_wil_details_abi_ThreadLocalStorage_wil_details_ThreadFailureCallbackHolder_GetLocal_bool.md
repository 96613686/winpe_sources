# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)

- ea: `0x1800060b4`
- end: `0x180006111`
- name: `?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005bb4`

## callees

- `0x1800060b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800060c1`

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
0x1800060b4  push    rbx
0x1800060b6  sub     rsp, 20h
0x1800060ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800060c1  call    cs:__imp_GetCurrentThreadId
0x1800060c8  nop     dword ptr [rax+rax+00h]
0x1800060cd  mov     r8d, eax
0x1800060d0  mov     r9d, eax
0x1800060d3  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800060dd  shr     r8, 2
0x1800060e1  mul     r8
0x1800060e4  shr     rdx, 3
0x1800060e8  lea     rcx, [rdx+rdx*4]
0x1800060ec  add     rcx, rcx
0x1800060ef  sub     r8, rcx
0x1800060f2  mov     rax, [rbx+r8*8]
0x1800060f6  test    rax, rax
0x1800060f9  jz      short loc_18000610A
0x1800060fb  cmp     [rax], r9d
0x1800060fe  jz      short loc_180006106
0x180006100  mov     rax, [rax+8]
0x180006104  jmp     short loc_1800060F6
0x180006106  add     rax, 10h
0x18000610a  add     rsp, 20h
0x18000610e  pop     rbx
0x18000610f  retn
```
