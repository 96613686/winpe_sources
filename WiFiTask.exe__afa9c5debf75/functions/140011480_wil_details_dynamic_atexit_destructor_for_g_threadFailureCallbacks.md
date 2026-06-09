# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140011480`
- end: `0x1400114de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011480`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400114b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400114b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400114a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400114a2`

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
0x140011480  mov     [rsp+arg_0], rbx
0x140011485  mov     [rsp+arg_8], rsi
0x14001148a  push    rdi
0x14001148b  sub     rsp, 20h
0x14001148f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140011496  mov     rsi, [rdi]
0x140011499  jmp     short loc_1400114B6
0x14001149b  mov     rbx, rsi
0x14001149e  mov     rsi, [rsi+8]
0x1400114a2  call    cs:__imp_GetProcessHeap
0x1400114a8  mov     r8, rbx; lpMem
0x1400114ab  xor     edx, edx; dwFlags
0x1400114ad  mov     rcx, rax; hHeap
0x1400114b0  call    cs:__imp_HeapFree
0x1400114b6  test    rsi, rsi
0x1400114b9  jnz     short loc_14001149B
0x1400114bb  mov     [rdi], rsi
0x1400114be  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x1400114c5  add     rdi, 8
0x1400114c9  cmp     rdi, rax
0x1400114cc  jnz     short loc_140011496
0x1400114ce  mov     rbx, [rsp+28h+arg_0]
0x1400114d3  mov     rsi, [rsp+28h+arg_8]
0x1400114d8  add     rsp, 20h
0x1400114dc  pop     rdi
0x1400114dd  retn
```
