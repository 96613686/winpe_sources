# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180010900`
- end: `0x18001096b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010900`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180010922`
- `KERNEL32!GetProcessHeap` at `0x180010922`
- `KERNEL32!HeapFree` at `0x180010936`
- `KERNEL32!HeapFree` at `0x180010936`

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
    result = qword_1800181D0;
    ++v0;
  }
  while ( v0 != qword_1800181D0 );
  return result;
}

```

## disassembly

```asm
0x180010900  mov     [rsp+arg_0], rbx
0x180010905  mov     [rsp+arg_8], rsi
0x18001090a  push    rdi
0x18001090b  sub     rsp, 20h
0x18001090f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180010916  mov     rsi, [rdi]
0x180010919  jmp     short loc_180010942
0x18001091b  mov     rbx, rsi
0x18001091e  mov     rsi, [rsi+8]
0x180010922  call    cs:__imp_GetProcessHeap
0x180010929  nop     dword ptr [rax+rax+00h]
0x18001092e  mov     r8, rbx; lpMem
0x180010931  xor     edx, edx; dwFlags
0x180010933  mov     rcx, rax; hHeap
0x180010936  call    cs:__imp_HeapFree
0x18001093d  nop     dword ptr [rax+rax+00h]
0x180010942  test    rsi, rsi
0x180010945  jnz     short loc_18001091B
0x180010947  mov     [rdi], rsi
0x18001094a  lea     rax, qword_1800181D0
0x180010951  add     rdi, 8
0x180010955  cmp     rdi, rax
0x180010958  jnz     short loc_180010916
0x18001095a  mov     rbx, [rsp+28h+arg_0]
0x18001095f  mov     rsi, [rsp+28h+arg_8]
0x180010964  add     rsp, 20h
0x180010968  pop     rdi
0x180010969  retn
```
