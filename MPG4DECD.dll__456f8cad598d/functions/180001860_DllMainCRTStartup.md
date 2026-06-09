# _DllMainCRTStartup

- ea: `0x180001860`
- end: `0x18000189d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001724`
- `0x180001860`
- `0x1800018d4`

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
0x180001860  mov     [rsp+arg_0], rbx
0x180001865  mov     [rsp+arg_8], rsi
0x18000186a  push    rdi
0x18000186b  sub     rsp, 20h
0x18000186f  mov     rdi, r8
0x180001872  mov     ebx, edx
0x180001874  mov     rsi, rcx
0x180001877  cmp     edx, 1
0x18000187a  jnz     short loc_180001881
0x18000187c  call    __security_init_cookie
0x180001881  mov     r8, rdi; lpvReserved
0x180001884  mov     edx, ebx; fdwReason
0x180001886  mov     rcx, rsi; hinstDLL
0x180001889  mov     rbx, [rsp+28h+arg_0]
0x18000188e  mov     rsi, [rsp+28h+arg_8]
0x180001893  add     rsp, 20h
0x180001897  pop     rdi
0x180001898  jmp     dllmain_dispatch
```
