# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000bf70`
- end: `0x18000bfce`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bf70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bfa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bfa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bf92`

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
0x18000bf70  mov     [rsp+arg_0], rbx
0x18000bf75  mov     [rsp+arg_8], rsi
0x18000bf7a  push    rdi
0x18000bf7b  sub     rsp, 20h
0x18000bf7f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000bf86  mov     rsi, [rdi]
0x18000bf89  jmp     short loc_18000BFA6
0x18000bf8b  mov     rbx, rsi
0x18000bf8e  mov     rsi, [rsi+8]
0x18000bf92  call    cs:__imp_GetProcessHeap
0x18000bf98  mov     r8, rbx; lpMem
0x18000bf9b  xor     edx, edx; dwFlags
0x18000bf9d  mov     rcx, rax; hHeap
0x18000bfa0  call    cs:__imp_HeapFree
0x18000bfa6  test    rsi, rsi
0x18000bfa9  jnz     short loc_18000BF8B
0x18000bfab  mov     [rdi], rsi
0x18000bfae  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000bfb5  add     rdi, 8
0x18000bfb9  cmp     rdi, rax
0x18000bfbc  jnz     short loc_18000BF86
0x18000bfbe  mov     rbx, [rsp+28h+arg_0]
0x18000bfc3  mov     rsi, [rsp+28h+arg_8]
0x18000bfc8  add     rsp, 20h
0x18000bfcc  pop     rdi
0x18000bfcd  retn
```
