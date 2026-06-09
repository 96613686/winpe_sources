# ReadPsData(PS_DEC *,CDK_BITSTREAM *,int)

- ea: `0x18001a9d0`
- end: `0x18001aea3`
- name: `?ReadPsData@@YAIPEAUPS_DEC@@PEAUCDK_BITSTREAM@@H@Z`
- size: `1235`
- prototype: `unsigned int __fastcall(struct PS_DEC *, struct CDK_BITSTREAM *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180019d84`

## callees

- `0x1800110c0`
- `0x18001a9d0`
- `0x18001aeac`
- `0x18001aefc`

## pseudocode

```c
__int64 __fastcall ReadPsData(struct PS_DEC *a1, struct CDK_BITSTREAM *a2, int a3)
{
  __int64 v6; // rax
  __int64 v7; // r14
  char *v8; // rsi
  _OWORD *v9; // rax
  _OWORD *v10; // rdx
  __int64 v11; // rcx
  __int128 v12; // xmm1
  int v13; // r15d
  __int64 v14; // r8
  __int64 v15; // r8
  char v16; // al
  __int64 v17; // r8
  int v18; // eax
  __int64 v19; // r8
  int v20; // edx
  unsigned __int8 v21; // cl
  unsigned __int8 v22; // al
  unsigned __int8 v23; // bp
  char v24; // al
  __int64 v25; // r12
  const signed __int8 (near **v26)[2]; // r15
  unsigned __int8 v27; // r13
  __int64 v28; // rbp
  char v29; // al
  __int64 v30; // rcx
  int i; // ebp
  __int64 v33; // r8
  unsigned int v34; // ebx
  char v35; // al
  __int64 v36; // r8
  char v37; // al
  __int64 v38; // r8
  unsigned __int8 v39; // r12
  const signed __int8 (near **v40)[2]; // rax
  const signed __int8 (near **v41)[2]; // rbp
  unsigned __int8 v42; // r13
  char v43; // al
  __int64 v44; // rcx
  __int64 v45; // rax
  unsigned __int8 v46; // r12
  char v47; // al
  __int64 v48; // rcx
  int v49; // esi
  __int64 v50; // r8
  char v51; // [rsp+20h] [rbp-58h]
  char v52; // [rsp+20h] [rbp-58h]
  __int64 v53; // [rsp+30h] [rbp-48h]
  unsigned __int8 v54; // [rsp+80h] [rbp+8h]
  unsigned __int8 v55; // [rsp+80h] [rbp+8h]
  int valid; // [rsp+98h] [rbp+20h]

  if ( !a1 )
    return 0;
  v6 = *((unsigned __int8 *)a1 + 14);
  v7 = 367 * v6;
  v8 = (char *)a1 + 367 * v6 + 16;
  if ( (_BYTE)v6 != *((_BYTE *)a1 + 13) )
  {
    v9 = (_OWORD *)((char *)a1 + 367 * v6 + 16);
    v10 = (_OWORD *)((char *)a1 + 367 * *((unsigned __int8 *)a1 + 13) + 16);
    v11 = 2;
    do
    {
      *v9 = *v10;
      v9[1] = v10[1];
      v9[2] = v10[2];
      v9[3] = v10[3];
      v9[4] = v10[4];
      v9[5] = v10[5];
      v9[6] = v10[6];
      v12 = v10[7];
      v10 += 8;
      v9[7] = v12;
      v9 += 8;
      --v11;
    }
    while ( v11 );
    *v9 = *v10;
    v9[1] = v10[1];
    v9[2] = v10[2];
    v9[3] = v10[3];
    v9[4] = v10[4];
    v9[5] = v10[5];
    *(_OWORD *)((char *)v9 + 95) = *(_OWORD *)((char *)v10 + 95);
  }
  valid = CDKgetValidBits(a2);
  v13 = valid;
  if ( (unsigned __int8)CDKreadBits(a2, 1, v14) )
  {
    *v8 = 1;
    v35 = CDKreadBits(a2, 1, v15);
    v8[1] = v35;
    if ( v35 )
      v8[4] = CDKreadBits(a2, 3, v36);
    v37 = CDKreadBits(a2, 1, v36);
    v8[2] = v37;
    if ( v37 )
      v8[5] = CDKreadBits(a2, 3, v38);
    v8[3] = CDKreadBits(a2, 1, v38);
  }
  v16 = CDKreadBits(a2, 1, v15);
  v8[9] = v16;
  if ( v16 )
  {
    v46 = 1;
    v20 = (unsigned __int8)(CDKreadBits(a2, 2, v17) + 1);
    v8[10] = v20;
    v18 = v20 + 1;
    if ( (unsigned int)(v20 + 1) > 1 )
    {
      do
      {
        v47 = CDKreadBits(a2, 5, v19);
        v48 = v46++;
        v8[v48 + 11] = v47 + 1;
        v20 = (unsigned __int8)v8[10];
        v18 = v46;
      }
      while ( v46 < (unsigned int)(v20 + 1) );
    }
  }
  else
  {
    v18 = CDKreadBits(a2, 2, v17);
    LOBYTE(v20) = *((_BYTE *)&CDK_sbrDecoder_aFixNoEnvDecode + (unsigned __int8)v18);
    v8[10] = v20;
  }
  LOBYTE(v18) = *((_BYTE *)a1 + v7 + 20);
  if ( (unsigned __int8)v18 > 5u || (v21 = *((_BYTE *)a1 + v7 + 21), v21 > 5u) )
  {
    *((_DWORD *)a1 + *((unsigned __int8 *)a1 + 14) + 1) = 0;
    for ( i = CDKgetValidBits(a2) - valid + a3; i > 0; i -= v34 )
    {
      v34 = i;
      if ( (unsigned int)i > 8 )
        v34 = 8;
      CDKreadBits(a2, v34, v33);
    }
  }
  else
  {
    if ( (unsigned __int8)v18 <= 2u )
      LOBYTE(v19) = *((_BYTE *)a1 + v7 + 20);
    else
      v19 = (unsigned int)(v18 - 3);
    *((_BYTE *)a1 + v7 + 22) = v19;
    *((_BYTE *)a1 + v7 + 24) = (unsigned __int8)v18 > 2u;
    if ( v21 > 2u )
      v21 -= 3;
    *((_BYTE *)a1 + v7 + 23) = v21;
    if ( *((_BYTE *)a1 + v7 + 17) && (v39 = 0, v55 = 0, (_BYTE)v20) )
    {
      do
      {
        v52 = CDKreadBits(a2, 1, v19);
        if ( v52 )
        {
          v41 = &aBookPsIidFineTimeDecode;
          v40 = &aBookPsIidTimeDecode;
        }
        else
        {
          v40 = &aBookPsIidFreqDecode;
          v41 = &aBookPsIidFineFreqDecode;
        }
        if ( !*((_BYTE *)a1 + v7 + 24) )
          v41 = v40;
        v42 = 0;
        if ( *((_BYTE *)&CDK_sbrDecoder_aNoIccBins + *((unsigned __int8 *)a1 + v7 + 22)) )
        {
          do
          {
            v43 = decode_huff_cw(v41, a2);
            v44 = v42++;
            v8[34 * v39 + 27 + v44] = v43;
          }
          while ( v42 < *((_BYTE *)&CDK_sbrDecoder_aNoIccBins + *((unsigned __int8 *)a1 + v7 + 22)) );
          v39 = v55;
        }
        v45 = v39++;
        v55 = v39;
        v8[v45 + 17] = v52;
        v22 = v8[10];
      }
      while ( v39 < v22 );
      v13 = valid;
    }
    else
    {
      v22 = v20;
    }
    if ( *((_BYTE *)a1 + v7 + 18) )
    {
      v23 = 0;
      v54 = 0;
      if ( v22 )
      {
        do
        {
          v24 = CDKreadBits(a2, 1, v19);
          v25 = v23;
          v51 = v24;
          v26 = &aBookPsIccFreqDecode;
          v53 = v23;
          if ( v24 )
            v26 = &aBookPsIccTimeDecode;
          v27 = 0;
          if ( *((_BYTE *)&CDK_sbrDecoder_aNoIccBins + (unsigned __int8)v8[7]) )
          {
            v28 = 34LL * v23;
            do
            {
              v29 = decode_huff_cw(v26, a2);
              v30 = v27++;
              v8[v30 + 197 + v28] = v29;
            }
            while ( v27 < *((_BYTE *)&CDK_sbrDecoder_aNoIccBins + *((unsigned __int8 *)a1 + v7 + 23)) );
            v23 = v54;
            v25 = v53;
            v24 = v51;
          }
          v8[v25 + 22] = v24;
          v54 = ++v23;
        }
        while ( v23 < (unsigned __int8)v8[10] );
        v13 = valid;
      }
    }
    if ( *((_BYTE *)a1 + v7 + 19) )
    {
      v49 = CDKreadBits(a2, 4, v19);
      if ( v49 == 15 )
        v49 = CDKreadBits(a2, 8, v50) + 15;
      for ( ; v49; --v49 )
        CDKreadBits(a2, 8, v50);
    }
    *((_DWORD *)a1 + *((unsigned __int8 *)a1 + 14) + 1) = 1;
  }
  return v13 - (unsigned int)CDKgetValidBits(a2);
}

```

## disassembly

```asm
0x18001a9d0  mov     [rsp+arg_8], rbx
0x18001a9d5  push    rbp
0x18001a9d6  push    rsi
0x18001a9d7  push    rdi
0x18001a9d8  push    r12
0x18001a9da  push    r13
0x18001a9dc  push    r14
0x18001a9de  push    r15
0x18001a9e0  sub     rsp, 40h
0x18001a9e4  mov     ebp, r8d
0x18001a9e7  mov     rdi, rdx
0x18001a9ea  mov     rbx, rcx
0x18001a9ed  test    rcx, rcx
0x18001a9f0  jz      loc_18001ACF8
0x18001a9f6  movzx   eax, byte ptr [rcx+0Eh]
0x18001a9fa  lea     rsi, [rcx+10h]
0x18001a9fe  imul    r14, rax, 16Fh
0x18001aa05  add     rsi, r14
0x18001aa08  cmp     al, [rcx+0Dh]
0x18001aa0b  jz      loc_18001AAAF
0x18001aa11  movzx   eax, byte ptr [rcx+0Dh]
0x18001aa15  imul    rdx, rax, 16Fh
0x18001aa1c  mov     rax, rsi
0x18001aa1f  add     rdx, 10h
0x18001aa23  add     rdx, rcx
0x18001aa26  mov     ecx, 2
0x18001aa2b  lea     r8d, [rcx+7Eh]
0x18001aa2f  movups  xmm0, xmmword ptr [rdx]
0x18001aa32  movups  xmmword ptr [rax], xmm0
0x18001aa35  movups  xmm1, xmmword ptr [rdx+10h]
0x18001aa39  movups  xmmword ptr [rax+10h], xmm1
0x18001aa3d  movups  xmm0, xmmword ptr [rdx+20h]
0x18001aa41  movups  xmmword ptr [rax+20h], xmm0
0x18001aa45  movups  xmm1, xmmword ptr [rdx+30h]
0x18001aa49  movups  xmmword ptr [rax+30h], xmm1
0x18001aa4d  movups  xmm0, xmmword ptr [rdx+40h]
0x18001aa51  movups  xmmword ptr [rax+40h], xmm0
0x18001aa55  movups  xmm1, xmmword ptr [rdx+50h]
0x18001aa59  movups  xmmword ptr [rax+50h], xmm1
0x18001aa5d  movups  xmm0, xmmword ptr [rdx+60h]
0x18001aa61  movups  xmmword ptr [rax+60h], xmm0
0x18001aa65  movups  xmm1, xmmword ptr [rdx+70h]
0x18001aa69  add     rdx, r8
0x18001aa6c  movups  xmmword ptr [rax+70h], xmm1
0x18001aa70  add     rax, r8
0x18001aa73  sub     rcx, 1
0x18001aa77  jnz     short loc_18001AA2F
0x18001aa79  movups  xmm0, xmmword ptr [rdx]
0x18001aa7c  movups  xmmword ptr [rax], xmm0
0x18001aa7f  movups  xmm1, xmmword ptr [rdx+10h]
0x18001aa83  movups  xmmword ptr [rax+10h], xmm1
0x18001aa87  movups  xmm0, xmmword ptr [rdx+20h]
0x18001aa8b  movups  xmmword ptr [rax+20h], xmm0
0x18001aa8f  movups  xmm1, xmmword ptr [rdx+30h]
0x18001aa93  movups  xmmword ptr [rax+30h], xmm1
0x18001aa97  movups  xmm0, xmmword ptr [rdx+40h]
0x18001aa9b  movups  xmmword ptr [rax+40h], xmm0
0x18001aa9f  movups  xmm1, xmmword ptr [rdx+50h]
0x18001aaa3  movups  xmmword ptr [rax+50h], xmm1
0x18001aaa7  movups  xmm0, xmmword ptr [rdx+5Fh]
0x18001aaab  movups  xmmword ptr [rax+5Fh], xmm0
0x18001aaaf  mov     rcx, rdi
0x18001aab2  call    CDKgetValidBits
0x18001aab7  mov     r13d, 1
0x18001aabd  mov     [rsp+78h+arg_18], eax
0x18001aac4  mov     edx, r13d
0x18001aac7  mov     rcx, rdi
0x18001aaca  mov     r15d, eax
0x18001aacd  call    CDKreadBits
0x18001aad2  test    al, al
0x18001aad4  jnz     loc_18001ACB6
0x18001aada  mov     edx, r13d
0x18001aadd  mov     rcx, rdi
0x18001aae0  call    CDKreadBits
0x18001aae5  mov     [rsi+9], al
0x18001aae8  lea     r12, __ImageBase
0x18001aaef  mov     edx, 2
0x18001aaf4  mov     rcx, rdi
0x18001aaf7  test    al, al
0x18001aaf9  jnz     loc_18001ADFD
0x18001aaff  call    CDKreadBits
0x18001ab04  movzx   ecx, al
0x18001ab07  mov     dl, [rcx+r12+0D28F8h]
0x18001ab0f  mov     [rsi+0Ah], dl
0x18001ab12  mov     al, [r14+rbx+14h]
0x18001ab17  cmp     al, 5
0x18001ab19  ja      loc_18001AC70
0x18001ab1f  mov     cl, [r14+rbx+15h]
0x18001ab24  cmp     cl, 5
0x18001ab27  ja      loc_18001AC70
0x18001ab2d  cmp     al, 2
0x18001ab2f  jbe     loc_18001ACAE
0x18001ab35  lea     r8d, [rax-3]
0x18001ab39  setnbe  al
0x18001ab3c  mov     [r14+rbx+16h], r8b
0x18001ab41  mov     [r14+rbx+18h], al
0x18001ab46  cmp     cl, 2
0x18001ab49  jbe     short loc_18001AB4E
0x18001ab4b  sub     cl, 3
0x18001ab4e  mov     [r14+rbx+17h], cl
0x18001ab53  cmp     byte ptr [r14+rbx+11h], 0
0x18001ab59  jnz     loc_18001ACFF
0x18001ab5f  mov     al, dl
0x18001ab61  cmp     byte ptr [r14+rbx+12h], 0
0x18001ab67  jz      loc_18001AC34
0x18001ab6d  xor     bpl, bpl
0x18001ab70  mov     [rsp+78h+arg_0], bpl
0x18001ab78  test    al, al
0x18001ab7a  jz      loc_18001AC34
0x18001ab80  mov     edx, r13d
0x18001ab83  mov     rcx, rdi
0x18001ab86  call    CDKreadBits
0x18001ab8b  test    al, al
0x18001ab8d  movzx   r12d, bpl
0x18001ab91  lea     rcx, ?aBookPsIccTimeDecode@@3QAY01$$CBCA; signed char const (near * aBookPsIccTimeDecode)[2]
0x18001ab98  mov     dword ptr [rsp+78h+var_58], eax
0x18001ab9c  lea     r15, ?aBookPsIccFreqDecode@@3QAY01$$CBCA; signed char const (near * aBookPsIccFreqDecode)[2]
0x18001aba3  mov     [rsp+78h+var_48], r12
0x18001aba8  cmovnz  r15, rcx
0x18001abac  lea     rdx, __ImageBase
0x18001abb3  movzx   ecx, byte ptr [rsi+7]
0x18001abb7  xor     r13b, r13b
0x18001abba  cmp     [rcx+rdx+0D2978h], r13b
0x18001abc2  jbe     short loc_18001AC0C
0x18001abc4  imul    rbp, r12, 22h ; '"'
0x18001abc8  lea     r12, __ImageBase
0x18001abcf  mov     rdx, rdi
0x18001abd2  mov     rcx, r15
0x18001abd5  call    decode_huff_cw
0x18001abda  movzx   ecx, r13b
0x18001abde  inc     r13b
0x18001abe1  add     rcx, rsi
0x18001abe4  mov     [rcx+rbp+0C5h], al
0x18001abeb  movzx   eax, byte ptr [r14+rbx+17h]
0x18001abf1  cmp     r13b, [rax+r12+0D2978h]
0x18001abf9  jb      short loc_18001ABCF
0x18001abfb  mov     bpl, [rsp+78h+arg_0]
0x18001ac03  mov     r12, [rsp+78h+var_48]
0x18001ac08  mov     eax, dword ptr [rsp+78h+var_58]
0x18001ac0c  mov     r13d, 1
0x18001ac12  mov     [rsi+r12+16h], al
0x18001ac17  add     bpl, r13b
0x18001ac1a  mov     [rsp+78h+arg_0], bpl
0x18001ac22  cmp     bpl, [rsi+0Ah]
0x18001ac26  jb      loc_18001AB80
0x18001ac2c  mov     r15d, [rsp+78h+arg_18]
0x18001ac34  cmp     byte ptr [r14+rbx+13h], 0
0x18001ac3a  jnz     loc_18001AE5E
0x18001ac40  movzx   eax, byte ptr [rbx+0Eh]
0x18001ac44  mov     [rbx+rax*4+4], r13d
0x18001ac49  mov     rcx, rdi
0x18001ac4c  call    CDKgetValidBits
0x18001ac51  sub     r15d, eax
0x18001ac54  mov     eax, r15d
0x18001ac57  mov     rbx, [rsp+78h+arg_8]
0x18001ac5f  add     rsp, 40h
0x18001ac63  pop     r15
0x18001ac65  pop     r14
0x18001ac67  pop     r13
0x18001ac69  pop     r12
0x18001ac6b  pop     rdi
0x18001ac6c  pop     rsi
0x18001ac6d  pop     rbp
0x18001ac6e  retn
0x18001ac70  movzx   eax, byte ptr [rbx+0Eh]
0x18001ac74  mov     rcx, rdi
0x18001ac77  mov     dword ptr [rbx+rax*4+4], 0
0x18001ac7f  call    CDKgetValidBits
0x18001ac84  sub     eax, r15d
0x18001ac87  add     ebp, eax
0x18001ac89  test    ebp, ebp
0x18001ac8b  jle     short loc_18001AC49
0x18001ac8d  mov     r14d, 8
0x18001ac93  cmp     ebp, r14d
0x18001ac96  mov     ebx, ebp
0x18001ac98  mov     rcx, rdi
0x18001ac9b  cmova   ebx, r14d
0x18001ac9f  mov     edx, ebx
0x18001aca1  call    CDKreadBits
0x18001aca6  sub     ebp, ebx
0x18001aca8  test    ebp, ebp
0x18001acaa  jg      short loc_18001AC93
0x18001acac  jmp     short loc_18001AC49
0x18001acae  mov     r8b, al
0x18001acb1  jmp     loc_18001AB39
0x18001acb6  mov     edx, r13d
0x18001acb9  mov     [rsi], r13b
0x18001acbc  mov     rcx, rdi
0x18001acbf  call    CDKreadBits
0x18001acc4  mov     [rsi+1], al
0x18001acc7  test    al, al
0x18001acc9  jnz     loc_18001ADD3
0x18001accf  mov     edx, r13d
0x18001acd2  mov     rcx, rdi
0x18001acd5  call    CDKreadBits
0x18001acda  mov     [rsi+2], al
0x18001acdd  test    al, al
0x18001acdf  jnz     loc_18001ADE8
0x18001ace5  mov     edx, r13d
0x18001ace8  mov     rcx, rdi
0x18001aceb  call    CDKreadBits
0x18001acf0  mov     [rsi+3], al
0x18001acf3  jmp     loc_18001AADA
0x18001acf8  xor     eax, eax
0x18001acfa  jmp     loc_18001AC57
0x18001acff  xor     r12b, r12b
0x18001ad02  mov     [rsp+78h+arg_0], r12b
0x18001ad0a  test    dl, dl
0x18001ad0c  jz      loc_18001AB5F
0x18001ad12  mov     edx, r13d
0x18001ad15  mov     rcx, rdi
0x18001ad18  call    CDKreadBits
0x18001ad1d  mov     cl, [r14+rbx+18h]
0x18001ad22  mov     dword ptr [rsp+78h+var_58], eax
0x18001ad26  test    al, al
0x18001ad28  jnz     loc_18001AE4B
0x18001ad2e  lea     rax, ?aBookPsIidFreqDecode@@3QAY01$$CBCA; signed char const (near * aBookPsIidFreqDecode)[2]
0x18001ad35  lea     rbp, ?aBookPsIidFineFreqDecode@@3QAY01$$CBCA; signed char const (near * aBookPsIidFineFreqDecode)[2]
0x18001ad3c  test    cl, cl
0x18001ad3e  lea     rcx, __ImageBase
0x18001ad45  cmovz   rbp, rax
0x18001ad49  movzx   eax, byte ptr [r14+rbx+16h]
0x18001ad4f  xor     r13b, r13b
0x18001ad52  cmp     [rax+rcx+0D2978h], r13b
0x18001ad5a  jbe     short loc_18001AD9D
0x18001ad5c  movzx   eax, r12b
0x18001ad60  lea     r12, __ImageBase
0x18001ad67  imul    r15, rax, 22h ; '"'
0x18001ad6b  mov     rdx, rdi
0x18001ad6e  mov     rcx, rbp
0x18001ad71  call    decode_huff_cw
0x18001ad76  movzx   ecx, r13b
0x18001ad7a  inc     r13b
0x18001ad7d  add     rcx, rsi
0x18001ad80  mov     [rcx+r15+1Bh], al
0x18001ad85  movzx   eax, byte ptr [r14+rbx+16h]
0x18001ad8b  cmp     r13b, [rax+r12+0D2978h]
0x18001ad93  jb      short loc_18001AD6B
0x18001ad95  mov     r12b, [rsp+78h+arg_0]
0x18001ad9d  mov     ecx, dword ptr [rsp+78h+var_58]
0x18001ada1  mov     r13d, 1
0x18001ada7  movzx   eax, r12b
0x18001adab  add     r12b, r13b
0x18001adae  mov     [rsp+78h+arg_0], r12b
0x18001adb6  mov     [rax+rsi+11h], cl
0x18001adba  mov     al, [rsi+0Ah]
0x18001adbd  cmp     r12b, al
0x18001adc0  jb      loc_18001AD12
0x18001adc6  mov     r15d, [rsp+78h+arg_18]
0x18001adce  jmp     loc_18001AB61
0x18001add3  mov     edx, 3
0x18001add8  mov     rcx, rdi
0x18001addb  call    CDKreadBits
0x18001ade0  mov     [rsi+4], al
0x18001ade3  jmp     loc_18001ACCF
0x18001ade8  mov     edx, 3
0x18001aded  mov     rcx, rdi
0x18001adf0  call    CDKreadBits
0x18001adf5  mov     [rsi+5], al
0x18001adf8  jmp     loc_18001ACE5
0x18001adfd  call    CDKreadBits
0x18001ae02  add     al, r13b
0x18001ae05  mov     r12b, r13b
0x18001ae08  movzx   edx, al
0x18001ae0b  mov     [rsi+0Ah], dl
0x18001ae0e  lea     eax, [rdx+r13]
0x18001ae12  cmp     eax, r13d
0x18001ae15  jbe     loc_18001AB12
0x18001ae1b  mov     edx, 5
0x18001ae20  mov     rcx, rdi
0x18001ae23  call    CDKreadBits
0x18001ae28  movzx   ecx, r12b
0x18001ae2c  add     al, r13b
0x18001ae2f  add     r12b, r13b
0x18001ae32  mov     [rcx+rsi+0Bh], al
0x18001ae36  movzx   edx, byte ptr [rsi+0Ah]
0x18001ae3a  movzx   eax, r12b
0x18001ae3e  lea     ecx, [rdx+r13]
0x18001ae42  cmp     eax, ecx
0x18001ae44  jb      short loc_18001AE1B
0x18001ae46  jmp     loc_18001AB12
0x18001ae4b  lea     rbp, ?aBookPsIidFineTimeDecode@@3QAY01$$CBCA; signed char const (near * aBookPsIidFineTimeDecode)[2]
0x18001ae52  lea     rax, ?aBookPsIidTimeDecode@@3QAY01$$CBCA; signed char const (near * aBookPsIidTimeDecode)[2]
0x18001ae59  jmp     loc_18001AD3C
0x18001ae5e  mov     edx, 4
0x18001ae63  mov     rcx, rdi
0x18001ae66  call    CDKreadBits
0x18001ae6b  mov     esi, eax
0x18001ae6d  mov     r14d, 8
0x18001ae73  cmp     eax, 0Fh
0x18001ae76  jnz     short loc_18001AE86
0x18001ae78  mov     edx, r14d
0x18001ae7b  mov     rcx, rdi
0x18001ae7e  call    CDKreadBits
0x18001ae83  lea     esi, [rax+0Fh]
0x18001ae86  test    esi, esi
0x18001ae88  jz      loc_18001AC40
0x18001ae8e  mov     edx, r14d
0x18001ae91  mov     rcx, rdi
0x18001ae94  call    CDKreadBits
  ... truncated ...
```
