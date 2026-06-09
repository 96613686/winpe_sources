# __GSHandlerCheckCommon

- ea: `0x14000436c`
- end: `0x1400043cf`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140004348`
- `0x1400043d8`

## callees

- `0x14000436c`
- `0x140004460`

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
0x14000436c  mov     r10, rcx
0x14000436f  mov     r11, rdx
0x140004372  mov     ecx, [r8]
0x140004375  and     ecx, 0FFFFFFF8h
0x140004378  test    byte ptr [r8], 4
0x14000437c  jz      short loc_140004393
0x14000437e  mov     eax, [r8+8]
0x140004382  movsxd  r9, dword ptr [r8+4]
0x140004386  neg     eax
0x140004388  movsxd  rdx, eax
0x14000438b  add     r9, r10
0x14000438e  and     r9, rdx
0x140004391  jmp     short loc_140004396
0x140004393  mov     r9, r10
0x140004396  movsxd  rax, ecx
0x140004399  mov     rdx, [rax+r9]
0x14000439d  mov     rax, [r11+10h]
0x1400043a1  mov     ecx, [rax+8]
0x1400043a4  mov     rax, [r11+8]
0x1400043a8  test    byte ptr [rcx+rax+3], 0Fh
0x1400043ad  jz      short loc_1400043C1
0x1400043af  movzx   eax, byte ptr [rcx+rax+3]
0x1400043b4  mov     ecx, 0FFFFFFF0h
0x1400043b9  and     rax, rcx
0x1400043bc  add     rax, r10
0x1400043bf  jmp     short loc_1400043C4
0x1400043c1  mov     rax, r10
0x1400043c4  xor     rdx, rax
0x1400043c7  mov     rcx, rdx; StackCookie
0x1400043ca  jmp     __security_check_cookie
```
