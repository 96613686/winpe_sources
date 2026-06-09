# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180018f40`
- end: `0x180018fab`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180018f40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180018f76`
- `KERNEL32!HeapFree` at `0x180018f76`
- `KERNEL32!GetProcessHeap` at `0x180018f62`
- `KERNEL32!GetProcessHeap` at `0x180018f62`

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
0x180018f40  mov     [rsp+arg_0], rbx
0x180018f45  mov     [rsp+arg_8], rsi
0x180018f4a  push    rdi
0x180018f4b  sub     rsp, 20h
0x180018f4f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180018f56  mov     rsi, [rdi]
0x180018f59  jmp     short loc_180018F82
0x180018f5b  mov     rbx, rsi
0x180018f5e  mov     rsi, [rsi+8]
0x180018f62  call    cs:__imp_GetProcessHeap
0x180018f69  nop     dword ptr [rax+rax+00h]
0x180018f6e  mov     r8, rbx; lpMem
0x180018f71  xor     edx, edx; dwFlags
0x180018f73  mov     rcx, rax; hHeap
0x180018f76  call    cs:__imp_HeapFree
0x180018f7d  nop     dword ptr [rax+rax+00h]
0x180018f82  test    rsi, rsi
0x180018f85  jnz     short loc_180018F5B
0x180018f87  mov     [rdi], rsi
0x180018f8a  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180018f91  add     rdi, 8
0x180018f95  cmp     rdi, rax
0x180018f98  jnz     short loc_180018F56
0x180018f9a  mov     rbx, [rsp+28h+arg_0]
0x180018f9f  mov     rsi, [rsp+28h+arg_8]
0x180018fa4  add     rsp, 20h
0x180018fa8  pop     rdi
0x180018fa9  retn
```
