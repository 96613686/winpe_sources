# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017e8`
- end: `0x180001880`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001148`

## callees

- `0x1800017e8`

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
0x1800017e8  sub     rsp, 18h
0x1800017ec  mov     r8, rcx
0x1800017ef  mov     eax, 5A4Dh
0x1800017f4  cmp     cs:180000000h, ax
0x1800017fb  jnz     short loc_180001875
0x1800017fd  movsxd  rcx, dword ptr cs:18000003Ch
0x180001804  lea     rdx, cs:180000000h
0x18000180b  add     rcx, rdx
0x18000180e  cmp     dword ptr [rcx], 4550h
0x180001814  jnz     short loc_180001875
0x180001816  mov     eax, 20Bh
0x18000181b  cmp     [rcx+18h], ax
0x18000181f  jnz     short loc_180001875
0x180001821  sub     r8, rdx
0x180001824  movzx   edx, word ptr [rcx+14h]
0x180001828  add     rdx, 18h
0x18000182c  add     rdx, rcx
0x18000182f  movzx   eax, word ptr [rcx+6]
0x180001833  lea     rcx, [rax+rax*4]
0x180001837  lea     r9, [rdx+rcx*8]
0x18000183b  mov     [rsp+18h+var_18], rdx
0x18000183f  cmp     rdx, r9
0x180001842  jz      short loc_18000185C
0x180001844  mov     ecx, [rdx+0Ch]
0x180001847  cmp     r8, rcx
0x18000184a  jb      short loc_180001856
0x18000184c  mov     eax, [rdx+8]
0x18000184f  add     eax, ecx
0x180001851  cmp     r8, rax
0x180001854  jb      short loc_18000185E
0x180001856  add     rdx, 28h ; '('
0x18000185a  jmp     short loc_18000183B
0x18000185c  xor     edx, edx
0x18000185e  test    rdx, rdx
0x180001861  jnz     short loc_180001867
0x180001863  xor     al, al
0x180001865  jmp     short loc_18000187B
0x180001867  cmp     dword ptr [rdx+24h], 0
0x18000186b  jge     short loc_180001871
0x18000186d  xor     al, al
0x18000186f  jmp     short loc_18000187B
0x180001871  mov     al, 1
0x180001873  jmp     short loc_18000187B
0x180001875  xor     al, al
0x180001877  jmp     short loc_18000187B
0x180001879  xor     al, al
0x18000187b  add     rsp, 18h
0x18000187f  retn
0x1800031d8  push    rbp
0x1800031da  mov     rbp, rdx
0x1800031dd  mov     rax, [rcx]
0x1800031e0  xor     ecx, ecx
0x1800031e2  cmp     dword ptr [rax], 0C0000005h
0x1800031e8  setz    cl
0x1800031eb  mov     eax, ecx
0x1800031ed  pop     rbp
0x1800031ee  retn
```
