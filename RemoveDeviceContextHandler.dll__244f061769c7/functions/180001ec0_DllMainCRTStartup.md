# _DllMainCRTStartup

- ea: `0x180001ec0`
- end: `0x180001efd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001ec0`
- `0x180001f04`
- `0x180002774`

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
0x180001ec0  mov     [rsp+arg_0], rbx
0x180001ec5  mov     [rsp+arg_8], rsi
0x180001eca  push    rdi
0x180001ecb  sub     rsp, 20h
0x180001ecf  mov     rdi, r8
0x180001ed2  mov     ebx, edx
0x180001ed4  mov     rsi, rcx
0x180001ed7  cmp     edx, 1
0x180001eda  jnz     short loc_180001EE1
0x180001edc  call    __security_init_cookie
0x180001ee1  mov     r8, rdi
0x180001ee4  mov     edx, ebx; fdwReason
0x180001ee6  mov     rcx, rsi; hinstDLL
0x180001ee9  mov     rbx, [rsp+28h+arg_0]
0x180001eee  mov     rsi, [rsp+28h+arg_8]
0x180001ef3  add     rsp, 20h
0x180001ef7  pop     rdi
0x180001ef8  jmp     __DllMainCRTStartup
```
