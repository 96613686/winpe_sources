# UpdateDstMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180042d90`
- end: `0x180042fbd`
- name: `?UpdateDstMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `557`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800438e0`

## callees

- `0x180042d90`

## pseudocode

```c
void __fastcall UpdateDstMBYVYU(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        int a6,
        int a7,
        int a8)
{
  int v9; // ebp
  int v11; // edx
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

  v9 = 8;
  do
  {
    v11 = (*a5 | (*a4 << 16)) << 8;
    *(_DWORD *)a2 = v11 | *a3 | (a3[1] << 16);
    *(_DWORD *)&a2[a8] = v11 | a3[a6] | (a3[a6 + 1] << 16);
    v12 = (a5[1] | (a4[1] << 16)) << 8;
    *((_DWORD *)a2 + 1) = v12 | a3[2] | (a3[3] << 16);
    *(_DWORD *)&a2[a8 + 4] = v12 | a3[a6 + 2] | (a3[a6 + 3] << 16);
    v13 = (a5[2] | (a4[2] << 16)) << 8;
    *((_DWORD *)a2 + 2) = v13 | a3[4] | (a3[5] << 16);
    *(_DWORD *)&a2[a8 + 8] = v13 | a3[a6 + 4] | (a3[a6 + 5] << 16);
    v14 = (a5[3] | (a4[3] << 16)) << 8;
    *((_DWORD *)a2 + 3) = v14 | a3[6] | (a3[7] << 16);
    *(_DWORD *)&a2[a8 + 12] = v14 | a3[a6 + 6] | (a3[a6 + 7] << 16);
    v15 = (a5[4] | (a4[4] << 16)) << 8;
    *((_DWORD *)a2 + 4) = v15 | a3[8] | (a3[9] << 16);
    *(_DWORD *)&a2[a8 + 16] = v15 | a3[a6 + 8] | (a3[a6 + 9] << 16);
    v16 = (a5[5] | (a4[5] << 16)) << 8;
    *((_DWORD *)a2 + 5) = v16 | a3[10] | (a3[11] << 16);
    *(_DWORD *)&a2[a8 + 20] = v16 | a3[a6 + 10] | (a3[a6 + 11] << 16);
    v17 = (a5[6] | (a4[6] << 16)) << 8;
    *((_DWORD *)a2 + 6) = v17 | a3[12] | (a3[13] << 16);
    *(_DWORD *)&a2[a8 + 24] = v17 | a3[a6 + 12] | (a3[a6 + 13] << 16);
    v18 = a5[7];
    a5 += a7;
    v19 = a4[7];
    a4 += a7;
    v20 = (v18 | (v19 << 16)) << 8;
    *((_DWORD *)a2 + 7) = v20 | a3[14] | (a3[15] << 16);
    v21 = a3[a6 + 15];
    v22 = a3[a6 + 14];
    a3 += 2 * a6;
    *(_DWORD *)&a2[a8 + 28] = v20 | v22 | (v21 << 16);
    a2 += 2 * a8;
    --v9;
  }
  while ( v9 );
}

```

## disassembly

```asm
0x180042d90  push    rbx
0x180042d92  push    rbp
0x180042d93  push    rsi
0x180042d94  push    rdi
0x180042d95  push    r14
0x180042d97  push    r15
0x180042d99  movsxd  r11, [rsp+30h+arg_38]
0x180042d9e  mov     rbx, rdx
0x180042da1  movsxd  r10, [rsp+30h+arg_28]
0x180042da6  mov     ebp, 8
0x180042dab  movsxd  rsi, [rsp+30h+arg_30]
0x180042db0  mov     rdi, [rsp+30h+arg_20]
0x180042db5  lea     r14, [r11+r11]
0x180042db9  lea     r15, [r10+r10]
0x180042dbd  movzx   eax, byte ptr [rdi]
0x180042dc0  movzx   edx, byte ptr [r9]
0x180042dc4  movzx   ecx, byte ptr [r8+1]
0x180042dc9  shl     ecx, 10h
0x180042dcc  shl     edx, 10h
0x180042dcf  or      edx, eax
0x180042dd1  movzx   eax, byte ptr [r8]
0x180042dd5  or      ecx, eax
0x180042dd7  shl     edx, 8
0x180042dda  or      ecx, edx
0x180042ddc  mov     [rbx], ecx
0x180042dde  movzx   eax, byte ptr [r10+r8]
0x180042de3  movzx   ecx, byte ptr [r10+r8+1]
0x180042de9  shl     ecx, 10h
0x180042dec  or      ecx, eax
0x180042dee  or      ecx, edx
0x180042df0  mov     [r11+rbx], ecx
0x180042df4  movzx   eax, byte ptr [rdi+1]
0x180042df8  movzx   edx, byte ptr [r9+1]
0x180042dfd  movzx   ecx, byte ptr [r8+3]
0x180042e02  shl     ecx, 10h
0x180042e05  shl     edx, 10h
0x180042e08  or      edx, eax
0x180042e0a  movzx   eax, byte ptr [r8+2]
0x180042e0f  or      ecx, eax
0x180042e11  shl     edx, 8
0x180042e14  or      ecx, edx
0x180042e16  mov     [rbx+4], ecx
0x180042e19  movzx   eax, byte ptr [r10+r8+2]
0x180042e1f  movzx   ecx, byte ptr [r10+r8+3]
0x180042e25  shl     ecx, 10h
0x180042e28  or      ecx, eax
0x180042e2a  or      ecx, edx
0x180042e2c  mov     [r11+rbx+4], ecx
0x180042e31  movzx   eax, byte ptr [rdi+2]
0x180042e35  movzx   edx, byte ptr [r9+2]
0x180042e3a  movzx   ecx, byte ptr [r8+5]
0x180042e3f  shl     ecx, 10h
0x180042e42  shl     edx, 10h
0x180042e45  or      edx, eax
0x180042e47  movzx   eax, byte ptr [r8+4]
0x180042e4c  or      ecx, eax
0x180042e4e  shl     edx, 8
0x180042e51  or      ecx, edx
0x180042e53  mov     [rbx+8], ecx
0x180042e56  movzx   eax, byte ptr [r10+r8+4]
0x180042e5c  movzx   ecx, byte ptr [r10+r8+5]
0x180042e62  shl     ecx, 10h
0x180042e65  or      ecx, eax
0x180042e67  or      ecx, edx
0x180042e69  mov     [r11+rbx+8], ecx
0x180042e6e  movzx   eax, byte ptr [rdi+3]
0x180042e72  movzx   edx, byte ptr [r9+3]
0x180042e77  movzx   ecx, byte ptr [r8+7]
0x180042e7c  shl     ecx, 10h
0x180042e7f  shl     edx, 10h
0x180042e82  or      edx, eax
0x180042e84  movzx   eax, byte ptr [r8+6]
0x180042e89  or      ecx, eax
0x180042e8b  shl     edx, 8
0x180042e8e  or      ecx, edx
0x180042e90  mov     [rbx+0Ch], ecx
0x180042e93  movzx   eax, byte ptr [r10+r8+6]
0x180042e99  movzx   ecx, byte ptr [r10+r8+7]
0x180042e9f  shl     ecx, 10h
0x180042ea2  or      ecx, eax
0x180042ea4  or      ecx, edx
0x180042ea6  mov     [r11+rbx+0Ch], ecx
0x180042eab  movzx   eax, byte ptr [rdi+4]
0x180042eaf  movzx   edx, byte ptr [r9+4]
0x180042eb4  movzx   ecx, byte ptr [r8+9]
0x180042eb9  shl     ecx, 10h
0x180042ebc  shl     edx, 10h
0x180042ebf  or      edx, eax
0x180042ec1  movzx   eax, byte ptr [r8+8]
0x180042ec6  or      ecx, eax
0x180042ec8  shl     edx, 8
0x180042ecb  or      ecx, edx
0x180042ecd  mov     [rbx+10h], ecx
0x180042ed0  movzx   ecx, byte ptr [r10+r8+9]
0x180042ed6  shl     ecx, 10h
0x180042ed9  movzx   eax, byte ptr [r10+r8+8]
0x180042edf  or      ecx, eax
0x180042ee1  or      ecx, edx
0x180042ee3  mov     [r11+rbx+10h], ecx
0x180042ee8  movzx   eax, byte ptr [rdi+5]
0x180042eec  movzx   edx, byte ptr [r9+5]
0x180042ef1  movzx   ecx, byte ptr [r8+0Bh]
0x180042ef6  shl     ecx, 10h
0x180042ef9  shl     edx, 10h
0x180042efc  or      edx, eax
0x180042efe  movzx   eax, byte ptr [r8+0Ah]
0x180042f03  or      ecx, eax
0x180042f05  shl     edx, 8
0x180042f08  or      ecx, edx
0x180042f0a  mov     [rbx+14h], ecx
0x180042f0d  movzx   eax, byte ptr [r10+r8+0Ah]
0x180042f13  movzx   ecx, byte ptr [r10+r8+0Bh]
0x180042f19  shl     ecx, 10h
0x180042f1c  or      ecx, eax
0x180042f1e  or      ecx, edx
0x180042f20  mov     [r11+rbx+14h], ecx
0x180042f25  movzx   eax, byte ptr [rdi+6]
0x180042f29  movzx   edx, byte ptr [r9+6]
0x180042f2e  movzx   ecx, byte ptr [r8+0Dh]
0x180042f33  shl     ecx, 10h
0x180042f36  shl     edx, 10h
0x180042f39  or      edx, eax
0x180042f3b  movzx   eax, byte ptr [r8+0Ch]
0x180042f40  or      ecx, eax
0x180042f42  shl     edx, 8
0x180042f45  or      ecx, edx
0x180042f47  mov     [rbx+18h], ecx
0x180042f4a  movzx   eax, byte ptr [r10+r8+0Ch]
0x180042f50  movzx   ecx, byte ptr [r10+r8+0Dh]
0x180042f56  shl     ecx, 10h
0x180042f59  or      ecx, eax
0x180042f5b  or      ecx, edx
0x180042f5d  mov     [r11+rbx+18h], ecx
0x180042f62  movzx   eax, byte ptr [rdi+7]
0x180042f66  add     rdi, rsi
0x180042f69  movzx   edx, byte ptr [r9+7]
0x180042f6e  add     r9, rsi
0x180042f71  movzx   ecx, byte ptr [r8+0Fh]
0x180042f76  shl     ecx, 10h
0x180042f79  shl     edx, 10h
0x180042f7c  or      edx, eax
0x180042f7e  movzx   eax, byte ptr [r8+0Eh]
0x180042f83  or      ecx, eax
0x180042f85  shl     edx, 8
0x180042f88  or      ecx, edx
0x180042f8a  mov     [rbx+1Ch], ecx
0x180042f8d  movzx   ecx, byte ptr [r10+r8+0Fh]
0x180042f93  movzx   eax, byte ptr [r10+r8+0Eh]
0x180042f99  add     r8, r15
0x180042f9c  shl     ecx, 10h
0x180042f9f  or      ecx, eax
0x180042fa1  or      ecx, edx
0x180042fa3  mov     [r11+rbx+1Ch], ecx
0x180042fa8  add     rbx, r14
0x180042fab  sub     ebp, 1
0x180042fae  jnz     loc_180042DBD
0x180042fb4  pop     r15
0x180042fb6  pop     r14
0x180042fb8  pop     rdi
0x180042fb9  pop     rsi
0x180042fba  pop     rbp
0x180042fbb  pop     rbx
0x180042fbc  retn
```
