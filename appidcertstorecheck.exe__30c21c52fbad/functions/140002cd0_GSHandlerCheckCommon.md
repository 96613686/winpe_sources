# __GSHandlerCheckCommon

- ea: `0x140002cd0`
- end: `0x140002d33`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140002cac`

## callees

- `0x140002cd0`
- `0x140002d60`

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
0x140002cd0  mov     r10, rcx
0x140002cd3  mov     r11, rdx
0x140002cd6  mov     ecx, [r8]
0x140002cd9  and     ecx, 0FFFFFFF8h
0x140002cdc  test    byte ptr [r8], 4
0x140002ce0  jz      short loc_140002CF7
0x140002ce2  mov     eax, [r8+8]
0x140002ce6  movsxd  r9, dword ptr [r8+4]
0x140002cea  neg     eax
0x140002cec  movsxd  rdx, eax
0x140002cef  add     r9, r10
0x140002cf2  and     r9, rdx
0x140002cf5  jmp     short loc_140002CFA
0x140002cf7  mov     r9, r10
0x140002cfa  movsxd  rax, ecx
0x140002cfd  mov     rdx, [rax+r9]
0x140002d01  mov     rax, [r11+10h]
0x140002d05  mov     ecx, [rax+8]
0x140002d08  mov     rax, [r11+8]
0x140002d0c  test    byte ptr [rcx+rax+3], 0Fh
0x140002d11  jz      short loc_140002D25
0x140002d13  movzx   eax, byte ptr [rcx+rax+3]
0x140002d18  mov     ecx, 0FFFFFFF0h
0x140002d1d  and     rax, rcx
0x140002d20  add     rax, r10
0x140002d23  jmp     short loc_140002D28
0x140002d25  mov     rax, r10
0x140002d28  xor     rdx, rax
0x140002d2b  mov     rcx, rdx; StackCookie
0x140002d2e  jmp     __security_check_cookie
```
