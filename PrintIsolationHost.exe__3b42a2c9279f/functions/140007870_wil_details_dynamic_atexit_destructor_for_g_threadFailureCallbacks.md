# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140007870`
- end: `0x1400078ce`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007870`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400078a0`
- `KERNEL32!HeapFree` at `0x1400078a0`
- `KERNEL32!GetProcessHeap` at `0x140007892`
- `KERNEL32!GetProcessHeap` at `0x140007892`

## pseudocode

```c
__int64 *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rdi
  __int64 v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *result; // rax

  v0 = wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = (void *)v1;
      v1 = *(_QWORD *)(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x140007870  mov     [rsp+arg_0], rbx
0x140007875  mov     [rsp+arg_8], rsi
0x14000787a  push    rdi
0x14000787b  sub     rsp, 20h
0x14000787f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140007886  mov     rsi, [rdi]
0x140007889  jmp     short loc_1400078A6
0x14000788b  mov     rbx, rsi
0x14000788e  mov     rsi, [rsi+8]
0x140007892  call    cs:__imp_GetProcessHeap
0x140007898  mov     r8, rbx; lpMem
0x14000789b  xor     edx, edx; dwFlags
0x14000789d  mov     rcx, rax; hHeap
0x1400078a0  call    cs:__imp_HeapFree
0x1400078a6  test    rsi, rsi
0x1400078a9  jnz     short loc_14000788B
0x1400078ab  mov     [rdi], rsi
0x1400078ae  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1400078b5  add     rdi, 8
0x1400078b9  cmp     rdi, rax
0x1400078bc  jnz     short loc_140007886
0x1400078be  mov     rbx, [rsp+28h+arg_0]
0x1400078c3  mov     rsi, [rsp+28h+arg_8]
0x1400078c8  add     rsp, 20h
0x1400078cc  pop     rdi
0x1400078cd  retn
```
