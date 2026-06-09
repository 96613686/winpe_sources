# __scrt_is_nonwritable_in_current_image

- ea: `0x1800017f4`
- end: `0x18000188c`
- name: `__scrt_is_nonwritable_in_current_image`
- size: `152`
- prototype: `bool __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001128`

## callees

- `0x1800017f4`

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
0x1800017f4  sub     rsp, 18h
0x1800017f8  mov     r8, rcx
0x1800017fb  mov     eax, 5A4Dh
0x180001800  cmp     cs:180000000h, ax
0x180001807  jnz     short loc_180001881
0x180001809  movsxd  rcx, dword ptr cs:18000003Ch
0x180001810  lea     rdx, cs:180000000h
0x180001817  add     rcx, rdx
0x18000181a  cmp     dword ptr [rcx], 4550h
0x180001820  jnz     short loc_180001881
0x180001822  mov     eax, 20Bh
0x180001827  cmp     [rcx+18h], ax
0x18000182b  jnz     short loc_180001881
0x18000182d  sub     r8, rdx
0x180001830  movzx   edx, word ptr [rcx+14h]
0x180001834  add     rdx, 18h
0x180001838  add     rdx, rcx
0x18000183b  movzx   eax, word ptr [rcx+6]
0x18000183f  lea     rcx, [rax+rax*4]
0x180001843  lea     r9, [rdx+rcx*8]
0x180001847  mov     [rsp+18h+var_18], rdx
0x18000184b  cmp     rdx, r9
0x18000184e  jz      short loc_180001868
0x180001850  mov     ecx, [rdx+0Ch]
0x180001853  cmp     r8, rcx
0x180001856  jb      short loc_180001862
0x180001858  mov     eax, [rdx+8]
0x18000185b  add     eax, ecx
0x18000185d  cmp     r8, rax
0x180001860  jb      short loc_18000186A
0x180001862  add     rdx, 28h ; '('
0x180001866  jmp     short loc_180001847
0x180001868  xor     edx, edx
0x18000186a  test    rdx, rdx
0x18000186d  jnz     short loc_180001873
0x18000186f  xor     al, al
0x180001871  jmp     short loc_180001887
0x180001873  cmp     dword ptr [rdx+24h], 0
0x180001877  jge     short loc_18000187D
0x180001879  xor     al, al
0x18000187b  jmp     short loc_180001887
0x18000187d  mov     al, 1
0x18000187f  jmp     short loc_180001887
0x180001881  xor     al, al
0x180001883  jmp     short loc_180001887
0x180001885  xor     al, al
0x180001887  add     rsp, 18h
0x18000188b  retn
0x1800021c8  push    rbp
0x1800021ca  mov     rbp, rdx
0x1800021cd  mov     rax, [rcx]
0x1800021d0  xor     ecx, ecx
0x1800021d2  cmp     dword ptr [rax], 0C0000005h
0x1800021d8  setz    cl
0x1800021db  mov     eax, ecx
0x1800021dd  pop     rbp
0x1800021de  retn
```
