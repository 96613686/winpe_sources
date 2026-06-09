# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017fc`
- end: `0x180001894`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800017fc`

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
0x1800017fc  sub     rsp, 18h
0x180001800  mov     r8, rcx
0x180001803  mov     eax, 5A4Dh
0x180001808  cmp     cs:180000000h, ax
0x18000180f  jnz     short loc_180001889
0x180001811  movsxd  rcx, dword ptr cs:18000003Ch
0x180001818  lea     rdx, cs:180000000h
0x18000181f  add     rcx, rdx
0x180001822  cmp     dword ptr [rcx], 4550h
0x180001828  jnz     short loc_180001889
0x18000182a  mov     eax, 20Bh
0x18000182f  cmp     [rcx+18h], ax
0x180001833  jnz     short loc_180001889
0x180001835  sub     r8, rdx
0x180001838  movzx   edx, word ptr [rcx+14h]
0x18000183c  add     rdx, 18h
0x180001840  add     rdx, rcx
0x180001843  movzx   eax, word ptr [rcx+6]
0x180001847  lea     rcx, [rax+rax*4]
0x18000184b  lea     r9, [rdx+rcx*8]
0x18000184f  mov     [rsp+18h+var_18], rdx
0x180001853  cmp     rdx, r9
0x180001856  jz      short loc_180001870
0x180001858  mov     ecx, [rdx+0Ch]
0x18000185b  cmp     r8, rcx
0x18000185e  jb      short loc_18000186A
0x180001860  mov     eax, [rdx+8]
0x180001863  add     eax, ecx
0x180001865  cmp     r8, rax
0x180001868  jb      short loc_180001872
0x18000186a  add     rdx, 28h ; '('
0x18000186e  jmp     short loc_18000184F
0x180001870  xor     edx, edx
0x180001872  test    rdx, rdx
0x180001875  jnz     short loc_18000187B
0x180001877  xor     al, al
0x180001879  jmp     short loc_18000188F
0x18000187b  cmp     dword ptr [rdx+24h], 0
0x18000187f  jge     short loc_180001885
0x180001881  xor     al, al
0x180001883  jmp     short loc_18000188F
0x180001885  mov     al, 1
0x180001887  jmp     short loc_18000188F
0x180001889  xor     al, al
0x18000188b  jmp     short loc_18000188F
0x18000188d  xor     al, al
0x18000188f  add     rsp, 18h
0x180001893  retn
0x180002d1a  push    rbp
0x180002d1c  mov     rbp, rdx
0x180002d1f  mov     rax, [rcx]
0x180002d22  xor     ecx, ecx
0x180002d24  cmp     dword ptr [rax], 0C0000005h
0x180002d2a  setz    cl
0x180002d2d  mov     eax, ecx
0x180002d2f  pop     rbp
0x180002d30  retn
```
