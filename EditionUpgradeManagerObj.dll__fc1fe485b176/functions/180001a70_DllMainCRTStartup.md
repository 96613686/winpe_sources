# _DllMainCRTStartup

- ea: `0x180001a70`
- end: `0x180001aad`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001934`
- `0x180001a70`
- `0x180001f1c`

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
0x180001a70  mov     [rsp+arg_0], rbx
0x180001a75  mov     [rsp+arg_8], rsi
0x180001a7a  push    rdi
0x180001a7b  sub     rsp, 20h
0x180001a7f  mov     rdi, r8
0x180001a82  mov     ebx, edx
0x180001a84  mov     rsi, rcx
0x180001a87  cmp     edx, 1
0x180001a8a  jnz     short loc_180001A91
0x180001a8c  call    __security_init_cookie
0x180001a91  mov     r8, rdi; lpvReserved
0x180001a94  mov     edx, ebx; fdwReason
0x180001a96  mov     rcx, rsi; hinstDLL
0x180001a99  mov     rbx, [rsp+28h+arg_0]
0x180001a9e  mov     rsi, [rsp+28h+arg_8]
0x180001aa3  add     rsp, 20h
0x180001aa7  pop     rdi
0x180001aa8  jmp     dllmain_dispatch
```
