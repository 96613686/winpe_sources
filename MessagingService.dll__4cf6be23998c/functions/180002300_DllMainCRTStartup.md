# _DllMainCRTStartup

- ea: `0x180002300`
- end: `0x18000233d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002300`
- `0x180002344`
- `0x180002844`

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
0x180002300  mov     [rsp+arg_0], rbx
0x180002305  mov     [rsp+arg_8], rsi
0x18000230a  push    rdi
0x18000230b  sub     rsp, 20h
0x18000230f  mov     rdi, r8
0x180002312  mov     ebx, edx
0x180002314  mov     rsi, rcx
0x180002317  cmp     edx, 1
0x18000231a  jnz     short loc_180002321
0x18000231c  call    __security_init_cookie
0x180002321  mov     r8, rdi
0x180002324  mov     edx, ebx; fdwReason
0x180002326  mov     rcx, rsi; hinstDLL
0x180002329  mov     rbx, [rsp+28h+arg_0]
0x18000232e  mov     rsi, [rsp+28h+arg_8]
0x180002333  add     rsp, 20h
0x180002337  pop     rdi
0x180002338  jmp     __DllMainCRTStartup
```
