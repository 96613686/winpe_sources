# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000c7e0`
- end: `0x18000c83e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c7e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c802`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c802`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c810`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c810`

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
0x18000c7e0  mov     [rsp+arg_0], rbx
0x18000c7e5  mov     [rsp+arg_8], rsi
0x18000c7ea  push    rdi
0x18000c7eb  sub     rsp, 20h
0x18000c7ef  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000c7f6  mov     rsi, [rdi]
0x18000c7f9  jmp     short loc_18000C816
0x18000c7fb  mov     rbx, rsi
0x18000c7fe  mov     rsi, [rsi+8]
0x18000c802  call    cs:__imp_GetProcessHeap
0x18000c808  mov     r8, rbx; lpMem
0x18000c80b  xor     edx, edx; dwFlags
0x18000c80d  mov     rcx, rax; hHeap
0x18000c810  call    cs:__imp_HeapFree
0x18000c816  test    rsi, rsi
0x18000c819  jnz     short loc_18000C7FB
0x18000c81b  mov     [rdi], rsi
0x18000c81e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000c825  add     rdi, 8
0x18000c829  cmp     rdi, rax
0x18000c82c  jnz     short loc_18000C7F6
0x18000c82e  mov     rbx, [rsp+28h+arg_0]
0x18000c833  mov     rsi, [rsp+28h+arg_8]
0x18000c838  add     rsp, 20h
0x18000c83c  pop     rdi
0x18000c83d  retn
```
