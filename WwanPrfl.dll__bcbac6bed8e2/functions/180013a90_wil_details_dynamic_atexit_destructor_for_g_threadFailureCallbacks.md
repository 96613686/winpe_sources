# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180013a90`
- end: `0x180013aee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013a90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013ac0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013ab2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013ab2`

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
    result = g_header_init_InitializeResultHeader;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x180013a90  mov     [rsp+arg_0], rbx
0x180013a95  mov     [rsp+arg_8], rsi
0x180013a9a  push    rdi
0x180013a9b  sub     rsp, 20h
0x180013a9f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180013aa6  mov     rsi, [rdi]
0x180013aa9  jmp     short loc_180013AC6
0x180013aab  mov     rbx, rsi
0x180013aae  mov     rsi, [rsi+8]
0x180013ab2  call    cs:__imp_GetProcessHeap
0x180013ab8  mov     r8, rbx; lpMem
0x180013abb  xor     edx, edx; dwFlags
0x180013abd  mov     rcx, rax; hHeap
0x180013ac0  call    cs:__imp_HeapFree
0x180013ac6  test    rsi, rsi
0x180013ac9  jnz     short loc_180013AAB
0x180013acb  mov     [rdi], rsi
0x180013ace  lea     rax, g_header_init_InitializeResultHeader
0x180013ad5  add     rdi, 8
0x180013ad9  cmp     rdi, rax
0x180013adc  jnz     short loc_180013AA6
0x180013ade  mov     rbx, [rsp+28h+arg_0]
0x180013ae3  mov     rsi, [rsp+28h+arg_8]
0x180013ae8  add     rsp, 20h
0x180013aec  pop     rdi
0x180013aed  retn
```
