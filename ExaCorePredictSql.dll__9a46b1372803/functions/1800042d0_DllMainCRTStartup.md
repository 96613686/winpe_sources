# _DllMainCRTStartup

- ea: `0x1800042d0`
- end: `0x18000430d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004180`
- `0x1800042d0`
- `0x1800047c4`

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
0x1800042d0  mov     [rsp+arg_0], rbx
0x1800042d5  mov     [rsp+arg_8], rsi
0x1800042da  push    rdi
0x1800042db  sub     rsp, 20h
0x1800042df  mov     rdi, r8
0x1800042e2  mov     ebx, edx
0x1800042e4  mov     rsi, rcx
0x1800042e7  cmp     edx, 1
0x1800042ea  jnz     short loc_1800042F1
0x1800042ec  call    __security_init_cookie
0x1800042f1  mov     r8, rdi; lpvReserved
0x1800042f4  mov     edx, ebx; fdwReason
0x1800042f6  mov     rcx, rsi; hinstDLL
0x1800042f9  mov     rbx, [rsp+28h+arg_0]
0x1800042fe  mov     rsi, [rsp+28h+arg_8]
0x180004303  add     rsp, 20h
0x180004307  pop     rdi
0x180004308  jmp     dllmain_dispatch
```
