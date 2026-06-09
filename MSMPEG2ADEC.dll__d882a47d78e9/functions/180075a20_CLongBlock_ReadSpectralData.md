# CLongBlock_ReadSpectralData

- ea: `0x180075a20`
- end: `0x180075ec0`
- name: `CLongBlock_ReadSpectralData`
- size: `1184`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18007f350`

## callees

- `0x1800021a8`
- `0x1800363f0`
- `0x180075a20`
- `0x18007f140`
- `0x18007f270`

## import_xrefs

- `mfperfhelper!__imp_ippsZero_8u` at `0x180075ac4`
- `mfperfhelper!__imp_ippsZero_8u` at `0x180075ac4`

## pseudocode

```c
__int64 __fastcall CLongBlock_ReadSpectralData(int *a1, __int64 *a2)
{
  float v2; // xmm0_4
  __int64 v3; // rax
  _BYTE *v4; // rdi
  __int64 *v6; // rsi
  char v7; // cl
  __int64 v9; // rbp
  __int64 v10; // r13
  __int64 v11; // r14
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  __int64 v15; // r12
  __int64 v16; // rbp
  int *v17; // r14
  __int64 v18; // rsi
  unsigned int v19; // edi
  int v20; // ecx
  int v21; // eax
  int v22; // edi
  char v23; // cl
  int v24; // edx
  int v25; // r8d
  int v26; // eax
  int v27; // edi
  __int64 i; // rdi
  int Escape; // eax
  __int64 v30; // rdx
  int v31; // eax
  bool v32; // sf
  int v33; // edx
  int v34; // ecx
  __int64 v35; // rax
  __int64 *v36; // rcx
  __int64 v37; // r11
  int v38; // edx
  int v39; // ecx
  int v40; // eax
  int v41; // r9d
  int v42; // eax
  int v43; // eax
  int v44; // r15d
  int v45; // ebx
  __int64 v46; // rbp
  __int64 v47; // rcx
  __int64 v48; // [rsp+28h] [rbp-50h]
  __int64 v49; // [rsp+30h] [rbp-48h]
  unsigned __int64 v50; // [rsp+38h] [rbp-40h]
  int v52; // [rsp+90h] [rbp+18h]
  int v53; // [rsp+90h] [rbp+18h]
  __int64 *v54; // [rsp+98h] [rbp+20h]

  v3 = 4LL * *((char *)a2 + 31);
  v4 = a2;
  if ( *((_BYTE *)a2 + 27) == 2 )
  {
    v6 = (__int64 *)(&off_18008B4A8)[v3];
    v7 = qword_18008B4A0[v3];
  }
  else
  {
    v6 = *(__int64 **)((char *)&off_18008B498 + v3 * 8);
    v7 = BYTE4(SamplingRateInfoTable[v3]);
  }
  v54 = v6;
  if ( v7 < *((char *)a2 + 28) )
    return 19;
  v9 = a2[1];
  v10 = a2[2];
  v11 = *a2;
  v49 = *a2;
  v48 = v9;
  ippsZero_8u(v10, 4096);
  LOBYTE(v12) = v4[28];
  v13 = 0;
  v52 = 0;
  if ( (char)v12 > 0 )
  {
    while ( 1 )
    {
      v14 = *(char *)(v13 + v9);
      if ( (_BYTE)v14 && (unsigned __int8)(v14 - 13) > 2u )
      {
        v15 = 2 * v14;
        v16 = HuffmanCodeBooks[16 * v14];
        v50 = v10 + 4LL * *((__int16 *)v6 + v13 + 1);
        v17 = (int *)(v10 + 4LL * *((__int16 *)v6 + v13));
        if ( (unsigned __int64)v17 < v50 )
        {
          while ( 1 )
          {
            v18 = qword_18008B618[v15];
            v19 = 0;
            do
            {
              if ( (unsigned int)*a1 < 4 )
                FillBitCache(a1, 4u);
              v20 = *a1 - 4;
              v19 = *(unsigned __int16 *)(v18 + 2LL * (v19 + (((unsigned int)a1[1] >> (*(_BYTE *)a1 - 4)) & 0xF)));
              *a1 = v20;
            }
            while ( (v19 & 8) == 0 );
            v21 = v19 & 3;
            v22 = v19 >> 4;
            *a1 = v20 + v21;
            v23 = byte_18008B611[8 * v15];
            v24 = byte_18008B612[8 * v15];
            v25 = (1 << v23) - 1;
            v26 = v22 & v25;
            v27 = v22 >> v23;
            *v17 = v26 - v24;
            v17[1] = (v25 & v27) - v24;
            if ( HuffmanCodeBooks[8 * v15] == 4 )
            {
              v17[2] = (v25 & (v27 >> v23)) - v24;
              v17[3] = (v25 & (v27 >> v23 >> v23)) - v24;
            }
            if ( !byte_18008B612[8 * v15] )
            {
              for ( i = 0; (int)i < (int)v16; i = (unsigned int)(i + 1) )
              {
                if ( v17[i] )
                {
                  if ( !*a1 )
                    FillBitCache(a1, 1u);
                  if ( (((unsigned int)a1[1] >> --*a1) & 1) != 0 )
                    v17[i] = -v17[i];
                }
              }
            }
            v13 = v52;
            if ( *(_BYTE *)(v52 + v48) == 11 )
            {
              Escape = CBlock_GetEscape(a1, (unsigned int)*v17);
              v30 = (unsigned int)v17[1];
              *v17 = Escape;
              v31 = CBlock_GetEscape(a1, v30);
              v32 = -*v17 < 0;
              v33 = -*v17;
              v17[1] = v31;
              if ( v32 )
                v33 = *v17;
              if ( v33 > 0x1FFF )
                return 3;
              v34 = -v31;
              if ( v31 > 0 )
                v34 = v31;
              if ( v34 > 0x1FFF )
                return 3;
              v13 = v52;
            }
            v17 += v16;
            if ( (unsigned __int64)v17 >= v50 )
            {
              v4 = a2;
              break;
            }
          }
        }
        v9 = v48;
      }
      v12 = (char)v4[28];
      v52 = ++v13;
      if ( v13 >= v12 )
        break;
      v6 = v54;
    }
    v11 = v49;
  }
  v35 = 4LL * (char)v4[31];
  if ( v4[27] == 2 )
    v36 = (__int64 *)(&off_18008B4A8)[v35];
  else
    v36 = *(__int64 **)((char *)&off_18008B498 + v35 * 8);
  v37 = v10;
  if ( v4[915] && (v38 = 0, v39 = *((__int16 *)v36 + (char)v4[917]), (char)v4[916] >= 0) )
  {
    while ( 1 )
    {
      v40 = (char)v4[v38 + 918];
      v39 += v40;
      if ( v39 < v40 || v39 >= 1024 )
        return 18;
      v41 = (char)v4[v38 + 922];
      v42 = *(_DWORD *)(v10 + 4LL * v39);
      if ( v42 <= 0 )
        v43 = v42 - v41;
      else
        v43 = v41 + v42;
      *(_DWORD *)(v10 + 4LL * v39) = v43;
      if ( ++v38 > (char)v4[916] )
      {
        LOBYTE(v12) = v4[28];
        goto LABEL_51;
      }
    }
  }
  else
  {
LABEL_51:
    v44 = 0;
    v45 = 0;
    v53 = 0;
    if ( (char)v12 <= 0 )
      goto LABEL_65;
    do
    {
      v45 = *((__int16 *)v54 + v44);
      if ( v45 < *((__int16 *)v54 + v44 + 1) )
      {
        v46 = *(__int16 *)(v11 + 2LL * v44);
        do
        {
          v47 = *(int *)(v37 + 4LL * v45);
          if ( (_DWORD)v47 )
          {
            if ( (unsigned int)(v47 + 192) > 0x155 || (unsigned int)(v46 + 84) > 0xB7 )
            {
              CBlock_Quantize_Impl(v47, (unsigned int)(v46 - 36));
              v37 = v10;
            }
            else
            {
              v2 = *(float *)&dword_1800A3450[v47] * *(float *)&dword_1800A3800[v46];
            }
          }
          else
          {
            v2 = 0.0;
          }
          *(float *)(v37 + 4LL * v45++) = v2;
        }
        while ( v45 < *((__int16 *)v54 + v44 + 1) );
        v44 = v53;
        v4 = a2;
      }
      ++v44;
      v11 = v49;
      v53 = v44;
    }
    while ( v44 < (char)v4[28] );
    if ( v45 < 1024 )
LABEL_65:
      memset_0((void *)(v37 + 4LL * v45), 0, 4LL * (1024 - v45));
    return 0;
  }
}

```

## disassembly

```asm
0x180075a20  mov     [rsp+arg_8], rdx
0x180075a25  push    rbx
0x180075a26  push    rsi
0x180075a27  push    rdi
0x180075a28  push    r15
0x180075a2a  sub     rsp, 58h
0x180075a2e  movsx   rax, byte ptr [rdx+1Fh]
0x180075a33  lea     r15, __ImageBase
0x180075a3a  shl     rax, 5
0x180075a3e  mov     rdi, rdx
0x180075a41  cmp     byte ptr [rdx+1Bh], 2
0x180075a45  mov     rbx, rcx
0x180075a48  jz      short loc_180075A5D
0x180075a4a  mov     rsi, [rax+r15+8B498h]
0x180075a52  movzx   ecx, byte ptr [rax+r15+8B494h]
0x180075a5b  jmp     short loc_180075A6E
0x180075a5d  mov     rsi, [rax+r15+8B4A8h]
0x180075a65  movzx   ecx, byte ptr [rax+r15+8B4A0h]
0x180075a6e  mov     [rsp+78h+arg_18], rsi
0x180075a76  cmp     cl, [rdx+1Ch]
0x180075a79  jge     short loc_180075A8B
0x180075a7b  mov     eax, 13h
0x180075a80  add     rsp, 58h
0x180075a84  pop     r15
0x180075a86  pop     rdi
0x180075a87  pop     rsi
0x180075a88  pop     rbx
0x180075a89  retn
0x180075a8b  mov     [rsp+78h+arg_0], rbp
0x180075a93  mov     rbp, [rdx+8]
0x180075a97  mov     [rsp+78h+var_28], r12
0x180075a9c  mov     [rsp+78h+var_30], r13
0x180075aa1  mov     r13, [rdx+10h]
0x180075aa5  mov     [rsp+78h+var_38], r14
0x180075aaa  mov     rcx, r13
0x180075aad  mov     r14, [rdx]
0x180075ab0  mov     edx, 1000h
0x180075ab5  mov     [rsp+78h+var_48], r14
0x180075aba  mov     [rsp+78h+var_50], rbp
0x180075abf  mov     [rsp+78h+var_58], r13
0x180075ac4  call    cs:__imp_ippsZero_8u
0x180075acb  nop     dword ptr [rax+rax+00h]
0x180075ad0  movzx   r8d, byte ptr [rdi+1Ch]
0x180075ad5  xor     r9d, r9d
0x180075ad8  mov     [rsp+78h+arg_10], r9d
0x180075ae0  test    r8b, r8b
0x180075ae3  jle     loc_180075CDF
0x180075ae9  nop     dword ptr [rax+00000000h]
0x180075af0  movsxd  rdx, r9d
0x180075af3  movsx   rcx, byte ptr [rdx+rbp]
0x180075af8  test    cl, cl
0x180075afa  jz      loc_180075CAE
0x180075b00  lea     eax, [rcx-0Dh]
0x180075b03  cmp     al, 2
0x180075b05  jbe     loc_180075CAE
0x180075b0b  movsx   rax, word ptr [rsi+rdx*2+2]
0x180075b11  mov     r12, rcx
0x180075b14  add     r12, r12
0x180075b17  lea     rcx, ds:0[rax*4]
0x180075b1f  movsx   rax, word ptr [rsi+rdx*2]
0x180075b24  movsx   rbp, ds:rva HuffmanCodeBooks[r15+r12*8]
0x180075b2d  add     rcx, r13
0x180075b30  mov     [rsp+78h+var_40], rcx
0x180075b35  lea     r14, ds:0[rax*4]
0x180075b3d  add     r14, r13
0x180075b40  cmp     r14, rcx
0x180075b43  jnb     loc_180075CA9
0x180075b49  nop     dword ptr [rax+00000000h]
0x180075b50  mov     rsi, ds:rva qword_18008B618[r15+r12*8]
0x180075b58  xor     edi, edi
0x180075b5a  nop     word ptr [rax+rax+00h]
0x180075b60  cmp     dword ptr [rbx], 4
0x180075b63  jnb     short loc_180075B72
0x180075b65  mov     edx, 4
0x180075b6a  mov     rcx, rbx
0x180075b6d  call    FillBitCache
0x180075b72  mov     ecx, [rbx]
0x180075b74  mov     eax, [rbx+4]
0x180075b77  add     ecx, 0FFFFFFFCh
0x180075b7a  shr     eax, cl
0x180075b7c  and     eax, 0Fh
0x180075b7f  add     eax, edi
0x180075b81  movzx   edi, word ptr [rsi+rax*2]
0x180075b85  mov     [rbx], ecx
0x180075b87  test    dil, 8
0x180075b8b  jz      short loc_180075B60
0x180075b8d  mov     eax, edi
0x180075b8f  mov     r8d, 1
0x180075b95  and     eax, 3
0x180075b98  shr     edi, 4
0x180075b9b  add     eax, ecx
0x180075b9d  mov     [rbx], eax
0x180075b9f  movsx   ecx, ds:rva byte_18008B611[r15+r12*8]
0x180075ba8  movsx   edx, ds:rva byte_18008B612[r15+r12*8]
0x180075bb1  shl     r8d, cl
0x180075bb4  dec     r8d
0x180075bb7  mov     eax, r8d
0x180075bba  and     eax, edi
0x180075bbc  sar     edi, cl
0x180075bbe  sub     eax, edx
0x180075bc0  mov     [r14], eax
0x180075bc3  mov     eax, edi
0x180075bc5  and     eax, r8d
0x180075bc8  sub     eax, edx
0x180075bca  mov     [r14+4], eax
0x180075bce  cmp     ds:rva HuffmanCodeBooks[r15+r12*8], 4
0x180075bd7  jnz     short loc_180075BF1
0x180075bd9  sar     edi, cl
0x180075bdb  mov     eax, edi
0x180075bdd  sar     edi, cl
0x180075bdf  and     eax, r8d
0x180075be2  and     edi, r8d
0x180075be5  sub     eax, edx
0x180075be7  sub     edi, edx
0x180075be9  mov     [r14+8], eax
0x180075bed  mov     [r14+0Ch], edi
0x180075bf1  cmp     ds:rva byte_18008B612[r15+r12*8], 0
0x180075bfa  jnz     short loc_180075C38
0x180075bfc  xor     edi, edi
0x180075bfe  test    ebp, ebp
0x180075c00  jle     short loc_180075C38
0x180075c02  cmp     dword ptr [r14+rdi*4], 0
0x180075c07  jz      short loc_180075C32
0x180075c09  cmp     dword ptr [rbx], 1
0x180075c0c  jnb     short loc_180075C1B
0x180075c0e  mov     edx, 1
0x180075c13  mov     rcx, rbx
0x180075c16  call    FillBitCache
0x180075c1b  dec     dword ptr [rbx]
0x180075c1d  mov     eax, [rbx+4]
0x180075c20  mov     ecx, [rbx]
0x180075c22  shr     eax, cl
0x180075c24  test    al, 1
0x180075c26  jz      short loc_180075C32
0x180075c28  mov     eax, [r14+rdi*4]
0x180075c2c  neg     eax
0x180075c2e  mov     [r14+rdi*4], eax
0x180075c32  inc     edi
0x180075c34  cmp     edi, ebp
0x180075c36  jl      short loc_180075C02
0x180075c38  movsxd  r9, [rsp+78h+arg_10]
0x180075c40  mov     rcx, [rsp+78h+var_50]
0x180075c45  cmp     byte ptr [r9+rcx], 0Bh
0x180075c4a  jnz     short loc_180075C92
0x180075c4c  mov     edx, [r14]
0x180075c4f  mov     rcx, rbx
0x180075c52  call    CBlock_GetEscape
0x180075c57  mov     edx, [r14+4]
0x180075c5b  mov     rcx, rbx
0x180075c5e  mov     [r14], eax
0x180075c61  call    CBlock_GetEscape
0x180075c66  mov     edx, [r14]
0x180075c69  neg     edx
0x180075c6b  mov     [r14+4], eax
0x180075c6f  cmovs   edx, [r14]
0x180075c73  cmp     edx, 1FFFh
0x180075c79  jg      short loc_180075CD0
0x180075c7b  mov     ecx, eax
0x180075c7d  neg     ecx
0x180075c7f  cmovs   ecx, eax
0x180075c82  cmp     ecx, 1FFFh
0x180075c88  jg      short loc_180075CD0
0x180075c8a  mov     r9d, [rsp+78h+arg_10]
0x180075c92  lea     r14, [r14+rbp*4]
0x180075c96  cmp     r14, [rsp+78h+var_40]
0x180075c9b  jb      loc_180075B50
0x180075ca1  mov     rdi, [rsp+78h+arg_8]
0x180075ca9  mov     rbp, [rsp+78h+var_50]
0x180075cae  movsx   r8d, byte ptr [rdi+1Ch]
0x180075cb3  inc     r9d
0x180075cb6  mov     [rsp+78h+arg_10], r9d
0x180075cbe  cmp     r9d, r8d
0x180075cc1  jge     short loc_180075CDA
0x180075cc3  mov     rsi, [rsp+78h+arg_18]
0x180075ccb  jmp     loc_180075AF0
0x180075cd0  mov     eax, 3
0x180075cd5  jmp     loc_180075E8A
0x180075cda  mov     r14, [rsp+78h+var_48]
0x180075cdf  movsx   rax, byte ptr [rdi+1Fh]
0x180075ce4  shl     rax, 5
0x180075ce8  cmp     byte ptr [rdi+1Bh], 2
0x180075cec  jz      short loc_180075CF8
0x180075cee  mov     rcx, [rax+r15+8B498h]
0x180075cf6  jmp     short loc_180075D00
0x180075cf8  mov     rcx, [rax+r15+8B4A8h]
0x180075d00  cmp     byte ptr [rdi+393h], 0
0x180075d07  mov     r13d, 400h
0x180075d0d  mov     r11, [rsp+78h+var_58]
0x180075d12  jz      short loc_180075D81
0x180075d14  movsx   rax, byte ptr [rdi+395h]
0x180075d1c  xor     edx, edx
0x180075d1e  movsx   ecx, word ptr [rcx+rax*2]
0x180075d22  cmp     [rdi+394h], dl
0x180075d28  jl      short loc_180075D81
0x180075d2a  nop     word ptr [rax+rax+00h]
0x180075d30  movsxd  r8, edx
0x180075d33  movsx   eax, byte ptr [r8+rdi+396h]
0x180075d3c  add     ecx, eax
0x180075d3e  cmp     ecx, eax
0x180075d40  jl      loc_180075E08
0x180075d46  cmp     ecx, r13d
0x180075d49  jge     loc_180075E08
0x180075d4f  movsx   r9d, byte ptr [r8+rdi+39Ah]
0x180075d58  movsxd  r10, ecx
0x180075d5b  mov     eax, [r11+r10*4]
0x180075d5f  test    eax, eax
0x180075d61  jle     short loc_180075D68
0x180075d63  add     eax, r9d
0x180075d66  jmp     short loc_180075D6B
0x180075d68  sub     eax, r9d
0x180075d6b  mov     [r11+r10*4], eax
0x180075d6f  inc     edx
0x180075d71  movsx   eax, byte ptr [rdi+394h]
0x180075d78  cmp     edx, eax
0x180075d7a  jle     short loc_180075D30
0x180075d7c  movzx   r8d, byte ptr [rdi+1Ch]
0x180075d81  xor     r15d, r15d
0x180075d84  xor     ebx, ebx
0x180075d86  mov     [rsp+78h+arg_10], r15d
0x180075d8e  test    r8b, r8b
0x180075d91  jle     loc_180075E70
0x180075d97  lea     r13, __ImageBase
0x180075d9e  xchg    ax, ax
0x180075da0  mov     rax, [rsp+78h+arg_18]
0x180075da8  movsxd  rsi, r15d
0x180075dab  movsx   ebx, word ptr [rax+rsi*2]
0x180075daf  movsx   eax, word ptr [rax+rsi*2+2]
0x180075db4  cmp     ebx, eax
0x180075db6  jge     loc_180075E43
0x180075dbc  movsx   rbp, word ptr [r14+rsi*2]
0x180075dc1  mov     r15, [rsp+78h+arg_18]
0x180075dc9  nop     dword ptr [rax+00000000h]
0x180075dd0  movsxd  rdi, ebx
0x180075dd3  movsxd  rcx, dword ptr [r11+rdi*4]
0x180075dd7  test    ecx, ecx
0x180075dd9  jz      short loc_180075E1E
0x180075ddb  lea     eax, [rcx+0C0h]
0x180075de1  cmp     eax, 155h
0x180075de6  ja      short loc_180075E0F
0x180075de8  lea     eax, [rbp+54h]
0x180075deb  cmp     eax, 0B7h
0x180075df0  ja      short loc_180075E0F
0x180075df2  movss   xmm0, ds:rva dword_1800A3450[r13+rcx*4]
0x180075dfc  mulss   xmm0, ds:rva dword_1800A3800[r13+rbp*4]
0x180075e06  jmp     short loc_180075E21
0x180075e08  mov     eax, 12h
0x180075e0d  jmp     short loc_180075E8A
0x180075e0f  lea     edx, [rbp-24h]
0x180075e12  call    CBlock_Quantize_Impl
0x180075e17  mov     r11, [rsp+78h+var_58]
0x180075e1c  jmp     short loc_180075E21
0x180075e1e  xorps   xmm0, xmm0
0x180075e21  movss   dword ptr [r11+rdi*4], xmm0
0x180075e27  inc     ebx
0x180075e29  movsx   eax, word ptr [r15+rsi*2+2]
0x180075e2f  cmp     ebx, eax
0x180075e31  jl      short loc_180075DD0
0x180075e33  mov     r15d, [rsp+78h+arg_10]
0x180075e3b  mov     rdi, [rsp+78h+arg_8]
0x180075e43  movsx   eax, byte ptr [rdi+1Ch]
0x180075e47  inc     r15d
0x180075e4a  mov     r14, [rsp+78h+var_48]
0x180075e4f  mov     [rsp+78h+arg_10], r15d
0x180075e57  cmp     r15d, eax
0x180075e5a  jl      loc_180075DA0
0x180075e60  mov     r13d, 400h
0x180075e66  cmp     ebx, r13d
0x180075e69  jge     short loc_180075E88
0x180075e6b  nop     dword ptr [rax+rax+00h]
0x180075e70  movsxd  rax, ebx
0x180075e73  sub     r13d, ebx
0x180075e76  movsxd  r8, r13d
0x180075e79  xor     edx, edx; Val
0x180075e7b  shl     r8, 2; Size
0x180075e7f  lea     rcx, [r11+rax*4]; void *
0x180075e83  call    memset_0
0x180075e88  xor     eax, eax
0x180075e8a  mov     r13, [rsp+78h+var_30]
0x180075e8f  mov     r12, [rsp+78h+var_28]
0x180075e94  mov     rbp, [rsp+78h+arg_0]
0x180075e9c  mov     r14, [rsp+78h+var_38]
0x180075ea1  add     rsp, 58h
0x180075ea5  pop     r15
0x180075ea7  pop     rdi
0x180075ea8  pop     rsi
0x180075ea9  pop     rbx
0x180075eaa  retn
```
