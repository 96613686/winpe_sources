# _DllMainCRTStartup

- ea: `0x180004180`
- end: `0x1800041bd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004180`
- `0x1800041c4`
- `0x1800044d4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180004180  mov     [rsp+arg_0], rbx
0x180004185  mov     [rsp+arg_8], rsi
0x18000418a  push    rdi
0x18000418b  sub     rsp, 20h
0x18000418f  mov     rdi, r8
0x180004192  mov     ebx, edx
0x180004194  mov     rsi, rcx
0x180004197  cmp     edx, 1
0x18000419a  jnz     short loc_1800041A1
0x18000419c  call    __security_init_cookie
0x1800041a1  mov     r8, rdi
0x1800041a4  mov     edx, ebx; fdwReason
0x1800041a6  mov     rcx, rsi; hinstDLL
0x1800041a9  mov     rbx, [rsp+28h+arg_0]
0x1800041ae  mov     rsi, [rsp+28h+arg_8]
0x1800041b3  add     rsp, 20h
0x1800041b7  pop     rdi
0x1800041b8  jmp     __DllMainCRTStartup
```
