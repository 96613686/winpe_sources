# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180012610`
- end: `0x18001266e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012610`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012640`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012640`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012632`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180012632`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != (_QWORD **)&g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x180012610  mov     [rsp+arg_0], rbx
0x180012615  mov     [rsp+arg_8], rsi
0x18001261a  push    rdi
0x18001261b  sub     rsp, 20h
0x18001261f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180012626  mov     rsi, [rdi]
0x180012629  jmp     short loc_180012646
0x18001262b  mov     rbx, rsi
0x18001262e  mov     rsi, [rsi+8]
0x180012632  call    cs:__imp_GetProcessHeap
0x180012638  mov     r8, rbx; lpMem
0x18001263b  xor     edx, edx; dwFlags
0x18001263d  mov     rcx, rax; hHeap
0x180012640  call    cs:__imp_HeapFree
0x180012646  test    rsi, rsi
0x180012649  jnz     short loc_18001262B
0x18001264b  mov     [rdi], rsi
0x18001264e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x180012655  add     rdi, 8
0x180012659  cmp     rdi, rax
0x18001265c  jnz     short loc_180012626
0x18001265e  mov     rbx, [rsp+28h+arg_0]
0x180012663  mov     rsi, [rsp+28h+arg_8]
0x180012668  add     rsp, 20h
0x18001266c  pop     rdi
0x18001266d  retn
```
