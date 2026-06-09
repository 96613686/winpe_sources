# UpdateDstMBYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001d140`
- end: `0x18001d371`
- name: `?UpdateDstMBYUY2@@YAXPEAEPEBE11JJJ@Z`
- size: `561`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001db30`

## callees

- `0x18001d140`

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
0x18001d140  push    rbx
0x18001d142  push    rbp
0x18001d143  push    rsi
0x18001d144  push    rdi
0x18001d145  push    r12
0x18001d147  push    r14
0x18001d149  push    r15
0x18001d14b  movsxd  rbx, [rsp+38h+arg_30]
0x18001d150  mov     rsi, r8
0x18001d153  movsxd  r10, [rsp+38h+arg_20]
0x18001d158  mov     r11, rdx
0x18001d15b  movsxd  rbp, [rsp+38h+arg_28]
0x18001d160  mov     rdi, rcx
0x18001d163  mov     r14d, 8
0x18001d169  lea     r15, [rbx+rbx]
0x18001d16d  lea     r12, [r10+r10]
0x18001d171  movzx   eax, byte ptr [rsi]
0x18001d174  movzx   r8d, byte ptr [r9]
0x18001d178  movzx   ecx, byte ptr [r11+1]
0x18001d17d  shl     ecx, 10h
0x18001d180  shl     r8d, 10h
0x18001d184  or      r8d, eax
0x18001d187  movzx   eax, byte ptr [r11]
0x18001d18b  or      ecx, eax
0x18001d18d  shl     r8d, 8
0x18001d191  or      ecx, r8d
0x18001d194  mov     [rdi], ecx
0x18001d196  movzx   eax, byte ptr [r10+r11]
0x18001d19b  movzx   ecx, byte ptr [r10+r11+1]
0x18001d1a1  shl     ecx, 10h
0x18001d1a4  or      ecx, eax
0x18001d1a6  or      ecx, r8d
0x18001d1a9  mov     [rbx+rdi], ecx
0x18001d1ac  movzx   eax, byte ptr [rsi+1]
0x18001d1b0  movzx   edx, byte ptr [r9+1]
0x18001d1b5  movzx   ecx, byte ptr [r11+3]
0x18001d1ba  shl     ecx, 10h
0x18001d1bd  shl     edx, 10h
0x18001d1c0  or      edx, eax
0x18001d1c2  movzx   eax, byte ptr [r11+2]
0x18001d1c7  or      ecx, eax
0x18001d1c9  shl     edx, 8
0x18001d1cc  or      ecx, edx
0x18001d1ce  mov     [rdi+4], ecx
0x18001d1d1  movzx   eax, byte ptr [r10+r11+2]
0x18001d1d7  movzx   ecx, byte ptr [r10+r11+3]
0x18001d1dd  shl     ecx, 10h
0x18001d1e0  or      ecx, eax
0x18001d1e2  or      ecx, edx
0x18001d1e4  mov     [rbx+rdi+4], ecx
0x18001d1e8  movzx   eax, byte ptr [rsi+2]
0x18001d1ec  movzx   edx, byte ptr [r9+2]
0x18001d1f1  movzx   ecx, byte ptr [r11+5]
0x18001d1f6  shl     ecx, 10h
0x18001d1f9  shl     edx, 10h
0x18001d1fc  or      edx, eax
0x18001d1fe  movzx   eax, byte ptr [r11+4]
0x18001d203  or      ecx, eax
0x18001d205  shl     edx, 8
0x18001d208  or      ecx, edx
0x18001d20a  mov     [rdi+8], ecx
0x18001d20d  movzx   eax, byte ptr [r10+r11+4]
0x18001d213  movzx   ecx, byte ptr [r10+r11+5]
0x18001d219  shl     ecx, 10h
0x18001d21c  or      ecx, eax
0x18001d21e  or      ecx, edx
0x18001d220  mov     [rbx+rdi+8], ecx
0x18001d224  movzx   eax, byte ptr [rsi+3]
0x18001d228  movzx   edx, byte ptr [r9+3]
0x18001d22d  movzx   ecx, byte ptr [r11+7]
0x18001d232  shl     ecx, 10h
0x18001d235  shl     edx, 10h
0x18001d238  or      edx, eax
0x18001d23a  movzx   eax, byte ptr [r11+6]
0x18001d23f  or      ecx, eax
0x18001d241  shl     edx, 8
0x18001d244  or      ecx, edx
0x18001d246  mov     [rdi+0Ch], ecx
0x18001d249  movzx   eax, byte ptr [r10+r11+6]
0x18001d24f  movzx   ecx, byte ptr [r10+r11+7]
0x18001d255  shl     ecx, 10h
0x18001d258  or      ecx, eax
0x18001d25a  or      ecx, edx
0x18001d25c  mov     [rbx+rdi+0Ch], ecx
0x18001d260  movzx   eax, byte ptr [rsi+4]
0x18001d264  movzx   edx, byte ptr [r9+4]
0x18001d269  movzx   ecx, byte ptr [r11+9]
0x18001d26e  shl     ecx, 10h
0x18001d271  shl     edx, 10h
0x18001d274  or      edx, eax
0x18001d276  movzx   eax, byte ptr [r11+8]
0x18001d27b  or      ecx, eax
0x18001d27d  shl     edx, 8
0x18001d280  or      ecx, edx
0x18001d282  mov     [rdi+10h], ecx
0x18001d285  movzx   ecx, byte ptr [r10+r11+9]
0x18001d28b  shl     ecx, 10h
0x18001d28e  movzx   eax, byte ptr [r10+r11+8]
0x18001d294  or      ecx, eax
0x18001d296  or      ecx, edx
0x18001d298  mov     [rbx+rdi+10h], ecx
0x18001d29c  movzx   eax, byte ptr [rsi+5]
0x18001d2a0  movzx   edx, byte ptr [r9+5]
0x18001d2a5  movzx   ecx, byte ptr [r11+0Bh]
0x18001d2aa  shl     ecx, 10h
0x18001d2ad  shl     edx, 10h
0x18001d2b0  or      edx, eax
0x18001d2b2  movzx   eax, byte ptr [r11+0Ah]
0x18001d2b7  or      ecx, eax
0x18001d2b9  shl     edx, 8
0x18001d2bc  or      ecx, edx
0x18001d2be  mov     [rdi+14h], ecx
0x18001d2c1  movzx   eax, byte ptr [r10+r11+0Ah]
0x18001d2c7  movzx   ecx, byte ptr [r10+r11+0Bh]
0x18001d2cd  shl     ecx, 10h
0x18001d2d0  or      ecx, eax
0x18001d2d2  or      ecx, edx
0x18001d2d4  mov     [rbx+rdi+14h], ecx
0x18001d2d8  movzx   eax, byte ptr [rsi+6]
0x18001d2dc  movzx   edx, byte ptr [r9+6]
0x18001d2e1  movzx   ecx, byte ptr [r11+0Dh]
0x18001d2e6  shl     ecx, 10h
0x18001d2e9  shl     edx, 10h
0x18001d2ec  or      edx, eax
0x18001d2ee  movzx   eax, byte ptr [r11+0Ch]
0x18001d2f3  or      ecx, eax
0x18001d2f5  shl     edx, 8
0x18001d2f8  or      ecx, edx
0x18001d2fa  mov     [rdi+18h], ecx
0x18001d2fd  movzx   eax, byte ptr [r10+r11+0Ch]
0x18001d303  movzx   ecx, byte ptr [r10+r11+0Dh]
0x18001d309  shl     ecx, 10h
0x18001d30c  or      ecx, eax
0x18001d30e  or      ecx, edx
0x18001d310  mov     [rbx+rdi+18h], ecx
0x18001d314  movzx   eax, byte ptr [rsi+7]
0x18001d318  add     rsi, rbp
0x18001d31b  movzx   edx, byte ptr [r9+7]
0x18001d320  add     r9, rbp
0x18001d323  movzx   ecx, byte ptr [r11+0Fh]
0x18001d328  shl     ecx, 10h
0x18001d32b  shl     edx, 10h
0x18001d32e  or      edx, eax
0x18001d330  movzx   eax, byte ptr [r11+0Eh]
0x18001d335  or      ecx, eax
0x18001d337  shl     edx, 8
0x18001d33a  or      ecx, edx
0x18001d33c  mov     [rdi+1Ch], ecx
0x18001d33f  movzx   ecx, byte ptr [r10+r11+0Fh]
0x18001d345  movzx   eax, byte ptr [r10+r11+0Eh]
0x18001d34b  add     r11, r12
0x18001d34e  shl     ecx, 10h
0x18001d351  or      ecx, eax
0x18001d353  or      ecx, edx
0x18001d355  mov     [rbx+rdi+1Ch], ecx
0x18001d359  add     rdi, r15
0x18001d35c  sub     r14d, 1
0x18001d360  jnz     loc_18001D171
0x18001d366  pop     r15
0x18001d368  pop     r14
0x18001d36a  pop     r12
0x18001d36c  pop     rdi
0x18001d36d  pop     rsi
0x18001d36e  pop     rbp
0x18001d36f  pop     rbx
0x18001d370  retn
```
