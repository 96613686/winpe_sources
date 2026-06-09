# __GSHandlerCheckCommon

- ea: `0x140007858`
- end: `0x1400078bb`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140007834`

## callees

- `0x140002910`
- `0x140007858`

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
0x140007858  mov     r10, rcx
0x14000785b  mov     r11, rdx
0x14000785e  mov     ecx, [r8]
0x140007861  and     ecx, 0FFFFFFF8h
0x140007864  test    byte ptr [r8], 4
0x140007868  jz      short loc_14000787F
0x14000786a  mov     eax, [r8+8]
0x14000786e  movsxd  r9, dword ptr [r8+4]
0x140007872  neg     eax
0x140007874  movsxd  rdx, eax
0x140007877  add     r9, r10
0x14000787a  and     r9, rdx
0x14000787d  jmp     short loc_140007882
0x14000787f  mov     r9, r10
0x140007882  movsxd  rax, ecx
0x140007885  mov     rdx, [rax+r9]
0x140007889  mov     rax, [r11+10h]
0x14000788d  mov     ecx, [rax+8]
0x140007890  mov     rax, [r11+8]
0x140007894  test    byte ptr [rcx+rax+3], 0Fh
0x140007899  jz      short loc_1400078AD
0x14000789b  movzx   eax, byte ptr [rcx+rax+3]
0x1400078a0  mov     ecx, 0FFFFFFF0h
0x1400078a5  and     rax, rcx
0x1400078a8  add     rax, r10
0x1400078ab  jmp     short loc_1400078B0
0x1400078ad  mov     rax, r10
0x1400078b0  xor     rdx, rax
0x1400078b3  mov     rcx, rdx; StackCookie
0x1400078b6  jmp     __security_check_cookie
```
