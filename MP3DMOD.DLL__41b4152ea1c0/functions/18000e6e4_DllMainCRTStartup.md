# _DllMainCRTStartup

- ea: `0x18000e6e4`
- end: `0x18000e721`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bd80`

## callees

- `0x18000e5b4`
- `0x18000e6e4`
- `0x18000e740`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return dllmain_dispatch(hinstDLL, fdwReason, lpvReserved);
}

```

## disassembly

```asm
0x18000e6e4  mov     [rsp+arg_0], rbx
0x18000e6e9  mov     [rsp+arg_8], rsi
0x18000e6ee  push    rdi
0x18000e6ef  sub     rsp, 20h
0x18000e6f3  mov     rdi, r8
0x18000e6f6  mov     ebx, edx
0x18000e6f8  mov     rsi, rcx
0x18000e6fb  cmp     edx, 1
0x18000e6fe  jnz     short loc_18000E705
0x18000e700  call    __security_init_cookie
0x18000e705  mov     r8, rdi; lpvReserved
0x18000e708  mov     edx, ebx; fdwReason
0x18000e70a  mov     rcx, rsi; hinstDLL
0x18000e70d  mov     rbx, [rsp+28h+arg_0]
0x18000e712  mov     rsi, [rsp+28h+arg_8]
0x18000e717  add     rsp, 20h
0x18000e71b  pop     rdi
0x18000e71c  jmp     dllmain_dispatch
```
