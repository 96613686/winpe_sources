# UpdateDstBlkYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003eb50`
- end: `0x18003ec89`
- name: `?UpdateDstBlkYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `313`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003eb50`

## pseudocode

```c
void __fastcall UpdateDstBlkYVYU(
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
  int v14; // eax
  int v15; // edx
  int v16; // edx
  int v17; // ecx
  int v18; // eax

  v9 = 4;
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
    v14 = a5[3];
    a5 += a7;
    v15 = a4[3];
    a4 += a7;
    v16 = (v14 | (v15 << 16)) << 8;
    *((_DWORD *)a2 + 3) = v16 | a3[6] | (a3[7] << 16);
    v17 = a3[a6 + 7];
    v18 = a3[a6 + 6];
    a3 += 2 * a6;
    *(_DWORD *)&a2[a8 + 12] = v16 | v18 | (v17 << 16);
    a2 += 2 * a8;
    --v9;
  }
  while ( v9 );
}

```

## disassembly

```asm
0x18003eb50  push    rbx
0x18003eb52  push    rbp
0x18003eb53  push    rsi
0x18003eb54  push    rdi
0x18003eb55  push    r14
0x18003eb57  push    r15
0x18003eb59  movsxd  r11, [rsp+30h+arg_38]
0x18003eb5e  mov     rbx, rdx
0x18003eb61  movsxd  r10, [rsp+30h+arg_28]
0x18003eb66  mov     ebp, 4
0x18003eb6b  movsxd  rsi, [rsp+30h+arg_30]
0x18003eb70  mov     rdi, [rsp+30h+arg_20]
0x18003eb75  lea     r14, [r11+r11]
0x18003eb79  lea     r15, [r10+r10]
0x18003eb7d  movzx   eax, byte ptr [rdi]
0x18003eb80  movzx   edx, byte ptr [r9]
0x18003eb84  movzx   ecx, byte ptr [r8+1]
0x18003eb89  shl     ecx, 10h
0x18003eb8c  shl     edx, 10h
0x18003eb8f  or      edx, eax
0x18003eb91  movzx   eax, byte ptr [r8]
0x18003eb95  or      ecx, eax
0x18003eb97  shl     edx, 8
0x18003eb9a  or      ecx, edx
0x18003eb9c  mov     [rbx], ecx
0x18003eb9e  movzx   eax, byte ptr [r10+r8]
0x18003eba3  movzx   ecx, byte ptr [r10+r8+1]
0x18003eba9  shl     ecx, 10h
0x18003ebac  or      ecx, eax
0x18003ebae  or      ecx, edx
0x18003ebb0  mov     [r11+rbx], ecx
0x18003ebb4  movzx   eax, byte ptr [rdi+1]
0x18003ebb8  movzx   edx, byte ptr [r9+1]
0x18003ebbd  movzx   ecx, byte ptr [r8+3]
0x18003ebc2  shl     ecx, 10h
0x18003ebc5  shl     edx, 10h
0x18003ebc8  or      edx, eax
0x18003ebca  movzx   eax, byte ptr [r8+2]
0x18003ebcf  or      ecx, eax
0x18003ebd1  shl     edx, 8
0x18003ebd4  or      ecx, edx
0x18003ebd6  mov     [rbx+4], ecx
0x18003ebd9  movzx   eax, byte ptr [r10+r8+2]
0x18003ebdf  movzx   ecx, byte ptr [r10+r8+3]
0x18003ebe5  shl     ecx, 10h
0x18003ebe8  or      ecx, eax
0x18003ebea  or      ecx, edx
0x18003ebec  mov     [r11+rbx+4], ecx
0x18003ebf1  movzx   eax, byte ptr [rdi+2]
0x18003ebf5  movzx   edx, byte ptr [r9+2]
0x18003ebfa  movzx   ecx, byte ptr [r8+5]
0x18003ebff  shl     ecx, 10h
0x18003ec02  shl     edx, 10h
0x18003ec05  or      edx, eax
0x18003ec07  movzx   eax, byte ptr [r8+4]
0x18003ec0c  or      ecx, eax
0x18003ec0e  shl     edx, 8
0x18003ec11  or      ecx, edx
0x18003ec13  mov     [rbx+8], ecx
0x18003ec16  movzx   eax, byte ptr [r10+r8+4]
0x18003ec1c  movzx   ecx, byte ptr [r10+r8+5]
0x18003ec22  shl     ecx, 10h
0x18003ec25  or      ecx, eax
0x18003ec27  or      ecx, edx
0x18003ec29  mov     [r11+rbx+8], ecx
0x18003ec2e  movzx   eax, byte ptr [rdi+3]
0x18003ec32  add     rdi, rsi
0x18003ec35  movzx   edx, byte ptr [r9+3]
0x18003ec3a  add     r9, rsi
0x18003ec3d  movzx   ecx, byte ptr [r8+7]
0x18003ec42  shl     ecx, 10h
0x18003ec45  shl     edx, 10h
0x18003ec48  or      edx, eax
0x18003ec4a  movzx   eax, byte ptr [r8+6]
0x18003ec4f  or      ecx, eax
0x18003ec51  shl     edx, 8
0x18003ec54  or      ecx, edx
0x18003ec56  mov     [rbx+0Ch], ecx
0x18003ec59  movzx   ecx, byte ptr [r10+r8+7]
0x18003ec5f  movzx   eax, byte ptr [r10+r8+6]
0x18003ec65  add     r8, r15
0x18003ec68  shl     ecx, 10h
0x18003ec6b  or      ecx, eax
0x18003ec6d  or      ecx, edx
0x18003ec6f  mov     [r11+rbx+0Ch], ecx
0x18003ec74  add     rbx, r14
0x18003ec77  sub     ebp, 1
0x18003ec7a  jnz     loc_18003EB7D
0x18003ec80  pop     r15
0x18003ec82  pop     r14
0x18003ec84  pop     rdi
0x18003ec85  pop     rsi
0x18003ec86  pop     rbp
0x18003ec87  pop     rbx
0x18003ec88  retn
```
