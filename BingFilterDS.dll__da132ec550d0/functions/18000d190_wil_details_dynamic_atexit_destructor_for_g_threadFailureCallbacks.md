# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000d190`
- end: `0x18000d1ee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d190`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d1b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d1c0`

## pseudocode

```c
__int64 *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rdi
  __int64 v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *result; // rax

  v0 = wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = (void *)v1;
      v1 = *(_QWORD *)(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x18000d190  mov     [rsp+arg_0], rbx
0x18000d195  mov     [rsp+arg_8], rsi
0x18000d19a  push    rdi
0x18000d19b  sub     rsp, 20h
0x18000d19f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000d1a6  mov     rsi, [rdi]
0x18000d1a9  jmp     short loc_18000D1C6
0x18000d1ab  mov     rbx, rsi
0x18000d1ae  mov     rsi, [rsi+8]
0x18000d1b2  call    cs:__imp_GetProcessHeap
0x18000d1b8  mov     r8, rbx; lpMem
0x18000d1bb  xor     edx, edx; dwFlags
0x18000d1bd  mov     rcx, rax; hHeap
0x18000d1c0  call    cs:__imp_HeapFree
0x18000d1c6  test    rsi, rsi
0x18000d1c9  jnz     short loc_18000D1AB
0x18000d1cb  mov     [rdi], rsi
0x18000d1ce  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000d1d5  add     rdi, 8
0x18000d1d9  cmp     rdi, rax
0x18000d1dc  jnz     short loc_18000D1A6
0x18000d1de  mov     rbx, [rsp+28h+arg_0]
0x18000d1e3  mov     rsi, [rsp+28h+arg_8]
0x18000d1e8  add     rsp, 20h
0x18000d1ec  pop     rdi
0x18000d1ed  retn
```
