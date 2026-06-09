# _DllMainCRTStartup

- ea: `0x180002a20`
- end: `0x180002a5d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800028e4`
- `0x180002a20`
- `0x180003010`

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
0x180002a20  mov     [rsp+arg_0], rbx
0x180002a25  mov     [rsp+arg_8], rsi
0x180002a2a  push    rdi
0x180002a2b  sub     rsp, 20h
0x180002a2f  mov     rdi, r8
0x180002a32  mov     ebx, edx
0x180002a34  mov     rsi, rcx
0x180002a37  cmp     edx, 1
0x180002a3a  jnz     short loc_180002A41
0x180002a3c  call    __security_init_cookie
0x180002a41  mov     r8, rdi; lpvReserved
0x180002a44  mov     edx, ebx; fdwReason
0x180002a46  mov     rcx, rsi; hinstDLL
0x180002a49  mov     rbx, [rsp+28h+arg_0]
0x180002a4e  mov     rsi, [rsp+28h+arg_8]
0x180002a53  add     rsp, 20h
0x180002a57  pop     rdi
0x180002a58  jmp     dllmain_dispatch
```
