# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400126f0`
- end: `0x14001274e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400126f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012720`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012712`

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
    result = &g_header_init_InitializeStagingHeaderInternalApi;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x1400126f0  mov     [rsp+arg_0], rbx
0x1400126f5  mov     [rsp+arg_8], rsi
0x1400126fa  push    rdi
0x1400126fb  sub     rsp, 20h
0x1400126ff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140012706  mov     rsi, [rdi]
0x140012709  jmp     short loc_140012726
0x14001270b  mov     rbx, rsi
0x14001270e  mov     rsi, [rsi+8]
0x140012712  call    cs:__imp_GetProcessHeap
0x140012718  mov     r8, rbx; lpMem
0x14001271b  xor     edx, edx; dwFlags
0x14001271d  mov     rcx, rax; hHeap
0x140012720  call    cs:__imp_HeapFree
0x140012726  test    rsi, rsi
0x140012729  jnz     short loc_14001270B
0x14001272b  mov     [rdi], rsi
0x14001272e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x140012735  add     rdi, 8
0x140012739  cmp     rdi, rax
0x14001273c  jnz     short loc_140012706
0x14001273e  mov     rbx, [rsp+28h+arg_0]
0x140012743  mov     rsi, [rsp+28h+arg_8]
0x140012748  add     rsp, 20h
0x14001274c  pop     rdi
0x14001274d  retn
```
