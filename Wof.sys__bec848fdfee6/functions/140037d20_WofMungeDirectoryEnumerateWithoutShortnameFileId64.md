# WofMungeDirectoryEnumerateWithoutShortnameFileId64

- ea: `0x140037d20`
- end: `0x1400382aa`
- name: `WofMungeDirectoryEnumerateWithoutShortnameFileId64`
- size: `1418`
- prototype: `__int64 __fastcall(int, _DWORD *, unsigned int, __int64, unsigned int, char, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140036e70`

## callees

- `0x140011590`
- `0x1400115b0`
- `0x140022fcc`
- `0x1400230a8`
- `0x140023150`
- `0x140023198`
- `0x140035ed0`
- `0x140037d20`

## pseudocode

```c
__int64 __fastcall WofMungeDirectoryEnumerateWithoutShortnameFileId64(
        int a1,
        _DWORD *a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        char a6,
        unsigned int *a7)
{
  _DWORD *v7; // rdi
  unsigned __int64 v8; // r15
  unsigned int v9; // ebx
  unsigned int v10; // r13d
  _DWORD *v11; // rsi
  unsigned int v12; // edx
  unsigned int v13; // r14d
  unsigned int v14; // esi
  unsigned int v15; // r8d
  SIZE_T v16; // r8
  void *v17; // rcx
  unsigned int *v18; // r15
  __int64 v19; // r8
  int v20; // eax
  int *v21; // rcx
  int v22; // eax
  int v23; // eax
  int *v24; // rcx
  void *v25; // rcx
  void *v26; // rdx
  unsigned int v27; // eax
  _DWORD *v28; // rcx
  void *v29; // rcx
  __int64 v30; // r8
  int v31; // eax
  int *v32; // rcx
  int v33; // eax
  _QWORD *v34; // rcx
  int v35; // eax
  int *v36; // rcx
  int v37; // eax
  int *v38; // rcx
  int v39; // eax
  int *v40; // rcx
  __int64 v41; // r8
  int v42; // eax
  int *v43; // rcx
  int v44; // eax
  int v45; // ecx
  int v46; // eax
  int v47; // ecx
  int v49; // [rsp+80h] [rbp+8h]
  unsigned __int64 v50; // [rsp+88h] [rbp+10h]
  __int64 v51; // [rsp+98h] [rbp+20h]

  v51 = a4;
  v49 = a1;
  v7 = a2;
  v8 = (unsigned __int64)a2 + a3;
  v50 = v8;
  v9 = 0;
  v10 = 0;
  v11 = a2;
  v12 = a5;
  while ( 1 )
  {
    v13 = v11[15];
    if ( v13 >= a3 - 80 )
      v13 = a3 - 80;
    switch ( a1 )
    {
      case 1:
        v18 = (unsigned int *)(a4 + v9);
        v10 = v13 + 64;
        if ( a6 )
          RtlCopyToUser(v18, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v18, v7, 0x38u);
        v37 = v11[14];
        if ( v11[17] == FileTag )
        {
          if ( byte_140018454 )
            v37 &= ~0x400u;
          if ( byte_140018455 )
            v37 &= ~0x200u;
          if ( !v37 )
            v37 = 128;
        }
        v38 = (int *)(v18 + 14);
        if ( a6 )
          RtlWriteULongToUser(v38, v37);
        else
          *v38 = v37;
        v39 = v11[15];
        v40 = (int *)(v18 + 15);
        if ( a6 )
          RtlWriteULongToUser(v40, v39);
        else
          *v40 = v39;
        v25 = v18 + 16;
        goto LABEL_28;
      case 2:
        v18 = (unsigned int *)(a4 + v9);
        v10 = v13 + 68;
        if ( a6 )
          RtlCopyToUser(v18, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v18, v7, 0x38u);
        if ( v11[17] != FileTag )
        {
          v20 = v11[14];
          if ( a6 )
            RtlWriteULongToUser(v18 + 14, v20);
          else
            v18[14] = v20;
          v21 = (int *)(v18 + 16);
          if ( (v11[14] & 0x400) != 0 )
            v22 = v11[17];
          else
            v22 = v11[16];
          if ( a6 )
            RtlWriteULongToUser(v21, v22);
          else
            *v21 = v22;
          goto LABEL_25;
        }
        v46 = WofSanitizeAttributes((unsigned int)v11[14], 0, v19);
        if ( a6 )
          RtlWriteULongToUser(v18 + 14, v46);
        else
          v18[14] = v46;
        if ( byte_140018454 )
        {
          v47 = v11[16];
          if ( !a6 )
          {
LABEL_112:
            v18[16] = v47;
LABEL_25:
            v23 = v11[15];
            v24 = (int *)(v18 + 15);
            if ( a6 )
              RtlWriteULongToUser(v24, v23);
            else
              *v24 = v23;
            v25 = v18 + 17;
LABEL_28:
            v26 = v7 + 20;
            goto LABEL_29;
          }
        }
        else
        {
          v47 = v11[17];
          if ( !a6 )
            goto LABEL_112;
        }
        RtlWriteULongToUser(v18 + 16, v47);
        goto LABEL_25;
      case 38:
        v18 = (unsigned int *)(a4 + v9);
        v10 = v13 + 80;
        if ( a6 )
          RtlCopyToUser(v18, v7, 0x38u);
        else
          RtlCopyVolatileMemory(v18, v7, 0x38u);
        v29 = v18 + 17;
        if ( a6 )
          RtlSetUserMemory(v29, 0, 4u);
        else
          RtlSetVolatileMemory(v29, 0, 4u);
        if ( v11[17] != FileTag )
        {
          v31 = v11[14];
          if ( a6 )
            RtlWriteULongToUser(v18 + 14, v31);
          else
            v18[14] = v31;
          v32 = (int *)(v18 + 16);
          if ( (v11[14] & 0x400) != 0 )
            v33 = v11[17];
          else
            v33 = v11[16];
          if ( a6 )
            RtlWriteULongToUser(v32, v33);
          else
            *v32 = v33;
          goto LABEL_48;
        }
        v44 = WofSanitizeAttributes((unsigned int)v11[14], 0, v30);
        if ( a6 )
          RtlWriteULongToUser(v18 + 14, v44);
        else
          v18[14] = v44;
        if ( byte_140018454 )
        {
          v45 = v11[16];
          if ( !a6 )
          {
LABEL_103:
            v18[16] = v45;
LABEL_48:
            v34 = v18 + 18;
            if ( a6 )
              RtlWriteULong64ToUser(v34, *((_QWORD *)v11 + 9));
            else
              *v34 = *((_QWORD *)v11 + 9);
            v35 = v11[15];
            v36 = (int *)(v18 + 15);
            if ( a6 )
              RtlWriteULongToUser(v36, v35);
            else
              *v36 = v35;
            v26 = v11 + 20;
            v25 = v18 + 20;
            goto LABEL_29;
          }
        }
        else
        {
          v45 = v11[17];
          if ( !a6 )
            goto LABEL_103;
        }
        RtlWriteULongToUser(v18 + 16, v45);
        goto LABEL_48;
    }
    if ( a1 != 78 )
      goto LABEL_8;
    v18 = (unsigned int *)(a4 + v9);
    v10 = v13 + 80;
    if ( a6 )
      RtlCopyToUser(v18, v7, 0x50u);
    else
      RtlCopyVolatileMemory(v18, v7, 0x50u);
    if ( v11[17] == FileTag )
    {
      v42 = WofSanitizeAttributes((unsigned int)v11[14], 0, v41);
      v43 = (int *)(v18 + 14);
      if ( a6 )
        RtlWriteULongToUser(v43, v42);
      else
        *v43 = v42;
      if ( byte_140018454 )
      {
        if ( a6 )
          RtlWriteULongToUser(v18 + 17, 0);
        else
          v18[17] = 0;
      }
    }
    v26 = v11 + 20;
    v25 = v18 + 20;
LABEL_29:
    if ( a6 )
      RtlCopyToUser(v25, v26, v13);
    else
      RtlCopyVolatileMemory(v25, v26, v13);
    v27 = (v10 + 7) & 0xFFFFFFF8;
    if ( a6 )
      RtlWriteULongToUser(v18, v27);
    else
      *v18 = v27;
    v12 = a5;
    a4 = v51;
    v8 = v50;
LABEL_8:
    if ( !*v7 )
      break;
    v14 = (v10 + 7) & 0xFFFFFFF8;
    v15 = v14;
    if ( v14 >= v12 - v9 )
      v15 = v12 - v9;
    v16 = v15 - v10;
    v17 = (void *)(a4 + v9 + v10);
    if ( a6 )
      RtlSetUserMemory(v17, 0, v16);
    else
      RtlSetVolatileMemory(v17, 0, v16);
    v9 += v14;
    v7 = (_DWORD *)((char *)v7 + (unsigned int)*v7);
    v11 = v7;
    if ( (unsigned __int64)v7 >= v8 )
      goto LABEL_117;
    v12 = a5;
    if ( v9 >= a5 )
      goto LABEL_117;
    a3 = v8 - (_DWORD)v7;
    a1 = v49;
    a4 = v51;
  }
  v28 = (_DWORD *)(a4 + v9);
  if ( a6 )
    RtlWriteULongToUser(v28, 0);
  else
    *v28 = 0;
  v9 += v10;
LABEL_117:
  *a7 = v9;
  return 0;
}

```

## disassembly

```asm
0x140037d20  mov     [rsp+arg_18], r9
0x140037d25  mov     [rsp+arg_0], ecx
0x140037d29  push    rbx
0x140037d2a  push    rsi
0x140037d2b  push    rdi
0x140037d2c  push    r12
0x140037d2e  push    r13
0x140037d30  push    r14
0x140037d32  push    r15
0x140037d34  sub     rsp, 40h
0x140037d38  mov     rdi, rdx
0x140037d3b  mov     [rsp+78h+var_58], 0
0x140037d40  mov     [rsp+78h+arg_10], 0
0x140037d4b  mov     r15d, r8d
0x140037d4e  add     r15, rdx
0x140037d51  mov     [rsp+78h+arg_8], r15
0x140037d59  xor     ebx, ebx
0x140037d5b  xor     r13d, r13d
0x140037d5e  mov     rsi, rdx
0x140037d61  movzx   r12d, [rsp+78h+arg_28]
0x140037d6a  mov     edx, [rsp+78h+arg_20]
0x140037d71  mov     r14d, [rsi+3Ch]
0x140037d75  lea     eax, [r8-50h]
0x140037d79  cmp     r14d, eax
0x140037d7c  cmovnb  r14d, eax
0x140037d80  mov     eax, ecx
0x140037d82  sub     eax, 1
0x140037d85  jz      loc_14003805D
0x140037d8b  sub     eax, 1
0x140037d8e  jz      loc_140037E2C
0x140037d94  sub     eax, 24h ; '$'
0x140037d97  jz      loc_140037F35
0x140037d9d  cmp     eax, 28h ; '('
0x140037da0  jz      loc_140038133
0x140037da6  mov     [rsp+78h+var_58], 1
0x140037dab  cmp     dword ptr [rdi], 0
0x140037dae  jz      loc_140037F0F
0x140037db4  mov     ecx, edx
0x140037db6  sub     ecx, ebx
0x140037db8  lea     esi, [r13+7]
0x140037dbc  and     esi, 0FFFFFFF8h
0x140037dbf  mov     r8d, esi
0x140037dc2  cmp     esi, ecx
0x140037dc4  cmovnb  r8d, ecx
0x140037dc8  sub     r8d, r13d; Size
0x140037dcb  lea     ecx, [rbx+r13]
0x140037dcf  add     rcx, r9; void *
0x140037dd2  xor     edx, edx; Val
0x140037dd4  test    r12b, r12b
0x140037dd7  jz      loc_140038009
0x140037ddd  call    RtlSetUserMemory
0x140037de2  mov     [rsp+78h+var_58], 0
0x140037de7  add     ebx, esi
0x140037de9  mov     [rsp+78h+var_48], ebx
0x140037ded  mov     eax, [rdi]
0x140037def  add     rdi, rax
0x140037df2  mov     [rsp+78h+var_40], rdi
0x140037df7  mov     rsi, rdi
0x140037dfa  cmp     rdi, r15
0x140037dfd  jnb     loc_140038281
0x140037e03  mov     edx, [rsp+78h+arg_20]
0x140037e0a  cmp     ebx, edx
0x140037e0c  jnb     loc_140038281
0x140037e12  mov     r8d, r15d
0x140037e15  sub     r8d, edi
0x140037e18  mov     ecx, [rsp+78h+arg_0]
0x140037e1f  mov     r9, [rsp+78h+arg_18]
0x140037e27  jmp     loc_140037D71
0x140037e2c  mov     r15d, ebx
0x140037e2f  add     r15, r9
0x140037e32  lea     r13d, [r14+44h]
0x140037e36  mov     [rsp+78h+var_54], r13d
0x140037e3b  mov     [rsp+78h+var_58], 1
0x140037e40  mov     r8d, 38h ; '8'; Size
0x140037e46  mov     rdx, rdi; Src
0x140037e49  mov     rcx, r15; void *
0x140037e4c  test    r12b, r12b
0x140037e4f  jz      loc_14003803F
0x140037e55  call    RtlCopyToUser
0x140037e5a  mov     eax, cs:FileTag
0x140037e60  cmp     [rsi+44h], eax
0x140037e63  jz      loc_14003821F
0x140037e69  mov     eax, [rsi+38h]
0x140037e6c  test    r12b, r12b
0x140037e6f  jz      loc_14003801D
0x140037e75  mov     edx, eax
0x140037e77  lea     rcx, [r15+38h]
0x140037e7b  call    RtlWriteULongToUser
0x140037e80  lea     rcx, [r15+40h]
0x140037e84  test    dword ptr [rsi+38h], 400h
0x140037e8b  jnz     loc_1400380CF
0x140037e91  mov     eax, [rsi+40h]
0x140037e94  test    r12b, r12b
0x140037e97  jz      loc_140038026
0x140037e9d  mov     edx, eax
0x140037e9f  call    RtlWriteULongToUser
0x140037ea4  mov     eax, [rsi+3Ch]
0x140037ea7  lea     rcx, [r15+3Ch]
0x140037eab  test    r12b, r12b
0x140037eae  jz      loc_14003802D
0x140037eb4  mov     edx, eax
0x140037eb6  call    RtlWriteULongToUser
0x140037ebb  lea     rcx, [r15+44h]; void *
0x140037ebf  lea     rdx, [rdi+50h]; Src
0x140037ec3  mov     r8d, r14d; Size
0x140037ec6  test    r12b, r12b
0x140037ec9  jz      loc_140038013
0x140037ecf  call    RtlCopyToUser
0x140037ed4  lea     eax, [r13+7]
0x140037ed8  and     eax, 0FFFFFFF8h
0x140037edb  test    r12b, r12b
0x140037ede  jz      loc_140037FFC
0x140037ee4  mov     edx, eax
0x140037ee6  mov     rcx, r15
0x140037ee9  call    RtlWriteULongToUser
0x140037eee  mov     [rsp+78h+var_58], 0
0x140037ef3  mov     edx, [rsp+78h+arg_20]
0x140037efa  mov     r9, [rsp+78h+arg_18]
0x140037f02  mov     r15, [rsp+78h+arg_8]
0x140037f0a  jmp     loc_140037DA6
0x140037f0f  mov     ecx, ebx
0x140037f11  add     rcx, r9
0x140037f14  test    r12b, r12b
0x140037f17  jz      loc_140038034
0x140037f1d  xor     edx, edx
0x140037f1f  call    RtlWriteULongToUser
0x140037f24  mov     [rsp+78h+var_58], 0
0x140037f29  add     ebx, r13d
0x140037f2c  mov     [rsp+78h+var_48], ebx
0x140037f30  jmp     loc_140038281
0x140037f35  mov     r15d, ebx
0x140037f38  add     r15, r9
0x140037f3b  lea     r13d, [r14+50h]
0x140037f3f  mov     [rsp+78h+var_54], r13d
0x140037f44  mov     [rsp+78h+var_58], 1
0x140037f49  mov     r8d, 38h ; '8'; Size
0x140037f4f  mov     rdx, rdi; Src
0x140037f52  mov     rcx, r15; void *
0x140037f55  test    r12b, r12b
0x140037f58  jz      loc_1400380C5
0x140037f5e  call    RtlCopyToUser
0x140037f63  lea     rcx, [r15+44h]; void *
0x140037f67  xor     edx, edx; Val
0x140037f69  mov     r8d, 4; Size
0x140037f6f  test    r12b, r12b
0x140037f72  jz      loc_1400380D7
0x140037f78  call    RtlSetUserMemory
0x140037f7d  mov     eax, cs:FileTag
0x140037f83  cmp     [rsi+44h], eax
0x140037f86  jz      loc_1400381BD
0x140037f8c  mov     eax, [rsi+38h]
0x140037f8f  test    r12b, r12b
0x140037f92  jz      loc_140038049
0x140037f98  mov     edx, eax
0x140037f9a  lea     rcx, [r15+38h]
0x140037f9e  call    RtlWriteULongToUser
0x140037fa3  lea     rcx, [r15+40h]
0x140037fa7  test    dword ptr [rsi+38h], 400h
0x140037fae  jz      loc_1400380E1
0x140037fb4  mov     eax, [rsi+44h]
0x140037fb7  test    r12b, r12b
0x140037fba  jz      loc_140038052
0x140037fc0  mov     edx, eax
0x140037fc2  call    RtlWriteULongToUser
0x140037fc7  mov     rax, [rsi+48h]
0x140037fcb  lea     rcx, [r15+48h]
0x140037fcf  test    r12b, r12b
0x140037fd2  jz      short loc_140038004
0x140037fd4  mov     rdx, rax
0x140037fd7  call    RtlWriteULong64ToUser
0x140037fdc  mov     eax, [rsi+3Ch]
0x140037fdf  lea     rcx, [r15+3Ch]
0x140037fe3  test    r12b, r12b
0x140037fe6  jz      short loc_140038059
0x140037fe8  mov     edx, eax
0x140037fea  call    RtlWriteULongToUser
0x140037fef  lea     rdx, [rsi+50h]
0x140037ff3  lea     rcx, [r15+50h]
0x140037ff7  jmp     loc_140037EC3
0x140037ffc  mov     [r15], eax
0x140037fff  jmp     loc_140037EEE
0x140038004  mov     [rcx], rax
0x140038007  jmp     short loc_140037FDC
0x140038009  call    RtlSetVolatileMemory
0x14003800e  jmp     loc_140037DE2
0x140038013  call    RtlCopyVolatileMemory
0x140038018  jmp     loc_140037ED4
0x14003801d  mov     [r15+38h], eax
0x140038021  jmp     loc_140037E80
0x140038026  mov     [rcx], eax
0x140038028  jmp     loc_140037EA4
0x14003802d  mov     [rcx], eax
0x14003802f  jmp     loc_140037EBB
0x140038034  mov     dword ptr [rcx], 0
0x14003803a  jmp     loc_140037F24
0x14003803f  call    RtlCopyVolatileMemory
0x140038044  jmp     loc_140037E5A
0x140038049  mov     [r15+38h], eax
0x14003804d  jmp     loc_140037FA3
0x140038052  mov     [rcx], eax
0x140038054  jmp     loc_140037FC7
0x140038059  mov     [rcx], eax
0x14003805b  jmp     short loc_140037FEF
0x14003805d  mov     r15d, ebx
0x140038060  add     r15, r9
0x140038063  lea     r13d, [r14+40h]
0x140038067  mov     [rsp+78h+var_54], r13d
0x14003806c  mov     [rsp+78h+var_58], 1
0x140038071  mov     r8d, 38h ; '8'; Size
0x140038077  mov     rdx, rdi; Src
0x14003807a  mov     rcx, r15; void *
0x14003807d  test    r12b, r12b
0x140038080  jz      loc_140038129
0x140038086  call    RtlCopyToUser
0x14003808b  mov     eax, cs:FileTag
0x140038091  cmp     [rsi+44h], eax
0x140038094  mov     eax, [rsi+38h]
0x140038097  jz      short loc_1400380E9
0x140038099  test    r12b, r12b
0x14003809c  lea     rcx, [r15+38h]
0x1400380a0  jz      short loc_140038121
0x1400380a2  mov     edx, eax
0x1400380a4  call    RtlWriteULongToUser
0x1400380a9  mov     eax, [rsi+3Ch]
0x1400380ac  lea     rcx, [r15+3Ch]
0x1400380b0  test    r12b, r12b
0x1400380b3  jz      short loc_140038125
0x1400380b5  mov     edx, eax
0x1400380b7  call    RtlWriteULongToUser
0x1400380bc  lea     rcx, [r15+40h]
0x1400380c0  jmp     loc_140037EBF
0x1400380c5  call    RtlCopyVolatileMemory
0x1400380ca  jmp     loc_140037F63
0x1400380cf  mov     eax, [rsi+44h]
0x1400380d2  jmp     loc_140037E94
0x1400380d7  call    RtlSetVolatileMemory
0x1400380dc  jmp     loc_140037F7D
0x1400380e1  mov     eax, [rsi+40h]
0x1400380e4  jmp     loc_140037FB7
0x1400380e9  mov     [rsp+78h+var_50], eax
0x1400380ed  cmp     cs:byte_140018454, 0
0x1400380f4  jz      short loc_1400380FE
0x1400380f6  btr     eax, 0Ah
0x1400380fa  mov     [rsp+78h+var_50], eax
0x1400380fe  cmp     cs:byte_140018455, 0
0x140038105  jnz     short loc_140038117
0x140038107  test    eax, eax
0x140038109  mov     ecx, 80h
0x14003810e  cmovz   eax, ecx
0x140038111  mov     [rsp+78h+var_50], eax
0x140038115  jmp     short loc_140038099
0x140038117  btr     eax, 9
0x14003811b  mov     [rsp+78h+var_50], eax
0x14003811f  jmp     short loc_140038107
0x140038121  mov     [rcx], eax
0x140038123  jmp     short loc_1400380A9
0x140038125  mov     [rcx], eax
0x140038127  jmp     short loc_1400380BC
0x140038129  call    RtlCopyVolatileMemory
0x14003812e  jmp     loc_14003808B
0x140038133  mov     r15d, ebx
0x140038136  add     r15, r9
0x140038139  lea     r13d, [r14+50h]
0x14003813d  mov     [rsp+78h+var_54], r13d
0x140038142  mov     [rsp+78h+var_58], 1
0x140038147  mov     r8d, 50h ; 'P'; Size
0x14003814d  mov     rdx, rdi; Src
0x140038150  mov     rcx, r15; void *
0x140038153  test    r12b, r12b
0x140038156  jz      short loc_1400381A8
0x140038158  call    RtlCopyToUser
0x14003815d  mov     eax, cs:FileTag
0x140038163  cmp     [rsi+44h], eax
0x140038166  jnz     short loc_14003819B
0x140038168  xor     edx, edx
0x14003816a  mov     ecx, [rsi+38h]
0x14003816d  call    WofSanitizeAttributes
0x140038172  lea     rcx, [r15+38h]
0x140038176  test    r12b, r12b
0x140038179  jz      short loc_1400381AF
0x14003817b  mov     edx, eax
0x14003817d  call    RtlWriteULongToUser
0x140038182  cmp     cs:byte_140018454, 0
0x140038189  jz      short loc_14003819B
0x14003818b  test    r12b, r12b
0x14003818e  jz      short loc_1400381B3
0x140038190  xor     edx, edx
0x140038192  lea     rcx, [r15+44h]
0x140038196  call    RtlWriteULongToUser
0x14003819b  lea     rdx, [rsi+50h]
0x14003819f  lea     rcx, [r15+50h]
0x1400381a3  jmp     loc_140037EC3
0x1400381a8  call    RtlCopyVolatileMemory
0x1400381ad  jmp     short loc_14003815D
0x1400381af  mov     [rcx], eax
0x1400381b1  jmp     short loc_140038182
0x1400381b3  mov     dword ptr [r15+44h], 0
0x1400381bb  jmp     short loc_14003819B
0x1400381bd  xor     edx, edx
0x1400381bf  mov     ecx, [rsi+38h]
  ... truncated ...
```
