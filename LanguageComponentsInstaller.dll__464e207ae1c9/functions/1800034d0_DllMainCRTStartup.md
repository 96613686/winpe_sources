# _DllMainCRTStartup

- ea: `0x1800034d0`
- end: `0x18000350d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003394`
- `0x1800034d0`
- `0x180003d94`

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
0x1800034d0  mov     [rsp+arg_0], rbx
0x1800034d5  mov     [rsp+arg_8], rsi
0x1800034da  push    rdi
0x1800034db  sub     rsp, 20h
0x1800034df  mov     rdi, r8
0x1800034e2  mov     ebx, edx
0x1800034e4  mov     rsi, rcx
0x1800034e7  cmp     edx, 1
0x1800034ea  jnz     short loc_1800034F1
0x1800034ec  call    __security_init_cookie
0x1800034f1  mov     r8, rdi; lpvReserved
0x1800034f4  mov     edx, ebx; fdwReason
0x1800034f6  mov     rcx, rsi; hinstDLL
0x1800034f9  mov     rbx, [rsp+28h+arg_0]
0x1800034fe  mov     rsi, [rsp+28h+arg_8]
0x180003503  add     rsp, 20h
0x180003507  pop     rdi
0x180003508  jmp     dllmain_dispatch
```
