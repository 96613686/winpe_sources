# __GSHandlerCheckCommon

- ea: `0x14001594c`
- end: `0x1400159bc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140015928`
- `0x1400159c4`

## callees

- `0x14001594c`
- `0x140015af0`

## pseudocode

```c
__int64 __fastcall _GSHandlerCheckCommon(__int64 a1, __int64 a2)
{
  int v2; // r8d

  v2 = *(unsigned __int8 *)(*(unsigned int *)(*(_QWORD *)(a2 + 16) + 8LL) + *(_QWORD *)(a2 + 8) + 3LL);
  if ( (v2 & 0xF) != 0 )
    return a1 + (v2 & 0xFFFFFFF0);
  else
    return a1;
}

```

## disassembly

```asm
0x14001594c  sub     rsp, 28h
0x140015950  mov     eax, [r8]
0x140015953  mov     r10, rcx
0x140015956  mov     ecx, eax
0x140015958  mov     r11, rdx
0x14001595b  and     ecx, 0FFFFFFF8h
0x14001595e  test    al, 4
0x140015960  jz      short loc_140015977
0x140015962  mov     eax, [r8+8]
0x140015966  movsxd  r9, dword ptr [r8+4]
0x14001596a  neg     eax
0x14001596c  movsxd  rdx, eax
0x14001596f  add     r9, r10
0x140015972  and     r9, rdx
0x140015975  jmp     short loc_14001597A
0x140015977  mov     r9, r10
0x14001597a  movsxd  rax, ecx
0x14001597d  mov     rdx, [rax+r9]
0x140015981  mov     rax, [r11+10h]
0x140015985  mov     ecx, [rax+8]
0x140015988  mov     rax, [r11+8]
0x14001598c  movzx   r8d, byte ptr [rcx+rax+3]
0x140015992  test    r8b, 0Fh
0x140015996  jz      short loc_1400159A8
0x140015998  mov     eax, r8d
0x14001599b  mov     ecx, 0FFFFFFF0h
0x1400159a0  and     rax, rcx
0x1400159a3  add     rax, r10
0x1400159a6  jmp     short loc_1400159AB
0x1400159a8  mov     rax, r10
0x1400159ab  xor     rdx, rax
0x1400159ae  mov     rcx, rdx; StackCookie
0x1400159b1  call    __security_check_cookie
0x1400159b6  add     rsp, 28h
0x1400159ba  retn
```
