# _DllMainCRTStartup

- ea: `0x1800024f0`
- end: `0x18000252d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800023b4`
- `0x1800024f0`
- `0x1800029c0`

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
0x1800024f0  mov     [rsp+arg_0], rbx
0x1800024f5  mov     [rsp+arg_8], rsi
0x1800024fa  push    rdi
0x1800024fb  sub     rsp, 20h
0x1800024ff  mov     rdi, r8
0x180002502  mov     ebx, edx
0x180002504  mov     rsi, rcx
0x180002507  cmp     edx, 1
0x18000250a  jnz     short loc_180002511
0x18000250c  call    __security_init_cookie
0x180002511  mov     r8, rdi; lpvReserved
0x180002514  mov     edx, ebx; fdwReason
0x180002516  mov     rcx, rsi; hinstDLL
0x180002519  mov     rbx, [rsp+28h+arg_0]
0x18000251e  mov     rsi, [rsp+28h+arg_8]
0x180002523  add     rsp, 20h
0x180002527  pop     rdi
0x180002528  jmp     dllmain_dispatch
```
