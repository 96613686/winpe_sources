# _DllMainCRTStartup

- ea: `0x180002120`
- end: `0x18000215d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001fe4`
- `0x180002120`
- `0x180002608`

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
0x180002120  mov     [rsp+arg_0], rbx
0x180002125  mov     [rsp+arg_8], rsi
0x18000212a  push    rdi
0x18000212b  sub     rsp, 20h
0x18000212f  mov     rdi, r8
0x180002132  mov     ebx, edx
0x180002134  mov     rsi, rcx
0x180002137  cmp     edx, 1
0x18000213a  jnz     short loc_180002141
0x18000213c  call    __security_init_cookie
0x180002141  mov     r8, rdi; lpvReserved
0x180002144  mov     edx, ebx; fdwReason
0x180002146  mov     rcx, rsi; hinstDLL
0x180002149  mov     rbx, [rsp+28h+arg_0]
0x18000214e  mov     rsi, [rsp+28h+arg_8]
0x180002153  add     rsp, 20h
0x180002157  pop     rdi
0x180002158  jmp     dllmain_dispatch
```
