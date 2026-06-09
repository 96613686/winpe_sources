# _DllMainCRTStartup

- ea: `0x180003250`
- end: `0x18000328d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003114`
- `0x180003250`
- `0x18000371c`

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
0x180003250  mov     [rsp+arg_0], rbx
0x180003255  mov     [rsp+arg_8], rsi
0x18000325a  push    rdi
0x18000325b  sub     rsp, 20h
0x18000325f  mov     rdi, r8
0x180003262  mov     ebx, edx
0x180003264  mov     rsi, rcx
0x180003267  cmp     edx, 1
0x18000326a  jnz     short loc_180003271
0x18000326c  call    __security_init_cookie
0x180003271  mov     r8, rdi; lpvReserved
0x180003274  mov     edx, ebx; fdwReason
0x180003276  mov     rcx, rsi; hinstDLL
0x180003279  mov     rbx, [rsp+28h+arg_0]
0x18000327e  mov     rsi, [rsp+28h+arg_8]
0x180003283  add     rsp, 20h
0x180003287  pop     rdi
0x180003288  jmp     dllmain_dispatch
```
