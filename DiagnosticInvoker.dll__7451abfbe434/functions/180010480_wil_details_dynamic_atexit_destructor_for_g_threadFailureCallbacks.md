# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180010480`
- end: `0x1800104de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010480`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800104a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800104a2`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x180010480  mov     [rsp+arg_0], rbx
0x180010485  mov     [rsp+arg_8], rsi
0x18001048a  push    rdi
0x18001048b  sub     rsp, 20h
0x18001048f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180010496  mov     rsi, [rdi]
0x180010499  jmp     short loc_1800104B6
0x18001049b  mov     rbx, rsi
0x18001049e  mov     rsi, [rsi+8]
0x1800104a2  call    cs:__imp_GetProcessHeap
0x1800104a8  mov     r8, rbx; lpMem
0x1800104ab  xor     edx, edx; dwFlags
0x1800104ad  mov     rcx, rax; hHeap
0x1800104b0  call    cs:__imp_HeapFree
0x1800104b6  test    rsi, rsi
0x1800104b9  jnz     short loc_18001049B
0x1800104bb  mov     [rdi], rsi
0x1800104be  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1800104c5  add     rdi, 8
0x1800104c9  cmp     rdi, rax
0x1800104cc  jnz     short loc_180010496
0x1800104ce  mov     rbx, [rsp+28h+arg_0]
0x1800104d3  mov     rsi, [rsp+28h+arg_8]
0x1800104d8  add     rsp, 20h
0x1800104dc  pop     rdi
0x1800104dd  retn
```
