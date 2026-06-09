# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000ffc0`
- end: `0x14001001e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ffc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ffe2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ffe2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000fff0`

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
0x14000ffc0  mov     [rsp+arg_0], rbx
0x14000ffc5  mov     [rsp+arg_8], rsi
0x14000ffca  push    rdi
0x14000ffcb  sub     rsp, 20h
0x14000ffcf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000ffd6  mov     rsi, [rdi]
0x14000ffd9  jmp     short loc_14000FFF6
0x14000ffdb  mov     rbx, rsi
0x14000ffde  mov     rsi, [rsi+8]
0x14000ffe2  call    cs:__imp_GetProcessHeap
0x14000ffe8  mov     r8, rbx; lpMem
0x14000ffeb  xor     edx, edx; dwFlags
0x14000ffed  mov     rcx, rax; hHeap
0x14000fff0  call    cs:__imp_HeapFree
0x14000fff6  test    rsi, rsi
0x14000fff9  jnz     short loc_14000FFDB
0x14000fffb  mov     [rdi], rsi
0x14000fffe  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x140010005  add     rdi, 8
0x140010009  cmp     rdi, rax
0x14001000c  jnz     short loc_14000FFD6
0x14001000e  mov     rbx, [rsp+28h+arg_0]
0x140010013  mov     rsi, [rsp+28h+arg_8]
0x140010018  add     rsp, 20h
0x14001001c  pop     rdi
0x14001001d  retn
```
