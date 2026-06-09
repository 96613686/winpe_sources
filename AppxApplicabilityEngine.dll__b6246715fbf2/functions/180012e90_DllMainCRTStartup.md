# _DllMainCRTStartup

- ea: `0x180012e90`
- end: `0x180012ecd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180012e90`
- `0x180012ed4`
- `0x1800133d4`

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
0x180012e90  mov     [rsp+arg_0], rbx
0x180012e95  mov     [rsp+arg_8], rsi
0x180012e9a  push    rdi
0x180012e9b  sub     rsp, 20h
0x180012e9f  mov     rdi, r8
0x180012ea2  mov     ebx, edx
0x180012ea4  mov     rsi, rcx
0x180012ea7  cmp     edx, 1
0x180012eaa  jnz     short loc_180012EB1
0x180012eac  call    __security_init_cookie
0x180012eb1  mov     r8, rdi
0x180012eb4  mov     edx, ebx; fdwReason
0x180012eb6  mov     rcx, rsi; hinstDLL
0x180012eb9  mov     rbx, [rsp+28h+arg_0]
0x180012ebe  mov     rsi, [rsp+28h+arg_8]
0x180012ec3  add     rsp, 20h
0x180012ec7  pop     rdi
0x180012ec8  jmp     __DllMainCRTStartup
```
