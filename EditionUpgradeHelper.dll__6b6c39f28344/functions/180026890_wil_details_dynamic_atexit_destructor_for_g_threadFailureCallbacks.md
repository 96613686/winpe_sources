# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180026890`
- end: `0x1800268ee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180026890`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800268b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800268b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800268c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800268c0`

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
0x180026890  mov     [rsp+arg_0], rbx
0x180026895  mov     [rsp+arg_8], rsi
0x18002689a  push    rdi
0x18002689b  sub     rsp, 20h
0x18002689f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800268a6  mov     rsi, [rdi]
0x1800268a9  jmp     short loc_1800268C6
0x1800268ab  mov     rbx, rsi
0x1800268ae  mov     rsi, [rsi+8]
0x1800268b2  call    cs:__imp_GetProcessHeap
0x1800268b8  mov     r8, rbx; lpMem
0x1800268bb  xor     edx, edx; dwFlags
0x1800268bd  mov     rcx, rax; hHeap
0x1800268c0  call    cs:__imp_HeapFree
0x1800268c6  test    rsi, rsi
0x1800268c9  jnz     short loc_1800268AB
0x1800268cb  mov     [rdi], rsi
0x1800268ce  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x1800268d5  add     rdi, 8
0x1800268d9  cmp     rdi, rax
0x1800268dc  jnz     short loc_1800268A6
0x1800268de  mov     rbx, [rsp+28h+arg_0]
0x1800268e3  mov     rsi, [rsp+28h+arg_8]
0x1800268e8  add     rsp, 20h
0x1800268ec  pop     rdi
0x1800268ed  retn
```
