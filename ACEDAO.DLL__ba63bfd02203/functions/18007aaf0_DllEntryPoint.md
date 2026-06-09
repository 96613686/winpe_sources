# DllEntryPoint

- ea: `0x18007aaf0`
- end: `0x18007ab2d`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18007a9c4`
- `0x18007aaf0`
- `0x18007b444`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18007B444();
  return sub_18007A9C4((__int64)hinstDLL, fdwReason, (__int64)lpReserved);
}

```

## disassembly

```asm
0x18007aaf0  mov     [rsp+arg_0], rbx
0x18007aaf5  mov     [rsp+arg_8], rsi
0x18007aafa  push    rdi
0x18007aafb  sub     rsp, 20h
0x18007aaff  mov     rdi, r8
0x18007ab02  mov     ebx, edx
0x18007ab04  mov     rsi, rcx
0x18007ab07  cmp     edx, 1
0x18007ab0a  jnz     short loc_18007AB11
0x18007ab0c  call    sub_18007B444
0x18007ab11  mov     r8, rdi
0x18007ab14  mov     edx, ebx
0x18007ab16  mov     rcx, rsi
0x18007ab19  mov     rbx, [rsp+28h+arg_0]
0x18007ab1e  mov     rsi, [rsp+28h+arg_8]
0x18007ab23  add     rsp, 20h
0x18007ab27  pop     rdi
0x18007ab28  jmp     sub_18007A9C4
```
