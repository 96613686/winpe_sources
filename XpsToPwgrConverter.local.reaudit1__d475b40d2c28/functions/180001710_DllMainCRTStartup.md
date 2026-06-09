# _DllMainCRTStartup

- ea: `0x180001710`
- end: `0x18000174d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800015d4`
- `0x180001710`
- `0x180001b9c`

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
0x180001710  mov     [rsp+arg_0], rbx
0x180001715  mov     [rsp+arg_8], rsi
0x18000171a  push    rdi
0x18000171b  sub     rsp, 20h
0x18000171f  mov     rdi, r8
0x180001722  mov     ebx, edx
0x180001724  mov     rsi, rcx
0x180001727  cmp     edx, 1
0x18000172a  jnz     short loc_180001731
0x18000172c  call    __security_init_cookie
0x180001731  mov     r8, rdi; lpvReserved
0x180001734  mov     edx, ebx; fdwReason
0x180001736  mov     rcx, rsi; hinstDLL
0x180001739  mov     rbx, [rsp+28h+arg_0]
0x18000173e  mov     rsi, [rsp+28h+arg_8]
0x180001743  add     rsp, 20h
0x180001747  pop     rdi
0x180001748  jmp     dllmain_dispatch
```
