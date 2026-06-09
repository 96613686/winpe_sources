# _DllMainCRTStartup

- ea: `0x180002460`
- end: `0x18000249d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002460`
- `0x1800024a4`
- `0x180002c94`

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
0x180002460  mov     [rsp+arg_0], rbx
0x180002465  mov     [rsp+arg_8], rsi
0x18000246a  push    rdi
0x18000246b  sub     rsp, 20h
0x18000246f  mov     rdi, r8
0x180002472  mov     ebx, edx
0x180002474  mov     rsi, rcx
0x180002477  cmp     edx, 1
0x18000247a  jnz     short loc_180002481
0x18000247c  call    __security_init_cookie
0x180002481  mov     r8, rdi
0x180002484  mov     edx, ebx; fdwReason
0x180002486  mov     rcx, rsi; hinstDLL
0x180002489  mov     rbx, [rsp+28h+arg_0]
0x18000248e  mov     rsi, [rsp+28h+arg_8]
0x180002493  add     rsp, 20h
0x180002497  pop     rdi
0x180002498  jmp     __DllMainCRTStartup
```
