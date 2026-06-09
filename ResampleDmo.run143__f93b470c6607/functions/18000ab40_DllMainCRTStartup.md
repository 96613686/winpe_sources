# _DllMainCRTStartup

- ea: `0x18000ab40`
- end: `0x18000ab7d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000aa04`
- `0x18000ab40`
- `0x18000ac40`

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
0x18000ab40  mov     [rsp+arg_0], rbx
0x18000ab45  mov     [rsp+arg_8], rsi
0x18000ab4a  push    rdi
0x18000ab4b  sub     rsp, 20h
0x18000ab4f  mov     rdi, r8
0x18000ab52  mov     ebx, edx
0x18000ab54  mov     rsi, rcx
0x18000ab57  cmp     edx, 1
0x18000ab5a  jnz     short loc_18000AB61
0x18000ab5c  call    __security_init_cookie
0x18000ab61  mov     r8, rdi; lpvReserved
0x18000ab64  mov     edx, ebx; fdwReason
0x18000ab66  mov     rcx, rsi; hinstDLL
0x18000ab69  mov     rbx, [rsp+28h+arg_0]
0x18000ab6e  mov     rsi, [rsp+28h+arg_8]
0x18000ab73  add     rsp, 20h
0x18000ab77  pop     rdi
0x18000ab78  jmp     dllmain_dispatch
```
