# __GSHandlerCheckCommon

- ea: `0x180001c60`
- end: `0x180001cc3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c3c`
- `0x18000ca0c`

## callees

- `0x1800017c0`
- `0x180001c60`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rax

  v3 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  v4 = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v3 + v4 + 3) & 0xF) != 0 )
    return a1 + (*(_BYTE *)(v3 + v4 + 3) & 0xF0);
  else
    return a1;
}

```

## disassembly

```asm
0x180001c60  mov     r10, rcx
0x180001c63  mov     r11, rdx
0x180001c66  mov     ecx, [r8]
0x180001c69  and     ecx, 0FFFFFFF8h
0x180001c6c  test    byte ptr [r8], 4
0x180001c70  jz      short loc_180001C87
0x180001c72  mov     eax, [r8+8]
0x180001c76  movsxd  r9, dword ptr [r8+4]
0x180001c7a  neg     eax
0x180001c7c  movsxd  rdx, eax
0x180001c7f  add     r9, r10
0x180001c82  and     r9, rdx
0x180001c85  jmp     short loc_180001C8A
0x180001c87  mov     r9, r10
0x180001c8a  movsxd  rax, ecx
0x180001c8d  mov     rdx, [rax+r9]
0x180001c91  mov     rax, [r11+10h]
0x180001c95  mov     ecx, [rax+8]
0x180001c98  mov     rax, [r11+8]
0x180001c9c  test    byte ptr [rcx+rax+3], 0Fh
0x180001ca1  jz      short loc_180001CB5
0x180001ca3  movzx   eax, byte ptr [rcx+rax+3]
0x180001ca8  mov     ecx, 0FFFFFFF0h
0x180001cad  and     rax, rcx
0x180001cb0  add     rax, r10
0x180001cb3  jmp     short loc_180001CB8
0x180001cb5  mov     rax, r10
0x180001cb8  xor     rdx, rax
0x180001cbb  mov     rcx, rdx; StackCookie
0x180001cbe  jmp     __security_check_cookie
```
