# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180008120`
- end: `0x18000817e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008120`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008150`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008150`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008142`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008142`

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
0x180008120  mov     [rsp+arg_0], rbx
0x180008125  mov     [rsp+arg_8], rsi
0x18000812a  push    rdi
0x18000812b  sub     rsp, 20h
0x18000812f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180008136  mov     rsi, [rdi]
0x180008139  jmp     short loc_180008156
0x18000813b  mov     rbx, rsi
0x18000813e  mov     rsi, [rsi+8]
0x180008142  call    cs:__imp_GetProcessHeap
0x180008148  mov     r8, rbx; lpMem
0x18000814b  xor     edx, edx; dwFlags
0x18000814d  mov     rcx, rax; hHeap
0x180008150  call    cs:__imp_HeapFree
0x180008156  test    rsi, rsi
0x180008159  jnz     short loc_18000813B
0x18000815b  mov     [rdi], rsi
0x18000815e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180008165  add     rdi, 8
0x180008169  cmp     rdi, rax
0x18000816c  jnz     short loc_180008136
0x18000816e  mov     rbx, [rsp+28h+arg_0]
0x180008173  mov     rsi, [rsp+28h+arg_8]
0x180008178  add     rsp, 20h
0x18000817c  pop     rdi
0x18000817d  retn
```
