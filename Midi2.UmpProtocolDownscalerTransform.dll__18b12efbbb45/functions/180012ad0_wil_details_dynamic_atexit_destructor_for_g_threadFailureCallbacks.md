# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180012ad0`
- end: `0x180012b2e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012ad0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012af2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012af2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b00`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012b00`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse );
  return result;
}

```

## disassembly

```asm
0x180012ad0  mov     [rsp+arg_0], rbx
0x180012ad5  mov     [rsp+arg_8], rsi
0x180012ada  push    rdi
0x180012adb  sub     rsp, 20h
0x180012adf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180012ae6  mov     rsi, [rdi]
0x180012ae9  jmp     short loc_180012B06
0x180012aeb  mov     rbx, rsi
0x180012aee  mov     rsi, [rsi+8]
0x180012af2  call    cs:__imp_GetProcessHeap
0x180012af8  mov     r8, rbx; lpMem
0x180012afb  xor     edx, edx; dwFlags
0x180012afd  mov     rcx, rax; hHeap
0x180012b00  call    cs:__imp_HeapFree
0x180012b06  test    rsi, rsi
0x180012b09  jnz     short loc_180012AEB
0x180012b0b  mov     [rdi], rsi
0x180012b0e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse
0x180012b15  add     rdi, 8
0x180012b19  cmp     rdi, rax
0x180012b1c  jnz     short loc_180012AE6
0x180012b1e  mov     rbx, [rsp+28h+arg_0]
0x180012b23  mov     rsi, [rsp+28h+arg_8]
0x180012b28  add     rsp, 20h
0x180012b2c  pop     rdi
0x180012b2d  retn
```
