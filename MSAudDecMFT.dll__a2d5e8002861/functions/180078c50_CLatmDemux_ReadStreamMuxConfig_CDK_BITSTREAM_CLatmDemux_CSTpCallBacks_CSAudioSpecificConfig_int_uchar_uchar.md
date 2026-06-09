# CLatmDemux_ReadStreamMuxConfig(CDK_BITSTREAM *,CLatmDemux *,CSTpCallBacks *,CSAudioSpecificConfig *,int *,uchar,uchar)

- ea: `0x180078c50`
- end: `0x180079334`
- name: `?CLatmDemux_ReadStreamMuxConfig@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCDK_BITSTREAM@@PEAUCLatmDemux@@PEAUCSTpCallBacks@@PEAUCSAudioSpecificConfig@@PEAHEE@Z`
- size: `1764`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180011b10`
- `0x1800789bc`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180011da8`
- `0x18004d320`
- `0x18004dd14`
- `0x1800788c8`
- `0x180078c50`
- `0x180096060`
- `0x18009606c`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall CLatmDemux_ReadStreamMuxConfig(
        __int128 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _DWORD *a5,
        char a6,
        char a7)
{
  _DWORD *v7; // r12
  __int64 v9; // r15
  __int64 v10; // r13
  char v12; // al
  __int64 v13; // r8
  char v14; // al
  __int64 v15; // r8
  __int64 v16; // r8
  unsigned __int8 v17; // al
  __int64 v18; // r8
  unsigned int v19; // edi
  char v20; // al
  __int64 v22; // rbx
  __int64 v23; // r13
  unsigned int v24; // eax
  unsigned __int8 v25; // al
  __int64 v26; // rcx
  int v27; // edx
  unsigned int i; // r12d
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 v31; // r8
  char v32; // r15
  __int64 v33; // rdi
  __int64 v34; // rbx
  unsigned int v35; // edi
  size_t v36; // r8
  int Value; // ebx
  bool v38; // zf
  __int128 v39; // xmm1
  __int64 v40; // rcx
  unsigned int v41; // eax
  int v42; // ecx
  int v43; // eax
  int v44; // ecx
  int v45; // eax
  __int64 v46; // rcx
  char v47; // cl
  unsigned int v48; // r15d
  __int64 v49; // rbx
  size_t v50; // r8
  __int64 v51; // r15
  int v52; // eax
  __int64 v53; // r8
  __int64 v54; // r15
  int v55; // ecx
  char v56; // al
  __int64 v57; // r8
  unsigned int v58; // eax
  int v59; // ebx
  __int64 v60; // r8
  char v61; // al
  __int64 v62; // r8
  __int64 v63; // r8
  __int64 v64; // r14
  unsigned int j; // ebx
  __int64 v66; // rdx
  int v67; // eax
  int v68; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+28h] [rbp-D8h]
  _BYTE v70[8]; // [rsp+40h] [rbp-C0h]
  __int64 v71; // [rsp+48h] [rbp-B8h]
  int v72; // [rsp+50h] [rbp-B0h]
  int v73; // [rsp+54h] [rbp-ACh]
  size_t Size; // [rsp+58h] [rbp-A8h]
  __int64 v75; // [rsp+60h] [rbp-A0h]
  __int64 v76; // [rsp+68h] [rbp-98h]
  __int64 v77; // [rsp+70h] [rbp-90h]
  __int64 v78; // [rsp+78h] [rbp-88h]
  _DWORD *v79; // [rsp+80h] [rbp-80h]
  __int128 v80; // [rsp+88h] [rbp-78h] BYREF
  __int128 v81; // [rsp+98h] [rbp-68h]
  __int128 v82; // [rsp+A8h] [rbp-58h]
  _BYTE Buf1[512]; // [rsp+C0h] [rbp-40h] BYREF

  v7 = a5;
  *(_BYTE *)(a2 + 38) = 0;
  v71 = a4;
  v9 = a4;
  v76 = a3;
  v10 = a3;
  v79 = a5;
  v70[0] = 0;
  v12 = CDKreadBits(a1, 1, a3);
  *(_BYTE *)(a2 + 29) = v12;
  if ( v12 )
  {
    v14 = CDKreadBits(a1, 1, v13);
    *(_BYTE *)(a2 + 30) = v14;
    if ( v14 )
    {
      v19 = 1026;
      goto LABEL_77;
    }
  }
  else
  {
    *(_BYTE *)(a2 + 30) = 0;
  }
  if ( *(_BYTE *)(a2 + 29) == 1 )
    *(_DWORD *)(a2 + 16) = CLatmDemux_GetValue(a1);
  *(_BYTE *)(a2 + 31) = CDKreadBits(a1, 1, v13);
  *(_BYTE *)(a2 + 32) = CDKreadBits(a1, 6, v15) + 1;
  v17 = CDKreadBits(a1, 4, v16) + 1;
  *(_BYTE *)(a2 + 33) = v17;
  if ( v17 > 1u )
  {
LABEL_7:
    v19 = 1026;
    goto LABEL_8;
  }
  v19 = 0;
  v22 = v9 + 1756;
  v75 = v9 + 1756;
  v23 = 0;
  v73 = 0;
LABEL_11:
  v24 = *(unsigned __int8 *)(a2 + 33);
  v72 = v23;
  if ( (unsigned int)v23 < v24 )
  {
    v25 = CDKreadBits(a1, 3, v18) + 1;
    v26 = (unsigned int)v23;
    *(_BYTE *)(v23 + a2 + 34) = v25;
    if ( v25 > 1u )
      goto LABEL_7;
    v27 = v73;
    for ( i = 0; ; ++i )
    {
      if ( i >= *(unsigned __int8 *)(v26 + a2 + 34) )
      {
        v23 = (unsigned int)(v23 + 1);
        goto LABEL_11;
      }
      if ( ((v29 = 16 * (v26 + i),
             v78 = v29,
             *(_DWORD *)(v29 + a2 + 8) = v27,
             *(_DWORD *)(v29 + a2 + 12) = 0,
             (_DWORD)v23)
         || i)
        && (unsigned int)CDKreadBits(a1, 1, v18) )
      {
        if ( !i )
          goto LABEL_66;
        v30 = i + (unsigned int)v23;
        memcpy_0((void *)(v9 + 1756 * v30), (const void *)(v9 + 1756LL * (i + (unsigned int)v23 - 1)), 0x6DCu);
      }
      else
      {
        v32 = *(_BYTE *)(a2 + 39);
        v33 = v71;
        LODWORD(Size) = 0;
        if ( !v32 )
        {
          v34 = 1756LL * (i + (unsigned int)v23);
          if ( *(_DWORD *)(v34 + v71 + 1200) == 42 )
          {
            v35 = ((unsigned int)*(unsigned __int16 *)(v34 + v71 + 728) + 7) >> 3;
            LODWORD(Size) = v35;
            if ( v35 > 0x200 )
              goto LABEL_66;
            memset_0(Buf1, 0, sizeof(Buf1));
            v36 = v35;
            v33 = v71;
            memcpy_0(Buf1, (const void *)(v34 + v71 + 215), v36);
          }
          v22 = v33 + 1756;
        }
        if ( *(_BYTE *)(a2 + 29) == 1 )
        {
          v80 = 0;
          v81 = 0;
          v82 = 0;
          Value = CLatmDemux_GetValue(a1);
          if ( Value < 0 )
            goto LABEL_66;
          CDKsyncCache_0((int *)a1);
          if ( Value > *((_DWORD *)a1 + 2) )
            goto LABEL_66;
          CDKsyncCache_0((int *)a1);
          v38 = *(_BYTE *)(a2 + 39) == 0;
          v39 = a1[1];
          v80 = *a1;
          LOBYTE(v69) = a7;
          v82 = a1[2];
          DWORD2(v80) = Value;
          v81 = v39;
          LOBYTE(v68) = a6;
          if ( v38 )
            v40 = v75;
          else
            v40 = v33 + 1756LL * (i + (unsigned int)v23);
          v19 = AudioSpecificConfig_Parse(v40, &v80, 1, v76, v68, v69, 0);
          if ( v19 )
            goto LABEL_8;
          CDKsyncCache_0((int *)&v80);
          if ( SDWORD2(v80) < 0 )
            goto LABEL_66;
          v41 = *((_DWORD *)a1 + 1);
          if ( v41 <= Value || *((_DWORD *)a1 + 10) )
          {
            CDKsyncCache_0((int *)a1);
            v42 = *((_DWORD *)a1 + 2);
            v43 = v42 + Value;
            v44 = v42 - Value;
            if ( *((_BYTE *)a1 + 40) )
              v44 = v43;
            v45 = *((_DWORD *)a1 + 9);
            *((_DWORD *)a1 + 2) = v44;
            *((_DWORD *)a1 + 5) = (v45 - 1) & (Value + *((_DWORD *)a1 + 5));
          }
          else
          {
            *((_DWORD *)a1 + 1) = v41 - Value;
          }
        }
        else
        {
          LOBYTE(v69) = a7;
          LOBYTE(v68) = a6;
          if ( v32 )
            v46 = v33 + 1756LL * (i + (unsigned int)v23);
          else
            v46 = v22;
          v19 = AudioSpecificConfig_Parse(v46, a1, 0, v76, v68, v69, 0);
          if ( v19 )
            goto LABEL_8;
        }
        v47 = *(_BYTE *)(a2 + 39);
        v30 = i + (unsigned int)v23;
        v77 = v30;
        v70[v30] = v47 != 0;
        if ( !v47 )
        {
          v23 = 1756 * v30;
          if ( *(_DWORD *)(v75 + 1756 * v30 + 1200) != 42 )
            goto LABEL_53;
          v48 = ((unsigned int)*(unsigned __int16 *)(v75 + 728) + 7) >> 3;
          if ( v48 > 0x200 )
            goto LABEL_66;
          if ( v48 == (_DWORD)Size && !memcmp_0(Buf1, (const void *)(v75 + 215), (unsigned int)Size) )
          {
            v51 = v75;
          }
          else
          {
            v49 = v71;
            memset_0((void *)(v23 + v71 + 215), 0, 0x200u);
            v50 = v48;
            v51 = v75;
            memcpy_0((void *)(v23 + v49 + 215), (const void *)(v75 + 215), v50);
            *(_WORD *)(v49 + v23 + 728) = *(_WORD *)(v51 + 728);
            v30 = v77;
            *(_BYTE *)(a2 + 38) = 1;
          }
          if ( *(_DWORD *)(v51 + v23 + 8) )
          {
            v38 = *(_BYTE *)(v51 + v23 + 31) == 0;
            LODWORD(v23) = v72;
            if ( !v38 )
              *(_BYTE *)(a2 + 40) = 1;
          }
          else
          {
LABEL_53:
            LODWORD(v23) = v72;
          }
        }
      }
      v52 = CDKreadBits(a1, 3, v31);
      v54 = v78;
      *(_DWORD *)(v78 + a2) = v52;
      if ( v52 )
        break;
      *(_DWORD *)(v54 + a2 + 4) = CDKreadBits(a1, 8, v53);
      if ( *(_BYTE *)(a2 + 31) )
        goto LABEL_57;
      v9 = v71;
      if ( i )
      {
        v55 = *(_DWORD *)(1756 * v30 + v71 + 1200);
        if ( (v55 == 6 || v55 == 20)
          && ((*(_DWORD *)(1756LL * (i + (_DWORD)v23 - 1) + v71 + 1200) - 8) & 0xFFFFFFEF) == 0 )
        {
          CDKreadBits(a1, 6, v18);
        }
      }
LABEL_58:
      v22 = v9 + 1756;
      v27 = v73 + 1;
      v26 = (unsigned int)v23;
      ++v73;
    }
    if ( v52 != 1 )
      goto LABEL_66;
    *(_DWORD *)(v54 + a2 + 12) = CDKreadBits(a1, 9, v53);
LABEL_57:
    v9 = v71;
    goto LABEL_58;
  }
  v56 = CDKreadBits(a1, 1, v18);
  *(_BYTE *)(a2 + 35) = v56;
  *(_DWORD *)(a2 + 20) = 0;
  if ( v56 )
  {
    if ( *(_BYTE *)(a2 + 29) == 1 )
    {
      v58 = CLatmDemux_GetValue(a1);
      *(_DWORD *)(a2 + 20) = v58;
    }
    else
    {
      v58 = 0;
      do
      {
        *(_DWORD *)(a2 + 20) = v58 << 8;
        v59 = CDKreadBits(a1, 1, v57);
        v58 = *(_DWORD *)(a2 + 20) + CDKreadBits(a1, 8, v60);
        *(_DWORD *)(a2 + 20) = v58;
      }
      while ( v59 );
    }
    if ( *(_DWORD *)(a2 + 24) < v58 >> 3 )
    {
LABEL_66:
      v19 = 1025;
      goto LABEL_8;
    }
  }
  v61 = CDKreadBits(a1, 1, v57);
  *(_BYTE *)(a2 + 36) = v61;
  if ( v61 )
    CDKreadBits(a1, 8, v62);
  v7 = v79;
  v10 = v76;
LABEL_77:
  CDKsyncCache_0((int *)a1);
  if ( *((int *)a1 + 2) < 0 )
  {
    v19 = 257;
    goto LABEL_8;
  }
  if ( v19 )
  {
LABEL_8:
    v20 = *(_BYTE *)(a2 + 39);
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 16) = 0;
    *(_OWORD *)(a2 + 28) = 0;
    *(_BYTE *)(a2 + 39) = v20;
  }
  else
  {
    v64 = 0;
LABEL_81:
    if ( (unsigned int)v64 < *(unsigned __int8 *)(a2 + 33) )
    {
      for ( j = 0; ; ++j )
      {
        if ( j >= *(unsigned __int8 *)(v64 + a2 + 34) )
        {
          v64 = (unsigned int)(v64 + 1);
          goto LABEL_81;
        }
        if ( !v70[j + (unsigned int)v64] )
          goto LABEL_89;
        v66 = v71 + 1756LL * (j + (unsigned int)v64);
        LOBYTE(v63) = *(_BYTE *)(v66 + 1234);
        v67 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))v10)(
                *(_QWORD *)(v10 + 8),
                v66,
                v63,
                v66 + 1235);
        if ( v67 == 515 )
        {
          *v7 = 0;
          v19 = 515;
          goto LABEL_8;
        }
        if ( v67 )
        {
          *v7 = 0;
          if ( !j )
          {
            v19 = 258;
            goto LABEL_8;
          }
        }
        else
        {
LABEL_89:
          *v7 = 1;
        }
      }
    }
    if ( a6 == 2 )
      *(_BYTE *)(a2 + 39) = 0;
  }
  return v19;
}

```

## disassembly

```asm
0x180078c50  push    rbp
0x180078c52  push    rbx
0x180078c53  push    rsi
0x180078c54  push    rdi
0x180078c55  push    r12
0x180078c57  push    r13
0x180078c59  push    r14
0x180078c5b  push    r15
0x180078c5d  lea     rbp, [rsp-1D8h]
0x180078c65  sub     rsp, 2D8h
0x180078c6c  mov     rax, cs:__security_cookie
0x180078c73  xor     rax, rsp
0x180078c76  mov     [rbp+210h+var_50], rax
0x180078c7d  mov     r12, [rbp+210h+arg_20]
0x180078c84  mov     rsi, rdx
0x180078c87  mov     byte ptr [rdx+26h], 0
0x180078c8b  mov     ebx, 1
0x180078c90  mov     edx, ebx
0x180078c92  mov     [rsp+310h+var_2C8], r9
0x180078c97  mov     r15, r9
0x180078c9a  mov     [rsp+310h+var_2A8], r8
0x180078c9f  mov     r13, r8
0x180078ca2  mov     [rbp+210h+var_290], r12
0x180078ca6  mov     r14, rcx
0x180078ca9  mov     [rsp+310h+var_2D0], 0
0x180078cae  call    CDKreadBits
0x180078cb3  mov     [rsi+1Dh], al
0x180078cb6  test    al, al
0x180078cb8  jnz     short loc_180078CBF
0x180078cba  mov     [rsi+1Eh], al
0x180078cbd  jmp     short loc_180078CD4
0x180078cbf  mov     edx, ebx
0x180078cc1  mov     rcx, r14
0x180078cc4  call    CDKreadBits
0x180078cc9  mov     [rsi+1Eh], al
0x180078ccc  test    al, al
0x180078cce  jnz     loc_180079263
0x180078cd4  cmp     [rsi+1Dh], bl
0x180078cd7  jnz     short loc_180078CE4
0x180078cd9  mov     rcx, r14
0x180078cdc  call    CLatmDemux_GetValue
0x180078ce1  mov     [rsi+10h], eax
0x180078ce4  mov     edx, ebx
0x180078ce6  mov     rcx, r14
0x180078ce9  call    CDKreadBits
0x180078cee  mov     edx, 6
0x180078cf3  mov     [rsi+1Fh], al
0x180078cf6  mov     rcx, r14
0x180078cf9  call    CDKreadBits
0x180078cfe  add     al, bl
0x180078d00  mov     edx, 4
0x180078d05  mov     rcx, r14
0x180078d08  mov     [rsi+20h], al
0x180078d0b  call    CDKreadBits
0x180078d10  add     al, bl
0x180078d12  mov     [rsi+21h], al
0x180078d15  cmp     al, bl
0x180078d17  jbe     short loc_180078D58
0x180078d19  mov     edi, 402h
0x180078d1e  mov     al, [rsi+27h]
0x180078d21  xorps   xmm0, xmm0
0x180078d24  movups  xmmword ptr [rsi], xmm0
0x180078d27  movups  xmmword ptr [rsi+10h], xmm0
0x180078d2b  movups  xmmword ptr [rsi+1Ch], xmm0
0x180078d2f  mov     [rsi+27h], al
0x180078d32  mov     eax, edi
0x180078d34  mov     rcx, [rbp+210h+var_50]
0x180078d3b  xor     rcx, rsp; StackCookie
0x180078d3e  call    __security_check_cookie
0x180078d43  add     rsp, 2D8h
0x180078d4a  pop     r15
0x180078d4c  pop     r14
0x180078d4e  pop     r13
0x180078d50  pop     r12
0x180078d52  pop     rdi
0x180078d53  pop     rsi
0x180078d54  pop     rbx
0x180078d55  pop     rbp
0x180078d56  retn
0x180078d58  xor     edi, edi
0x180078d5a  lea     rbx, [r15+6DCh]
0x180078d61  mov     [rsp+310h+var_2B0], rbx
0x180078d66  xor     r13d, r13d
0x180078d69  mov     [rsp+310h+var_2BC], edi
0x180078d6d  movzx   eax, byte ptr [rsi+21h]
0x180078d71  mov     rcx, r14
0x180078d74  mov     [rsp+310h+var_2C0], r13d
0x180078d79  cmp     r13d, eax
0x180078d7c  jnb     loc_1800791D6
0x180078d82  mov     edx, 3
0x180078d87  call    CDKreadBits
0x180078d8c  inc     al
0x180078d8e  mov     ecx, r13d
0x180078d91  mov     [r13+rsi+22h], al
0x180078d96  cmp     al, 1
0x180078d98  ja      loc_180078D19
0x180078d9e  mov     edx, [rsp+310h+var_2BC]
0x180078da2  xor     r12d, r12d
0x180078da5  movzx   eax, byte ptr [rcx+rsi+22h]
0x180078daa  cmp     r12d, eax
0x180078dad  jnb     loc_1800791B7
0x180078db3  mov     eax, r12d
0x180078db6  add     rax, rcx
0x180078db9  shl     rax, 4
0x180078dbd  mov     [rsp+310h+var_298], rax
0x180078dc2  mov     [rax+rsi+8], edx
0x180078dc6  mov     dword ptr [rax+rsi+0Ch], 0
0x180078dce  test    r13d, r13d
0x180078dd1  jnz     short loc_180078DD8
0x180078dd3  test    r12d, r12d
0x180078dd6  jz      short loc_180078E1F
0x180078dd8  mov     edx, 1
0x180078ddd  mov     rcx, r14
0x180078de0  call    CDKreadBits
0x180078de5  test    eax, eax
0x180078de7  jz      short loc_180078E1F
0x180078de9  test    r12d, r12d
0x180078dec  jz      loc_1800791CC
0x180078df2  lea     eax, [r12+r13]
0x180078df6  mov     r8d, 6DCh; Size
0x180078dfc  lea     ecx, [rax-1]
0x180078dff  mov     ebx, eax
0x180078e01  imul    rdx, rcx, 6DCh
0x180078e08  imul    rcx, rbx, 6DCh
0x180078e0f  add     rdx, r15; Src
0x180078e12  add     rcx, r15; void *
0x180078e15  call    memcpy_0
0x180078e1a  jmp     loc_1800790F5
0x180078e1f  mov     r15b, [rsi+27h]
0x180078e23  mov     rdi, [rsp+310h+var_2C8]
0x180078e28  mov     dword ptr [rsp+310h+Size], 0
0x180078e30  test    r15b, r15b
0x180078e33  jnz     short loc_180078E99
0x180078e35  lea     ecx, [r12+r13]
0x180078e39  imul    rbx, rcx, 6DCh
0x180078e40  cmp     dword ptr [rbx+rdi+4B0h], 2Ah ; '*'
0x180078e48  jnz     short loc_180078E92
0x180078e4a  movzx   edi, word ptr [rbx+rdi+2D8h]
0x180078e52  mov     eax, 200h
0x180078e57  add     edi, 7
0x180078e5a  shr     edi, 3
0x180078e5d  mov     dword ptr [rsp+310h+Size], edi
0x180078e61  cmp     edi, eax
0x180078e63  ja      loc_1800791CC
0x180078e69  mov     r8d, eax; Size
0x180078e6c  lea     rcx, [rbp+210h+Buf1]; void *
0x180078e70  xor     edx, edx; Val
0x180078e72  call    memset_0
0x180078e77  mov     r8d, edi; Size
0x180078e7a  lea     rcx, [rbp+210h+Buf1]; void *
0x180078e7e  mov     rdi, [rsp+310h+var_2C8]
0x180078e83  lea     rdx, [rdi+0D7h]
0x180078e8a  add     rdx, rbx; Src
0x180078e8d  call    memcpy_0
0x180078e92  lea     rbx, [rdi+6DCh]
0x180078e99  cmp     byte ptr [rsi+1Dh], 1
0x180078e9d  jnz     loc_180078FAB
0x180078ea3  xorps   xmm0, xmm0
0x180078ea6  mov     rcx, r14
0x180078ea9  movups  [rbp+210h+var_288], xmm0
0x180078ead  movups  [rbp+210h+var_278], xmm0
0x180078eb1  movups  [rbp+210h+var_268], xmm0
0x180078eb5  call    CLatmDemux_GetValue
0x180078eba  mov     ebx, eax
0x180078ebc  test    eax, eax
0x180078ebe  js      loc_1800791CC
0x180078ec4  mov     rcx, r14
0x180078ec7  call    CDKsyncCache_0
0x180078ecc  cmp     ebx, [r14+8]
0x180078ed0  jg      loc_1800791CC
0x180078ed6  mov     rcx, r14
0x180078ed9  call    CDKsyncCache_0
0x180078ede  cmp     byte ptr [rsi+27h], 0
0x180078ee2  lea     rdx, [rbp+210h+var_288]
0x180078ee6  movups  xmm0, xmmword ptr [r14]
0x180078eea  mov     al, [rbp+210h+arg_30]
0x180078ef0  mov     r8d, 1
0x180078ef6  movups  xmm1, xmmword ptr [r14+10h]
0x180078efb  mov     r9, [rsp+310h+var_2A8]
0x180078f00  movups  [rbp+210h+var_288], xmm0
0x180078f04  mov     [rsp+310h+var_2E0], 0
0x180078f0c  movups  xmm0, xmmword ptr [r14+20h]
0x180078f11  mov     [rsp+310h+var_2E8], al
0x180078f15  mov     al, [rbp+210h+arg_28]
0x180078f1b  movups  [rbp+210h+var_268], xmm0
0x180078f1f  mov     dword ptr [rbp+210h+var_288+8], ebx
0x180078f22  movups  [rbp+210h+var_278], xmm1
0x180078f26  mov     [rsp+310h+var_2F0], al
0x180078f2a  jz      short loc_180078F3C
0x180078f2c  lea     ecx, [r12+r13]
0x180078f30  imul    rcx, 6DCh
0x180078f37  add     rcx, rdi
0x180078f3a  jmp     short loc_180078F41
0x180078f3c  mov     rcx, [rsp+310h+var_2B0]
0x180078f41  call    ?AudioSpecificConfig_Parse@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCSAudioSpecificConfig@@PEAUCDK_BITSTREAM@@HPEAUCSTpCallBacks@@EEW4AUDIO_OBJECT_TYPE@@@Z; AudioSpecificConfig_Parse(CSAudioSpecificConfig *,CDK_BITSTREAM *,int,CSTpCallBacks *,uchar,uchar,AUDIO_OBJECT_TYPE)
0x180078f46  mov     edi, eax
0x180078f48  test    eax, eax
0x180078f4a  jnz     loc_180078D1E
0x180078f50  lea     rcx, [rbp+210h+var_288]
0x180078f54  call    CDKsyncCache_0
0x180078f59  cmp     dword ptr [rbp+210h+var_288+8], 0
0x180078f5d  jl      loc_1800791CC
0x180078f63  mov     eax, [r14+4]
0x180078f67  cmp     eax, ebx
0x180078f69  jbe     short loc_180078F7A
0x180078f6b  cmp     dword ptr [r14+28h], 0
0x180078f70  jnz     short loc_180078F7A
0x180078f72  sub     eax, ebx
0x180078f74  mov     [r14+4], eax
0x180078f78  jmp     short loc_180078FF9
0x180078f7a  mov     rcx, r14
0x180078f7d  call    CDKsyncCache_0
0x180078f82  mov     ecx, [r14+8]
0x180078f86  lea     eax, [rcx+rbx]
0x180078f89  sub     ecx, ebx
0x180078f8b  cmp     byte ptr [r14+28h], 0
0x180078f90  cmovnz  ecx, eax
0x180078f93  mov     eax, [r14+24h]
0x180078f97  mov     [r14+8], ecx
0x180078f9b  dec     eax
0x180078f9d  mov     ecx, [r14+14h]
0x180078fa1  add     ecx, ebx
0x180078fa3  and     ecx, eax
0x180078fa5  mov     [r14+14h], ecx
0x180078fa9  jmp     short loc_180078FF9
0x180078fab  mov     al, [rbp+210h+arg_30]
0x180078fb1  xor     r8d, r8d
0x180078fb4  mov     r9, [rsp+310h+var_2A8]
0x180078fb9  mov     rdx, r14
0x180078fbc  mov     [rsp+310h+var_2E0], 0
0x180078fc4  mov     [rsp+310h+var_2E8], al
0x180078fc8  mov     al, [rbp+210h+arg_28]
0x180078fce  mov     [rsp+310h+var_2F0], al
0x180078fd2  test    r15b, r15b
0x180078fd5  jz      short loc_180078FE7
0x180078fd7  lea     ecx, [r12+r13]
0x180078fdb  imul    rcx, 6DCh
0x180078fe2  add     rcx, rdi
0x180078fe5  jmp     short loc_180078FEA
0x180078fe7  mov     rcx, rbx
0x180078fea  call    ?AudioSpecificConfig_Parse@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCSAudioSpecificConfig@@PEAUCDK_BITSTREAM@@HPEAUCSTpCallBacks@@EEW4AUDIO_OBJECT_TYPE@@@Z; AudioSpecificConfig_Parse(CSAudioSpecificConfig *,CDK_BITSTREAM *,int,CSTpCallBacks *,uchar,uchar,AUDIO_OBJECT_TYPE)
0x180078fef  mov     edi, eax
0x180078ff1  test    eax, eax
0x180078ff3  jnz     loc_180078D1E
0x180078ff9  mov     cl, [rsi+27h]
0x180078ffc  lea     ebx, [r12+r13]
0x180079000  test    cl, cl
0x180079002  mov     [rsp+310h+var_2A0], rbx
0x180079007  setnz   al
0x18007900a  mov     [rsp+rbx+310h+var_2D0], al
0x18007900e  test    cl, cl
0x180079010  jnz     loc_1800790F5
0x180079016  mov     rax, [rsp+310h+var_2B0]
0x18007901b  imul    r13, rbx, 6DCh
0x180079022  cmp     dword ptr [rax+r13+4B0h], 2Ah ; '*'
0x18007902b  jnz     loc_1800790F0
0x180079031  movzx   r15d, word ptr [rax+2D8h]
0x180079039  mov     edx, 200h
0x18007903e  add     r15d, 7
0x180079042  shr     r15d, 3
0x180079046  cmp     r15d, edx
0x180079049  ja      loc_1800791CC
0x18007904f  lea     rcx, [rax+0D7h]
0x180079056  mov     eax, dword ptr [rsp+310h+Size]
0x18007905a  cmp     r15d, eax
0x18007905d  jz      short loc_1800790B5
0x18007905f  mov     r8d, edx; Size
0x180079062  mov     rbx, [rsp+310h+var_2C8]
0x180079067  xor     edx, edx; Val
0x180079069  lea     rcx, [rbx+0D7h]
0x180079070  add     rcx, r13; void *
0x180079073  call    memset_0
0x180079078  mov     r8d, r15d; Size
0x18007907b  lea     rcx, [rbx+0D7h]
0x180079082  mov     r15, [rsp+310h+var_2B0]
0x180079087  add     rcx, r13; void *
0x18007908a  lea     rdx, [r15+0D7h]; Src
0x180079091  call    memcpy_0
0x180079096  movzx   eax, word ptr [r15+2D8h]
0x18007909e  mov     rcx, rbx
0x1800790a1  mov     [rbx+r13+2D8h], ax
0x1800790aa  mov     rbx, [rsp+310h+var_2A0]
0x1800790af  mov     byte ptr [rsi+26h], 1
0x1800790b3  jmp     short loc_1800790D5
0x1800790b5  mov     rdx, rcx; Buf2
0x1800790b8  mov     r8, rax; Size
0x1800790bb  lea     rcx, [rbp+210h+Buf1]; Buf1
0x1800790bf  call    memcmp_0
0x1800790c4  test    eax, eax
0x1800790c6  jz      short loc_1800790D0
0x1800790c8  mov     r8d, 200h
0x1800790ce  jmp     short loc_180079062
0x1800790d0  mov     r15, [rsp+310h+var_2B0]
0x1800790d5  cmp     dword ptr [r15+r13+8], 0
0x1800790db  jz      short loc_1800790F0
0x1800790dd  cmp     byte ptr [r15+r13+1Fh], 0
0x1800790e3  mov     r13d, [rsp+310h+var_2C0]
0x1800790e8  jz      short loc_1800790F5
0x1800790ea  mov     byte ptr [rsi+28h], 1
0x1800790ee  jmp     short loc_1800790F5
  ... truncated ...
```
