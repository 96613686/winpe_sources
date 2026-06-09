# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180013d00`
- end: `0x180013d5e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013d00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013d30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013d30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013d22`

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
0x180013d00  mov     [rsp+arg_0], rbx
0x180013d05  mov     [rsp+arg_8], rsi
0x180013d0a  push    rdi
0x180013d0b  sub     rsp, 20h
0x180013d0f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180013d16  mov     rsi, [rdi]
0x180013d19  jmp     short loc_180013D36
0x180013d1b  mov     rbx, rsi
0x180013d1e  mov     rsi, [rsi+8]
0x180013d22  call    cs:__imp_GetProcessHeap
0x180013d28  mov     r8, rbx; lpMem
0x180013d2b  xor     edx, edx; dwFlags
0x180013d2d  mov     rcx, rax; hHeap
0x180013d30  call    cs:__imp_HeapFree
0x180013d36  test    rsi, rsi
0x180013d39  jnz     short loc_180013D1B
0x180013d3b  mov     [rdi], rsi
0x180013d3e  lea     rax, g_header_init_InitializeResultHeader
0x180013d45  add     rdi, 8
0x180013d49  cmp     rdi, rax
0x180013d4c  jnz     short loc_180013D16
0x180013d4e  mov     rbx, [rsp+28h+arg_0]
0x180013d53  mov     rsi, [rsp+28h+arg_8]
0x180013d58  add     rsp, 20h
0x180013d5c  pop     rdi
0x180013d5d  retn
```
