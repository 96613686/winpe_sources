# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000d900`
- end: `0x18000d95e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d900`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d930`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d930`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d922`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d922`

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
0x18000d900  mov     [rsp+arg_0], rbx
0x18000d905  mov     [rsp+arg_8], rsi
0x18000d90a  push    rdi
0x18000d90b  sub     rsp, 20h
0x18000d90f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000d916  mov     rsi, [rdi]
0x18000d919  jmp     short loc_18000D936
0x18000d91b  mov     rbx, rsi
0x18000d91e  mov     rsi, [rsi+8]
0x18000d922  call    cs:__imp_GetProcessHeap
0x18000d928  mov     r8, rbx; lpMem
0x18000d92b  xor     edx, edx; dwFlags
0x18000d92d  mov     rcx, rax; hHeap
0x18000d930  call    cs:__imp_HeapFree
0x18000d936  test    rsi, rsi
0x18000d939  jnz     short loc_18000D91B
0x18000d93b  mov     [rdi], rsi
0x18000d93e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18000d945  add     rdi, 8
0x18000d949  cmp     rdi, rax
0x18000d94c  jnz     short loc_18000D916
0x18000d94e  mov     rbx, [rsp+28h+arg_0]
0x18000d953  mov     rsi, [rsp+28h+arg_8]
0x18000d958  add     rsp, 20h
0x18000d95c  pop     rdi
0x18000d95d  retn
```
