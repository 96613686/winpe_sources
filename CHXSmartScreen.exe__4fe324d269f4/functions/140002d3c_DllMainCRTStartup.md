# _DllMainCRTStartup

- ea: `0x140002d3c`
- end: `0x140002d79`
- name: `_DllMainCRTStartup`
- size: `61`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400318b0`

## callees

- `0x140002d3c`
- `0x140002d80`
- `0x140003754`

## pseudocode

```c
__int64 __fastcall DllMainCRTStartup(HINSTANCE hinstDLL, DWORD fdwReason, void *a3)
{
  if ( fdwReason == 1 )
    _security_init_cookie();
  return _DllMainCRTStartup(hinstDLL, fdwReason, a3);
}

```

## disassembly

```asm
0x140002d3c  mov     [rsp+arg_0], rbx
0x140002d41  mov     [rsp+arg_8], rsi
0x140002d46  push    rdi
0x140002d47  sub     rsp, 20h
0x140002d4b  mov     rdi, r8
0x140002d4e  mov     ebx, edx
0x140002d50  mov     rsi, rcx
0x140002d53  cmp     edx, 1
0x140002d56  jnz     short loc_140002D5D
0x140002d58  call    __security_init_cookie
0x140002d5d  mov     r8, rdi
0x140002d60  mov     edx, ebx; fdwReason
0x140002d62  mov     rcx, rsi; hinstDLL
0x140002d65  mov     rbx, [rsp+28h+arg_0]
0x140002d6a  mov     rsi, [rsp+28h+arg_8]
0x140002d6f  add     rsp, 20h
0x140002d73  pop     rdi
0x140002d74  jmp     __DllMainCRTStartup
```
