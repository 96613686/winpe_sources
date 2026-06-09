# __scrt_is_nonwritable_in_current_image

- ea: `0x1800019e8`
- end: `0x180001a80`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001408`

## callees

- `0x1800019e8`

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
0x1800019e8  sub     rsp, 18h
0x1800019ec  mov     r8, rcx
0x1800019ef  mov     eax, 5A4Dh
0x1800019f4  cmp     cs:180000000h, ax
0x1800019fb  jnz     short loc_180001A75
0x1800019fd  movsxd  rcx, dword ptr cs:18000003Ch
0x180001a04  lea     rdx, cs:180000000h
0x180001a0b  add     rcx, rdx
0x180001a0e  cmp     dword ptr [rcx], 4550h
0x180001a14  jnz     short loc_180001A75
0x180001a16  mov     eax, 20Bh
0x180001a1b  cmp     [rcx+18h], ax
0x180001a1f  jnz     short loc_180001A75
0x180001a21  sub     r8, rdx
0x180001a24  movzx   edx, word ptr [rcx+14h]
0x180001a28  add     rdx, 18h
0x180001a2c  add     rdx, rcx
0x180001a2f  movzx   eax, word ptr [rcx+6]
0x180001a33  lea     rcx, [rax+rax*4]
0x180001a37  lea     r9, [rdx+rcx*8]
0x180001a3b  mov     [rsp+18h+var_18], rdx
0x180001a3f  cmp     rdx, r9
0x180001a42  jz      short loc_180001A5C
0x180001a44  mov     ecx, [rdx+0Ch]
0x180001a47  cmp     r8, rcx
0x180001a4a  jb      short loc_180001A56
0x180001a4c  mov     eax, [rdx+8]
0x180001a4f  add     eax, ecx
0x180001a51  cmp     r8, rax
0x180001a54  jb      short loc_180001A5E
0x180001a56  add     rdx, 28h ; '('
0x180001a5a  jmp     short loc_180001A3B
0x180001a5c  xor     edx, edx
0x180001a5e  test    rdx, rdx
0x180001a61  jnz     short loc_180001A67
0x180001a63  xor     al, al
0x180001a65  jmp     short loc_180001A7B
0x180001a67  cmp     dword ptr [rdx+24h], 0
0x180001a6b  jge     short loc_180001A71
0x180001a6d  xor     al, al
0x180001a6f  jmp     short loc_180001A7B
0x180001a71  mov     al, 1
0x180001a73  jmp     short loc_180001A7B
0x180001a75  xor     al, al
0x180001a77  jmp     short loc_180001A7B
0x180001a79  xor     al, al
0x180001a7b  add     rsp, 18h
0x180001a7f  retn
0x180003c38  push    rbp
0x180003c3a  mov     rbp, rdx
0x180003c3d  mov     rax, [rcx]
0x180003c40  xor     ecx, ecx
0x180003c42  cmp     dword ptr [rax], 0C0000005h
0x180003c48  setz    cl
0x180003c4b  mov     eax, ecx
0x180003c4d  pop     rbp
0x180003c4e  retn
```
