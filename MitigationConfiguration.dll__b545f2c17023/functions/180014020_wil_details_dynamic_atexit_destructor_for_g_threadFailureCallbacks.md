# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180014020`
- end: `0x18001407e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014020`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014050`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014050`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014042`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014042`

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
0x180014020  mov     [rsp+arg_0], rbx
0x180014025  mov     [rsp+arg_8], rsi
0x18001402a  push    rdi
0x18001402b  sub     rsp, 20h
0x18001402f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180014036  mov     rsi, [rdi]
0x180014039  jmp     short loc_180014056
0x18001403b  mov     rbx, rsi
0x18001403e  mov     rsi, [rsi+8]
0x180014042  call    cs:__imp_GetProcessHeap
0x180014048  mov     r8, rbx; lpMem
0x18001404b  xor     edx, edx; dwFlags
0x18001404d  mov     rcx, rax; hHeap
0x180014050  call    cs:__imp_HeapFree
0x180014056  test    rsi, rsi
0x180014059  jnz     short loc_18001403B
0x18001405b  mov     [rdi], rsi
0x18001405e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180014065  add     rdi, 8
0x180014069  cmp     rdi, rax
0x18001406c  jnz     short loc_180014036
0x18001406e  mov     rbx, [rsp+28h+arg_0]
0x180014073  mov     rsi, [rsp+28h+arg_8]
0x180014078  add     rsp, 20h
0x18001407c  pop     rdi
0x18001407d  retn
```
