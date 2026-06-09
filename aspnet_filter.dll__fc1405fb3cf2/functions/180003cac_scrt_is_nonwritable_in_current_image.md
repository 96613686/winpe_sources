# __scrt_is_nonwritable_in_current_image

- ea: `0x180003cac`
- end: `0x180003d44`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800032e0`

## callees

- `0x180003cac`

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
0x180003cac  sub     rsp, 18h
0x180003cb0  mov     r8, rcx
0x180003cb3  mov     eax, 5A4Dh
0x180003cb8  cmp     cs:180000000h, ax
0x180003cbf  jnz     short loc_180003D39
0x180003cc1  movsxd  rcx, dword ptr cs:18000003Ch
0x180003cc8  lea     rdx, cs:180000000h
0x180003ccf  add     rcx, rdx
0x180003cd2  cmp     dword ptr [rcx], 4550h
0x180003cd8  jnz     short loc_180003D39
0x180003cda  mov     eax, 20Bh
0x180003cdf  cmp     [rcx+18h], ax
0x180003ce3  jnz     short loc_180003D39
0x180003ce5  sub     r8, rdx
0x180003ce8  movzx   eax, word ptr [rcx+14h]
0x180003cec  lea     rdx, [rcx+18h]
0x180003cf0  add     rdx, rax
0x180003cf3  movzx   eax, word ptr [rcx+6]
0x180003cf7  lea     rcx, [rax+rax*4]
0x180003cfb  lea     r9, [rdx+rcx*8]
0x180003cff  mov     [rsp+18h+var_18], rdx
0x180003d03  cmp     rdx, r9
0x180003d06  jz      short loc_180003D20
0x180003d08  mov     ecx, [rdx+0Ch]
0x180003d0b  cmp     r8, rcx
0x180003d0e  jb      short loc_180003D1A
0x180003d10  mov     eax, [rdx+8]
0x180003d13  add     eax, ecx
0x180003d15  cmp     r8, rax
0x180003d18  jb      short loc_180003D22
0x180003d1a  add     rdx, 28h ; '('
0x180003d1e  jmp     short loc_180003CFF
0x180003d20  xor     edx, edx
0x180003d22  test    rdx, rdx
0x180003d25  jnz     short loc_180003D2B
0x180003d27  xor     al, al
0x180003d29  jmp     short loc_180003D3F
0x180003d2b  cmp     dword ptr [rdx+24h], 0
0x180003d2f  jge     short loc_180003D35
0x180003d31  xor     al, al
0x180003d33  jmp     short loc_180003D3F
0x180003d35  mov     al, 1
0x180003d37  jmp     short loc_180003D3F
0x180003d39  xor     al, al
0x180003d3b  jmp     short loc_180003D3F
0x180003d3d  xor     al, al
0x180003d3f  add     rsp, 18h
0x180003d43  retn
0x180004450  push    rbp
0x180004452  mov     rbp, rdx
0x180004455  mov     rax, [rcx]
0x180004458  xor     ecx, ecx
0x18000445a  cmp     dword ptr [rax], 0C0000005h
0x180004460  setz    cl
0x180004463  mov     eax, ecx
0x180004465  pop     rbp
0x180004466  retn
```
