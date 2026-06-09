# CJointStereo_Read(CDK_BITSTREAM *,CJointStereoData *,int,int,int,CJointStereoPersistentData *,CCplxPredictionData *,int,int,int,uint)

- ea: `0x1800285e0`
- end: `0x180028b15`
- name: `?CJointStereo_Read@@YAHPEAUCDK_BITSTREAM@@PEAUCJointStereoData@@HHHPEAUCJointStereoPersistentData@@PEAUCCplxPredictionData@@HHHI@Z`
- size: `1333`
- prototype: `__int64 __usercall@<rax>(struct CDK_BITSTREAM *@<rcx>, struct CJointStereoData *@<rdx>, int@<r8d>, int@<r9d>, int, struct CJointStereoPersistentData *, struct CCplxPredictionData *, int, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180014ae0`

## callees

- `0x180013550`
- `0x1800175b0`
- `0x180017db8`
- `0x1800285e0`
- `0x18004dd14`

## pseudocode

```c
__int64 __fastcall CJointStereo_Read(
        struct CDK_BITSTREAM *a1,
        struct CJointStereoData *a2,
        __int64 a3,
        int a4,
        int a5,
        struct CJointStereoPersistentData *a6,
        struct CCplxPredictionData *a7,
        int a8,
        int a9,
        int a10,
        unsigned int a11)
{
  int v11; // ebx
  size_t v12; // r15
  int v14; // r12d
  int v15; // ecx
  int v17; // ecx
  int v18; // eax
  int v19; // edx
  int i; // ebx
  __int64 j; // rbp
  int v23; // eax
  int ii; // ecx
  __int64 jj; // rdx
  int kk; // ebx
  int mm; // ebp
  char v28; // r8
  char v29; // al
  unsigned int v30; // ecx
  int v31; // eax
  int k; // r9d
  __int64 v33; // r13
  int v34; // edx
  __int64 v35; // r10
  __int64 v36; // r11
  __int64 v37; // rcx
  __int64 v38; // rbp
  __int64 v39; // rcx
  __int16 v40; // r8
  __int16 v41; // ax
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // r8
  __int16 v48; // ax
  __int16 v49; // ax
  __int16 v50; // r9
  __int16 v51; // ax
  char *v52; // r10
  __int64 v53; // rcx
  __int16 v54; // ax
  int v55; // r8d
  __int64 v56; // r13
  __int64 v57; // rdx
  int m; // r8d
  unsigned __int64 v59; // r9
  __int64 n; // rdx
  __int64 v61; // rcx
  __int64 v62; // [rsp+20h] [rbp-68h]
  __int64 v63; // [rsp+28h] [rbp-60h]
  __int64 v64; // [rsp+30h] [rbp-58h]
  int v65; // [rsp+90h] [rbp+8h]
  int v66; // [rsp+98h] [rbp+10h]
  __int16 v67; // [rsp+A8h] [rbp+20h]
  int v68; // [rsp+B0h] [rbp+28h]
  __int16 v69; // [rsp+C8h] [rbp+40h]

  LOBYTE(v11) = 0;
  v12 = a4;
  v14 = a3;
  v15 = *((_DWORD *)a1 + 1);
  if ( 2 - v15 > 0 )
  {
    v11 = *(_DWORD *)a1 << (2 - v15);
    v23 = CDK_get32((char *)a1 + 8, a2, a3);
    v15 = *((_DWORD *)a1 + 1) + 32;
    *(_DWORD *)a1 = v23;
  }
  v17 = v15 - 2;
  v18 = *(_DWORD *)a1 >> v17;
  *((_DWORD *)a1 + 1) = v17;
  *(_BYTE *)a2 = (v11 | v18) & 3;
  memset_0((char *)a2 + 1, 0, (unsigned int)v12);
  *((_BYTE *)a2 + 65) = 0;
  if ( a8 )
    *(_DWORD *)a7 = 0;
  if ( *(_BYTE *)a2 == 1 )
  {
    for ( i = 0; i < v14; ++i )
    {
      for ( j = 0; (int)j < (int)v12; j = (unsigned int)(j + 1) )
        *((_BYTE *)a2 + j + 1) |= (unsigned int)CDKreadBit((__int64)a1) << i;
    }
LABEL_8:
    if ( !a8 )
      return 0;
LABEL_31:
    if ( *(_BYTE *)a2 == 3 )
    {
      if ( *((_BYTE *)a2 + 65) )
      {
        if ( a10 == 2 )
        {
          if ( *((_BYTE *)a6 + 2080) == 2 )
            goto LABEL_38;
        }
        else if ( *((_BYTE *)a6 + 2080) != 2 )
        {
          goto LABEL_38;
        }
        memset_0((char *)a6 + 32, 0, 0x400u);
        memset_0((char *)a6 + 1056, 0, 0x400u);
LABEL_38:
        memset_0((char *)a7 + 4, 0, 0x400u);
        memset_0((char *)a7 + 1028, 0, 0x400u);
        *(_BYTE *)a7 = CDKreadBit((__int64)a1);
        v29 = CDKreadBit((__int64)a1);
        v30 = a11 & 0x100000;
        *((_BYTE *)a7 + 2) = v29;
        if ( v29 )
        {
          if ( v30 )
          {
            *((_BYTE *)a7 + 3) = 0;
LABEL_51:
            v31 = 0;
            goto LABEL_43;
          }
          *((_BYTE *)a7 + 3) = CDKreadBit((__int64)a1);
        }
        else if ( v30 )
        {
          goto LABEL_51;
        }
        v31 = CDKreadBit((__int64)a1);
LABEL_43:
        v68 = v31;
        for ( k = 0; ; ++k )
        {
          v66 = k;
          if ( k >= v14 )
            break;
          v33 = k;
          v34 = 0;
          v35 = k;
          v64 = k;
          v36 = k;
          v37 = k;
          while ( 1 )
          {
            v65 = v34;
            if ( v34 >= (int)v12 )
              break;
            if ( v31 == 1 )
            {
              if ( k > 0 )
              {
                v38 = v34;
                v33 = v35;
                v39 = (v35 << 6) + v34;
                v40 = *((_WORD *)a7 + v39 - 62);
                v41 = *((_WORD *)a7 + v39 + 450);
                goto LABEL_62;
              }
              if ( a10 != 2 )
              {
                v44 = v37;
                goto LABEL_58;
              }
              if ( *((_BYTE *)a6 + 2080) != 2 )
              {
                v44 = v33;
LABEL_58:
                v38 = v34;
                v45 = v34 + (v44 << 6);
                v40 = *((_WORD *)a6 + v45 + 16);
                v41 = *((_WORD *)a6 + v45 + 528);
                goto LABEL_62;
              }
              v42 = *((unsigned __int8 *)a6 + 2082);
              if ( !(_BYTE)v42 )
                return 0xFFFFFFFFLL;
              v38 = v34;
              v43 = (v42 << 6) + v34;
              v40 = *((_WORD *)a6 + v43 - 48);
              v41 = *((_WORD *)a6 + v43 + 464);
            }
            else
            {
              v38 = v34;
              if ( v34 <= 0 )
              {
                v40 = 0;
                v41 = 0;
              }
              else
              {
                v46 = (v33 << 6) + v34;
                v40 = *((_WORD *)a7 + v46 + 1);
                v41 = *((_WORD *)a7 + v46 + 513);
              }
            }
LABEL_62:
            v67 = v41;
            v69 = v40;
            v63 = v36 << 6;
            v47 = (v36 << 6) + v38;
            v62 = v47;
            if ( ((unsigned __int8)(1 << k) & *((_BYTE *)a2 + v38 + 1)) != 0 )
            {
              v48 = CBlock_DecodeHuffmanWord(a1, (const struct CodeBookDescription *)&off_180098870);
              v47 = v62;
              *((_WORD *)a7 + v62 + 2) = v69 - v48 + 60;
              if ( *((_BYTE *)a7 + 2) )
              {
                v49 = CBlock_DecodeHuffmanWord(a1, (const struct CodeBookDescription *)&off_180098870);
                v47 = v62;
                v50 = v67 - v49 + 60;
              }
              else
              {
                v50 = 0;
              }
              v34 = v65;
              v51 = v50;
            }
            else
            {
              v51 = 0;
              *((_WORD *)a7 + v47 + 2) = 0;
              v50 = 0;
            }
            v52 = (char *)a7 + 2 * v47;
            *((_WORD *)v52 + 514) = v51;
            if ( v34 + 1 < (int)v12 )
            {
              v53 = v38 + v63;
              *((_WORD *)a7 + v53 + 3) = *((_WORD *)a7 + v47 + 2);
              *((_WORD *)a7 + v53 + 515) = v50;
            }
            v34 += 2;
            k = v66;
            *((_WORD *)a6 + v47 + 16) = *((_WORD *)a7 + v47 + 2);
            v54 = *((_WORD *)v52 + 514);
            v35 = v64;
            *((_WORD *)a6 + v47 + 528) = v54;
            v37 = v64;
            v31 = v68;
            v36 = v64;
          }
          v55 = v12;
          if ( (int)v12 < 64 )
          {
            v56 = v33 << 6;
            do
            {
              v57 = v55++;
              *((_WORD *)a7 + v57 + v56 + 2) = 0;
              *((_WORD *)a7 + v57 + v56 + 514) = 0;
              *((_WORD *)a6 + v57 + v56 + 16) = 0;
              *((_WORD *)a6 + v57 + v56 + 528) = 0;
            }
            while ( v55 < 64 );
          }
          v31 = v68;
        }
      }
    }
    else
    {
      for ( m = 0; m < v14; ++m )
      {
        v59 = (unsigned __int64)(unsigned int)m << 6;
        for ( n = 0; n != 64; ++n )
        {
          *((_WORD *)a6 + v59 + n + 16) = 0;
          v61 = n + v59;
          *((_WORD *)a6 + v61 + 528) = 0;
        }
      }
    }
    *((_BYTE *)a6 + 2082) = v14;
    return 0;
  }
  if ( *(_BYTE *)a2 == 2 )
  {
    if ( (int)v12 > 0 )
    {
      LOBYTE(v19) = -1;
      memset_0((char *)a2 + 1, v19, v12);
    }
    goto LABEL_8;
  }
  if ( *(_BYTE *)a2 != 3 || (a11 & 0x4300) == 0 )
    goto LABEL_8;
  if ( a8 )
  {
    *((_BYTE *)a2 + 65) = 1;
    if ( (unsigned int)CDKreadBit((__int64)a1) )
    {
      for ( ii = 0; ii < v14; ++ii )
      {
        for ( jj = 0; (int)jj < (int)v12; jj = (unsigned int)(jj + 1) )
          *((_BYTE *)a2 + jj + 1) |= 1 << ii;
      }
    }
    else
    {
      for ( kk = 0; kk < v14; ++kk )
      {
        for ( mm = 0; mm < (int)v12; mm += 2 )
        {
          v28 = *((_BYTE *)a2 + mm + 1) | ((unsigned int)CDKreadBit((__int64)a1) << kk);
          *((_BYTE *)a2 + mm + 1) = v28;
          if ( mm + 1 < a9 )
            *((_BYTE *)a2 + mm + 2) |= v28 & (unsigned __int8)(1 << kk);
        }
      }
    }
    goto LABEL_31;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1800285e0  mov     [rsp+arg_10], rbx
0x1800285e5  push    rbp
0x1800285e6  push    rsi
0x1800285e7  push    rdi
0x1800285e8  push    r12
0x1800285ea  push    r13
0x1800285ec  push    r14
0x1800285ee  push    r15
0x1800285f0  sub     rsp, 50h
0x1800285f4  xor     ebx, ebx
0x1800285f6  movsxd  r15, r9d
0x1800285f9  mov     r14, rcx
0x1800285fc  mov     r12d, r8d
0x1800285ff  mov     ecx, [rcx+4]
0x180028602  mov     rsi, rdx
0x180028605  lea     eax, [rbx+2]
0x180028608  sub     eax, ecx
0x18002860a  test    eax, eax
0x18002860c  jg      loc_1800286CC
0x180028612  mov     eax, [r14]
0x180028615  add     ecx, 0FFFFFFFEh
0x180028618  shr     eax, cl
0x18002861a  xor     edx, edx; Val
0x18002861c  mov     [r14+4], ecx
0x180028620  or      al, bl
0x180028622  and     al, 3
0x180028624  mov     r8d, r15d; Size
0x180028627  lea     rcx, [rsi+1]; void *
0x18002862b  mov     [rsi], al
0x18002862d  call    memset_0
0x180028632  mov     r13d, [rsp+88h+arg_38]
0x18002863a  mov     rdi, [rsp+88h+arg_30]
0x180028642  mov     byte ptr [rsi+41h], 0
0x180028646  test    r13d, r13d
0x180028649  jnz     loc_1800286EB
0x18002864f  movzx   ecx, byte ptr [rsi]
0x180028652  sub     ecx, 1
0x180028655  jz      short loc_18002869E
0x180028657  sub     ecx, 1
0x18002865a  jz      short loc_180028689
0x18002865c  cmp     ecx, 1
0x18002865f  jz      loc_1800286F6
0x180028665  test    r13d, r13d
0x180028668  jnz     loc_18002879D
0x18002866e  xor     eax, eax
0x180028670  mov     rbx, [rsp+88h+arg_10]
0x180028678  add     rsp, 50h
0x18002867c  pop     r15
0x18002867e  pop     r14
0x180028680  pop     r13
0x180028682  pop     r12
0x180028684  pop     rdi
0x180028685  pop     rsi
0x180028686  pop     rbp
0x180028687  retn
0x180028689  test    r15d, r15d
0x18002868c  jle     short loc_180028665
0x18002868e  mov     r8, r15; Size
0x180028691  lea     rcx, [rsi+1]; void *
0x180028695  mov     dl, 0FFh; Val
0x180028697  call    memset_0
0x18002869c  jmp     short loc_180028665
0x18002869e  xor     ebx, ebx
0x1800286a0  test    r12d, r12d
0x1800286a3  jle     short loc_180028665
0x1800286a5  xor     ebp, ebp
0x1800286a7  test    r15d, r15d
0x1800286aa  jle     short loc_1800286C3
0x1800286ac  mov     rcx, r14
0x1800286af  call    CDKreadBit
0x1800286b4  mov     ecx, ebx
0x1800286b6  shl     eax, cl
0x1800286b8  or      [rbp+rsi+1], al
0x1800286bc  inc     ebp
0x1800286be  cmp     ebp, r15d
0x1800286c1  jl      short loc_1800286AC
0x1800286c3  inc     ebx
0x1800286c5  cmp     ebx, r12d
0x1800286c8  jl      short loc_1800286A5
0x1800286ca  jmp     short loc_180028665
0x1800286cc  mov     ebx, [r14]
0x1800286cf  mov     ecx, eax
0x1800286d1  shl     ebx, cl
0x1800286d3  lea     rcx, [r14+8]
0x1800286d7  call    CDK_get32
0x1800286dc  mov     ecx, [r14+4]
0x1800286e0  add     ecx, 20h ; ' '
0x1800286e3  mov     [r14], eax
0x1800286e6  jmp     loc_180028612
0x1800286eb  mov     dword ptr [rdi], 0
0x1800286f1  jmp     loc_18002864F
0x1800286f6  test    [rsp+88h+arg_50], 4300h
0x180028701  jz      loc_180028665
0x180028707  test    r13d, r13d
0x18002870a  jz      loc_180028AC8
0x180028710  mov     rcx, r14
0x180028713  mov     byte ptr [rsi+41h], 1
0x180028717  call    CDKreadBit
0x18002871c  test    eax, eax
0x18002871e  jz      short loc_18002874C
0x180028720  xor     ecx, ecx
0x180028722  test    r12d, r12d
0x180028725  jle     short loc_18002879D
0x180028727  mov     r8d, 1
0x18002872d  xor     edx, edx
0x18002872f  shl     r8b, cl
0x180028732  test    r15d, r15d
0x180028735  jle     short loc_180028743
0x180028737  or      [rdx+rsi+1], r8b
0x18002873c  inc     edx
0x18002873e  cmp     edx, r15d
0x180028741  jl      short loc_180028737
0x180028743  inc     ecx
0x180028745  cmp     ecx, r12d
0x180028748  jl      short loc_180028727
0x18002874a  jmp     short loc_18002879D
0x18002874c  xor     ebx, ebx
0x18002874e  test    r12d, r12d
0x180028751  jle     short loc_18002879D
0x180028753  xor     ebp, ebp
0x180028755  test    r15d, r15d
0x180028758  jle     short loc_180028796
0x18002875a  mov     rcx, r14
0x18002875d  call    CDKreadBit
0x180028762  movsxd  rdx, ebp
0x180028765  mov     ecx, ebx
0x180028767  shl     eax, cl
0x180028769  or      al, [rsi+rdx+1]
0x18002876d  mov     r8b, al
0x180028770  mov     [rsi+rdx+1], al
0x180028774  lea     eax, [rbp+1]
0x180028777  cmp     eax, [rsp+88h+arg_40]
0x18002877e  jge     short loc_18002878E
0x180028780  mov     eax, 1
0x180028785  shl     al, cl
0x180028787  and     al, r8b
0x18002878a  or      [rsi+rdx+2], al
0x18002878e  add     ebp, 2
0x180028791  cmp     ebp, r15d
0x180028794  jl      short loc_18002875A
0x180028796  inc     ebx
0x180028798  cmp     ebx, r12d
0x18002879b  jl      short loc_180028753
0x18002879d  cmp     byte ptr [rsi], 3
0x1800287a0  mov     rbx, [rsp+88h+arg_28]
0x1800287a8  jnz     loc_180028AD0
0x1800287ae  cmp     byte ptr [rsi+41h], 0
0x1800287b2  jz      loc_180028B09
0x1800287b8  cmp     [rsp+88h+arg_48], 2
0x1800287c0  mov     ebp, 400h
0x1800287c5  jnz     short loc_1800287D2
0x1800287c7  cmp     byte ptr [rbx+820h], 2
0x1800287ce  jz      short loc_1800287FA
0x1800287d0  jmp     short loc_1800287DB
0x1800287d2  cmp     byte ptr [rbx+820h], 2
0x1800287d9  jnz     short loc_1800287FA
0x1800287db  lea     rcx, [rbx+20h]; void *
0x1800287df  mov     r8, rbp; Size
0x1800287e2  xor     edx, edx; Val
0x1800287e4  call    memset_0
0x1800287e9  lea     rcx, [rbx+420h]; void *
0x1800287f0  mov     r8, rbp; Size
0x1800287f3  xor     edx, edx; Val
0x1800287f5  call    memset_0
0x1800287fa  lea     rcx, [rdi+4]; void *
0x1800287fe  mov     r8, rbp; Size
0x180028801  xor     edx, edx; Val
0x180028803  call    memset_0
0x180028808  lea     rcx, [rdi+404h]; void *
0x18002880f  mov     r8, rbp; Size
0x180028812  xor     edx, edx; Val
0x180028814  call    memset_0
0x180028819  mov     rcx, r14
0x18002881c  call    CDKreadBit
0x180028821  mov     rcx, r14
0x180028824  mov     [rdi], al
0x180028826  call    CDKreadBit
0x18002882b  mov     ecx, [rsp+88h+arg_50]
0x180028832  and     ecx, 100000h
0x180028838  mov     [rdi+2], al
0x18002883b  test    al, al
0x18002883d  jz      loc_1800288D3
0x180028843  test    ecx, ecx
0x180028845  jz      short loc_180028850
0x180028847  mov     byte ptr [rdi+3], 0
0x18002884b  jmp     loc_1800288D7
0x180028850  mov     rcx, r14
0x180028853  call    CDKreadBit
0x180028858  mov     [rdi+3], al
0x18002885b  mov     rcx, r14
0x18002885e  call    CDKreadBit
0x180028863  mov     [rsp+88h+arg_20], eax
0x18002886a  xor     r9d, r9d
0x18002886d  mov     [rsp+88h+arg_8], r9d
0x180028875  cmp     r9d, r12d
0x180028878  jge     loc_180028B09
0x18002887e  movsxd  r13, r9d
0x180028881  xor     edx, edx
0x180028883  mov     r10, r13
0x180028886  mov     [rsp+88h+var_58], r13
0x18002888b  mov     r11, r13
0x18002888e  mov     rcx, r13
0x180028891  mov     [rsp+88h+arg_0], edx
0x180028898  cmp     edx, r15d
0x18002889b  jge     loc_180028A74
0x1800288a1  cmp     eax, 1
0x1800288a4  jnz     loc_18002893A
0x1800288aa  test    r9d, r9d
0x1800288ad  jle     short loc_1800288DB
0x1800288af  mov     rax, r10
0x1800288b2  movsxd  rbp, edx
0x1800288b5  shl     rax, 6
0x1800288b9  mov     r13, r10
0x1800288bc  lea     rcx, [rax+rbp]
0x1800288c0  movzx   r8d, word ptr [rdi+rcx*2-7Ch]
0x1800288c6  movzx   eax, word ptr [rdi+rcx*2+384h]
0x1800288ce  jmp     loc_180028961
0x1800288d3  test    ecx, ecx
0x1800288d5  jz      short loc_18002885B
0x1800288d7  xor     eax, eax
0x1800288d9  jmp     short loc_180028863
0x1800288db  cmp     [rsp+88h+arg_48], 2
0x1800288e3  jnz     short loc_18002891D
0x1800288e5  cmp     byte ptr [rbx+820h], 2
0x1800288ec  jnz     short loc_180028918
0x1800288ee  movzx   eax, byte ptr [rbx+822h]
0x1800288f5  test    al, al
0x1800288f7  jz      loc_180028AC8
0x1800288fd  shl     rax, 6
0x180028901  movsxd  rbp, edx
0x180028904  lea     rcx, [rax+rbp]
0x180028908  movzx   r8d, word ptr [rbx+rcx*2-60h]
0x18002890e  movzx   eax, word ptr [rbx+rcx*2+3A0h]
0x180028916  jmp     short loc_180028961
0x180028918  mov     rax, r13
0x18002891b  jmp     short loc_180028920
0x18002891d  mov     rax, rcx
0x180028920  shl     rax, 6
0x180028924  movsxd  rbp, edx
0x180028927  add     rax, rbp
0x18002892a  movzx   r8d, word ptr [rbx+rax*2+20h]
0x180028930  movzx   eax, word ptr [rbx+rax*2+420h]
0x180028938  jmp     short loc_180028961
0x18002893a  movsxd  rbp, edx
0x18002893d  test    edx, edx
0x18002893f  jle     short loc_18002895C
0x180028941  mov     rax, r13
0x180028944  shl     rax, 6
0x180028948  lea     rcx, [rax+rbp]
0x18002894c  movzx   r8d, word ptr [rdi+rcx*2+2]
0x180028952  movzx   eax, word ptr [rdi+rcx*2+402h]
0x18002895a  jmp     short loc_180028961
0x18002895c  xor     r8d, r8d
0x18002895f  xor     eax, eax
0x180028961  mov     [rsp+88h+arg_18], eax
0x180028968  mov     ecx, r9d
0x18002896b  mov     rax, r11
0x18002896e  mov     [rsp+88h+arg_38], r8d
0x180028976  shl     rax, 6
0x18002897a  mov     [rsp+88h+var_60], rax
0x18002897f  lea     r8, [rax+rbp]
0x180028983  mov     eax, 1
0x180028988  shl     eax, cl
0x18002898a  mov     [rsp+88h+var_68], r8
0x18002898f  test    [rsi+rbp+1], al
0x180028993  jz      short loc_1800289FA
0x180028995  lea     rdx, off_180098870; struct CodeBookDescription *
0x18002899c  mov     rcx, r14; struct CDK_BITSTREAM *
0x18002899f  call    ?CBlock_DecodeHuffmanWord@@YAHPEAUCDK_BITSTREAM@@PEBUCodeBookDescription@@@Z; CBlock_DecodeHuffmanWord(CDK_BITSTREAM *,CodeBookDescription const *)
0x1800289a4  mov     ecx, [rsp+88h+arg_38]
0x1800289ab  mov     r8, [rsp+88h+var_68]
0x1800289b0  sub     cx, ax
0x1800289b3  add     cx, 3Ch ; '<'
0x1800289b7  mov     [rdi+r8*2+4], cx
0x1800289bd  cmp     byte ptr [rdi+2], 0
0x1800289c1  jz      short loc_1800289EA
0x1800289c3  lea     rdx, off_180098870; struct CodeBookDescription *
0x1800289ca  mov     rcx, r14; struct CDK_BITSTREAM *
0x1800289cd  call    ?CBlock_DecodeHuffmanWord@@YAHPEAUCDK_BITSTREAM@@PEBUCodeBookDescription@@@Z; CBlock_DecodeHuffmanWord(CDK_BITSTREAM *,CodeBookDescription const *)
0x1800289d2  mov     r9d, [rsp+88h+arg_18]
0x1800289da  mov     r8, [rsp+88h+var_68]
0x1800289df  sub     r9w, ax
0x1800289e3  add     r9w, 3Ch ; '<'
0x1800289e8  jmp     short loc_1800289ED
0x1800289ea  xor     r9d, r9d
0x1800289ed  mov     edx, [rsp+88h+arg_0]
0x1800289f4  movzx   eax, r9w
0x1800289f8  jmp     short loc_180028A05
0x1800289fa  xor     eax, eax
0x1800289fc  mov     [rdi+r8*2+4], ax
0x180028a02  xor     r9d, r9d
0x180028a05  mov     r11d, 404h
0x180028a0b  lea     r10, [rdi+r8*2]
0x180028a0f  mov     [r11+r10], ax
0x180028a14  lea     eax, [rdx+1]
0x180028a17  cmp     eax, r15d
0x180028a1a  jge     short loc_180028A38
0x180028a1c  mov     rcx, [rsp+88h+var_60]
0x180028a21  movzx   eax, word ptr [rdi+r8*2+4]
0x180028a27  add     rcx, rbp
  ... truncated ...
```
