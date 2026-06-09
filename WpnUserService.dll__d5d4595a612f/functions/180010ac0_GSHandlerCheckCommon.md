# __GSHandlerCheckCommon

- ea: `0x180010ac0`
- end: `0x180010b23`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010a9c`
- `0x180010b2c`

## callees

- `0x180002bc0`
- `0x180010ac0`

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
0x180010ac0  mov     r10, rcx
0x180010ac3  mov     r11, rdx
0x180010ac6  mov     ecx, [r8]
0x180010ac9  and     ecx, 0FFFFFFF8h
0x180010acc  test    byte ptr [r8], 4
0x180010ad0  jz      short loc_180010AE7
0x180010ad2  mov     eax, [r8+8]
0x180010ad6  movsxd  r9, dword ptr [r8+4]
0x180010ada  neg     eax
0x180010adc  movsxd  rdx, eax
0x180010adf  add     r9, r10
0x180010ae2  and     r9, rdx
0x180010ae5  jmp     short loc_180010AEA
0x180010ae7  mov     r9, r10
0x180010aea  movsxd  rax, ecx
0x180010aed  mov     rdx, [rax+r9]
0x180010af1  mov     rax, [r11+10h]
0x180010af5  mov     ecx, [rax+8]
0x180010af8  mov     rax, [r11+8]
0x180010afc  test    byte ptr [rcx+rax+3], 0Fh
0x180010b01  jz      short loc_180010B15
0x180010b03  movzx   eax, byte ptr [rcx+rax+3]
0x180010b08  mov     ecx, 0FFFFFFF0h
0x180010b0d  and     rax, rcx
0x180010b10  add     rax, r10
0x180010b13  jmp     short loc_180010B18
0x180010b15  mov     rax, r10
0x180010b18  xor     rdx, rax
0x180010b1b  mov     rcx, rdx; StackCookie
0x180010b1e  jmp     __security_check_cookie
```
