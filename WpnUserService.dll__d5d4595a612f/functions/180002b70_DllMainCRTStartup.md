# _DllMainCRTStartup

- ea: `0x180002b70`
- end: `0x180002bad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002a34`
- `0x180002b70`
- `0x180002fcc`

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
0x180002b70  mov     [rsp+arg_0], rbx
0x180002b75  mov     [rsp+arg_8], rsi
0x180002b7a  push    rdi
0x180002b7b  sub     rsp, 20h
0x180002b7f  mov     rdi, r8
0x180002b82  mov     ebx, edx
0x180002b84  mov     rsi, rcx
0x180002b87  cmp     edx, 1
0x180002b8a  jnz     short loc_180002B91
0x180002b8c  call    __security_init_cookie
0x180002b91  mov     r8, rdi; lpvReserved
0x180002b94  mov     edx, ebx; fdwReason
0x180002b96  mov     rcx, rsi; hinstDLL
0x180002b99  mov     rbx, [rsp+28h+arg_0]
0x180002b9e  mov     rsi, [rsp+28h+arg_8]
0x180002ba3  add     rsp, 20h
0x180002ba7  pop     rdi
0x180002ba8  jmp     dllmain_dispatch
```
