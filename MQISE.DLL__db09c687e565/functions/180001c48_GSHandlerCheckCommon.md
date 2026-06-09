# __GSHandlerCheckCommon

- ea: `0x180001c48`
- end: `0x180001cab`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001c24`
- `0x180001cb4`
- `0x18000f4d4`
- `0x18000f53c`

## callees

- `0x180001c48`
- `0x18000f5f0`

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
0x180001c48  mov     r10, rcx
0x180001c4b  mov     r11, rdx
0x180001c4e  mov     ecx, [r8]
0x180001c51  and     ecx, 0FFFFFFF8h
0x180001c54  test    byte ptr [r8], 4
0x180001c58  jz      short loc_180001C6F
0x180001c5a  mov     eax, [r8+8]
0x180001c5e  movsxd  r9, dword ptr [r8+4]
0x180001c62  neg     eax
0x180001c64  movsxd  rdx, eax
0x180001c67  add     r9, r10
0x180001c6a  and     r9, rdx
0x180001c6d  jmp     short loc_180001C72
0x180001c6f  mov     r9, r10
0x180001c72  movsxd  rax, ecx
0x180001c75  mov     rdx, [rax+r9]
0x180001c79  mov     rax, [r11+10h]
0x180001c7d  mov     ecx, [rax+8]
0x180001c80  mov     rax, [r11+8]
0x180001c84  test    byte ptr [rcx+rax+3], 0Fh
0x180001c89  jz      short loc_180001C9D
0x180001c8b  movzx   eax, byte ptr [rcx+rax+3]
0x180001c90  mov     ecx, 0FFFFFFF0h
0x180001c95  and     rax, rcx
0x180001c98  add     rax, r10
0x180001c9b  jmp     short loc_180001CA0
0x180001c9d  mov     rax, r10
0x180001ca0  xor     rdx, rax
0x180001ca3  mov     rcx, rdx; StackCookie
0x180001ca6  jmp     __security_check_cookie
```
