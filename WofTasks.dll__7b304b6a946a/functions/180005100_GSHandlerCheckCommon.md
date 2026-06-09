# __GSHandlerCheckCommon

- ea: `0x180005100`
- end: `0x180005163`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800050dc`

## callees

- `0x180005100`
- `0x1800051c0`

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
0x180005100  mov     r10, rcx
0x180005103  mov     r11, rdx
0x180005106  mov     ecx, [r8]
0x180005109  and     ecx, 0FFFFFFF8h
0x18000510c  test    byte ptr [r8], 4
0x180005110  jz      short loc_180005127
0x180005112  mov     eax, [r8+8]
0x180005116  movsxd  r9, dword ptr [r8+4]
0x18000511a  neg     eax
0x18000511c  movsxd  rdx, eax
0x18000511f  add     r9, r10
0x180005122  and     r9, rdx
0x180005125  jmp     short loc_18000512A
0x180005127  mov     r9, r10
0x18000512a  movsxd  rax, ecx
0x18000512d  mov     rdx, [rax+r9]
0x180005131  mov     rax, [r11+10h]
0x180005135  mov     ecx, [rax+8]
0x180005138  mov     rax, [r11+8]
0x18000513c  test    byte ptr [rcx+rax+3], 0Fh
0x180005141  jz      short loc_180005155
0x180005143  movzx   eax, byte ptr [rcx+rax+3]
0x180005148  mov     ecx, 0FFFFFFF0h
0x18000514d  and     rax, rcx
0x180005150  add     rax, r10
0x180005153  jmp     short loc_180005158
0x180005155  mov     rax, r10
0x180005158  xor     rdx, rax
0x18000515b  mov     rcx, rdx; StackCookie
0x18000515e  jmp     __security_check_cookie
```
