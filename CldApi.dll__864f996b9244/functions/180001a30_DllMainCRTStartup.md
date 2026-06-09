# _DllMainCRTStartup

- ea: `0x180001a30`
- end: `0x180001a6d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800018f4`
- `0x180001a30`
- `0x180001aa4`

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
0x180001a30  mov     [rsp+arg_0], rbx
0x180001a35  mov     [rsp+arg_8], rsi
0x180001a3a  push    rdi
0x180001a3b  sub     rsp, 20h
0x180001a3f  mov     rdi, r8
0x180001a42  mov     ebx, edx
0x180001a44  mov     rsi, rcx
0x180001a47  cmp     edx, 1
0x180001a4a  jnz     short loc_180001A51
0x180001a4c  call    __security_init_cookie
0x180001a51  mov     r8, rdi; lpvReserved
0x180001a54  mov     edx, ebx; fdwReason
0x180001a56  mov     rcx, rsi; hinstDLL
0x180001a59  mov     rbx, [rsp+28h+arg_0]
0x180001a5e  mov     rsi, [rsp+28h+arg_8]
0x180001a63  add     rsp, 20h
0x180001a67  pop     rdi
0x180001a68  jmp     dllmain_dispatch
```
