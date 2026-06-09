# _DllMainCRTStartup

- ea: `0x180001d10`
- end: `0x180001d4d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001bd4`
- `0x180001d10`
- `0x18000219c`

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
0x180001d10  mov     [rsp+arg_0], rbx
0x180001d15  mov     [rsp+arg_8], rsi
0x180001d1a  push    rdi
0x180001d1b  sub     rsp, 20h
0x180001d1f  mov     rdi, r8
0x180001d22  mov     ebx, edx
0x180001d24  mov     rsi, rcx
0x180001d27  cmp     edx, 1
0x180001d2a  jnz     short loc_180001D31
0x180001d2c  call    __security_init_cookie
0x180001d31  mov     r8, rdi; lpvReserved
0x180001d34  mov     edx, ebx; fdwReason
0x180001d36  mov     rcx, rsi; hinstDLL
0x180001d39  mov     rbx, [rsp+28h+arg_0]
0x180001d3e  mov     rsi, [rsp+28h+arg_8]
0x180001d43  add     rsp, 20h
0x180001d47  pop     rdi
0x180001d48  jmp     dllmain_dispatch
```
