# UpdateDstBlkYVYU(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180018500`
- end: `0x180018642`
- name: `?UpdateDstBlkYVYU@@YAXPEAEPEBE11JJJ@Z`
- size: `322`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180018500`

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
0x180018500  push    rbx
0x180018502  push    rbp
0x180018503  push    rsi
0x180018504  push    rdi
0x180018505  push    r12
0x180018507  push    r14
0x180018509  push    r15
0x18001850b  movsxd  rbx, [rsp+38h+arg_30]
0x180018510  mov     rsi, r8
0x180018513  movsxd  r10, [rsp+38h+arg_20]
0x180018518  mov     r11, rdx
0x18001851b  movsxd  rbp, [rsp+38h+arg_28]
0x180018520  mov     rdi, rcx
0x180018523  mov     r14d, 4
0x180018529  lea     r15, [rbx+rbx]
0x18001852d  lea     r12, [r10+r10]
0x180018531  movzx   eax, byte ptr [r9]
0x180018535  movzx   r8d, byte ptr [rsi]
0x180018539  movzx   ecx, byte ptr [r11+1]
0x18001853e  shl     ecx, 10h
0x180018541  shl     r8d, 10h
0x180018545  or      r8d, eax
0x180018548  movzx   eax, byte ptr [r11]
0x18001854c  or      ecx, eax
0x18001854e  shl     r8d, 8
0x180018552  or      ecx, r8d
0x180018555  mov     [rdi], ecx
0x180018557  movzx   eax, byte ptr [r10+r11]
0x18001855c  movzx   ecx, byte ptr [r10+r11+1]
0x180018562  shl     ecx, 10h
0x180018565  or      ecx, eax
0x180018567  or      ecx, r8d
0x18001856a  mov     [rbx+rdi], ecx
0x18001856d  movzx   eax, byte ptr [r9+1]
0x180018572  movzx   edx, byte ptr [rsi+1]
0x180018576  movzx   ecx, byte ptr [r11+3]
0x18001857b  shl     ecx, 10h
0x18001857e  shl     edx, 10h
0x180018581  or      edx, eax
0x180018583  movzx   eax, byte ptr [r11+2]
0x180018588  or      ecx, eax
0x18001858a  shl     edx, 8
0x18001858d  or      ecx, edx
0x18001858f  mov     [rdi+4], ecx
0x180018592  movzx   eax, byte ptr [r10+r11+2]
0x180018598  movzx   ecx, byte ptr [r10+r11+3]
0x18001859e  shl     ecx, 10h
0x1800185a1  or      ecx, eax
0x1800185a3  or      ecx, edx
0x1800185a5  mov     [rbx+rdi+4], ecx
0x1800185a9  movzx   eax, byte ptr [r9+2]
0x1800185ae  movzx   edx, byte ptr [rsi+2]
0x1800185b2  movzx   ecx, byte ptr [r11+5]
0x1800185b7  shl     ecx, 10h
0x1800185ba  shl     edx, 10h
0x1800185bd  or      edx, eax
0x1800185bf  movzx   eax, byte ptr [r11+4]
0x1800185c4  or      ecx, eax
0x1800185c6  shl     edx, 8
0x1800185c9  or      ecx, edx
0x1800185cb  mov     [rdi+8], ecx
0x1800185ce  movzx   eax, byte ptr [r10+r11+4]
0x1800185d4  movzx   ecx, byte ptr [r10+r11+5]
0x1800185da  shl     ecx, 10h
0x1800185dd  or      ecx, eax
0x1800185df  or      ecx, edx
0x1800185e1  mov     [rbx+rdi+8], ecx
0x1800185e5  movzx   eax, byte ptr [r9+3]
0x1800185ea  add     r9, rbp
0x1800185ed  movzx   edx, byte ptr [rsi+3]
0x1800185f1  add     rsi, rbp
0x1800185f4  movzx   ecx, byte ptr [r11+7]
0x1800185f9  shl     ecx, 10h
0x1800185fc  shl     edx, 10h
0x1800185ff  or      edx, eax
0x180018601  movzx   eax, byte ptr [r11+6]
0x180018606  or      ecx, eax
0x180018608  shl     edx, 8
0x18001860b  or      ecx, edx
0x18001860d  mov     [rdi+0Ch], ecx
0x180018610  movzx   ecx, byte ptr [r10+r11+7]
0x180018616  movzx   eax, byte ptr [r10+r11+6]
0x18001861c  add     r11, r12
0x18001861f  shl     ecx, 10h
0x180018622  or      ecx, eax
0x180018624  or      ecx, edx
0x180018626  mov     [rbx+rdi+0Ch], ecx
0x18001862a  add     rdi, r15
0x18001862d  sub     r14d, 1
0x180018631  jnz     loc_180018531
0x180018637  pop     r15
0x180018639  pop     r14
0x18001863b  pop     r12
0x18001863d  pop     rdi
0x18001863e  pop     rsi
0x18001863f  pop     rbp
0x180018640  pop     rbx
0x180018641  retn
```
