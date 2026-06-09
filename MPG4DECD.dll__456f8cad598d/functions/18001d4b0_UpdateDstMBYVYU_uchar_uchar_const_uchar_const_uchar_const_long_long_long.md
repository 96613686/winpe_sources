# UpdateDstMBYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18001d4b0`
- end: `0x18001d6e2`
- name: `?UpdateDstMBYVYU@@YAXPEAEPEBE11JJJ@Z`
- size: `562`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001de70`

## callees

- `0x18001d4b0`

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
0x18001d4b0  push    rbx
0x18001d4b2  push    rbp
0x18001d4b3  push    rsi
0x18001d4b4  push    rdi
0x18001d4b5  push    r12
0x18001d4b7  push    r14
0x18001d4b9  push    r15
0x18001d4bb  movsxd  rbx, [rsp+38h+arg_30]
0x18001d4c0  mov     rsi, r8
0x18001d4c3  movsxd  r10, [rsp+38h+arg_20]
0x18001d4c8  mov     r11, rdx
0x18001d4cb  movsxd  rbp, [rsp+38h+arg_28]
0x18001d4d0  mov     rdi, rcx
0x18001d4d3  mov     r14d, 8
0x18001d4d9  lea     r15, [rbx+rbx]
0x18001d4dd  lea     r12, [r10+r10]
0x18001d4e1  movzx   eax, byte ptr [r9]
0x18001d4e5  movzx   r8d, byte ptr [rsi]
0x18001d4e9  movzx   ecx, byte ptr [r11+1]
0x18001d4ee  shl     ecx, 10h
0x18001d4f1  shl     r8d, 10h
0x18001d4f5  or      r8d, eax
0x18001d4f8  movzx   eax, byte ptr [r11]
0x18001d4fc  or      ecx, eax
0x18001d4fe  shl     r8d, 8
0x18001d502  or      ecx, r8d
0x18001d505  mov     [rdi], ecx
0x18001d507  movzx   eax, byte ptr [r10+r11]
0x18001d50c  movzx   ecx, byte ptr [r10+r11+1]
0x18001d512  shl     ecx, 10h
0x18001d515  or      ecx, eax
0x18001d517  or      ecx, r8d
0x18001d51a  mov     [rbx+rdi], ecx
0x18001d51d  movzx   eax, byte ptr [r9+1]
0x18001d522  movzx   edx, byte ptr [rsi+1]
0x18001d526  movzx   ecx, byte ptr [r11+3]
0x18001d52b  shl     ecx, 10h
0x18001d52e  shl     edx, 10h
0x18001d531  or      edx, eax
0x18001d533  movzx   eax, byte ptr [r11+2]
0x18001d538  or      ecx, eax
0x18001d53a  shl     edx, 8
0x18001d53d  or      ecx, edx
0x18001d53f  mov     [rdi+4], ecx
0x18001d542  movzx   eax, byte ptr [r10+r11+2]
0x18001d548  movzx   ecx, byte ptr [r10+r11+3]
0x18001d54e  shl     ecx, 10h
0x18001d551  or      ecx, eax
0x18001d553  or      ecx, edx
0x18001d555  mov     [rbx+rdi+4], ecx
0x18001d559  movzx   eax, byte ptr [r9+2]
0x18001d55e  movzx   edx, byte ptr [rsi+2]
0x18001d562  movzx   ecx, byte ptr [r11+5]
0x18001d567  shl     ecx, 10h
0x18001d56a  shl     edx, 10h
0x18001d56d  or      edx, eax
0x18001d56f  movzx   eax, byte ptr [r11+4]
0x18001d574  or      ecx, eax
0x18001d576  shl     edx, 8
0x18001d579  or      ecx, edx
0x18001d57b  mov     [rdi+8], ecx
0x18001d57e  movzx   eax, byte ptr [r10+r11+4]
0x18001d584  movzx   ecx, byte ptr [r10+r11+5]
0x18001d58a  shl     ecx, 10h
0x18001d58d  or      ecx, eax
0x18001d58f  or      ecx, edx
0x18001d591  mov     [rbx+rdi+8], ecx
0x18001d595  movzx   eax, byte ptr [r9+3]
0x18001d59a  movzx   edx, byte ptr [rsi+3]
0x18001d59e  movzx   ecx, byte ptr [r11+7]
0x18001d5a3  shl     ecx, 10h
0x18001d5a6  shl     edx, 10h
0x18001d5a9  or      edx, eax
0x18001d5ab  movzx   eax, byte ptr [r11+6]
0x18001d5b0  or      ecx, eax
0x18001d5b2  shl     edx, 8
0x18001d5b5  or      ecx, edx
0x18001d5b7  mov     [rdi+0Ch], ecx
0x18001d5ba  movzx   eax, byte ptr [r10+r11+6]
0x18001d5c0  movzx   ecx, byte ptr [r10+r11+7]
0x18001d5c6  shl     ecx, 10h
0x18001d5c9  or      ecx, eax
0x18001d5cb  or      ecx, edx
0x18001d5cd  mov     [rbx+rdi+0Ch], ecx
0x18001d5d1  movzx   eax, byte ptr [r9+4]
0x18001d5d6  movzx   edx, byte ptr [rsi+4]
0x18001d5da  movzx   ecx, byte ptr [r11+9]
0x18001d5df  shl     ecx, 10h
0x18001d5e2  shl     edx, 10h
0x18001d5e5  or      edx, eax
0x18001d5e7  movzx   eax, byte ptr [r11+8]
0x18001d5ec  or      ecx, eax
0x18001d5ee  shl     edx, 8
0x18001d5f1  or      ecx, edx
0x18001d5f3  mov     [rdi+10h], ecx
0x18001d5f6  movzx   ecx, byte ptr [r10+r11+9]
0x18001d5fc  shl     ecx, 10h
0x18001d5ff  movzx   eax, byte ptr [r10+r11+8]
0x18001d605  or      ecx, eax
0x18001d607  or      ecx, edx
0x18001d609  mov     [rbx+rdi+10h], ecx
0x18001d60d  movzx   eax, byte ptr [r9+5]
0x18001d612  movzx   edx, byte ptr [rsi+5]
0x18001d616  movzx   ecx, byte ptr [r11+0Bh]
0x18001d61b  shl     ecx, 10h
0x18001d61e  shl     edx, 10h
0x18001d621  or      edx, eax
0x18001d623  movzx   eax, byte ptr [r11+0Ah]
0x18001d628  or      ecx, eax
0x18001d62a  shl     edx, 8
0x18001d62d  or      ecx, edx
0x18001d62f  mov     [rdi+14h], ecx
0x18001d632  movzx   eax, byte ptr [r10+r11+0Ah]
0x18001d638  movzx   ecx, byte ptr [r10+r11+0Bh]
0x18001d63e  shl     ecx, 10h
0x18001d641  or      ecx, eax
0x18001d643  or      ecx, edx
0x18001d645  mov     [rbx+rdi+14h], ecx
0x18001d649  movzx   eax, byte ptr [r9+6]
0x18001d64e  movzx   edx, byte ptr [rsi+6]
0x18001d652  movzx   ecx, byte ptr [r11+0Dh]
0x18001d657  shl     ecx, 10h
0x18001d65a  shl     edx, 10h
0x18001d65d  or      edx, eax
0x18001d65f  movzx   eax, byte ptr [r11+0Ch]
0x18001d664  or      ecx, eax
0x18001d666  shl     edx, 8
0x18001d669  or      ecx, edx
0x18001d66b  mov     [rdi+18h], ecx
0x18001d66e  movzx   eax, byte ptr [r10+r11+0Ch]
0x18001d674  movzx   ecx, byte ptr [r10+r11+0Dh]
0x18001d67a  shl     ecx, 10h
0x18001d67d  or      ecx, eax
0x18001d67f  or      ecx, edx
0x18001d681  mov     [rbx+rdi+18h], ecx
0x18001d685  movzx   eax, byte ptr [r9+7]
0x18001d68a  add     r9, rbp
0x18001d68d  movzx   edx, byte ptr [rsi+7]
0x18001d691  add     rsi, rbp
0x18001d694  movzx   ecx, byte ptr [r11+0Fh]
0x18001d699  shl     ecx, 10h
0x18001d69c  shl     edx, 10h
0x18001d69f  or      edx, eax
0x18001d6a1  movzx   eax, byte ptr [r11+0Eh]
0x18001d6a6  or      ecx, eax
0x18001d6a8  shl     edx, 8
0x18001d6ab  or      ecx, edx
0x18001d6ad  mov     [rdi+1Ch], ecx
0x18001d6b0  movzx   ecx, byte ptr [r10+r11+0Fh]
0x18001d6b6  movzx   eax, byte ptr [r10+r11+0Eh]
0x18001d6bc  add     r11, r12
0x18001d6bf  shl     ecx, 10h
0x18001d6c2  or      ecx, eax
0x18001d6c4  or      ecx, edx
0x18001d6c6  mov     [rbx+rdi+1Ch], ecx
0x18001d6ca  add     rdi, r15
0x18001d6cd  sub     r14d, 1
0x18001d6d1  jnz     loc_18001D4E1
0x18001d6d7  pop     r15
0x18001d6d9  pop     r14
0x18001d6db  pop     r12
0x18001d6dd  pop     rdi
0x18001d6de  pop     rsi
0x18001d6df  pop     rbp
0x18001d6e0  pop     rbx
0x18001d6e1  retn
```
