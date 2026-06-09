# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000cd20`
- end: `0x18000cd7e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cd20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cd50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cd42`

## pseudocode

```c
__int64 *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rdi
  __int64 v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *result; // rax

  v0 = wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = (void *)v1;
      v1 = *(_QWORD *)(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = g_header_init_InitializeStagingHeaderInternalApi;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x18000cd20  mov     [rsp+arg_0], rbx
0x18000cd25  mov     [rsp+arg_8], rsi
0x18000cd2a  push    rdi
0x18000cd2b  sub     rsp, 20h
0x18000cd2f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000cd36  mov     rsi, [rdi]
0x18000cd39  jmp     short loc_18000CD56
0x18000cd3b  mov     rbx, rsi
0x18000cd3e  mov     rsi, [rsi+8]
0x18000cd42  call    cs:__imp_GetProcessHeap
0x18000cd48  mov     r8, rbx; lpMem
0x18000cd4b  xor     edx, edx; dwFlags
0x18000cd4d  mov     rcx, rax; hHeap
0x18000cd50  call    cs:__imp_HeapFree
0x18000cd56  test    rsi, rsi
0x18000cd59  jnz     short loc_18000CD3B
0x18000cd5b  mov     [rdi], rsi
0x18000cd5e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18000cd65  add     rdi, 8
0x18000cd69  cmp     rdi, rax
0x18000cd6c  jnz     short loc_18000CD36
0x18000cd6e  mov     rbx, [rsp+28h+arg_0]
0x18000cd73  mov     rsi, [rsp+28h+arg_8]
0x18000cd78  add     rsp, 20h
0x18000cd7c  pop     rdi
0x18000cd7d  retn
```
