# UpdateDstBlkYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)

- ea: `0x18003ea10`
- end: `0x18003eb49`
- name: `?UpdateDstBlkYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z`
- size: `313`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18003ea10`

## pseudocode

```c
void __fastcall UpdateDstBlkYUY2(
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
    v11 = (*a4 | (*a5 << 16)) << 8;
    *(_DWORD *)a2 = v11 | *a3 | (a3[1] << 16);
    *(_DWORD *)&a2[a8] = v11 | a3[a6] | (a3[a6 + 1] << 16);
    v12 = (a4[1] | (a5[1] << 16)) << 8;
    *((_DWORD *)a2 + 1) = v12 | a3[2] | (a3[3] << 16);
    *(_DWORD *)&a2[a8 + 4] = v12 | a3[a6 + 2] | (a3[a6 + 3] << 16);
    v13 = (a4[2] | (a5[2] << 16)) << 8;
    *((_DWORD *)a2 + 2) = v13 | a3[4] | (a3[5] << 16);
    *(_DWORD *)&a2[a8 + 8] = v13 | a3[a6 + 4] | (a3[a6 + 5] << 16);
    v14 = a4[3];
    a4 += a7;
    v15 = a5[3];
    a5 += a7;
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
0x18003ea10  push    rbx
0x18003ea12  push    rbp
0x18003ea13  push    rsi
0x18003ea14  push    rdi
0x18003ea15  push    r14
0x18003ea17  push    r15
0x18003ea19  movsxd  r11, [rsp+30h+arg_38]
0x18003ea1e  mov     rbx, rdx
0x18003ea21  movsxd  r10, [rsp+30h+arg_28]
0x18003ea26  mov     ebp, 4
0x18003ea2b  movsxd  rsi, [rsp+30h+arg_30]
0x18003ea30  mov     rdi, [rsp+30h+arg_20]
0x18003ea35  lea     r14, [r11+r11]
0x18003ea39  lea     r15, [r10+r10]
0x18003ea3d  movzx   eax, byte ptr [r9]
0x18003ea41  movzx   edx, byte ptr [rdi]
0x18003ea44  movzx   ecx, byte ptr [r8+1]
0x18003ea49  shl     ecx, 10h
0x18003ea4c  shl     edx, 10h
0x18003ea4f  or      edx, eax
0x18003ea51  movzx   eax, byte ptr [r8]
0x18003ea55  or      ecx, eax
0x18003ea57  shl     edx, 8
0x18003ea5a  or      ecx, edx
0x18003ea5c  mov     [rbx], ecx
0x18003ea5e  movzx   eax, byte ptr [r10+r8]
0x18003ea63  movzx   ecx, byte ptr [r10+r8+1]
0x18003ea69  shl     ecx, 10h
0x18003ea6c  or      ecx, eax
0x18003ea6e  or      ecx, edx
0x18003ea70  mov     [r11+rbx], ecx
0x18003ea74  movzx   eax, byte ptr [r9+1]
0x18003ea79  movzx   edx, byte ptr [rdi+1]
0x18003ea7d  movzx   ecx, byte ptr [r8+3]
0x18003ea82  shl     ecx, 10h
0x18003ea85  shl     edx, 10h
0x18003ea88  or      edx, eax
0x18003ea8a  movzx   eax, byte ptr [r8+2]
0x18003ea8f  or      ecx, eax
0x18003ea91  shl     edx, 8
0x18003ea94  or      ecx, edx
0x18003ea96  mov     [rbx+4], ecx
0x18003ea99  movzx   eax, byte ptr [r10+r8+2]
0x18003ea9f  movzx   ecx, byte ptr [r10+r8+3]
0x18003eaa5  shl     ecx, 10h
0x18003eaa8  or      ecx, eax
0x18003eaaa  or      ecx, edx
0x18003eaac  mov     [r11+rbx+4], ecx
0x18003eab1  movzx   eax, byte ptr [r9+2]
0x18003eab6  movzx   edx, byte ptr [rdi+2]
0x18003eaba  movzx   ecx, byte ptr [r8+5]
0x18003eabf  shl     ecx, 10h
0x18003eac2  shl     edx, 10h
0x18003eac5  or      edx, eax
0x18003eac7  movzx   eax, byte ptr [r8+4]
0x18003eacc  or      ecx, eax
0x18003eace  shl     edx, 8
0x18003ead1  or      ecx, edx
0x18003ead3  mov     [rbx+8], ecx
0x18003ead6  movzx   eax, byte ptr [r10+r8+4]
0x18003eadc  movzx   ecx, byte ptr [r10+r8+5]
0x18003eae2  shl     ecx, 10h
0x18003eae5  or      ecx, eax
0x18003eae7  or      ecx, edx
0x18003eae9  mov     [r11+rbx+8], ecx
0x18003eaee  movzx   eax, byte ptr [r9+3]
0x18003eaf3  add     r9, rsi
0x18003eaf6  movzx   edx, byte ptr [rdi+3]
0x18003eafa  add     rdi, rsi
0x18003eafd  movzx   ecx, byte ptr [r8+7]
0x18003eb02  shl     ecx, 10h
0x18003eb05  shl     edx, 10h
0x18003eb08  or      edx, eax
0x18003eb0a  movzx   eax, byte ptr [r8+6]
0x18003eb0f  or      ecx, eax
0x18003eb11  shl     edx, 8
0x18003eb14  or      ecx, edx
0x18003eb16  mov     [rbx+0Ch], ecx
0x18003eb19  movzx   ecx, byte ptr [r10+r8+7]
0x18003eb1f  movzx   eax, byte ptr [r10+r8+6]
0x18003eb25  add     r8, r15
0x18003eb28  shl     ecx, 10h
0x18003eb2b  or      ecx, eax
0x18003eb2d  or      ecx, edx
0x18003eb2f  mov     [r11+rbx+0Ch], ecx
0x18003eb34  add     rbx, r14
0x18003eb37  sub     ebp, 1
0x18003eb3a  jnz     loc_18003EA3D
0x18003eb40  pop     r15
0x18003eb42  pop     r14
0x18003eb44  pop     rdi
0x18003eb45  pop     rsi
0x18003eb46  pop     rbp
0x18003eb47  pop     rbx
0x18003eb48  retn
```
