# __GSHandlerCheckCommon

- ea: `0x18001bbbc`
- end: `0x18001bc1f`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bb98`
- `0x18001bc28`

## callees

- `0x18001bbbc`
- `0x18001bcf0`

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
0x18001bbbc  mov     r10, rcx
0x18001bbbf  mov     r11, rdx
0x18001bbc2  mov     ecx, [r8]
0x18001bbc5  and     ecx, 0FFFFFFF8h
0x18001bbc8  test    byte ptr [r8], 4
0x18001bbcc  jz      short loc_18001BBE3
0x18001bbce  mov     eax, [r8+8]
0x18001bbd2  movsxd  r9, dword ptr [r8+4]
0x18001bbd6  neg     eax
0x18001bbd8  movsxd  rdx, eax
0x18001bbdb  add     r9, r10
0x18001bbde  and     r9, rdx
0x18001bbe1  jmp     short loc_18001BBE6
0x18001bbe3  mov     r9, r10
0x18001bbe6  movsxd  rax, ecx
0x18001bbe9  mov     rdx, [rax+r9]
0x18001bbed  mov     rax, [r11+10h]
0x18001bbf1  mov     ecx, [rax+8]
0x18001bbf4  mov     rax, [r11+8]
0x18001bbf8  test    byte ptr [rcx+rax+3], 0Fh
0x18001bbfd  jz      short loc_18001BC11
0x18001bbff  movzx   eax, byte ptr [rcx+rax+3]
0x18001bc04  mov     ecx, 0FFFFFFF0h
0x18001bc09  and     rax, rcx
0x18001bc0c  add     rax, r10
0x18001bc0f  jmp     short loc_18001BC14
0x18001bc11  mov     rax, r10
0x18001bc14  xor     rdx, rax
0x18001bc17  mov     rcx, rdx; StackCookie
0x18001bc1a  jmp     __security_check_cookie
```
