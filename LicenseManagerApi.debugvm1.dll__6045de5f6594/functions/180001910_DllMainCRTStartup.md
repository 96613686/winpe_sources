# _DllMainCRTStartup

- ea: `0x180001910`
- end: `0x18000194d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800017d4`
- `0x180001910`
- `0x180001d6c`

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
0x180001910  mov     [rsp+arg_0], rbx
0x180001915  mov     [rsp+arg_8], rsi
0x18000191a  push    rdi
0x18000191b  sub     rsp, 20h
0x18000191f  mov     rdi, r8
0x180001922  mov     ebx, edx
0x180001924  mov     rsi, rcx
0x180001927  cmp     edx, 1
0x18000192a  jnz     short loc_180001931
0x18000192c  call    __security_init_cookie
0x180001931  mov     r8, rdi; lpvReserved
0x180001934  mov     edx, ebx; fdwReason
0x180001936  mov     rcx, rsi; hinstDLL
0x180001939  mov     rbx, [rsp+28h+arg_0]
0x18000193e  mov     rsi, [rsp+28h+arg_8]
0x180001943  add     rsp, 20h
0x180001947  pop     rdi
0x180001948  jmp     dllmain_dispatch
```
