# _DllMainCRTStartup

- ea: `0x180009f60`
- end: `0x180009f9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009e24`
- `0x180009f60`
- `0x18000a000`

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
0x180009f60  mov     [rsp+arg_0], rbx
0x180009f65  mov     [rsp+arg_8], rsi
0x180009f6a  push    rdi
0x180009f6b  sub     rsp, 20h
0x180009f6f  mov     rdi, r8
0x180009f72  mov     ebx, edx
0x180009f74  mov     rsi, rcx
0x180009f77  cmp     edx, 1
0x180009f7a  jnz     short loc_180009F81
0x180009f7c  call    __security_init_cookie
0x180009f81  mov     r8, rdi; lpvReserved
0x180009f84  mov     edx, ebx; fdwReason
0x180009f86  mov     rcx, rsi; hinstDLL
0x180009f89  mov     rbx, [rsp+28h+arg_0]
0x180009f8e  mov     rsi, [rsp+28h+arg_8]
0x180009f93  add     rsp, 20h
0x180009f97  pop     rdi
0x180009f98  jmp     dllmain_dispatch
```
