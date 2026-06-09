# _DllMainCRTStartup

- ea: `0x180003c30`
- end: `0x180003c6d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003af4`
- `0x180003c30`
- `0x180003ca4`

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
0x180003c30  mov     [rsp+arg_0], rbx
0x180003c35  mov     [rsp+arg_8], rsi
0x180003c3a  push    rdi
0x180003c3b  sub     rsp, 20h
0x180003c3f  mov     rdi, r8
0x180003c42  mov     ebx, edx
0x180003c44  mov     rsi, rcx
0x180003c47  cmp     edx, 1
0x180003c4a  jnz     short loc_180003C51
0x180003c4c  call    __security_init_cookie
0x180003c51  mov     r8, rdi; lpvReserved
0x180003c54  mov     edx, ebx; fdwReason
0x180003c56  mov     rcx, rsi; hinstDLL
0x180003c59  mov     rbx, [rsp+28h+arg_0]
0x180003c5e  mov     rsi, [rsp+28h+arg_8]
0x180003c63  add     rsp, 20h
0x180003c67  pop     rdi
0x180003c68  jmp     dllmain_dispatch
```
