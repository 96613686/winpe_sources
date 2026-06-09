# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000ef90`
- end: `0x14000efee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ef90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000efc0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000efc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000efb2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000efb2`

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
0x14000ef90  mov     [rsp+arg_0], rbx
0x14000ef95  mov     [rsp+arg_8], rsi
0x14000ef9a  push    rdi
0x14000ef9b  sub     rsp, 20h
0x14000ef9f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000efa6  mov     rsi, [rdi]
0x14000efa9  jmp     short loc_14000EFC6
0x14000efab  mov     rbx, rsi
0x14000efae  mov     rsi, [rsi+8]
0x14000efb2  call    cs:__imp_GetProcessHeap
0x14000efb8  mov     r8, rbx; lpMem
0x14000efbb  xor     edx, edx; dwFlags
0x14000efbd  mov     rcx, rax; hHeap
0x14000efc0  call    cs:__imp_HeapFree
0x14000efc6  test    rsi, rsi
0x14000efc9  jnz     short loc_14000EFAB
0x14000efcb  mov     [rdi], rsi
0x14000efce  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x14000efd5  add     rdi, 8
0x14000efd9  cmp     rdi, rax
0x14000efdc  jnz     short loc_14000EFA6
0x14000efde  mov     rbx, [rsp+28h+arg_0]
0x14000efe3  mov     rsi, [rsp+28h+arg_8]
0x14000efe8  add     rsp, 20h
0x14000efec  pop     rdi
0x14000efed  retn
```
