# _DllMainCRTStartup

- ea: `0x180003380`
- end: `0x1800033bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003244`
- `0x180003380`
- `0x180003aac`

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
0x180003380  mov     [rsp+arg_0], rbx
0x180003385  mov     [rsp+arg_8], rsi
0x18000338a  push    rdi
0x18000338b  sub     rsp, 20h
0x18000338f  mov     rdi, r8
0x180003392  mov     ebx, edx
0x180003394  mov     rsi, rcx
0x180003397  cmp     edx, 1
0x18000339a  jnz     short loc_1800033A1
0x18000339c  call    __security_init_cookie
0x1800033a1  mov     r8, rdi; lpvReserved
0x1800033a4  mov     edx, ebx; fdwReason
0x1800033a6  mov     rcx, rsi; hinstDLL
0x1800033a9  mov     rbx, [rsp+28h+arg_0]
0x1800033ae  mov     rsi, [rsp+28h+arg_8]
0x1800033b3  add     rsp, 20h
0x1800033b7  pop     rdi
0x1800033b8  jmp     dllmain_dispatch
```
