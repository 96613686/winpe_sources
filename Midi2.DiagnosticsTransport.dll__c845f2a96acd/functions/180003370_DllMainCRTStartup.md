# _DllMainCRTStartup

- ea: `0x180003370`
- end: `0x1800033ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003234`
- `0x180003370`
- `0x180003e1c`

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
0x180003370  mov     [rsp+arg_0], rbx
0x180003375  mov     [rsp+arg_8], rsi
0x18000337a  push    rdi
0x18000337b  sub     rsp, 20h
0x18000337f  mov     rdi, r8
0x180003382  mov     ebx, edx
0x180003384  mov     rsi, rcx
0x180003387  cmp     edx, 1
0x18000338a  jnz     short loc_180003391
0x18000338c  call    __security_init_cookie
0x180003391  mov     r8, rdi; lpvReserved
0x180003394  mov     edx, ebx; fdwReason
0x180003396  mov     rcx, rsi; hinstDLL
0x180003399  mov     rbx, [rsp+28h+arg_0]
0x18000339e  mov     rsi, [rsp+28h+arg_8]
0x1800033a3  add     rsp, 20h
0x1800033a7  pop     rdi
0x1800033a8  jmp     dllmain_dispatch
```
