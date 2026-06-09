# __GSHandlerCheckCommon

- ea: `0x180008ad0`
- end: `0x180008b33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008aac`

## callees

- `0x180008ad0`
- `0x180008ba0`

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
0x180008ad0  mov     r10, rcx
0x180008ad3  mov     r11, rdx
0x180008ad6  mov     ecx, [r8]
0x180008ad9  and     ecx, 0FFFFFFF8h
0x180008adc  test    byte ptr [r8], 4
0x180008ae0  jz      short loc_180008AF7
0x180008ae2  mov     eax, [r8+8]
0x180008ae6  movsxd  r9, dword ptr [r8+4]
0x180008aea  neg     eax
0x180008aec  movsxd  rdx, eax
0x180008aef  add     r9, r10
0x180008af2  and     r9, rdx
0x180008af5  jmp     short loc_180008AFA
0x180008af7  mov     r9, r10
0x180008afa  movsxd  rax, ecx
0x180008afd  mov     rdx, [rax+r9]
0x180008b01  mov     rax, [r11+10h]
0x180008b05  mov     ecx, [rax+8]
0x180008b08  mov     rax, [r11+8]
0x180008b0c  test    byte ptr [rcx+rax+3], 0Fh
0x180008b11  jz      short loc_180008B25
0x180008b13  movzx   eax, byte ptr [rcx+rax+3]
0x180008b18  mov     ecx, 0FFFFFFF0h
0x180008b1d  and     rax, rcx
0x180008b20  add     rax, r10
0x180008b23  jmp     short loc_180008B28
0x180008b25  mov     rax, r10
0x180008b28  xor     rdx, rax
0x180008b2b  mov     rcx, rdx; StackCookie
0x180008b2e  jmp     __security_check_cookie
```
