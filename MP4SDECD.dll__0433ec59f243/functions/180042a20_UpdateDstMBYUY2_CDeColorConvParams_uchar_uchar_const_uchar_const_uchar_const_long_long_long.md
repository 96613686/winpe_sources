# UpdateDstMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180042a20`
- end: `0x180042c4d`
- name: `?UpdateDstMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `557`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800435a0`

## callees

- `0x180042a20`

## pseudocode

```c
void __fastcall UpdateDstMBYUY2(
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
    v11 = (*a4 | (*a5 << 16)) << 8;
    *(_DWORD *)a2 = v11 | *a3 | (a3[1] << 16);
    *(_DWORD *)&a2[a8] = v11 | a3[a6] | (a3[a6 + 1] << 16);
    v12 = (a4[1] | (a5[1] << 16)) << 8;
    *((_DWORD *)a2 + 1) = v12 | a3[2] | (a3[3] << 16);
    *(_DWORD *)&a2[a8 + 4] = v12 | a3[a6 + 2] | (a3[a6 + 3] << 16);
    v13 = (a4[2] | (a5[2] << 16)) << 8;
    *((_DWORD *)a2 + 2) = v13 | a3[4] | (a3[5] << 16);
    *(_DWORD *)&a2[a8 + 8] = v13 | a3[a6 + 4] | (a3[a6 + 5] << 16);
    v14 = (a4[3] | (a5[3] << 16)) << 8;
    *((_DWORD *)a2 + 3) = v14 | a3[6] | (a3[7] << 16);
    *(_DWORD *)&a2[a8 + 12] = v14 | a3[a6 + 6] | (a3[a6 + 7] << 16);
    v15 = (a4[4] | (a5[4] << 16)) << 8;
    *((_DWORD *)a2 + 4) = v15 | a3[8] | (a3[9] << 16);
    *(_DWORD *)&a2[a8 + 16] = v15 | a3[a6 + 8] | (a3[a6 + 9] << 16);
    v16 = (a4[5] | (a5[5] << 16)) << 8;
    *((_DWORD *)a2 + 5) = v16 | a3[10] | (a3[11] << 16);
    *(_DWORD *)&a2[a8 + 20] = v16 | a3[a6 + 10] | (a3[a6 + 11] << 16);
    v17 = (a4[6] | (a5[6] << 16)) << 8;
    *((_DWORD *)a2 + 6) = v17 | a3[12] | (a3[13] << 16);
    *(_DWORD *)&a2[a8 + 24] = v17 | a3[a6 + 12] | (a3[a6 + 13] << 16);
    v18 = a4[7];
    a4 += a7;
    v19 = a5[7];
    a5 += a7;
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
0x180042a20  push    rbx
0x180042a22  push    rbp
0x180042a23  push    rsi
0x180042a24  push    rdi
0x180042a25  push    r14
0x180042a27  push    r15
0x180042a29  movsxd  r11, [rsp+30h+arg_38]
0x180042a2e  mov     rbx, rdx
0x180042a31  movsxd  r10, [rsp+30h+arg_28]
0x180042a36  mov     ebp, 8
0x180042a3b  movsxd  rsi, [rsp+30h+arg_30]
0x180042a40  mov     rdi, [rsp+30h+arg_20]
0x180042a45  lea     r14, [r11+r11]
0x180042a49  lea     r15, [r10+r10]
0x180042a4d  movzx   eax, byte ptr [r9]
0x180042a51  movzx   edx, byte ptr [rdi]
0x180042a54  movzx   ecx, byte ptr [r8+1]
0x180042a59  shl     ecx, 10h
0x180042a5c  shl     edx, 10h
0x180042a5f  or      edx, eax
0x180042a61  movzx   eax, byte ptr [r8]
0x180042a65  or      ecx, eax
0x180042a67  shl     edx, 8
0x180042a6a  or      ecx, edx
0x180042a6c  mov     [rbx], ecx
0x180042a6e  movzx   eax, byte ptr [r10+r8]
0x180042a73  movzx   ecx, byte ptr [r10+r8+1]
0x180042a79  shl     ecx, 10h
0x180042a7c  or      ecx, eax
0x180042a7e  or      ecx, edx
0x180042a80  mov     [r11+rbx], ecx
0x180042a84  movzx   eax, byte ptr [r9+1]
0x180042a89  movzx   edx, byte ptr [rdi+1]
0x180042a8d  movzx   ecx, byte ptr [r8+3]
0x180042a92  shl     ecx, 10h
0x180042a95  shl     edx, 10h
0x180042a98  or      edx, eax
0x180042a9a  movzx   eax, byte ptr [r8+2]
0x180042a9f  or      ecx, eax
0x180042aa1  shl     edx, 8
0x180042aa4  or      ecx, edx
0x180042aa6  mov     [rbx+4], ecx
0x180042aa9  movzx   eax, byte ptr [r10+r8+2]
0x180042aaf  movzx   ecx, byte ptr [r10+r8+3]
0x180042ab5  shl     ecx, 10h
0x180042ab8  or      ecx, eax
0x180042aba  or      ecx, edx
0x180042abc  mov     [r11+rbx+4], ecx
0x180042ac1  movzx   eax, byte ptr [r9+2]
0x180042ac6  movzx   edx, byte ptr [rdi+2]
0x180042aca  movzx   ecx, byte ptr [r8+5]
0x180042acf  shl     ecx, 10h
0x180042ad2  shl     edx, 10h
0x180042ad5  or      edx, eax
0x180042ad7  movzx   eax, byte ptr [r8+4]
0x180042adc  or      ecx, eax
0x180042ade  shl     edx, 8
0x180042ae1  or      ecx, edx
0x180042ae3  mov     [rbx+8], ecx
0x180042ae6  movzx   eax, byte ptr [r10+r8+4]
0x180042aec  movzx   ecx, byte ptr [r10+r8+5]
0x180042af2  shl     ecx, 10h
0x180042af5  or      ecx, eax
0x180042af7  or      ecx, edx
0x180042af9  mov     [r11+rbx+8], ecx
0x180042afe  movzx   eax, byte ptr [r9+3]
0x180042b03  movzx   edx, byte ptr [rdi+3]
0x180042b07  movzx   ecx, byte ptr [r8+7]
0x180042b0c  shl     ecx, 10h
0x180042b0f  shl     edx, 10h
0x180042b12  or      edx, eax
0x180042b14  movzx   eax, byte ptr [r8+6]
0x180042b19  or      ecx, eax
0x180042b1b  shl     edx, 8
0x180042b1e  or      ecx, edx
0x180042b20  mov     [rbx+0Ch], ecx
0x180042b23  movzx   eax, byte ptr [r10+r8+6]
0x180042b29  movzx   ecx, byte ptr [r10+r8+7]
0x180042b2f  shl     ecx, 10h
0x180042b32  or      ecx, eax
0x180042b34  or      ecx, edx
0x180042b36  mov     [r11+rbx+0Ch], ecx
0x180042b3b  movzx   eax, byte ptr [r9+4]
0x180042b40  movzx   edx, byte ptr [rdi+4]
0x180042b44  movzx   ecx, byte ptr [r8+9]
0x180042b49  shl     ecx, 10h
0x180042b4c  shl     edx, 10h
0x180042b4f  or      edx, eax
0x180042b51  movzx   eax, byte ptr [r8+8]
0x180042b56  or      ecx, eax
0x180042b58  shl     edx, 8
0x180042b5b  or      ecx, edx
0x180042b5d  mov     [rbx+10h], ecx
0x180042b60  movzx   ecx, byte ptr [r10+r8+9]
0x180042b66  shl     ecx, 10h
0x180042b69  movzx   eax, byte ptr [r10+r8+8]
0x180042b6f  or      ecx, eax
0x180042b71  or      ecx, edx
0x180042b73  mov     [r11+rbx+10h], ecx
0x180042b78  movzx   eax, byte ptr [r9+5]
0x180042b7d  movzx   edx, byte ptr [rdi+5]
0x180042b81  movzx   ecx, byte ptr [r8+0Bh]
0x180042b86  shl     ecx, 10h
0x180042b89  shl     edx, 10h
0x180042b8c  or      edx, eax
0x180042b8e  movzx   eax, byte ptr [r8+0Ah]
0x180042b93  or      ecx, eax
0x180042b95  shl     edx, 8
0x180042b98  or      ecx, edx
0x180042b9a  mov     [rbx+14h], ecx
0x180042b9d  movzx   eax, byte ptr [r10+r8+0Ah]
0x180042ba3  movzx   ecx, byte ptr [r10+r8+0Bh]
0x180042ba9  shl     ecx, 10h
0x180042bac  or      ecx, eax
0x180042bae  or      ecx, edx
0x180042bb0  mov     [r11+rbx+14h], ecx
0x180042bb5  movzx   eax, byte ptr [r9+6]
0x180042bba  movzx   edx, byte ptr [rdi+6]
0x180042bbe  movzx   ecx, byte ptr [r8+0Dh]
0x180042bc3  shl     ecx, 10h
0x180042bc6  shl     edx, 10h
0x180042bc9  or      edx, eax
0x180042bcb  movzx   eax, byte ptr [r8+0Ch]
0x180042bd0  or      ecx, eax
0x180042bd2  shl     edx, 8
0x180042bd5  or      ecx, edx
0x180042bd7  mov     [rbx+18h], ecx
0x180042bda  movzx   eax, byte ptr [r10+r8+0Ch]
0x180042be0  movzx   ecx, byte ptr [r10+r8+0Dh]
0x180042be6  shl     ecx, 10h
0x180042be9  or      ecx, eax
0x180042beb  or      ecx, edx
0x180042bed  mov     [r11+rbx+18h], ecx
0x180042bf2  movzx   eax, byte ptr [r9+7]
0x180042bf7  add     r9, rsi
0x180042bfa  movzx   edx, byte ptr [rdi+7]
0x180042bfe  add     rdi, rsi
0x180042c01  movzx   ecx, byte ptr [r8+0Fh]
0x180042c06  shl     ecx, 10h
0x180042c09  shl     edx, 10h
0x180042c0c  or      edx, eax
0x180042c0e  movzx   eax, byte ptr [r8+0Eh]
0x180042c13  or      ecx, eax
0x180042c15  shl     edx, 8
0x180042c18  or      ecx, edx
0x180042c1a  mov     [rbx+1Ch], ecx
0x180042c1d  movzx   ecx, byte ptr [r10+r8+0Fh]
0x180042c23  movzx   eax, byte ptr [r10+r8+0Eh]
0x180042c29  add     r8, r15
0x180042c2c  shl     ecx, 10h
0x180042c2f  or      ecx, eax
0x180042c31  or      ecx, edx
0x180042c33  mov     [r11+rbx+1Ch], ecx
0x180042c38  add     rbx, r14
0x180042c3b  sub     ebp, 1
0x180042c3e  jnz     loc_180042A4D
0x180042c44  pop     r15
0x180042c46  pop     r14
0x180042c48  pop     rdi
0x180042c49  pop     rsi
0x180042c4a  pop     rbp
0x180042c4b  pop     rbx
0x180042c4c  retn
```
