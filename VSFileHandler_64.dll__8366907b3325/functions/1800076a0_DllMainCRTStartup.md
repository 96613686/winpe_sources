# _DllMainCRTStartup

- ea: `0x1800076a0`
- end: `0x1800076dd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007578`
- `0x1800076a0`
- `0x180007dc4`

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
0x1800076a0  mov     [rsp+arg_0], rbx
0x1800076a5  mov     [rsp+arg_8], rsi
0x1800076aa  push    rdi
0x1800076ab  sub     rsp, 20h
0x1800076af  mov     rdi, r8
0x1800076b2  mov     ebx, edx
0x1800076b4  mov     rsi, rcx
0x1800076b7  cmp     edx, 1
0x1800076ba  jnz     short loc_1800076C1
0x1800076bc  call    __security_init_cookie
0x1800076c1  mov     r8, rdi; lpvReserved
0x1800076c4  mov     edx, ebx; fdwReason
0x1800076c6  mov     rcx, rsi; hinstDLL
0x1800076c9  mov     rbx, [rsp+28h+arg_0]
0x1800076ce  mov     rsi, [rsp+28h+arg_8]
0x1800076d3  add     rsp, 20h
0x1800076d7  pop     rdi
0x1800076d8  jmp     dllmain_dispatch
```
