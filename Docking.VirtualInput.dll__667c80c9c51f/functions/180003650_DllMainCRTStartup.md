# _DllMainCRTStartup

- ea: `0x180003650`
- end: `0x18000368d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003514`
- `0x180003650`
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
0x180003650  mov     [rsp+arg_0], rbx
0x180003655  mov     [rsp+arg_8], rsi
0x18000365a  push    rdi
0x18000365b  sub     rsp, 20h
0x18000365f  mov     rdi, r8
0x180003662  mov     ebx, edx
0x180003664  mov     rsi, rcx
0x180003667  cmp     edx, 1
0x18000366a  jnz     short loc_180003671
0x18000366c  call    __security_init_cookie
0x180003671  mov     r8, rdi; lpvReserved
0x180003674  mov     edx, ebx; fdwReason
0x180003676  mov     rcx, rsi; hinstDLL
0x180003679  mov     rbx, [rsp+28h+arg_0]
0x18000367e  mov     rsi, [rsp+28h+arg_8]
0x180003683  add     rsp, 20h
0x180003687  pop     rdi
0x180003688  jmp     dllmain_dispatch
```
