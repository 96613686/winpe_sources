# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180022bf0`
- end: `0x180022c4e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180022bf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022c20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022c20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022c12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022c12`

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
0x180022bf0  mov     [rsp+arg_0], rbx
0x180022bf5  mov     [rsp+arg_8], rsi
0x180022bfa  push    rdi
0x180022bfb  sub     rsp, 20h
0x180022bff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180022c06  mov     rsi, [rdi]
0x180022c09  jmp     short loc_180022C26
0x180022c0b  mov     rbx, rsi
0x180022c0e  mov     rsi, [rsi+8]
0x180022c12  call    cs:__imp_GetProcessHeap
0x180022c18  mov     r8, rbx; lpMem
0x180022c1b  xor     edx, edx; dwFlags
0x180022c1d  mov     rcx, rax; hHeap
0x180022c20  call    cs:__imp_HeapFree
0x180022c26  test    rsi, rsi
0x180022c29  jnz     short loc_180022C0B
0x180022c2b  mov     [rdi], rsi
0x180022c2e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180022c35  add     rdi, 8
0x180022c39  cmp     rdi, rax
0x180022c3c  jnz     short loc_180022C06
0x180022c3e  mov     rbx, [rsp+28h+arg_0]
0x180022c43  mov     rsi, [rsp+28h+arg_8]
0x180022c48  add     rsp, 20h
0x180022c4c  pop     rdi
0x180022c4d  retn
```
