# _DllMainCRTStartup

- ea: `0x1800013f0`
- end: `0x18000142d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800012b4`
- `0x1800013f0`
- `0x180001470`

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
0x1800013f0  mov     [rsp+arg_0], rbx
0x1800013f5  mov     [rsp+arg_8], rsi
0x1800013fa  push    rdi
0x1800013fb  sub     rsp, 20h
0x1800013ff  mov     rdi, r8
0x180001402  mov     ebx, edx
0x180001404  mov     rsi, rcx
0x180001407  cmp     edx, 1
0x18000140a  jnz     short loc_180001411
0x18000140c  call    __security_init_cookie
0x180001411  mov     r8, rdi; lpvReserved
0x180001414  mov     edx, ebx; fdwReason
0x180001416  mov     rcx, rsi; hinstDLL
0x180001419  mov     rbx, [rsp+28h+arg_0]
0x18000141e  mov     rsi, [rsp+28h+arg_8]
0x180001423  add     rsp, 20h
0x180001427  pop     rdi
0x180001428  jmp     dllmain_dispatch
```
