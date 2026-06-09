# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140017a90`
- end: `0x140017aee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140017a90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017ac0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140017ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017ab2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140017ab2`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x140017a90  mov     [rsp+arg_0], rbx
0x140017a95  mov     [rsp+arg_8], rsi
0x140017a9a  push    rdi
0x140017a9b  sub     rsp, 20h
0x140017a9f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140017aa6  mov     rsi, [rdi]
0x140017aa9  jmp     short loc_140017AC6
0x140017aab  mov     rbx, rsi
0x140017aae  mov     rsi, [rsi+8]
0x140017ab2  call    cs:__imp_GetProcessHeap
0x140017ab8  mov     r8, rbx; lpMem
0x140017abb  xor     edx, edx; dwFlags
0x140017abd  mov     rcx, rax; hHeap
0x140017ac0  call    cs:__imp_HeapFree
0x140017ac6  test    rsi, rsi
0x140017ac9  jnz     short loc_140017AAB
0x140017acb  mov     [rdi], rsi
0x140017ace  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140017ad5  add     rdi, 8
0x140017ad9  cmp     rdi, rax
0x140017adc  jnz     short loc_140017AA6
0x140017ade  mov     rbx, [rsp+28h+arg_0]
0x140017ae3  mov     rsi, [rsp+28h+arg_8]
0x140017ae8  add     rsp, 20h
0x140017aec  pop     rdi
0x140017aed  retn
```
