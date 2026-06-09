# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000cd30`
- end: `0x18000cd8e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cd30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd52`

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
0x18000cd30  mov     [rsp+arg_0], rbx
0x18000cd35  mov     [rsp+arg_8], rsi
0x18000cd3a  push    rdi
0x18000cd3b  sub     rsp, 20h
0x18000cd3f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000cd46  mov     rsi, [rdi]
0x18000cd49  jmp     short loc_18000CD66
0x18000cd4b  mov     rbx, rsi
0x18000cd4e  mov     rsi, [rsi+8]
0x18000cd52  call    cs:__imp_GetProcessHeap
0x18000cd58  mov     r8, rbx; lpMem
0x18000cd5b  xor     edx, edx; dwFlags
0x18000cd5d  mov     rcx, rax; hHeap
0x18000cd60  call    cs:__imp_HeapFree
0x18000cd66  test    rsi, rsi
0x18000cd69  jnz     short loc_18000CD4B
0x18000cd6b  mov     [rdi], rsi
0x18000cd6e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18000cd75  add     rdi, 8
0x18000cd79  cmp     rdi, rax
0x18000cd7c  jnz     short loc_18000CD46
0x18000cd7e  mov     rbx, [rsp+28h+arg_0]
0x18000cd83  mov     rsi, [rsp+28h+arg_8]
0x18000cd88  add     rsp, 20h
0x18000cd8c  pop     rdi
0x18000cd8d  retn
```
