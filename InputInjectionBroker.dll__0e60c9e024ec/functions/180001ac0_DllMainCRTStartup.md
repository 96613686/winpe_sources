# _DllMainCRTStartup

- ea: `0x180001ac0`
- end: `0x180001afd`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001ac0`
- `0x180001b04`
- `0x180001ff4`

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
0x180001ac0  mov     [rsp+arg_0], rbx
0x180001ac5  mov     [rsp+arg_8], rsi
0x180001aca  push    rdi
0x180001acb  sub     rsp, 20h
0x180001acf  mov     rdi, r8
0x180001ad2  mov     ebx, edx
0x180001ad4  mov     rsi, rcx
0x180001ad7  cmp     edx, 1
0x180001ada  jnz     short loc_180001AE1
0x180001adc  call    __security_init_cookie
0x180001ae1  mov     r8, rdi
0x180001ae4  mov     edx, ebx; fdwReason
0x180001ae6  mov     rcx, rsi; hinstDLL
0x180001ae9  mov     rbx, [rsp+28h+arg_0]
0x180001aee  mov     rsi, [rsp+28h+arg_8]
0x180001af3  add     rsp, 20h
0x180001af7  pop     rdi
0x180001af8  jmp     __DllMainCRTStartup
```
