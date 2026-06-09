# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140001e20`
- end: `0x140001e78`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140001e20`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001e54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140001e54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140001e46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140001e46`

## pseudocode

```c
void wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  char *v0; // rbx
  _QWORD *v1; // rsi
  void *v2; // rdi
  HANDLE ProcessHeap; // rax

  v0 = (char *)wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *(_QWORD **)v0;
    if ( *(_QWORD *)v0 )
    {
      do
      {
        v2 = v1;
        v1 = (_QWORD *)v1[1];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v2);
      }
      while ( v1 );
    }
    *(_QWORD *)v0 = 0;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeStagingHeaderInternalApi );
}

```

## disassembly

```asm
0x140001e20  push    rbx
0x140001e22  push    rbp
0x140001e23  push    rsi
0x140001e24  push    rdi
0x140001e25  sub     rsp, 28h
0x140001e29  lea     rbx, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140001e30  lea     rbp, g_header_init_InitializeStagingHeaderInternalApi
0x140001e37  mov     rsi, [rbx]
0x140001e3a  test    rsi, rsi
0x140001e3d  jz      short loc_140001E5F
0x140001e3f  mov     rdi, rsi
0x140001e42  mov     rsi, [rsi+8]
0x140001e46  call    cs:__imp_GetProcessHeap
0x140001e4c  mov     r8, rdi; lpMem
0x140001e4f  xor     edx, edx; dwFlags
0x140001e51  mov     rcx, rax; hHeap
0x140001e54  call    cs:__imp_HeapFree
0x140001e5a  test    rsi, rsi
0x140001e5d  jnz     short loc_140001E3F
0x140001e5f  mov     qword ptr [rbx], 0
0x140001e66  add     rbx, 8
0x140001e6a  cmp     rbx, rbp
0x140001e6d  jnz     short loc_140001E37
0x140001e6f  add     rsp, 28h
0x140001e73  pop     rdi
0x140001e74  pop     rsi
0x140001e75  pop     rbp
0x140001e76  pop     rbx
0x140001e77  retn
```
