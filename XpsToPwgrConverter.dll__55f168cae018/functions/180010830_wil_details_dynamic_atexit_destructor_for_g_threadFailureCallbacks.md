# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180010830`
- end: `0x18001088e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010830`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010860`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010860`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010852`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010852`

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
0x180010830  mov     [rsp+arg_0], rbx
0x180010835  mov     [rsp+arg_8], rsi
0x18001083a  push    rdi
0x18001083b  sub     rsp, 20h
0x18001083f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180010846  mov     rsi, [rdi]
0x180010849  jmp     short loc_180010866
0x18001084b  mov     rbx, rsi
0x18001084e  mov     rsi, [rsi+8]
0x180010852  call    cs:__imp_GetProcessHeap
0x180010858  mov     r8, rbx; lpMem
0x18001085b  xor     edx, edx; dwFlags
0x18001085d  mov     rcx, rax; hHeap
0x180010860  call    cs:__imp_HeapFree
0x180010866  test    rsi, rsi
0x180010869  jnz     short loc_18001084B
0x18001086b  mov     [rdi], rsi
0x18001086e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180010875  add     rdi, 8
0x180010879  cmp     rdi, rax
0x18001087c  jnz     short loc_180010846
0x18001087e  mov     rbx, [rsp+28h+arg_0]
0x180010883  mov     rsi, [rsp+28h+arg_8]
0x180010888  add     rsp, 20h
0x18001088c  pop     rdi
0x18001088d  retn
```
