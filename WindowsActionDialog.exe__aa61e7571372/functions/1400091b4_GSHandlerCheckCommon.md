# __GSHandlerCheckCommon

- ea: `0x1400091b4`
- end: `0x140009217`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009190`
- `0x140009220`

## callees

- `0x140001460`
- `0x1400091b4`

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
0x1400091b4  mov     r10, rcx
0x1400091b7  mov     r11, rdx
0x1400091ba  mov     ecx, [r8]
0x1400091bd  and     ecx, 0FFFFFFF8h
0x1400091c0  test    byte ptr [r8], 4
0x1400091c4  jz      short loc_1400091DB
0x1400091c6  mov     eax, [r8+8]
0x1400091ca  movsxd  r9, dword ptr [r8+4]
0x1400091ce  neg     eax
0x1400091d0  movsxd  rdx, eax
0x1400091d3  add     r9, r10
0x1400091d6  and     r9, rdx
0x1400091d9  jmp     short loc_1400091DE
0x1400091db  mov     r9, r10
0x1400091de  movsxd  rax, ecx
0x1400091e1  mov     rdx, [rax+r9]
0x1400091e5  mov     rax, [r11+10h]
0x1400091e9  mov     ecx, [rax+8]
0x1400091ec  mov     rax, [r11+8]
0x1400091f0  test    byte ptr [rcx+rax+3], 0Fh
0x1400091f5  jz      short loc_140009209
0x1400091f7  movzx   eax, byte ptr [rcx+rax+3]
0x1400091fc  mov     ecx, 0FFFFFFF0h
0x140009201  and     rax, rcx
0x140009204  add     rax, r10
0x140009207  jmp     short loc_14000920C
0x140009209  mov     rax, r10
0x14000920c  xor     rdx, rax
0x14000920f  mov     rcx, rdx; StackCookie
0x140009212  jmp     __security_check_cookie
```
