# __GSHandlerCheckCommon

- ea: `0x18002ac44`
- end: `0x18002aca7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ac20`
- `0x18002acb0`

## callees

- `0x1800016d0`
- `0x18002ac44`

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
0x18002ac44  mov     r10, rcx
0x18002ac47  mov     r11, rdx
0x18002ac4a  mov     ecx, [r8]
0x18002ac4d  and     ecx, 0FFFFFFF8h
0x18002ac50  test    byte ptr [r8], 4
0x18002ac54  jz      short loc_18002AC6B
0x18002ac56  mov     eax, [r8+8]
0x18002ac5a  movsxd  r9, dword ptr [r8+4]
0x18002ac5e  neg     eax
0x18002ac60  movsxd  rdx, eax
0x18002ac63  add     r9, r10
0x18002ac66  and     r9, rdx
0x18002ac69  jmp     short loc_18002AC6E
0x18002ac6b  mov     r9, r10
0x18002ac6e  movsxd  rax, ecx
0x18002ac71  mov     rdx, [rax+r9]
0x18002ac75  mov     rax, [r11+10h]
0x18002ac79  mov     ecx, [rax+8]
0x18002ac7c  mov     rax, [r11+8]
0x18002ac80  test    byte ptr [rcx+rax+3], 0Fh
0x18002ac85  jz      short loc_18002AC99
0x18002ac87  movzx   eax, byte ptr [rcx+rax+3]
0x18002ac8c  mov     ecx, 0FFFFFFF0h
0x18002ac91  and     rax, rcx
0x18002ac94  add     rax, r10
0x18002ac97  jmp     short loc_18002AC9C
0x18002ac99  mov     rax, r10
0x18002ac9c  xor     rdx, rax
0x18002ac9f  mov     rcx, rdx; StackCookie
0x18002aca2  jmp     __security_check_cookie
```
