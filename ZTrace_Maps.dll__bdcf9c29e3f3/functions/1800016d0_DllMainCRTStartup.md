# _DllMainCRTStartup

- ea: `0x1800016d0`
- end: `0x18000170d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001594`
- `0x1800016d0`
- `0x180001b44`

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
0x1800016d0  mov     [rsp+arg_0], rbx
0x1800016d5  mov     [rsp+arg_8], rsi
0x1800016da  push    rdi
0x1800016db  sub     rsp, 20h
0x1800016df  mov     rdi, r8
0x1800016e2  mov     ebx, edx
0x1800016e4  mov     rsi, rcx
0x1800016e7  cmp     edx, 1
0x1800016ea  jnz     short loc_1800016F1
0x1800016ec  call    __security_init_cookie
0x1800016f1  mov     r8, rdi; lpvReserved
0x1800016f4  mov     edx, ebx; fdwReason
0x1800016f6  mov     rcx, rsi; hinstDLL
0x1800016f9  mov     rbx, [rsp+28h+arg_0]
0x1800016fe  mov     rsi, [rsp+28h+arg_8]
0x180001703  add     rsp, 20h
0x180001707  pop     rdi
0x180001708  jmp     dllmain_dispatch
```
