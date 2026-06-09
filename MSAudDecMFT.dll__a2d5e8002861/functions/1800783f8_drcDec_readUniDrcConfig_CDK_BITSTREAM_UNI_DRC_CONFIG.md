# drcDec_readUniDrcConfig(CDK_BITSTREAM *,UNI_DRC_CONFIG *)

- ea: `0x1800783f8`
- end: `0x1800788c0`
- name: `?drcDec_readUniDrcConfig@@YA?AW4DRC_ERROR@@PEAUCDK_BITSTREAM@@PEAUUNI_DRC_CONFIG@@@Z`
- size: `1224`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting`

## callers

- `0x180070940`

## callees

- `0x1800110c0`
- `0x180012264`
- `0x18004d320`
- `0x18004dd14`
- `0x180075de0`
- `0x180075fec`
- `0x180076184`
- `0x180076aa8`
- `0x1800777bc`
- `0x18007792c`
- `0x1800783f8`
- `0x180096060`
- `0x18009606c`

## pseudocode

```c
__int64 __fastcall drcDec_readUniDrcConfig(_DWORD *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  unsigned __int8 v6; // al
  __int64 v7; // r8
  int v8; // ebx
  int v9; // eax
  unsigned __int8 v10; // al
  int v11; // ebp
  __int64 v12; // r8
  __int64 v13; // r8
  int v14; // r13d
  __int64 v15; // r8
  int v16; // r12d
  char v17; // al
  char v18; // bl
  char v19; // di
  __int64 v20; // r8
  unsigned __int8 v21; // al
  bool v22; // zf
  int v23; // ebp
  __int64 v24; // r8
  unsigned int v25; // ebx
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  unsigned int v28; // ecx
  int v29; // eax
  char v30; // al
  int v31; // r15d
  _OWORD *v32; // rdi
  __int64 v33; // rax
  _OWORD *v34; // rdx
  __int128 v35; // xmm1
  int i; // edi
  int j; // edi
  unsigned int v38; // ecx
  char v39; // al
  int v40; // edi
  void *v41; // r15
  unsigned int v42; // ecx
  char v43; // al
  int v44; // r15d
  _OWORD *v45; // rdi
  int v46; // r9d
  __int64 v47; // rax
  _OWORD *v48; // rdx
  __int128 v49; // xmm1
  unsigned __int8 v50; // al
  _QWORD v51[2]; // [rsp+30h] [rbp-58h] BYREF

  memset(v51, 0, 11);
  if ( !a2 )
    return 4294967196LL;
  v6 = CDKreadBits(a1, 1, a3);
  v22 = *(_BYTE *)a2 == v6;
  *(_BYTE *)a2 = v6;
  v8 = !v22;
  if ( v6 == 1 )
  {
    v9 = CDKreadBits(a1, 18, v7) + 1000;
    v22 = *(_DWORD *)(a2 + 4) == v9;
    *(_DWORD *)(a2 + 4) = v9;
    v8 |= !v22;
  }
  v10 = CDKreadBits(a1, 7, v7);
  v22 = *(_BYTE *)(a2 + 8) == v10;
  *(_BYTE *)(a2 + 8) = v10;
  v11 = v8 | !v22;
  if ( (unsigned int)CDKreadBits(a1, 1, v12) == 1 )
  {
    v14 = CDKreadBits(a1, 3, v13);
    v16 = CDKreadBits(a1, 4, v15);
  }
  else
  {
    v14 = 0;
    v16 = 0;
  }
  v17 = CDKreadBits(a1, 3, v13);
  v18 = *(_BYTE *)(a2 + 11);
  v19 = v17;
  *(_BYTE *)(a2 + 11) = v17;
  v21 = CDKreadBits(a1, 6, v20);
  v22 = *(_BYTE *)(a2 + 14) == v21;
  *(_BYTE *)(a2 + 14) = v21;
  if ( v18 != v19 )
    v11 = 1;
  v23 = !v22 | v11;
  result = readChannelLayout(a1, v51);
  v25 = result;
  if ( !(_DWORD)result )
  {
    if ( !v23 )
    {
      v26 = v51[0] - *(_QWORD *)(a2 + 17);
      if ( v51[0] == *(_QWORD *)(a2 + 17) )
      {
        v27 = *(unsigned __int16 *)(a2 + 25);
        v26 = LOWORD(v51[1]) - v27;
        if ( LOWORD(v51[1]) == v27 )
          v26 = BYTE2(v51[1]) - (unsigned __int64)*(unsigned __int8 *)(a2 + 27);
      }
      v23 = v26 != 0;
    }
    v28 = *(unsigned __int8 *)(a2 + 8);
    v29 = *(_DWORD *)((char *)v51 + 7);
    *(_QWORD *)(a2 + 17) = v51[0];
    *(_DWORD *)(a2 + 24) = v29;
    v30 = 6;
    if ( v28 < 6 )
      v30 = v28;
    v31 = 0;
    *(_BYTE *)(a2 + 10) = v30;
    if ( v28 )
    {
      while ( 1 )
      {
        v32 = *(_OWORD **)(a2 + 21088);
        memset_0(v32, 0, 0x108u);
        result = readDownmixInstructions(a1, 0, a2 + 17, v32);
        v25 = result;
        if ( (_DWORD)result )
          break;
        if ( v31 < 6 )
        {
          if ( !v23 )
            v23 = memcmp_0(v32, (const void *)(a2 + 264LL * v31 + 28), 0x108u) != 0;
          v33 = 2;
          v34 = (_OWORD *)(a2 + 264LL * v31 + 28);
          v24 = 128;
          do
          {
            *v34 = *v32;
            v34[1] = v32[1];
            v34[2] = v32[2];
            v34[3] = v32[3];
            v34[4] = v32[4];
            v34[5] = v32[5];
            v34[6] = v32[6];
            v35 = v32[7];
            v32 += 8;
            v34[7] = v35;
            v34 += 8;
            --v33;
          }
          while ( v33 );
          *(_QWORD *)v34 = *(_QWORD *)v32;
        }
        if ( ++v31 >= *(unsigned __int8 *)(a2 + 8) )
          goto LABEL_27;
      }
    }
    else
    {
LABEL_27:
      for ( i = 0; i < v14; ++i )
      {
        CDKpushFor(a1, 4);
        CDKpushFor(a1, 7);
      }
      for ( j = 0; j < v16; ++j )
        skipDrcInstructionsBasic(a1);
      v38 = *(unsigned __int8 *)(a2 + 11);
      v39 = 2;
      if ( v38 < 2 )
        v39 = *(_BYTE *)(a2 + 11);
      v40 = 0;
      *(_BYTE *)(a2 + 13) = v39;
      if ( v38 )
      {
        while ( 1 )
        {
          v41 = *(void **)(a2 + 21088);
          memset_0(v41, 0, 0x784u);
          result = readDrcCoefficientsUniDrc(a1, 0, v41);
          v25 = result;
          if ( (_DWORD)result )
            break;
          if ( v40 < 2 )
          {
            if ( !v23 )
              v23 = memcmp_0(v41, (const void *)(a2 + 1924LL * v40 + 1612), 0x784u) != 0;
            memcpy_0((void *)(a2 + 1924LL * v40 + 1612), v41, 0x784u);
          }
          if ( ++v40 >= *(unsigned __int8 *)(a2 + 11) )
            goto LABEL_40;
        }
      }
      else
      {
LABEL_40:
        v42 = *(unsigned __int8 *)(a2 + 14);
        v43 = 12;
        if ( v42 < 0xC )
          v43 = *(_BYTE *)(a2 + 14);
        v44 = 0;
        *(_BYTE *)(a2 + 16) = v43;
        if ( v42 )
        {
          while ( 1 )
          {
            v45 = *(_OWORD **)(a2 + 21088);
            memset_0(v45, 0, 0x334u);
            LOBYTE(v46) = *(_BYTE *)(a2 + 17);
            result = readDrcInstructionsUniDrc((_DWORD)a1, 0, a2, v46, (__int64)v45);
            v25 = result;
            if ( (_DWORD)result )
              break;
            if ( v44 < 12 )
            {
              if ( !v23 )
                v23 = memcmp_0(v45, (const void *)(a2 + 820LL * v44 + 5460), 0x334u) != 0;
              v47 = 6;
              v48 = (_OWORD *)(a2 + 820LL * v44 + 5460);
              do
              {
                *v48 = *v45;
                v48[1] = v45[1];
                v48[2] = v45[2];
                v48[3] = v45[3];
                v48[4] = v45[4];
                v48[5] = v45[5];
                v48[6] = v45[6];
                v49 = v45[7];
                v45 += 8;
                v48[7] = v49;
                v48 += 8;
                --v47;
              }
              while ( v47 );
              *v48 = *v45;
              v48[1] = v45[1];
              v48[2] = v45[2];
              *((_DWORD *)v48 + 12) = *((_DWORD *)v45 + 12);
            }
            if ( ++v44 >= *(unsigned __int8 *)(a2 + 14) )
              goto LABEL_51;
          }
        }
        else
        {
LABEL_51:
          v50 = CDKreadBits(a1, 1, v24);
          v22 = *(_BYTE *)(a2 + 21040) == v50;
          *(_BYTE *)(a2 + 21040) = v50;
          *(_BYTE *)(a2 + 21081) = v23 | !v22;
          if ( v50 != 1 )
            return v25;
          result = readUniDrcConfigExtension(a1, a2);
          v25 = result;
          if ( !(_DWORD)result )
            return v25;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800783f8  mov     [rsp+arg_10], rbx
0x1800783fd  push    rbp
0x1800783fe  push    rsi
0x1800783ff  push    rdi
0x180078400  push    r12
0x180078402  push    r13
0x180078404  push    r14
0x180078406  push    r15
0x180078408  sub     rsp, 50h
0x18007840c  mov     rax, cs:__security_cookie
0x180078413  xor     rax, rsp
0x180078416  mov     [rsp+88h+var_48], rax
0x18007841b  xor     eax, eax
0x18007841d  mov     rsi, rdx
0x180078420  mov     [rsp+88h+var_58], rax
0x180078425  mov     r14, rcx
0x180078428  mov     [rsp+88h+var_50], ax
0x18007842d  mov     [rsp+88h+var_4E], al
0x180078431  test    rdx, rdx
0x180078434  jnz     short loc_18007843E
0x180078436  lea     eax, [rdx-64h]
0x180078439  jmp     loc_18007889A
0x18007843e  mov     r15d, 1
0x180078444  mov     edx, r15d
0x180078447  call    CDKreadBits
0x18007844c  xor     ebx, ebx
0x18007844e  cmp     [rsi], al
0x180078450  mov     [rsi], al
0x180078452  setnz   bl
0x180078455  cmp     al, r15b
0x180078458  jnz     short loc_180078478
0x18007845a  lea     edx, [r15+11h]
0x18007845e  mov     rcx, r14
0x180078461  call    CDKreadBits
0x180078466  add     eax, 3E8h
0x18007846b  xor     ecx, ecx
0x18007846d  cmp     [rsi+4], eax
0x180078470  mov     [rsi+4], eax
0x180078473  setnz   cl
0x180078476  or      ebx, ecx
0x180078478  mov     edx, 7
0x18007847d  mov     rcx, r14
0x180078480  call    CDKreadBits
0x180078485  xor     ebp, ebp
0x180078487  mov     edx, r15d
0x18007848a  cmp     [rsi+8], al
0x18007848d  mov     rcx, r14
0x180078490  mov     [rsi+8], al
0x180078493  setnz   bpl
0x180078497  or      ebp, ebx
0x180078499  call    CDKreadBits
0x18007849e  mov     ebx, 3
0x1800784a3  cmp     eax, r15d
0x1800784a6  jnz     short loc_1800784C5
0x1800784a8  mov     edx, ebx
0x1800784aa  mov     rcx, r14
0x1800784ad  call    CDKreadBits
0x1800784b2  lea     edx, [rbx+1]
0x1800784b5  mov     rcx, r14
0x1800784b8  mov     r13d, eax
0x1800784bb  call    CDKreadBits
0x1800784c0  mov     r12d, eax
0x1800784c3  jmp     short loc_1800784CB
0x1800784c5  xor     r13d, r13d
0x1800784c8  xor     r12d, r12d
0x1800784cb  mov     edx, ebx
0x1800784cd  mov     rcx, r14
0x1800784d0  call    CDKreadBits
0x1800784d5  mov     bl, [rsi+0Bh]
0x1800784d8  mov     edi, eax
0x1800784da  mov     edx, 6
0x1800784df  mov     [rsi+0Bh], dil
0x1800784e3  mov     rcx, r14
0x1800784e6  call    CDKreadBits
0x1800784eb  xor     ecx, ecx
0x1800784ed  lea     rdx, [rsp+88h+var_58]
0x1800784f2  cmp     [rsi+0Eh], al
0x1800784f5  mov     [rsi+0Eh], al
0x1800784f8  setnz   cl
0x1800784fb  cmp     bl, dil
0x1800784fe  cmovnz  ebp, r15d
0x180078502  or      ebp, ecx
0x180078504  mov     rcx, r14
0x180078507  call    _readChannelLayout
0x18007850c  mov     ebx, eax
0x18007850e  test    eax, eax
0x180078510  jnz     loc_18007889A
0x180078516  test    ebp, ebp
0x180078518  jnz     short loc_180078548
0x18007851a  mov     rcx, [rsp+88h+var_58]
0x18007851f  sub     rcx, [rsi+11h]
0x180078523  jnz     short loc_18007853F
0x180078525  movzx   ecx, [rsp+88h+var_50]
0x18007852a  movzx   eax, word ptr [rsi+19h]
0x18007852e  sub     rcx, rax
0x180078531  jnz     short loc_18007853F
0x180078533  movzx   ecx, [rsp+88h+var_4E]
0x180078538  movzx   eax, byte ptr [rsi+1Bh]
0x18007853c  sub     rcx, rax
0x18007853f  xor     ebp, ebp
0x180078541  test    rcx, rcx
0x180078544  setnz   bpl
0x180078548  movzx   ecx, byte ptr [rsi+8]
0x18007854c  mov     eax, dword ptr [rsp+88h+var_58+7]
0x180078550  movsd   xmm0, [rsp+88h+var_58]
0x180078556  movsd   qword ptr [rsi+11h], xmm0
0x18007855b  mov     [rsi+18h], eax
0x18007855e  mov     eax, 6
0x180078563  cmp     ecx, eax
0x180078565  cmovb   eax, ecx
0x180078568  xor     r15d, r15d
0x18007856b  mov     [rsi+0Ah], al
0x18007856e  test    ecx, ecx
0x180078570  jz      loc_180078655
0x180078576  mov     rdi, [rsi+5260h]
0x18007857d  xor     edx, edx; Val
0x18007857f  mov     rcx, rdi; void *
0x180078582  mov     r8d, 108h; Size
0x180078588  call    memset_0
0x18007858d  mov     r9, rdi
0x180078590  lea     r8, [rsi+11h]
0x180078594  xor     edx, edx
0x180078596  mov     rcx, r14
0x180078599  call    _readDownmixInstructions
0x18007859e  mov     ebx, eax
0x1800785a0  test    eax, eax
0x1800785a2  jnz     loc_18007889A
0x1800785a8  cmp     r15d, 6
0x1800785ac  jge     loc_180078645
0x1800785b2  test    ebp, ebp
0x1800785b4  jnz     short loc_1800785DB
0x1800785b6  movsxd  rax, r15d
0x1800785b9  mov     r8d, 108h; Size
0x1800785bf  imul    rdx, rax, 108h
0x1800785c6  mov     rcx, rdi; Buf1
0x1800785c9  add     rdx, 1Ch
0x1800785cd  add     rdx, rsi; Buf2
0x1800785d0  call    memcmp_0
0x1800785d5  test    eax, eax
0x1800785d7  setnz   bpl
0x1800785db  movsxd  rax, r15d
0x1800785de  imul    rdx, rax, 108h
0x1800785e5  mov     eax, 2
0x1800785ea  add     rdx, 1Ch
0x1800785ee  add     rdx, rsi
0x1800785f1  lea     r8d, [rax+7Eh]
0x1800785f5  movups  xmm0, xmmword ptr [rdi]
0x1800785f8  movups  xmmword ptr [rdx], xmm0
0x1800785fb  movups  xmm1, xmmword ptr [rdi+10h]
0x1800785ff  movups  xmmword ptr [rdx+10h], xmm1
0x180078603  movups  xmm0, xmmword ptr [rdi+20h]
0x180078607  movups  xmmword ptr [rdx+20h], xmm0
0x18007860b  movups  xmm1, xmmword ptr [rdi+30h]
0x18007860f  movups  xmmword ptr [rdx+30h], xmm1
0x180078613  movups  xmm0, xmmword ptr [rdi+40h]
0x180078617  movups  xmmword ptr [rdx+40h], xmm0
0x18007861b  movups  xmm1, xmmword ptr [rdi+50h]
0x18007861f  movups  xmmword ptr [rdx+50h], xmm1
0x180078623  movups  xmm0, xmmword ptr [rdi+60h]
0x180078627  movups  xmmword ptr [rdx+60h], xmm0
0x18007862b  movups  xmm1, xmmword ptr [rdi+70h]
0x18007862f  add     rdi, r8
0x180078632  movups  xmmword ptr [rdx+70h], xmm1
0x180078636  add     rdx, r8
0x180078639  sub     rax, 1
0x18007863d  jnz     short loc_1800785F5
0x18007863f  mov     rax, [rdi]
0x180078642  mov     [rdx], rax
0x180078645  movzx   eax, byte ptr [rsi+8]
0x180078649  inc     r15d
0x18007864c  cmp     r15d, eax
0x18007864f  jl      loc_180078576
0x180078655  xor     edi, edi
0x180078657  test    r13d, r13d
0x18007865a  jle     short loc_18007867D
0x18007865c  mov     edx, 4
0x180078661  mov     rcx, r14
0x180078664  call    CDKpushFor
0x180078669  mov     edx, 7
0x18007866e  mov     rcx, r14
0x180078671  call    CDKpushFor
0x180078676  inc     edi
0x180078678  cmp     edi, r13d
0x18007867b  jl      short loc_18007865C
0x18007867d  xor     edi, edi
0x18007867f  test    r12d, r12d
0x180078682  jle     short loc_180078693
0x180078684  mov     rcx, r14
0x180078687  call    _skipDrcInstructionsBasic
0x18007868c  inc     edi
0x18007868e  cmp     edi, r12d
0x180078691  jl      short loc_180078684
0x180078693  movzx   ecx, byte ptr [rsi+0Bh]
0x180078697  mov     eax, 2
0x18007869c  cmp     ecx, eax
0x18007869e  cmovb   eax, ecx
0x1800786a1  xor     edi, edi
0x1800786a3  mov     [rsi+0Dh], al
0x1800786a6  test    ecx, ecx
0x1800786a8  jz      loc_18007873A
0x1800786ae  mov     r12d, 784h
0x1800786b4  mov     r15, [rsi+5260h]
0x1800786bb  mov     r8, r12; Size
0x1800786be  mov     rcx, r15; void *
0x1800786c1  xor     edx, edx; Val
0x1800786c3  call    memset_0
0x1800786c8  mov     r8, r15
0x1800786cb  xor     edx, edx
0x1800786cd  mov     rcx, r14
0x1800786d0  call    _readDrcCoefficientsUniDrc
0x1800786d5  mov     ebx, eax
0x1800786d7  test    eax, eax
0x1800786d9  jnz     loc_18007889A
0x1800786df  cmp     edi, 2
0x1800786e2  jge     short loc_18007872C
0x1800786e4  test    ebp, ebp
0x1800786e6  jnz     short loc_18007870D
0x1800786e8  movsxd  rax, edi
0x1800786eb  mov     r8, r12; Size
0x1800786ee  imul    rdx, rax, 784h
0x1800786f5  mov     rcx, r15; Buf1
0x1800786f8  add     rdx, 64Ch
0x1800786ff  add     rdx, rsi; Buf2
0x180078702  call    memcmp_0
0x180078707  test    eax, eax
0x180078709  setnz   bpl
0x18007870d  movsxd  rax, edi
0x180078710  mov     rdx, r15; Src
0x180078713  imul    rcx, rax, 784h
0x18007871a  mov     r8, r12; Size
0x18007871d  add     rcx, 64Ch
0x180078724  add     rcx, rsi; void *
0x180078727  call    memcpy_0
0x18007872c  movzx   eax, byte ptr [rsi+0Bh]
0x180078730  inc     edi
0x180078732  cmp     edi, eax
0x180078734  jl      loc_1800786B4
0x18007873a  movzx   ecx, byte ptr [rsi+0Eh]
0x18007873e  mov     eax, 0Ch
0x180078743  cmp     ecx, eax
0x180078745  cmovb   eax, ecx
0x180078748  xor     r15d, r15d
0x18007874b  mov     [rsi+10h], al
0x18007874e  test    ecx, ecx
0x180078750  jz      loc_180078858
0x180078756  mov     r12d, 334h
0x18007875c  mov     r13d, 80h
0x180078762  mov     rdi, [rsi+5260h]
0x180078769  mov     r8, r12; Size
0x18007876c  mov     rcx, rdi; void *
0x18007876f  xor     edx, edx; Val
0x180078771  call    memset_0
0x180078776  mov     r9b, [rsi+11h]
0x18007877a  mov     r8, rsi
0x18007877d  xor     edx, edx
0x18007877f  mov     [rsp+88h+var_68], rdi
0x180078784  mov     rcx, r14
0x180078787  call    _readDrcInstructionsUniDrc
0x18007878c  mov     ebx, eax
0x18007878e  test    eax, eax
0x180078790  jnz     loc_18007889A
0x180078796  cmp     r15d, 0Ch
0x18007879a  jge     loc_180078848
0x1800787a0  test    ebp, ebp
0x1800787a2  jnz     short loc_1800787C9
0x1800787a4  movsxd  rax, r15d
0x1800787a7  mov     r8, r12; Size
0x1800787aa  imul    rdx, rax, 334h
0x1800787b1  mov     rcx, rdi; Buf1
0x1800787b4  add     rdx, 1554h
0x1800787bb  add     rdx, rsi; Buf2
0x1800787be  call    memcmp_0
0x1800787c3  test    eax, eax
0x1800787c5  setnz   bpl
0x1800787c9  movsxd  rax, r15d
0x1800787cc  imul    rdx, rax, 334h
0x1800787d3  mov     eax, 6
0x1800787d8  add     rdx, 1554h
0x1800787df  add     rdx, rsi
0x1800787e2  movups  xmm0, xmmword ptr [rdi]
0x1800787e5  movups  xmmword ptr [rdx], xmm0
0x1800787e8  movups  xmm1, xmmword ptr [rdi+10h]
0x1800787ec  movups  xmmword ptr [rdx+10h], xmm1
0x1800787f0  movups  xmm0, xmmword ptr [rdi+20h]
0x1800787f4  movups  xmmword ptr [rdx+20h], xmm0
0x1800787f8  movups  xmm1, xmmword ptr [rdi+30h]
0x1800787fc  movups  xmmword ptr [rdx+30h], xmm1
0x180078800  movups  xmm0, xmmword ptr [rdi+40h]
0x180078804  movups  xmmword ptr [rdx+40h], xmm0
0x180078808  movups  xmm1, xmmword ptr [rdi+50h]
0x18007880c  movups  xmmword ptr [rdx+50h], xmm1
0x180078810  movups  xmm0, xmmword ptr [rdi+60h]
0x180078814  movups  xmmword ptr [rdx+60h], xmm0
0x180078818  movups  xmm1, xmmword ptr [rdi+70h]
0x18007881c  add     rdi, r13
0x18007881f  movups  xmmword ptr [rdx+70h], xmm1
0x180078823  add     rdx, r13
0x180078826  sub     rax, 1
0x18007882a  jnz     short loc_1800787E2
0x18007882c  movups  xmm0, xmmword ptr [rdi]
  ... truncated ...
```
