# _DllMainCRTStartup

- ea: `0x180001ce0`
- end: `0x180001d1d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001ba4`
- `0x180001ce0`
- `0x1800021c8`

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
0x180001ce0  mov     [rsp+arg_0], rbx
0x180001ce5  mov     [rsp+arg_8], rsi
0x180001cea  push    rdi
0x180001ceb  sub     rsp, 20h
0x180001cef  mov     rdi, r8
0x180001cf2  mov     ebx, edx
0x180001cf4  mov     rsi, rcx
0x180001cf7  cmp     edx, 1
0x180001cfa  jnz     short loc_180001D01
0x180001cfc  call    __security_init_cookie
0x180001d01  mov     r8, rdi; lpvReserved
0x180001d04  mov     edx, ebx; fdwReason
0x180001d06  mov     rcx, rsi; hinstDLL
0x180001d09  mov     rbx, [rsp+28h+arg_0]
0x180001d0e  mov     rsi, [rsp+28h+arg_8]
0x180001d13  add     rsp, 20h
0x180001d17  pop     rdi
0x180001d18  jmp     dllmain_dispatch
```
