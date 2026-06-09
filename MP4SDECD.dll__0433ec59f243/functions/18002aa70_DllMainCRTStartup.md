# _DllMainCRTStartup

- ea: `0x18002aa70`
- end: `0x18002aaad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18002a934`
- `0x18002aa70`
- `0x18002aaf0`

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
0x18002aa70  mov     [rsp+arg_0], rbx
0x18002aa75  mov     [rsp+arg_8], rsi
0x18002aa7a  push    rdi
0x18002aa7b  sub     rsp, 20h
0x18002aa7f  mov     rdi, r8
0x18002aa82  mov     ebx, edx
0x18002aa84  mov     rsi, rcx
0x18002aa87  cmp     edx, 1
0x18002aa8a  jnz     short loc_18002AA91
0x18002aa8c  call    __security_init_cookie
0x18002aa91  mov     r8, rdi; lpvReserved
0x18002aa94  mov     edx, ebx; fdwReason
0x18002aa96  mov     rcx, rsi; hinstDLL
0x18002aa99  mov     rbx, [rsp+28h+arg_0]
0x18002aa9e  mov     rsi, [rsp+28h+arg_8]
0x18002aaa3  add     rsp, 20h
0x18002aaa7  pop     rdi
0x18002aaa8  jmp     dllmain_dispatch
```
