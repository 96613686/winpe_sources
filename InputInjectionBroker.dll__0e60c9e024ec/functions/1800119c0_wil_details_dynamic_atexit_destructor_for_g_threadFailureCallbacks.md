# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800119c0`
- end: `0x180011a1e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800119c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800119e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800119e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800119f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800119f0`

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
0x1800119c0  mov     [rsp+arg_0], rbx
0x1800119c5  mov     [rsp+arg_8], rsi
0x1800119ca  push    rdi
0x1800119cb  sub     rsp, 20h
0x1800119cf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800119d6  mov     rsi, [rdi]
0x1800119d9  jmp     short loc_1800119F6
0x1800119db  mov     rbx, rsi
0x1800119de  mov     rsi, [rsi+8]
0x1800119e2  call    cs:__imp_GetProcessHeap
0x1800119e8  mov     r8, rbx; lpMem
0x1800119eb  xor     edx, edx; dwFlags
0x1800119ed  mov     rcx, rax; hHeap
0x1800119f0  call    cs:__imp_HeapFree
0x1800119f6  test    rsi, rsi
0x1800119f9  jnz     short loc_1800119DB
0x1800119fb  mov     [rdi], rsi
0x1800119fe  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180011a05  add     rdi, 8
0x180011a09  cmp     rdi, rax
0x180011a0c  jnz     short loc_1800119D6
0x180011a0e  mov     rbx, [rsp+28h+arg_0]
0x180011a13  mov     rsi, [rsp+28h+arg_8]
0x180011a18  add     rsp, 20h
0x180011a1c  pop     rdi
0x180011a1d  retn
```
