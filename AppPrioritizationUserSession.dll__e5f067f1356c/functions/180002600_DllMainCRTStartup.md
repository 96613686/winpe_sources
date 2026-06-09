# _DllMainCRTStartup

- ea: `0x180002600`
- end: `0x18000263d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800024c4`
- `0x180002600`
- `0x180002f30`

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
0x180002600  mov     [rsp+arg_0], rbx
0x180002605  mov     [rsp+arg_8], rsi
0x18000260a  push    rdi
0x18000260b  sub     rsp, 20h
0x18000260f  mov     rdi, r8
0x180002612  mov     ebx, edx
0x180002614  mov     rsi, rcx
0x180002617  cmp     edx, 1
0x18000261a  jnz     short loc_180002621
0x18000261c  call    __security_init_cookie
0x180002621  mov     r8, rdi; lpvReserved
0x180002624  mov     edx, ebx; fdwReason
0x180002626  mov     rcx, rsi; hinstDLL
0x180002629  mov     rbx, [rsp+28h+arg_0]
0x18000262e  mov     rsi, [rsp+28h+arg_8]
0x180002633  add     rsp, 20h
0x180002637  pop     rdi
0x180002638  jmp     dllmain_dispatch
```
