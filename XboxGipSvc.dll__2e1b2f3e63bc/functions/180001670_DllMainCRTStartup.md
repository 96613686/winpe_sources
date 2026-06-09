# _DllMainCRTStartup

- ea: `0x180001670`
- end: `0x1800016ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001534`
- `0x180001670`
- `0x180001b78`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001670  mov     [rsp+arg_0], rbx
0x180001675  mov     [rsp+arg_8], rsi
0x18000167a  push    rdi
0x18000167b  sub     rsp, 20h
0x18000167f  mov     rdi, r8
0x180001682  mov     ebx, edx
0x180001684  mov     rsi, rcx
0x180001687  cmp     edx, 1
0x18000168a  jnz     short loc_180001691
0x18000168c  call    __security_init_cookie
0x180001691  mov     r8, rdi; lpvReserved
0x180001694  mov     edx, ebx; fdwReason
0x180001696  mov     rcx, rsi; hinstDLL
0x180001699  mov     rbx, [rsp+28h+arg_0]
0x18000169e  mov     rsi, [rsp+28h+arg_8]
0x1800016a3  add     rsp, 20h
0x1800016a7  pop     rdi
0x1800016a8  jmp     dllmain_dispatch
```
