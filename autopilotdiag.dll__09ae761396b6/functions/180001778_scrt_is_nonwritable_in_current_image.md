# __scrt_is_nonwritable_in_current_image

- ea: `0x180001778`
- end: `0x180001810`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x180001778`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( MEMORY[0x180000000] != 23117 )
    return 0;
  v2 = (_DWORD *)(0x180000000LL + MEMORY[0x18000003C]);
  if ( *v2 != 17744 || *(_WORD *)(0x180000018LL + MEMORY[0x18000003C]) != 523 )
    return 0;
  v3 = a1 - 0x180000000LL;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)(0x180000014LL + MEMORY[0x18000003C]) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)(0x180000006LL + MEMORY[0x18000003C])];
  while ( v4 != v5 )
  {
    v6 = (unsigned int)v4[3];
    if ( v3 >= v6 && v3 < (unsigned int)(v6 + v4[2]) )
      return v4 && v4[9] >= 0;
    v4 += 10;
  }
  v4 = 0;
  return v4 && v4[9] >= 0;
}

```

## disassembly

```asm
0x180001778  sub     rsp, 18h
0x18000177c  mov     r8, rcx
0x18000177f  mov     eax, 5A4Dh
0x180001784  cmp     cs:180000000h, ax
0x18000178b  jnz     short loc_180001805
0x18000178d  movsxd  rcx, dword ptr cs:18000003Ch
0x180001794  lea     rdx, cs:180000000h
0x18000179b  add     rcx, rdx
0x18000179e  cmp     dword ptr [rcx], 4550h
0x1800017a4  jnz     short loc_180001805
0x1800017a6  mov     eax, 20Bh
0x1800017ab  cmp     [rcx+18h], ax
0x1800017af  jnz     short loc_180001805
0x1800017b1  sub     r8, rdx
0x1800017b4  movzx   edx, word ptr [rcx+14h]
0x1800017b8  add     rdx, 18h
0x1800017bc  add     rdx, rcx
0x1800017bf  movzx   eax, word ptr [rcx+6]
0x1800017c3  lea     rcx, [rax+rax*4]
0x1800017c7  lea     r9, [rdx+rcx*8]
0x1800017cb  mov     [rsp+18h+var_18], rdx
0x1800017cf  cmp     rdx, r9
0x1800017d2  jz      short loc_1800017EC
0x1800017d4  mov     ecx, [rdx+0Ch]
0x1800017d7  cmp     r8, rcx
0x1800017da  jb      short loc_1800017E6
0x1800017dc  mov     eax, [rdx+8]
0x1800017df  add     eax, ecx
0x1800017e1  cmp     r8, rax
0x1800017e4  jb      short loc_1800017EE
0x1800017e6  add     rdx, 28h ; '('
0x1800017ea  jmp     short loc_1800017CB
0x1800017ec  xor     edx, edx
0x1800017ee  test    rdx, rdx
0x1800017f1  jnz     short loc_1800017F7
0x1800017f3  xor     al, al
0x1800017f5  jmp     short loc_18000180B
0x1800017f7  cmp     dword ptr [rdx+24h], 0
0x1800017fb  jge     short loc_180001801
0x1800017fd  xor     al, al
0x1800017ff  jmp     short loc_18000180B
0x180001801  mov     al, 1
0x180001803  jmp     short loc_18000180B
0x180001805  xor     al, al
0x180001807  jmp     short loc_18000180B
0x180001809  xor     al, al
0x18000180b  add     rsp, 18h
0x18000180f  retn
0x180001d68  push    rbp
0x180001d6a  mov     rbp, rdx
0x180001d6d  mov     rax, [rcx]
0x180001d70  xor     ecx, ecx
0x180001d72  cmp     dword ptr [rax], 0C0000005h
0x180001d78  setz    cl
0x180001d7b  mov     eax, ecx
0x180001d7d  pop     rbp
0x180001d7e  retn
```
