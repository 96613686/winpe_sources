# _DllMainCRTStartup

- ea: `0x18000eb20`
- end: `0x18000eb5d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000e9e4`
- `0x18000eb20`
- `0x18000ef70`

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
0x18000eb20  mov     [rsp+arg_0], rbx
0x18000eb25  mov     [rsp+arg_8], rsi
0x18000eb2a  push    rdi
0x18000eb2b  sub     rsp, 20h
0x18000eb2f  mov     rdi, r8
0x18000eb32  mov     ebx, edx
0x18000eb34  mov     rsi, rcx
0x18000eb37  cmp     edx, 1
0x18000eb3a  jnz     short loc_18000EB41
0x18000eb3c  call    __security_init_cookie
0x18000eb41  mov     r8, rdi; lpvReserved
0x18000eb44  mov     edx, ebx; fdwReason
0x18000eb46  mov     rcx, rsi; hinstDLL
0x18000eb49  mov     rbx, [rsp+28h+arg_0]
0x18000eb4e  mov     rsi, [rsp+28h+arg_8]
0x18000eb53  add     rsp, 20h
0x18000eb57  pop     rdi
0x18000eb58  jmp     dllmain_dispatch
```
