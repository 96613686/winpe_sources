# UpdateDstBlkYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x1800183b0`
- end: `0x1800184f1`
- name: `?UpdateDstBlkYUY2@@YAXPEAEPEBE11JJJ@Z`
- size: `321`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800183b0`

## pseudocode

```c
void __fastcall UpdateDstBlkYUY2(
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
  int v14; // eax
  int v15; // edx
  int v16; // edx
  int v17; // ecx
  int v18; // eax

  v10 = 4;
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
    v14 = a3[3];
    a3 += a6;
    v15 = a4[3];
    a4 += a6;
    v16 = (v14 | (v15 << 16)) << 8;
    *((_DWORD *)a1 + 3) = v16 | a2[6] | (a2[7] << 16);
    v17 = a2[a5 + 7];
    v18 = a2[a5 + 6];
    a2 += 2 * a5;
    *(_DWORD *)&a1[a7 + 12] = v16 | v18 | (v17 << 16);
    a1 += 2 * a7;
    --v10;
  }
  while ( v10 );
}

```

## disassembly

```asm
0x1800183b0  push    rbx
0x1800183b2  push    rbp
0x1800183b3  push    rsi
0x1800183b4  push    rdi
0x1800183b5  push    r12
0x1800183b7  push    r14
0x1800183b9  push    r15
0x1800183bb  movsxd  rbx, [rsp+38h+arg_30]
0x1800183c0  mov     rsi, r8
0x1800183c3  movsxd  r10, [rsp+38h+arg_20]
0x1800183c8  mov     r11, rdx
0x1800183cb  movsxd  rbp, [rsp+38h+arg_28]
0x1800183d0  mov     rdi, rcx
0x1800183d3  mov     r14d, 4
0x1800183d9  lea     r15, [rbx+rbx]
0x1800183dd  lea     r12, [r10+r10]
0x1800183e1  movzx   eax, byte ptr [rsi]
0x1800183e4  movzx   r8d, byte ptr [r9]
0x1800183e8  movzx   ecx, byte ptr [r11+1]
0x1800183ed  shl     ecx, 10h
0x1800183f0  shl     r8d, 10h
0x1800183f4  or      r8d, eax
0x1800183f7  movzx   eax, byte ptr [r11]
0x1800183fb  or      ecx, eax
0x1800183fd  shl     r8d, 8
0x180018401  or      ecx, r8d
0x180018404  mov     [rdi], ecx
0x180018406  movzx   eax, byte ptr [r10+r11]
0x18001840b  movzx   ecx, byte ptr [r10+r11+1]
0x180018411  shl     ecx, 10h
0x180018414  or      ecx, eax
0x180018416  or      ecx, r8d
0x180018419  mov     [rbx+rdi], ecx
0x18001841c  movzx   eax, byte ptr [rsi+1]
0x180018420  movzx   edx, byte ptr [r9+1]
0x180018425  movzx   ecx, byte ptr [r11+3]
0x18001842a  shl     ecx, 10h
0x18001842d  shl     edx, 10h
0x180018430  or      edx, eax
0x180018432  movzx   eax, byte ptr [r11+2]
0x180018437  or      ecx, eax
0x180018439  shl     edx, 8
0x18001843c  or      ecx, edx
0x18001843e  mov     [rdi+4], ecx
0x180018441  movzx   eax, byte ptr [r10+r11+2]
0x180018447  movzx   ecx, byte ptr [r10+r11+3]
0x18001844d  shl     ecx, 10h
0x180018450  or      ecx, eax
0x180018452  or      ecx, edx
0x180018454  mov     [rbx+rdi+4], ecx
0x180018458  movzx   eax, byte ptr [rsi+2]
0x18001845c  movzx   edx, byte ptr [r9+2]
0x180018461  movzx   ecx, byte ptr [r11+5]
0x180018466  shl     ecx, 10h
0x180018469  shl     edx, 10h
0x18001846c  or      edx, eax
0x18001846e  movzx   eax, byte ptr [r11+4]
0x180018473  or      ecx, eax
0x180018475  shl     edx, 8
0x180018478  or      ecx, edx
0x18001847a  mov     [rdi+8], ecx
0x18001847d  movzx   eax, byte ptr [r10+r11+4]
0x180018483  movzx   ecx, byte ptr [r10+r11+5]
0x180018489  shl     ecx, 10h
0x18001848c  or      ecx, eax
0x18001848e  or      ecx, edx
0x180018490  mov     [rbx+rdi+8], ecx
0x180018494  movzx   eax, byte ptr [rsi+3]
0x180018498  add     rsi, rbp
0x18001849b  movzx   edx, byte ptr [r9+3]
0x1800184a0  add     r9, rbp
0x1800184a3  movzx   ecx, byte ptr [r11+7]
0x1800184a8  shl     ecx, 10h
0x1800184ab  shl     edx, 10h
0x1800184ae  or      edx, eax
0x1800184b0  movzx   eax, byte ptr [r11+6]
0x1800184b5  or      ecx, eax
0x1800184b7  shl     edx, 8
0x1800184ba  or      ecx, edx
0x1800184bc  mov     [rdi+0Ch], ecx
0x1800184bf  movzx   ecx, byte ptr [r10+r11+7]
0x1800184c5  movzx   eax, byte ptr [r10+r11+6]
0x1800184cb  add     r11, r12
0x1800184ce  shl     ecx, 10h
0x1800184d1  or      ecx, eax
0x1800184d3  or      ecx, edx
0x1800184d5  mov     [rbx+rdi+0Ch], ecx
0x1800184d9  add     rdi, r15
0x1800184dc  sub     r14d, 1
0x1800184e0  jnz     loc_1800183E1
0x1800184e6  pop     r15
0x1800184e8  pop     r14
0x1800184ea  pop     r12
0x1800184ec  pop     rdi
0x1800184ed  pop     rsi
0x1800184ee  pop     rbp
0x1800184ef  pop     rbx
0x1800184f0  retn
```
