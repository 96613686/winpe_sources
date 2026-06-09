# utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>> *)

- ea: `0x180010f40`
- end: `0x180011329`
- name: `?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@@Z`
- size: `1001`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180010c78`
- `0x180011330`
- `0x180011450`
- `0x180011640`

## callees

- `0x18000d128`
- `0x180010f40`

## pseudocode

```c
unsigned __int64 __fastcall utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(
        _QWORD *a1,
        unsigned __int64 *a2)
{
  unsigned __int64 v2; // r10
  unsigned __int64 v3; // r8
  unsigned __int64 *v5; // rdi
  _QWORD *v6; // r14
  __int64 v7; // r12
  unsigned __int64 result; // rax
  int v9; // ecx
  __int64 v10; // r11
  _BYTE **v11; // rdx
  bool v12; // r9
  unsigned __int64 *v13; // rcx
  unsigned __int64 v14; // rbx
  bool v15; // si
  unsigned __int64 **v16; // r10
  unsigned __int64 **v17; // rdx
  bool v18; // r9
  unsigned __int64 *v19; // rcx
  unsigned __int64 *v20; // rcx
  unsigned __int64 *v21; // rcx
  unsigned __int64 *v22; // r11
  unsigned __int64 v23; // rcx
  unsigned __int64 *v24; // rdx
  unsigned __int64 *v25; // r8
  __int64 v26; // rax
  unsigned __int64 *v27; // rdi
  __int64 v28; // rax
  bool v29; // zf
  unsigned __int64 v30; // rdx
  __int64 v31; // r10
  unsigned __int64 v32; // rcx
  unsigned __int64 *v33; // r9
  unsigned __int64 *v34; // r8
  __int64 v35; // rax
  __int64 v36; // rcx
  _QWORD *v37; // r8
  unsigned __int64 v38; // rdx
  _QWORD *v39; // r10
  _QWORD *v40; // rax
  unsigned __int64 *v41; // r9

  v2 = *a2;
  v3 = a2[2];
  v5 = a2;
  v6 = (_QWORD *)(*a2 & 0xFFFFFFFFFFFFFFFEuLL);
  LOBYTE(a2) = v3 != (_QWORD)&utl::_TreeSentinel;
  v7 = 1;
  result = v3 != (_QWORD)&utl::_TreeSentinel;
  v9 = result + (v5[1] != (_QWORD)&utl::_TreeSentinel);
  if ( v9 )
  {
    if ( v9 == 1 )
    {
      v22 = (unsigned __int64 *)v5[(unsigned __int8)a2 + 1];
      if ( (unsigned __int64 *)a1[(unsigned __int8)a2 + 1] == v5 )
        a1[(unsigned __int8)a2 + 1] = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(
                                        v5,
                                        a2);
      if ( (unsigned __int64 *)(*v6 & 0xFFFFFFFFFFFFFFFEuLL) == v5 )
      {
        *v6 = v22;
      }
      else
      {
        if ( (unsigned __int64 *)v6[2] == v5 )
          v7 = 2;
        v6[v7] = v22;
      }
      result = *v5;
      *v22 = *v5;
    }
    else if ( *(_UNKNOWN **)(v3 + 8) == &utl::_TreeSentinel )
    {
      v10 = 1;
      v11 = (_BYTE **)(v3 + 16);
      v12 = (*(_BYTE *)v3 & 1) != 0 && (**v11 & 1) != 0;
      *(_QWORD *)v3 = v2;
      v13 = (unsigned __int64 *)v5[1];
      *(_QWORD *)(v3 + 8) = v13;
      *v13 = v3 | *(_DWORD *)v13 & 1LL;
      *(_QWORD *)*v11 = v3 | 1;
      result = *v6 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( (unsigned __int64 *)result == v5 )
      {
        *v6 = v3;
      }
      else
      {
        result = 8;
        if ( (unsigned __int64 *)v6[2] == v5 )
          result = 16;
        *(_QWORD *)((char *)v6 + result) = v3;
      }
      if ( v12 )
      {
        v14 = v3;
        v15 = 1;
        goto LABEL_43;
      }
    }
    else
    {
      do
      {
        v16 = (unsigned __int64 **)(v3 + 8);
        v14 = v3;
        v3 = *(_QWORD *)(v3 + 8);
      }
      while ( *(_UNKNOWN **)(v3 + 8) != &utl::_TreeSentinel );
      v10 = 1;
      v17 = (unsigned __int64 **)(v3 + 16);
      v18 = (*(_BYTE *)v3 & 1) != 0 && (*(_BYTE *)*v17 & 1) != 0;
      v19 = *v17;
      *v16 = *v17;
      *v19 = v14 | 1;
      *(_QWORD *)v3 = *v5;
      v20 = (unsigned __int64 *)v5[1];
      *(_QWORD *)(v3 + 8) = v20;
      *v20 = v3 | *(_DWORD *)v20 & 1LL;
      v21 = (unsigned __int64 *)v5[2];
      *v17 = v21;
      *v21 = v3 | *(_DWORD *)v21 & 1LL;
      result = *v6 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( (unsigned __int64 *)result == v5 )
      {
        *v6 = v3;
      }
      else
      {
        result = 8;
        if ( (unsigned __int64 *)v6[2] == v5 )
          result = 16;
        *(_QWORD *)((char *)v6 + result) = v3;
      }
      if ( v18 )
      {
        v15 = 0;
        goto LABEL_43;
      }
    }
  }
  else if ( a1 == v6 )
  {
    *a1 = a1;
    a1[1] = a1;
    a1[2] = a1;
  }
  else
  {
    v10 = 1;
    if ( (unsigned __int64 *)a1[1] == v5 )
    {
      a1[1] = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(v5, 0);
    }
    else if ( (unsigned __int64 *)a1[2] == v5 )
    {
      LOBYTE(a2) = 1;
      a1[2] = utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(v5, a2);
    }
    v15 = v6[2] == (_QWORD)v5;
    result = v15;
    v6[v15 + 1] = &utl::_TreeSentinel;
    if ( ((unsigned __int8)v10 & *(_BYTE *)v5) != 0 )
    {
      v14 = (unsigned __int64)v6;
      while ( 1 )
      {
LABEL_43:
        if ( ((unsigned __int8)v10 & **(_BYTE **)(v14 + 8 * (v10 ^ v15) + 8)) == 0 )
        {
          v23 = *(_QWORD *)v14 & 0xFFFFFFFFFFFFFFFEuLL;
          v24 = *(unsigned __int64 **)(v14 + 8 * (v10 ^ v15) + 8);
          v25 = (unsigned __int64 *)v24[v15 + 1];
          *v24 = v10 | v23;
          if ( (*(_QWORD *)v23 & 0xFFFFFFFFFFFFFFFEuLL) == v14 )
          {
            *(_QWORD *)v23 = v24;
          }
          else
          {
            v26 = 8;
            if ( *(_QWORD *)(v23 + 16) == v14 )
              v26 = 16;
            *(_QWORD *)(v26 + v23) = v24;
          }
          *(_QWORD *)v14 = v24;
          *v25 = v14 | (unsigned int)v10 & *(_DWORD *)v25;
          *(_QWORD *)(v14 + 8 * (v10 ^ v15) + 8) = v25;
          v24[v15 + 1] = v14;
        }
        v27 = *(unsigned __int64 **)(v14 + 8 * (v10 ^ v15) + 8);
        if ( ((unsigned __int8)v10 & *(_BYTE *)v27[(v10 ^ v15) + 1]) == 0 )
        {
          v40 = (_QWORD *)v27[(v10 ^ v15) + 1];
          *v40 |= v10;
          v36 = *(_QWORD *)v14;
          v37 = (_QWORD *)(*(_QWORD *)v14 & 0xFFFFFFFFFFFFFFFEuLL);
          v38 = *(_QWORD *)(v14 + 8 * (v10 ^ v15) + 8);
          v39 = (_QWORD *)(v38 + 8LL * v15);
          goto LABEL_60;
        }
        if ( ((unsigned __int8)v10 & *(_BYTE *)v27[v15 + 1]) == 0 )
          break;
        *v27 &= ~1uLL;
        v28 = *(_QWORD *)v14;
        if ( ((unsigned __int8)*(_QWORD *)v14 & (unsigned __int8)v10) == 0 )
        {
          result = v10 | v28;
          *(_QWORD *)v14 = result;
          return result;
        }
        result = v28 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( a1 == (_QWORD *)result )
          return result;
        v29 = *(_QWORD *)(result + 16) == v14;
        v14 = result;
        v15 = v29;
      }
      v30 = *v27 & 0xFFFFFFFFFFFFFFFEuLL;
      v31 = (unsigned __int8)(v10 ^ v15);
      v32 = v27[(v10 ^ v31) + 1];
      v33 = (unsigned __int64 *)(v32 + 8 * v31);
      v34 = (unsigned __int64 *)v33[1];
      *(_QWORD *)v32 = v10 | v30;
      v35 = 8;
      if ( *(unsigned __int64 **)(v30 + 16) == v27 )
        v35 = 16;
      *(_QWORD *)(v35 + v30) = v32;
      *v27 = v10 | v32;
      *v34 = (unsigned __int64)v27 | (unsigned int)v10 & *(_DWORD *)v34;
      v27[(v10 ^ v31) + 1] = (unsigned __int64)v34;
      v33[1] = (unsigned __int64)v27;
      v36 = *(_QWORD *)v14;
      v37 = (_QWORD *)(*(_QWORD *)v14 & 0xFFFFFFFFFFFFFFFEuLL);
      v38 = *(_QWORD *)(v14 + 8 * (v10 ^ v15) + 8);
      v39 = (_QWORD *)(v38 + 8LL * v15);
LABEL_60:
      v41 = (unsigned __int64 *)v39[1];
      *(_QWORD *)v38 = v36;
      if ( (*v37 & 0xFFFFFFFFFFFFFFFEuLL) == v14 )
      {
        *v37 = v38;
      }
      else
      {
        if ( v37[2] == v14 )
          v7 = 2;
        v37[v7] = v38;
      }
      *(_QWORD *)v14 = v10 | v38;
      *v41 = v14 | (unsigned int)v10 & *(_DWORD *)v41;
      result = v10 ^ v15;
      *(_QWORD *)(v14 + 8 * result + 8) = v41;
      v39[1] = v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010f40  push    rbx
0x180010f42  push    rbp
0x180010f43  push    rsi
0x180010f44  push    rdi
0x180010f45  push    r12
0x180010f47  push    r14
0x180010f49  push    r15
0x180010f4b  sub     rsp, 20h
0x180010f4f  mov     r10, [rdx]
0x180010f52  lea     r11, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x180010f59  mov     r8, [rdx+10h]
0x180010f5d  mov     r15, rcx
0x180010f60  mov     rdi, rdx
0x180010f63  mov     r14, r10
0x180010f66  and     r14, 0FFFFFFFFFFFFFFFEh
0x180010f6a  mov     ebp, 10h
0x180010f6f  cmp     r8, r11
0x180010f72  setnz   dl
0x180010f75  xor     ecx, ecx
0x180010f77  cmp     [rdi+8], r11
0x180010f7b  lea     r12d, [rbp-8]
0x180010f7f  movzx   eax, dl
0x180010f82  setnz   cl
0x180010f85  add     ecx, eax
0x180010f87  jz      loc_1800110ED
0x180010f8d  cmp     ecx, 1
0x180010f90  jz      loc_1800110A9
0x180010f96  cmp     [r8+8], r11
0x180010f9a  jnz     short loc_18001100F
0x180010f9c  lea     r11d, [rbp-0Fh]
0x180010fa0  lea     rdx, [r8+10h]
0x180010fa4  test    [r8], r11b
0x180010fa7  jz      short loc_180010FB6
0x180010fa9  mov     rax, [rdx]
0x180010fac  test    [rax], r11b
0x180010faf  jz      short loc_180010FB6
0x180010fb1  mov     r9b, r11b
0x180010fb4  jmp     short loc_180010FB9
0x180010fb6  xor     r9b, r9b
0x180010fb9  mov     [r8], r10
0x180010fbc  mov     rcx, [rdi+8]
0x180010fc0  mov     [r8+8], rcx
0x180010fc4  mov     eax, [rcx]
0x180010fc6  and     rax, r11
0x180010fc9  or      rax, r8
0x180010fcc  mov     [rcx], rax
0x180010fcf  mov     rcx, r8
0x180010fd2  mov     rax, [rdx]
0x180010fd5  or      rcx, r11
0x180010fd8  mov     [rax], rcx
0x180010fdb  mov     rax, [r14]
0x180010fde  and     rax, 0FFFFFFFFFFFFFFFEh
0x180010fe2  cmp     rax, rdi
0x180010fe5  jnz     short loc_180010FEC
0x180010fe7  mov     [r14], r8
0x180010fea  jmp     short loc_180010FFB
0x180010fec  cmp     [r14+10h], rdi
0x180010ff0  mov     rax, r12
0x180010ff3  cmovz   rax, rbp
0x180010ff7  mov     [rax+r14], r8
0x180010ffb  test    r9b, r9b
0x180010ffe  jz      loc_180011319
0x180011004  mov     rbx, r8
0x180011007  mov     sil, r11b
0x18001100a  jmp     loc_180011157
0x18001100f  lea     r10, [r8+8]
0x180011013  mov     rbx, r8
0x180011016  mov     r8, [r10]
0x180011019  cmp     [r8+8], r11
0x18001101d  jnz     short loc_18001100F
0x18001101f  mov     r11d, 1
0x180011025  lea     rdx, [r8+10h]
0x180011029  test    [r8], r11b
0x18001102c  jz      short loc_18001103B
0x18001102e  mov     rax, [rdx]
0x180011031  test    [rax], r11b
0x180011034  jz      short loc_18001103B
0x180011036  mov     r9b, r11b
0x180011039  jmp     short loc_18001103E
0x18001103b  xor     r9b, r9b
0x18001103e  mov     rcx, [rdx]
0x180011041  mov     rax, rbx
0x180011044  mov     [r10], rcx
0x180011047  or      rax, r11
0x18001104a  mov     [rcx], rax
0x18001104d  mov     rax, [rdi]
0x180011050  mov     [r8], rax
0x180011053  mov     rcx, [rdi+8]
0x180011057  mov     [r8+8], rcx
0x18001105b  mov     eax, [rcx]
0x18001105d  and     rax, r11
0x180011060  or      rax, r8
0x180011063  mov     [rcx], rax
0x180011066  mov     rcx, [rdi+10h]
0x18001106a  mov     [rdx], rcx
0x18001106d  mov     eax, [rcx]
0x18001106f  and     rax, r11
0x180011072  or      rax, r8
0x180011075  mov     [rcx], rax
0x180011078  mov     rax, [r14]
0x18001107b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001107f  cmp     rax, rdi
0x180011082  jnz     short loc_180011089
0x180011084  mov     [r14], r8
0x180011087  jmp     short loc_180011098
0x180011089  cmp     [r14+10h], rdi
0x18001108d  mov     rax, r12
0x180011090  cmovz   rax, rbp
0x180011094  mov     [rax+r14], r8
0x180011098  test    r9b, r9b
0x18001109b  jz      loc_180011319
0x1800110a1  xor     sil, sil
0x1800110a4  jmp     loc_180011157
0x1800110a9  movzx   ebx, dl
0x1800110ac  mov     r11, [rdi+rbx*8+8]
0x1800110b1  cmp     [r15+rbx*8+8], rdi
0x1800110b6  jnz     short loc_1800110C5
0x1800110b8  mov     rcx, rdi
0x1800110bb  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x1800110c0  mov     [r15+rbx*8+8], rax
0x1800110c5  mov     rax, [r14]
0x1800110c8  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800110cc  cmp     rax, rdi
0x1800110cf  jnz     short loc_1800110D6
0x1800110d1  mov     [r14], r11
0x1800110d4  jmp     short loc_1800110E2
0x1800110d6  cmp     [r14+10h], rdi
0x1800110da  cmovz   r12, rbp
0x1800110de  mov     [r12+r14], r11
0x1800110e2  mov     rax, [rdi]
0x1800110e5  mov     [r11], rax
0x1800110e8  jmp     loc_180011319
0x1800110ed  cmp     r15, r14
0x1800110f0  jnz     short loc_180011102
0x1800110f2  mov     [r15], r15
0x1800110f5  mov     [r15+8], r15
0x1800110f9  mov     [r15+10h], r15
0x1800110fd  jmp     loc_180011319
0x180011102  mov     r11d, 1
0x180011108  cmp     [r15+8], rdi
0x18001110c  jnz     short loc_18001111E
0x18001110e  xor     edx, edx
0x180011110  mov     rcx, rdi
0x180011113  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x180011118  mov     [r15+8], rax
0x18001111c  jmp     short loc_180011133
0x18001111e  cmp     [r15+10h], rdi
0x180011122  jnz     short loc_180011133
0x180011124  mov     dl, r11b
0x180011127  mov     rcx, rdi
0x18001112a  call    ?_Traverse@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@_N@Z; utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_Traverse(bool)
0x18001112f  mov     [r15+10h], rax
0x180011133  cmp     [r14+10h], rdi
0x180011137  lea     rcx, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18001113e  setz    sil
0x180011142  movzx   eax, sil
0x180011146  mov     [r14+rax*8+8], rcx
0x18001114b  test    [rdi], r11b
0x18001114e  jz      loc_180011319
0x180011154  mov     rbx, r14
0x180011157  movzx   eax, sil
0x18001115b  xor     rax, r11
0x18001115e  mov     rax, [rbx+rax*8+8]
0x180011163  test    [rax], r11b
0x180011166  jnz     short loc_1800111CD
0x180011168  mov     rcx, [rbx]
0x18001116b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18001116f  movzx   eax, sil
0x180011173  xor     rax, r11
0x180011176  movzx   r9d, sil
0x18001117a  mov     rdx, [rbx+rax*8+8]
0x18001117f  mov     rax, rcx
0x180011182  or      rax, r11
0x180011185  mov     r8, [rdx+r9*8+8]
0x18001118a  mov     [rdx], rax
0x18001118d  mov     rax, [rcx]
0x180011190  and     rax, 0FFFFFFFFFFFFFFFEh
0x180011194  cmp     rax, rbx
0x180011197  jnz     short loc_18001119E
0x180011199  mov     [rcx], rdx
0x18001119c  jmp     short loc_1800111AD
0x18001119e  cmp     [rcx+10h], rbx
0x1800111a2  mov     rax, r12
0x1800111a5  cmovz   rax, rbp
0x1800111a9  mov     [rax+rcx], rdx
0x1800111ad  mov     [rbx], rdx
0x1800111b0  mov     eax, [r8]
0x1800111b3  and     rax, r11
0x1800111b6  or      rax, rbx
0x1800111b9  mov     [r8], rax
0x1800111bc  movzx   eax, sil
0x1800111c0  xor     rax, r11
0x1800111c3  mov     [rbx+rax*8+8], r8
0x1800111c8  mov     [rdx+r9*8+8], rbx
0x1800111cd  movzx   eax, sil
0x1800111d1  xor     rax, r11
0x1800111d4  mov     rdi, [rbx+rax*8+8]
0x1800111d9  movzx   eax, sil
0x1800111dd  xor     rax, r11
0x1800111e0  mov     rax, [rdi+rax*8+8]
0x1800111e5  test    [rax], r11b
0x1800111e8  jz      loc_1800112A6
0x1800111ee  movzx   r14d, sil
0x1800111f2  mov     rax, [rdi+r14*8+8]
0x1800111f7  test    [rax], r11b
0x1800111fa  jz      short loc_180011230
0x1800111fc  and     qword ptr [rdi], 0FFFFFFFFFFFFFFFEh
0x180011200  mov     rax, [rbx]
0x180011203  test    r11b, al
0x180011206  jz      short loc_180011225
0x180011208  and     rax, 0FFFFFFFFFFFFFFFEh
0x18001120c  cmp     r15, rax
0x18001120f  jz      loc_180011319
0x180011215  cmp     [rax+10h], rbx
0x180011219  mov     rbx, rax
0x18001121c  setz    sil
0x180011220  jmp     loc_180011157
0x180011225  or      rax, r11
0x180011228  mov     [rbx], rax
0x18001122b  jmp     loc_180011319
0x180011230  mov     rdx, [rdi]
0x180011233  mov     al, sil
0x180011236  xor     al, r11b
0x180011239  and     rdx, 0FFFFFFFFFFFFFFFEh
0x18001123d  movzx   r10d, al
0x180011241  mov     eax, r10d
0x180011244  xor     rax, r11
0x180011247  mov     rcx, [rdi+rax*8+8]
0x18001124c  mov     rax, rdx
0x18001124f  or      rax, r11
0x180011252  lea     r9, [rcx+r10*8]
0x180011256  mov     r8, [r9+8]
0x18001125a  mov     [rcx], rax
0x18001125d  mov     rax, r12
0x180011260  cmp     [rdx+10h], rdi
0x180011264  cmovz   rax, rbp
0x180011268  xor     r10, r11
0x18001126b  mov     [rax+rdx], rcx
0x18001126f  or      rcx, r11
0x180011272  mov     [rdi], rcx
0x180011275  mov     eax, [r8]
0x180011278  and     rax, r11
0x18001127b  or      rax, rdi
0x18001127e  mov     [r8], rax
0x180011281  mov     [rdi+r10*8+8], r8
0x180011286  mov     [r9+8], rdi
0x18001128a  mov     rcx, [rbx]
0x18001128d  mov     r8, rcx
0x180011290  movzx   eax, sil
0x180011294  and     r8, 0FFFFFFFFFFFFFFFEh
0x180011298  xor     rax, r11
0x18001129b  mov     rdx, [rbx+rax*8+8]
0x1800112a0  lea     r10, [rdx+r14*8]
0x1800112a4  jmp     short loc_1800112D3
0x1800112a6  movzx   eax, sil
0x1800112aa  xor     rax, r11
0x1800112ad  mov     rax, [rdi+rax*8+8]
0x1800112b2  or      [rax], r11
0x1800112b5  mov     rcx, [rbx]
0x1800112b8  mov     r8, rcx
0x1800112bb  movzx   eax, sil
0x1800112bf  and     r8, 0FFFFFFFFFFFFFFFEh
0x1800112c3  xor     rax, r11
0x1800112c6  mov     rdx, [rbx+rax*8+8]
0x1800112cb  movzx   eax, sil
0x1800112cf  lea     r10, [rdx+rax*8]
0x1800112d3  mov     r9, [r10+8]
0x1800112d7  mov     [rdx], rcx
0x1800112da  mov     rax, [r8]
0x1800112dd  and     rax, 0FFFFFFFFFFFFFFFEh
0x1800112e1  cmp     rax, rbx
0x1800112e4  jnz     short loc_1800112EB
0x1800112e6  mov     [r8], rdx
0x1800112e9  jmp     short loc_1800112F7
0x1800112eb  cmp     [r8+10h], rbx
0x1800112ef  cmovz   r12, rbp
0x1800112f3  mov     [r12+r8], rdx
0x1800112f7  or      rdx, r11
0x1800112fa  mov     [rbx], rdx
0x1800112fd  mov     eax, [r9]
0x180011300  and     rax, r11
0x180011303  or      rax, rbx
0x180011306  mov     [r9], rax
0x180011309  movzx   eax, sil
0x18001130d  xor     rax, r11
0x180011310  mov     [rbx+rax*8+8], r9
0x180011315  mov     [r10+8], rbx
0x180011319  add     rsp, 20h
0x18001131d  pop     r15
0x18001131f  pop     r14
0x180011321  pop     r12
0x180011323  pop     rdi
0x180011324  pop     rsi
0x180011325  pop     rbp
0x180011326  pop     rbx
0x180011327  retn
```
