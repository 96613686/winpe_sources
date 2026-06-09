# _DllMainCRTStartup

- ea: `0x180012d80`
- end: `0x180012dbd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180012c44`
- `0x180012d80`
- `0x18001336c`

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
0x180012d80  mov     [rsp+arg_0], rbx
0x180012d85  mov     [rsp+arg_8], rsi
0x180012d8a  push    rdi
0x180012d8b  sub     rsp, 20h
0x180012d8f  mov     rdi, r8
0x180012d92  mov     ebx, edx
0x180012d94  mov     rsi, rcx
0x180012d97  cmp     edx, 1
0x180012d9a  jnz     short loc_180012DA1
0x180012d9c  call    __security_init_cookie
0x180012da1  mov     r8, rdi; lpvReserved
0x180012da4  mov     edx, ebx; fdwReason
0x180012da6  mov     rcx, rsi; hinstDLL
0x180012da9  mov     rbx, [rsp+28h+arg_0]
0x180012dae  mov     rsi, [rsp+28h+arg_8]
0x180012db3  add     rsp, 20h
0x180012db7  pop     rdi
0x180012db8  jmp     dllmain_dispatch
```
