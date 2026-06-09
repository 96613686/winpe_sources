# __scrt_is_nonwritable_in_current_image

- ea: `0x140001498`
- end: `0x140001530`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001180`

## callees

- `0x140001498`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( LOWORD(MEMORY[0x140000000].unused) != 23117 )
    return 0;
  v2 = (_DWORD *)(0x140000000LL + MEMORY[0x14000003C]);
  if ( *v2 != 17744 || *(_WORD *)(0x140000018LL + MEMORY[0x14000003C]) != 523 )
    return 0;
  v3 = a1 - 0x140000000LL;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)(0x140000014LL + MEMORY[0x14000003C]) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)(0x140000006LL + MEMORY[0x14000003C])];
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
0x140001498  sub     rsp, 18h
0x14000149c  mov     r8, rcx
0x14000149f  mov     eax, 5A4Dh
0x1400014a4  cmp     cs:140000000h, ax
0x1400014ab  jnz     short loc_140001525
0x1400014ad  movsxd  rcx, dword ptr cs:14000003Ch
0x1400014b4  lea     rdx, cs:140000000h
0x1400014bb  add     rcx, rdx
0x1400014be  cmp     dword ptr [rcx], 4550h
0x1400014c4  jnz     short loc_140001525
0x1400014c6  mov     eax, 20Bh
0x1400014cb  cmp     [rcx+18h], ax
0x1400014cf  jnz     short loc_140001525
0x1400014d1  sub     r8, rdx
0x1400014d4  movzx   edx, word ptr [rcx+14h]
0x1400014d8  add     rdx, 18h
0x1400014dc  add     rdx, rcx
0x1400014df  movzx   eax, word ptr [rcx+6]
0x1400014e3  lea     rcx, [rax+rax*4]
0x1400014e7  lea     r9, [rdx+rcx*8]
0x1400014eb  mov     [rsp+18h+var_18], rdx
0x1400014ef  cmp     rdx, r9
0x1400014f2  jz      short loc_14000150C
0x1400014f4  mov     ecx, [rdx+0Ch]
0x1400014f7  cmp     r8, rcx
0x1400014fa  jb      short loc_140001506
0x1400014fc  mov     eax, [rdx+8]
0x1400014ff  add     eax, ecx
0x140001501  cmp     r8, rax
0x140001504  jb      short loc_14000150E
0x140001506  add     rdx, 28h ; '('
0x14000150a  jmp     short loc_1400014EB
0x14000150c  xor     edx, edx
0x14000150e  test    rdx, rdx
0x140001511  jnz     short loc_140001517
0x140001513  xor     al, al
0x140001515  jmp     short loc_14000152B
0x140001517  cmp     dword ptr [rdx+24h], 0
0x14000151b  jge     short loc_140001521
0x14000151d  xor     al, al
0x14000151f  jmp     short loc_14000152B
0x140001521  mov     al, 1
0x140001523  jmp     short loc_14000152B
0x140001525  xor     al, al
0x140001527  jmp     short loc_14000152B
0x140001529  xor     al, al
0x14000152b  add     rsp, 18h
0x14000152f  retn
0x140002831  push    rbp
0x140002833  mov     rbp, rdx
0x140002836  mov     rax, [rcx]
0x140002839  xor     ecx, ecx
0x14000283b  cmp     dword ptr [rax], 0C0000005h
0x140002841  setz    cl
0x140002844  mov     eax, ecx
0x140002846  pop     rbp
0x140002847  retn
```
