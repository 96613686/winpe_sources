# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140012400`
- end: `0x14001245e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012400`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012430`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012422`

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
0x140012400  mov     [rsp+arg_0], rbx
0x140012405  mov     [rsp+arg_8], rsi
0x14001240a  push    rdi
0x14001240b  sub     rsp, 20h
0x14001240f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140012416  mov     rsi, [rdi]
0x140012419  jmp     short loc_140012436
0x14001241b  mov     rbx, rsi
0x14001241e  mov     rsi, [rsi+8]
0x140012422  call    cs:__imp_GetProcessHeap
0x140012428  mov     r8, rbx; lpMem
0x14001242b  xor     edx, edx; dwFlags
0x14001242d  mov     rcx, rax; hHeap
0x140012430  call    cs:__imp_HeapFree
0x140012436  test    rsi, rsi
0x140012439  jnz     short loc_14001241B
0x14001243b  mov     [rdi], rsi
0x14001243e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140012445  add     rdi, 8
0x140012449  cmp     rdi, rax
0x14001244c  jnz     short loc_140012416
0x14001244e  mov     rbx, [rsp+28h+arg_0]
0x140012453  mov     rsi, [rsp+28h+arg_8]
0x140012458  add     rsp, 20h
0x14001245c  pop     rdi
0x14001245d  retn
```
