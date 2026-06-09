# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800365d0`
- end: `0x18003662e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800365d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036600`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036600`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800365f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800365f2`

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
    result = &g_header_init_InitializeResultHeader;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x1800365d0  mov     [rsp+arg_0], rbx
0x1800365d5  mov     [rsp+arg_8], rsi
0x1800365da  push    rdi
0x1800365db  sub     rsp, 20h
0x1800365df  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800365e6  mov     rsi, [rdi]
0x1800365e9  jmp     short loc_180036606
0x1800365eb  mov     rbx, rsi
0x1800365ee  mov     rsi, [rsi+8]
0x1800365f2  call    cs:__imp_GetProcessHeap
0x1800365f8  mov     r8, rbx; lpMem
0x1800365fb  xor     edx, edx; dwFlags
0x1800365fd  mov     rcx, rax; hHeap
0x180036600  call    cs:__imp_HeapFree
0x180036606  test    rsi, rsi
0x180036609  jnz     short loc_1800365EB
0x18003660b  mov     [rdi], rsi
0x18003660e  lea     rax, g_header_init_InitializeResultHeader
0x180036615  add     rdi, 8
0x180036619  cmp     rdi, rax
0x18003661c  jnz     short loc_1800365E6
0x18003661e  mov     rbx, [rsp+28h+arg_0]
0x180036623  mov     rsi, [rsp+28h+arg_8]
0x180036628  add     rsp, 20h
0x18003662c  pop     rdi
0x18003662d  retn
```
