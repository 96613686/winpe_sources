# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000d050`
- end: `0x18000d0ae`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000d050`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d080`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d080`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d072`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d072`

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
    result = g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x18000d050  mov     [rsp+arg_0], rbx
0x18000d055  mov     [rsp+arg_8], rsi
0x18000d05a  push    rdi
0x18000d05b  sub     rsp, 20h
0x18000d05f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000d066  mov     rsi, [rdi]
0x18000d069  jmp     short loc_18000D086
0x18000d06b  mov     rbx, rsi
0x18000d06e  mov     rsi, [rsi+8]
0x18000d072  call    cs:__imp_GetProcessHeap
0x18000d078  mov     r8, rbx; lpMem
0x18000d07b  xor     edx, edx; dwFlags
0x18000d07d  mov     rcx, rax; hHeap
0x18000d080  call    cs:__imp_HeapFree
0x18000d086  test    rsi, rsi
0x18000d089  jnz     short loc_18000D06B
0x18000d08b  mov     [rdi], rsi
0x18000d08e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000d095  add     rdi, 8
0x18000d099  cmp     rdi, rax
0x18000d09c  jnz     short loc_18000D066
0x18000d09e  mov     rbx, [rsp+28h+arg_0]
0x18000d0a3  mov     rsi, [rsp+28h+arg_8]
0x18000d0a8  add     rsp, 20h
0x18000d0ac  pop     rdi
0x18000d0ad  retn
```
