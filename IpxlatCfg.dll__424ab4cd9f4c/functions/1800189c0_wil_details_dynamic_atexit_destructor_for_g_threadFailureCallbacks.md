# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800189c0`
- end: `0x180018a1e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800189c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800189f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800189f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800189e2`

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
0x1800189c0  mov     [rsp+arg_0], rbx
0x1800189c5  mov     [rsp+arg_8], rsi
0x1800189ca  push    rdi
0x1800189cb  sub     rsp, 20h
0x1800189cf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800189d6  mov     rsi, [rdi]
0x1800189d9  jmp     short loc_1800189F6
0x1800189db  mov     rbx, rsi
0x1800189de  mov     rsi, [rsi+8]
0x1800189e2  call    cs:__imp_GetProcessHeap
0x1800189e8  mov     r8, rbx; lpMem
0x1800189eb  xor     edx, edx; dwFlags
0x1800189ed  mov     rcx, rax; hHeap
0x1800189f0  call    cs:__imp_HeapFree
0x1800189f6  test    rsi, rsi
0x1800189f9  jnz     short loc_1800189DB
0x1800189fb  mov     [rdi], rsi
0x1800189fe  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180018a05  add     rdi, 8
0x180018a09  cmp     rdi, rax
0x180018a0c  jnz     short loc_1800189D6
0x180018a0e  mov     rbx, [rsp+28h+arg_0]
0x180018a13  mov     rsi, [rsp+28h+arg_8]
0x180018a18  add     rsp, 20h
0x180018a1c  pop     rdi
0x180018a1d  retn
```
