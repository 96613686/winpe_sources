# __GSHandlerCheckCommon

- ea: `0x18001bd74`
- end: `0x18001bdd7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bd50`

## callees

- `0x180001a80`
- `0x18001bd74`

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
0x18001bd74  mov     r10, rcx
0x18001bd77  mov     r11, rdx
0x18001bd7a  mov     ecx, [r8]
0x18001bd7d  and     ecx, 0FFFFFFF8h
0x18001bd80  test    byte ptr [r8], 4
0x18001bd84  jz      short loc_18001BD9B
0x18001bd86  mov     eax, [r8+8]
0x18001bd8a  movsxd  r9, dword ptr [r8+4]
0x18001bd8e  neg     eax
0x18001bd90  movsxd  rdx, eax
0x18001bd93  add     r9, r10
0x18001bd96  and     r9, rdx
0x18001bd99  jmp     short loc_18001BD9E
0x18001bd9b  mov     r9, r10
0x18001bd9e  movsxd  rax, ecx
0x18001bda1  mov     rdx, [rax+r9]
0x18001bda5  mov     rax, [r11+10h]
0x18001bda9  mov     ecx, [rax+8]
0x18001bdac  mov     rax, [r11+8]
0x18001bdb0  test    byte ptr [rcx+rax+3], 0Fh
0x18001bdb5  jz      short loc_18001BDC9
0x18001bdb7  movzx   eax, byte ptr [rcx+rax+3]
0x18001bdbc  mov     ecx, 0FFFFFFF0h
0x18001bdc1  and     rax, rcx
0x18001bdc4  add     rax, r10
0x18001bdc7  jmp     short loc_18001BDCC
0x18001bdc9  mov     rax, r10
0x18001bdcc  xor     rdx, rax
0x18001bdcf  mov     rcx, rdx; StackCookie
0x18001bdd2  jmp     __security_check_cookie
```
