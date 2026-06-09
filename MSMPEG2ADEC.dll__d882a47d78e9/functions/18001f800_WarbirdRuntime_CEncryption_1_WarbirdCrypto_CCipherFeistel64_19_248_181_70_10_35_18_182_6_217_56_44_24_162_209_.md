# WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)

- ea: `0x18001f800`
- end: `0x18001fe82`
- name: `?Decrypt@?$CEncryption@$00V?$CCipherFeistel64@$0BD@$0PI@$0LF@$0EG@$09$0CD@$0BC@$0LG@$05$0NJ@$0DI@$0CM@$0BI@$0KC@$0NB@$0JF@$0BA@$0NF@$0NO@$0LH@$0BE@$0CD@$0DD@$0CI@$0BN@$0IL@$0HD@$0NF@$0M@$0OE@$0BK@$0PN@$03$0FI@$0HI@$0DF@$0BF@$0OF@$0CP@$0OD@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$0A@$0A@$0ENFLKLIPNEIOMFLN@@2@UENCRYPTED_SEGMENT_DATA_CONST_2@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_2@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z`
- size: `1666`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022470`

## callees

- `0x1800017b0`
- `0x18001f800`
- `0x180025230`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<1,WarbirdCrypto::CCipherFeistel64<19,248,181,70,10,35,18,182,6,217,56,44,24,162,209,149,16,213,222,183,20,35,51,40,29,139,115,213,12,228,26,253,4,88,120,53,21,229,47,227>,WarbirdCrypto::CHashFunctionSCP<1,0,0,5574237598035920317>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_2,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_2>::Decrypt(
        char *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        char a6,
        int a7)
{
  __int64 v7; // rbx
  _BYTE *v8; // rbp
  char *v10; // r12
  volatile unsigned int v12; // r15d
  char *v13; // rsi
  unsigned int v14; // r10d
  signed int v15; // r8d
  signed int v16; // r9d
  unsigned int v17; // edx
  unsigned int v18; // ecx
  unsigned int v19; // r13d
  unsigned __int64 v20; // r11
  volatile unsigned int i; // r9d
  unsigned int v22; // r8d
  unsigned int v23; // ecx
  char *v24; // r10
  signed __int64 v25; // r8
  char v26; // r11
  unsigned __int16 v27; // r9
  int v28; // ecx
  int v29; // r14d
  unsigned __int64 v30; // rax
  int v31; // r9d
  int v32; // r8d
  int v33; // ecx
  int v34; // r9d
  int v35; // r8d
  int v36; // ecx
  unsigned int v37; // r9d
  int v38; // r8d
  int v39; // r10d
  int v40; // r14d
  __int64 *v41; // r9
  __int64 v42; // rcx
  char *v43; // r8
  char v44; // al
  _BYTE *v45; // r8
  __int64 v46; // rax
  __int64 v47; // r8
  char *v48; // r9
  _BYTE *v49; // r10
  char v50; // al
  __int64 *v51; // r10
  int v52; // r13d
  unsigned __int64 v53; // rsi
  int v54; // r12d
  int v55; // ebp
  int v56; // r15d
  _QWORD *v57; // rdx
  int v58; // ebx
  __int64 v59; // rax
  int v60; // r11d
  int v61; // r9d
  int v62; // r10d
  int v63; // r11d
  int v64; // r9d
  int v65; // r10d
  unsigned int v66; // r11d
  int v67; // ebx
  int v68; // r9d
  _QWORD *v69; // r8
  int v70; // r14d
  char *v71; // r10
  unsigned int v72; // r8d
  unsigned int v73; // ecx
  char *v74; // r9
  signed __int64 v75; // r8
  char v76; // [rsp+20h] [rbp-C8h]
  _BYTE v77[12]; // [rsp+24h] [rbp-C4h] BYREF
  int v78; // [rsp+30h] [rbp-B8h]
  unsigned int v79; // [rsp+34h] [rbp-B4h]
  __int64 v80; // [rsp+38h] [rbp-B0h] BYREF
  unsigned __int64 v81; // [rsp+40h] [rbp-A8h]
  volatile unsigned int v82; // [rsp+48h] [rbp-A0h]
  unsigned int v83; // [rsp+4Ch] [rbp-9Ch]
  _QWORD *v84; // [rsp+50h] [rbp-98h]
  unsigned __int64 v85; // [rsp+58h] [rbp-90h]
  _QWORD *v86; // [rsp+60h] [rbp-88h]
  unsigned __int64 v87; // [rsp+68h] [rbp-80h]
  char *v88; // [rsp+70h] [rbp-78h]
  unsigned __int64 v89; // [rsp+78h] [rbp-70h]
  _BYTE *v90; // [rsp+80h] [rbp-68h]
  char *v91; // [rsp+88h] [rbp-60h]

  v7 = 0;
  v8 = a2;
  v10 = a1;
  v91 = a1;
  v87 = a4;
  v89 = a3;
  v90 = a2;
  if ( a7 )
  {
    v12 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v13 = (char *)&_ImageBase + WarbirdRuntime::g_PrivateRelocationsTable;
    v14 = (_DWORD)a1 - (unsigned int)&_ImageBase;
    v88 = v13;
    v82 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v15 = 0;
    v16 = WarbirdRuntime::g_PrivateRelocationsTableCount - 1;
    while ( v16 >= v15 )
    {
      v17 = (v16 + v15) / 2;
      v79 = v17;
      v18 = *(_DWORD *)&v13[4 * v17] & 0xFFFFFFF;
      if ( v14 >= v18 )
      {
        if ( v14 <= v18 )
          goto LABEL_9;
        v15 = v17 + 1;
      }
      else
      {
        v16 = v17 - 1;
      }
    }
    v17 = v15;
    v79 = v15;
LABEL_9:
    v19 = a3 + v14;
    v83 = a3 + v14;
    v20 = WarbirdRuntime::g_preferedImageBase - (_QWORD)&_ImageBase;
    for ( i = v17; i < v12; ++i )
    {
      v22 = *(_DWORD *)&v13[4 * i];
      if ( (v22 & 0xFFFFFFF) >= v19 )
        break;
      v23 = v22 >> 28;
      if ( v22 >> 28 )
      {
        v24 = (char *)&_ImageBase + (v22 & 0xFFFFFFF);
        v25 = v24 - v10;
        if ( v23 == 3 )
        {
          *(_DWORD *)&v8[v25] = v20 + *(_DWORD *)v24;
        }
        else if ( v23 == 10 )
        {
          *(_QWORD *)&v8[v25] = v20 + *(_QWORD *)v24;
        }
      }
    }
  }
  else
  {
    v19 = v80;
    v13 = 0;
    v17 = v80;
    v12 = 0;
    v83 = v80;
    v79 = v80;
    v88 = 0;
    v82 = 0;
  }
  v26 = 0;
  v76 = 0;
  if ( a3 )
  {
    *(_DWORD *)&v77[8] = 0;
    *(_QWORD *)v77 = a3 & 7;
    v27 = a4;
    v28 = ~a5;
    if ( *(_DWORD *)v77 )
    {
      v81 = HIDWORD(a4);
      v84 = (_QWORD *)(a4 >> 16);
      v31 = v28 ^ (__ROR4__(a5, 11) + WORD1(a4) * __ROR4__(a5 - HIDWORD(a4), 17));
      v32 = a5 ^ ((unsigned __int16)a4 * (v31 ^ WORD2(a4)) - __ROR4__(v31, 1));
      v85 = HIWORD(a4);
      v33 = v31 ^ (__ROR4__(v32, 6) + HIWORD(a4) * __ROR4__(a4 + v32, 27));
      v34 = v32 ^ a4 ^ (v33 - WORD2(a4));
      v35 = v33 ^ __ROR4__(v34, 10) ^ (WORD1(a4) * __ROR4__(HIDWORD(a4) ^ v34, 21));
      v36 = v34 ^ ((unsigned __int16)a4 * __ROR4__(HIDWORD(a4) - v35, 6) - __ROR4__(v35, 29));
      v37 = v35 ^ (WORD2(a4) * (HIWORD(a4) + __ROR4__(~v36, 13)));
      v38 = v36 ^ ((v37 >> 15) + WORD2(a4) * __ROL4__((unsigned __int16)a4 ^ v37, 1));
      v39 = v37 ^ (WORD1(a4) * __ROL4__((unsigned __int16)a4 ^ v38, 5) - __ROR4__(v38, 28));
      v40 = v38 ^ __ROR4__(v39, 9) ^ ((unsigned __int16)a4 * __ROR4__(HIDWORD(a4) - v39, 27));
      v7 = *(unsigned int *)v77;
      v41 = &v80;
      v42 = *(unsigned int *)v77;
      v80 = 0;
      v43 = v10;
      do
      {
        v44 = *v43++;
        *(_BYTE *)v41 = v44;
        v41 = (__int64 *)((char *)v41 + 1);
        --v42;
      }
      while ( v42 );
      v28 = v80;
      v45 = &v77[*(unsigned int *)v77 + 4];
      a5 = HIDWORD(v80);
      *(_DWORD *)&v77[8] = HIDWORD(v80) ^ v40;
      *(_DWORD *)&v77[4] = v80 ^ v39;
      v46 = 8LL - *(unsigned int *)v77;
      do
      {
        *v45++ = 0;
        --v46;
      }
      while ( v46 );
      v29 = *(_DWORD *)&v77[8];
      *(_DWORD *)v77 = *(_DWORD *)&v77[4];
      v47 = v7;
      v48 = &v77[4];
      v49 = v8;
      do
      {
        v50 = *v48++;
        *v49++ = v50;
        --v47;
      }
      while ( v47 );
      LOWORD(v30) = (_WORD)v84;
      v27 = a4;
      v87 = a4;
    }
    else
    {
      v29 = *(_DWORD *)&v77[8];
      v81 = HIDWORD(a4);
      v30 = a4 >> 16;
      v85 = HIWORD(a4);
      *(_DWORD *)v77 = 0;
    }
    v84 = &v8[v7];
    v51 = (__int64 *)&v10[v7];
    v86 = (_QWORD *)(v89 >> 3);
    if ( v89 >> 3 )
    {
      v52 = v81;
      v53 = 0;
      v54 = v87;
      v55 = *(_DWORD *)v77;
      v56 = a5;
      v57 = v86;
      v58 = (unsigned __int16)v30;
      LODWORD(v80) = (unsigned __int16)v81;
      v78 = (unsigned __int16)v30;
      LODWORD(v81) = v27;
      do
      {
        v59 = *v51;
        v86 = v51 + 1;
        v60 = v55 ^ v59 ^ (__ROR4__(v29 ^ HIDWORD(v59), 11) + v58 * __ROR4__((v29 ^ HIDWORD(v59)) - v52, 17));
        v61 = v29 ^ HIDWORD(v59) ^ (v81 * (v60 ^ v80) - __ROR4__(v60, 1));
        v62 = v60 ^ (__ROR4__(v61, 6) + v85 * __ROR4__(v54 + v61, 27));
        v63 = v61 ^ v54 ^ (v62 - v80);
        v64 = v62 ^ __ROR4__(v63, 10) ^ (v78 * __ROR4__(v63 ^ v52, 21));
        v65 = v63 ^ (v81 * __ROR4__(v52 - v64, 6) - __ROR4__(v64, 29));
        v66 = v64 ^ (v80 * (v85 + __ROR4__(~v65, 13)));
        v67 = v65 ^ ((v66 >> 15) + v80 * __ROL4__(v66 ^ v81, 1));
        v68 = v66 ^ (v78 * __ROL4__(v81 ^ v67, 5) - __ROR4__(v67, 28));
        v55 = v68 ^ v28;
        *(_DWORD *)&v77[4] = v68 ^ v28;
        v28 = v59;
        v69 = v84;
        ++v53;
        v51 = v86;
        v70 = v56 ^ __ROR4__(v68, 9) ^ (v81 * __ROR4__(v52 - v68, 27));
        v56 = HIDWORD(v59);
        v29 = v67 ^ v70;
        v58 = v78;
        *(_DWORD *)&v77[8] = v29;
        *v84 = *(_QWORD *)&v77[4];
        v84 = v69 + 1;
      }
      while ( v53 < (unsigned __int64)v57 );
      v17 = v79;
      v13 = v88;
      v8 = v90;
      v12 = v82;
      v10 = v91;
      v19 = v83;
    }
    v26 = v8[v89 - 1];
    v76 = v26;
  }
  if ( a7 )
  {
    v71 = (char *)&_ImageBase - WarbirdRuntime::g_preferedImageBase;
    while ( v17 < v12 )
    {
      v72 = *(_DWORD *)&v13[4 * v17];
      if ( (v72 & 0xFFFFFFF) >= v19 )
        break;
      ++v17;
      v73 = v72 >> 28;
      if ( v72 >> 28 )
      {
        v74 = (char *)&_ImageBase + (v72 & 0xFFFFFFF);
        v75 = v74 - v10;
        if ( v73 == 3 )
        {
          *(_DWORD *)&v8[v75] = (_DWORD)v71 + *(_DWORD *)v74;
        }
        else if ( v73 == 10 )
        {
          *(_QWORD *)&v8[v75] = &v71[*(_QWORD *)v74];
        }
      }
    }
    v26 = v76;
  }
  if ( v26 != a6 )
    WarbirdRuntime::CTermination::TrashStack();
}

```

## disassembly

```asm
0x18001f800  mov     r11, rsp
0x18001f803  sub     rsp, 0E8h
0x18001f80a  mov     rax, cs:__security_cookie
0x18001f811  xor     rax, rsp
0x18001f814  mov     [rsp+0E8h+var_58], rax
0x18001f81c  mov     [r11-8], rbx
0x18001f820  xor     ebx, ebx
0x18001f822  mov     [r11-10h], rbp
0x18001f826  mov     rbp, rdx
0x18001f829  mov     [r11-18h], rsi
0x18001f82d  mov     [r11-20h], rdi
0x18001f831  mov     rdi, r9
0x18001f834  mov     [r11-28h], r12
0x18001f838  mov     r12, rcx
0x18001f83b  mov     [r11-30h], r13
0x18001f83f  mov     [r11-38h], r14
0x18001f843  mov     r14, r8
0x18001f846  mov     [rsp+0E8h+var_60], rcx
0x18001f84e  lea     rcx, __ImageBase
0x18001f855  mov     [r11-40h], r15
0x18001f859  mov     [rsp+0E8h+var_80], r9
0x18001f85e  mov     [rsp+0E8h+var_70], r8
0x18001f863  mov     [rsp+0E8h+var_68], rdx
0x18001f86b  cmp     [rsp+0E8h+arg_30], ebx
0x18001f872  jz      loc_18001F95F
0x18001f878  mov     esi, cs:?g_PrivateRelocationsTable@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTable
0x18001f87e  mov     r10d, r12d
0x18001f881  mov     r15d, cs:?g_PrivateRelocationsTableCount@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTableCount
0x18001f888  add     rsi, rcx
0x18001f88b  sub     r10d, ecx
0x18001f88e  mov     [rsp+0E8h+var_78], rsi
0x18001f893  mov     [rsp+0E8h+var_A0], r15d
0x18001f898  mov     r8d, ebx
0x18001f89b  lea     r9d, [r15-1]
0x18001f89f  test    r9d, r9d
0x18001f8a2  js      short loc_18001F8D6
0x18001f8a4  lea     edx, [r9+r8]
0x18001f8a8  test    edx, edx
0x18001f8aa  jns     short loc_18001F8AE
0x18001f8ac  inc     edx
0x18001f8ae  sar     edx, 1
0x18001f8b0  movsxd  rax, edx
0x18001f8b3  mov     [rsp+0E8h+var_B4], edx
0x18001f8b7  mov     ecx, [rsi+rax*4]
0x18001f8ba  and     ecx, 0FFFFFFFh
0x18001f8c0  cmp     r10d, ecx
0x18001f8c3  jnb     short loc_18001F8CB
0x18001f8c5  lea     r9d, [rdx-1]
0x18001f8c9  jmp     short loc_18001F8D1
0x18001f8cb  jbe     short loc_18001F8DD
0x18001f8cd  lea     r8d, [rdx+1]
0x18001f8d1  cmp     r9d, r8d
0x18001f8d4  jge     short loc_18001F8A4
0x18001f8d6  mov     edx, r8d
0x18001f8d9  mov     [rsp+0E8h+var_B4], edx
0x18001f8dd  mov     r11, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x18001f8e4  lea     r13d, [r14+r10]
0x18001f8e8  lea     r10, __ImageBase
0x18001f8ef  mov     [rsp+0E8h+var_9C], r13d
0x18001f8f4  sub     r11, r10
0x18001f8f7  mov     r9d, edx
0x18001f8fa  jmp     short loc_18001F907
0x18001f900  lea     r10, __ImageBase
0x18001f907  cmp     r9d, r15d
0x18001f90a  jnb     short loc_18001F980
0x18001f90c  mov     eax, r9d
0x18001f90f  mov     r8d, [rsi+rax*4]
0x18001f913  mov     eax, r8d
0x18001f916  and     eax, 0FFFFFFFh
0x18001f91b  cmp     eax, r13d
0x18001f91e  jnb     short loc_18001F980
0x18001f920  mov     ecx, r8d
0x18001f923  inc     r9d
0x18001f926  shr     ecx, 1Ch
0x18001f929  test    ecx, ecx
0x18001f92b  jz      short loc_18001F907
0x18001f92d  and     r8d, 0FFFFFFFh
0x18001f934  add     r10, r8
0x18001f937  mov     r8, r10
0x18001f93a  sub     r8, r12
0x18001f93d  cmp     ecx, 3
0x18001f940  jz      short loc_18001F953
0x18001f942  cmp     ecx, 0Ah
0x18001f945  jnz     short loc_18001F900
0x18001f947  mov     rcx, [r10]
0x18001f94a  add     rcx, r11
0x18001f94d  mov     [r8+rbp], rcx
0x18001f951  jmp     short loc_18001F900
0x18001f953  mov     ecx, [r10]
0x18001f956  add     ecx, r11d
0x18001f959  mov     [r8+rbp], ecx
0x18001f95d  jmp     short loc_18001F900
0x18001f95f  mov     r13d, dword ptr [rsp+0E8h+var_B0]
0x18001f964  mov     rsi, rbx
0x18001f967  mov     edx, dword ptr [rsp+0E8h+var_B0]
0x18001f96b  mov     r15d, ebx
0x18001f96e  mov     [rsp+0E8h+var_9C], r13d
0x18001f973  mov     [rsp+0E8h+var_B4], edx
0x18001f977  mov     [rsp+0E8h+var_78], rbx
0x18001f97c  mov     [rsp+0E8h+var_A0], ebx
0x18001f980  xor     r11b, r11b
0x18001f983  mov     eax, r14d
0x18001f986  mov     [rsp+0E8h+var_C8], r11b
0x18001f98b  test    r14, r14
0x18001f98e  jz      loc_18001FD9F
0x18001f994  and     eax, 7
0x18001f997  mov     [rsp+0E8h+var_C0], rbx
0x18001f99c  mov     [rsp+0E8h+var_C4], eax
0x18001f9a0  mov     r8, rdi
0x18001f9a3  mov     eax, [rsp+0E8h+arg_20]
0x18001f9aa  mov     r9, rdi
0x18001f9ad  mov     ecx, eax
0x18001f9af  not     ecx
0x18001f9b1  jnz     short loc_18001F9E0
0x18001f9b3  mov     r14d, dword ptr [rsp+0E8h+var_C0+4]
0x18001f9b8  mov     rax, rdi
0x18001f9bb  shr     r8, 20h
0x18001f9bf  mov     r10d, ebx
0x18001f9c2  mov     [rsp+0E8h+var_A8], r8
0x18001f9c7  mov     r8, rdi
0x18001f9ca  shr     rax, 10h
0x18001f9ce  shr     r8, 30h
0x18001f9d2  mov     [rsp+0E8h+var_90], r8
0x18001f9d7  mov     [rsp+0E8h+var_C4], ebx
0x18001f9db  jmp     loc_18001FBB2
0x18001f9e0  shr     r8, 20h
0x18001f9e4  movzx   r10d, r8w
0x18001f9e8  mov     r14d, r8d
0x18001f9eb  shr     r9, 10h
0x18001f9ef  movzx   ebx, r9w
0x18001f9f3  mov     [rsp+0E8h+var_A8], r8
0x18001f9f8  mov     [rsp+0E8h+var_98], r9
0x18001f9fd  mov     r9d, eax
0x18001fa00  sub     r9d, r8d
0x18001fa03  ror     eax, 0Bh
0x18001fa06  ror     r9d, 11h
0x18001fa0a  mov     r8d, r10d
0x18001fa0d  imul    r9d, ebx
0x18001fa11  movzx   r11d, di
0x18001fa15  add     r9d, eax
0x18001fa18  xor     r9d, ecx
0x18001fa1b  xor     r8d, r9d
0x18001fa1e  mov     eax, r9d
0x18001fa21  ror     eax, 1
0x18001fa23  imul    r8d, r11d
0x18001fa27  sub     r8d, eax
0x18001fa2a  mov     rax, rdi
0x18001fa2d  xor     r8d, [rsp+0E8h+arg_20]
0x18001fa35  shr     rax, 30h
0x18001fa39  mov     [rsp+0E8h+var_90], rax
0x18001fa3e  lea     ecx, [rdi+r8]
0x18001fa42  ror     ecx, 1Bh
0x18001fa45  imul    ecx, eax
0x18001fa48  mov     eax, r8d
0x18001fa4b  ror     eax, 6
0x18001fa4e  add     ecx, eax
0x18001fa50  xor     ecx, r9d
0x18001fa53  mov     r9d, ecx
0x18001fa56  sub     r9d, r10d
0x18001fa59  xor     r9d, edi
0x18001fa5c  xor     r9d, r8d
0x18001fa5f  mov     r8d, r9d
0x18001fa62  mov     eax, r9d
0x18001fa65  xor     r8d, r14d
0x18001fa68  ror     eax, 0Ah
0x18001fa6b  ror     r8d, 15h
0x18001fa6f  imul    r8d, ebx
0x18001fa73  xor     r8d, eax
0x18001fa76  xor     r8d, ecx
0x18001fa79  mov     ecx, r14d
0x18001fa7c  sub     ecx, r8d
0x18001fa7f  mov     eax, r8d
0x18001fa82  ror     eax, 1Dh
0x18001fa85  ror     ecx, 6
0x18001fa88  imul    ecx, r11d
0x18001fa8c  sub     ecx, eax
0x18001fa8e  xor     ecx, r9d
0x18001fa91  mov     r9d, ecx
0x18001fa94  not     r9d
0x18001fa97  ror     r9d, 0Dh
0x18001fa9b  add     r9d, dword ptr [rsp+0E8h+var_90]
0x18001faa0  imul    r9d, r10d
0x18001faa4  xor     r9d, r8d
0x18001faa7  mov     r8d, r9d
0x18001faaa  mov     eax, r9d
0x18001faad  shr     eax, 0Fh
0x18001fab0  xor     r8d, r11d
0x18001fab3  rol     r8d, 1
0x18001fab6  imul    r8d, r10d
0x18001faba  add     r8d, eax
0x18001fabd  xor     r8d, ecx
0x18001fac0  mov     r10d, r8d
0x18001fac3  mov     eax, r8d
0x18001fac6  xor     r10d, r11d
0x18001fac9  ror     eax, 1Ch
0x18001facc  rol     r10d, 5
0x18001fad0  imul    r10d, ebx
0x18001fad4  sub     r10d, eax
0x18001fad7  xor     r10d, r9d
0x18001fada  sub     r14d, r10d
0x18001fadd  mov     eax, r10d
0x18001fae0  ror     r14d, 1Bh
0x18001fae4  imul    r14d, r11d
0x18001fae8  ror     eax, 9
0x18001faeb  xor     r14d, eax
0x18001faee  xor     r14d, r8d
0x18001faf1  mov     ebx, [rsp+0E8h+var_C4]
0x18001faf5  lea     r9, [rsp+0E8h+var_B0]
0x18001fafa  mov     ecx, ebx
0x18001fafc  mov     [rsp+0E8h+var_B0], 0
0x18001fb05  mov     r8, r12
0x18001fb08  nop     dword ptr [rax+rax+00000000h]
0x18001fb10  movzx   eax, byte ptr [r8]
0x18001fb14  lea     r8, [r8+1]
0x18001fb18  mov     [r9], al
0x18001fb1b  lea     r9, [r9+1]
0x18001fb1f  sub     rcx, 1
0x18001fb23  jnz     short loc_18001FB10
0x18001fb25  mov     eax, dword ptr [rsp+0E8h+var_B0+4]
0x18001fb29  lea     r8, [rsp+0E8h+var_C0]
0x18001fb2e  mov     rcx, [rsp+0E8h+var_B0]
0x18001fb33  lea     r8, [r8+rbx]
0x18001fb37  xor     r14d, eax
0x18001fb3a  mov     [rsp+0E8h+arg_20], eax
0x18001fb41  xor     r10d, ecx
0x18001fb44  mov     dword ptr [rsp+0E8h+var_C0+4], r14d
0x18001fb49  mov     eax, 8
0x18001fb4e  mov     [rsp+0E8h+var_C4], r10d
0x18001fb53  mov     dword ptr [rsp+0E8h+var_C0], r10d
0x18001fb58  sub     rax, rbx
0x18001fb5b  jz      short loc_18001FB7D
0x18001fb5d  nop     dword ptr [rax]
0x18001fb60  mov     byte ptr [r8], 0
0x18001fb64  lea     r8, [r8+1]
0x18001fb68  sub     rax, 1
0x18001fb6c  jnz     short loc_18001FB60
0x18001fb6e  mov     r10d, dword ptr [rsp+0E8h+var_C0]
0x18001fb73  mov     r14d, dword ptr [rsp+0E8h+var_C0+4]
0x18001fb78  mov     [rsp+0E8h+var_C4], r10d
0x18001fb7d  mov     r8, rbx
0x18001fb80  lea     r9, [rsp+0E8h+var_C0]
0x18001fb85  mov     r10, rbp
0x18001fb88  nop     dword ptr [rax+rax+00000000h]
0x18001fb90  movzx   eax, byte ptr [r9]
0x18001fb94  lea     r9, [r9+1]
0x18001fb98  mov     [r10], al
0x18001fb9b  lea     r10, [r10+1]
0x18001fb9f  sub     r8, 1
0x18001fba3  jnz     short loc_18001FB90
0x18001fba5  mov     rax, [rsp+0E8h+var_98]
0x18001fbaa  mov     r9, rdi
0x18001fbad  mov     [rsp+0E8h+var_80], rdi
0x18001fbb2  lea     r8, [rbx+rbp]
0x18001fbb6  mov     [rsp+0E8h+var_98], r8
0x18001fbbb  lea     r10, [rbx+r12]
0x18001fbbf  mov     r8, [rsp+0E8h+var_70]
0x18001fbc4  shr     r8, 3
0x18001fbc8  mov     [rsp+0E8h+var_88], r8
0x18001fbcd  test    r8, r8
0x18001fbd0  jz      loc_18001FD8F
0x18001fbd6  mov     r13, [rsp+0E8h+var_A8]
0x18001fbdb  xor     esi, esi
0x18001fbdd  mov     r12, [rsp+0E8h+var_80]
0x18001fbe2  mov     ebp, [rsp+0E8h+var_C4]
0x18001fbe6  mov     r15d, [rsp+0E8h+arg_20]
0x18001fbee  mov     rdx, [rsp+0E8h+var_88]
0x18001fbf3  movzx   ebx, ax
0x18001fbf6  movzx   eax, r13w
0x18001fbfa  movzx   r8d, r9w
0x18001fbfe  mov     dword ptr [rsp+0E8h+var_B0], eax
0x18001fc02  mov     [rsp+0E8h+var_B8], ebx
0x18001fc06  mov     dword ptr [rsp+0E8h+var_A8], r8d
0x18001fc0b  nop     dword ptr [rax+rax+00h]
0x18001fc10  mov     rax, [r10]
0x18001fc13  add     r10, 8
0x18001fc17  mov     [rsp+0E8h+var_88], r10
0x18001fc1c  mov     rdi, rax
0x18001fc1f  shr     rdi, 20h
0x18001fc23  mov     r10d, edi
0x18001fc26  xor     r10d, r14d
0x18001fc29  mov     r14d, dword ptr [rsp+0E8h+var_B0]
0x18001fc2e  mov     r11d, r10d
0x18001fc31  mov     r8d, r10d
0x18001fc34  sub     r11d, r13d
0x18001fc37  ror     r8d, 0Bh
0x18001fc3b  ror     r11d, 11h
0x18001fc3f  mov     r9d, r14d
0x18001fc42  imul    r11d, ebx
0x18001fc46  mov     rbx, [rsp+0E8h+var_90]
0x18001fc4b  add     r11d, r8d
0x18001fc4e  xor     r11d, eax
0x18001fc51  xor     r11d, ebp
0x18001fc54  mov     ebp, dword ptr [rsp+0E8h+var_A8]
0x18001fc58  xor     r9d, r11d
0x18001fc5b  mov     r8d, r11d
0x18001fc5e  imul    r9d, ebp
0x18001fc62  ror     r8d, 1
0x18001fc65  sub     r9d, r8d
0x18001fc68  xor     r9d, r10d
0x18001fc6b  mov     r8d, r9d
  ... truncated ...
```
