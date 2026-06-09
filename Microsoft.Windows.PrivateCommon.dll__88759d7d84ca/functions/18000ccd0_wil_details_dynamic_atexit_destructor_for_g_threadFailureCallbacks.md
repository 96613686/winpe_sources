# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000ccd0`
- end: `0x18000cd57`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `135`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000ccd0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000cd25`
- `KERNEL32!HeapFree` at `0x18000cd25`
- `KERNEL32!GetProcessHeap` at `0x18000cd17`
- `KERNEL32!GetProcessHeap` at `0x18000cd17`

## pseudocode

```c
void wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rsi
  __int64 v1; // rbx
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
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse );
}

```

## disassembly

```asm
0x18000ccd0  mov     [rsp+arg_0], rbx
0x18000ccd5  mov     [rsp+arg_8], rbp
0x18000ccda  mov     [rsp+arg_10], rsi
0x18000ccdf  mov     [rsp+arg_18], rdi
0x18000cce4  push    r14
0x18000cce6  sub     rsp, 20h
0x18000ccea  lea     rsi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000ccf1  xor     ebp, ebp
0x18000ccf3  lea     r14, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse
0x18000ccfa  nop     word ptr [rax+rax+00h]
0x18000cd00  mov     rbx, [rsi]
0x18000cd03  test    rbx, rbx
0x18000cd06  jz      short loc_18000CD30
0x18000cd08  nop     dword ptr [rax+rax+00000000h]
0x18000cd10  mov     rdi, rbx
0x18000cd13  mov     rbx, [rbx+8]
0x18000cd17  call    cs:__imp_GetProcessHeap
0x18000cd1d  mov     r8, rdi; lpMem
0x18000cd20  xor     edx, edx; dwFlags
0x18000cd22  mov     rcx, rax; hHeap
0x18000cd25  call    cs:__imp_HeapFree
0x18000cd2b  test    rbx, rbx
0x18000cd2e  jnz     short loc_18000CD10
0x18000cd30  mov     [rsi], rbp
0x18000cd33  add     rsi, 8
0x18000cd37  cmp     rsi, r14
0x18000cd3a  jnz     short loc_18000CD00
0x18000cd3c  mov     rbx, [rsp+28h+arg_0]
0x18000cd41  mov     rbp, [rsp+28h+arg_8]
0x18000cd46  mov     rsi, [rsp+28h+arg_10]
0x18000cd4b  mov     rdi, [rsp+28h+arg_18]
0x18000cd50  add     rsp, 20h
0x18000cd54  pop     r14
0x18000cd56  retn
```
