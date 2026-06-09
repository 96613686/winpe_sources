# _DllMainCRTStartup

- ea: `0x180001d40`
- end: `0x180001d7d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001d40`
- `0x180001d84`
- `0x180002614`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001d40  mov     [rsp+arg_0], rbx
0x180001d45  mov     [rsp+arg_8], rsi
0x180001d4a  push    rdi
0x180001d4b  sub     rsp, 20h
0x180001d4f  mov     rdi, r8
0x180001d52  mov     ebx, edx
0x180001d54  mov     rsi, rcx
0x180001d57  cmp     edx, 1
0x180001d5a  jnz     short loc_180001D61
0x180001d5c  call    __security_init_cookie
0x180001d61  mov     r8, rdi
0x180001d64  mov     edx, ebx; fdwReason
0x180001d66  mov     rcx, rsi; hinstDLL
0x180001d69  mov     rbx, [rsp+28h+arg_0]
0x180001d6e  mov     rsi, [rsp+28h+arg_8]
0x180001d73  add     rsp, 20h
0x180001d77  pop     rdi
0x180001d78  jmp     __DllMainCRTStartup
```
