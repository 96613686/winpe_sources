# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000f050`
- end: `0x18000f0ae`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f050`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f072`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f072`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f080`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f080`

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
    result = qword_18001B190;
    ++v0;
  }
  while ( v0 != qword_18001B190 );
  return result;
}

```

## disassembly

```asm
0x18000f050  mov     [rsp+arg_0], rbx
0x18000f055  mov     [rsp+arg_8], rsi
0x18000f05a  push    rdi
0x18000f05b  sub     rsp, 20h
0x18000f05f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000f066  mov     rsi, [rdi]
0x18000f069  jmp     short loc_18000F086
0x18000f06b  mov     rbx, rsi
0x18000f06e  mov     rsi, [rsi+8]
0x18000f072  call    cs:__imp_GetProcessHeap
0x18000f078  mov     r8, rbx; lpMem
0x18000f07b  xor     edx, edx; dwFlags
0x18000f07d  mov     rcx, rax; hHeap
0x18000f080  call    cs:__imp_HeapFree
0x18000f086  test    rsi, rsi
0x18000f089  jnz     short loc_18000F06B
0x18000f08b  mov     [rdi], rsi
0x18000f08e  lea     rax, qword_18001B190
0x18000f095  add     rdi, 8
0x18000f099  cmp     rdi, rax
0x18000f09c  jnz     short loc_18000F066
0x18000f09e  mov     rbx, [rsp+28h+arg_0]
0x18000f0a3  mov     rsi, [rsp+28h+arg_8]
0x18000f0a8  add     rsp, 20h
0x18000f0ac  pop     rdi
0x18000f0ad  retn
```
