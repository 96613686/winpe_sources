# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180009a20`
- end: `0x180009a7e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009a20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009a50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009a42`

## pseudocode

```c
char *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  char *v0; // rdi
  _QWORD *v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  char *result; // rax

  v0 = (char *)wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *(_QWORD **)v0;
    while ( v1 )
    {
      v2 = v1;
      v1 = (_QWORD *)v1[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *(_QWORD *)v0 = 0;
    result = &g_header_init_InitializeStagingHeaderInternalApi;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x180009a20  mov     [rsp+arg_0], rbx
0x180009a25  mov     [rsp+arg_8], rsi
0x180009a2a  push    rdi
0x180009a2b  sub     rsp, 20h
0x180009a2f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180009a36  mov     rsi, [rdi]
0x180009a39  jmp     short loc_180009A56
0x180009a3b  mov     rbx, rsi
0x180009a3e  mov     rsi, [rsi+8]
0x180009a42  call    cs:__imp_GetProcessHeap
0x180009a48  mov     r8, rbx; lpMem
0x180009a4b  xor     edx, edx; dwFlags
0x180009a4d  mov     rcx, rax; hHeap
0x180009a50  call    cs:__imp_HeapFree
0x180009a56  test    rsi, rsi
0x180009a59  jnz     short loc_180009A3B
0x180009a5b  mov     [rdi], rsi
0x180009a5e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180009a65  add     rdi, 8
0x180009a69  cmp     rdi, rax
0x180009a6c  jnz     short loc_180009A36
0x180009a6e  mov     rbx, [rsp+28h+arg_0]
0x180009a73  mov     rsi, [rsp+28h+arg_8]
0x180009a78  add     rsp, 20h
0x180009a7c  pop     rdi
0x180009a7d  retn
```
