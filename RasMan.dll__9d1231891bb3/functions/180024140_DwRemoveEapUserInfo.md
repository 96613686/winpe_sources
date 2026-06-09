# DwRemoveEapUserInfo

- ea: `0x180024140`
- end: `0x180024205`
- name: `DwRemoveEapUserInfo`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18002420c`
- `0x180024358`

## callees

- `0x180024140`
- `0x180024328`
- `0x1800263c2`

## pseudocode

```c
__int64 __fastcall DwRemoveEapUserInfo(_QWORD *a1, const BYTE *a2, unsigned int *a3, HKEY a4, int a5, int a6)
{
  unsigned int v6; // r11d
  unsigned int v8; // esi
  __int64 v9; // r10
  const BYTE *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  DWORD v16; // edi

  v6 = *a3;
  v8 = 0;
  v9 = 0;
  v13 = a2;
  if ( *a3 )
  {
    do
    {
      v14 = *a1 - *((_QWORD *)v13 + 1);
      if ( *a1 == *((_QWORD *)v13 + 1) )
        v14 = a1[1] - *((_QWORD *)v13 + 2);
      if ( !v14 && a6 == *((_DWORD *)v13 + 1) )
        break;
      v9 = ((*((_DWORD *)v13 + 6) + 39) & 0xFFFFFFF8) + (unsigned int)v9;
      v13 = &a2[(unsigned int)v9];
    }
    while ( (unsigned int)v9 < v6 );
    if ( (unsigned int)v9 < v6 )
    {
      v15 = *((unsigned int *)v13 + 6);
      v16 = v6 - ((v15 + 39) & 0xFFFFFFF8);
      memmove_0(
        (void *)&a2[v9],
        &a2[((v15 + 39) & 0xFFFFFFFFFFFFFFF8uLL) + v9],
        v6 - (unsigned int)v9 - ((v15 + 39) & 0xFFFFFFFFFFFFFFF8uLL));
      if ( a5 )
        return (unsigned int)DwSetEapInfo(a4, a2, v16);
      else
        *a3 = v16;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180024140  push    rbx
0x180024142  push    rbp
0x180024143  push    rsi
0x180024144  push    rdi
0x180024145  push    r14
0x180024147  sub     rsp, 20h
0x18002414b  mov     r11d, [r8]
0x18002414e  mov     rbx, rdx
0x180024151  xor     esi, esi
0x180024153  xor     r10d, r10d
0x180024156  mov     rbp, r9
0x180024159  mov     r14, r8
0x18002415c  mov     rdx, rcx
0x18002415f  mov     rax, rbx
0x180024162  test    r11d, r11d
0x180024165  jz      loc_1800241F8
0x18002416b  mov     r8d, [rsp+48h+arg_28]
0x180024170  mov     r9d, 0FFFFFFF8h
0x180024176  mov     rcx, [rdx]
0x180024179  sub     rcx, [rax+8]
0x18002417d  jnz     short loc_180024187
0x18002417f  mov     rcx, [rdx+8]
0x180024183  sub     rcx, [rax+10h]
0x180024187  test    rcx, rcx
0x18002418a  jnz     short loc_180024192
0x18002418c  cmp     r8d, [rax+4]
0x180024190  jz      short loc_1800241A9
0x180024192  mov     eax, [rax+18h]
0x180024195  add     eax, 27h ; '''
0x180024198  and     eax, r9d
0x18002419b  add     r10d, eax
0x18002419e  mov     eax, r10d
0x1800241a1  add     rax, rbx
0x1800241a4  cmp     r10d, r11d
0x1800241a7  jb      short loc_180024176
0x1800241a9  cmp     r10d, r11d
0x1800241ac  jnb     short loc_1800241F8
0x1800241ae  mov     ecx, [rax+18h]
0x1800241b1  mov     edi, r11d
0x1800241b4  sub     r11d, r10d
0x1800241b7  mov     r8d, r11d
0x1800241ba  lea     eax, [rcx+27h]
0x1800241bd  add     rcx, 27h ; '''
0x1800241c1  and     rcx, 0FFFFFFFFFFFFFFF8h
0x1800241c5  and     eax, r9d
0x1800241c8  sub     r8, rcx; Size
0x1800241cb  sub     edi, eax
0x1800241cd  lea     rdx, [rcx+r10]
0x1800241d1  add     rdx, rbx; Src
0x1800241d4  lea     rcx, [r10+rbx]; void *
0x1800241d8  call    memmove_0
0x1800241dd  cmp     [rsp+48h+arg_20], esi
0x1800241e1  jz      short loc_1800241F5
0x1800241e3  mov     r8d, edi
0x1800241e6  mov     rdx, rbx
0x1800241e9  mov     rcx, rbp
0x1800241ec  call    DwSetEapInfo
0x1800241f1  mov     esi, eax
0x1800241f3  jmp     short loc_1800241F8
0x1800241f5  mov     [r14], edi
0x1800241f8  mov     eax, esi
0x1800241fa  add     rsp, 20h
0x1800241fe  pop     r14
0x180024200  pop     rdi
0x180024201  pop     rsi
0x180024202  pop     rbp
0x180024203  pop     rbx
0x180024204  retn
```
