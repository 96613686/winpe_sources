# _DllMainCRTStartup

- ea: `0x180001c60`
- end: `0x180001c9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001c60`
- `0x180001ca4`
- `0x180002484`

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
0x180001c60  mov     [rsp+arg_0], rbx
0x180001c65  mov     [rsp+arg_8], rsi
0x180001c6a  push    rdi
0x180001c6b  sub     rsp, 20h
0x180001c6f  mov     rdi, r8
0x180001c72  mov     ebx, edx
0x180001c74  mov     rsi, rcx
0x180001c77  cmp     edx, 1
0x180001c7a  jnz     short loc_180001C81
0x180001c7c  call    __security_init_cookie
0x180001c81  mov     r8, rdi
0x180001c84  mov     edx, ebx; fdwReason
0x180001c86  mov     rcx, rsi; hinstDLL
0x180001c89  mov     rbx, [rsp+28h+arg_0]
0x180001c8e  mov     rsi, [rsp+28h+arg_8]
0x180001c93  add     rsp, 20h
0x180001c97  pop     rdi
0x180001c98  jmp     __DllMainCRTStartup
```
