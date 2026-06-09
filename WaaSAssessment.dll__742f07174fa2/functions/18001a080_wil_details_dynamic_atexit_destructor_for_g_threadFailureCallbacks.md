# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001a080`
- end: `0x18001a0de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a080`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a0a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a0b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a0b0`

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
    result = &g_header_init_StagingEventsInitialize;
    v0 += 8;
  }
  while ( v0 != &g_header_init_StagingEventsInitialize );
  return result;
}

```

## disassembly

```asm
0x18001a080  mov     [rsp+arg_0], rbx
0x18001a085  mov     [rsp+arg_8], rsi
0x18001a08a  push    rdi
0x18001a08b  sub     rsp, 20h
0x18001a08f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001a096  mov     rsi, [rdi]
0x18001a099  jmp     short loc_18001A0B6
0x18001a09b  mov     rbx, rsi
0x18001a09e  mov     rsi, [rsi+8]
0x18001a0a2  call    cs:__imp_GetProcessHeap
0x18001a0a8  mov     r8, rbx; lpMem
0x18001a0ab  xor     edx, edx; dwFlags
0x18001a0ad  mov     rcx, rax; hHeap
0x18001a0b0  call    cs:__imp_HeapFree
0x18001a0b6  test    rsi, rsi
0x18001a0b9  jnz     short loc_18001A09B
0x18001a0bb  mov     [rdi], rsi
0x18001a0be  lea     rax, g_header_init_StagingEventsInitialize
0x18001a0c5  add     rdi, 8
0x18001a0c9  cmp     rdi, rax
0x18001a0cc  jnz     short loc_18001A096
0x18001a0ce  mov     rbx, [rsp+28h+arg_0]
0x18001a0d3  mov     rsi, [rsp+28h+arg_8]
0x18001a0d8  add     rsp, 20h
0x18001a0dc  pop     rdi
0x18001a0dd  retn
```
