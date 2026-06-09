# _DllMainCRTStartup

- ea: `0x180013a90`
- end: `0x180013acd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180013a90`
- `0x180013ad4`
- `0x180013ef0`

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
0x180013a90  mov     [rsp+arg_0], rbx
0x180013a95  mov     [rsp+arg_8], rsi
0x180013a9a  push    rdi
0x180013a9b  sub     rsp, 20h
0x180013a9f  mov     rdi, r8
0x180013aa2  mov     ebx, edx
0x180013aa4  mov     rsi, rcx
0x180013aa7  cmp     edx, 1
0x180013aaa  jnz     short loc_180013AB1
0x180013aac  call    __security_init_cookie
0x180013ab1  mov     r8, rdi
0x180013ab4  mov     edx, ebx; fdwReason
0x180013ab6  mov     rcx, rsi; hinstDLL
0x180013ab9  mov     rbx, [rsp+28h+arg_0]
0x180013abe  mov     rsi, [rsp+28h+arg_8]
0x180013ac3  add     rsp, 20h
0x180013ac7  pop     rdi
0x180013ac8  jmp     __DllMainCRTStartup
```
