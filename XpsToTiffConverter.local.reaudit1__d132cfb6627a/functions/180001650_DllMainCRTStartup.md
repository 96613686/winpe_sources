# _DllMainCRTStartup

- ea: `0x180001650`
- end: `0x18000168d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001514`
- `0x180001650`
- `0x180001b14`

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
0x180001650  mov     [rsp+arg_0], rbx
0x180001655  mov     [rsp+arg_8], rsi
0x18000165a  push    rdi
0x18000165b  sub     rsp, 20h
0x18000165f  mov     rdi, r8
0x180001662  mov     ebx, edx
0x180001664  mov     rsi, rcx
0x180001667  cmp     edx, 1
0x18000166a  jnz     short loc_180001671
0x18000166c  call    __security_init_cookie
0x180001671  mov     r8, rdi; lpvReserved
0x180001674  mov     edx, ebx; fdwReason
0x180001676  mov     rcx, rsi; hinstDLL
0x180001679  mov     rbx, [rsp+28h+arg_0]
0x18000167e  mov     rsi, [rsp+28h+arg_8]
0x180001683  add     rsp, 20h
0x180001687  pop     rdi
0x180001688  jmp     dllmain_dispatch
```
