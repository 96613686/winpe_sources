# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000bf80`
- end: `0x18000bfde`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bf80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bfb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bfb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bfa2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bfa2`

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
0x18000bf80  mov     [rsp+arg_0], rbx
0x18000bf85  mov     [rsp+arg_8], rsi
0x18000bf8a  push    rdi
0x18000bf8b  sub     rsp, 20h
0x18000bf8f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000bf96  mov     rsi, [rdi]
0x18000bf99  jmp     short loc_18000BFB6
0x18000bf9b  mov     rbx, rsi
0x18000bf9e  mov     rsi, [rsi+8]
0x18000bfa2  call    cs:__imp_GetProcessHeap
0x18000bfa8  mov     r8, rbx; lpMem
0x18000bfab  xor     edx, edx; dwFlags
0x18000bfad  mov     rcx, rax; hHeap
0x18000bfb0  call    cs:__imp_HeapFree
0x18000bfb6  test    rsi, rsi
0x18000bfb9  jnz     short loc_18000BF9B
0x18000bfbb  mov     [rdi], rsi
0x18000bfbe  lea     rax, g_header_init_InitializeResultHeader
0x18000bfc5  add     rdi, 8
0x18000bfc9  cmp     rdi, rax
0x18000bfcc  jnz     short loc_18000BF96
0x18000bfce  mov     rbx, [rsp+28h+arg_0]
0x18000bfd3  mov     rsi, [rsp+28h+arg_8]
0x18000bfd8  add     rsp, 20h
0x18000bfdc  pop     rdi
0x18000bfdd  retn
```
