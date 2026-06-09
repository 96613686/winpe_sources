# _DllMainCRTStartup

- ea: `0x18000e950`
- end: `0x18000e98d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e950`
- `0x18000e994`
- `0x18000ee84`

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
0x18000e950  mov     [rsp+arg_0], rbx
0x18000e955  mov     [rsp+arg_8], rsi
0x18000e95a  push    rdi
0x18000e95b  sub     rsp, 20h
0x18000e95f  mov     rdi, r8
0x18000e962  mov     ebx, edx
0x18000e964  mov     rsi, rcx
0x18000e967  cmp     edx, 1
0x18000e96a  jnz     short loc_18000E971
0x18000e96c  call    __security_init_cookie
0x18000e971  mov     r8, rdi
0x18000e974  mov     edx, ebx; fdwReason
0x18000e976  mov     rcx, rsi; hinstDLL
0x18000e979  mov     rbx, [rsp+28h+arg_0]
0x18000e97e  mov     rsi, [rsp+28h+arg_8]
0x18000e983  add     rsp, 20h
0x18000e987  pop     rdi
0x18000e988  jmp     __DllMainCRTStartup
```
