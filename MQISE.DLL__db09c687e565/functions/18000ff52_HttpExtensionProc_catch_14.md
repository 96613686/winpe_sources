# HttpExtensionProc$catch$14

- ea: `0x18000ff52`
- end: `0x18000ff93`
- name: `HttpExtensionProc$catch$14`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800096b8`
- `0x18000ff52`

## pseudocode

```c
_BOOL8 __fastcall HttpExtensionProc_catch_14(__int64 a1, __int64 a2)
{
  return (unsigned int)SendResponse(*(_QWORD *)(a2 + 64), (__int64)"500 Internal server error", 0) != 0;
}

```

## disassembly

```asm
0x18000ff52  mov     [rsp+arg_8], rdx
0x18000ff57  push    rbp
0x18000ff58  sub     rsp, 30h
0x18000ff5c  mov     rbp, rdx
0x18000ff5f  xor     r8d, r8d
0x18000ff62  lea     rdx, a500InternalSer; "500 Internal server error"
0x18000ff69  mov     rcx, [rbp+40h]
0x18000ff6d  call    SendResponse
0x18000ff72  test    eax, eax
0x18000ff74  jnz     short loc_18000FF82
0x18000ff76  mov     rax, 0
0x18000ff80  jmp     short loc_18000FF8C
0x18000ff82  mov     rax, 1
0x18000ff8c  add     rsp, 30h
0x18000ff90  pop     rbp
0x18000ff91  retn
```
