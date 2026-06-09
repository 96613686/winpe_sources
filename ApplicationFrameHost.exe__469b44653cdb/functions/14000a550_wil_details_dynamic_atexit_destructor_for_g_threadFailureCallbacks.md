# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000a550`
- end: `0x14000a5ae`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a550`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a580`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a580`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a572`

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
0x14000a550  mov     [rsp+arg_0], rbx
0x14000a555  mov     [rsp+arg_8], rsi
0x14000a55a  push    rdi
0x14000a55b  sub     rsp, 20h
0x14000a55f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000a566  mov     rsi, [rdi]
0x14000a569  jmp     short loc_14000A586
0x14000a56b  mov     rbx, rsi
0x14000a56e  mov     rsi, [rsi+8]
0x14000a572  call    cs:__imp_GetProcessHeap
0x14000a578  mov     r8, rbx; lpMem
0x14000a57b  xor     edx, edx; dwFlags
0x14000a57d  mov     rcx, rax; hHeap
0x14000a580  call    cs:__imp_HeapFree
0x14000a586  test    rsi, rsi
0x14000a589  jnz     short loc_14000A56B
0x14000a58b  mov     [rdi], rsi
0x14000a58e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x14000a595  add     rdi, 8
0x14000a599  cmp     rdi, rax
0x14000a59c  jnz     short loc_14000A566
0x14000a59e  mov     rbx, [rsp+28h+arg_0]
0x14000a5a3  mov     rsi, [rsp+28h+arg_8]
0x14000a5a8  add     rsp, 20h
0x14000a5ac  pop     rdi
0x14000a5ad  retn
```
