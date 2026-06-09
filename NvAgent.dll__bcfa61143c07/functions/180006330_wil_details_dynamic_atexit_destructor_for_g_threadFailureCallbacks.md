# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180006330`
- end: `0x18000638e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006330`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006352`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006352`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006360`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006360`

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
0x180006330  mov     [rsp+arg_0], rbx
0x180006335  mov     [rsp+arg_8], rsi
0x18000633a  push    rdi
0x18000633b  sub     rsp, 20h
0x18000633f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180006346  mov     rsi, [rdi]
0x180006349  jmp     short loc_180006366
0x18000634b  mov     rbx, rsi
0x18000634e  mov     rsi, [rsi+8]
0x180006352  call    cs:__imp_GetProcessHeap
0x180006358  mov     r8, rbx; lpMem
0x18000635b  xor     edx, edx; dwFlags
0x18000635d  mov     rcx, rax; hHeap
0x180006360  call    cs:__imp_HeapFree
0x180006366  test    rsi, rsi
0x180006369  jnz     short loc_18000634B
0x18000636b  mov     [rdi], rsi
0x18000636e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180006375  add     rdi, 8
0x180006379  cmp     rdi, rax
0x18000637c  jnz     short loc_180006346
0x18000637e  mov     rbx, [rsp+28h+arg_0]
0x180006383  mov     rsi, [rsp+28h+arg_8]
0x180006388  add     rsp, 20h
0x18000638c  pop     rdi
0x18000638d  retn
```
