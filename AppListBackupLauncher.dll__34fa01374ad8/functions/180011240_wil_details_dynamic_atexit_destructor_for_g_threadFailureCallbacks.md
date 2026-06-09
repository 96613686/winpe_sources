# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180011240`
- end: `0x18001129e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011240`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011270`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011262`

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
0x180011240  mov     [rsp+arg_0], rbx
0x180011245  mov     [rsp+arg_8], rsi
0x18001124a  push    rdi
0x18001124b  sub     rsp, 20h
0x18001124f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180011256  mov     rsi, [rdi]
0x180011259  jmp     short loc_180011276
0x18001125b  mov     rbx, rsi
0x18001125e  mov     rsi, [rsi+8]
0x180011262  call    cs:__imp_GetProcessHeap
0x180011268  mov     r8, rbx; lpMem
0x18001126b  xor     edx, edx; dwFlags
0x18001126d  mov     rcx, rax; hHeap
0x180011270  call    cs:__imp_HeapFree
0x180011276  test    rsi, rsi
0x180011279  jnz     short loc_18001125B
0x18001127b  mov     [rdi], rsi
0x18001127e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180011285  add     rdi, 8
0x180011289  cmp     rdi, rax
0x18001128c  jnz     short loc_180011256
0x18001128e  mov     rbx, [rsp+28h+arg_0]
0x180011293  mov     rsi, [rsp+28h+arg_8]
0x180011298  add     rsp, 20h
0x18001129c  pop     rdi
0x18001129d  retn
```
