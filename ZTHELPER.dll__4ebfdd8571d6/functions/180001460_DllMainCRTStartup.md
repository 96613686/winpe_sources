# _DllMainCRTStartup

- ea: `0x180001460`
- end: `0x18000149d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001324`
- `0x180001460`
- `0x1800018d0`

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
0x180001460  mov     [rsp+arg_0], rbx
0x180001465  mov     [rsp+arg_8], rsi
0x18000146a  push    rdi
0x18000146b  sub     rsp, 20h
0x18000146f  mov     rdi, r8
0x180001472  mov     ebx, edx
0x180001474  mov     rsi, rcx
0x180001477  cmp     edx, 1
0x18000147a  jnz     short loc_180001481
0x18000147c  call    __security_init_cookie
0x180001481  mov     r8, rdi; lpvReserved
0x180001484  mov     edx, ebx; fdwReason
0x180001486  mov     rcx, rsi; hinstDLL
0x180001489  mov     rbx, [rsp+28h+arg_0]
0x18000148e  mov     rsi, [rsp+28h+arg_8]
0x180001493  add     rsp, 20h
0x180001497  pop     rdi
0x180001498  jmp     dllmain_dispatch
```
