# _DllMainCRTStartup

- ea: `0x180001430`
- end: `0x18000146d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800012f4`
- `0x180001430`
- `0x180001bf0`

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
0x180001430  mov     [rsp+arg_0], rbx
0x180001435  mov     [rsp+arg_8], rsi
0x18000143a  push    rdi
0x18000143b  sub     rsp, 20h
0x18000143f  mov     rdi, r8
0x180001442  mov     ebx, edx
0x180001444  mov     rsi, rcx
0x180001447  cmp     edx, 1
0x18000144a  jnz     short loc_180001451
0x18000144c  call    __security_init_cookie
0x180001451  mov     r8, rdi; lpvReserved
0x180001454  mov     edx, ebx; fdwReason
0x180001456  mov     rcx, rsi; hinstDLL
0x180001459  mov     rbx, [rsp+28h+arg_0]
0x18000145e  mov     rsi, [rsp+28h+arg_8]
0x180001463  add     rsp, 20h
0x180001467  pop     rdi
0x180001468  jmp     dllmain_dispatch
```
