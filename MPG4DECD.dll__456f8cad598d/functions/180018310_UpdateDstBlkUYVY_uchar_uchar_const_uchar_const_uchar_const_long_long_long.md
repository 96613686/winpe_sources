# UpdateDstBlkUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180018310`
- end: `0x18001845c`
- name: `?UpdateDstBlkUYVY@@YAXPEAEPEBE11JJJ@Z`
- size: `332`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180018310`

## pseudocode

```c
void __fastcall UpdateDstBlkUYVY(
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
    v11 = *a3 | (*a4 << 16);
    *(_DWORD *)a1 = v11 | ((*a2 | (a2[1] << 16)) << 8);
    *(_DWORD *)&a1[a7] = v11 | ((a2[a5] | (a2[a5 + 1] << 16)) << 8);
    v12 = a3[1] | (a4[1] << 16);
    *((_DWORD *)a1 + 1) = v12 | ((a2[2] | (a2[3] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 4] = v12 | ((a2[a5 + 2] | (a2[a5 + 3] << 16)) << 8);
    v13 = a3[2] | (a4[2] << 16);
    *((_DWORD *)a1 + 2) = v13 | ((a2[4] | (a2[5] << 16)) << 8);
    *(_DWORD *)&a1[a7 + 8] = v13 | ((a2[a5 + 4] | (a2[a5 + 5] << 16)) << 8);
    v14 = a3[3];
    a3 += a6;
    v15 = a4[3];
    a4 += a6;
    v16 = v14 | (v15 << 16);
    *((_DWORD *)a1 + 3) = v16 | ((a2[6] | (a2[7] << 16)) << 8);
    v17 = a2[a5 + 7];
    v18 = a2[a5 + 6];
    a2 += 2 * a5;
    *(_DWORD *)&a1[a7 + 12] = v16 | ((v18 | (v17 << 16)) << 8);
    a1 += 2 * a7;
    --v10;
  }
  while ( v10 );
}

```

## disassembly

```asm
0x180018310  push    rbx
0x180018312  push    rbp
0x180018313  push    rsi
0x180018314  push    rdi
0x180018315  push    r12
0x180018317  push    r14
0x180018319  push    r15
0x18001831b  movsxd  rbx, [rsp+38h+arg_30]
0x180018320  mov     rsi, r8
0x180018323  movsxd  r10, [rsp+38h+arg_20]
0x180018328  mov     r11, rdx
0x18001832b  movsxd  rbp, [rsp+38h+arg_28]
0x180018330  mov     rdi, rcx
0x180018333  mov     r14d, 4
0x180018339  lea     r15, [rbx+rbx]
0x18001833d  lea     r12, [r10+r10]
0x180018341  movzx   eax, byte ptr [rsi]
0x180018344  movzx   r8d, byte ptr [r9]
0x180018348  movzx   ecx, byte ptr [r11+1]
0x18001834d  shl     ecx, 10h
0x180018350  shl     r8d, 10h
0x180018354  or      r8d, eax
0x180018357  movzx   eax, byte ptr [r11]
0x18001835b  or      ecx, eax
0x18001835d  shl     ecx, 8
0x180018360  or      ecx, r8d
0x180018363  mov     [rdi], ecx
0x180018365  movzx   eax, byte ptr [r10+r11]
0x18001836a  movzx   ecx, byte ptr [r10+r11+1]
0x180018370  shl     ecx, 10h
0x180018373  or      ecx, eax
0x180018375  shl     ecx, 8
0x180018378  or      ecx, r8d
0x18001837b  mov     [rbx+rdi], ecx
0x18001837e  movzx   eax, byte ptr [rsi+1]
0x180018382  movzx   edx, byte ptr [r9+1]
0x180018387  movzx   ecx, byte ptr [r11+3]
0x18001838c  shl     ecx, 10h
0x18001838f  shl     edx, 10h
0x180018392  or      edx, eax
0x180018394  movzx   eax, byte ptr [r11+2]
0x180018399  or      ecx, eax
0x18001839b  shl     ecx, 8
0x18001839e  or      ecx, edx
0x1800183a0  mov     [rdi+4], ecx
0x1800183a3  movzx   eax, byte ptr [r10+r11+2]
0x1800183a9  movzx   ecx, byte ptr [r10+r11+3]
0x1800183af  shl     ecx, 10h
0x1800183b2  or      ecx, eax
0x1800183b4  shl     ecx, 8
0x1800183b7  or      ecx, edx
0x1800183b9  mov     [rbx+rdi+4], ecx
0x1800183bd  movzx   eax, byte ptr [rsi+2]
0x1800183c1  movzx   edx, byte ptr [r9+2]
0x1800183c6  movzx   ecx, byte ptr [r11+5]
0x1800183cb  shl     ecx, 10h
0x1800183ce  shl     edx, 10h
0x1800183d1  or      edx, eax
0x1800183d3  movzx   eax, byte ptr [r11+4]
0x1800183d8  or      ecx, eax
0x1800183da  shl     ecx, 8
0x1800183dd  or      ecx, edx
0x1800183df  mov     [rdi+8], ecx
0x1800183e2  movzx   eax, byte ptr [r10+r11+4]
0x1800183e8  movzx   ecx, byte ptr [r10+r11+5]
0x1800183ee  shl     ecx, 10h
0x1800183f1  or      ecx, eax
0x1800183f3  shl     ecx, 8
0x1800183f6  or      ecx, edx
0x1800183f8  mov     [rbx+rdi+8], ecx
0x1800183fc  movzx   eax, byte ptr [rsi+3]
0x180018400  add     rsi, rbp
0x180018403  movzx   edx, byte ptr [r9+3]
0x180018408  add     r9, rbp
0x18001840b  movzx   ecx, byte ptr [r11+7]
0x180018410  shl     ecx, 10h
0x180018413  shl     edx, 10h
0x180018416  or      edx, eax
0x180018418  movzx   eax, byte ptr [r11+6]
0x18001841d  or      ecx, eax
0x18001841f  shl     ecx, 8
0x180018422  or      ecx, edx
0x180018424  mov     [rdi+0Ch], ecx
0x180018427  movzx   ecx, byte ptr [r10+r11+7]
0x18001842d  movzx   eax, byte ptr [r10+r11+6]
0x180018433  add     r11, r12
0x180018436  shl     ecx, 10h
0x180018439  or      ecx, eax
0x18001843b  shl     ecx, 8
0x18001843e  or      ecx, edx
0x180018440  mov     [rbx+rdi+0Ch], ecx
0x180018444  add     rdi, r15
0x180018447  sub     r14d, 1
0x18001844b  jnz     loc_180018341
0x180018451  pop     r15
0x180018453  pop     r14
0x180018455  pop     r12
0x180018457  pop     rdi
0x180018458  pop     rsi
0x180018459  pop     rbp
0x18001845a  pop     rbx
0x18001845b  retn
```
