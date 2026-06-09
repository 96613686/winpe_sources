# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000ba80`
- end: `0x14000bade`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ba80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000baa2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000baa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bab0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bab0`

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
0x14000ba80  mov     [rsp+arg_0], rbx
0x14000ba85  mov     [rsp+arg_8], rsi
0x14000ba8a  push    rdi
0x14000ba8b  sub     rsp, 20h
0x14000ba8f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000ba96  mov     rsi, [rdi]
0x14000ba99  jmp     short loc_14000BAB6
0x14000ba9b  mov     rbx, rsi
0x14000ba9e  mov     rsi, [rsi+8]
0x14000baa2  call    cs:__imp_GetProcessHeap
0x14000baa8  mov     r8, rbx; lpMem
0x14000baab  xor     edx, edx; dwFlags
0x14000baad  mov     rcx, rax; hHeap
0x14000bab0  call    cs:__imp_HeapFree
0x14000bab6  test    rsi, rsi
0x14000bab9  jnz     short loc_14000BA9B
0x14000babb  mov     [rdi], rsi
0x14000babe  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x14000bac5  add     rdi, 8
0x14000bac9  cmp     rdi, rax
0x14000bacc  jnz     short loc_14000BA96
0x14000bace  mov     rbx, [rsp+28h+arg_0]
0x14000bad3  mov     rsi, [rsp+28h+arg_8]
0x14000bad8  add     rsp, 20h
0x14000badc  pop     rdi
0x14000badd  retn
```
