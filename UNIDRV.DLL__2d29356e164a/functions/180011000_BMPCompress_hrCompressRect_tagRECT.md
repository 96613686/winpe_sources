# BMPCompress::hrCompressRect(tagRECT)

- ea: `0x180011000`
- end: `0x180011398`
- name: `?hrCompressRect@BMPCompress@@AEAAJUtagRECT@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(BMPCompress *__hidden this, struct tagRECT *__struct_ptr)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000fb0c`

## callees

- `0x180011000`
- `0x1800113a0`
- `0x1800483a8`
- `0x180048d98`
- `0x18006cdd4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800111e2`
- `KERNEL32!LocalFree` at `0x180011284`
- `KERNEL32!LocalFree` at `0x180011296`
- `KERNEL32!LocalFree` at `0x1800111e2`
- `KERNEL32!LocalFree` at `0x180011284`
- `KERNEL32!LocalFree` at `0x180011296`

## pseudocode

```c
__int64 __fastcall BMPCompress::hrCompressRect(BMPCompress *this, struct tagRECT *a2)
{
  unsigned int v2; // r12d
  LONG left; // r9d
  LONG bottom; // edi
  int v6; // ebx
  LONG top; // ecx
  unsigned int v8; // r10d
  __int64 v9; // rsi
  unsigned int v10; // r12d
  unsigned int v11; // ebp
  int v12; // ecx
  unsigned __int8 *v13; // rdx
  int v14; // ebx
  int v15; // r13d
  unsigned int v16; // eax
  __int64 v17; // r15
  int v18; // esi
  unsigned __int8 *v19; // rdi
  char *v20; // rbp
  unsigned __int8 *v21; // rax
  int v22; // edx
  unsigned int *v23; // r15
  unsigned int v24; // eax
  int v25; // eax
  void *v26; // rcx
  void *v27; // rcx
  void *v28; // rcx
  unsigned __int8 *Block; // [rsp+30h] [rbp-68h]
  __int64 v31; // [rsp+38h] [rbp-60h]
  unsigned __int8 *v32; // [rsp+40h] [rbp-58h]
  unsigned __int8 *v33; // [rsp+48h] [rbp-50h]
  LONG v34; // [rsp+A0h] [rbp+8h]
  int v35; // [rsp+A0h] [rbp+8h]
  unsigned int v36; // [rsp+A8h] [rbp+10h]
  unsigned int v37; // [rsp+B0h] [rbp+18h]
  unsigned int v38; // [rsp+B8h] [rbp+20h]

  v2 = *((_DWORD *)this + 6);
  left = a2->left;
  bottom = a2->bottom;
  switch ( v2 )
  {
    case 8u:
LABEL_2:
      v6 = *(_DWORD *)(*(_QWORD *)this + 64LL) * bottom + left * (v2 >> 3);
      break;
    case 1u:
      v6 = left / 8 + *(_DWORD *)(*(_QWORD *)this + 64LL) * bottom;
      break;
    case 4u:
      v6 = left / 2 + *(_DWORD *)(*(_QWORD *)this + 64LL) * bottom;
      break;
    case 0x10u:
    case 0x18u:
    case 0x20u:
      goto LABEL_2;
    default:
      return 2147500037LL;
  }
  top = a2->top;
  v8 = a2->right - left;
  v9 = *((_QWORD *)this + 1);
  Block = 0;
  v36 = v8;
  v10 = (v8 * v2 + 7) >> 3;
  v34 = top;
  v37 = v10;
  if ( *((_DWORD *)this + 92) == 1 )
  {
    Block = (unsigned __int8 *)operator new(v10);
    if ( !Block )
      return 2147500037LL;
    top = v34;
    v8 = v36;
  }
  v11 = -2147467259;
  if ( !*((_DWORD *)this + 9) )
    goto LABEL_37;
  v12 = top - bottom;
  v13 = (unsigned __int8 *)(v9 + v6);
  v14 = 255;
  v33 = v13;
  v35 = v12;
  v15 = 255;
  v16 = 0;
LABEL_6:
  v38 = v16;
  if ( v16 < *((_DWORD *)this + 9) )
  {
    v17 = v16;
    v18 = v12;
    v31 = v16;
    v19 = v13;
    v20 = (char *)this + 104 * v16;
    while ( 1 )
    {
      if ( !v18 )
      {
        v26 = (void *)*((_QWORD *)v20 + 11);
        if ( v26 )
        {
          LocalFree(v26);
          *((_QWORD *)v20 + 11) = 0;
        }
        v27 = (void *)*((_QWORD *)v20 + 16);
        if ( v27 )
        {
          LocalFree(v27);
          *((_QWORD *)v20 + 16) = 0;
        }
        v28 = (void *)*((_QWORD *)v20 + 13);
        if ( v28 )
        {
          LocalFree(v28);
          *((_QWORD *)v20 + 13) = 0;
        }
        v12 = v35;
        v16 = v38 + 1;
        v13 = v33;
        v8 = v36;
        *((_DWORD *)v20 + 14) = 0;
        *((_DWORD *)v20 + 21) = 0;
        *((_DWORD *)v20 + 24) = 0;
        *((_DWORD *)v20 + 28) = 0;
        goto LABEL_6;
      }
      if ( *((_DWORD *)this + 92) == 1 )
      {
        if ( (int)hrChangePixelColorInScanLine(v19, *((_DWORD *)this + 6), v8, *((_DWORD *)this + 93), Block, v10) < 0 )
        {
LABEL_43:
          v11 = -2147467259;
          goto LABEL_37;
        }
        v21 = Block;
      }
      else
      {
        v21 = v19;
      }
      v32 = v21;
      BMPConv::PubConvertBMP((BMPConv *)(v20 + 40), v21, v10);
      v22 = *((_DWORD *)v20 + 20);
      if ( v22 == 3 )
        break;
      v23 = (unsigned int *)(v20 + 84);
      if ( v22 == 1 )
      {
        v24 = *((_DWORD *)v20 + 25);
      }
      else
      {
        v24 = *v23;
        if ( v22 )
          goto LABEL_43;
      }
      if ( v24 >= v37 )
      {
        v14 = 0;
        *((_DWORD *)v20 + 20) = 0;
        BMPConv::PubConvertBMP((BMPConv *)(v20 + 40), v32, v37);
        v25 = *((_DWORD *)v20 + 20);
        if ( v25 == 3 )
        {
          v24 = *((_DWORD *)v20 + 30);
        }
        else
        {
          if ( v25 == 1 )
            v23 = (unsigned int *)(v20 + 100);
          v24 = *v23;
        }
      }
      else
      {
        v14 = 1;
      }
      if ( v14 == v15 )
      {
        v17 = v31;
LABEL_20:
        *((_DWORD *)this + v17 + 88) += v24;
        --v18;
        if ( v14 == v15 )
          goto LABEL_22;
        goto LABEL_21;
      }
      *((_DWORD *)this + v31 + 88) += v24 + 5;
      --v18;
LABEL_21:
      v15 = v14;
LABEL_22:
      v17 = v31;
      v10 = v37;
      v8 = v36;
      v19 += *(int *)(*(_QWORD *)this + 64LL);
    }
    v24 = *((_DWORD *)v20 + 30);
    goto LABEL_20;
  }
  v11 = 0;
LABEL_37:
  if ( Block )
    operator delete(Block);
  return v11;
}

```

## disassembly

```asm
0x180011000  push    rbx
0x180011002  push    rdi
0x180011003  push    r12
0x180011005  push    r14
0x180011007  sub     rsp, 78h
0x18001100b  mov     r12d, [rcx+18h]
0x18001100f  mov     r8, rdx
0x180011012  mov     r9d, [rdx]
0x180011015  mov     r14, rcx
0x180011018  mov     edi, [rdx+0Ch]
0x18001101b  cmp     r12d, 8
0x18001101f  jnz     loc_1800112A5
0x180011025  mov     rax, [rcx]
0x180011028  mov     ebx, r12d
0x18001102b  shr     ebx, 3
0x18001102e  mov     ecx, edi
0x180011030  imul    ebx, r9d
0x180011034  imul    ecx, [rax+40h]
0x180011038  add     ebx, ecx
0x18001103a  mov     r10d, [r8+8]
0x18001103e  mov     ecx, [r8+4]
0x180011042  sub     r10d, r9d
0x180011045  imul    r12d, r10d
0x180011049  mov     [rsp+98h+var_30], rsi
0x18001104e  mov     rsi, [r14+8]
0x180011052  mov     [rsp+98h+var_40], r15
0x180011057  xor     r15d, r15d
0x18001105a  mov     [rsp+98h+Block], r15
0x18001105f  add     r12d, 7
0x180011063  mov     [rsp+98h+arg_8], r10d
0x18001106b  shr     r12d, 3
0x18001106f  cmp     dword ptr [r14+170h], 1
0x180011077  mov     [rsp+98h+arg_0], ecx
0x18001107e  mov     [rsp+98h+arg_10], r12d
0x180011086  jz      loc_180011324
0x18001108c  cmp     dword ptr [r14+24h], 1
0x180011091  mov     [rsp+98h+var_28], rbp
0x180011096  mov     ebp, 80004005h
0x18001109b  jb      loc_180011252
0x1800110a1  sub     ecx, edi
0x1800110a3  movsxd  rdx, ebx
0x1800110a6  add     rdx, rsi
0x1800110a9  mov     [rsp+98h+var_38], r13
0x1800110ae  mov     ebx, 0FFh
0x1800110b3  mov     [rsp+98h+var_50], rdx
0x1800110b8  mov     [rsp+98h+arg_0], ecx
0x1800110bf  mov     r13d, ebx
0x1800110c2  mov     eax, r15d
0x1800110c5  mov     [rsp+98h+arg_18], eax
0x1800110cc  cmp     eax, [r14+24h]
0x1800110d0  jnb     loc_18001124A
0x1800110d6  mov     r15d, eax
0x1800110d9  mov     esi, ecx
0x1800110db  imul    rbp, r15, 68h ; 'h'
0x1800110df  mov     [rsp+98h+var_60], r15
0x1800110e4  mov     rdi, rdx
0x1800110e7  add     rbp, r14
0x1800110ea  nop     word ptr [rax+rax+00h]
0x1800110f0  test    esi, esi
0x1800110f2  jz      loc_1800111D5
0x1800110f8  cmp     dword ptr [r14+170h], 1
0x180011100  jz      loc_180011354
0x180011106  mov     rax, rdi
0x180011109  mov     r8d, r12d; unsigned int
0x18001110c  mov     [rsp+98h+var_58], rax
0x180011111  mov     rdx, rax; unsigned __int8 *
0x180011114  lea     rcx, [rbp+28h]; this
0x180011118  call    ?PubConvertBMP@BMPConv@@QEAAPEAEPEAEK@Z; BMPConv::PubConvertBMP(uchar *,ulong)
0x18001111d  mov     edx, [rbp+50h]
0x180011120  cmp     edx, 3
0x180011123  jz      short loc_18001116E
0x180011125  lea     r12, [rbp+64h]
0x180011129  lea     r15, [rbp+54h]
0x18001112d  cmp     edx, 1
0x180011130  jnz     short loc_180011138
0x180011132  mov     eax, [r12]
0x180011136  jmp     short loc_180011143
0x180011138  mov     eax, [r15]
0x18001113b  test    edx, edx
0x18001113d  jnz     loc_1800112C9
0x180011143  mov     r8d, [rsp+98h+arg_10]; unsigned int
0x18001114b  cmp     eax, r8d
0x18001114e  jnb     short loc_1800111AE
0x180011150  mov     ebx, 1
0x180011155  cmp     ebx, r13d
0x180011158  jz      short loc_1800111A7
0x18001115a  mov     rdx, [rsp+98h+var_60]
0x18001115f  add     eax, 5
0x180011162  add     [r14+rdx*4+160h], eax
0x18001116a  dec     esi
0x18001116c  jmp     short loc_180011180
0x18001116e  mov     eax, [rbp+78h]
0x180011171  add     [r14+r15*4+160h], eax
0x180011179  dec     esi
0x18001117b  cmp     ebx, r13d
0x18001117e  jz      short loc_180011183
0x180011180  mov     r13d, ebx
0x180011183  mov     rax, [r14]
0x180011186  mov     r15, [rsp+98h+var_60]
0x18001118b  mov     r12d, [rsp+98h+arg_10]
0x180011193  mov     r10d, [rsp+98h+arg_8]
0x18001119b  movsxd  rcx, dword ptr [rax+40h]
0x18001119f  add     rdi, rcx
0x1800111a2  jmp     loc_1800110F0
0x1800111a7  mov     r15, [rsp+98h+var_60]
0x1800111ac  jmp     short loc_180011171
0x1800111ae  mov     rdx, [rsp+98h+var_58]; unsigned __int8 *
0x1800111b3  lea     rcx, [rbp+28h]; this
0x1800111b7  xor     ebx, ebx
0x1800111b9  mov     [rbp+50h], ebx
0x1800111bc  call    ?PubConvertBMP@BMPConv@@QEAAPEAEPEAEK@Z; BMPConv::PubConvertBMP(uchar *,ulong)
0x1800111c1  mov     eax, [rbp+50h]
0x1800111c4  cmp     eax, 3
0x1800111c7  jz      short loc_18001123E
0x1800111c9  cmp     eax, 1
0x1800111cc  cmovz   r15, r12
0x1800111d0  mov     eax, [r15]
0x1800111d3  jmp     short loc_180011155
0x1800111d5  mov     rcx, [rbp+58h]; hMem
0x1800111d9  test    rcx, rcx
0x1800111dc  jz      loc_18001127C
0x1800111e2  call    cs:__imp_LocalFree
0x1800111e8  xor     r15d, r15d
0x1800111eb  mov     [rbp+58h], r15
0x1800111ef  mov     rcx, [rbp+80h]; hMem
0x1800111f6  test    rcx, rcx
0x1800111f9  jnz     loc_180011284
0x1800111ff  mov     rcx, [rbp+68h]; hMem
0x180011203  test    rcx, rcx
0x180011206  jnz     loc_180011296
0x18001120c  mov     eax, [rsp+98h+arg_18]
0x180011213  mov     ecx, [rsp+98h+arg_0]
0x18001121a  inc     eax
0x18001121c  mov     rdx, [rsp+98h+var_50]
0x180011221  mov     r10d, [rsp+98h+arg_8]
0x180011229  mov     [rbp+38h], r15d
0x18001122d  mov     [rbp+54h], r15d
0x180011231  mov     [rbp+60h], r15d
0x180011235  mov     [rbp+70h], r15d
0x180011239  jmp     loc_1800110C5
0x18001123e  mov     eax, [rbp+78h]
0x180011241  lea     r15, [rbp+78h]
0x180011245  jmp     loc_180011155
0x18001124a  mov     ebp, r15d
0x18001124d  mov     r13, [rsp+98h+var_38]
0x180011252  mov     rax, [rsp+98h+Block]
0x180011257  test    rax, rax
0x18001125a  jnz     loc_18001138B
0x180011260  mov     eax, ebp
0x180011262  mov     rbp, [rsp+98h+var_28]
0x180011267  mov     rsi, [rsp+98h+var_30]
0x18001126c  mov     r15, [rsp+98h+var_40]
0x180011271  add     rsp, 78h
0x180011275  pop     r14
0x180011277  pop     r12
0x180011279  pop     rdi
0x18001127a  pop     rbx
0x18001127b  retn
0x18001127c  xor     r15d, r15d
0x18001127f  jmp     loc_1800111EF
0x180011284  call    cs:__imp_LocalFree
0x18001128a  mov     [rbp+80h], r15
0x180011291  jmp     loc_1800111FF
0x180011296  call    cs:__imp_LocalFree
0x18001129c  mov     [rbp+68h], r15
0x1800112a0  jmp     loc_18001120C
0x1800112a5  mov     eax, r12d
0x1800112a8  sub     eax, 1
0x1800112ab  jnz     short loc_1800112DC
0x1800112ad  mov     rax, [rcx]
0x1800112b0  mov     ebx, edi
0x1800112b2  imul    ebx, [rax+40h]
0x1800112b6  mov     eax, r9d
0x1800112b9  cdq
0x1800112ba  and     edx, 7
0x1800112bd  add     eax, edx
0x1800112bf  sar     eax, 3
0x1800112c2  add     ebx, eax
0x1800112c4  jmp     loc_18001103A
0x1800112c9  cmp     edx, 1
0x1800112cc  jz      loc_180011143
0x1800112d2  mov     ebp, 80004005h
0x1800112d7  jmp     loc_18001124D
0x1800112dc  sub     eax, 3
0x1800112df  jnz     short loc_1800112F9
0x1800112e1  mov     rax, [rcx]
0x1800112e4  mov     ebx, edi
0x1800112e6  imul    ebx, [rax+40h]
0x1800112ea  mov     eax, r9d
0x1800112ed  cdq
0x1800112ee  sub     eax, edx
0x1800112f0  sar     eax, 1
0x1800112f2  add     ebx, eax
0x1800112f4  jmp     loc_18001103A
0x1800112f9  sub     eax, 0Ch
0x1800112fc  jz      loc_180011025
0x180011302  sub     eax, 8
0x180011305  jz      loc_180011025
0x18001130b  cmp     eax, 8
0x18001130e  jz      loc_180011025
0x180011314  mov     eax, 80004005h
0x180011319  add     rsp, 78h
0x18001131d  pop     r14
0x18001131f  pop     r12
0x180011321  pop     rdi
0x180011322  pop     rbx
0x180011323  retn
0x180011324  mov     ecx, r12d; Size
0x180011327  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001132c  mov     [rsp+98h+Block], rax
0x180011331  test    rax, rax
0x180011334  jnz     short loc_180011340
0x180011336  mov     eax, 80004005h
0x18001133b  jmp     loc_180011267
0x180011340  mov     ecx, [rsp+98h+arg_0]
0x180011347  mov     r10d, [rsp+98h+arg_8]
0x18001134f  jmp     loc_18001108C
0x180011354  mov     rax, [rsp+98h+Block]
0x180011359  mov     r8d, r10d; unsigned int
0x18001135c  mov     r9d, [r14+174h]; unsigned int
0x180011363  mov     rcx, rdi; Src
0x180011366  mov     edx, [r14+18h]; unsigned int
0x18001136a  mov     [rsp+98h+var_70], r12d; unsigned int
0x18001136f  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x180011374  call    ?hrChangePixelColorInScanLine@@YAJPEAEKKK0K@Z; hrChangePixelColorInScanLine(uchar *,ulong,ulong,ulong,uchar *,ulong)
0x180011379  test    eax, eax
0x18001137b  js      loc_1800112D2
0x180011381  mov     rax, [rsp+98h+Block]
0x180011386  jmp     loc_180011109
0x18001138b  mov     rcx, rax; Block
0x18001138e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011393  jmp     loc_180011260
```
