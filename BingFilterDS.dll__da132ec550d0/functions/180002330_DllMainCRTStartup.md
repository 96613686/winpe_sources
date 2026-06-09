# _DllMainCRTStartup

- ea: `0x180002330`
- end: `0x18000236d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002330`
- `0x180002374`
- `0x180002874`

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
0x180002330  mov     [rsp+arg_0], rbx
0x180002335  mov     [rsp+arg_8], rsi
0x18000233a  push    rdi
0x18000233b  sub     rsp, 20h
0x18000233f  mov     rdi, r8
0x180002342  mov     ebx, edx
0x180002344  mov     rsi, rcx
0x180002347  cmp     edx, 1
0x18000234a  jnz     short loc_180002351
0x18000234c  call    __security_init_cookie
0x180002351  mov     r8, rdi
0x180002354  mov     edx, ebx; fdwReason
0x180002356  mov     rcx, rsi; hinstDLL
0x180002359  mov     rbx, [rsp+28h+arg_0]
0x18000235e  mov     rsi, [rsp+28h+arg_8]
0x180002363  add     rsp, 20h
0x180002367  pop     rdi
0x180002368  jmp     __DllMainCRTStartup
```
