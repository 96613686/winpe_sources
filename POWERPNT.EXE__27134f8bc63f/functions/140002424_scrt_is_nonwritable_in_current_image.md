# __scrt_is_nonwritable_in_current_image

- ea: `0x140002424`
- end: `0x1400024bc`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ac0`

## callees

- `0x140002424`

## pseudocode

```c
bool __fastcall _scrt_is_nonwritable_in_current_image(__int64 a1)
{
  _DWORD *v2; // rcx
  unsigned __int64 v3; // r8
  _DWORD *v4; // rdx
  _DWORD *v5; // r9
  unsigned __int64 v6; // rcx

  if ( LOWORD(_NULL_IMPORT_DESCRIPTOR.unused) != 23117 )
    return 0;
  v2 = (int *)((char *)&_NULL_IMPORT_DESCRIPTOR.unused + (int)off_14000003C);
  if ( *v2 != 17744 || *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) != 523 )
    return 0;
  v3 = a1 - (_QWORD)&_NULL_IMPORT_DESCRIPTOR;
  v4 = (_DWORD *)((char *)v2 + *(unsigned __int16 *)((char *)&word_140000014 + (int)off_14000003C) + 24);
  v5 = &v4[10 * *(unsigned __int16 *)((char *)&word_140000006 + (int)off_14000003C)];
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
0x140002424  sub     rsp, 18h
0x140002428  mov     r8, rcx
0x14000242b  mov     eax, 5A4Dh
0x140002430  cmp     word ptr cs:__NULL_IMPORT_DESCRIPTOR.unused, ax
0x140002437  jnz     short loc_1400024B1
0x140002439  movsxd  rcx, cs:off_14000003C
0x140002440  lea     rdx, __NULL_IMPORT_DESCRIPTOR
0x140002447  add     rcx, rdx
0x14000244a  cmp     dword ptr [rcx], 4550h
0x140002450  jnz     short loc_1400024B1
0x140002452  mov     eax, 20Bh
0x140002457  cmp     [rcx+18h], ax
0x14000245b  jnz     short loc_1400024B1
0x14000245d  sub     r8, rdx
0x140002460  movzx   edx, word ptr [rcx+14h]
0x140002464  add     rdx, 18h
0x140002468  add     rdx, rcx
0x14000246b  movzx   eax, word ptr [rcx+6]
0x14000246f  lea     rcx, [rax+rax*4]
0x140002473  lea     r9, [rdx+rcx*8]
0x140002477  mov     [rsp+18h+var_18], rdx
0x14000247b  cmp     rdx, r9
0x14000247e  jz      short loc_140002498
0x140002480  mov     ecx, [rdx+0Ch]
0x140002483  cmp     r8, rcx
0x140002486  jb      short loc_140002492
0x140002488  mov     eax, [rdx+8]
0x14000248b  add     eax, ecx
0x14000248d  cmp     r8, rax
0x140002490  jb      short loc_14000249A
0x140002492  add     rdx, 28h ; '('
0x140002496  jmp     short loc_140002477
0x140002498  xor     edx, edx
0x14000249a  test    rdx, rdx
0x14000249d  jnz     short loc_1400024A3
0x14000249f  xor     al, al
0x1400024a1  jmp     short loc_1400024B7
0x1400024a3  cmp     dword ptr [rdx+24h], 0
0x1400024a7  jge     short loc_1400024AD
0x1400024a9  xor     al, al
0x1400024ab  jmp     short loc_1400024B7
0x1400024ad  mov     al, 1
0x1400024af  jmp     short loc_1400024B7
0x1400024b1  xor     al, al
0x1400024b3  jmp     short loc_1400024B7
0x1400024b5  xor     al, al
0x1400024b7  add     rsp, 18h
0x1400024bb  retn
0x140002a18  push    rbp
0x140002a1a  mov     rbp, rdx
0x140002a1d  mov     rax, [rcx]
0x140002a20  xor     ecx, ecx
0x140002a22  cmp     dword ptr [rax], 0C0000005h
0x140002a28  setz    cl
0x140002a2b  mov     eax, ecx
0x140002a2d  pop     rbp
0x140002a2e  retn
```
