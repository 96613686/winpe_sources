# UpdateDstMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x1800427d0`
- end: `0x180042a15`
- name: `?UpdateDstMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `581`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800434c0`

## callees

- `0x1800427d0`

## pseudocode

```c
void __fastcall UpdateDstMBUYVY(
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
    v11 = *a4 | (*a5 << 16);
    *(_DWORD *)a2 = v11 | ((*a3 | (a3[1] << 16)) << 8);
    *(_DWORD *)&a2[a8] = v11 | ((a3[a6] | (a3[a6 + 1] << 16)) << 8);
    v12 = a4[1] | (a5[1] << 16);
    *((_DWORD *)a2 + 1) = v12 | ((a3[2] | (a3[3] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 4] = v12 | ((a3[a6 + 2] | (a3[a6 + 3] << 16)) << 8);
    v13 = a4[2] | (a5[2] << 16);
    *((_DWORD *)a2 + 2) = v13 | ((a3[4] | (a3[5] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 8] = v13 | ((a3[a6 + 4] | (a3[a6 + 5] << 16)) << 8);
    v14 = a4[3] | (a5[3] << 16);
    *((_DWORD *)a2 + 3) = v14 | ((a3[6] | (a3[7] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 12] = v14 | ((a3[a6 + 6] | (a3[a6 + 7] << 16)) << 8);
    v15 = a4[4] | (a5[4] << 16);
    *((_DWORD *)a2 + 4) = v15 | ((a3[8] | (a3[9] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 16] = v15 | ((a3[a6 + 8] | (a3[a6 + 9] << 16)) << 8);
    v16 = a4[5] | (a5[5] << 16);
    *((_DWORD *)a2 + 5) = v16 | ((a3[10] | (a3[11] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 20] = v16 | ((a3[a6 + 10] | (a3[a6 + 11] << 16)) << 8);
    v17 = a4[6] | (a5[6] << 16);
    *((_DWORD *)a2 + 6) = v17 | ((a3[12] | (a3[13] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 24] = v17 | ((a3[a6 + 12] | (a3[a6 + 13] << 16)) << 8);
    v18 = a4[7];
    a4 += a7;
    v19 = a5[7];
    a5 += a7;
    v20 = v18 | (v19 << 16);
    *((_DWORD *)a2 + 7) = v20 | ((a3[14] | (a3[15] << 16)) << 8);
    v21 = a3[a6 + 15];
    v22 = a3[a6 + 14];
    a3 += 2 * a6;
    *(_DWORD *)&a2[a8 + 28] = v20 | ((v22 | (v21 << 16)) << 8);
    a2 += 2 * a8;
    --v9;
  }
  while ( v9 );
}

```

## disassembly

```asm
0x1800427d0  push    rbx
0x1800427d2  push    rbp
0x1800427d3  push    rsi
0x1800427d4  push    rdi
0x1800427d5  push    r14
0x1800427d7  push    r15
0x1800427d9  movsxd  r11, [rsp+30h+arg_38]
0x1800427de  mov     rbx, rdx
0x1800427e1  movsxd  r10, [rsp+30h+arg_28]
0x1800427e6  mov     ebp, 8
0x1800427eb  movsxd  rsi, [rsp+30h+arg_30]
0x1800427f0  mov     rdi, [rsp+30h+arg_20]
0x1800427f5  lea     r14, [r11+r11]
0x1800427f9  lea     r15, [r10+r10]
0x1800427fd  movzx   eax, byte ptr [r9]
0x180042801  movzx   edx, byte ptr [rdi]
0x180042804  movzx   ecx, byte ptr [r8+1]
0x180042809  shl     ecx, 10h
0x18004280c  shl     edx, 10h
0x18004280f  or      edx, eax
0x180042811  movzx   eax, byte ptr [r8]
0x180042815  or      ecx, eax
0x180042817  shl     ecx, 8
0x18004281a  or      ecx, edx
0x18004281c  mov     [rbx], ecx
0x18004281e  movzx   eax, byte ptr [r10+r8]
0x180042823  movzx   ecx, byte ptr [r10+r8+1]
0x180042829  shl     ecx, 10h
0x18004282c  or      ecx, eax
0x18004282e  shl     ecx, 8
0x180042831  or      ecx, edx
0x180042833  mov     [r11+rbx], ecx
0x180042837  movzx   eax, byte ptr [r9+1]
0x18004283c  movzx   edx, byte ptr [rdi+1]
0x180042840  movzx   ecx, byte ptr [r8+3]
0x180042845  shl     ecx, 10h
0x180042848  shl     edx, 10h
0x18004284b  or      edx, eax
0x18004284d  movzx   eax, byte ptr [r8+2]
0x180042852  or      ecx, eax
0x180042854  shl     ecx, 8
0x180042857  or      ecx, edx
0x180042859  mov     [rbx+4], ecx
0x18004285c  movzx   eax, byte ptr [r10+r8+2]
0x180042862  movzx   ecx, byte ptr [r10+r8+3]
0x180042868  shl     ecx, 10h
0x18004286b  or      ecx, eax
0x18004286d  shl     ecx, 8
0x180042870  or      ecx, edx
0x180042872  mov     [r11+rbx+4], ecx
0x180042877  movzx   eax, byte ptr [r9+2]
0x18004287c  movzx   edx, byte ptr [rdi+2]
0x180042880  movzx   ecx, byte ptr [r8+5]
0x180042885  shl     ecx, 10h
0x180042888  shl     edx, 10h
0x18004288b  or      edx, eax
0x18004288d  movzx   eax, byte ptr [r8+4]
0x180042892  or      ecx, eax
0x180042894  shl     ecx, 8
0x180042897  or      ecx, edx
0x180042899  mov     [rbx+8], ecx
0x18004289c  movzx   eax, byte ptr [r10+r8+4]
0x1800428a2  movzx   ecx, byte ptr [r10+r8+5]
0x1800428a8  shl     ecx, 10h
0x1800428ab  or      ecx, eax
0x1800428ad  shl     ecx, 8
0x1800428b0  or      ecx, edx
0x1800428b2  mov     [r11+rbx+8], ecx
0x1800428b7  movzx   eax, byte ptr [r9+3]
0x1800428bc  movzx   edx, byte ptr [rdi+3]
0x1800428c0  movzx   ecx, byte ptr [r8+7]
0x1800428c5  shl     ecx, 10h
0x1800428c8  shl     edx, 10h
0x1800428cb  or      edx, eax
0x1800428cd  movzx   eax, byte ptr [r8+6]
0x1800428d2  or      ecx, eax
0x1800428d4  shl     ecx, 8
0x1800428d7  or      ecx, edx
0x1800428d9  mov     [rbx+0Ch], ecx
0x1800428dc  movzx   eax, byte ptr [r10+r8+6]
0x1800428e2  movzx   ecx, byte ptr [r10+r8+7]
0x1800428e8  shl     ecx, 10h
0x1800428eb  or      ecx, eax
0x1800428ed  shl     ecx, 8
0x1800428f0  or      ecx, edx
0x1800428f2  mov     [r11+rbx+0Ch], ecx
0x1800428f7  movzx   eax, byte ptr [r9+4]
0x1800428fc  movzx   edx, byte ptr [rdi+4]
0x180042900  movzx   ecx, byte ptr [r8+9]
0x180042905  shl     edx, 10h
0x180042908  or      edx, eax
0x18004290a  shl     ecx, 10h
0x18004290d  movzx   eax, byte ptr [r8+8]
0x180042912  or      ecx, eax
0x180042914  shl     ecx, 8
0x180042917  or      ecx, edx
0x180042919  mov     [rbx+10h], ecx
0x18004291c  movzx   eax, byte ptr [r10+r8+8]
0x180042922  movzx   ecx, byte ptr [r10+r8+9]
0x180042928  shl     ecx, 10h
0x18004292b  or      ecx, eax
0x18004292d  shl     ecx, 8
0x180042930  or      ecx, edx
0x180042932  mov     [r11+rbx+10h], ecx
0x180042937  movzx   eax, byte ptr [r9+5]
0x18004293c  movzx   edx, byte ptr [rdi+5]
0x180042940  movzx   ecx, byte ptr [r8+0Bh]
0x180042945  shl     ecx, 10h
0x180042948  shl     edx, 10h
0x18004294b  or      edx, eax
0x18004294d  movzx   eax, byte ptr [r8+0Ah]
0x180042952  or      ecx, eax
0x180042954  shl     ecx, 8
0x180042957  or      ecx, edx
0x180042959  mov     [rbx+14h], ecx
0x18004295c  movzx   eax, byte ptr [r10+r8+0Ah]
0x180042962  movzx   ecx, byte ptr [r10+r8+0Bh]
0x180042968  shl     ecx, 10h
0x18004296b  or      ecx, eax
0x18004296d  shl     ecx, 8
0x180042970  or      ecx, edx
0x180042972  mov     [r11+rbx+14h], ecx
0x180042977  movzx   eax, byte ptr [r9+6]
0x18004297c  movzx   edx, byte ptr [rdi+6]
0x180042980  movzx   ecx, byte ptr [r8+0Dh]
0x180042985  shl     ecx, 10h
0x180042988  shl     edx, 10h
0x18004298b  or      edx, eax
0x18004298d  movzx   eax, byte ptr [r8+0Ch]
0x180042992  or      ecx, eax
0x180042994  shl     ecx, 8
0x180042997  or      ecx, edx
0x180042999  mov     [rbx+18h], ecx
0x18004299c  movzx   eax, byte ptr [r10+r8+0Ch]
0x1800429a2  movzx   ecx, byte ptr [r10+r8+0Dh]
0x1800429a8  shl     ecx, 10h
0x1800429ab  or      ecx, eax
0x1800429ad  shl     ecx, 8
0x1800429b0  or      ecx, edx
0x1800429b2  mov     [r11+rbx+18h], ecx
0x1800429b7  movzx   eax, byte ptr [r9+7]
0x1800429bc  add     r9, rsi
0x1800429bf  movzx   edx, byte ptr [rdi+7]
0x1800429c3  add     rdi, rsi
0x1800429c6  movzx   ecx, byte ptr [r8+0Fh]
0x1800429cb  shl     ecx, 10h
0x1800429ce  shl     edx, 10h
0x1800429d1  or      edx, eax
0x1800429d3  movzx   eax, byte ptr [r8+0Eh]
0x1800429d8  or      ecx, eax
0x1800429da  shl     ecx, 8
0x1800429dd  or      ecx, edx
0x1800429df  mov     [rbx+1Ch], ecx
0x1800429e2  movzx   ecx, byte ptr [r10+r8+0Fh]
0x1800429e8  movzx   eax, byte ptr [r10+r8+0Eh]
0x1800429ee  add     r8, r15
0x1800429f1  shl     ecx, 10h
0x1800429f4  or      ecx, eax
0x1800429f6  shl     ecx, 8
0x1800429f9  or      ecx, edx
0x1800429fb  mov     [r11+rbx+1Ch], ecx
0x180042a00  add     rbx, r14
0x180042a03  sub     ebp, 1
0x180042a06  jnz     loc_1800427FD
0x180042a0c  pop     r15
0x180042a0e  pop     r14
0x180042a10  pop     rdi
0x180042a11  pop     rsi
0x180042a12  pop     rbp
0x180042a13  pop     rbx
0x180042a14  retn
```
