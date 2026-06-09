# _DllMainCRTStartup

- ea: `0x180001f30`
- end: `0x180001f6d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001f30`
- `0x180001f74`
- `0x180002434`

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
0x180001f30  mov     [rsp+arg_0], rbx
0x180001f35  mov     [rsp+arg_8], rsi
0x180001f3a  push    rdi
0x180001f3b  sub     rsp, 20h
0x180001f3f  mov     rdi, r8
0x180001f42  mov     ebx, edx
0x180001f44  mov     rsi, rcx
0x180001f47  cmp     edx, 1
0x180001f4a  jnz     short loc_180001F51
0x180001f4c  call    __security_init_cookie
0x180001f51  mov     r8, rdi
0x180001f54  mov     edx, ebx; fdwReason
0x180001f56  mov     rcx, rsi; hinstDLL
0x180001f59  mov     rbx, [rsp+28h+arg_0]
0x180001f5e  mov     rsi, [rsp+28h+arg_8]
0x180001f63  add     rsp, 20h
0x180001f67  pop     rdi
0x180001f68  jmp     __DllMainCRTStartup
```
