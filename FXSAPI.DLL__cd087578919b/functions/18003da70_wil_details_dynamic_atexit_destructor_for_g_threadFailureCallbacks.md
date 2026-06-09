# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18003da70`
- end: `0x18003dadb`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003da70`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18003da92`
- `KERNEL32!GetProcessHeap` at `0x18003da92`
- `KERNEL32!HeapFree` at `0x18003daa6`
- `KERNEL32!HeapFree` at `0x18003daa6`

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
    result = &g_header_init_InitializeResultHeader;
    ++v0;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x18003da70  mov     [rsp+arg_0], rbx
0x18003da75  mov     [rsp+arg_8], rsi
0x18003da7a  push    rdi
0x18003da7b  sub     rsp, 20h
0x18003da7f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18003da86  mov     rsi, [rdi]
0x18003da89  jmp     short loc_18003DAB2
0x18003da8b  mov     rbx, rsi
0x18003da8e  mov     rsi, [rsi+8]
0x18003da92  call    cs:__imp_GetProcessHeap
0x18003da99  nop     dword ptr [rax+rax+00h]
0x18003da9e  mov     r8, rbx; lpMem
0x18003daa1  xor     edx, edx; dwFlags
0x18003daa3  mov     rcx, rax; hHeap
0x18003daa6  call    cs:__imp_HeapFree
0x18003daad  nop     dword ptr [rax+rax+00h]
0x18003dab2  test    rsi, rsi
0x18003dab5  jnz     short loc_18003DA8B
0x18003dab7  mov     [rdi], rsi
0x18003daba  lea     rax, g_header_init_InitializeResultHeader
0x18003dac1  add     rdi, 8
0x18003dac5  cmp     rdi, rax
0x18003dac8  jnz     short loc_18003DA86
0x18003daca  mov     rbx, [rsp+28h+arg_0]
0x18003dacf  mov     rsi, [rsp+28h+arg_8]
0x18003dad4  add     rsp, 20h
0x18003dad8  pop     rdi
0x18003dad9  retn
```
