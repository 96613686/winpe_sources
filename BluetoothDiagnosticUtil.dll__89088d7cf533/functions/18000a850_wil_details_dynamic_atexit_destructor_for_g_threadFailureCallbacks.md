# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000a850`
- end: `0x18000a8bb`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a850`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000a886`
- `KERNEL32!HeapFree` at `0x18000a886`
- `KERNEL32!GetProcessHeap` at `0x18000a872`
- `KERNEL32!GetProcessHeap` at `0x18000a872`

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
    result = &g_header_init_InitializeResultHeader;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x18000a850  mov     [rsp+arg_0], rbx
0x18000a855  mov     [rsp+arg_8], rsi
0x18000a85a  push    rdi
0x18000a85b  sub     rsp, 20h
0x18000a85f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000a866  mov     rsi, [rdi]
0x18000a869  jmp     short loc_18000A892
0x18000a86b  mov     rbx, rsi
0x18000a86e  mov     rsi, [rsi+8]
0x18000a872  call    cs:__imp_GetProcessHeap
0x18000a879  nop     dword ptr [rax+rax+00h]
0x18000a87e  mov     r8, rbx; lpMem
0x18000a881  xor     edx, edx; dwFlags
0x18000a883  mov     rcx, rax; hHeap
0x18000a886  call    cs:__imp_HeapFree
0x18000a88d  nop     dword ptr [rax+rax+00h]
0x18000a892  test    rsi, rsi
0x18000a895  jnz     short loc_18000A86B
0x18000a897  mov     [rdi], rsi
0x18000a89a  lea     rax, g_header_init_InitializeResultHeader
0x18000a8a1  add     rdi, 8
0x18000a8a5  cmp     rdi, rax
0x18000a8a8  jnz     short loc_18000A866
0x18000a8aa  mov     rbx, [rsp+28h+arg_0]
0x18000a8af  mov     rsi, [rsp+28h+arg_8]
0x18000a8b4  add     rsp, 20h
0x18000a8b8  pop     rdi
0x18000a8b9  retn
```
