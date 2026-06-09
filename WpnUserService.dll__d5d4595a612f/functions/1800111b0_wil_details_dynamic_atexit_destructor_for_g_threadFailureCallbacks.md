# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800111b0`
- end: `0x18001120e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800111b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800111d2`

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
0x1800111b0  mov     [rsp+arg_0], rbx
0x1800111b5  mov     [rsp+arg_8], rsi
0x1800111ba  push    rdi
0x1800111bb  sub     rsp, 20h
0x1800111bf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800111c6  mov     rsi, [rdi]
0x1800111c9  jmp     short loc_1800111E6
0x1800111cb  mov     rbx, rsi
0x1800111ce  mov     rsi, [rsi+8]
0x1800111d2  call    cs:__imp_GetProcessHeap
0x1800111d8  mov     r8, rbx; lpMem
0x1800111db  xor     edx, edx; dwFlags
0x1800111dd  mov     rcx, rax; hHeap
0x1800111e0  call    cs:__imp_HeapFree
0x1800111e6  test    rsi, rsi
0x1800111e9  jnz     short loc_1800111CB
0x1800111eb  mov     [rdi], rsi
0x1800111ee  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1800111f5  add     rdi, 8
0x1800111f9  cmp     rdi, rax
0x1800111fc  jnz     short loc_1800111C6
0x1800111fe  mov     rbx, [rsp+28h+arg_0]
0x180011203  mov     rsi, [rsp+28h+arg_8]
0x180011208  add     rsp, 20h
0x18001120c  pop     rdi
0x18001120d  retn
```
