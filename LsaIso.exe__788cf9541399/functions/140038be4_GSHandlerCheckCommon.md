# __GSHandlerCheckCommon

- ea: `0x140038be4`
- end: `0x140038c47`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140038bc0`
- `0x140038c50`

## callees

- `0x140038be4`
- `0x140038d10`

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
0x140038be4  mov     r10, rcx
0x140038be7  mov     r11, rdx
0x140038bea  mov     ecx, [r8]
0x140038bed  and     ecx, 0FFFFFFF8h
0x140038bf0  test    byte ptr [r8], 4
0x140038bf4  jz      short loc_140038C0B
0x140038bf6  mov     eax, [r8+8]
0x140038bfa  movsxd  r9, dword ptr [r8+4]
0x140038bfe  neg     eax
0x140038c00  movsxd  rdx, eax
0x140038c03  add     r9, r10
0x140038c06  and     r9, rdx
0x140038c09  jmp     short loc_140038C0E
0x140038c0b  mov     r9, r10
0x140038c0e  movsxd  rax, ecx
0x140038c11  mov     rdx, [rax+r9]
0x140038c15  mov     rax, [r11+10h]
0x140038c19  mov     ecx, [rax+8]
0x140038c1c  mov     rax, [r11+8]
0x140038c20  test    byte ptr [rcx+rax+3], 0Fh
0x140038c25  jz      short loc_140038C39
0x140038c27  movzx   eax, byte ptr [rcx+rax+3]
0x140038c2c  mov     ecx, 0FFFFFFF0h
0x140038c31  and     rax, rcx
0x140038c34  add     rax, r10
0x140038c37  jmp     short loc_140038C3C
0x140038c39  mov     rax, r10
0x140038c3c  xor     rdx, rax
0x140038c3f  mov     rcx, rdx; StackCookie
0x140038c42  jmp     __security_check_cookie
```
