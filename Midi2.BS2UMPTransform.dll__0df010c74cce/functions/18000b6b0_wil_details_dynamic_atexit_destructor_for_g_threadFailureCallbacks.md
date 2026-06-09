# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000b6b0`
- end: `0x18000b70e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b6b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b6d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b6d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b6e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b6e0`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse );
  return result;
}

```

## disassembly

```asm
0x18000b6b0  mov     [rsp+arg_0], rbx
0x18000b6b5  mov     [rsp+arg_8], rsi
0x18000b6ba  push    rdi
0x18000b6bb  sub     rsp, 20h
0x18000b6bf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000b6c6  mov     rsi, [rdi]
0x18000b6c9  jmp     short loc_18000B6E6
0x18000b6cb  mov     rbx, rsi
0x18000b6ce  mov     rsi, [rsi+8]
0x18000b6d2  call    cs:__imp_GetProcessHeap
0x18000b6d8  mov     r8, rbx; lpMem
0x18000b6db  xor     edx, edx; dwFlags
0x18000b6dd  mov     rcx, rax; hHeap
0x18000b6e0  call    cs:__imp_HeapFree
0x18000b6e6  test    rsi, rsi
0x18000b6e9  jnz     short loc_18000B6CB
0x18000b6eb  mov     [rdi], rsi
0x18000b6ee  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse
0x18000b6f5  add     rdi, 8
0x18000b6f9  cmp     rdi, rax
0x18000b6fc  jnz     short loc_18000B6C6
0x18000b6fe  mov     rbx, [rsp+28h+arg_0]
0x18000b703  mov     rsi, [rsp+28h+arg_8]
0x18000b708  add     rsp, 20h
0x18000b70c  pop     rdi
0x18000b70d  retn
```
