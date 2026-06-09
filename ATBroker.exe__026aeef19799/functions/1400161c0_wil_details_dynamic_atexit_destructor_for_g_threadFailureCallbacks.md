# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400161c0`
- end: `0x14001621e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400161c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400161f0`
- `KERNEL32!HeapFree` at `0x1400161f0`
- `KERNEL32!GetProcessHeap` at `0x1400161e2`
- `KERNEL32!GetProcessHeap` at `0x1400161e2`

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
0x1400161c0  mov     [rsp+arg_0], rbx
0x1400161c5  mov     [rsp+arg_8], rsi
0x1400161ca  push    rdi
0x1400161cb  sub     rsp, 20h
0x1400161cf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1400161d6  mov     rsi, [rdi]
0x1400161d9  jmp     short loc_1400161F6
0x1400161db  mov     rbx, rsi
0x1400161de  mov     rsi, [rsi+8]
0x1400161e2  call    cs:__imp_GetProcessHeap
0x1400161e8  mov     r8, rbx; lpMem
0x1400161eb  xor     edx, edx; dwFlags
0x1400161ed  mov     rcx, rax; hHeap
0x1400161f0  call    cs:__imp_HeapFree
0x1400161f6  test    rsi, rsi
0x1400161f9  jnz     short loc_1400161DB
0x1400161fb  mov     [rdi], rsi
0x1400161fe  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x140016205  add     rdi, 8
0x140016209  cmp     rdi, rax
0x14001620c  jnz     short loc_1400161D6
0x14001620e  mov     rbx, [rsp+28h+arg_0]
0x140016213  mov     rsi, [rsp+28h+arg_8]
0x140016218  add     rsp, 20h
0x14001621c  pop     rdi
0x14001621d  retn
```
