# _DllMainCRTStartup

- ea: `0x180001dd0`
- end: `0x180001e0d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001c94`
- `0x180001dd0`
- `0x18000232c`

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
0x180001dd0  mov     [rsp+arg_0], rbx
0x180001dd5  mov     [rsp+arg_8], rsi
0x180001dda  push    rdi
0x180001ddb  sub     rsp, 20h
0x180001ddf  mov     rdi, r8
0x180001de2  mov     ebx, edx
0x180001de4  mov     rsi, rcx
0x180001de7  cmp     edx, 1
0x180001dea  jnz     short loc_180001DF1
0x180001dec  call    __security_init_cookie
0x180001df1  mov     r8, rdi; lpvReserved
0x180001df4  mov     edx, ebx; fdwReason
0x180001df6  mov     rcx, rsi; hinstDLL
0x180001df9  mov     rbx, [rsp+28h+arg_0]
0x180001dfe  mov     rsi, [rsp+28h+arg_8]
0x180001e03  add     rsp, 20h
0x180001e07  pop     rdi
0x180001e08  jmp     dllmain_dispatch
```
