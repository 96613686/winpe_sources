# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400136c0`
- end: `0x14001371e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400136c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400136e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400136e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400136f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400136f0`

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
0x1400136c0  mov     [rsp+arg_0], rbx
0x1400136c5  mov     [rsp+arg_8], rsi
0x1400136ca  push    rdi
0x1400136cb  sub     rsp, 20h
0x1400136cf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1400136d6  mov     rsi, [rdi]
0x1400136d9  jmp     short loc_1400136F6
0x1400136db  mov     rbx, rsi
0x1400136de  mov     rsi, [rsi+8]
0x1400136e2  call    cs:__imp_GetProcessHeap
0x1400136e8  mov     r8, rbx; lpMem
0x1400136eb  xor     edx, edx; dwFlags
0x1400136ed  mov     rcx, rax; hHeap
0x1400136f0  call    cs:__imp_HeapFree
0x1400136f6  test    rsi, rsi
0x1400136f9  jnz     short loc_1400136DB
0x1400136fb  mov     [rdi], rsi
0x1400136fe  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140013705  add     rdi, 8
0x140013709  cmp     rdi, rax
0x14001370c  jnz     short loc_1400136D6
0x14001370e  mov     rbx, [rsp+28h+arg_0]
0x140013713  mov     rsi, [rsp+28h+arg_8]
0x140013718  add     rsp, 20h
0x14001371c  pop     rdi
0x14001371d  retn
```
