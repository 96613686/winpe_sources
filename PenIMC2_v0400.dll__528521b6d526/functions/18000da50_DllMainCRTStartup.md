# _DllMainCRTStartup

- ea: `0x18000da50`
- end: `0x18000da8d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000d91c`
- `0x18000da50`
- `0x18000df44`

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
0x18000da50  mov     [rsp+arg_0], rbx
0x18000da55  mov     [rsp+arg_8], rsi
0x18000da5a  push    rdi
0x18000da5b  sub     rsp, 20h
0x18000da5f  mov     rdi, r8
0x18000da62  mov     ebx, edx
0x18000da64  mov     rsi, rcx
0x18000da67  cmp     edx, 1
0x18000da6a  jnz     short loc_18000DA71
0x18000da6c  call    __security_init_cookie
0x18000da71  mov     r8, rdi; lpvReserved
0x18000da74  mov     edx, ebx; fdwReason
0x18000da76  mov     rcx, rsi; hinstDLL
0x18000da79  mov     rbx, [rsp+28h+arg_0]
0x18000da7e  mov     rsi, [rsp+28h+arg_8]
0x18000da83  add     rsp, 20h
0x18000da87  pop     rdi
0x18000da88  jmp     dllmain_dispatch
```
