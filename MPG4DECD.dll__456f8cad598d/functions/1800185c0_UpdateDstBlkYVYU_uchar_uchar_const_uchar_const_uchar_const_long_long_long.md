# UpdateDstBlkYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x1800185c0`
- end: `0x180018702`
- name: `?UpdateDstBlkYVYU@@YAXPEAEPEBE11JJJ@Z`
- size: `322`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800185c0`

## pseudocode

```c
void __fastcall UpdateDstBlkYVYU(
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
    v11 = (*a4 | (*a3 << 16)) << 8;
    *(_DWORD *)a1 = v11 | *a2 | (a2[1] << 16);
    *(_DWORD *)&a1[a7] = v11 | a2[a5] | (a2[a5 + 1] << 16);
    v12 = (a4[1] | (a3[1] << 16)) << 8;
    *((_DWORD *)a1 + 1) = v12 | a2[2] | (a2[3] << 16);
    *(_DWORD *)&a1[a7 + 4] = v12 | a2[a5 + 2] | (a2[a5 + 3] << 16);
    v13 = (a4[2] | (a3[2] << 16)) << 8;
    *((_DWORD *)a1 + 2) = v13 | a2[4] | (a2[5] << 16);
    *(_DWORD *)&a1[a7 + 8] = v13 | a2[a5 + 4] | (a2[a5 + 5] << 16);
    v14 = a4[3];
    a4 += a6;
    v15 = a3[3];
    a3 += a6;
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
0x1800185c0  push    rbx
0x1800185c2  push    rbp
0x1800185c3  push    rsi
0x1800185c4  push    rdi
0x1800185c5  push    r12
0x1800185c7  push    r14
0x1800185c9  push    r15
0x1800185cb  movsxd  rbx, [rsp+38h+arg_30]
0x1800185d0  mov     rsi, r8
0x1800185d3  movsxd  r10, [rsp+38h+arg_20]
0x1800185d8  mov     r11, rdx
0x1800185db  movsxd  rbp, [rsp+38h+arg_28]
0x1800185e0  mov     rdi, rcx
0x1800185e3  mov     r14d, 4
0x1800185e9  lea     r15, [rbx+rbx]
0x1800185ed  lea     r12, [r10+r10]
0x1800185f1  movzx   eax, byte ptr [r9]
0x1800185f5  movzx   r8d, byte ptr [rsi]
0x1800185f9  movzx   ecx, byte ptr [r11+1]
0x1800185fe  shl     ecx, 10h
0x180018601  shl     r8d, 10h
0x180018605  or      r8d, eax
0x180018608  movzx   eax, byte ptr [r11]
0x18001860c  or      ecx, eax
0x18001860e  shl     r8d, 8
0x180018612  or      ecx, r8d
0x180018615  mov     [rdi], ecx
0x180018617  movzx   eax, byte ptr [r10+r11]
0x18001861c  movzx   ecx, byte ptr [r10+r11+1]
0x180018622  shl     ecx, 10h
0x180018625  or      ecx, eax
0x180018627  or      ecx, r8d
0x18001862a  mov     [rbx+rdi], ecx
0x18001862d  movzx   eax, byte ptr [r9+1]
0x180018632  movzx   edx, byte ptr [rsi+1]
0x180018636  movzx   ecx, byte ptr [r11+3]
0x18001863b  shl     ecx, 10h
0x18001863e  shl     edx, 10h
0x180018641  or      edx, eax
0x180018643  movzx   eax, byte ptr [r11+2]
0x180018648  or      ecx, eax
0x18001864a  shl     edx, 8
0x18001864d  or      ecx, edx
0x18001864f  mov     [rdi+4], ecx
0x180018652  movzx   eax, byte ptr [r10+r11+2]
0x180018658  movzx   ecx, byte ptr [r10+r11+3]
0x18001865e  shl     ecx, 10h
0x180018661  or      ecx, eax
0x180018663  or      ecx, edx
0x180018665  mov     [rbx+rdi+4], ecx
0x180018669  movzx   eax, byte ptr [r9+2]
0x18001866e  movzx   edx, byte ptr [rsi+2]
0x180018672  movzx   ecx, byte ptr [r11+5]
0x180018677  shl     ecx, 10h
0x18001867a  shl     edx, 10h
0x18001867d  or      edx, eax
0x18001867f  movzx   eax, byte ptr [r11+4]
0x180018684  or      ecx, eax
0x180018686  shl     edx, 8
0x180018689  or      ecx, edx
0x18001868b  mov     [rdi+8], ecx
0x18001868e  movzx   eax, byte ptr [r10+r11+4]
0x180018694  movzx   ecx, byte ptr [r10+r11+5]
0x18001869a  shl     ecx, 10h
0x18001869d  or      ecx, eax
0x18001869f  or      ecx, edx
0x1800186a1  mov     [rbx+rdi+8], ecx
0x1800186a5  movzx   eax, byte ptr [r9+3]
0x1800186aa  add     r9, rbp
0x1800186ad  movzx   edx, byte ptr [rsi+3]
0x1800186b1  add     rsi, rbp
0x1800186b4  movzx   ecx, byte ptr [r11+7]
0x1800186b9  shl     ecx, 10h
0x1800186bc  shl     edx, 10h
0x1800186bf  or      edx, eax
0x1800186c1  movzx   eax, byte ptr [r11+6]
0x1800186c6  or      ecx, eax
0x1800186c8  shl     edx, 8
0x1800186cb  or      ecx, edx
0x1800186cd  mov     [rdi+0Ch], ecx
0x1800186d0  movzx   ecx, byte ptr [r10+r11+7]
0x1800186d6  movzx   eax, byte ptr [r10+r11+6]
0x1800186dc  add     r11, r12
0x1800186df  shl     ecx, 10h
0x1800186e2  or      ecx, eax
0x1800186e4  or      ecx, edx
0x1800186e6  mov     [rbx+rdi+0Ch], ecx
0x1800186ea  add     rdi, r15
0x1800186ed  sub     r14d, 1
0x1800186f1  jnz     loc_1800185F1
0x1800186f7  pop     r15
0x1800186f9  pop     r14
0x1800186fb  pop     r12
0x1800186fd  pop     rdi
0x1800186fe  pop     rsi
0x1800186ff  pop     rbp
0x180018700  pop     rbx
0x180018701  retn
```
