# __GSHandlerCheckCommon

- ea: `0x18002ce70`
- end: `0x18002ced3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ce4c`
- `0x18002cedc`

## callees

- `0x18002ce70`
- `0x18002cfa0`

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
0x18002ce70  mov     r10, rcx
0x18002ce73  mov     r11, rdx
0x18002ce76  mov     ecx, [r8]
0x18002ce79  and     ecx, 0FFFFFFF8h
0x18002ce7c  test    byte ptr [r8], 4
0x18002ce80  jz      short loc_18002CE97
0x18002ce82  mov     eax, [r8+8]
0x18002ce86  movsxd  r9, dword ptr [r8+4]
0x18002ce8a  neg     eax
0x18002ce8c  movsxd  rdx, eax
0x18002ce8f  add     r9, r10
0x18002ce92  and     r9, rdx
0x18002ce95  jmp     short loc_18002CE9A
0x18002ce97  mov     r9, r10
0x18002ce9a  movsxd  rax, ecx
0x18002ce9d  mov     rdx, [rax+r9]
0x18002cea1  mov     rax, [r11+10h]
0x18002cea5  mov     ecx, [rax+8]
0x18002cea8  mov     rax, [r11+8]
0x18002ceac  test    byte ptr [rcx+rax+3], 0Fh
0x18002ceb1  jz      short loc_18002CEC5
0x18002ceb3  movzx   eax, byte ptr [rcx+rax+3]
0x18002ceb8  mov     ecx, 0FFFFFFF0h
0x18002cebd  and     rax, rcx
0x18002cec0  add     rax, r10
0x18002cec3  jmp     short loc_18002CEC8
0x18002cec5  mov     rax, r10
0x18002cec8  xor     rdx, rax
0x18002cecb  mov     rcx, rdx; StackCookie
0x18002cece  jmp     __security_check_cookie
```
