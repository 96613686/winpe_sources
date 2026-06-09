# _DllMainCRTStartup

- ea: `0x180001cf0`
- end: `0x180001d2d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001bb4`
- `0x180001cf0`
- `0x180002140`

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
0x180001cf0  mov     [rsp+arg_0], rbx
0x180001cf5  mov     [rsp+arg_8], rsi
0x180001cfa  push    rdi
0x180001cfb  sub     rsp, 20h
0x180001cff  mov     rdi, r8
0x180001d02  mov     ebx, edx
0x180001d04  mov     rsi, rcx
0x180001d07  cmp     edx, 1
0x180001d0a  jnz     short loc_180001D11
0x180001d0c  call    __security_init_cookie
0x180001d11  mov     r8, rdi; lpvReserved
0x180001d14  mov     edx, ebx; fdwReason
0x180001d16  mov     rcx, rsi; hinstDLL
0x180001d19  mov     rbx, [rsp+28h+arg_0]
0x180001d1e  mov     rsi, [rsp+28h+arg_8]
0x180001d23  add     rsp, 20h
0x180001d27  pop     rdi
0x180001d28  jmp     dllmain_dispatch
```
