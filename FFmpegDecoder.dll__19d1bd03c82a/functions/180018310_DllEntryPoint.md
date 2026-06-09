# DllEntryPoint

- ea: `0x180018310`
- end: `0x18001834d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800181dc`
- `0x180018310`
- `0x1800188fc`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_1800188FC();
  return sub_1800181DC(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x180018310  mov     [rsp+arg_0], rbx
0x180018315  mov     [rsp+arg_8], rsi
0x18001831a  push    rdi
0x18001831b  sub     rsp, 20h
0x18001831f  mov     rdi, r8
0x180018322  mov     ebx, edx
0x180018324  mov     rsi, rcx
0x180018327  cmp     edx, 1
0x18001832a  jnz     short loc_180018331
0x18001832c  call    sub_1800188FC
0x180018331  mov     r8, rdi
0x180018334  mov     edx, ebx
0x180018336  mov     rcx, rsi
0x180018339  mov     rbx, [rsp+28h+arg_0]
0x18001833e  mov     rsi, [rsp+28h+arg_8]
0x180018343  add     rsp, 20h
0x180018347  pop     rdi
0x180018348  jmp     sub_1800181DC
```
