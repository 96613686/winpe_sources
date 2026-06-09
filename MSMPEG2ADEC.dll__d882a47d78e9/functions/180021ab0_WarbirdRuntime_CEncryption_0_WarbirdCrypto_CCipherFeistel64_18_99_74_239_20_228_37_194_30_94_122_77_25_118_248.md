# WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)

- ea: `0x180021ab0`
- end: `0x180022123`
- name: `?Decrypt@?$CEncryption@$0A@V?$CCipherFeistel64@$0BC@$0GD@$0EK@$0OP@$0BE@$0OE@$0CF@$0MC@$0BO@$0FO@$0HK@$0EN@$0BJ@$0HG@$0PI@$0OK@$0BG@$0PH@$0CF@$0JN@$00$03$0N@$0BE@$07$0HP@$07$0NI@$0L@$0BN@$0FB@$0EK@$09$0OH@$0HF@$0BM@$01$0NF@$0ND@$0FG@@WarbirdCrypto@@V?$CHashFunctionSCP@$01$02$0A@$0?BMINLIEJLPHNNHJC@@2@UENCRYPTED_SEGMENT_DATA_CONST_1@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_1@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z`
- size: `1651`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800236a0`

## callees

- `0x1800017b0`
- `0x180021ab0`
- `0x180025230`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<0,WarbirdCrypto::CCipherFeistel64<18,99,74,239,20,228,37,194,30,94,122,77,25,118,248,234,22,247,37,157,1,4,13,20,8,127,8,216,11,29,81,74,10,231,117,28,2,213,211,86>,WarbirdCrypto::CHashFunctionSCP<2,3,0,-2057503231663003538>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_1,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_1>::Decrypt(
        char *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned int a5,
        char a6,
        int a7)
{
  __int64 v7; // rbx
  _BYTE *v8; // rsi
  char *v10; // r15
  volatile unsigned int v11; // ebp
  char *v12; // rdi
  unsigned int v13; // r10d
  signed int v14; // r8d
  signed int v15; // r9d
  unsigned int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // r12d
  unsigned __int64 v19; // r11
  volatile unsigned int i; // r9d
  unsigned int v21; // r8d
  unsigned int v22; // ecx
  char *v23; // r10
  signed __int64 v24; // r8
  char v25; // r11
  int v26; // ecx
  int v27; // r14d
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // r10
  int v30; // r13d
  int v31; // r11d
  int v32; // ebx
  int v33; // r8d
  unsigned int v34; // ecx
  unsigned int v35; // r8d
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  int v39; // r13d
  int v40; // r14d
  char *v41; // r8
  __int64 v42; // rcx
  int v43; // r14d
  __int64 *v44; // r9
  char v45; // al
  char *v46; // r8
  __int64 v47; // rax
  __int64 v48; // r8
  char *v49; // r9
  _BYTE *v50; // r10
  char v51; // al
  int v52; // r15d
  unsigned __int64 v53; // rsi
  int v54; // edi
  int v55; // r12d
  unsigned int v56; // ebp
  int v57; // r11d
  unsigned __int64 v58; // rdx
  __int64 v59; // rax
  int v60; // r10d
  int v61; // r11d
  unsigned int v62; // r9d
  unsigned int v63; // r10d
  int v64; // r11d
  int v65; // r9d
  int v66; // r10d
  int v67; // r11d
  int v68; // r9d
  _QWORD *v69; // r8
  char *v70; // r10
  unsigned int v71; // r8d
  unsigned int v72; // ecx
  char *v73; // r9
  signed __int64 v74; // r8
  unsigned int v75; // [rsp+20h] [rbp-D8h]
  int v76; // [rsp+20h] [rbp-D8h]
  __int64 v77; // [rsp+28h] [rbp-D0h] BYREF
  unsigned int v78; // [rsp+30h] [rbp-C8h]
  __int64 v79; // [rsp+38h] [rbp-C0h] BYREF
  unsigned __int64 v80; // [rsp+40h] [rbp-B8h]
  int v81; // [rsp+48h] [rbp-B0h]
  volatile unsigned int v82; // [rsp+4Ch] [rbp-ACh]
  unsigned int v83; // [rsp+50h] [rbp-A8h]
  unsigned __int64 v84; // [rsp+58h] [rbp-A0h]
  unsigned __int64 v85; // [rsp+60h] [rbp-98h]
  _QWORD *v86; // [rsp+68h] [rbp-90h]
  __int64 *v87; // [rsp+70h] [rbp-88h]
  char *v88; // [rsp+78h] [rbp-80h]
  unsigned __int64 v89; // [rsp+80h] [rbp-78h]
  _BYTE *v90; // [rsp+90h] [rbp-68h]
  char *v91; // [rsp+98h] [rbp-60h]

  v7 = 0;
  v8 = a2;
  v10 = a1;
  v80 = a4;
  v89 = a3;
  v90 = a2;
  v91 = a1;
  if ( a7 )
  {
    v11 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v12 = (char *)&_ImageBase + WarbirdRuntime::g_PrivateRelocationsTable;
    v13 = (_DWORD)a1 - (unsigned int)&_ImageBase;
    v88 = v12;
    v82 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v14 = 0;
    v15 = WarbirdRuntime::g_PrivateRelocationsTableCount - 1;
    while ( v15 >= v14 )
    {
      v16 = (v15 + v14) / 2;
      v78 = v16;
      v17 = *(_DWORD *)&v12[4 * v16] & 0xFFFFFFF;
      if ( v13 >= v17 )
      {
        if ( v13 <= v17 )
          goto LABEL_9;
        v14 = v16 + 1;
      }
      else
      {
        v15 = v16 - 1;
      }
    }
    v16 = v14;
    v78 = v14;
LABEL_9:
    v18 = a3 + v13;
    v83 = a3 + v13;
    v19 = WarbirdRuntime::g_preferedImageBase - (_QWORD)&_ImageBase;
    for ( i = v16; i < v11; ++i )
    {
      v21 = *(_DWORD *)&v12[4 * i];
      if ( (v21 & 0xFFFFFFF) >= v18 )
        break;
      v22 = v21 >> 28;
      if ( v21 >> 28 )
      {
        v23 = (char *)&_ImageBase + (v21 & 0xFFFFFFF);
        v24 = v23 - v10;
        if ( v22 == 3 )
        {
          *(_DWORD *)&v8[v24] = v19 + *(_DWORD *)v23;
        }
        else if ( v22 == 10 )
        {
          *(_QWORD *)&v8[v24] = v19 + *(_QWORD *)v23;
        }
      }
    }
    a4 = v80;
  }
  else
  {
    v18 = v79;
    v12 = 0;
    v16 = v79;
    v11 = 0;
    v83 = v79;
    v78 = v79;
    v88 = 0;
    v82 = 0;
  }
  v25 = 0;
  if ( a3 )
  {
    v75 = a3 & 7;
    v26 = ~a5;
    v77 = 0;
    if ( (a3 & 7) != 0 )
    {
      v31 = WORD1(a4);
      v32 = (unsigned __int16)a4;
      v86 = (_QWORD *)(a4 >> 16);
      v84 = HIDWORD(a4);
      v33 = v26 ^ (a5 >> 2) ^ (WORD1(a4) * (a5 ^ WORD2(a4)));
      LODWORD(a4) = a5 ^ ((unsigned __int16)a4 * __ROL4__(WORD1(a4) ^ v33, 6) - __ROR4__(v33, 29));
      v85 = HIWORD(v80);
      v34 = v33 ^ __ROR4__(a4, 13) ^ (HIWORD(v80) * __ROL4__(WORD2(a4) ^ (unsigned int)a4, 5));
      v35 = a4 ^ (v34 >> 7) ^ (WORD2(a4) * __ROL4__(v34 - v32, 2));
      LODWORD(a4) = v34 ^ (v31 * (v35 - HIWORD(v80)) - (v35 >> 14));
      v36 = v35 ^ (v32 * __ROR4__(a4 - v84, 7) - __ROR4__(a4, 3));
      v37 = a4 ^ (WORD2(a4) * (__ROR4__(v36, 14) - HIWORD(v80)));
      v38 = v36 ^ (v37 - v80 - WORD2(a4));
      v39 = v37 ^ __ROR4__(v38, 9) ^ (v31 * __ROR4__(v84 ^ v38, 7));
      v40 = v32 * __ROR4__(v39 - v84, 13);
      v7 = v75;
      v41 = v10;
      v42 = v75;
      v79 = 0;
      v43 = v38 ^ __ROR4__(v39, 23) ^ v40;
      v44 = &v79;
      do
      {
        v45 = *v41++;
        *(_BYTE *)v44 = v45;
        v44 = (__int64 *)((char *)v44 + 1);
        --v42;
      }
      while ( v42 );
      v26 = v79;
      v46 = (char *)&v77 + v75;
      a5 = HIDWORD(v79);
      HIDWORD(v77) = HIDWORD(v79) ^ v43;
      LODWORD(v77) = v79 ^ v39;
      v47 = 8LL - v75;
      do
      {
        *v46++ = 0;
        --v47;
      }
      while ( v47 );
      v27 = HIDWORD(v77);
      v30 = v77;
      v48 = v75;
      v49 = (char *)&v77;
      v50 = v8;
      do
      {
        v51 = *v49++;
        *v50++ = v51;
        --v48;
      }
      while ( v48 );
      LOWORD(v29) = (_WORD)v86;
      LOWORD(a4) = v80;
      LOWORD(v28) = v84;
    }
    else
    {
      v27 = HIDWORD(v77);
      v28 = HIDWORD(a4);
      v29 = a4 >> 16;
      v30 = 0;
      v85 = HIWORD(a4);
      v84 = HIDWORD(a4);
    }
    v87 = (__int64 *)&v10[v7];
    v86 = &v8[v7];
    if ( v89 >> 3 )
    {
      v52 = v80;
      v53 = 0;
      v54 = v84;
      v55 = v85;
      v56 = a5;
      v57 = (unsigned __int16)v29;
      LODWORD(v79) = (unsigned __int16)v28;
      v58 = v89 >> 3;
      v76 = (unsigned __int16)a4;
      v81 = (unsigned __int16)v29;
      do
      {
        v59 = *v87++;
        v60 = v30 ^ v59 ^ (((unsigned int)v27 ^ HIDWORD(v59)) >> 2) ^ (v57 * (v79 ^ v27 ^ HIDWORD(v59)));
        v61 = v27 ^ HIDWORD(v59) ^ (v76 * __ROL4__(v60 ^ v57, 6) - __ROR4__(v60, 29));
        v62 = v60 ^ __ROR4__(v61, 13) ^ (v55 * __ROL4__(v61 ^ v79, 5));
        v63 = v61 ^ (v62 >> 7) ^ (v79 * __ROL4__(v62 - v76, 2));
        v64 = v62 ^ (v81 * (v63 - v55) - (v63 >> 14));
        v65 = v63 ^ (v76 * __ROR4__(v64 - v54, 7) - __ROR4__(v64, 3));
        v66 = v64 ^ (v79 * (__ROR4__(v65, 14) - v55));
        v67 = v65 ^ (v66 - v79 - v52);
        v68 = v66 ^ __ROR4__(v67, 9) ^ (v81 * __ROR4__(v67 ^ v54, 7));
        v30 = v68 ^ v26;
        LODWORD(v77) = v68 ^ v26;
        v69 = v86;
        v27 = v67 ^ v56 ^ __ROR4__(v68, 23) ^ (v76 * __ROR4__(v68 - v54, 13));
        v26 = v59;
        v57 = v81;
        ++v53;
        HIDWORD(v77) = v27;
        v56 = HIDWORD(v59);
        *v86 = v77;
        v86 = v69 + 1;
      }
      while ( v53 < v58 );
      v16 = v78;
      v12 = v88;
      v8 = v90;
      v11 = v82;
      v10 = v91;
      v18 = v83;
    }
    v25 = v8[v89 - 1];
  }
  if ( a7 )
  {
    v70 = (char *)&_ImageBase - WarbirdRuntime::g_preferedImageBase;
    while ( v16 < v11 )
    {
      v71 = *(_DWORD *)&v12[4 * v16];
      if ( (v71 & 0xFFFFFFF) >= v18 )
        break;
      ++v16;
      v72 = v71 >> 28;
      if ( v71 >> 28 )
      {
        v73 = (char *)&_ImageBase + (v71 & 0xFFFFFFF);
        v74 = v73 - v10;
        if ( v72 == 3 )
        {
          *(_DWORD *)&v8[v74] = (_DWORD)v70 + *(_DWORD *)v73;
        }
        else if ( v72 == 10 )
        {
          *(_QWORD *)&v8[v74] = &v70[*(_QWORD *)v73];
        }
      }
    }
  }
  if ( v25 != a6 )
    WarbirdRuntime::CTermination::TrashStack();
}

```

## disassembly

```asm
0x180021ab0  mov     r11, rsp
0x180021ab3  sub     rsp, 0F8h
0x180021aba  mov     rax, cs:__security_cookie
0x180021ac1  xor     rax, rsp
0x180021ac4  mov     [rsp+0F8h+var_58], rax
0x180021acc  mov     [r11-8], rbx
0x180021ad0  xor     ebx, ebx
0x180021ad2  mov     [r11-10h], rbp
0x180021ad6  mov     [r11-18h], rsi
0x180021ada  mov     rsi, rdx
0x180021add  mov     [r11-20h], rdi
0x180021ae1  mov     [r11-28h], r12
0x180021ae5  mov     [r11-30h], r13
0x180021ae9  lea     r13, __ImageBase
0x180021af0  mov     [r11-38h], r14
0x180021af4  mov     r14, r8
0x180021af7  mov     [r11-40h], r15
0x180021afb  mov     r15, rcx
0x180021afe  mov     [rsp+0F8h+var_B8], r9
0x180021b03  mov     [rsp+0F8h+var_78], r8
0x180021b0b  mov     [rsp+0F8h+var_68], rdx
0x180021b13  mov     [rsp+0F8h+var_60], rcx
0x180021b1b  cmp     [rsp+0F8h+arg_30], ebx
0x180021b22  jz      loc_180021BFA
0x180021b28  mov     edi, cs:?g_PrivateRelocationsTable@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTable
0x180021b2e  mov     r10d, r15d
0x180021b31  mov     ebp, cs:?g_PrivateRelocationsTableCount@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTableCount
0x180021b37  add     rdi, r13
0x180021b3a  sub     r10d, r13d
0x180021b3d  mov     [rsp+0F8h+var_80], rdi
0x180021b42  mov     [rsp+0F8h+var_AC], ebp
0x180021b46  mov     r8d, ebx
0x180021b49  lea     r9d, [rbp-1]
0x180021b4d  test    r9d, r9d
0x180021b50  js      short loc_180021B84
0x180021b52  lea     edx, [r9+r8]
0x180021b56  test    edx, edx
0x180021b58  jns     short loc_180021B5C
0x180021b5a  inc     edx
0x180021b5c  sar     edx, 1
0x180021b5e  movsxd  rax, edx
0x180021b61  mov     [rsp+0F8h+var_C8], edx
0x180021b65  mov     ecx, [rdi+rax*4]
0x180021b68  and     ecx, 0FFFFFFFh
0x180021b6e  cmp     r10d, ecx
0x180021b71  jnb     short loc_180021B79
0x180021b73  lea     r9d, [rdx-1]
0x180021b77  jmp     short loc_180021B7F
0x180021b79  jbe     short loc_180021B8B
0x180021b7b  lea     r8d, [rdx+1]
0x180021b7f  cmp     r9d, r8d
0x180021b82  jge     short loc_180021B52
0x180021b84  mov     edx, r8d
0x180021b87  mov     [rsp+0F8h+var_C8], edx
0x180021b8b  mov     r11, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x180021b92  lea     r12d, [r14+r10]
0x180021b96  mov     [rsp+0F8h+var_A8], r12d
0x180021b9b  sub     r11, r13
0x180021b9e  mov     r9d, edx
0x180021ba1  cmp     r9d, ebp
0x180021ba4  jnb     short loc_180021C1C
0x180021ba6  mov     eax, r9d
0x180021ba9  mov     r8d, [rdi+rax*4]
0x180021bad  mov     eax, r8d
0x180021bb0  and     eax, 0FFFFFFFh
0x180021bb5  cmp     eax, r12d
0x180021bb8  jnb     short loc_180021C1C
0x180021bba  mov     ecx, r8d
0x180021bbd  inc     r9d
0x180021bc0  shr     ecx, 1Ch
0x180021bc3  test    ecx, ecx
0x180021bc5  jz      short loc_180021BA1
0x180021bc7  and     r8d, 0FFFFFFFh
0x180021bce  lea     r10, [r8+r13]
0x180021bd2  mov     r8, r10
0x180021bd5  sub     r8, r15
0x180021bd8  cmp     ecx, 3
0x180021bdb  jz      short loc_180021BEE
0x180021bdd  cmp     ecx, 0Ah
0x180021be0  jnz     short loc_180021BA1
0x180021be2  mov     rcx, [r10]
0x180021be5  add     rcx, r11
0x180021be8  mov     [r8+rsi], rcx
0x180021bec  jmp     short loc_180021BA1
0x180021bee  mov     ecx, [r10]
0x180021bf1  add     ecx, r11d
0x180021bf4  mov     [r8+rsi], ecx
0x180021bf8  jmp     short loc_180021BA1
0x180021bfa  mov     r12d, dword ptr [rsp+0F8h+var_C0]
0x180021bff  mov     rdi, rbx
0x180021c02  mov     edx, dword ptr [rsp+0F8h+var_C0]
0x180021c06  mov     ebp, ebx
0x180021c08  mov     [rsp+0F8h+var_A8], r12d
0x180021c0d  mov     [rsp+0F8h+var_C8], edx
0x180021c11  mov     [rsp+0F8h+var_80], rbx
0x180021c16  mov     [rsp+0F8h+var_AC], ebx
0x180021c1a  jmp     short loc_180021C21
0x180021c1c  mov     r9, [rsp+0F8h+var_B8]
0x180021c21  xor     r11b, r11b
0x180021c24  mov     eax, r14d
0x180021c27  test    r14, r14
0x180021c2a  jz      loc_18002204E
0x180021c30  mov     r14d, [rsp+0F8h+arg_20]
0x180021c38  and     eax, 7
0x180021c3b  mov     ecx, r14d
0x180021c3e  mov     [rsp+0F8h+var_D8], eax
0x180021c42  not     ecx
0x180021c44  mov     [rsp+0F8h+var_D0], rbx
0x180021c49  mov     rax, r9
0x180021c4c  jnz     short loc_180021C77
0x180021c4e  mov     r14d, dword ptr [rsp+0F8h+var_D0+4]
0x180021c53  mov     r10, r9
0x180021c56  shr     rax, 20h
0x180021c5a  mov     r8, r9
0x180021c5d  shr     r10, 10h
0x180021c61  mov     r13d, ebx
0x180021c64  shr     r8, 30h
0x180021c68  mov     [rsp+0F8h+var_98], r8
0x180021c6d  mov     [rsp+0F8h+var_A0], rax
0x180021c72  jmp     loc_180021E5C
0x180021c77  shr     rax, 10h
0x180021c7b  mov     r13, r9
0x180021c7e  movzx   r11d, ax
0x180021c82  movzx   ebx, r9w
0x180021c86  mov     [rsp+0F8h+var_90], rax
0x180021c8b  mov     eax, r14d
0x180021c8e  shr     eax, 2
0x180021c91  shr     r13, 20h
0x180021c95  movzx   r10d, r13w
0x180021c99  mov     [rsp+0F8h+var_A0], r13
0x180021c9e  mov     r8d, r10d
0x180021ca1  xor     r8d, r14d
0x180021ca4  imul    r8d, r11d
0x180021ca8  xor     r8d, eax
0x180021cab  xor     r8d, ecx
0x180021cae  mov     eax, r8d
0x180021cb1  mov     r9d, r8d
0x180021cb4  ror     eax, 1Dh
0x180021cb7  xor     r9d, r11d
0x180021cba  rol     r9d, 6
0x180021cbe  imul    r9d, ebx
0x180021cc2  sub     r9d, eax
0x180021cc5  xor     r9d, r14d
0x180021cc8  mov     r14, [rsp+0F8h+var_B8]
0x180021ccd  mov     ecx, r9d
0x180021cd0  mov     rax, r14
0x180021cd3  shr     rax, 30h
0x180021cd7  xor     ecx, r10d
0x180021cda  mov     [rsp+0F8h+var_98], rax
0x180021cdf  rol     ecx, 5
0x180021ce2  imul    ecx, eax
0x180021ce5  mov     eax, r9d
0x180021ce8  ror     eax, 0Dh
0x180021ceb  xor     ecx, eax
0x180021ced  xor     ecx, r8d
0x180021cf0  mov     r8d, ecx
0x180021cf3  mov     eax, ecx
0x180021cf5  sub     r8d, ebx
0x180021cf8  shr     eax, 7
0x180021cfb  rol     r8d, 2
0x180021cff  imul    r8d, r10d
0x180021d03  xor     r8d, eax
0x180021d06  xor     r8d, r9d
0x180021d09  mov     r9d, r8d
0x180021d0c  mov     eax, r8d
0x180021d0f  sub     r9d, dword ptr [rsp+0F8h+var_98]
0x180021d14  imul    r9d, r11d
0x180021d18  shr     eax, 0Eh
0x180021d1b  sub     r9d, eax
0x180021d1e  xor     r9d, ecx
0x180021d21  mov     ecx, r9d
0x180021d24  mov     eax, r9d
0x180021d27  sub     ecx, r13d
0x180021d2a  ror     eax, 3
0x180021d2d  ror     ecx, 7
0x180021d30  imul    ecx, ebx
0x180021d33  sub     ecx, eax
0x180021d35  xor     ecx, r8d
0x180021d38  mov     r8d, ecx
0x180021d3b  ror     r8d, 0Eh
0x180021d3f  sub     r8d, dword ptr [rsp+0F8h+var_98]
0x180021d44  imul    r8d, r10d
0x180021d48  xor     r8d, r9d
0x180021d4b  mov     r9d, r8d
0x180021d4e  sub     r9d, r14d
0x180021d51  sub     r9d, r10d
0x180021d54  xor     r9d, ecx
0x180021d57  mov     rcx, [rsp+0F8h+var_A0]
0x180021d5c  mov     r13d, r9d
0x180021d5f  mov     eax, r9d
0x180021d62  xor     r13d, ecx
0x180021d65  ror     eax, 9
0x180021d68  ror     r13d, 7
0x180021d6c  imul    r13d, r11d
0x180021d70  xor     r13d, eax
0x180021d73  xor     r13d, r8d
0x180021d76  mov     r14d, r13d
0x180021d79  mov     eax, r13d
0x180021d7c  sub     r14d, ecx
0x180021d7f  ror     r14d, 0Dh
0x180021d83  imul    r14d, ebx
0x180021d87  mov     ebx, [rsp+0F8h+var_D8]
0x180021d8b  mov     r8, r15
0x180021d8e  ror     eax, 17h
0x180021d91  mov     ecx, ebx
0x180021d93  xor     r14d, eax
0x180021d96  mov     [rsp+0F8h+var_C0], 0
0x180021d9f  xor     r14d, r9d
0x180021da2  lea     r9, [rsp+0F8h+var_C0]
0x180021da7  nop     word ptr [rax+rax+00000000h]
0x180021db0  movzx   eax, byte ptr [r8]
0x180021db4  lea     r8, [r8+1]
0x180021db8  mov     [r9], al
0x180021dbb  lea     r9, [r9+1]
0x180021dbf  sub     rcx, 1
0x180021dc3  jnz     short loc_180021DB0
0x180021dc5  mov     eax, dword ptr [rsp+0F8h+var_C0+4]
0x180021dc9  lea     r8, [rsp+0F8h+var_D0]
0x180021dce  mov     rcx, [rsp+0F8h+var_C0]
0x180021dd3  lea     r8, [r8+rbx]
0x180021dd7  xor     r14d, eax
0x180021dda  mov     [rsp+0F8h+arg_20], eax
0x180021de1  xor     r13d, ecx
0x180021de4  mov     dword ptr [rsp+0F8h+var_D0+4], r14d
0x180021de9  mov     eax, 8
0x180021dee  mov     dword ptr [rsp+0F8h+var_D0], r13d
0x180021df3  sub     rax, rbx
0x180021df6  jz      short loc_180021E18
0x180021df8  nop     dword ptr [rax+rax+00000000h]
0x180021e00  mov     byte ptr [r8], 0
0x180021e04  lea     r8, [r8+1]
0x180021e08  sub     rax, 1
0x180021e0c  jnz     short loc_180021E00
0x180021e0e  mov     r14d, dword ptr [rsp+0F8h+var_D0+4]
0x180021e13  mov     r13d, dword ptr [rsp+0F8h+var_D0]
0x180021e18  mov     r8, rbx
0x180021e1b  lea     r9, [rsp+0F8h+var_D0]
0x180021e20  mov     r10, rsi
0x180021e23  nop     dword ptr [rax+00h]
0x180021e27  nop     word ptr [rax+rax+00000000h]
0x180021e30  movzx   eax, byte ptr [r9]
0x180021e34  lea     r9, [r9+1]
0x180021e38  mov     [r10], al
0x180021e3b  lea     r10, [r10+1]
0x180021e3f  sub     r8, 1
0x180021e43  jnz     short loc_180021E30
0x180021e45  mov     rax, [rsp+0F8h+var_B8]
0x180021e4a  mov     r10, [rsp+0F8h+var_90]
0x180021e4f  mov     r9, rax
0x180021e52  mov     [rsp+0F8h+var_B8], rax
0x180021e57  mov     rax, [rsp+0F8h+var_A0]
0x180021e5c  lea     r8, [rbx+r15]
0x180021e60  mov     [rsp+0F8h+var_88], r8
0x180021e65  lea     r11, [rbx+rsi]
0x180021e69  mov     r8, [rsp+0F8h+var_78]
0x180021e71  shr     r8, 3
0x180021e75  mov     [rsp+0F8h+var_90], r11
0x180021e7a  test    r8, r8
0x180021e7d  jz      loc_180022039
0x180021e83  mov     r15, [rsp+0F8h+var_B8]
0x180021e88  xor     esi, esi
0x180021e8a  mov     rdi, [rsp+0F8h+var_A0]
0x180021e8f  mov     r12, [rsp+0F8h+var_98]
0x180021e94  mov     ebp, [rsp+0F8h+arg_20]
0x180021e9b  movzx   edx, ax
0x180021e9e  movzx   eax, r9w
0x180021ea2  movzx   r11d, r10w
0x180021ea6  mov     dword ptr [rsp+0F8h+var_C0], edx
0x180021eaa  mov     rdx, r8
0x180021ead  mov     [rsp+0F8h+var_D8], eax
0x180021eb1  mov     [rsp+0F8h+var_B0], r11d
0x180021eb6  nop     word ptr [rax+rax+00000000h]
0x180021ec0  mov     r8, [rsp+0F8h+var_88]
0x180021ec5  mov     rax, [r8]
0x180021ec8  add     r8, 8
0x180021ecc  mov     [rsp+0F8h+var_88], r8
0x180021ed1  mov     rbx, rax
0x180021ed4  shr     rbx, 20h
0x180021ed8  mov     r9d, ebx
0x180021edb  xor     r9d, r14d
0x180021ede  mov     r14d, dword ptr [rsp+0F8h+var_C0]
0x180021ee3  mov     r10d, r9d
0x180021ee6  mov     r8d, r9d
0x180021ee9  xor     r10d, r14d
0x180021eec  shr     r8d, 2
0x180021ef0  imul    r10d, r11d
0x180021ef4  xor     r10d, r8d
0x180021ef7  xor     r10d, eax
0x180021efa  xor     r10d, r13d
0x180021efd  mov     r13d, ecx
0x180021f00  xor     r11d, r10d
0x180021f03  mov     r8d, r10d
0x180021f06  rol     r11d, 6
0x180021f0a  imul    r11d, [rsp+0F8h+var_D8]
0x180021f10  ror     r8d, 1Dh
0x180021f14  sub     r11d, r8d
0x180021f17  xor     r11d, r9d
0x180021f1a  mov     r9d, r14d
0x180021f1d  xor     r9d, r11d
0x180021f20  mov     r8d, r11d
  ... truncated ...
```
