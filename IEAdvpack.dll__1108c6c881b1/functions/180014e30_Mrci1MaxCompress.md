# Mrci1MaxCompress

- ea: `0x180014e30`
- end: `0x1800151d2`
- name: `Mrci1MaxCompress`
- size: `930`
- prototype: `__int64 __fastcall(__int64, unsigned int, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800156b8`

## callees

- `0x180014894`
- `0x180014a78`
- `0x180014aa0`
- `0x180014e30`
- `0x18001b936`

## pseudocode

```c
__int64 __fastcall Mrci1MaxCompress(__int64 a1, unsigned int a2, _DWORD *a3)
{
  __int64 v3; // rbx
  unsigned int v4; // r9d
  int v5; // r14d
  __int64 result; // rax
  int v8; // eax
  __int64 *v9; // rcx
  __int64 *v10; // rdx
  unsigned int v11; // r15d
  unsigned int v12; // ebp
  unsigned int v13; // edi
  unsigned int v14; // esi
  unsigned int v15; // eax
  unsigned __int64 v16; // r12
  bool v17; // zf
  unsigned __int8 *v18; // r9
  __int64 v19; // rcx
  unsigned int v20; // r8d
  unsigned int v21; // ecx
  unsigned __int8 *v22; // r10
  _BYTE *v23; // rcx
  char *v24; // r10
  char v25; // al
  int v26; // eax
  int v27; // r9d
  __int64 v28; // rax
  unsigned int v29; // r8d
  unsigned int v30; // r10d
  __int16 v31; // cx
  __int64 v32; // rdx
  int v33; // ecx
  __int64 v34; // r9
  __int64 v35; // rcx
  int v36; // r8d
  unsigned int v37; // kr00_4
  unsigned int v38; // [rsp+88h] [rbp+10h]

  LODWORD(v3) = 0;
  dword_180025CA8 = 8;
  v4 = 0x8000;
  dword_180025CA4 = 0;
  v5 = (int)a3;
  qword_180025CB0 = (__int64)a3;
  if ( a2 >= 0x8000 )
  {
    dword_180025CAC = 0x8000;
  }
  else
  {
    dword_180025CAC = a2;
    v4 = a2;
  }
  if ( v4 < 4 )
    return 0xFFFFFFFFLL;
  *a3 = 16798532;
  qword_180025CB0 = (__int64)(a3 + 1);
  dword_180025CAC = v4 - 4;
  result = a2;
  v38 = a2 - 1;
  if ( !a2 )
    return result;
  v8 = 0x2000;
  v9 = qword_180025DC0;
  v10 = qword_180025DC0;
  do
  {
    *(_DWORD *)v9 = -1;
    v9 = (__int64 *)((char *)v10 + 4);
    v10 = (__int64 *)((char *)v10 + 4);
    --v8;
  }
  while ( v8 );
  if ( setjmp_0(Buf) )
    return 0xFFFFFFFFLL;
  v11 = v38;
  v12 = 511;
  v13 = 0;
  if ( v38 + 511 >= 0x1FF )
  {
    v14 = 0;
    v15 = 511;
    do
    {
      if ( v15 > v11 )
      {
        v12 = v11;
        v15 = v11;
      }
      v16 = a1 + v15;
      while ( 1 )
      {
        v17 = (_DWORD)v3 == v12;
        if ( (unsigned int)v3 >= v12 )
          break;
        v18 = (unsigned __int8 *)(a1 + (unsigned int)v3);
        v19 = (*v18 + (v18[1] << 8)) & 0x1FFF;
        v20 = *((_DWORD *)qword_180025DC0 + v19);
        *((_DWORD *)qword_180025DC0 + v19) = v3;
        *((_DWORD *)qword_18002DDC0 + (unsigned int)v3 % 0x113F) = v20;
        v21 = v20;
        if ( v20 < (unsigned int)v3 )
        {
          do
          {
            if ( (unsigned int)v3 - v21 > 0x113E )
              break;
            v22 = (unsigned __int8 *)(a1 + v21);
            if ( v18[v13] == v22[v13] && *v18 + (v18[1] << 8) == *v22 + (v22[1] << 8) )
            {
              v23 = v18 + 2;
              v24 = (char *)(v22 + 2);
              while ( (unsigned __int64)v23 <= v16 )
              {
                v25 = *v24++;
                if ( *v23 != v25 )
                  break;
                ++v23;
              }
              if ( (int)v23 - (int)a1 - (int)v3 > v13 )
              {
                v13 = (_DWORD)v23 - a1 - v3;
                v14 = v20;
                if ( (unsigned __int64)v23 > v16 )
                  break;
              }
            }
            v20 = *((_DWORD *)qword_18002DDC0 + v20 % 0x113F);
            v21 = v20;
          }
          while ( v20 < (unsigned int)v3 );
          v11 = v38;
        }
        if ( v13 < 2 )
        {
          LODWORD(v3) = v3 + 1;
          mrci1outsingle(*v18);
          v13 = 0;
        }
        else
        {
          mrci1outstring((unsigned int)v3 - v14, v13);
          v26 = v3 + v13;
          if ( (unsigned int)v3 + v13 >= v11 )
          {
            v13 = 0;
            v17 = v26 == v12;
            LODWORD(v3) = v26;
            break;
          }
          v3 = (unsigned int)(v3 + 1);
          v14 = (unsigned int)v3 % 0x113F;
          if ( --v13 )
          {
            v27 = v3;
            v28 = (unsigned int)v3;
            v29 = (unsigned int)v3 % 0x113F;
            v30 = (unsigned int)v3 % 0x113F;
            do
            {
              v14 = v29 + 1;
              v31 = *(unsigned __int8 *)(v3 + a1);
              v3 = (unsigned int)(v27 + 1);
              v32 = (v31 + (*(unsigned __int8 *)(v28 + a1 + 1) << 8)) & 0x1FFF;
              v33 = *((_DWORD *)qword_180025DC0 + v32);
              *((_DWORD *)qword_180025DC0 + v32) = v27;
              *((_DWORD *)qword_18002DDC0 + v30) = v33;
              if ( v29 + 1 < 0x113F )
              {
                ++v29;
              }
              else
              {
                v14 = 0;
                v29 = 0;
              }
              v28 = (unsigned int)v3;
              ++v27;
              v30 = v29;
              --v13;
            }
            while ( v13 );
            v11 = v38;
          }
        }
      }
      if ( v17 )
      {
        v34 = (unsigned int)v3;
        v35 = (*(unsigned __int8 *)((unsigned int)v3 + a1) + (*(unsigned __int8 *)((unsigned int)v3 + a1 + 1) << 8))
            & 0x1FFF;
        v36 = *((_DWORD *)qword_180025DC0 + v35);
        *((_DWORD *)qword_180025DC0 + v35) = v3;
        v37 = v3;
        LODWORD(v3) = v3 + 1;
        *((_DWORD *)qword_18002DDC0 + v37 % 0x113F) = v36;
        mrci1outsingle(*(unsigned __int8 *)(v34 + a1));
      }
      mrci1outstring(4415, 0);
      v12 += 512;
      v15 = v12;
    }
    while ( v12 <= v11 + 511 );
  }
  if ( dword_180025CA8 != 8 )
    charbuf();
  result = (unsigned int)(qword_180025CB0 - v5);
  if ( (unsigned int)result > v11 )
    return 0xFFFFFFFFLL;
  return result;
}

```

## disassembly

```asm
0x180014e30  push    rbx
0x180014e32  push    rbp
0x180014e33  push    rsi
0x180014e34  push    rdi
0x180014e35  push    r12
0x180014e37  push    r13
0x180014e39  push    r14
0x180014e3b  push    r15
0x180014e3d  sub     rsp, 38h
0x180014e41  xor     ebx, ebx
0x180014e43  mov     cs:dword_180025CA8, 8
0x180014e4d  mov     r9d, 8000h
0x180014e53  mov     [rsp+78h+var_58], ebx
0x180014e57  mov     cs:dword_180025CA4, ebx
0x180014e5d  mov     r14, r8
0x180014e60  mov     cs:qword_180025CB0, r8
0x180014e67  mov     r13, rcx
0x180014e6a  cmp     edx, r9d
0x180014e6d  jnb     short loc_180014E7A
0x180014e6f  mov     cs:dword_180025CAC, edx
0x180014e75  mov     r9d, edx
0x180014e78  jmp     short loc_180014E81
0x180014e7a  mov     cs:dword_180025CAC, r9d
0x180014e81  or      esi, 0FFFFFFFFh
0x180014e84  cmp     r9d, 4
0x180014e88  jb      loc_1800151BF
0x180014e8e  lea     rax, [r8+4]
0x180014e92  mov     dword ptr [r8], 1005344h
0x180014e99  mov     cs:qword_180025CB0, rax
0x180014ea0  lea     eax, [r9-4]
0x180014ea4  mov     cs:dword_180025CAC, eax
0x180014eaa  mov     eax, edx
0x180014eac  add     edx, esi
0x180014eae  mov     [rsp+78h+arg_8], edx
0x180014eb5  test    eax, eax
0x180014eb7  jz      loc_1800151C1
0x180014ebd  lea     r12, qword_180025DC0
0x180014ec4  mov     eax, 2000h
0x180014ec9  mov     rcx, r12
0x180014ecc  mov     rdx, r12
0x180014ecf  mov     [rcx], esi
0x180014ed1  lea     rcx, [rdx+4]
0x180014ed5  mov     rdx, rcx
0x180014ed8  sub     eax, 1
0x180014edb  jnz     short loc_180014ECF
0x180014edd  lea     rcx, Buf; Buf
0x180014ee4  mov     rdx, rsp
0x180014ee7  call    _setjmp_0
0x180014eec  test    eax, eax
0x180014eee  jnz     loc_1800151BF
0x180014ef4  mov     r15d, [rsp+78h+arg_8]
0x180014efc  mov     ebp, 1FFh
0x180014f01  mov     edi, ebx
0x180014f03  lea     eax, [r15+1FFh]
0x180014f0a  cmp     eax, ebp
0x180014f0c  jb      loc_1800151A0
0x180014f12  mov     esi, [rsp+78h+var_58]
0x180014f16  lea     r10, qword_18002DDC0
0x180014f1d  mov     eax, ebp
0x180014f1f  cmp     eax, r15d
0x180014f22  jbe     short loc_180014F2A
0x180014f24  mov     ebp, r15d
0x180014f27  mov     eax, r15d
0x180014f2a  mov     r12d, eax
0x180014f2d  lea     r11, qword_180025DC0
0x180014f34  add     r12, r13
0x180014f37  jmp     short loc_180014F40
0x180014f39  lea     r10, qword_18002DDC0
0x180014f40  cmp     ebx, ebp
0x180014f42  jnb     loc_180015126
0x180014f48  mov     r9d, ebx
0x180014f4b  add     r9, r13
0x180014f4e  movzx   ecx, byte ptr [r9+1]
0x180014f53  movzx   eax, byte ptr [r9]
0x180014f57  shl     ecx, 8
0x180014f5a  add     ecx, eax
0x180014f5c  mov     eax, 0ED80C865h
0x180014f61  and     ecx, 1FFFh
0x180014f67  mul     ebx
0x180014f69  mov     r8d, [r11+rcx*4]
0x180014f6d  mov     [r11+rcx*4], ebx
0x180014f71  mov     ecx, ebx
0x180014f73  shr     edx, 0Ch
0x180014f76  imul    eax, edx, 113Fh
0x180014f7c  sub     ecx, eax
0x180014f7e  mov     [r10+rcx*4], r8d
0x180014f82  mov     ecx, r8d
0x180014f85  cmp     r8d, ebx
0x180014f88  jnb     loc_18001503C
0x180014f8e  lea     r15, qword_18002DDC0
0x180014f95  mov     eax, ebx
0x180014f97  sub     eax, ecx
0x180014f99  cmp     eax, 113Eh
0x180014f9e  ja      loc_180015034
0x180014fa4  mov     r10d, ecx
0x180014fa7  add     r10, r13
0x180014faa  mov     ecx, edi
0x180014fac  mov     al, [rcx+r10]
0x180014fb0  cmp     [rcx+r9], al
0x180014fb4  jnz     short loc_180015010
0x180014fb6  movzx   eax, byte ptr [r9]
0x180014fba  movzx   edx, byte ptr [r9+1]
0x180014fbf  movzx   ecx, byte ptr [r10+1]
0x180014fc4  shl     edx, 8
0x180014fc7  add     edx, eax
0x180014fc9  shl     ecx, 8
0x180014fcc  movzx   eax, byte ptr [r10]
0x180014fd0  add     ecx, eax
0x180014fd2  cmp     edx, ecx
0x180014fd4  jnz     short loc_180015010
0x180014fd6  lea     rcx, [r9+2]
0x180014fda  add     r10, 2
0x180014fde  jmp     short loc_180014FEE
0x180014fe0  mov     al, [r10]
0x180014fe3  lea     r10, [rdx+1]
0x180014fe7  cmp     [rcx], al
0x180014fe9  jnz     short loc_180014FF6
0x180014feb  inc     rcx
0x180014fee  mov     rdx, r10
0x180014ff1  cmp     rcx, r12
0x180014ff4  jbe     short loc_180014FE0
0x180014ff6  mov     eax, ecx
0x180014ff8  sub     eax, r13d
0x180014ffb  sub     eax, ebx
0x180014ffd  cmp     eax, edi
0x180014fff  jbe     short loc_180015010
0x180015001  mov     [rsp+78h+var_58], r8d
0x180015006  mov     edi, eax
0x180015008  mov     esi, r8d
0x18001500b  cmp     rcx, r12
0x18001500e  ja      short loc_180015034
0x180015010  mov     eax, 0ED80C865h
0x180015015  mul     r8d
0x180015018  shr     edx, 0Ch
0x18001501b  imul    eax, edx, 113Fh
0x180015021  sub     r8d, eax
0x180015024  mov     r8d, [r15+r8*4]
0x180015028  mov     ecx, r8d
0x18001502b  cmp     r8d, ebx
0x18001502e  jb      loc_180014F95
0x180015034  mov     r15d, [rsp+78h+arg_8]
0x18001503c  cmp     edi, 2
0x18001503f  jb      loc_180015100
0x180015045  mov     ecx, ebx
0x180015047  mov     edx, edi
0x180015049  sub     ecx, esi
0x18001504b  call    mrci1outstring
0x180015050  lea     eax, [rbx+rdi]
0x180015053  cmp     eax, r15d
0x180015056  jnb     loc_180015119
0x18001505c  inc     ebx
0x18001505e  lea     r11, qword_180025DC0
0x180015065  mov     eax, 0ED80C865h
0x18001506a  mov     esi, ebx
0x18001506c  mul     ebx
0x18001506e  shr     edx, 0Ch
0x180015071  imul    eax, edx, 113Fh
0x180015077  sub     esi, eax
0x180015079  mov     [rsp+78h+var_58], esi
0x18001507d  add     edi, 0FFFFFFFFh
0x180015080  jz      loc_180014F39
0x180015086  mov     r9d, ebx
0x180015089  mov     eax, ebx
0x18001508b  mov     r8d, esi
0x18001508e  lea     r11, qword_180025DC0
0x180015095  mov     r10d, esi
0x180015098  lea     r15, qword_18002DDC0
0x18001509f  movzx   edx, byte ptr [rax+r13+1]
0x1800150a5  lea     esi, [r8+1]
0x1800150a9  movzx   ecx, byte ptr [rbx+r13]
0x1800150ae  lea     ebx, [r9+1]
0x1800150b2  shl     edx, 8
0x1800150b5  add     edx, ecx
0x1800150b7  mov     eax, r10d
0x1800150ba  and     edx, 1FFFh
0x1800150c0  mov     [rsp+78h+var_58], esi
0x1800150c4  mov     ecx, [r11+rdx*4]
0x1800150c8  mov     [r11+rdx*4], r9d
0x1800150cc  mov     [r15+rax*4], ecx
0x1800150d0  cmp     esi, 113Fh
0x1800150d6  jb      short loc_1800150E3
0x1800150d8  xor     esi, esi
0x1800150da  mov     [rsp+78h+var_58], esi
0x1800150de  xor     r8d, r8d
0x1800150e1  jmp     short loc_1800150E6
0x1800150e3  mov     r8d, esi
0x1800150e6  mov     eax, ebx
0x1800150e8  mov     r9d, ebx
0x1800150eb  mov     r10d, r8d
0x1800150ee  sub     edi, 1
0x1800150f1  jnz     short loc_18001509F
0x1800150f3  mov     r15d, [rsp+78h+arg_8]
0x1800150fb  jmp     loc_180014F39
0x180015100  movzx   ecx, byte ptr [r9]
0x180015104  inc     ebx
0x180015106  call    mrci1outsingle
0x18001510b  xor     edi, edi
0x18001510d  lea     r11, qword_180025DC0
0x180015114  jmp     loc_180014F39
0x180015119  xor     edi, edi
0x18001511b  lea     r10, qword_18002DDC0
0x180015122  cmp     eax, ebp
0x180015124  mov     ebx, eax
0x180015126  jnz     short loc_180015173
0x180015128  mov     r9d, ebx
0x18001512b  movzx   ecx, byte ptr [r9+r13+1]
0x180015131  movzx   eax, byte ptr [r9+r13]
0x180015136  shl     ecx, 8
0x180015139  add     ecx, eax
0x18001513b  lea     rax, qword_180025DC0
0x180015142  and     ecx, 1FFFh
0x180015148  mov     r8d, [rax+rcx*4]
0x18001514c  mov     [rax+rcx*4], ebx
0x18001514f  mov     ecx, ebx
0x180015151  mov     eax, 0ED80C865h
0x180015156  mul     ebx
0x180015158  inc     ebx
0x18001515a  shr     edx, 0Ch
0x18001515d  imul    eax, edx, 113Fh
0x180015163  sub     ecx, eax
0x180015165  mov     [r10+rcx*4], r8d
0x180015169  movzx   ecx, byte ptr [r9+r13]
0x18001516e  call    mrci1outsingle
0x180015173  xor     edx, edx
0x180015175  mov     ecx, 113Fh
0x18001517a  call    mrci1outstring
0x18001517f  add     ebp, 200h
0x180015185  lea     ecx, [r15+1FFh]
0x18001518c  lea     r10, qword_18002DDC0
0x180015193  mov     eax, ebp
0x180015195  cmp     ebp, ecx
0x180015197  jbe     loc_180014F1F
0x18001519d  or      esi, 0FFFFFFFFh
0x1800151a0  cmp     cs:dword_180025CA8, 8
0x1800151a7  jz      short loc_1800151AE
0x1800151a9  call    charbuf
0x1800151ae  mov     eax, dword ptr cs:qword_180025CB0
0x1800151b4  sub     eax, r14d
0x1800151b7  cmp     eax, r15d
0x1800151ba  cmova   eax, esi
0x1800151bd  jmp     short loc_1800151C1
0x1800151bf  mov     eax, esi
0x1800151c1  add     rsp, 38h
0x1800151c5  pop     r15
0x1800151c7  pop     r14
0x1800151c9  pop     r13
0x1800151cb  pop     r12
0x1800151cd  pop     rdi
0x1800151ce  pop     rsi
0x1800151cf  pop     rbp
0x1800151d0  pop     rbx
0x1800151d1  retn
```
