# _DllMainCRTStartup

- ea: `0x180004c20`
- end: `0x180004c5d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180004ae4`
- `0x180004c20`
- `0x1800050ac`

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
0x180004c20  mov     [rsp+arg_0], rbx
0x180004c25  mov     [rsp+arg_8], rsi
0x180004c2a  push    rdi
0x180004c2b  sub     rsp, 20h
0x180004c2f  mov     rdi, r8
0x180004c32  mov     ebx, edx
0x180004c34  mov     rsi, rcx
0x180004c37  cmp     edx, 1
0x180004c3a  jnz     short loc_180004C41
0x180004c3c  call    __security_init_cookie
0x180004c41  mov     r8, rdi; lpvReserved
0x180004c44  mov     edx, ebx; fdwReason
0x180004c46  mov     rcx, rsi; hinstDLL
0x180004c49  mov     rbx, [rsp+28h+arg_0]
0x180004c4e  mov     rsi, [rsp+28h+arg_8]
0x180004c53  add     rsp, 20h
0x180004c57  pop     rdi
0x180004c58  jmp     dllmain_dispatch
```
