# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180002390`
- end: `0x1800023f2`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002390`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800023e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800023e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800023d7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800023d7`

## pseudocode

```c
void wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rbx
  __int64 v1; // rsi
  void *v2; // rdi
  HANDLE ProcessHeap; // rax

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
    *v0++ = 0;
  }
  while ( v0 != g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
}

```

## disassembly

```asm
0x180002390  push    rbx
0x180002392  push    rbp
0x180002393  push    rsi
0x180002394  push    rdi
0x180002395  push    r14
0x180002397  sub     rsp, 20h
0x18000239b  lea     rbx, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800023a2  xor     ebp, ebp
0x1800023a4  lea     r14, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1800023ab  nop     dword ptr [rax+rax+00h]
0x1800023b0  mov     rsi, [rbx]
0x1800023b3  test    rsi, rsi
0x1800023b6  jnz     short loc_1800023D0
0x1800023b8  mov     [rbx], rbp
0x1800023bb  add     rbx, 8
0x1800023bf  cmp     rbx, r14
0x1800023c2  jnz     short loc_1800023B0
0x1800023c4  add     rsp, 20h
0x1800023c8  pop     r14
0x1800023ca  pop     rdi
0x1800023cb  pop     rsi
0x1800023cc  pop     rbp
0x1800023cd  pop     rbx
0x1800023ce  retn
0x1800023d0  mov     rdi, rsi
0x1800023d3  mov     rsi, [rsi+8]
0x1800023d7  call    cs:__imp_GetProcessHeap
0x1800023dd  mov     r8, rdi; lpMem
0x1800023e0  xor     edx, edx; dwFlags
0x1800023e2  mov     rcx, rax; hHeap
0x1800023e5  call    cs:__imp_HeapFree
0x1800023eb  test    rsi, rsi
0x1800023ee  jz      short loc_1800023B8
0x1800023f0  jmp     short loc_1800023D0
```
