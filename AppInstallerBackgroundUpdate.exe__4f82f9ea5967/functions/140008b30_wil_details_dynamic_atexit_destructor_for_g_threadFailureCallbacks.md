# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140008b30`
- end: `0x140008b8e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008b30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140008b52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008b60`

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
0x140008b30  mov     [rsp+arg_0], rbx
0x140008b35  mov     [rsp+arg_8], rsi
0x140008b3a  push    rdi
0x140008b3b  sub     rsp, 20h
0x140008b3f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140008b46  mov     rsi, [rdi]
0x140008b49  jmp     short loc_140008B66
0x140008b4b  mov     rbx, rsi
0x140008b4e  mov     rsi, [rsi+8]
0x140008b52  call    cs:__imp_GetProcessHeap
0x140008b58  mov     r8, rbx; lpMem
0x140008b5b  xor     edx, edx; dwFlags
0x140008b5d  mov     rcx, rax; hHeap
0x140008b60  call    cs:__imp_HeapFree
0x140008b66  test    rsi, rsi
0x140008b69  jnz     short loc_140008B4B
0x140008b6b  mov     [rdi], rsi
0x140008b6e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140008b75  add     rdi, 8
0x140008b79  cmp     rdi, rax
0x140008b7c  jnz     short loc_140008B46
0x140008b7e  mov     rbx, [rsp+28h+arg_0]
0x140008b83  mov     rsi, [rsp+28h+arg_8]
0x140008b88  add     rsp, 20h
0x140008b8c  pop     rdi
0x140008b8d  retn
```
