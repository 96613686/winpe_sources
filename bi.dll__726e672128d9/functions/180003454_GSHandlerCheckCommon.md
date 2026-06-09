# __GSHandlerCheckCommon

- ea: `0x180003454`
- end: `0x1800034b7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003430`

## callees

- `0x180003454`
- `0x1800034e0`

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
0x180003454  mov     r10, rcx
0x180003457  mov     r11, rdx
0x18000345a  mov     ecx, [r8]
0x18000345d  and     ecx, 0FFFFFFF8h
0x180003460  test    byte ptr [r8], 4
0x180003464  jz      short loc_18000347B
0x180003466  mov     eax, [r8+8]
0x18000346a  movsxd  r9, dword ptr [r8+4]
0x18000346e  neg     eax
0x180003470  movsxd  rdx, eax
0x180003473  add     r9, r10
0x180003476  and     r9, rdx
0x180003479  jmp     short loc_18000347E
0x18000347b  mov     r9, r10
0x18000347e  movsxd  rax, ecx
0x180003481  mov     rdx, [rax+r9]
0x180003485  mov     rax, [r11+10h]
0x180003489  mov     ecx, [rax+8]
0x18000348c  mov     rax, [r11+8]
0x180003490  test    byte ptr [rcx+rax+3], 0Fh
0x180003495  jz      short loc_1800034A9
0x180003497  movzx   eax, byte ptr [rcx+rax+3]
0x18000349c  mov     ecx, 0FFFFFFF0h
0x1800034a1  and     rax, rcx
0x1800034a4  add     rax, r10
0x1800034a7  jmp     short loc_1800034AC
0x1800034a9  mov     rax, r10
0x1800034ac  xor     rdx, rax
0x1800034af  mov     rcx, rdx; StackCookie
0x1800034b2  jmp     __security_check_cookie
```
