# __GSHandlerCheckCommon

- ea: `0x180013790`
- end: `0x1800137f3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001376c`

## callees

- `0x180001400`
- `0x180013790`

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
0x180013790  mov     r10, rcx
0x180013793  mov     r11, rdx
0x180013796  mov     ecx, [r8]
0x180013799  and     ecx, 0FFFFFFF8h
0x18001379c  test    byte ptr [r8], 4
0x1800137a0  jz      short loc_1800137B7
0x1800137a2  mov     eax, [r8+8]
0x1800137a6  movsxd  r9, dword ptr [r8+4]
0x1800137aa  neg     eax
0x1800137ac  movsxd  rdx, eax
0x1800137af  add     r9, r10
0x1800137b2  and     r9, rdx
0x1800137b5  jmp     short loc_1800137BA
0x1800137b7  mov     r9, r10
0x1800137ba  movsxd  rax, ecx
0x1800137bd  mov     rdx, [rax+r9]
0x1800137c1  mov     rax, [r11+10h]
0x1800137c5  mov     ecx, [rax+8]
0x1800137c8  mov     rax, [r11+8]
0x1800137cc  test    byte ptr [rcx+rax+3], 0Fh
0x1800137d1  jz      short loc_1800137E5
0x1800137d3  movzx   eax, byte ptr [rcx+rax+3]
0x1800137d8  mov     ecx, 0FFFFFFF0h
0x1800137dd  and     rax, rcx
0x1800137e0  add     rax, r10
0x1800137e3  jmp     short loc_1800137E8
0x1800137e5  mov     rax, r10
0x1800137e8  xor     rdx, rax
0x1800137eb  mov     rcx, rdx; StackCookie
0x1800137ee  jmp     __security_check_cookie
```
