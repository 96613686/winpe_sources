# __GSHandlerCheckCommon

- ea: `0x14000ddac`
- end: `0x14000de0f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000dd88`
- `0x14000de18`

## callees

- `0x14000ddac`
- `0x14000ded0`

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
0x14000ddac  mov     r10, rcx
0x14000ddaf  mov     r11, rdx
0x14000ddb2  mov     ecx, [r8]
0x14000ddb5  and     ecx, 0FFFFFFF8h
0x14000ddb8  test    byte ptr [r8], 4
0x14000ddbc  jz      short loc_14000DDD3
0x14000ddbe  mov     eax, [r8+8]
0x14000ddc2  movsxd  r9, dword ptr [r8+4]
0x14000ddc6  neg     eax
0x14000ddc8  movsxd  rdx, eax
0x14000ddcb  add     r9, r10
0x14000ddce  and     r9, rdx
0x14000ddd1  jmp     short loc_14000DDD6
0x14000ddd3  mov     r9, r10
0x14000ddd6  movsxd  rax, ecx
0x14000ddd9  mov     rdx, [rax+r9]
0x14000dddd  mov     rax, [r11+10h]
0x14000dde1  mov     ecx, [rax+8]
0x14000dde4  mov     rax, [r11+8]
0x14000dde8  test    byte ptr [rcx+rax+3], 0Fh
0x14000dded  jz      short loc_14000DE01
0x14000ddef  movzx   eax, byte ptr [rcx+rax+3]
0x14000ddf4  mov     ecx, 0FFFFFFF0h
0x14000ddf9  and     rax, rcx
0x14000ddfc  add     rax, r10
0x14000ddff  jmp     short loc_14000DE04
0x14000de01  mov     rax, r10
0x14000de04  xor     rdx, rax
0x14000de07  mov     rcx, rdx; StackCookie
0x14000de0a  jmp     __security_check_cookie
```
