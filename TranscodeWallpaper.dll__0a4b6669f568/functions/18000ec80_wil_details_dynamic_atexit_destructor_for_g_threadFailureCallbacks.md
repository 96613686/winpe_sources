# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000ec80`
- end: `0x18000ecde`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ec80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eca2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eca2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ecb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ecb0`

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
0x18000ec80  mov     [rsp+arg_0], rbx
0x18000ec85  mov     [rsp+arg_8], rsi
0x18000ec8a  push    rdi
0x18000ec8b  sub     rsp, 20h
0x18000ec8f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000ec96  mov     rsi, [rdi]
0x18000ec99  jmp     short loc_18000ECB6
0x18000ec9b  mov     rbx, rsi
0x18000ec9e  mov     rsi, [rsi+8]
0x18000eca2  call    cs:__imp_GetProcessHeap
0x18000eca8  mov     r8, rbx; lpMem
0x18000ecab  xor     edx, edx; dwFlags
0x18000ecad  mov     rcx, rax; hHeap
0x18000ecb0  call    cs:__imp_HeapFree
0x18000ecb6  test    rsi, rsi
0x18000ecb9  jnz     short loc_18000EC9B
0x18000ecbb  mov     [rdi], rsi
0x18000ecbe  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000ecc5  add     rdi, 8
0x18000ecc9  cmp     rdi, rax
0x18000eccc  jnz     short loc_18000EC96
0x18000ecce  mov     rbx, [rsp+28h+arg_0]
0x18000ecd3  mov     rsi, [rsp+28h+arg_8]
0x18000ecd8  add     rsp, 20h
0x18000ecdc  pop     rdi
0x18000ecdd  retn
```
