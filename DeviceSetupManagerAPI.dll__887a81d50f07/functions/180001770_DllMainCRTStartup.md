# _DllMainCRTStartup

- ea: `0x180001770`
- end: `0x1800017ad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001634`
- `0x180001770`
- `0x180001fb4`

## pseudocode

```c
BOOL __stdcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180001770  mov     [rsp+arg_0], rbx
0x180001775  mov     [rsp+arg_8], rsi
0x18000177a  push    rdi
0x18000177b  sub     rsp, 20h
0x18000177f  mov     rdi, r8
0x180001782  mov     ebx, edx
0x180001784  mov     rsi, rcx
0x180001787  cmp     edx, 1
0x18000178a  jnz     short loc_180001791
0x18000178c  call    __security_init_cookie
0x180001791  mov     r8, rdi; lpvReserved
0x180001794  mov     edx, ebx; fdwReason
0x180001796  mov     rcx, rsi; hinstDLL
0x180001799  mov     rbx, [rsp+28h+arg_0]
0x18000179e  mov     rsi, [rsp+28h+arg_8]
0x1800017a3  add     rsp, 20h
0x1800017a7  pop     rdi
0x1800017a8  jmp     dllmain_dispatch
```
