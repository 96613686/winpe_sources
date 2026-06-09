# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180014610`
- end: `0x18001466e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014610`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180014632`
- `KERNEL32!GetProcessHeap` at `0x180014632`
- `KERNEL32!HeapFree` at `0x180014640`
- `KERNEL32!HeapFree` at `0x180014640`

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
0x180014610  mov     [rsp+arg_0], rbx
0x180014615  mov     [rsp+arg_8], rsi
0x18001461a  push    rdi
0x18001461b  sub     rsp, 20h
0x18001461f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180014626  mov     rsi, [rdi]
0x180014629  jmp     short loc_180014646
0x18001462b  mov     rbx, rsi
0x18001462e  mov     rsi, [rsi+8]
0x180014632  call    cs:__imp_GetProcessHeap
0x180014638  mov     r8, rbx; lpMem
0x18001463b  xor     edx, edx; dwFlags
0x18001463d  mov     rcx, rax; hHeap
0x180014640  call    cs:__imp_HeapFree
0x180014646  test    rsi, rsi
0x180014649  jnz     short loc_18001462B
0x18001464b  mov     [rdi], rsi
0x18001464e  lea     rax, g_header_init_InitializeResultHeader
0x180014655  add     rdi, 8
0x180014659  cmp     rdi, rax
0x18001465c  jnz     short loc_180014626
0x18001465e  mov     rbx, [rsp+28h+arg_0]
0x180014663  mov     rsi, [rsp+28h+arg_8]
0x180014668  add     rsp, 20h
0x18001466c  pop     rdi
0x18001466d  retn
```
