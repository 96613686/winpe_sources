# DllEntryPoint

- ea: `0x18017e990`
- end: `0x18017e9cd`
- name: `DllEntryPoint`
- size: `61`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18017e85c`
- `0x18017e990`
- `0x18017f040`

## pseudocode

```c
BOOL __stdcall DllEntryPoint(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  if ( fdwReason == 1 )
    sub_18017F040();
  return sub_18017E85C(hinstDLL, fdwReason, lpReserved);
}

```

## disassembly

```asm
0x18017e990  mov     [rsp+arg_0], rbx
0x18017e995  mov     [rsp+arg_8], rsi
0x18017e99a  push    rdi
0x18017e99b  sub     rsp, 20h
0x18017e99f  mov     rdi, r8
0x18017e9a2  mov     ebx, edx
0x18017e9a4  mov     rsi, rcx
0x18017e9a7  cmp     edx, 1
0x18017e9aa  jnz     short loc_18017E9B1
0x18017e9ac  call    sub_18017F040
0x18017e9b1  mov     r8, rdi
0x18017e9b4  mov     edx, ebx
0x18017e9b6  mov     rcx, rsi
0x18017e9b9  mov     rbx, [rsp+28h+arg_0]
0x18017e9be  mov     rsi, [rsp+28h+arg_8]
0x18017e9c3  add     rsp, 20h
0x18017e9c7  pop     rdi
0x18017e9c8  jmp     sub_18017E85C
```
