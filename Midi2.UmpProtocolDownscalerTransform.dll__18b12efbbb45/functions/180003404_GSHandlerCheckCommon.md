# __GSHandlerCheckCommon

- ea: `0x180003404`
- end: `0x180003467`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800033e0`
- `0x180012008`

## callees

- `0x180002e70`
- `0x180003404`

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
0x180003404  mov     r10, rcx
0x180003407  mov     r11, rdx
0x18000340a  mov     ecx, [r8]
0x18000340d  and     ecx, 0FFFFFFF8h
0x180003410  test    byte ptr [r8], 4
0x180003414  jz      short loc_18000342B
0x180003416  mov     eax, [r8+8]
0x18000341a  movsxd  r9, dword ptr [r8+4]
0x18000341e  neg     eax
0x180003420  movsxd  rdx, eax
0x180003423  add     r9, r10
0x180003426  and     r9, rdx
0x180003429  jmp     short loc_18000342E
0x18000342b  mov     r9, r10
0x18000342e  movsxd  rax, ecx
0x180003431  mov     rdx, [rax+r9]
0x180003435  mov     rax, [r11+10h]
0x180003439  mov     ecx, [rax+8]
0x18000343c  mov     rax, [r11+8]
0x180003440  test    byte ptr [rcx+rax+3], 0Fh
0x180003445  jz      short loc_180003459
0x180003447  movzx   eax, byte ptr [rcx+rax+3]
0x18000344c  mov     ecx, 0FFFFFFF0h
0x180003451  and     rax, rcx
0x180003454  add     rax, r10
0x180003457  jmp     short loc_18000345C
0x180003459  mov     rax, r10
0x18000345c  xor     rdx, rax
0x18000345f  mov     rcx, rdx; StackCookie
0x180003462  jmp     __security_check_cookie
```
