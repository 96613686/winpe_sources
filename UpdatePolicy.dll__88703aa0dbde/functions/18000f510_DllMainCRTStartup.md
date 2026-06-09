# _DllMainCRTStartup

- ea: `0x18000f510`
- end: `0x18000f54d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000f3dc`
- `0x18000f510`
- `0x18000fb88`

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
0x18000f510  mov     [rsp+arg_0], rbx
0x18000f515  mov     [rsp+arg_8], rsi
0x18000f51a  push    rdi
0x18000f51b  sub     rsp, 20h
0x18000f51f  mov     rdi, r8
0x18000f522  mov     ebx, edx
0x18000f524  mov     rsi, rcx
0x18000f527  cmp     edx, 1
0x18000f52a  jnz     short loc_18000F531
0x18000f52c  call    __security_init_cookie
0x18000f531  mov     r8, rdi; lpvReserved
0x18000f534  mov     edx, ebx; fdwReason
0x18000f536  mov     rcx, rsi; hinstDLL
0x18000f539  mov     rbx, [rsp+28h+arg_0]
0x18000f53e  mov     rsi, [rsp+28h+arg_8]
0x18000f543  add     rsp, 20h
0x18000f547  pop     rdi
0x18000f548  jmp     dllmain_dispatch
```
