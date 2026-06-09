# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001d6d0`
- end: `0x18001d72e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d6d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d6f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d6f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d700`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d700`

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
    result = &`__local_stdio_printf_options'::`2'::_OptionsStorage;
    ++v0;
  }
  while ( v0 != &`__local_stdio_printf_options'::`2'::_OptionsStorage );
  return result;
}

```

## disassembly

```asm
0x18001d6d0  mov     [rsp+arg_0], rbx
0x18001d6d5  mov     [rsp+arg_8], rsi
0x18001d6da  push    rdi
0x18001d6db  sub     rsp, 20h
0x18001d6df  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001d6e6  mov     rsi, [rdi]
0x18001d6e9  jmp     short loc_18001D706
0x18001d6eb  mov     rbx, rsi
0x18001d6ee  mov     rsi, [rsi+8]
0x18001d6f2  call    cs:__imp_GetProcessHeap
0x18001d6f8  mov     r8, rbx; lpMem
0x18001d6fb  xor     edx, edx; dwFlags
0x18001d6fd  mov     rcx, rax; hHeap
0x18001d700  call    cs:__imp_HeapFree
0x18001d706  test    rsi, rsi
0x18001d709  jnz     short loc_18001D6EB
0x18001d70b  mov     [rdi], rsi
0x18001d70e  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18001d715  add     rdi, 8
0x18001d719  cmp     rdi, rax
0x18001d71c  jnz     short loc_18001D6E6
0x18001d71e  mov     rbx, [rsp+28h+arg_0]
0x18001d723  mov     rsi, [rsp+28h+arg_8]
0x18001d728  add     rsp, 20h
0x18001d72c  pop     rdi
0x18001d72d  retn
```
