# _DllMainCRTStartup

- ea: `0x180001940`
- end: `0x18000197d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001940`
- `0x180001984`
- `0x180002034`

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
0x180001940  mov     [rsp+arg_0], rbx
0x180001945  mov     [rsp+arg_8], rsi
0x18000194a  push    rdi
0x18000194b  sub     rsp, 20h
0x18000194f  mov     rdi, r8
0x180001952  mov     ebx, edx
0x180001954  mov     rsi, rcx
0x180001957  cmp     edx, 1
0x18000195a  jnz     short loc_180001961
0x18000195c  call    __security_init_cookie
0x180001961  mov     r8, rdi
0x180001964  mov     edx, ebx; fdwReason
0x180001966  mov     rcx, rsi; hinstDLL
0x180001969  mov     rbx, [rsp+28h+arg_0]
0x18000196e  mov     rsi, [rsp+28h+arg_8]
0x180001973  add     rsp, 20h
0x180001977  pop     rdi
0x180001978  jmp     __DllMainCRTStartup
```
