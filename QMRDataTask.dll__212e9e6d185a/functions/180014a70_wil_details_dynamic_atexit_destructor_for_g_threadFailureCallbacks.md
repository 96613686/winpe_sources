# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180014a70`
- end: `0x180014ace`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014a70`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180014a92`
- `KERNEL32!GetProcessHeap` at `0x180014a92`
- `KERNEL32!HeapFree` at `0x180014aa0`
- `KERNEL32!HeapFree` at `0x180014aa0`

## pseudocode

```c
void *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  _QWORD **v0; // rdi
  _QWORD *v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  void *result; // rax

  v0 = (_QWORD **)&wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = v1;
      v1 = (_QWORD *)v1[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = &g_header_init_InitializeStagingHeaderInternalApi;
    ++v0;
  }
  while ( v0 != (_QWORD **)&g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x180014a70  mov     [rsp+arg_0], rbx
0x180014a75  mov     [rsp+arg_8], rsi
0x180014a7a  push    rdi
0x180014a7b  sub     rsp, 20h
0x180014a7f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180014a86  mov     rsi, [rdi]
0x180014a89  jmp     short loc_180014AA6
0x180014a8b  mov     rbx, rsi
0x180014a8e  mov     rsi, [rsi+8]
0x180014a92  call    cs:__imp_GetProcessHeap
0x180014a98  mov     r8, rbx; lpMem
0x180014a9b  xor     edx, edx; dwFlags
0x180014a9d  mov     rcx, rax; hHeap
0x180014aa0  call    cs:__imp_HeapFree
0x180014aa6  test    rsi, rsi
0x180014aa9  jnz     short loc_180014A8B
0x180014aab  mov     [rdi], rsi
0x180014aae  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x180014ab5  add     rdi, 8
0x180014ab9  cmp     rdi, rax
0x180014abc  jnz     short loc_180014A86
0x180014abe  mov     rbx, [rsp+28h+arg_0]
0x180014ac3  mov     rsi, [rsp+28h+arg_8]
0x180014ac8  add     rsp, 20h
0x180014acc  pop     rdi
0x180014acd  retn
```
