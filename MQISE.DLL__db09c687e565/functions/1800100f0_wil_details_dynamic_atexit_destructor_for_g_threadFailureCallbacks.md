# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800100f0`
- end: `0x18001014e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800100f0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180010112`
- `KERNEL32!GetProcessHeap` at `0x180010112`
- `KERNEL32!HeapFree` at `0x180010120`
- `KERNEL32!HeapFree` at `0x180010120`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    *v0++ = 0;
    result = g_header_init_InitializeResultHeader;
  }
  while ( v0 != g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x1800100f0  mov     [rsp+arg_0], rbx
0x1800100f5  mov     [rsp+arg_8], rsi
0x1800100fa  push    rdi
0x1800100fb  sub     rsp, 20h
0x1800100ff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180010106  mov     rsi, [rdi]
0x180010109  jmp     short loc_180010126
0x18001010b  mov     rbx, rsi
0x18001010e  mov     rsi, [rsi+8]
0x180010112  call    cs:__imp_GetProcessHeap
0x180010118  mov     rcx, rax; hHeap
0x18001011b  mov     r8, rbx; lpMem
0x18001011e  xor     edx, edx; dwFlags
0x180010120  call    cs:__imp_HeapFree
0x180010126  test    rsi, rsi
0x180010129  jnz     short loc_18001010B
0x18001012b  mov     [rdi], rsi
0x18001012e  add     rdi, 8
0x180010132  lea     rax, g_header_init_InitializeResultHeader
0x180010139  cmp     rdi, rax
0x18001013c  jnz     short loc_180010106
0x18001013e  mov     rbx, [rsp+28h+arg_0]
0x180010143  mov     rsi, [rsp+28h+arg_8]
0x180010148  add     rsp, 20h
0x18001014c  pop     rdi
0x18001014d  retn
```
