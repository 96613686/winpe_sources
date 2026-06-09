# _DllMainCRTStartup

- ea: `0x1800079c0`
- end: `0x1800079fd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000788c`
- `0x1800079c0`
- `0x18000803c`

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
0x1800079c0  mov     [rsp+arg_0], rbx
0x1800079c5  mov     [rsp+arg_8], rsi
0x1800079ca  push    rdi
0x1800079cb  sub     rsp, 20h
0x1800079cf  mov     rdi, r8
0x1800079d2  mov     ebx, edx
0x1800079d4  mov     rsi, rcx
0x1800079d7  cmp     edx, 1
0x1800079da  jnz     short loc_1800079E1
0x1800079dc  call    __security_init_cookie
0x1800079e1  mov     r8, rdi
0x1800079e4  mov     edx, ebx
0x1800079e6  mov     rcx, rsi
0x1800079e9  mov     rbx, [rsp+28h+arg_0]
0x1800079ee  mov     rsi, [rsp+28h+arg_8]
0x1800079f3  add     rsp, 20h
0x1800079f7  pop     rdi
0x1800079f8  jmp     dllmain_dispatch
```
