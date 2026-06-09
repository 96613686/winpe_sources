# _DllMainCRTStartup

- ea: `0x180001e90`
- end: `0x180001ecd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d54`
- `0x180001e90`
- `0x180002390`

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
0x180001e90  mov     [rsp+arg_0], rbx
0x180001e95  mov     [rsp+arg_8], rsi
0x180001e9a  push    rdi
0x180001e9b  sub     rsp, 20h
0x180001e9f  mov     rdi, r8
0x180001ea2  mov     ebx, edx
0x180001ea4  mov     rsi, rcx
0x180001ea7  cmp     edx, 1
0x180001eaa  jnz     short loc_180001EB1
0x180001eac  call    __security_init_cookie
0x180001eb1  mov     r8, rdi; lpvReserved
0x180001eb4  mov     edx, ebx; fdwReason
0x180001eb6  mov     rcx, rsi; hinstDLL
0x180001eb9  mov     rbx, [rsp+28h+arg_0]
0x180001ebe  mov     rsi, [rsp+28h+arg_8]
0x180001ec3  add     rsp, 20h
0x180001ec7  pop     rdi
0x180001ec8  jmp     dllmain_dispatch
```
