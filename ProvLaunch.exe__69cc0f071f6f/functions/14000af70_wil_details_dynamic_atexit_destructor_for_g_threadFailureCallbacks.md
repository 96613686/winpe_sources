# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000af70`
- end: `0x14000afce`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000af70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000af92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000af92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000afa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000afa0`

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
0x14000af70  mov     [rsp+arg_0], rbx
0x14000af75  mov     [rsp+arg_8], rsi
0x14000af7a  push    rdi
0x14000af7b  sub     rsp, 20h
0x14000af7f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000af86  mov     rsi, [rdi]
0x14000af89  jmp     short loc_14000AFA6
0x14000af8b  mov     rbx, rsi
0x14000af8e  mov     rsi, [rsi+8]
0x14000af92  call    cs:__imp_GetProcessHeap
0x14000af98  mov     r8, rbx; lpMem
0x14000af9b  xor     edx, edx; dwFlags
0x14000af9d  mov     rcx, rax; hHeap
0x14000afa0  call    cs:__imp_HeapFree
0x14000afa6  test    rsi, rsi
0x14000afa9  jnz     short loc_14000AF8B
0x14000afab  mov     [rdi], rsi
0x14000afae  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x14000afb5  add     rdi, 8
0x14000afb9  cmp     rdi, rax
0x14000afbc  jnz     short loc_14000AF86
0x14000afbe  mov     rbx, [rsp+28h+arg_0]
0x14000afc3  mov     rsi, [rsp+28h+arg_8]
0x14000afc8  add     rsp, 20h
0x14000afcc  pop     rdi
0x14000afcd  retn
```
