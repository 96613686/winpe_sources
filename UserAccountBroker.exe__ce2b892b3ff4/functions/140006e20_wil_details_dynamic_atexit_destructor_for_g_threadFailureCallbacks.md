# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140006e20`
- end: `0x140006e7e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140006e20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006e50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006e50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006e42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006e42`

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
0x140006e20  mov     [rsp+arg_0], rbx
0x140006e25  mov     [rsp+arg_8], rsi
0x140006e2a  push    rdi
0x140006e2b  sub     rsp, 20h
0x140006e2f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140006e36  mov     rsi, [rdi]
0x140006e39  jmp     short loc_140006E56
0x140006e3b  mov     rbx, rsi
0x140006e3e  mov     rsi, [rsi+8]
0x140006e42  call    cs:__imp_GetProcessHeap
0x140006e48  mov     r8, rbx; lpMem
0x140006e4b  xor     edx, edx; dwFlags
0x140006e4d  mov     rcx, rax; hHeap
0x140006e50  call    cs:__imp_HeapFree
0x140006e56  test    rsi, rsi
0x140006e59  jnz     short loc_140006E3B
0x140006e5b  mov     [rdi], rsi
0x140006e5e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse
0x140006e65  add     rdi, 8
0x140006e69  cmp     rdi, rax
0x140006e6c  jnz     short loc_140006E36
0x140006e6e  mov     rbx, [rsp+28h+arg_0]
0x140006e73  mov     rsi, [rsp+28h+arg_8]
0x140006e78  add     rsp, 20h
0x140006e7c  pop     rdi
0x140006e7d  retn
```
