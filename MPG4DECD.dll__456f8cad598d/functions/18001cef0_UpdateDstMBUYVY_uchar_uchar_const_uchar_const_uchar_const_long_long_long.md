# UpdateDstMBUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001cef0`
- end: `0x18001d130`
- name: `?UpdateDstMBUYVY@@YAXPEAEPEBE11JJJ@Z`
- size: `576`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001da50`

## callees

- `0x18001cef0`

## pseudocode

```c
void __fastcall UpdateDstMBUYVY(
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
    v11 = *a3 | (*a4 << 16);
    *(_DWORD *)a1 = v11 | ((*a2 | (a2[1] << 16)) << 8);
    *(_DWORD *)&a1[a7] = v11 | ((a2[a5] | (a2[a5 + 1] << 16)) << 8);
    v12 = a3[1] | (a4[1] << 16);
    *((_DWORD *)a1 + 1) = v12 | ((a2[2] | (a2[3] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 4] = v12 | ((a2[a5 + 2] | (a2[a5 + 3] << 16)) << 8);
    v13 = a3[2] | (a4[2] << 16);
    *((_DWORD *)a1 + 2) = v13 | ((a2[4] | (a2[5] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 8] = v13 | ((a2[a5 + 4] | (a2[a5 + 5] << 16)) << 8);
    v14 = a3[3] | (a4[3] << 16);
    *((_DWORD *)a1 + 3) = v14 | ((a2[6] | (a2[7] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 12] = v14 | ((a2[a5 + 6] | (a2[a5 + 7] << 16)) << 8);
    v15 = a3[4] | (a4[4] << 16);
    *((_DWORD *)a1 + 4) = v15 | ((a2[8] | (a2[9] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 16] = v15 | ((a2[a5 + 8] | (a2[a5 + 9] << 16)) << 8);
    v16 = a3[5] | (a4[5] << 16);
    *((_DWORD *)a1 + 5) = v16 | ((a2[10] | (a2[11] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 20] = v16 | ((a2[a5 + 10] | (a2[a5 + 11] << 16)) << 8);
    v17 = a3[6] | (a4[6] << 16);
    *((_DWORD *)a1 + 6) = v17 | ((a2[12] | (a2[13] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 24] = v17 | ((a2[a5 + 12] | (a2[a5 + 13] << 16)) << 8);
    v18 = a3[7];
    a3 += a6;
    v19 = a4[7];
    a4 += a6;
    v20 = v18 | (v19 << 16);
    *((_DWORD *)a1 + 7) = v20 | ((a2[14] | (a2[15] << 16)) << 8);
    v21 = a2[a5 + 15];
    v22 = a2[a5 + 14];
    a2 += 2 * a5;
    *(_DWORD *)&a1[a7 + 28] = v20 | ((v22 | (v21 << 16)) << 8);
    a1 += 2 * a7;
    --v10;
  }
  while ( v10 );
}

```

## disassembly

```asm
0x18001cef0  push    rbx
0x18001cef2  push    rbp
0x18001cef3  push    rsi
0x18001cef4  push    rdi
0x18001cef5  push    r12
0x18001cef7  push    r14
0x18001cef9  push    r15
0x18001cefb  movsxd  r11, [rsp+38h+arg_30]
0x18001cf00  mov     rsi, r8
0x18001cf03  movsxd  r10, [rsp+38h+arg_20]
0x18001cf08  mov     rbx, rdx
0x18001cf0b  movsxd  rbp, [rsp+38h+arg_28]
0x18001cf10  mov     rdi, rcx
0x18001cf13  mov     r14d, 8
0x18001cf19  lea     r15, [r11+r11]
0x18001cf1d  lea     r12, [r10+r10]
0x18001cf21  movzx   eax, byte ptr [rsi]
0x18001cf24  movzx   r8d, byte ptr [r9]
0x18001cf28  movzx   ecx, byte ptr [rbx+1]
0x18001cf2c  shl     ecx, 10h
0x18001cf2f  shl     r8d, 10h
0x18001cf33  or      r8d, eax
0x18001cf36  movzx   eax, byte ptr [rbx]
0x18001cf39  or      ecx, eax
0x18001cf3b  shl     ecx, 8
0x18001cf3e  or      ecx, r8d
0x18001cf41  mov     [rdi], ecx
0x18001cf43  movzx   eax, byte ptr [r10+rbx]
0x18001cf48  movzx   ecx, byte ptr [r10+rbx+1]
0x18001cf4e  shl     ecx, 10h
0x18001cf51  or      ecx, eax
0x18001cf53  shl     ecx, 8
0x18001cf56  or      ecx, r8d
0x18001cf59  mov     [r11+rdi], ecx
0x18001cf5d  movzx   eax, byte ptr [rsi+1]
0x18001cf61  movzx   edx, byte ptr [r9+1]
0x18001cf66  movzx   ecx, byte ptr [rbx+3]
0x18001cf6a  shl     ecx, 10h
0x18001cf6d  shl     edx, 10h
0x18001cf70  or      edx, eax
0x18001cf72  movzx   eax, byte ptr [rbx+2]
0x18001cf76  or      ecx, eax
0x18001cf78  shl     ecx, 8
0x18001cf7b  or      ecx, edx
0x18001cf7d  mov     [rdi+4], ecx
0x18001cf80  movzx   eax, byte ptr [r10+rbx+2]
0x18001cf86  movzx   ecx, byte ptr [r10+rbx+3]
0x18001cf8c  shl     ecx, 10h
0x18001cf8f  or      ecx, eax
0x18001cf91  shl     ecx, 8
0x18001cf94  or      ecx, edx
0x18001cf96  mov     [r11+rdi+4], ecx
0x18001cf9b  movzx   eax, byte ptr [rsi+2]
0x18001cf9f  movzx   edx, byte ptr [r9+2]
0x18001cfa4  movzx   ecx, byte ptr [rbx+5]
0x18001cfa8  shl     ecx, 10h
0x18001cfab  shl     edx, 10h
0x18001cfae  or      edx, eax
0x18001cfb0  movzx   eax, byte ptr [rbx+4]
0x18001cfb4  or      ecx, eax
0x18001cfb6  shl     ecx, 8
0x18001cfb9  or      ecx, edx
0x18001cfbb  mov     [rdi+8], ecx
0x18001cfbe  movzx   eax, byte ptr [r10+rbx+4]
0x18001cfc4  movzx   ecx, byte ptr [r10+rbx+5]
0x18001cfca  shl     ecx, 10h
0x18001cfcd  or      ecx, eax
0x18001cfcf  shl     ecx, 8
0x18001cfd2  or      ecx, edx
0x18001cfd4  mov     [r11+rdi+8], ecx
0x18001cfd9  movzx   eax, byte ptr [rsi+3]
0x18001cfdd  movzx   edx, byte ptr [r9+3]
0x18001cfe2  movzx   ecx, byte ptr [rbx+7]
0x18001cfe6  shl     ecx, 10h
0x18001cfe9  shl     edx, 10h
0x18001cfec  or      edx, eax
0x18001cfee  movzx   eax, byte ptr [rbx+6]
0x18001cff2  or      ecx, eax
0x18001cff4  shl     ecx, 8
0x18001cff7  or      ecx, edx
0x18001cff9  mov     [rdi+0Ch], ecx
0x18001cffc  movzx   eax, byte ptr [r10+rbx+6]
0x18001d002  movzx   ecx, byte ptr [r10+rbx+7]
0x18001d008  shl     ecx, 10h
0x18001d00b  or      ecx, eax
0x18001d00d  shl     ecx, 8
0x18001d010  or      ecx, edx
0x18001d012  mov     [r11+rdi+0Ch], ecx
0x18001d017  movzx   eax, byte ptr [rsi+4]
0x18001d01b  movzx   edx, byte ptr [r9+4]
0x18001d020  movzx   ecx, byte ptr [rbx+9]
0x18001d024  shl     edx, 10h
0x18001d027  or      edx, eax
0x18001d029  shl     ecx, 10h
0x18001d02c  movzx   eax, byte ptr [rbx+8]
0x18001d030  or      ecx, eax
0x18001d032  shl     ecx, 8
0x18001d035  or      ecx, edx
0x18001d037  mov     [rdi+10h], ecx
0x18001d03a  movzx   eax, byte ptr [r10+rbx+8]
0x18001d040  movzx   ecx, byte ptr [r10+rbx+9]
0x18001d046  shl     ecx, 10h
0x18001d049  or      ecx, eax
0x18001d04b  shl     ecx, 8
0x18001d04e  or      ecx, edx
0x18001d050  mov     [r11+rdi+10h], ecx
0x18001d055  movzx   eax, byte ptr [rsi+5]
0x18001d059  movzx   edx, byte ptr [r9+5]
0x18001d05e  movzx   ecx, byte ptr [rbx+0Bh]
0x18001d062  shl     ecx, 10h
0x18001d065  shl     edx, 10h
0x18001d068  or      edx, eax
0x18001d06a  movzx   eax, byte ptr [rbx+0Ah]
0x18001d06e  or      ecx, eax
0x18001d070  shl     ecx, 8
0x18001d073  or      ecx, edx
0x18001d075  mov     [rdi+14h], ecx
0x18001d078  movzx   eax, byte ptr [r10+rbx+0Ah]
0x18001d07e  movzx   ecx, byte ptr [r10+rbx+0Bh]
0x18001d084  shl     ecx, 10h
0x18001d087  or      ecx, eax
0x18001d089  shl     ecx, 8
0x18001d08c  or      ecx, edx
0x18001d08e  mov     [r11+rdi+14h], ecx
0x18001d093  movzx   eax, byte ptr [rsi+6]
0x18001d097  movzx   edx, byte ptr [r9+6]
0x18001d09c  movzx   ecx, byte ptr [rbx+0Dh]
0x18001d0a0  shl     ecx, 10h
0x18001d0a3  shl     edx, 10h
0x18001d0a6  or      edx, eax
0x18001d0a8  movzx   eax, byte ptr [rbx+0Ch]
0x18001d0ac  or      ecx, eax
0x18001d0ae  shl     ecx, 8
0x18001d0b1  or      ecx, edx
0x18001d0b3  mov     [rdi+18h], ecx
0x18001d0b6  movzx   eax, byte ptr [r10+rbx+0Ch]
0x18001d0bc  movzx   ecx, byte ptr [r10+rbx+0Dh]
0x18001d0c2  shl     ecx, 10h
0x18001d0c5  or      ecx, eax
0x18001d0c7  shl     ecx, 8
0x18001d0ca  or      ecx, edx
0x18001d0cc  mov     [r11+rdi+18h], ecx
0x18001d0d1  movzx   eax, byte ptr [rsi+7]
0x18001d0d5  add     rsi, rbp
0x18001d0d8  movzx   edx, byte ptr [r9+7]
0x18001d0dd  add     r9, rbp
0x18001d0e0  movzx   ecx, byte ptr [rbx+0Fh]
0x18001d0e4  shl     ecx, 10h
0x18001d0e7  shl     edx, 10h
0x18001d0ea  or      edx, eax
0x18001d0ec  movzx   eax, byte ptr [rbx+0Eh]
0x18001d0f0  or      ecx, eax
0x18001d0f2  shl     ecx, 8
0x18001d0f5  or      ecx, edx
0x18001d0f7  mov     [rdi+1Ch], ecx
0x18001d0fa  movzx   ecx, byte ptr [r10+rbx+0Fh]
0x18001d100  movzx   eax, byte ptr [r10+rbx+0Eh]
0x18001d106  add     rbx, r12
0x18001d109  shl     ecx, 10h
0x18001d10c  or      ecx, eax
0x18001d10e  shl     ecx, 8
0x18001d111  or      ecx, edx
0x18001d113  mov     [r11+rdi+1Ch], ecx
0x18001d118  add     rdi, r15
0x18001d11b  sub     r14d, 1
0x18001d11f  jnz     loc_18001CF21
0x18001d125  pop     r15
0x18001d127  pop     r14
0x18001d129  pop     r12
0x18001d12b  pop     rdi
0x18001d12c  pop     rsi
0x18001d12d  pop     rbp
0x18001d12e  pop     rbx
0x18001d12f  retn
```
