# __GSHandlerCheckCommon

- ea: `0x180006064`
- end: `0x1800060c7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006040`

## callees

- `0x180006064`
- `0x180006100`

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
0x180006064  mov     r10, rcx
0x180006067  mov     r11, rdx
0x18000606a  mov     ecx, [r8]
0x18000606d  and     ecx, 0FFFFFFF8h
0x180006070  test    byte ptr [r8], 4
0x180006074  jz      short loc_18000608B
0x180006076  mov     eax, [r8+8]
0x18000607a  movsxd  r9, dword ptr [r8+4]
0x18000607e  neg     eax
0x180006080  movsxd  rdx, eax
0x180006083  add     r9, r10
0x180006086  and     r9, rdx
0x180006089  jmp     short loc_18000608E
0x18000608b  mov     r9, r10
0x18000608e  movsxd  rax, ecx
0x180006091  mov     rdx, [rax+r9]
0x180006095  mov     rax, [r11+10h]
0x180006099  mov     ecx, [rax+8]
0x18000609c  mov     rax, [r11+8]
0x1800060a0  test    byte ptr [rcx+rax+3], 0Fh
0x1800060a5  jz      short loc_1800060B9
0x1800060a7  movzx   eax, byte ptr [rcx+rax+3]
0x1800060ac  mov     ecx, 0FFFFFFF0h
0x1800060b1  and     rax, rcx
0x1800060b4  add     rax, r10
0x1800060b7  jmp     short loc_1800060BC
0x1800060b9  mov     rax, r10
0x1800060bc  xor     rdx, rax
0x1800060bf  mov     rcx, rdx; StackCookie
0x1800060c2  jmp     __security_check_cookie
```
