# UpdateDstBlkUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003e8c0`
- end: `0x18003ea05`
- name: `?UpdateDstBlkUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `325`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003e8c0`

## pseudocode

```c
void __fastcall UpdateDstBlkUYVY(
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
    v11 = *a4 | (*a5 << 16);
    *(_DWORD *)a2 = v11 | ((*a3 | (a3[1] << 16)) << 8);
    *(_DWORD *)&a2[a8] = v11 | ((a3[a6] | (a3[a6 + 1] << 16)) << 8);
    v12 = a4[1] | (a5[1] << 16);
    *((_DWORD *)a2 + 1) = v12 | ((a3[2] | (a3[3] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 4] = v12 | ((a3[a6 + 2] | (a3[a6 + 3] << 16)) << 8);
    v13 = a4[2] | (a5[2] << 16);
    *((_DWORD *)a2 + 2) = v13 | ((a3[4] | (a3[5] << 16)) << 8);
    *(_DWORD *)&a2[a8 + 8] = v13 | ((a3[a6 + 4] | (a3[a6 + 5] << 16)) << 8);
    v14 = a4[3];
    a4 += a7;
    v15 = a5[3];
    a5 += a7;
    v16 = v14 | (v15 << 16);
    *((_DWORD *)a2 + 3) = v16 | ((a3[6] | (a3[7] << 16)) << 8);
    v17 = a3[a6 + 7];
    v18 = a3[a6 + 6];
    a3 += 2 * a6;
    *(_DWORD *)&a2[a8 + 12] = v16 | ((v18 | (v17 << 16)) << 8);
    a2 += 2 * a8;
    --v9;
  }
  while ( v9 );
}

```

## disassembly

```asm
0x18003e8c0  push    rbx
0x18003e8c2  push    rbp
0x18003e8c3  push    rsi
0x18003e8c4  push    rdi
0x18003e8c5  push    r14
0x18003e8c7  push    r15
0x18003e8c9  movsxd  r11, [rsp+30h+arg_38]
0x18003e8ce  mov     rbx, rdx
0x18003e8d1  movsxd  r10, [rsp+30h+arg_28]
0x18003e8d6  mov     ebp, 4
0x18003e8db  movsxd  rsi, [rsp+30h+arg_30]
0x18003e8e0  mov     rdi, [rsp+30h+arg_20]
0x18003e8e5  lea     r14, [r11+r11]
0x18003e8e9  lea     r15, [r10+r10]
0x18003e8ed  movzx   eax, byte ptr [r9]
0x18003e8f1  movzx   edx, byte ptr [rdi]
0x18003e8f4  movzx   ecx, byte ptr [r8+1]
0x18003e8f9  shl     ecx, 10h
0x18003e8fc  shl     edx, 10h
0x18003e8ff  or      edx, eax
0x18003e901  movzx   eax, byte ptr [r8]
0x18003e905  or      ecx, eax
0x18003e907  shl     ecx, 8
0x18003e90a  or      ecx, edx
0x18003e90c  mov     [rbx], ecx
0x18003e90e  movzx   eax, byte ptr [r10+r8]
0x18003e913  movzx   ecx, byte ptr [r10+r8+1]
0x18003e919  shl     ecx, 10h
0x18003e91c  or      ecx, eax
0x18003e91e  shl     ecx, 8
0x18003e921  or      ecx, edx
0x18003e923  mov     [r11+rbx], ecx
0x18003e927  movzx   eax, byte ptr [r9+1]
0x18003e92c  movzx   edx, byte ptr [rdi+1]
0x18003e930  movzx   ecx, byte ptr [r8+3]
0x18003e935  shl     ecx, 10h
0x18003e938  shl     edx, 10h
0x18003e93b  or      edx, eax
0x18003e93d  movzx   eax, byte ptr [r8+2]
0x18003e942  or      ecx, eax
0x18003e944  shl     ecx, 8
0x18003e947  or      ecx, edx
0x18003e949  mov     [rbx+4], ecx
0x18003e94c  movzx   eax, byte ptr [r10+r8+2]
0x18003e952  movzx   ecx, byte ptr [r10+r8+3]
0x18003e958  shl     ecx, 10h
0x18003e95b  or      ecx, eax
0x18003e95d  shl     ecx, 8
0x18003e960  or      ecx, edx
0x18003e962  mov     [r11+rbx+4], ecx
0x18003e967  movzx   eax, byte ptr [r9+2]
0x18003e96c  movzx   edx, byte ptr [rdi+2]
0x18003e970  movzx   ecx, byte ptr [r8+5]
0x18003e975  shl     ecx, 10h
0x18003e978  shl     edx, 10h
0x18003e97b  or      edx, eax
0x18003e97d  movzx   eax, byte ptr [r8+4]
0x18003e982  or      ecx, eax
0x18003e984  shl     ecx, 8
0x18003e987  or      ecx, edx
0x18003e989  mov     [rbx+8], ecx
0x18003e98c  movzx   eax, byte ptr [r10+r8+4]
0x18003e992  movzx   ecx, byte ptr [r10+r8+5]
0x18003e998  shl     ecx, 10h
0x18003e99b  or      ecx, eax
0x18003e99d  shl     ecx, 8
0x18003e9a0  or      ecx, edx
0x18003e9a2  mov     [r11+rbx+8], ecx
0x18003e9a7  movzx   eax, byte ptr [r9+3]
0x18003e9ac  add     r9, rsi
0x18003e9af  movzx   edx, byte ptr [rdi+3]
0x18003e9b3  add     rdi, rsi
0x18003e9b6  movzx   ecx, byte ptr [r8+7]
0x18003e9bb  shl     ecx, 10h
0x18003e9be  shl     edx, 10h
0x18003e9c1  or      edx, eax
0x18003e9c3  movzx   eax, byte ptr [r8+6]
0x18003e9c8  or      ecx, eax
0x18003e9ca  shl     ecx, 8
0x18003e9cd  or      ecx, edx
0x18003e9cf  mov     [rbx+0Ch], ecx
0x18003e9d2  movzx   ecx, byte ptr [r10+r8+7]
0x18003e9d8  movzx   eax, byte ptr [r10+r8+6]
0x18003e9de  add     r8, r15
0x18003e9e1  shl     ecx, 10h
0x18003e9e4  or      ecx, eax
0x18003e9e6  shl     ecx, 8
0x18003e9e9  or      ecx, edx
0x18003e9eb  mov     [r11+rbx+0Ch], ecx
0x18003e9f0  add     rbx, r14
0x18003e9f3  sub     ebp, 1
0x18003e9f6  jnz     loc_18003E8ED
0x18003e9fc  pop     r15
0x18003e9fe  pop     r14
0x18003ea00  pop     rdi
0x18003ea01  pop     rsi
0x18003ea02  pop     rbp
0x18003ea03  pop     rbx
0x18003ea04  retn
```
