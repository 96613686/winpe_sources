# _DllMainCRTStartup

- ea: `0x180002c40`
- end: `0x180002c7d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002c40`
- `0x180002c84`
- `0x180002fb4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180002c40  mov     [rsp+arg_0], rbx
0x180002c45  mov     [rsp+arg_8], rsi
0x180002c4a  push    rdi
0x180002c4b  sub     rsp, 20h
0x180002c4f  mov     rdi, r8
0x180002c52  mov     ebx, edx
0x180002c54  mov     rsi, rcx
0x180002c57  cmp     edx, 1
0x180002c5a  jnz     short loc_180002C61
0x180002c5c  call    __security_init_cookie
0x180002c61  mov     r8, rdi
0x180002c64  mov     edx, ebx; fdwReason
0x180002c66  mov     rcx, rsi; hinstDLL
0x180002c69  mov     rbx, [rsp+28h+arg_0]
0x180002c6e  mov     rsi, [rsp+28h+arg_8]
0x180002c73  add     rsp, 20h
0x180002c77  pop     rdi
0x180002c78  jmp     __DllMainCRTStartup
```
