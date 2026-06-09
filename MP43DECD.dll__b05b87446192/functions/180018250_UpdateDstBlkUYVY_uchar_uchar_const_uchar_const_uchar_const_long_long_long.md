# UpdateDstBlkUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x180018250`
- end: `0x18001839c`
- name: `?UpdateDstBlkUYVY@@YAXPEAEPEBE11JJJ@Z`
- size: `332`
- prototype: `void __fastcall(unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180018250`

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
0x180018250  push    rbx
0x180018252  push    rbp
0x180018253  push    rsi
0x180018254  push    rdi
0x180018255  push    r12
0x180018257  push    r14
0x180018259  push    r15
0x18001825b  movsxd  rbx, [rsp+38h+arg_30]
0x180018260  mov     rsi, r8
0x180018263  movsxd  r10, [rsp+38h+arg_20]
0x180018268  mov     r11, rdx
0x18001826b  movsxd  rbp, [rsp+38h+arg_28]
0x180018270  mov     rdi, rcx
0x180018273  mov     r14d, 4
0x180018279  lea     r15, [rbx+rbx]
0x18001827d  lea     r12, [r10+r10]
0x180018281  movzx   eax, byte ptr [rsi]
0x180018284  movzx   r8d, byte ptr [r9]
0x180018288  movzx   ecx, byte ptr [r11+1]
0x18001828d  shl     ecx, 10h
0x180018290  shl     r8d, 10h
0x180018294  or      r8d, eax
0x180018297  movzx   eax, byte ptr [r11]
0x18001829b  or      ecx, eax
0x18001829d  shl     ecx, 8
0x1800182a0  or      ecx, r8d
0x1800182a3  mov     [rdi], ecx
0x1800182a5  movzx   eax, byte ptr [r10+r11]
0x1800182aa  movzx   ecx, byte ptr [r10+r11+1]
0x1800182b0  shl     ecx, 10h
0x1800182b3  or      ecx, eax
0x1800182b5  shl     ecx, 8
0x1800182b8  or      ecx, r8d
0x1800182bb  mov     [rbx+rdi], ecx
0x1800182be  movzx   eax, byte ptr [rsi+1]
0x1800182c2  movzx   edx, byte ptr [r9+1]
0x1800182c7  movzx   ecx, byte ptr [r11+3]
0x1800182cc  shl     ecx, 10h
0x1800182cf  shl     edx, 10h
0x1800182d2  or      edx, eax
0x1800182d4  movzx   eax, byte ptr [r11+2]
0x1800182d9  or      ecx, eax
0x1800182db  shl     ecx, 8
0x1800182de  or      ecx, edx
0x1800182e0  mov     [rdi+4], ecx
0x1800182e3  movzx   eax, byte ptr [r10+r11+2]
0x1800182e9  movzx   ecx, byte ptr [r10+r11+3]
0x1800182ef  shl     ecx, 10h
0x1800182f2  or      ecx, eax
0x1800182f4  shl     ecx, 8
0x1800182f7  or      ecx, edx
0x1800182f9  mov     [rbx+rdi+4], ecx
0x1800182fd  movzx   eax, byte ptr [rsi+2]
0x180018301  movzx   edx, byte ptr [r9+2]
0x180018306  movzx   ecx, byte ptr [r11+5]
0x18001830b  shl     ecx, 10h
0x18001830e  shl     edx, 10h
0x180018311  or      edx, eax
0x180018313  movzx   eax, byte ptr [r11+4]
0x180018318  or      ecx, eax
0x18001831a  shl     ecx, 8
0x18001831d  or      ecx, edx
0x18001831f  mov     [rdi+8], ecx
0x180018322  movzx   eax, byte ptr [r10+r11+4]
0x180018328  movzx   ecx, byte ptr [r10+r11+5]
0x18001832e  shl     ecx, 10h
0x180018331  or      ecx, eax
0x180018333  shl     ecx, 8
0x180018336  or      ecx, edx
0x180018338  mov     [rbx+rdi+8], ecx
0x18001833c  movzx   eax, byte ptr [rsi+3]
0x180018340  add     rsi, rbp
0x180018343  movzx   edx, byte ptr [r9+3]
0x180018348  add     r9, rbp
0x18001834b  movzx   ecx, byte ptr [r11+7]
0x180018350  shl     ecx, 10h
0x180018353  shl     edx, 10h
0x180018356  or      edx, eax
0x180018358  movzx   eax, byte ptr [r11+6]
0x18001835d  or      ecx, eax
0x18001835f  shl     ecx, 8
0x180018362  or      ecx, edx
0x180018364  mov     [rdi+0Ch], ecx
0x180018367  movzx   ecx, byte ptr [r10+r11+7]
0x18001836d  movzx   eax, byte ptr [r10+r11+6]
0x180018373  add     r11, r12
0x180018376  shl     ecx, 10h
0x180018379  or      ecx, eax
0x18001837b  shl     ecx, 8
0x18001837e  or      ecx, edx
0x180018380  mov     [rbx+rdi+0Ch], ecx
0x180018384  add     rdi, r15
0x180018387  sub     r14d, 1
0x18001838b  jnz     loc_180018281
0x180018391  pop     r15
0x180018393  pop     r14
0x180018395  pop     r12
0x180018397  pop     rdi
0x180018398  pop     rsi
0x180018399  pop     rbp
0x18001839a  pop     rbx
0x18001839b  retn
```
