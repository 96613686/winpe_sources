# _DllMainCRTStartup

- ea: `0x180001bb0`
- end: `0x180001bed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180001a74`
- `0x180001bb0`
- `0x180002060`

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
0x180001bb0  mov     [rsp+arg_0], rbx
0x180001bb5  mov     [rsp+arg_8], rsi
0x180001bba  push    rdi
0x180001bbb  sub     rsp, 20h
0x180001bbf  mov     rdi, r8
0x180001bc2  mov     ebx, edx
0x180001bc4  mov     rsi, rcx
0x180001bc7  cmp     edx, 1
0x180001bca  jnz     short loc_180001BD1
0x180001bcc  call    __security_init_cookie
0x180001bd1  mov     r8, rdi; lpvReserved
0x180001bd4  mov     edx, ebx; fdwReason
0x180001bd6  mov     rcx, rsi; hinstDLL
0x180001bd9  mov     rbx, [rsp+28h+arg_0]
0x180001bde  mov     rsi, [rsp+28h+arg_8]
0x180001be3  add     rsp, 20h
0x180001be7  pop     rdi
0x180001be8  jmp     dllmain_dispatch
```
