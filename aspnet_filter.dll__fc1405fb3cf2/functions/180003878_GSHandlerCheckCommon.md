# __GSHandlerCheckCommon

- ea: `0x180003878`
- end: `0x1800038d3`
- name: `__GSHandlerCheckCommon`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003858`

## callees

- `0x180003878`
- `0x180003950`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  __int64 result; // rax

  v2 = *(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL);
  result = *(_QWORD *)(a2 + 8);
  if ( (*(_BYTE *)(v2 + result + 3) & 0xF) != 0 )
    return *(_BYTE *)(v2 + result + 3) & 0xF0;
  return result;
}

```

## disassembly

```asm
0x180003878  push    rbx
0x18000387a  mov     r11d, [r8]
0x18000387d  mov     rbx, rdx
0x180003880  and     r11d, 0FFFFFFF8h
0x180003884  mov     r9, rcx
0x180003887  test    byte ptr [r8], 4
0x18000388b  mov     r10, rcx
0x18000388e  jz      short loc_1800038A3
0x180003890  mov     eax, [r8+8]
0x180003894  movsxd  r10, dword ptr [r8+4]
0x180003898  neg     eax
0x18000389a  add     r10, rcx
0x18000389d  movsxd  rcx, eax
0x1800038a0  and     r10, rcx
0x1800038a3  movsxd  rax, r11d
0x1800038a6  mov     rdx, [rax+r10]
0x1800038aa  mov     rax, [rbx+10h]
0x1800038ae  mov     ecx, [rax+8]
0x1800038b1  mov     rax, [rbx+8]
0x1800038b5  test    byte ptr [rcx+rax+3], 0Fh
0x1800038ba  jz      short loc_1800038C7
0x1800038bc  movzx   eax, byte ptr [rcx+rax+3]
0x1800038c1  and     eax, 0FFFFFFF0h
0x1800038c4  add     r9, rax
0x1800038c7  xor     r9, rdx
0x1800038ca  mov     rcx, r9; StackCookie
0x1800038cd  pop     rbx
0x1800038ce  jmp     __security_check_cookie
```
