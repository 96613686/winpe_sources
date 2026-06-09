# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180009b30`
- end: `0x180009b9b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009b30`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009b52`
- `KERNEL32!GetProcessHeap` at `0x180009b52`
- `KERNEL32!HeapFree` at `0x180009b66`
- `KERNEL32!HeapFree` at `0x180009b66`

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
    result = &g_header_init_InitializeResultHeader;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x180009b30  mov     [rsp+arg_0], rbx
0x180009b35  mov     [rsp+arg_8], rsi
0x180009b3a  push    rdi
0x180009b3b  sub     rsp, 20h
0x180009b3f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180009b46  mov     rsi, [rdi]
0x180009b49  jmp     short loc_180009B72
0x180009b4b  mov     rbx, rsi
0x180009b4e  mov     rsi, [rsi+8]
0x180009b52  call    cs:__imp_GetProcessHeap
0x180009b59  nop     dword ptr [rax+rax+00h]
0x180009b5e  mov     r8, rbx; lpMem
0x180009b61  xor     edx, edx; dwFlags
0x180009b63  mov     rcx, rax; hHeap
0x180009b66  call    cs:__imp_HeapFree
0x180009b6d  nop     dword ptr [rax+rax+00h]
0x180009b72  test    rsi, rsi
0x180009b75  jnz     short loc_180009B4B
0x180009b77  mov     [rdi], rsi
0x180009b7a  lea     rax, g_header_init_InitializeResultHeader
0x180009b81  add     rdi, 8
0x180009b85  cmp     rdi, rax
0x180009b88  jnz     short loc_180009B46
0x180009b8a  mov     rbx, [rsp+28h+arg_0]
0x180009b8f  mov     rsi, [rsp+28h+arg_8]
0x180009b94  add     rsp, 20h
0x180009b98  pop     rdi
0x180009b99  retn
```
