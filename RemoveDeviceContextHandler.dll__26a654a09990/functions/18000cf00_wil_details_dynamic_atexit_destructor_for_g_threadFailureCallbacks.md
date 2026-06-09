# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000cf00`
- end: `0x18000cf5e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000cf00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000cf22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000cf30`

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
0x18000cf00  mov     [rsp+arg_0], rbx
0x18000cf05  mov     [rsp+arg_8], rsi
0x18000cf0a  push    rdi
0x18000cf0b  sub     rsp, 20h
0x18000cf0f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000cf16  mov     rsi, [rdi]
0x18000cf19  jmp     short loc_18000CF36
0x18000cf1b  mov     rbx, rsi
0x18000cf1e  mov     rsi, [rsi+8]
0x18000cf22  call    cs:__imp_GetProcessHeap
0x18000cf28  mov     r8, rbx; lpMem
0x18000cf2b  xor     edx, edx; dwFlags
0x18000cf2d  mov     rcx, rax; hHeap
0x18000cf30  call    cs:__imp_HeapFree
0x18000cf36  test    rsi, rsi
0x18000cf39  jnz     short loc_18000CF1B
0x18000cf3b  mov     [rdi], rsi
0x18000cf3e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000cf45  add     rdi, 8
0x18000cf49  cmp     rdi, rax
0x18000cf4c  jnz     short loc_18000CF16
0x18000cf4e  mov     rbx, [rsp+28h+arg_0]
0x18000cf53  mov     rsi, [rsp+28h+arg_8]
0x18000cf58  add     rsp, 20h
0x18000cf5c  pop     rdi
0x18000cf5d  retn
```
