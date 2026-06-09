# _DllMainCRTStartup

- ea: `0x180002690`
- end: `0x1800026cd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002554`
- `0x180002690`
- `0x180002ce8`

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
0x180002690  mov     [rsp+arg_0], rbx
0x180002695  mov     [rsp+arg_8], rsi
0x18000269a  push    rdi
0x18000269b  sub     rsp, 20h
0x18000269f  mov     rdi, r8
0x1800026a2  mov     ebx, edx
0x1800026a4  mov     rsi, rcx
0x1800026a7  cmp     edx, 1
0x1800026aa  jnz     short loc_1800026B1
0x1800026ac  call    __security_init_cookie
0x1800026b1  mov     r8, rdi; lpvReserved
0x1800026b4  mov     edx, ebx; fdwReason
0x1800026b6  mov     rcx, rsi; hinstDLL
0x1800026b9  mov     rbx, [rsp+28h+arg_0]
0x1800026be  mov     rsi, [rsp+28h+arg_8]
0x1800026c3  add     rsp, 20h
0x1800026c7  pop     rdi
0x1800026c8  jmp     dllmain_dispatch
```
