# _DllMainCRTStartup

- ea: `0x180002bb0`
- end: `0x180002bed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002a74`
- `0x180002bb0`
- `0x1800033a8`

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
0x180002bb0  mov     [rsp+arg_0], rbx
0x180002bb5  mov     [rsp+arg_8], rsi
0x180002bba  push    rdi
0x180002bbb  sub     rsp, 20h
0x180002bbf  mov     rdi, r8
0x180002bc2  mov     ebx, edx
0x180002bc4  mov     rsi, rcx
0x180002bc7  cmp     edx, 1
0x180002bca  jnz     short loc_180002BD1
0x180002bcc  call    __security_init_cookie
0x180002bd1  mov     r8, rdi; lpvReserved
0x180002bd4  mov     edx, ebx; fdwReason
0x180002bd6  mov     rcx, rsi; hinstDLL
0x180002bd9  mov     rbx, [rsp+28h+arg_0]
0x180002bde  mov     rsi, [rsp+28h+arg_8]
0x180002be3  add     rsp, 20h
0x180002be7  pop     rdi
0x180002be8  jmp     dllmain_dispatch
```
