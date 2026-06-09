# _DllMainCRTStartup

- ea: `0x180001fd0`
- end: `0x18000200d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001e94`
- `0x180001fd0`
- `0x18000256c`

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
0x180001fd0  mov     [rsp+arg_0], rbx
0x180001fd5  mov     [rsp+arg_8], rsi
0x180001fda  push    rdi
0x180001fdb  sub     rsp, 20h
0x180001fdf  mov     rdi, r8
0x180001fe2  mov     ebx, edx
0x180001fe4  mov     rsi, rcx
0x180001fe7  cmp     edx, 1
0x180001fea  jnz     short loc_180001FF1
0x180001fec  call    __security_init_cookie
0x180001ff1  mov     r8, rdi; lpvReserved
0x180001ff4  mov     edx, ebx; fdwReason
0x180001ff6  mov     rcx, rsi; hinstDLL
0x180001ff9  mov     rbx, [rsp+28h+arg_0]
0x180001ffe  mov     rsi, [rsp+28h+arg_8]
0x180002003  add     rsp, 20h
0x180002007  pop     rdi
0x180002008  jmp     dllmain_dispatch
```
