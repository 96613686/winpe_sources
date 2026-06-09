# __GSHandlerCheckCommon

- ea: `0x18000ff30`
- end: `0x18000ff93`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ff0c`
- `0x18000ff9c`

## callees

- `0x180001ed0`
- `0x18000ff30`

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
0x18000ff30  mov     r10, rcx
0x18000ff33  mov     r11, rdx
0x18000ff36  mov     ecx, [r8]
0x18000ff39  and     ecx, 0FFFFFFF8h
0x18000ff3c  test    byte ptr [r8], 4
0x18000ff40  jz      short loc_18000FF57
0x18000ff42  mov     eax, [r8+8]
0x18000ff46  movsxd  r9, dword ptr [r8+4]
0x18000ff4a  neg     eax
0x18000ff4c  movsxd  rdx, eax
0x18000ff4f  add     r9, r10
0x18000ff52  and     r9, rdx
0x18000ff55  jmp     short loc_18000FF5A
0x18000ff57  mov     r9, r10
0x18000ff5a  movsxd  rax, ecx
0x18000ff5d  mov     rdx, [rax+r9]
0x18000ff61  mov     rax, [r11+10h]
0x18000ff65  mov     ecx, [rax+8]
0x18000ff68  mov     rax, [r11+8]
0x18000ff6c  test    byte ptr [rcx+rax+3], 0Fh
0x18000ff71  jz      short loc_18000FF85
0x18000ff73  movzx   eax, byte ptr [rcx+rax+3]
0x18000ff78  mov     ecx, 0FFFFFFF0h
0x18000ff7d  and     rax, rcx
0x18000ff80  add     rax, r10
0x18000ff83  jmp     short loc_18000FF88
0x18000ff85  mov     rax, r10
0x18000ff88  xor     rdx, rax
0x18000ff8b  mov     rcx, rdx; StackCookie
0x18000ff8e  jmp     __security_check_cookie
```
