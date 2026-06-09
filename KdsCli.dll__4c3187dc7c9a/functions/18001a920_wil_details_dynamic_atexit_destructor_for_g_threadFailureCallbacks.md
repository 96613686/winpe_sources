# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001a920`
- end: `0x18001a97e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a920`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a950`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a950`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a942`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a942`

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
0x18001a920  mov     [rsp+arg_0], rbx
0x18001a925  mov     [rsp+arg_8], rsi
0x18001a92a  push    rdi
0x18001a92b  sub     rsp, 20h
0x18001a92f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001a936  mov     rsi, [rdi]
0x18001a939  jmp     short loc_18001A956
0x18001a93b  mov     rbx, rsi
0x18001a93e  mov     rsi, [rsi+8]
0x18001a942  call    cs:__imp_GetProcessHeap
0x18001a948  mov     r8, rbx; lpMem
0x18001a94b  xor     edx, edx; dwFlags
0x18001a94d  mov     rcx, rax; hHeap
0x18001a950  call    cs:__imp_HeapFree
0x18001a956  test    rsi, rsi
0x18001a959  jnz     short loc_18001A93B
0x18001a95b  mov     [rdi], rsi
0x18001a95e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18001a965  add     rdi, 8
0x18001a969  cmp     rdi, rax
0x18001a96c  jnz     short loc_18001A936
0x18001a96e  mov     rbx, [rsp+28h+arg_0]
0x18001a973  mov     rsi, [rsp+28h+arg_8]
0x18001a978  add     rsp, 20h
0x18001a97c  pop     rdi
0x18001a97d  retn
```
