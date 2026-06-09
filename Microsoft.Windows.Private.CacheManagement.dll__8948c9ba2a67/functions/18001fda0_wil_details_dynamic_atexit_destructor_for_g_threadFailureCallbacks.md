# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001fda0`
- end: `0x18001fe27`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001fda0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001fdf5`
- `KERNEL32!HeapFree` at `0x18001fdf5`
- `KERNEL32!GetProcessHeap` at `0x18001fde7`
- `KERNEL32!GetProcessHeap` at `0x18001fde7`

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
0x18001fda0  mov     [rsp+arg_0], rbx
0x18001fda5  mov     [rsp+arg_8], rbp
0x18001fdaa  mov     [rsp+arg_10], rsi
0x18001fdaf  mov     [rsp+arg_18], rdi
0x18001fdb4  push    r14
0x18001fdb6  sub     rsp, 20h
0x18001fdba  lea     rsi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001fdc1  xor     ebp, ebp
0x18001fdc3  lea     r14, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse
0x18001fdca  nop     word ptr [rax+rax+00h]
0x18001fdd0  mov     rbx, [rsi]
0x18001fdd3  test    rbx, rbx
0x18001fdd6  jz      short loc_18001FE00
0x18001fdd8  nop     dword ptr [rax+rax+00000000h]
0x18001fde0  mov     rdi, rbx
0x18001fde3  mov     rbx, [rbx+8]
0x18001fde7  call    cs:__imp_GetProcessHeap
0x18001fded  mov     r8, rdi; lpMem
0x18001fdf0  xor     edx, edx; dwFlags
0x18001fdf2  mov     rcx, rax; hHeap
0x18001fdf5  call    cs:__imp_HeapFree
0x18001fdfb  test    rbx, rbx
0x18001fdfe  jnz     short loc_18001FDE0
0x18001fe00  mov     [rsi], rbp
0x18001fe03  add     rsi, 8
0x18001fe07  cmp     rsi, r14
0x18001fe0a  jnz     short loc_18001FDD0
0x18001fe0c  mov     rbx, [rsp+28h+arg_0]
0x18001fe11  mov     rbp, [rsp+28h+arg_8]
0x18001fe16  mov     rsi, [rsp+28h+arg_10]
0x18001fe1b  mov     rdi, [rsp+28h+arg_18]
0x18001fe20  add     rsp, 20h
0x18001fe24  pop     r14
0x18001fe26  retn
```
