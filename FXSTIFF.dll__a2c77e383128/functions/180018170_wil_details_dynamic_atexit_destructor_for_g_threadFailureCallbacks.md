# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180018170`
- end: `0x1800181ce`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018170`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800181a0`
- `KERNEL32!HeapFree` at `0x1800181a0`
- `KERNEL32!GetProcessHeap` at `0x180018192`
- `KERNEL32!GetProcessHeap` at `0x180018192`

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
0x180018170  mov     [rsp+arg_0], rbx
0x180018175  mov     [rsp+arg_8], rsi
0x18001817a  push    rdi
0x18001817b  sub     rsp, 20h
0x18001817f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180018186  mov     rsi, [rdi]
0x180018189  jmp     short loc_1800181A6
0x18001818b  mov     rbx, rsi
0x18001818e  mov     rsi, [rsi+8]
0x180018192  call    cs:__imp_GetProcessHeap
0x180018198  mov     r8, rbx; lpMem
0x18001819b  xor     edx, edx; dwFlags
0x18001819d  mov     rcx, rax; hHeap
0x1800181a0  call    cs:__imp_HeapFree
0x1800181a6  test    rsi, rsi
0x1800181a9  jnz     short loc_18001818B
0x1800181ab  mov     [rdi], rsi
0x1800181ae  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x1800181b5  add     rdi, 8
0x1800181b9  cmp     rdi, rax
0x1800181bc  jnz     short loc_180018186
0x1800181be  mov     rbx, [rsp+28h+arg_0]
0x1800181c3  mov     rsi, [rsp+28h+arg_8]
0x1800181c8  add     rsp, 20h
0x1800181cc  pop     rdi
0x1800181cd  retn
```
