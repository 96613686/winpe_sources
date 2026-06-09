# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180011680`
- end: `0x1800116de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180011680`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800116b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800116a2`

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
0x180011680  mov     [rsp+arg_0], rbx
0x180011685  mov     [rsp+arg_8], rsi
0x18001168a  push    rdi
0x18001168b  sub     rsp, 20h
0x18001168f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180011696  mov     rsi, [rdi]
0x180011699  jmp     short loc_1800116B6
0x18001169b  mov     rbx, rsi
0x18001169e  mov     rsi, [rsi+8]
0x1800116a2  call    cs:__imp_GetProcessHeap
0x1800116a8  mov     r8, rbx; lpMem
0x1800116ab  xor     edx, edx; dwFlags
0x1800116ad  mov     rcx, rax; hHeap
0x1800116b0  call    cs:__imp_HeapFree
0x1800116b6  test    rsi, rsi
0x1800116b9  jnz     short loc_18001169B
0x1800116bb  mov     [rdi], rsi
0x1800116be  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1800116c5  add     rdi, 8
0x1800116c9  cmp     rdi, rax
0x1800116cc  jnz     short loc_180011696
0x1800116ce  mov     rbx, [rsp+28h+arg_0]
0x1800116d3  mov     rsi, [rsp+28h+arg_8]
0x1800116d8  add     rsp, 20h
0x1800116dc  pop     rdi
0x1800116dd  retn
```
