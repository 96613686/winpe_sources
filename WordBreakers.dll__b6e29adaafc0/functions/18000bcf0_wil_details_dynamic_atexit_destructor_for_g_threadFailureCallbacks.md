# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000bcf0`
- end: `0x18000bd4e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000bcf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000bd12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000bd20`

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
0x18000bcf0  mov     [rsp+arg_0], rbx
0x18000bcf5  mov     [rsp+arg_8], rsi
0x18000bcfa  push    rdi
0x18000bcfb  sub     rsp, 20h
0x18000bcff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000bd06  mov     rsi, [rdi]
0x18000bd09  jmp     short loc_18000BD26
0x18000bd0b  mov     rbx, rsi
0x18000bd0e  mov     rsi, [rsi+8]
0x18000bd12  call    cs:__imp_GetProcessHeap
0x18000bd18  mov     r8, rbx; lpMem
0x18000bd1b  xor     edx, edx; dwFlags
0x18000bd1d  mov     rcx, rax; hHeap
0x18000bd20  call    cs:__imp_HeapFree
0x18000bd26  test    rsi, rsi
0x18000bd29  jnz     short loc_18000BD0B
0x18000bd2b  mov     [rdi], rsi
0x18000bd2e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000bd35  add     rdi, 8
0x18000bd39  cmp     rdi, rax
0x18000bd3c  jnz     short loc_18000BD06
0x18000bd3e  mov     rbx, [rsp+28h+arg_0]
0x18000bd43  mov     rsi, [rsp+28h+arg_8]
0x18000bd48  add     rsp, 20h
0x18000bd4c  pop     rdi
0x18000bd4d  retn
```
