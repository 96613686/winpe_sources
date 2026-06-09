# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000a680`
- end: `0x18000a6de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a680`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a6b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a6a2`

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
    result = g_header_init_InitializeStagingHeaderInternalApi;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x18000a680  mov     [rsp+arg_0], rbx
0x18000a685  mov     [rsp+arg_8], rsi
0x18000a68a  push    rdi
0x18000a68b  sub     rsp, 20h
0x18000a68f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000a696  mov     rsi, [rdi]
0x18000a699  jmp     short loc_18000A6B6
0x18000a69b  mov     rbx, rsi
0x18000a69e  mov     rsi, [rsi+8]
0x18000a6a2  call    cs:__imp_GetProcessHeap
0x18000a6a8  mov     r8, rbx; lpMem
0x18000a6ab  xor     edx, edx; dwFlags
0x18000a6ad  mov     rcx, rax; hHeap
0x18000a6b0  call    cs:__imp_HeapFree
0x18000a6b6  test    rsi, rsi
0x18000a6b9  jnz     short loc_18000A69B
0x18000a6bb  mov     [rdi], rsi
0x18000a6be  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18000a6c5  add     rdi, 8
0x18000a6c9  cmp     rdi, rax
0x18000a6cc  jnz     short loc_18000A696
0x18000a6ce  mov     rbx, [rsp+28h+arg_0]
0x18000a6d3  mov     rsi, [rsp+28h+arg_8]
0x18000a6d8  add     rsp, 20h
0x18000a6dc  pop     rdi
0x18000a6dd  retn
```
