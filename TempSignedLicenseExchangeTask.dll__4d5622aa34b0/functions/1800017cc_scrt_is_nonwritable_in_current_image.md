# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017cc`
- end: `0x180001864`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800010e8`

## callees

- `0x1800017cc`

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
0x1800017cc  sub     rsp, 18h
0x1800017d0  mov     r8, rcx
0x1800017d3  mov     eax, 5A4Dh
0x1800017d8  cmp     cs:180000000h, ax
0x1800017df  jnz     short loc_180001859
0x1800017e1  movsxd  rcx, dword ptr cs:18000003Ch
0x1800017e8  lea     rdx, cs:180000000h
0x1800017ef  add     rcx, rdx
0x1800017f2  cmp     dword ptr [rcx], 4550h
0x1800017f8  jnz     short loc_180001859
0x1800017fa  mov     eax, 20Bh
0x1800017ff  cmp     [rcx+18h], ax
0x180001803  jnz     short loc_180001859
0x180001805  sub     r8, rdx
0x180001808  movzx   edx, word ptr [rcx+14h]
0x18000180c  add     rdx, 18h
0x180001810  add     rdx, rcx
0x180001813  movzx   eax, word ptr [rcx+6]
0x180001817  lea     rcx, [rax+rax*4]
0x18000181b  lea     r9, [rdx+rcx*8]
0x18000181f  mov     [rsp+18h+var_18], rdx
0x180001823  cmp     rdx, r9
0x180001826  jz      short loc_180001840
0x180001828  mov     ecx, [rdx+0Ch]
0x18000182b  cmp     r8, rcx
0x18000182e  jb      short loc_18000183A
0x180001830  mov     eax, [rdx+8]
0x180001833  add     eax, ecx
0x180001835  cmp     r8, rax
0x180001838  jb      short loc_180001842
0x18000183a  add     rdx, 28h ; '('
0x18000183e  jmp     short loc_18000181F
0x180001840  xor     edx, edx
0x180001842  test    rdx, rdx
0x180001845  jnz     short loc_18000184B
0x180001847  xor     al, al
0x180001849  jmp     short loc_18000185F
0x18000184b  cmp     dword ptr [rdx+24h], 0
0x18000184f  jge     short loc_180001855
0x180001851  xor     al, al
0x180001853  jmp     short loc_18000185F
0x180001855  mov     al, 1
0x180001857  jmp     short loc_18000185F
0x180001859  xor     al, al
0x18000185b  jmp     short loc_18000185F
0x18000185d  xor     al, al
0x18000185f  add     rsp, 18h
0x180001863  retn
0x18000cbb8  push    rbp
0x18000cbba  mov     rbp, rdx
0x18000cbbd  mov     rax, [rcx]
0x18000cbc0  xor     ecx, ecx
0x18000cbc2  cmp     dword ptr [rax], 0C0000005h
0x18000cbc8  setz    cl
0x18000cbcb  mov     eax, ecx
0x18000cbcd  pop     rbp
0x18000cbce  retn
```
