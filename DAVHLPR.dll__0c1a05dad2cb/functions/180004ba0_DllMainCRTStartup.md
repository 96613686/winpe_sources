# _DllMainCRTStartup

- ea: `0x180004ba0`
- end: `0x180004bdd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004ba0`
- `0x180004be4`
- `0x180004ee4`

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
0x180004ba0  mov     [rsp+arg_0], rbx
0x180004ba5  mov     [rsp+arg_8], rsi
0x180004baa  push    rdi
0x180004bab  sub     rsp, 20h
0x180004baf  mov     rdi, r8
0x180004bb2  mov     ebx, edx
0x180004bb4  mov     rsi, rcx
0x180004bb7  cmp     edx, 1
0x180004bba  jnz     short loc_180004BC1
0x180004bbc  call    __security_init_cookie
0x180004bc1  mov     r8, rdi
0x180004bc4  mov     edx, ebx; fdwReason
0x180004bc6  mov     rcx, rsi; hinstDLL
0x180004bc9  mov     rbx, [rsp+28h+arg_0]
0x180004bce  mov     rsi, [rsp+28h+arg_8]
0x180004bd3  add     rsp, 20h
0x180004bd7  pop     rdi
0x180004bd8  jmp     __DllMainCRTStartup
```
