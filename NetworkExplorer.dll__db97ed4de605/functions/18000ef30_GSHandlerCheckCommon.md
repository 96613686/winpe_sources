# __GSHandlerCheckCommon

- ea: `0x18000ef30`
- end: `0x18000ef93`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ef0c`
- `0x18000ef9c`
- `0x18000f004`

## callees

- `0x18000ef30`
- `0x18000f0a0`

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
0x18000ef30  mov     r10, rcx
0x18000ef33  mov     r11, rdx
0x18000ef36  mov     ecx, [r8]
0x18000ef39  and     ecx, 0FFFFFFF8h
0x18000ef3c  test    byte ptr [r8], 4
0x18000ef40  jz      short loc_18000EF57
0x18000ef42  mov     eax, [r8+8]
0x18000ef46  movsxd  r9, dword ptr [r8+4]
0x18000ef4a  neg     eax
0x18000ef4c  movsxd  rdx, eax
0x18000ef4f  add     r9, r10
0x18000ef52  and     r9, rdx
0x18000ef55  jmp     short loc_18000EF5A
0x18000ef57  mov     r9, r10
0x18000ef5a  movsxd  rax, ecx
0x18000ef5d  mov     rdx, [rax+r9]
0x18000ef61  mov     rax, [r11+10h]
0x18000ef65  mov     ecx, [rax+8]
0x18000ef68  mov     rax, [r11+8]
0x18000ef6c  test    byte ptr [rcx+rax+3], 0Fh
0x18000ef71  jz      short loc_18000EF85
0x18000ef73  movzx   eax, byte ptr [rcx+rax+3]
0x18000ef78  mov     ecx, 0FFFFFFF0h
0x18000ef7d  and     rax, rcx
0x18000ef80  add     rax, r10
0x18000ef83  jmp     short loc_18000EF88
0x18000ef85  mov     rax, r10
0x18000ef88  xor     rdx, rax
0x18000ef8b  mov     rcx, rdx; StackCookie
0x18000ef8e  jmp     __security_check_cookie
```
