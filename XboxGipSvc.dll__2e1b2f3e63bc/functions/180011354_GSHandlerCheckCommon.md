# __GSHandlerCheckCommon

- ea: `0x180011354`
- end: `0x1800113b7`
- name: `__GSHandlerCheckCommon`
- size: `99`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011330`
- `0x1800113c0`

## callees

- `0x1800016c0`
- `0x180011354`

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
0x180011354  mov     r10, rcx
0x180011357  mov     r11, rdx
0x18001135a  mov     ecx, [r8]
0x18001135d  and     ecx, 0FFFFFFF8h
0x180011360  test    byte ptr [r8], 4
0x180011364  jz      short loc_18001137B
0x180011366  mov     eax, [r8+8]
0x18001136a  movsxd  r9, dword ptr [r8+4]
0x18001136e  neg     eax
0x180011370  movsxd  rdx, eax
0x180011373  add     r9, r10
0x180011376  and     r9, rdx
0x180011379  jmp     short loc_18001137E
0x18001137b  mov     r9, r10
0x18001137e  movsxd  rax, ecx
0x180011381  mov     rdx, [rax+r9]
0x180011385  mov     rax, [r11+10h]
0x180011389  mov     ecx, [rax+8]
0x18001138c  mov     rax, [r11+8]
0x180011390  test    byte ptr [rcx+rax+3], 0Fh
0x180011395  jz      short loc_1800113A9
0x180011397  movzx   eax, byte ptr [rcx+rax+3]
0x18001139c  mov     ecx, 0FFFFFFF0h
0x1800113a1  and     rax, rcx
0x1800113a4  add     rax, r10
0x1800113a7  jmp     short loc_1800113AC
0x1800113a9  mov     rax, r10
0x1800113ac  xor     rdx, rax
0x1800113af  mov     rcx, rdx; StackCookie
0x1800113b2  jmp     __security_check_cookie
```
