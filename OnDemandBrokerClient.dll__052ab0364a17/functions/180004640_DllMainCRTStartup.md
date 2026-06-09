# _DllMainCRTStartup

- ea: `0x180004640`
- end: `0x18000467d`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004640`
- `0x180004684`
- `0x1800049c4`

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
0x180004640  mov     [rsp+arg_0], rbx
0x180004645  mov     [rsp+arg_8], rsi
0x18000464a  push    rdi
0x18000464b  sub     rsp, 20h
0x18000464f  mov     rdi, r8
0x180004652  mov     ebx, edx
0x180004654  mov     rsi, rcx
0x180004657  cmp     edx, 1
0x18000465a  jnz     short loc_180004661
0x18000465c  call    __security_init_cookie
0x180004661  mov     r8, rdi
0x180004664  mov     edx, ebx; fdwReason
0x180004666  mov     rcx, rsi; hinstDLL
0x180004669  mov     rbx, [rsp+28h+arg_0]
0x18000466e  mov     rsi, [rsp+28h+arg_8]
0x180004673  add     rsp, 20h
0x180004677  pop     rdi
0x180004678  jmp     __DllMainCRTStartup
```
