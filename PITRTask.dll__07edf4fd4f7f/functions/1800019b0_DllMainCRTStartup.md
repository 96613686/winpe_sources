# _DllMainCRTStartup

- ea: `0x1800019b0`
- end: `0x1800019ed`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800019b0`
- `0x1800019f4`
- `0x180001ef4`

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
0x1800019b0  mov     [rsp+arg_0], rbx
0x1800019b5  mov     [rsp+arg_8], rsi
0x1800019ba  push    rdi
0x1800019bb  sub     rsp, 20h
0x1800019bf  mov     rdi, r8
0x1800019c2  mov     ebx, edx
0x1800019c4  mov     rsi, rcx
0x1800019c7  cmp     edx, 1
0x1800019ca  jnz     short loc_1800019D1
0x1800019cc  call    __security_init_cookie
0x1800019d1  mov     r8, rdi
0x1800019d4  mov     edx, ebx; fdwReason
0x1800019d6  mov     rcx, rsi; hinstDLL
0x1800019d9  mov     rbx, [rsp+28h+arg_0]
0x1800019de  mov     rsi, [rsp+28h+arg_8]
0x1800019e3  add     rsp, 20h
0x1800019e7  pop     rdi
0x1800019e8  jmp     __DllMainCRTStartup
```
