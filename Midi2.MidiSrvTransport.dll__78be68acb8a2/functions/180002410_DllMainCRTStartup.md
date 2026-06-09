# _DllMainCRTStartup

- ea: `0x180002410`
- end: `0x18000244d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800022d4`
- `0x180002410`
- `0x180002910`

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
0x180002410  mov     [rsp+arg_0], rbx
0x180002415  mov     [rsp+arg_8], rsi
0x18000241a  push    rdi
0x18000241b  sub     rsp, 20h
0x18000241f  mov     rdi, r8
0x180002422  mov     ebx, edx
0x180002424  mov     rsi, rcx
0x180002427  cmp     edx, 1
0x18000242a  jnz     short loc_180002431
0x18000242c  call    __security_init_cookie
0x180002431  mov     r8, rdi; lpvReserved
0x180002434  mov     edx, ebx; fdwReason
0x180002436  mov     rcx, rsi; hinstDLL
0x180002439  mov     rbx, [rsp+28h+arg_0]
0x18000243e  mov     rsi, [rsp+28h+arg_8]
0x180002443  add     rsp, 20h
0x180002447  pop     rdi
0x180002448  jmp     dllmain_dispatch
```
