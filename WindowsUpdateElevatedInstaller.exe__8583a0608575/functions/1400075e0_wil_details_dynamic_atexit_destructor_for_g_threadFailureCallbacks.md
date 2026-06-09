# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400075e0`
- end: `0x14000763e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400075e0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140007610`
- `KERNEL32!HeapFree` at `0x140007610`
- `KERNEL32!GetProcessHeap` at `0x140007602`
- `KERNEL32!GetProcessHeap` at `0x140007602`

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
0x1400075e0  mov     [rsp+arg_0], rbx
0x1400075e5  mov     [rsp+arg_8], rsi
0x1400075ea  push    rdi
0x1400075eb  sub     rsp, 20h
0x1400075ef  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1400075f6  mov     rsi, [rdi]
0x1400075f9  jmp     short loc_140007616
0x1400075fb  mov     rbx, rsi
0x1400075fe  mov     rsi, [rsi+8]
0x140007602  call    cs:__imp_GetProcessHeap
0x140007608  mov     r8, rbx; lpMem
0x14000760b  xor     edx, edx; dwFlags
0x14000760d  mov     rcx, rax; hHeap
0x140007610  call    cs:__imp_HeapFree
0x140007616  test    rsi, rsi
0x140007619  jnz     short loc_1400075FB
0x14000761b  mov     [rdi], rsi
0x14000761e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140007625  add     rdi, 8
0x140007629  cmp     rdi, rax
0x14000762c  jnz     short loc_1400075F6
0x14000762e  mov     rbx, [rsp+28h+arg_0]
0x140007633  mov     rsi, [rsp+28h+arg_8]
0x140007638  add     rsp, 20h
0x14000763c  pop     rdi
0x14000763d  retn
```
