# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180011a90`
- end: `0x180011aee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011a90`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ac0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ab2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ab2`

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
0x180011a90  mov     [rsp+arg_0], rbx
0x180011a95  mov     [rsp+arg_8], rsi
0x180011a9a  push    rdi
0x180011a9b  sub     rsp, 20h
0x180011a9f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180011aa6  mov     rsi, [rdi]
0x180011aa9  jmp     short loc_180011AC6
0x180011aab  mov     rbx, rsi
0x180011aae  mov     rsi, [rsi+8]
0x180011ab2  call    cs:__imp_GetProcessHeap
0x180011ab8  mov     r8, rbx; lpMem
0x180011abb  xor     edx, edx; dwFlags
0x180011abd  mov     rcx, rax; hHeap
0x180011ac0  call    cs:__imp_HeapFree
0x180011ac6  test    rsi, rsi
0x180011ac9  jnz     short loc_180011AAB
0x180011acb  mov     [rdi], rsi
0x180011ace  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180011ad5  add     rdi, 8
0x180011ad9  cmp     rdi, rax
0x180011adc  jnz     short loc_180011AA6
0x180011ade  mov     rbx, [rsp+28h+arg_0]
0x180011ae3  mov     rsi, [rsp+28h+arg_8]
0x180011ae8  add     rsp, 20h
0x180011aec  pop     rdi
0x180011aed  retn
```
