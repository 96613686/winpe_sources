# UpdateDstMBYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001d080`
- end: `0x18001d2b1`
- name: `?UpdateDstMBYUY2@@YAXPEAEPEBE11JJJ@Z`
- size: `561`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001da70`

## callees

- `0x18001d080`

## pseudocode

```c
void __fastcall UpdateDstMBYUY2(
        unsigned __int8 *a1,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        int a5,
        int a6,
        int a7)
{
  int v10; // r14d
  int v11; // r8d
  int v12; // edx
  int v13; // edx
  int v14; // edx
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // eax
  int v19; // edx
  int v20; // edx
  int v21; // ecx
  int v22; // eax

  v10 = 8;
  do
  {
    v11 = (*a3 | (*a4 << 16)) << 8;
    *(_DWORD *)a1 = v11 | *a2 | (a2[1] << 16);
    *(_DWORD *)&a1[a7] = v11 | a2[a5] | (a2[a5 + 1] << 16);
    v12 = (a3[1] | (a4[1] << 16)) << 8;
    *((_DWORD *)a1 + 1) = v12 | a2[2] | (a2[3] << 16);
    *(_DWORD *)&a1[a7 + 4] = v12 | a2[a5 + 2] | (a2[a5 + 3] << 16);
    v13 = (a3[2] | (a4[2] << 16)) << 8;
    *((_DWORD *)a1 + 2) = v13 | a2[4] | (a2[5] << 16);
    *(_DWORD *)&a1[a7 + 8] = v13 | a2[a5 + 4] | (a2[a5 + 5] << 16);
    v14 = (a3[3] | (a4[3] << 16)) << 8;
    *((_DWORD *)a1 + 3) = v14 | a2[6] | (a2[7] << 16);
    *(_DWORD *)&a1[a7 + 12] = v14 | a2[a5 + 6] | (a2[a5 + 7] << 16);
    v15 = (a3[4] | (a4[4] << 16)) << 8;
    *((_DWORD *)a1 + 4) = v15 | a2[8] | (a2[9] << 16);
    *(_DWORD *)&a1[a7 + 16] = v15 | a2[a5 + 8] | (a2[a5 + 9] << 16);
    v16 = (a3[5] | (a4[5] << 16)) << 8;
    *((_DWORD *)a1 + 5) = v16 | a2[10] | (a2[11] << 16);
    *(_DWORD *)&a1[a7 + 20] = v16 | a2[a5 + 10] | (a2[a5 + 11] << 16);
    v17 = (a3[6] | (a4[6] << 16)) << 8;
    *((_DWORD *)a1 + 6) = v17 | a2[12] | (a2[13] << 16);
    *(_DWORD *)&a1[a7 + 24] = v17 | a2[a5 + 12] | (a2[a5 + 13] << 16);
    v18 = a3[7];
    a3 += a6;
    v19 = a4[7];
    a4 += a6;
    v20 = (v18 | (v19 << 16)) << 8;
    *((_DWORD *)a1 + 7) = v20 | a2[14] | (a2[15] << 16);
    v21 = a2[a5 + 15];
    v22 = a2[a5 + 14];
    a2 += 2 * a5;
    *(_DWORD *)&a1[a7 + 28] = v20 | v22 | (v21 << 16);
    a1 += 2 * a7;
    --v10;
  }
  while ( v10 );
}

```

## disassembly

```asm
0x18001d080  push    rbx
0x18001d082  push    rbp
0x18001d083  push    rsi
0x18001d084  push    rdi
0x18001d085  push    r12
0x18001d087  push    r14
0x18001d089  push    r15
0x18001d08b  movsxd  rbx, [rsp+38h+arg_30]
0x18001d090  mov     rsi, r8
0x18001d093  movsxd  r10, [rsp+38h+arg_20]
0x18001d098  mov     r11, rdx
0x18001d09b  movsxd  rbp, [rsp+38h+arg_28]
0x18001d0a0  mov     rdi, rcx
0x18001d0a3  mov     r14d, 8
0x18001d0a9  lea     r15, [rbx+rbx]
0x18001d0ad  lea     r12, [r10+r10]
0x18001d0b1  movzx   eax, byte ptr [rsi]
0x18001d0b4  movzx   r8d, byte ptr [r9]
0x18001d0b8  movzx   ecx, byte ptr [r11+1]
0x18001d0bd  shl     ecx, 10h
0x18001d0c0  shl     r8d, 10h
0x18001d0c4  or      r8d, eax
0x18001d0c7  movzx   eax, byte ptr [r11]
0x18001d0cb  or      ecx, eax
0x18001d0cd  shl     r8d, 8
0x18001d0d1  or      ecx, r8d
0x18001d0d4  mov     [rdi], ecx
0x18001d0d6  movzx   eax, byte ptr [r10+r11]
0x18001d0db  movzx   ecx, byte ptr [r10+r11+1]
0x18001d0e1  shl     ecx, 10h
0x18001d0e4  or      ecx, eax
0x18001d0e6  or      ecx, r8d
0x18001d0e9  mov     [rbx+rdi], ecx
0x18001d0ec  movzx   eax, byte ptr [rsi+1]
0x18001d0f0  movzx   edx, byte ptr [r9+1]
0x18001d0f5  movzx   ecx, byte ptr [r11+3]
0x18001d0fa  shl     ecx, 10h
0x18001d0fd  shl     edx, 10h
0x18001d100  or      edx, eax
0x18001d102  movzx   eax, byte ptr [r11+2]
0x18001d107  or      ecx, eax
0x18001d109  shl     edx, 8
0x18001d10c  or      ecx, edx
0x18001d10e  mov     [rdi+4], ecx
0x18001d111  movzx   eax, byte ptr [r10+r11+2]
0x18001d117  movzx   ecx, byte ptr [r10+r11+3]
0x18001d11d  shl     ecx, 10h
0x18001d120  or      ecx, eax
0x18001d122  or      ecx, edx
0x18001d124  mov     [rbx+rdi+4], ecx
0x18001d128  movzx   eax, byte ptr [rsi+2]
0x18001d12c  movzx   edx, byte ptr [r9+2]
0x18001d131  movzx   ecx, byte ptr [r11+5]
0x18001d136  shl     ecx, 10h
0x18001d139  shl     edx, 10h
0x18001d13c  or      edx, eax
0x18001d13e  movzx   eax, byte ptr [r11+4]
0x18001d143  or      ecx, eax
0x18001d145  shl     edx, 8
0x18001d148  or      ecx, edx
0x18001d14a  mov     [rdi+8], ecx
0x18001d14d  movzx   eax, byte ptr [r10+r11+4]
0x18001d153  movzx   ecx, byte ptr [r10+r11+5]
0x18001d159  shl     ecx, 10h
0x18001d15c  or      ecx, eax
0x18001d15e  or      ecx, edx
0x18001d160  mov     [rbx+rdi+8], ecx
0x18001d164  movzx   eax, byte ptr [rsi+3]
0x18001d168  movzx   edx, byte ptr [r9+3]
0x18001d16d  movzx   ecx, byte ptr [r11+7]
0x18001d172  shl     ecx, 10h
0x18001d175  shl     edx, 10h
0x18001d178  or      edx, eax
0x18001d17a  movzx   eax, byte ptr [r11+6]
0x18001d17f  or      ecx, eax
0x18001d181  shl     edx, 8
0x18001d184  or      ecx, edx
0x18001d186  mov     [rdi+0Ch], ecx
0x18001d189  movzx   eax, byte ptr [r10+r11+6]
0x18001d18f  movzx   ecx, byte ptr [r10+r11+7]
0x18001d195  shl     ecx, 10h
0x18001d198  or      ecx, eax
0x18001d19a  or      ecx, edx
0x18001d19c  mov     [rbx+rdi+0Ch], ecx
0x18001d1a0  movzx   eax, byte ptr [rsi+4]
0x18001d1a4  movzx   edx, byte ptr [r9+4]
0x18001d1a9  movzx   ecx, byte ptr [r11+9]
0x18001d1ae  shl     ecx, 10h
0x18001d1b1  shl     edx, 10h
0x18001d1b4  or      edx, eax
0x18001d1b6  movzx   eax, byte ptr [r11+8]
0x18001d1bb  or      ecx, eax
0x18001d1bd  shl     edx, 8
0x18001d1c0  or      ecx, edx
0x18001d1c2  mov     [rdi+10h], ecx
0x18001d1c5  movzx   ecx, byte ptr [r10+r11+9]
0x18001d1cb  shl     ecx, 10h
0x18001d1ce  movzx   eax, byte ptr [r10+r11+8]
0x18001d1d4  or      ecx, eax
0x18001d1d6  or      ecx, edx
0x18001d1d8  mov     [rbx+rdi+10h], ecx
0x18001d1dc  movzx   eax, byte ptr [rsi+5]
0x18001d1e0  movzx   edx, byte ptr [r9+5]
0x18001d1e5  movzx   ecx, byte ptr [r11+0Bh]
0x18001d1ea  shl     ecx, 10h
0x18001d1ed  shl     edx, 10h
0x18001d1f0  or      edx, eax
0x18001d1f2  movzx   eax, byte ptr [r11+0Ah]
0x18001d1f7  or      ecx, eax
0x18001d1f9  shl     edx, 8
0x18001d1fc  or      ecx, edx
0x18001d1fe  mov     [rdi+14h], ecx
0x18001d201  movzx   eax, byte ptr [r10+r11+0Ah]
0x18001d207  movzx   ecx, byte ptr [r10+r11+0Bh]
0x18001d20d  shl     ecx, 10h
0x18001d210  or      ecx, eax
0x18001d212  or      ecx, edx
0x18001d214  mov     [rbx+rdi+14h], ecx
0x18001d218  movzx   eax, byte ptr [rsi+6]
0x18001d21c  movzx   edx, byte ptr [r9+6]
0x18001d221  movzx   ecx, byte ptr [r11+0Dh]
0x18001d226  shl     ecx, 10h
0x18001d229  shl     edx, 10h
0x18001d22c  or      edx, eax
0x18001d22e  movzx   eax, byte ptr [r11+0Ch]
0x18001d233  or      ecx, eax
0x18001d235  shl     edx, 8
0x18001d238  or      ecx, edx
0x18001d23a  mov     [rdi+18h], ecx
0x18001d23d  movzx   eax, byte ptr [r10+r11+0Ch]
0x18001d243  movzx   ecx, byte ptr [r10+r11+0Dh]
0x18001d249  shl     ecx, 10h
0x18001d24c  or      ecx, eax
0x18001d24e  or      ecx, edx
0x18001d250  mov     [rbx+rdi+18h], ecx
0x18001d254  movzx   eax, byte ptr [rsi+7]
0x18001d258  add     rsi, rbp
0x18001d25b  movzx   edx, byte ptr [r9+7]
0x18001d260  add     r9, rbp
0x18001d263  movzx   ecx, byte ptr [r11+0Fh]
0x18001d268  shl     ecx, 10h
0x18001d26b  shl     edx, 10h
0x18001d26e  or      edx, eax
0x18001d270  movzx   eax, byte ptr [r11+0Eh]
0x18001d275  or      ecx, eax
0x18001d277  shl     edx, 8
0x18001d27a  or      ecx, edx
0x18001d27c  mov     [rdi+1Ch], ecx
0x18001d27f  movzx   ecx, byte ptr [r10+r11+0Fh]
0x18001d285  movzx   eax, byte ptr [r10+r11+0Eh]
0x18001d28b  add     r11, r12
0x18001d28e  shl     ecx, 10h
0x18001d291  or      ecx, eax
0x18001d293  or      ecx, edx
0x18001d295  mov     [rbx+rdi+1Ch], ecx
0x18001d299  add     rdi, r15
0x18001d29c  sub     r14d, 1
0x18001d2a0  jnz     loc_18001D0B1
0x18001d2a6  pop     r15
0x18001d2a8  pop     r14
0x18001d2aa  pop     r12
0x18001d2ac  pop     rdi
0x18001d2ad  pop     rsi
0x18001d2ae  pop     rbp
0x18001d2af  pop     rbx
0x18001d2b0  retn
```
