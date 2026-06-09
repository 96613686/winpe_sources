# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140012470`
- end: `0x1400124ce`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012470`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400124a0`
- `KERNEL32!HeapFree` at `0x1400124a0`
- `KERNEL32!GetProcessHeap` at `0x140012492`
- `KERNEL32!GetProcessHeap` at `0x140012492`

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
0x140012470  mov     [rsp+arg_0], rbx
0x140012475  mov     [rsp+arg_8], rsi
0x14001247a  push    rdi
0x14001247b  sub     rsp, 20h
0x14001247f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140012486  mov     rsi, [rdi]
0x140012489  jmp     short loc_1400124A6
0x14001248b  mov     rbx, rsi
0x14001248e  mov     rsi, [rsi+8]
0x140012492  call    cs:__imp_GetProcessHeap
0x140012498  mov     r8, rbx; lpMem
0x14001249b  xor     edx, edx; dwFlags
0x14001249d  mov     rcx, rax; hHeap
0x1400124a0  call    cs:__imp_HeapFree
0x1400124a6  test    rsi, rsi
0x1400124a9  jnz     short loc_14001248B
0x1400124ab  mov     [rdi], rsi
0x1400124ae  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1400124b5  add     rdi, 8
0x1400124b9  cmp     rdi, rax
0x1400124bc  jnz     short loc_140012486
0x1400124be  mov     rbx, [rsp+28h+arg_0]
0x1400124c3  mov     rsi, [rsp+28h+arg_8]
0x1400124c8  add     rsp, 20h
0x1400124cc  pop     rdi
0x1400124cd  retn
```
