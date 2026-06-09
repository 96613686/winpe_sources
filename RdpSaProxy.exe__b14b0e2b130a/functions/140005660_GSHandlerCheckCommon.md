# __GSHandlerCheckCommon

- ea: `0x140005660`
- end: `0x1400056c3`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000563c`

## callees

- `0x140005660`
- `0x1400056f0`

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
0x140005660  mov     r10, rcx
0x140005663  mov     r11, rdx
0x140005666  mov     ecx, [r8]
0x140005669  and     ecx, 0FFFFFFF8h
0x14000566c  test    byte ptr [r8], 4
0x140005670  jz      short loc_140005687
0x140005672  mov     eax, [r8+8]
0x140005676  movsxd  r9, dword ptr [r8+4]
0x14000567a  neg     eax
0x14000567c  movsxd  rdx, eax
0x14000567f  add     r9, r10
0x140005682  and     r9, rdx
0x140005685  jmp     short loc_14000568A
0x140005687  mov     r9, r10
0x14000568a  movsxd  rax, ecx
0x14000568d  mov     rdx, [rax+r9]
0x140005691  mov     rax, [r11+10h]
0x140005695  mov     ecx, [rax+8]
0x140005698  mov     rax, [r11+8]
0x14000569c  test    byte ptr [rcx+rax+3], 0Fh
0x1400056a1  jz      short loc_1400056B5
0x1400056a3  movzx   eax, byte ptr [rcx+rax+3]
0x1400056a8  mov     ecx, 0FFFFFFF0h
0x1400056ad  and     rax, rcx
0x1400056b0  add     rax, r10
0x1400056b3  jmp     short loc_1400056B8
0x1400056b5  mov     rax, r10
0x1400056b8  xor     rdx, rax
0x1400056bb  mov     rcx, rdx; StackCookie
0x1400056be  jmp     __security_check_cookie
```
