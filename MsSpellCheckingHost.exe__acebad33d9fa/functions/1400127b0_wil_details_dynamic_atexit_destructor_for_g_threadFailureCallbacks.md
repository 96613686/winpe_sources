# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400127b0`
- end: `0x14001280e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400127b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400127e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400127e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400127d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400127d2`

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
    result = &g_header_init_InitializeResultHeader;
    ++v0;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x1400127b0  mov     [rsp+arg_0], rbx
0x1400127b5  mov     [rsp+arg_8], rsi
0x1400127ba  push    rdi
0x1400127bb  sub     rsp, 20h
0x1400127bf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1400127c6  mov     rsi, [rdi]
0x1400127c9  jmp     short loc_1400127E6
0x1400127cb  mov     rbx, rsi
0x1400127ce  mov     rsi, [rsi+8]
0x1400127d2  call    cs:__imp_GetProcessHeap
0x1400127d8  mov     r8, rbx; lpMem
0x1400127db  xor     edx, edx; dwFlags
0x1400127dd  mov     rcx, rax; hHeap
0x1400127e0  call    cs:__imp_HeapFree
0x1400127e6  test    rsi, rsi
0x1400127e9  jnz     short loc_1400127CB
0x1400127eb  mov     [rdi], rsi
0x1400127ee  lea     rax, g_header_init_InitializeResultHeader
0x1400127f5  add     rdi, 8
0x1400127f9  cmp     rdi, rax
0x1400127fc  jnz     short loc_1400127C6
0x1400127fe  mov     rbx, [rsp+28h+arg_0]
0x140012803  mov     rsi, [rsp+28h+arg_8]
0x140012808  add     rsp, 20h
0x14001280c  pop     rdi
0x14001280d  retn
```
