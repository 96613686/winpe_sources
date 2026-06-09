# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000e8b0`
- end: `0x14000e90e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000e8b0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000e8e0`
- `KERNEL32!HeapFree` at `0x14000e8e0`
- `KERNEL32!GetProcessHeap` at `0x14000e8d2`
- `KERNEL32!GetProcessHeap` at `0x14000e8d2`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x14000e8b0  mov     [rsp+arg_0], rbx
0x14000e8b5  mov     [rsp+arg_8], rsi
0x14000e8ba  push    rdi
0x14000e8bb  sub     rsp, 20h
0x14000e8bf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000e8c6  mov     rsi, [rdi]
0x14000e8c9  jmp     short loc_14000E8E6
0x14000e8cb  mov     rbx, rsi
0x14000e8ce  mov     rsi, [rsi+8]
0x14000e8d2  call    cs:__imp_GetProcessHeap
0x14000e8d8  mov     r8, rbx; lpMem
0x14000e8db  xor     edx, edx; dwFlags
0x14000e8dd  mov     rcx, rax; hHeap
0x14000e8e0  call    cs:__imp_HeapFree
0x14000e8e6  test    rsi, rsi
0x14000e8e9  jnz     short loc_14000E8CB
0x14000e8eb  mov     [rdi], rsi
0x14000e8ee  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x14000e8f5  add     rdi, 8
0x14000e8f9  cmp     rdi, rax
0x14000e8fc  jnz     short loc_14000E8C6
0x14000e8fe  mov     rbx, [rsp+28h+arg_0]
0x14000e903  mov     rsi, [rsp+28h+arg_8]
0x14000e908  add     rsp, 20h
0x14000e90c  pop     rdi
0x14000e90d  retn
```
