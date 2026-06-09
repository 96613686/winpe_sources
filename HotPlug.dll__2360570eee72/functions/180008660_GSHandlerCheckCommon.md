# __GSHandlerCheckCommon

- ea: `0x180008660`
- end: `0x1800086c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000863c`
- `0x1800086cc`

## callees

- `0x180008660`
- `0x180008760`

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
0x180008660  mov     r10, rcx
0x180008663  mov     r11, rdx
0x180008666  mov     ecx, [r8]
0x180008669  and     ecx, 0FFFFFFF8h
0x18000866c  test    byte ptr [r8], 4
0x180008670  jz      short loc_180008687
0x180008672  mov     eax, [r8+8]
0x180008676  movsxd  r9, dword ptr [r8+4]
0x18000867a  neg     eax
0x18000867c  movsxd  rdx, eax
0x18000867f  add     r9, r10
0x180008682  and     r9, rdx
0x180008685  jmp     short loc_18000868A
0x180008687  mov     r9, r10
0x18000868a  movsxd  rax, ecx
0x18000868d  mov     rdx, [rax+r9]
0x180008691  mov     rax, [r11+10h]
0x180008695  mov     ecx, [rax+8]
0x180008698  mov     rax, [r11+8]
0x18000869c  test    byte ptr [rcx+rax+3], 0Fh
0x1800086a1  jz      short loc_1800086B5
0x1800086a3  movzx   eax, byte ptr [rcx+rax+3]
0x1800086a8  mov     ecx, 0FFFFFFF0h
0x1800086ad  and     rax, rcx
0x1800086b0  add     rax, r10
0x1800086b3  jmp     short loc_1800086B8
0x1800086b5  mov     rax, r10
0x1800086b8  xor     rdx, rax
0x1800086bb  mov     rcx, rdx; StackCookie
0x1800086be  jmp     __security_check_cookie
```
