# UpdateDstBlkYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180018470`
- end: `0x1800185b1`
- name: `?UpdateDstBlkYUY2@@YAXPEAEPEBE11JJJ@Z`
- size: `321`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180018470`

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
0x180018470  push    rbx
0x180018472  push    rbp
0x180018473  push    rsi
0x180018474  push    rdi
0x180018475  push    r12
0x180018477  push    r14
0x180018479  push    r15
0x18001847b  movsxd  rbx, [rsp+38h+arg_30]
0x180018480  mov     rsi, r8
0x180018483  movsxd  r10, [rsp+38h+arg_20]
0x180018488  mov     r11, rdx
0x18001848b  movsxd  rbp, [rsp+38h+arg_28]
0x180018490  mov     rdi, rcx
0x180018493  mov     r14d, 4
0x180018499  lea     r15, [rbx+rbx]
0x18001849d  lea     r12, [r10+r10]
0x1800184a1  movzx   eax, byte ptr [rsi]
0x1800184a4  movzx   r8d, byte ptr [r9]
0x1800184a8  movzx   ecx, byte ptr [r11+1]
0x1800184ad  shl     ecx, 10h
0x1800184b0  shl     r8d, 10h
0x1800184b4  or      r8d, eax
0x1800184b7  movzx   eax, byte ptr [r11]
0x1800184bb  or      ecx, eax
0x1800184bd  shl     r8d, 8
0x1800184c1  or      ecx, r8d
0x1800184c4  mov     [rdi], ecx
0x1800184c6  movzx   eax, byte ptr [r10+r11]
0x1800184cb  movzx   ecx, byte ptr [r10+r11+1]
0x1800184d1  shl     ecx, 10h
0x1800184d4  or      ecx, eax
0x1800184d6  or      ecx, r8d
0x1800184d9  mov     [rbx+rdi], ecx
0x1800184dc  movzx   eax, byte ptr [rsi+1]
0x1800184e0  movzx   edx, byte ptr [r9+1]
0x1800184e5  movzx   ecx, byte ptr [r11+3]
0x1800184ea  shl     ecx, 10h
0x1800184ed  shl     edx, 10h
0x1800184f0  or      edx, eax
0x1800184f2  movzx   eax, byte ptr [r11+2]
0x1800184f7  or      ecx, eax
0x1800184f9  shl     edx, 8
0x1800184fc  or      ecx, edx
0x1800184fe  mov     [rdi+4], ecx
0x180018501  movzx   eax, byte ptr [r10+r11+2]
0x180018507  movzx   ecx, byte ptr [r10+r11+3]
0x18001850d  shl     ecx, 10h
0x180018510  or      ecx, eax
0x180018512  or      ecx, edx
0x180018514  mov     [rbx+rdi+4], ecx
0x180018518  movzx   eax, byte ptr [rsi+2]
0x18001851c  movzx   edx, byte ptr [r9+2]
0x180018521  movzx   ecx, byte ptr [r11+5]
0x180018526  shl     ecx, 10h
0x180018529  shl     edx, 10h
0x18001852c  or      edx, eax
0x18001852e  movzx   eax, byte ptr [r11+4]
0x180018533  or      ecx, eax
0x180018535  shl     edx, 8
0x180018538  or      ecx, edx
0x18001853a  mov     [rdi+8], ecx
0x18001853d  movzx   eax, byte ptr [r10+r11+4]
0x180018543  movzx   ecx, byte ptr [r10+r11+5]
0x180018549  shl     ecx, 10h
0x18001854c  or      ecx, eax
0x18001854e  or      ecx, edx
0x180018550  mov     [rbx+rdi+8], ecx
0x180018554  movzx   eax, byte ptr [rsi+3]
0x180018558  add     rsi, rbp
0x18001855b  movzx   edx, byte ptr [r9+3]
0x180018560  add     r9, rbp
0x180018563  movzx   ecx, byte ptr [r11+7]
0x180018568  shl     ecx, 10h
0x18001856b  shl     edx, 10h
0x18001856e  or      edx, eax
0x180018570  movzx   eax, byte ptr [r11+6]
0x180018575  or      ecx, eax
0x180018577  shl     edx, 8
0x18001857a  or      ecx, edx
0x18001857c  mov     [rdi+0Ch], ecx
0x18001857f  movzx   ecx, byte ptr [r10+r11+7]
0x180018585  movzx   eax, byte ptr [r10+r11+6]
0x18001858b  add     r11, r12
0x18001858e  shl     ecx, 10h
0x180018591  or      ecx, eax
0x180018593  or      ecx, edx
0x180018595  mov     [rbx+rdi+0Ch], ecx
0x180018599  add     rdi, r15
0x18001859c  sub     r14d, 1
0x1800185a0  jnz     loc_1800184A1
0x1800185a6  pop     r15
0x1800185a8  pop     r14
0x1800185aa  pop     r12
0x1800185ac  pop     rdi
0x1800185ad  pop     rsi
0x1800185ae  pop     rbp
0x1800185af  pop     rbx
0x1800185b0  retn
```
