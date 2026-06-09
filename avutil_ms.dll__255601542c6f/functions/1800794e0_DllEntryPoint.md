# DllEntryPoint

- ea: `0x1800794e0`
- end: `0x18007951d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800793ac`
- `0x1800794e0`
- `0x180079520`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_180079520();
  return sub_1800793AC(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x1800794e0  mov     [rsp+arg_0], rbx
0x1800794e5  mov     [rsp+arg_8], rsi
0x1800794ea  push    rdi
0x1800794eb  sub     rsp, 20h
0x1800794ef  mov     rdi, r8
0x1800794f2  mov     ebx, edx
0x1800794f4  mov     rsi, rcx
0x1800794f7  cmp     edx, 1
0x1800794fa  jnz     short loc_180079501
0x1800794fc  call    sub_180079520
0x180079501  mov     r8, rdi
0x180079504  mov     edx, ebx
0x180079506  mov     rcx, rsi
0x180079509  mov     rbx, [rsp+28h+arg_0]
0x18007950e  mov     rsi, [rsp+28h+arg_8]
0x180079513  add     rsp, 20h
0x180079517  pop     rdi
0x180079518  jmp     sub_1800793AC
```
