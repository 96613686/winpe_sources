# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000ebb0`
- end: `0x18000ec0e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ebb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ebd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ebd2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ebe0`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse );
  return result;
}

```

## disassembly

```asm
0x18000ebb0  mov     [rsp+arg_0], rbx
0x18000ebb5  mov     [rsp+arg_8], rsi
0x18000ebba  push    rdi
0x18000ebbb  sub     rsp, 20h
0x18000ebbf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000ebc6  mov     rsi, [rdi]
0x18000ebc9  jmp     short loc_18000EBE6
0x18000ebcb  mov     rbx, rsi
0x18000ebce  mov     rsi, [rsi+8]
0x18000ebd2  call    cs:__imp_GetProcessHeap
0x18000ebd8  mov     r8, rbx; lpMem
0x18000ebdb  xor     edx, edx; dwFlags
0x18000ebdd  mov     rcx, rax; hHeap
0x18000ebe0  call    cs:__imp_HeapFree
0x18000ebe6  test    rsi, rsi
0x18000ebe9  jnz     short loc_18000EBCB
0x18000ebeb  mov     [rdi], rsi
0x18000ebee  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse
0x18000ebf5  add     rdi, 8
0x18000ebf9  cmp     rdi, rax
0x18000ebfc  jnz     short loc_18000EBC6
0x18000ebfe  mov     rbx, [rsp+28h+arg_0]
0x18000ec03  mov     rsi, [rsp+28h+arg_8]
0x18000ec08  add     rsp, 20h
0x18000ec0c  pop     rdi
0x18000ec0d  retn
```
