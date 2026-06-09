# _DllMainCRTStartup

- ea: `0x18000e2f0`
- end: `0x18000e32d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e2f0`
- `0x18000e334`
- `0x18000e9e4`

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
0x18000e2f0  mov     [rsp+arg_0], rbx
0x18000e2f5  mov     [rsp+arg_8], rsi
0x18000e2fa  push    rdi
0x18000e2fb  sub     rsp, 20h
0x18000e2ff  mov     rdi, r8
0x18000e302  mov     ebx, edx
0x18000e304  mov     rsi, rcx
0x18000e307  cmp     edx, 1
0x18000e30a  jnz     short loc_18000E311
0x18000e30c  call    __security_init_cookie
0x18000e311  mov     r8, rdi
0x18000e314  mov     edx, ebx; fdwReason
0x18000e316  mov     rcx, rsi; hinstDLL
0x18000e319  mov     rbx, [rsp+28h+arg_0]
0x18000e31e  mov     rsi, [rsp+28h+arg_8]
0x18000e323  add     rsp, 20h
0x18000e327  pop     rdi
0x18000e328  jmp     __DllMainCRTStartup
```
