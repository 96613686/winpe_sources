# __GSHandlerCheckCommon

- ea: `0x18002681c`
- end: `0x18002687f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800267f8`
- `0x180026888`
- `0x180035050`

## callees

- `0x18002681c`
- `0x1800350e0`

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
0x18002681c  mov     r10, rcx
0x18002681f  mov     r11, rdx
0x180026822  mov     ecx, [r8]
0x180026825  and     ecx, 0FFFFFFF8h
0x180026828  test    byte ptr [r8], 4
0x18002682c  jz      short loc_180026843
0x18002682e  mov     eax, [r8+8]
0x180026832  movsxd  r9, dword ptr [r8+4]
0x180026836  neg     eax
0x180026838  movsxd  rdx, eax
0x18002683b  add     r9, r10
0x18002683e  and     r9, rdx
0x180026841  jmp     short loc_180026846
0x180026843  mov     r9, r10
0x180026846  movsxd  rax, ecx
0x180026849  mov     rdx, [rax+r9]
0x18002684d  mov     rax, [r11+10h]
0x180026851  mov     ecx, [rax+8]
0x180026854  mov     rax, [r11+8]
0x180026858  test    byte ptr [rcx+rax+3], 0Fh
0x18002685d  jz      short loc_180026871
0x18002685f  movzx   eax, byte ptr [rcx+rax+3]
0x180026864  mov     ecx, 0FFFFFFF0h
0x180026869  and     rax, rcx
0x18002686c  add     rax, r10
0x18002686f  jmp     short loc_180026874
0x180026871  mov     rax, r10
0x180026874  xor     rdx, rax
0x180026877  mov     rcx, rdx; StackCookie
0x18002687a  jmp     __security_check_cookie
```
