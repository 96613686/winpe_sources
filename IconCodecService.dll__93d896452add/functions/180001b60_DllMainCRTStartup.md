# _DllMainCRTStartup

- ea: `0x180001b60`
- end: `0x180001b9d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001b60`
- `0x180001ba4`
- `0x180001eb4`

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
0x180001b60  mov     [rsp+arg_0], rbx
0x180001b65  mov     [rsp+arg_8], rsi
0x180001b6a  push    rdi
0x180001b6b  sub     rsp, 20h
0x180001b6f  mov     rdi, r8
0x180001b72  mov     ebx, edx
0x180001b74  mov     rsi, rcx
0x180001b77  cmp     edx, 1
0x180001b7a  jnz     short loc_180001B81
0x180001b7c  call    __security_init_cookie
0x180001b81  mov     r8, rdi
0x180001b84  mov     edx, ebx; fdwReason
0x180001b86  mov     rcx, rsi; hinstDLL
0x180001b89  mov     rbx, [rsp+28h+arg_0]
0x180001b8e  mov     rsi, [rsp+28h+arg_8]
0x180001b93  add     rsp, 20h
0x180001b97  pop     rdi
0x180001b98  jmp     __DllMainCRTStartup
```
