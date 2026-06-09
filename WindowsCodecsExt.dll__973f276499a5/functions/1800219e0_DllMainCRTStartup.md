# _DllMainCRTStartup

- ea: `0x1800219e0`
- end: `0x180021a1d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800218a4`
- `0x1800219e0`
- `0x180021a60`

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
0x1800219e0  mov     [rsp+arg_0], rbx
0x1800219e5  mov     [rsp+arg_8], rsi
0x1800219ea  push    rdi
0x1800219eb  sub     rsp, 20h
0x1800219ef  mov     rdi, r8
0x1800219f2  mov     ebx, edx
0x1800219f4  mov     rsi, rcx
0x1800219f7  cmp     edx, 1
0x1800219fa  jnz     short loc_180021A01
0x1800219fc  call    __security_init_cookie
0x180021a01  mov     r8, rdi; lpvReserved
0x180021a04  mov     edx, ebx; fdwReason
0x180021a06  mov     rcx, rsi; hinstDLL
0x180021a09  mov     rbx, [rsp+28h+arg_0]
0x180021a0e  mov     rsi, [rsp+28h+arg_8]
0x180021a13  add     rsp, 20h
0x180021a17  pop     rdi
0x180021a18  jmp     dllmain_dispatch
```
