# _DllMainCRTStartup

- ea: `0x180006e50`
- end: `0x180006e8d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180006e50`
- `0x180006e94`
- `0x180007774`

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
0x180006e50  mov     [rsp+arg_0], rbx
0x180006e55  mov     [rsp+arg_8], rsi
0x180006e5a  push    rdi
0x180006e5b  sub     rsp, 20h
0x180006e5f  mov     rdi, r8
0x180006e62  mov     ebx, edx
0x180006e64  mov     rsi, rcx
0x180006e67  cmp     edx, 1
0x180006e6a  jnz     short loc_180006E71
0x180006e6c  call    __security_init_cookie
0x180006e71  mov     r8, rdi
0x180006e74  mov     edx, ebx; fdwReason
0x180006e76  mov     rcx, rsi; hinstDLL
0x180006e79  mov     rbx, [rsp+28h+arg_0]
0x180006e7e  mov     rsi, [rsp+28h+arg_8]
0x180006e83  add     rsp, 20h
0x180006e87  pop     rdi
0x180006e88  jmp     __DllMainCRTStartup
```
