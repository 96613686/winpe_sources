# _DllMainCRTStartup

- ea: `0x1800188f0`
- end: `0x18001892d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800187bc`
- `0x1800188f0`
- `0x18001904c`

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
0x1800188f0  mov     [rsp+arg_0], rbx
0x1800188f5  mov     [rsp+arg_8], rsi
0x1800188fa  push    rdi
0x1800188fb  sub     rsp, 20h
0x1800188ff  mov     rdi, r8
0x180018902  mov     ebx, edx
0x180018904  mov     rsi, rcx
0x180018907  cmp     edx, 1
0x18001890a  jnz     short loc_180018911
0x18001890c  call    __security_init_cookie
0x180018911  mov     r8, rdi
0x180018914  mov     edx, ebx
0x180018916  mov     rcx, rsi
0x180018919  mov     rbx, [rsp+28h+arg_0]
0x18001891e  mov     rsi, [rsp+28h+arg_8]
0x180018923  add     rsp, 20h
0x180018927  pop     rdi
0x180018928  jmp     dllmain_dispatch
```
