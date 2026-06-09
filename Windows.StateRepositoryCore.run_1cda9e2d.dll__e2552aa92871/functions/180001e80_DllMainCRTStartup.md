# _DllMainCRTStartup

- ea: `0x180001e80`
- end: `0x180001ebd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001d44`
- `0x180001e80`
- `0x1800022dc`

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
0x180001e80  mov     [rsp+arg_0], rbx
0x180001e85  mov     [rsp+arg_8], rsi
0x180001e8a  push    rdi
0x180001e8b  sub     rsp, 20h
0x180001e8f  mov     rdi, r8
0x180001e92  mov     ebx, edx
0x180001e94  mov     rsi, rcx
0x180001e97  cmp     edx, 1
0x180001e9a  jnz     short loc_180001EA1
0x180001e9c  call    __security_init_cookie
0x180001ea1  mov     r8, rdi; lpvReserved
0x180001ea4  mov     edx, ebx; fdwReason
0x180001ea6  mov     rcx, rsi; hinstDLL
0x180001ea9  mov     rbx, [rsp+28h+arg_0]
0x180001eae  mov     rsi, [rsp+28h+arg_8]
0x180001eb3  add     rsp, 20h
0x180001eb7  pop     rdi
0x180001eb8  jmp     dllmain_dispatch
```
