# _DllMainCRTStartup

- ea: `0x1800015e0`
- end: `0x18000161d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800014a4`
- `0x1800015e0`
- `0x180001654`

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
0x1800015e0  mov     [rsp+arg_0], rbx
0x1800015e5  mov     [rsp+arg_8], rsi
0x1800015ea  push    rdi
0x1800015eb  sub     rsp, 20h
0x1800015ef  mov     rdi, r8
0x1800015f2  mov     ebx, edx
0x1800015f4  mov     rsi, rcx
0x1800015f7  cmp     edx, 1
0x1800015fa  jnz     short loc_180001601
0x1800015fc  call    __security_init_cookie
0x180001601  mov     r8, rdi; lpvReserved
0x180001604  mov     edx, ebx; fdwReason
0x180001606  mov     rcx, rsi; hinstDLL
0x180001609  mov     rbx, [rsp+28h+arg_0]
0x18000160e  mov     rsi, [rsp+28h+arg_8]
0x180001613  add     rsp, 20h
0x180001617  pop     rdi
0x180001618  jmp     dllmain_dispatch
```
