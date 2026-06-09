# __GSHandlerCheckCommon

- ea: `0x14000ad44`
- end: `0x14000ada7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000ad20`
- `0x14000adb0`

## callees

- `0x14000ad44`
- `0x14000ae60`

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
0x14000ad44  mov     r10, rcx
0x14000ad47  mov     r11, rdx
0x14000ad4a  mov     ecx, [r8]
0x14000ad4d  and     ecx, 0FFFFFFF8h
0x14000ad50  test    byte ptr [r8], 4
0x14000ad54  jz      short loc_14000AD6B
0x14000ad56  mov     eax, [r8+8]
0x14000ad5a  movsxd  r9, dword ptr [r8+4]
0x14000ad5e  neg     eax
0x14000ad60  movsxd  rdx, eax
0x14000ad63  add     r9, r10
0x14000ad66  and     r9, rdx
0x14000ad69  jmp     short loc_14000AD6E
0x14000ad6b  mov     r9, r10
0x14000ad6e  movsxd  rax, ecx
0x14000ad71  mov     rdx, [rax+r9]
0x14000ad75  mov     rax, [r11+10h]
0x14000ad79  mov     ecx, [rax+8]
0x14000ad7c  mov     rax, [r11+8]
0x14000ad80  test    byte ptr [rcx+rax+3], 0Fh
0x14000ad85  jz      short loc_14000AD99
0x14000ad87  movzx   eax, byte ptr [rcx+rax+3]
0x14000ad8c  mov     ecx, 0FFFFFFF0h
0x14000ad91  and     rax, rcx
0x14000ad94  add     rax, r10
0x14000ad97  jmp     short loc_14000AD9C
0x14000ad99  mov     rax, r10
0x14000ad9c  xor     rdx, rax
0x14000ad9f  mov     rcx, rdx; StackCookie
0x14000ada2  jmp     __security_check_cookie
```
