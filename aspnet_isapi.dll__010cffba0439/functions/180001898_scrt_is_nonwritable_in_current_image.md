# __scrt_is_nonwritable_in_current_image

- ea: `0x180001898`
- end: `0x180001930`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011a0`

## callees

- `0x180001898`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  unsigned __int64 v1; // r8
  _DWORD *v2; // rdx
  _DWORD *v3; // r9
  unsigned __int64 v4; // rcx

  if ( MEMORY[0x180000000] != 23117
    || *(_DWORD *)(0x180000000LL + MEMORY[0x18000003C]) != 17744
    || *(_WORD *)(0x180000018LL + MEMORY[0x18000003C]) != 523 )
  {
    return 0;
  }
  v1 = a1 - 0x180000000LL;
  v2 = (_DWORD *)(*(unsigned __int16 *)(0x180000014LL + MEMORY[0x18000003C]) + 0x180000018LL + MEMORY[0x18000003C]);
  v3 = &v2[10 * *(unsigned __int16 *)(0x180000006LL + MEMORY[0x18000003C])];
  while ( v2 != v3 )
  {
    v4 = (unsigned int)v2[3];
    if ( v1 >= v4 && v1 < (unsigned int)(v4 + v2[2]) )
      return v2 && v2[9] >= 0;
    v2 += 10;
  }
  v2 = 0;
  return v2 && v2[9] >= 0;
}

```

## disassembly

```asm
0x180001898  sub     rsp, 18h
0x18000189c  mov     r8, rcx
0x18000189f  mov     eax, 5A4Dh
0x1800018a4  cmp     cs:180000000h, ax
0x1800018ab  jnz     short loc_180001925
0x1800018ad  movsxd  rcx, dword ptr cs:18000003Ch
0x1800018b4  lea     rdx, cs:180000000h
0x1800018bb  add     rcx, rdx
0x1800018be  cmp     dword ptr [rcx], 4550h
0x1800018c4  jnz     short loc_180001925
0x1800018c6  mov     eax, 20Bh
0x1800018cb  cmp     [rcx+18h], ax
0x1800018cf  jnz     short loc_180001925
0x1800018d1  sub     r8, rdx
0x1800018d4  movzx   eax, word ptr [rcx+14h]
0x1800018d8  lea     rdx, [rcx+18h]
0x1800018dc  add     rdx, rax
0x1800018df  movzx   eax, word ptr [rcx+6]
0x1800018e3  lea     rcx, [rax+rax*4]
0x1800018e7  lea     r9, [rdx+rcx*8]
0x1800018eb  mov     [rsp+18h+var_18], rdx
0x1800018ef  cmp     rdx, r9
0x1800018f2  jz      short loc_18000190C
0x1800018f4  mov     ecx, [rdx+0Ch]
0x1800018f7  cmp     r8, rcx
0x1800018fa  jb      short loc_180001906
0x1800018fc  mov     eax, [rdx+8]
0x1800018ff  add     eax, ecx
0x180001901  cmp     r8, rax
0x180001904  jb      short loc_18000190E
0x180001906  add     rdx, 28h ; '('
0x18000190a  jmp     short loc_1800018EB
0x18000190c  xor     edx, edx
0x18000190e  test    rdx, rdx
0x180001911  jnz     short loc_180001917
0x180001913  xor     al, al
0x180001915  jmp     short loc_18000192B
0x180001917  cmp     dword ptr [rdx+24h], 0
0x18000191b  jge     short loc_180001921
0x18000191d  xor     al, al
0x18000191f  jmp     short loc_18000192B
0x180001921  mov     al, 1
0x180001923  jmp     short loc_18000192B
0x180001925  xor     al, al
0x180001927  jmp     short loc_18000192B
0x180001929  xor     al, al
0x18000192b  add     rsp, 18h
0x18000192f  retn
0x180001fa0  push    rbp
0x180001fa2  mov     rbp, rdx
0x180001fa5  mov     rax, [rcx]
0x180001fa8  xor     ecx, ecx
0x180001faa  cmp     dword ptr [rax], 0C0000005h
0x180001fb0  setz    cl
0x180001fb3  mov     eax, ecx
0x180001fb5  pop     rbp
0x180001fb6  retn
```
