# __GSHandlerCheckCommon

- ea: `0x14001395c`
- end: `0x1400139cc`
- name: `__GSHandlerCheckCommon`
- size: `112`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013938`
- `0x1400139d4`

## callees

- `0x14001395c`
- `0x140013b00`

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
0x14001395c  sub     rsp, 28h
0x140013960  mov     eax, [r8]
0x140013963  mov     r10, rcx
0x140013966  mov     ecx, eax
0x140013968  mov     r11, rdx
0x14001396b  and     ecx, 0FFFFFFF8h
0x14001396e  test    al, 4
0x140013970  jz      short loc_140013987
0x140013972  mov     eax, [r8+8]
0x140013976  movsxd  r9, dword ptr [r8+4]
0x14001397a  neg     eax
0x14001397c  movsxd  rdx, eax
0x14001397f  add     r9, r10
0x140013982  and     r9, rdx
0x140013985  jmp     short loc_14001398A
0x140013987  mov     r9, r10
0x14001398a  movsxd  rax, ecx
0x14001398d  mov     rdx, [rax+r9]
0x140013991  mov     rax, [r11+10h]
0x140013995  mov     ecx, [rax+8]
0x140013998  mov     rax, [r11+8]
0x14001399c  movzx   r8d, byte ptr [rcx+rax+3]
0x1400139a2  test    r8b, 0Fh
0x1400139a6  jz      short loc_1400139B8
0x1400139a8  mov     eax, r8d
0x1400139ab  mov     ecx, 0FFFFFFF0h
0x1400139b0  and     rax, rcx
0x1400139b3  add     rax, r10
0x1400139b6  jmp     short loc_1400139BB
0x1400139b8  mov     rax, r10
0x1400139bb  xor     rdx, rax
0x1400139be  mov     rcx, rdx; StackCookie
0x1400139c1  call    __security_check_cookie
0x1400139c6  add     rsp, 28h
0x1400139ca  retn
```
