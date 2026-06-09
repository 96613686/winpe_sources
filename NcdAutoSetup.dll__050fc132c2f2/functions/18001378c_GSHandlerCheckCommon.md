# __GSHandlerCheckCommon

- ea: `0x18001378c`
- end: `0x1800137ef`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013768`

## callees

- `0x18001378c`
- `0x180013840`

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
0x18001378c  mov     r10, rcx
0x18001378f  mov     r11, rdx
0x180013792  mov     ecx, [r8]
0x180013795  and     ecx, 0FFFFFFF8h
0x180013798  test    byte ptr [r8], 4
0x18001379c  jz      short loc_1800137B3
0x18001379e  mov     eax, [r8+8]
0x1800137a2  movsxd  r9, dword ptr [r8+4]
0x1800137a6  neg     eax
0x1800137a8  movsxd  rdx, eax
0x1800137ab  add     r9, r10
0x1800137ae  and     r9, rdx
0x1800137b1  jmp     short loc_1800137B6
0x1800137b3  mov     r9, r10
0x1800137b6  movsxd  rax, ecx
0x1800137b9  mov     rdx, [rax+r9]
0x1800137bd  mov     rax, [r11+10h]
0x1800137c1  mov     ecx, [rax+8]
0x1800137c4  mov     rax, [r11+8]
0x1800137c8  test    byte ptr [rcx+rax+3], 0Fh
0x1800137cd  jz      short loc_1800137E1
0x1800137cf  movzx   eax, byte ptr [rcx+rax+3]
0x1800137d4  mov     ecx, 0FFFFFFF0h
0x1800137d9  and     rax, rcx
0x1800137dc  add     rax, r10
0x1800137df  jmp     short loc_1800137E4
0x1800137e1  mov     rax, r10
0x1800137e4  xor     rdx, rax
0x1800137e7  mov     rcx, rdx; StackCookie
0x1800137ea  jmp     __security_check_cookie
```
