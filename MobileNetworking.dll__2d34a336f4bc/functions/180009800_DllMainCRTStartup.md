# _DllMainCRTStartup

- ea: `0x180009800`
- end: `0x18000983d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800096c4`
- `0x180009800`
- `0x180009874`

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
0x180009800  mov     [rsp+arg_0], rbx
0x180009805  mov     [rsp+arg_8], rsi
0x18000980a  push    rdi
0x18000980b  sub     rsp, 20h
0x18000980f  mov     rdi, r8
0x180009812  mov     ebx, edx
0x180009814  mov     rsi, rcx
0x180009817  cmp     edx, 1
0x18000981a  jnz     short loc_180009821
0x18000981c  call    __security_init_cookie
0x180009821  mov     r8, rdi; lpvReserved
0x180009824  mov     edx, ebx; fdwReason
0x180009826  mov     rcx, rsi; hinstDLL
0x180009829  mov     rbx, [rsp+28h+arg_0]
0x18000982e  mov     rsi, [rsp+28h+arg_8]
0x180009833  add     rsp, 20h
0x180009837  pop     rdi
0x180009838  jmp     dllmain_dispatch
```
