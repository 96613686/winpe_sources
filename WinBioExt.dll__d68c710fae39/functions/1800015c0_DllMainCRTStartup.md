# _DllMainCRTStartup

- ea: `0x1800015c0`
- end: `0x1800015fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001484`
- `0x1800015c0`
- `0x180001a40`

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
0x1800015c0  mov     [rsp+arg_0], rbx
0x1800015c5  mov     [rsp+arg_8], rsi
0x1800015ca  push    rdi
0x1800015cb  sub     rsp, 20h
0x1800015cf  mov     rdi, r8
0x1800015d2  mov     ebx, edx
0x1800015d4  mov     rsi, rcx
0x1800015d7  cmp     edx, 1
0x1800015da  jnz     short loc_1800015E1
0x1800015dc  call    __security_init_cookie
0x1800015e1  mov     r8, rdi; lpvReserved
0x1800015e4  mov     edx, ebx; fdwReason
0x1800015e6  mov     rcx, rsi; hinstDLL
0x1800015e9  mov     rbx, [rsp+28h+arg_0]
0x1800015ee  mov     rsi, [rsp+28h+arg_8]
0x1800015f3  add     rsp, 20h
0x1800015f7  pop     rdi
0x1800015f8  jmp     dllmain_dispatch
```
