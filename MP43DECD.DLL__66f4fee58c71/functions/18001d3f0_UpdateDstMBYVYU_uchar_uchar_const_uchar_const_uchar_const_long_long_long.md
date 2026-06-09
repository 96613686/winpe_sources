# UpdateDstMBYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001d3f0`
- end: `0x18001d622`
- name: `?UpdateDstMBYVYU@@YAXPEAEPEBE11JJJ@Z`
- size: `562`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001ddb0`

## callees

- `0x18001d3f0`

## pseudocode

```c
void __fastcall UpdateDstMBYVYU(
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
    v11 = (*a4 | (*a3 << 16)) << 8;
    *(_DWORD *)a1 = v11 | *a2 | (a2[1] << 16);
    *(_DWORD *)&a1[a7] = v11 | a2[a5] | (a2[a5 + 1] << 16);
    v12 = (a4[1] | (a3[1] << 16)) << 8;
    *((_DWORD *)a1 + 1) = v12 | a2[2] | (a2[3] << 16);
    *(_DWORD *)&a1[a7 + 4] = v12 | a2[a5 + 2] | (a2[a5 + 3] << 16);
    v13 = (a4[2] | (a3[2] << 16)) << 8;
    *((_DWORD *)a1 + 2) = v13 | a2[4] | (a2[5] << 16);
    *(_DWORD *)&a1[a7 + 8] = v13 | a2[a5 + 4] | (a2[a5 + 5] << 16);
    v14 = (a4[3] | (a3[3] << 16)) << 8;
    *((_DWORD *)a1 + 3) = v14 | a2[6] | (a2[7] << 16);
    *(_DWORD *)&a1[a7 + 12] = v14 | a2[a5 + 6] | (a2[a5 + 7] << 16);
    v15 = (a4[4] | (a3[4] << 16)) << 8;
    *((_DWORD *)a1 + 4) = v15 | a2[8] | (a2[9] << 16);
    *(_DWORD *)&a1[a7 + 16] = v15 | a2[a5 + 8] | (a2[a5 + 9] << 16);
    v16 = (a4[5] | (a3[5] << 16)) << 8;
    *((_DWORD *)a1 + 5) = v16 | a2[10] | (a2[11] << 16);
    *(_DWORD *)&a1[a7 + 20] = v16 | a2[a5 + 10] | (a2[a5 + 11] << 16);
    v17 = (a4[6] | (a3[6] << 16)) << 8;
    *((_DWORD *)a1 + 6) = v17 | a2[12] | (a2[13] << 16);
    *(_DWORD *)&a1[a7 + 24] = v17 | a2[a5 + 12] | (a2[a5 + 13] << 16);
    v18 = a4[7];
    a4 += a6;
    v19 = a3[7];
    a3 += a6;
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
0x18001d3f0  push    rbx
0x18001d3f2  push    rbp
0x18001d3f3  push    rsi
0x18001d3f4  push    rdi
0x18001d3f5  push    r12
0x18001d3f7  push    r14
0x18001d3f9  push    r15
0x18001d3fb  movsxd  rbx, [rsp+38h+arg_30]
0x18001d400  mov     rsi, r8
0x18001d403  movsxd  r10, [rsp+38h+arg_20]
0x18001d408  mov     r11, rdx
0x18001d40b  movsxd  rbp, [rsp+38h+arg_28]
0x18001d410  mov     rdi, rcx
0x18001d413  mov     r14d, 8
0x18001d419  lea     r15, [rbx+rbx]
0x18001d41d  lea     r12, [r10+r10]
0x18001d421  movzx   eax, byte ptr [r9]
0x18001d425  movzx   r8d, byte ptr [rsi]
0x18001d429  movzx   ecx, byte ptr [r11+1]
0x18001d42e  shl     ecx, 10h
0x18001d431  shl     r8d, 10h
0x18001d435  or      r8d, eax
0x18001d438  movzx   eax, byte ptr [r11]
0x18001d43c  or      ecx, eax
0x18001d43e  shl     r8d, 8
0x18001d442  or      ecx, r8d
0x18001d445  mov     [rdi], ecx
0x18001d447  movzx   eax, byte ptr [r10+r11]
0x18001d44c  movzx   ecx, byte ptr [r10+r11+1]
0x18001d452  shl     ecx, 10h
0x18001d455  or      ecx, eax
0x18001d457  or      ecx, r8d
0x18001d45a  mov     [rbx+rdi], ecx
0x18001d45d  movzx   eax, byte ptr [r9+1]
0x18001d462  movzx   edx, byte ptr [rsi+1]
0x18001d466  movzx   ecx, byte ptr [r11+3]
0x18001d46b  shl     ecx, 10h
0x18001d46e  shl     edx, 10h
0x18001d471  or      edx, eax
0x18001d473  movzx   eax, byte ptr [r11+2]
0x18001d478  or      ecx, eax
0x18001d47a  shl     edx, 8
0x18001d47d  or      ecx, edx
0x18001d47f  mov     [rdi+4], ecx
0x18001d482  movzx   eax, byte ptr [r10+r11+2]
0x18001d488  movzx   ecx, byte ptr [r10+r11+3]
0x18001d48e  shl     ecx, 10h
0x18001d491  or      ecx, eax
0x18001d493  or      ecx, edx
0x18001d495  mov     [rbx+rdi+4], ecx
0x18001d499  movzx   eax, byte ptr [r9+2]
0x18001d49e  movzx   edx, byte ptr [rsi+2]
0x18001d4a2  movzx   ecx, byte ptr [r11+5]
0x18001d4a7  shl     ecx, 10h
0x18001d4aa  shl     edx, 10h
0x18001d4ad  or      edx, eax
0x18001d4af  movzx   eax, byte ptr [r11+4]
0x18001d4b4  or      ecx, eax
0x18001d4b6  shl     edx, 8
0x18001d4b9  or      ecx, edx
0x18001d4bb  mov     [rdi+8], ecx
0x18001d4be  movzx   eax, byte ptr [r10+r11+4]
0x18001d4c4  movzx   ecx, byte ptr [r10+r11+5]
0x18001d4ca  shl     ecx, 10h
0x18001d4cd  or      ecx, eax
0x18001d4cf  or      ecx, edx
0x18001d4d1  mov     [rbx+rdi+8], ecx
0x18001d4d5  movzx   eax, byte ptr [r9+3]
0x18001d4da  movzx   edx, byte ptr [rsi+3]
0x18001d4de  movzx   ecx, byte ptr [r11+7]
0x18001d4e3  shl     ecx, 10h
0x18001d4e6  shl     edx, 10h
0x18001d4e9  or      edx, eax
0x18001d4eb  movzx   eax, byte ptr [r11+6]
0x18001d4f0  or      ecx, eax
0x18001d4f2  shl     edx, 8
0x18001d4f5  or      ecx, edx
0x18001d4f7  mov     [rdi+0Ch], ecx
0x18001d4fa  movzx   eax, byte ptr [r10+r11+6]
0x18001d500  movzx   ecx, byte ptr [r10+r11+7]
0x18001d506  shl     ecx, 10h
0x18001d509  or      ecx, eax
0x18001d50b  or      ecx, edx
0x18001d50d  mov     [rbx+rdi+0Ch], ecx
0x18001d511  movzx   eax, byte ptr [r9+4]
0x18001d516  movzx   edx, byte ptr [rsi+4]
0x18001d51a  movzx   ecx, byte ptr [r11+9]
0x18001d51f  shl     ecx, 10h
0x18001d522  shl     edx, 10h
0x18001d525  or      edx, eax
0x18001d527  movzx   eax, byte ptr [r11+8]
0x18001d52c  or      ecx, eax
0x18001d52e  shl     edx, 8
0x18001d531  or      ecx, edx
0x18001d533  mov     [rdi+10h], ecx
0x18001d536  movzx   ecx, byte ptr [r10+r11+9]
0x18001d53c  shl     ecx, 10h
0x18001d53f  movzx   eax, byte ptr [r10+r11+8]
0x18001d545  or      ecx, eax
0x18001d547  or      ecx, edx
0x18001d549  mov     [rbx+rdi+10h], ecx
0x18001d54d  movzx   eax, byte ptr [r9+5]
0x18001d552  movzx   edx, byte ptr [rsi+5]
0x18001d556  movzx   ecx, byte ptr [r11+0Bh]
0x18001d55b  shl     ecx, 10h
0x18001d55e  shl     edx, 10h
0x18001d561  or      edx, eax
0x18001d563  movzx   eax, byte ptr [r11+0Ah]
0x18001d568  or      ecx, eax
0x18001d56a  shl     edx, 8
0x18001d56d  or      ecx, edx
0x18001d56f  mov     [rdi+14h], ecx
0x18001d572  movzx   eax, byte ptr [r10+r11+0Ah]
0x18001d578  movzx   ecx, byte ptr [r10+r11+0Bh]
0x18001d57e  shl     ecx, 10h
0x18001d581  or      ecx, eax
0x18001d583  or      ecx, edx
0x18001d585  mov     [rbx+rdi+14h], ecx
0x18001d589  movzx   eax, byte ptr [r9+6]
0x18001d58e  movzx   edx, byte ptr [rsi+6]
0x18001d592  movzx   ecx, byte ptr [r11+0Dh]
0x18001d597  shl     ecx, 10h
0x18001d59a  shl     edx, 10h
0x18001d59d  or      edx, eax
0x18001d59f  movzx   eax, byte ptr [r11+0Ch]
0x18001d5a4  or      ecx, eax
0x18001d5a6  shl     edx, 8
0x18001d5a9  or      ecx, edx
0x18001d5ab  mov     [rdi+18h], ecx
0x18001d5ae  movzx   eax, byte ptr [r10+r11+0Ch]
0x18001d5b4  movzx   ecx, byte ptr [r10+r11+0Dh]
0x18001d5ba  shl     ecx, 10h
0x18001d5bd  or      ecx, eax
0x18001d5bf  or      ecx, edx
0x18001d5c1  mov     [rbx+rdi+18h], ecx
0x18001d5c5  movzx   eax, byte ptr [r9+7]
0x18001d5ca  add     r9, rbp
0x18001d5cd  movzx   edx, byte ptr [rsi+7]
0x18001d5d1  add     rsi, rbp
0x18001d5d4  movzx   ecx, byte ptr [r11+0Fh]
0x18001d5d9  shl     ecx, 10h
0x18001d5dc  shl     edx, 10h
0x18001d5df  or      edx, eax
0x18001d5e1  movzx   eax, byte ptr [r11+0Eh]
0x18001d5e6  or      ecx, eax
0x18001d5e8  shl     edx, 8
0x18001d5eb  or      ecx, edx
0x18001d5ed  mov     [rdi+1Ch], ecx
0x18001d5f0  movzx   ecx, byte ptr [r10+r11+0Fh]
0x18001d5f6  movzx   eax, byte ptr [r10+r11+0Eh]
0x18001d5fc  add     r11, r12
0x18001d5ff  shl     ecx, 10h
0x18001d602  or      ecx, eax
0x18001d604  or      ecx, edx
0x18001d606  mov     [rbx+rdi+1Ch], ecx
0x18001d60a  add     rdi, r15
0x18001d60d  sub     r14d, 1
0x18001d611  jnz     loc_18001D421
0x18001d617  pop     r15
0x18001d619  pop     r14
0x18001d61b  pop     r12
0x18001d61d  pop     rdi
0x18001d61e  pop     rsi
0x18001d61f  pop     rbp
0x18001d620  pop     rbx
0x18001d621  retn
```
