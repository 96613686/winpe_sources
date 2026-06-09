# WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)

- ea: `0x180020640`
- end: `0x180020c8f`
- name: `?Decrypt@?$CEncryption@$03V?$CCipherFeistel64@$0BI@$0EI@$0EG@$0ON@$0BL@$0NO@$0DF@$0NA@$0A@$0OH@$09$0MB@$00$0M@$0HA@$0JA@$05$0MG@$0GL@$0GF@$01$0OL@$0FA@$0LK@$0L@$0JN@$0EI@$0FO@$0BG@$0NO@$0DG@$0CI@$0BC@$0KP@$0CN@$0FG@$0BK@$0HI@$0HI@$0ML@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$02$00$0CCNNJAPCKOHNKCBH@@2@UENCRYPTED_SEGMENT_DATA_CONST_5@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_5@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z`
- size: `1615`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180022bd0`

## callees

- `0x1800017b0`
- `0x180020640`
- `0x180025230`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<4,WarbirdCrypto::CCipherFeistel64<24,72,70,237,27,222,53,208,0,231,10,193,1,12,112,144,6,198,107,101,2,235,80,186,11,157,72,94,22,222,54,40,18,175,45,86,26,120,120,203>,WarbirdCrypto::CHashFunctionSCP<1,3,1,2512323539126559255>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_5,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_5>::Decrypt(
        char *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        char a6,
        int a7)
{
  unsigned __int64 v7; // r10
  __int64 v8; // rbx
  unsigned __int64 v9; // rdi
  char *v10; // r12
  _BYTE *v11; // r14
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
  int v27; // ecx
  int v28; // ebp
  int v29; // r11d
  unsigned __int64 v30; // r8
  int v31; // r11d
  int v32; // ebx
  int v33; // r8d
  int v34; // r9d
  int v35; // ebp
  int v36; // ecx
  unsigned int v37; // r8d
  unsigned int v38; // r9d
  unsigned int v39; // ecx
  int v40; // r8d
  int v41; // r11d
  int v42; // ebp
  __int64 *v43; // r9
  __int64 v44; // rcx
  char *v45; // r8
  char v46; // al
  char *v47; // r8
  __int64 v48; // rax
  __int64 v49; // r8
  char *v50; // r9
  _BYTE *v51; // r10
  char v52; // al
  __int64 *v53; // r9
  int v54; // esi
  unsigned __int64 v55; // r14
  int v56; // r12d
  int v57; // r13d
  _QWORD *v58; // r15
  int v59; // edx
  int v60; // ebx
  __int64 v61; // rax
  int v62; // r10d
  int v63; // r11d
  int v64; // r9d
  unsigned int v65; // ebx
  unsigned int v66; // r10d
  unsigned int v67; // r11d
  unsigned int v68; // r9d
  int v69; // r10d
  int v70; // ebp
  _QWORD *v71; // r8
  char *v72; // r10
  unsigned int v73; // r8d
  unsigned int v74; // ecx
  _DWORD *v75; // r9
  __int64 v76; // r8
  int v77; // [rsp+20h] [rbp-C8h]
  __int64 v78; // [rsp+28h] [rbp-C0h] BYREF
  unsigned int v79; // [rsp+30h] [rbp-B8h]
  unsigned int v80; // [rsp+34h] [rbp-B4h]
  unsigned __int64 v81; // [rsp+38h] [rbp-B0h]
  __int64 v82; // [rsp+40h] [rbp-A8h] BYREF
  volatile unsigned int v83; // [rsp+48h] [rbp-A0h]
  unsigned __int64 v84; // [rsp+50h] [rbp-98h]
  unsigned __int64 v85; // [rsp+58h] [rbp-90h]
  _QWORD *v86; // [rsp+60h] [rbp-88h]
  _QWORD *v87; // [rsp+68h] [rbp-80h]
  char *v88; // [rsp+70h] [rbp-78h]
  unsigned __int64 v89; // [rsp+78h] [rbp-70h]
  _BYTE *v90; // [rsp+80h] [rbp-68h]
  char *v91; // [rsp+88h] [rbp-60h]

  v7 = a4;
  v8 = 0;
  v9 = a3;
  v10 = a1;
  v11 = a2;
  v84 = a4;
  v89 = a3;
  v90 = a2;
  v91 = a1;
  if ( a7 )
  {
    v12 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v13 = (char *)&_ImageBase + WarbirdRuntime::g_PrivateRelocationsTable;
    v14 = (_DWORD)a1 - (unsigned int)&_ImageBase;
    v88 = v13;
    v83 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v15 = 0;
    v16 = WarbirdRuntime::g_PrivateRelocationsTableCount - 1;
    while ( v16 >= v15 )
    {
      v17 = (v16 + v15) / 2;
      v80 = v17;
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
    v80 = v15;
LABEL_9:
    v19 = v9 + v14;
    v79 = v9 + v14;
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
          *(_DWORD *)&v11[v25] = v20 + *(_DWORD *)v24;
        }
        else if ( v23 == 10 )
        {
          *(_QWORD *)&v11[v25] = v20 + *(_QWORD *)v24;
        }
      }
    }
    v7 = v84;
  }
  else
  {
    v19 = v79;
    v13 = 0;
    v12 = 0;
    v17 = v79;
    v80 = v79;
    v88 = 0;
    v83 = 0;
  }
  v26 = 0;
  if ( v9 )
  {
    v27 = ~a5;
    v78 = 0;
    if ( (v9 & 7) != 0 )
    {
      v81 = HIDWORD(v7);
      v31 = WORD1(v7);
      v86 = (_QWORD *)(v7 >> 16);
      v32 = (unsigned __int16)v7;
      v33 = v27 ^ (WORD2(v7) * (WORD1(v7) ^ __ROR4__(a5, 1)));
      v34 = a5 ^ __ROR4__(v33, 25) ^ ((unsigned __int16)v7 * __ROR4__(v33 - HIDWORD(v7), 15));
      v85 = HIWORD(v7);
      v35 = v7;
      v36 = v33 ^ (HIWORD(v7) * __ROR4__(v34 - v7, 24) - __ROR4__(v34, 10));
      LODWORD(v7) = v34 ^ __ROR4__(v36, 2) ^ (WORD2(v7) * __ROL4__((unsigned __int16)v7 ^ v36, 3));
      v37 = v36 ^ ((unsigned int)v7 >> 6) ^ (v31 * (v85 ^ v7));
      v38 = v7 ^ ((v37 >> 12) + v32 * __ROL4__(v31 ^ v37, 3));
      v39 = v37 ^ (v85 * (v38 - v32) - (v38 >> 8));
      v40 = v38 ^ ((v39 >> 11) + WORD2(v7) * (v85 ^ v39));
      v41 = v39 ^ (v35 - (v81 ^ v40));
      v42 = v40 ^ (WORD2(v7) * (v32 + __ROR4__(~v41, 13)));
      v8 = v9 & 7;
      v43 = &v82;
      v44 = v8;
      v82 = 0;
      v45 = v10;
      do
      {
        v46 = *v45++;
        *(_BYTE *)v43 = v46;
        v43 = (__int64 *)((char *)v43 + 1);
        --v44;
      }
      while ( v44 );
      v27 = v82;
      v47 = (char *)&v78 + (v9 & 7);
      a5 = HIDWORD(v82);
      HIDWORD(v78) = HIDWORD(v82) ^ v42;
      LODWORD(v78) = v82 ^ v41;
      v48 = 8 - (v9 & 7);
      do
      {
        *v47++ = 0;
        --v48;
      }
      while ( v48 );
      v28 = HIDWORD(v78);
      v29 = v78;
      v49 = v9 & 7;
      v50 = (char *)&v78;
      v51 = v11;
      do
      {
        v52 = *v50++;
        *v51++ = v52;
        --v49;
      }
      while ( v49 );
      LOWORD(v30) = (_WORD)v86;
      LOWORD(v7) = v84;
      v9 = v89;
    }
    else
    {
      v28 = HIDWORD(v78);
      v29 = 0;
      v30 = v7 >> 16;
      v85 = HIWORD(v7);
      v81 = HIDWORD(v7);
    }
    v86 = &v11[v8];
    v53 = (__int64 *)&v10[v8];
    v87 = (_QWORD *)(v9 >> 3);
    if ( v9 >> 3 )
    {
      v54 = v81;
      v55 = 0;
      v56 = v84;
      v57 = v85;
      v58 = v87;
      v59 = a5;
      v60 = (unsigned __int16)v81;
      LODWORD(v81) = (unsigned __int16)v81;
      v77 = (unsigned __int16)v30;
      LODWORD(v82) = (unsigned __int16)v7;
      do
      {
        v61 = *v53;
        v87 = v53 + 1;
        v62 = v29 ^ v61 ^ (v60 * (v77 ^ __ROR4__(v28 ^ HIDWORD(v61), 1)));
        v63 = v28 ^ HIDWORD(v61) ^ __ROR4__(v62, 25) ^ (v82 * __ROR4__(v62 - v54, 15));
        v64 = v62 ^ (v57 * __ROR4__(v63 - v56, 24) - __ROR4__(v63, 10));
        v65 = v63 ^ __ROR4__(v64, 2) ^ (v81 * __ROL4__(v82 ^ v64, 3));
        v66 = v64 ^ (v65 >> 6) ^ (v77 * (v65 ^ v57));
        v67 = v65 ^ ((v66 >> 12) + v82 * __ROL4__(v77 ^ v66, 3));
        v60 = v81;
        v68 = v66 ^ (v57 * (v67 - v82) - (v67 >> 8));
        v69 = v67 ^ ((v68 >> 11) + v81 * (v57 ^ v68));
        v70 = v68 ^ (v56 - (v69 ^ v54));
        v29 = v70 ^ v27;
        LODWORD(v78) = v70 ^ v27;
        v71 = v86;
        v28 = v69 ^ v59 ^ (v81 * (v82 + __ROR4__(~v70, 13)));
        v53 = v87;
        v27 = v61;
        HIDWORD(v78) = v28;
        ++v55;
        v59 = HIDWORD(v61);
        *v86 = v78;
        v86 = v71 + 1;
      }
      while ( v55 < (unsigned __int64)v58 );
      v17 = v80;
      v13 = v88;
      v11 = v90;
      v12 = v83;
      v10 = v91;
      v19 = v79;
      v9 = v89;
    }
    v26 = v11[v9 - 1];
  }
  if ( a7 )
  {
    v72 = (char *)&_ImageBase - WarbirdRuntime::g_preferedImageBase;
    while ( v17 < v12 )
    {
      v73 = *(_DWORD *)&v13[4 * v17];
      if ( (v73 & 0xFFFFFFF) >= v19 )
        break;
      ++v17;
      v74 = v73 >> 28;
      if ( v73 >> 28 )
      {
        v75 = (int *)((char *)&_ImageBase.unused + (v73 & 0xFFFFFFF));
        v76 = v11 - v10;
        if ( v74 == 3 )
        {
          *(_DWORD *)((char *)v75 + v76) = (_DWORD)v72 + *v75;
        }
        else if ( v74 == 10 )
        {
          *(_QWORD *)((char *)v75 + v76) = &v72[*(_QWORD *)v75];
        }
      }
    }
  }
  if ( v26 != a6 )
    WarbirdRuntime::CTermination::TrashStack();
}

```

## disassembly

```asm
0x180020640  mov     r11, rsp
0x180020643  sub     rsp, 0E8h
0x18002064a  mov     rax, cs:__security_cookie
0x180020651  xor     rax, rsp
0x180020654  mov     [rsp+0E8h+var_58], rax
0x18002065c  mov     [r11-8], rbx
0x180020660  mov     r10, r9
0x180020663  mov     [r11-10h], rbp
0x180020667  xor     ebx, ebx
0x180020669  lea     rbp, __ImageBase
0x180020670  mov     [r11-18h], rsi
0x180020674  mov     [r11-20h], rdi
0x180020678  mov     rdi, r8
0x18002067b  mov     [r11-28h], r12
0x18002067f  mov     r12, rcx
0x180020682  mov     [r11-30h], r13
0x180020686  mov     [r11-38h], r14
0x18002068a  mov     r14, rdx
0x18002068d  mov     [r11-40h], r15
0x180020691  mov     [rsp+0E8h+var_98], r9
0x180020696  mov     [rsp+0E8h+var_70], r8
0x18002069b  mov     [rsp+0E8h+var_68], rdx
0x1800206a3  mov     [rsp+0E8h+var_60], rcx
0x1800206ab  cmp     [rsp+0E8h+arg_30], ebx
0x1800206b2  jz      loc_18002078C
0x1800206b8  mov     esi, cs:?g_PrivateRelocationsTable@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTable
0x1800206be  mov     r10d, r12d
0x1800206c1  mov     r15d, cs:?g_PrivateRelocationsTableCount@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTableCount
0x1800206c8  add     rsi, rbp
0x1800206cb  sub     r10d, ebp
0x1800206ce  mov     [rsp+0E8h+var_78], rsi
0x1800206d3  mov     [rsp+0E8h+var_A0], r15d
0x1800206d8  mov     r8d, ebx
0x1800206db  lea     r9d, [r15-1]
0x1800206df  test    r9d, r9d
0x1800206e2  js      short loc_180020716
0x1800206e4  lea     edx, [r9+r8]
0x1800206e8  test    edx, edx
0x1800206ea  jns     short loc_1800206EE
0x1800206ec  inc     edx
0x1800206ee  sar     edx, 1
0x1800206f0  movsxd  rax, edx
0x1800206f3  mov     [rsp+0E8h+var_B4], edx
0x1800206f7  mov     ecx, [rsi+rax*4]
0x1800206fa  and     ecx, 0FFFFFFFh
0x180020700  cmp     r10d, ecx
0x180020703  jnb     short loc_18002070B
0x180020705  lea     r9d, [rdx-1]
0x180020709  jmp     short loc_180020711
0x18002070b  jbe     short loc_18002071D
0x18002070d  lea     r8d, [rdx+1]
0x180020711  cmp     r9d, r8d
0x180020714  jge     short loc_1800206E4
0x180020716  mov     edx, r8d
0x180020719  mov     [rsp+0E8h+var_B4], edx
0x18002071d  mov     r11, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x180020724  lea     r13d, [rdi+r10]
0x180020728  mov     [rsp+0E8h+var_B8], r13d
0x18002072d  sub     r11, rbp
0x180020730  mov     r9d, edx
0x180020733  cmp     r9d, r15d
0x180020736  jnb     short loc_1800207AF
0x180020738  mov     eax, r9d
0x18002073b  mov     r8d, [rsi+rax*4]
0x18002073f  mov     eax, r8d
0x180020742  and     eax, 0FFFFFFFh
0x180020747  cmp     eax, r13d
0x18002074a  jnb     short loc_1800207AF
0x18002074c  mov     ecx, r8d
0x18002074f  inc     r9d
0x180020752  shr     ecx, 1Ch
0x180020755  test    ecx, ecx
0x180020757  jz      short loc_180020733
0x180020759  and     r8d, 0FFFFFFFh
0x180020760  lea     r10, [r8+rbp]
0x180020764  mov     r8, r10
0x180020767  sub     r8, r12
0x18002076a  cmp     ecx, 3
0x18002076d  jz      short loc_180020780
0x18002076f  cmp     ecx, 0Ah
0x180020772  jnz     short loc_180020733
0x180020774  mov     rcx, [r10]
0x180020777  add     rcx, r11
0x18002077a  mov     [r8+r14], rcx
0x18002077e  jmp     short loc_180020733
0x180020780  mov     ecx, [r10]
0x180020783  add     ecx, r11d
0x180020786  mov     [r8+r14], ecx
0x18002078a  jmp     short loc_180020733
0x18002078c  mov     r13d, [rsp+0E8h+var_B8]
0x180020791  mov     rsi, rbx
0x180020794  mov     [rsp+0E8h+var_B8], r13d
0x180020799  mov     r15d, ebx
0x18002079c  mov     edx, [rsp+0E8h+var_B8]
0x1800207a0  mov     [rsp+0E8h+var_B4], edx
0x1800207a4  mov     [rsp+0E8h+var_78], rbx
0x1800207a9  mov     [rsp+0E8h+var_A0], ebx
0x1800207ad  jmp     short loc_1800207B4
0x1800207af  mov     r10, [rsp+0E8h+var_98]
0x1800207b4  xor     r11b, r11b
0x1800207b7  mov     eax, edi
0x1800207b9  test    rdi, rdi
0x1800207bc  jz      loc_180020BB9
0x1800207c2  mov     ebp, [rsp+0E8h+arg_20]
0x1800207c9  and     eax, 7
0x1800207cc  mov     ecx, ebp
0x1800207ce  mov     [rsp+0E8h+var_C8], eax
0x1800207d2  not     ecx
0x1800207d4  mov     [rsp+0E8h+var_C0], rbx
0x1800207d9  mov     rax, r10
0x1800207dc  mov     r8, r10
0x1800207df  jnz     short loc_180020806
0x1800207e1  mov     ebp, dword ptr [rsp+0E8h+var_C0+4]
0x1800207e5  mov     r9, r10
0x1800207e8  shr     r9, 20h
0x1800207ec  mov     r11d, ebx
0x1800207ef  shr     r8, 10h
0x1800207f3  shr     rax, 30h
0x1800207f7  mov     [rsp+0E8h+var_90], rax
0x1800207fc  mov     [rsp+0E8h+var_B0], r9
0x180020801  jmp     loc_1800209DC
0x180020806  shr     rax, 20h
0x18002080a  movzx   edi, ax
0x18002080d  mov     [rsp+0E8h+var_B0], rax
0x180020812  shr     r8, 10h
0x180020816  movzx   r11d, r8w
0x18002081a  mov     [rsp+0E8h+var_88], r8
0x18002081f  mov     r8d, ebp
0x180020822  ror     r8d, 1
0x180020825  xor     r8d, r11d
0x180020828  movzx   ebx, r10w
0x18002082c  imul    r8d, edi
0x180020830  xor     r8d, ecx
0x180020833  mov     r9d, r8d
0x180020836  sub     r9d, eax
0x180020839  mov     eax, r8d
0x18002083c  ror     eax, 19h
0x18002083f  ror     r9d, 0Fh
0x180020843  imul    r9d, ebx
0x180020847  xor     r9d, eax
0x18002084a  mov     rax, r10
0x18002084d  xor     r9d, ebp
0x180020850  shr     rax, 30h
0x180020854  mov     [rsp+0E8h+var_90], rax
0x180020859  mov     ecx, r9d
0x18002085c  sub     ecx, r10d
0x18002085f  mov     ebp, r10d
0x180020862  ror     ecx, 18h
0x180020865  imul    ecx, eax
0x180020868  mov     eax, r9d
0x18002086b  ror     eax, 0Ah
0x18002086e  sub     ecx, eax
0x180020870  xor     ecx, r8d
0x180020873  mov     r10d, ecx
0x180020876  mov     eax, ecx
0x180020878  ror     eax, 2
0x18002087b  xor     r10d, ebx
0x18002087e  rol     r10d, 3
0x180020882  imul    r10d, edi
0x180020886  xor     r10d, eax
0x180020889  xor     r10d, r9d
0x18002088c  mov     r8d, r10d
0x18002088f  mov     eax, r10d
0x180020892  xor     r8d, dword ptr [rsp+0E8h+var_90]
0x180020897  shr     eax, 6
0x18002089a  imul    r8d, r11d
0x18002089e  xor     r8d, eax
0x1800208a1  xor     r8d, ecx
0x1800208a4  mov     r9d, r8d
0x1800208a7  mov     eax, r8d
0x1800208aa  shr     eax, 0Ch
0x1800208ad  xor     r9d, r11d
0x1800208b0  rol     r9d, 3
0x1800208b4  imul    r9d, ebx
0x1800208b8  add     r9d, eax
0x1800208bb  xor     r9d, r10d
0x1800208be  mov     r10, [rsp+0E8h+var_90]
0x1800208c3  mov     ecx, r9d
0x1800208c6  mov     eax, r9d
0x1800208c9  shr     eax, 8
0x1800208cc  sub     ecx, ebx
0x1800208ce  imul    ecx, r10d
0x1800208d2  sub     ecx, eax
0x1800208d4  xor     ecx, r8d
0x1800208d7  mov     r8d, ecx
0x1800208da  mov     eax, ecx
0x1800208dc  xor     r8d, r10d
0x1800208df  shr     eax, 0Bh
0x1800208e2  imul    r8d, edi
0x1800208e6  add     r8d, eax
0x1800208e9  xor     r8d, r9d
0x1800208ec  mov     r9, [rsp+0E8h+var_B0]
0x1800208f1  mov     eax, r8d
0x1800208f4  xor     eax, r9d
0x1800208f7  sub     ebp, eax
0x1800208f9  xor     ebp, ecx
0x1800208fb  mov     r11d, ebp
0x1800208fe  not     ebp
0x180020900  ror     ebp, 0Dh
0x180020903  add     ebp, ebx
0x180020905  imul    ebp, edi
0x180020908  xor     ebp, r8d
0x18002090b  mov     ebx, [rsp+0E8h+var_C8]
0x18002090f  lea     r9, [rsp+0E8h+var_A8]
0x180020914  mov     ecx, ebx
0x180020916  mov     [rsp+0E8h+var_A8], 0
0x18002091f  mov     r8, r12
0x180020922  nop     dword ptr [rax+00h]
0x180020926  nop     word ptr [rax+rax+00000000h]
0x180020930  movzx   eax, byte ptr [r8]
0x180020934  lea     r8, [r8+1]
0x180020938  mov     [r9], al
0x18002093b  lea     r9, [r9+1]
0x18002093f  sub     rcx, 1
0x180020943  jnz     short loc_180020930
0x180020945  mov     eax, dword ptr [rsp+0E8h+var_A8+4]
0x180020949  lea     r8, [rsp+0E8h+var_C0]
0x18002094e  mov     rcx, [rsp+0E8h+var_A8]
0x180020953  lea     r8, [r8+rbx]
0x180020957  xor     ebp, eax
0x180020959  mov     [rsp+0E8h+arg_20], eax
0x180020960  xor     r11d, ecx
0x180020963  mov     dword ptr [rsp+0E8h+var_C0+4], ebp
0x180020967  mov     eax, 8
0x18002096c  mov     dword ptr [rsp+0E8h+var_C0], r11d
0x180020971  sub     rax, rbx
0x180020974  jz      short loc_180020997
0x180020976  nop     word ptr [rax+rax+00000000h]
0x180020980  mov     byte ptr [r8], 0
0x180020984  lea     r8, [r8+1]
0x180020988  sub     rax, 1
0x18002098c  jnz     short loc_180020980
0x18002098e  mov     ebp, dword ptr [rsp+0E8h+var_C0+4]
0x180020992  mov     r11d, dword ptr [rsp+0E8h+var_C0]
0x180020997  mov     r8, rbx
0x18002099a  lea     r9, [rsp+0E8h+var_C0]
0x18002099f  mov     r10, r14
0x1800209a2  nop     dword ptr [rax+00h]
0x1800209a6  nop     word ptr [rax+rax+00000000h]
0x1800209b0  movzx   eax, byte ptr [r9]
0x1800209b4  lea     r9, [r9+1]
0x1800209b8  mov     [r10], al
0x1800209bb  lea     r10, [r10+1]
0x1800209bf  sub     r8, 1
0x1800209c3  jnz     short loc_1800209B0
0x1800209c5  mov     rax, [rsp+0E8h+var_98]
0x1800209ca  mov     r8, [rsp+0E8h+var_88]
0x1800209cf  mov     r10, rax
0x1800209d2  mov     rdi, [rsp+0E8h+var_70]
0x1800209d7  mov     [rsp+0E8h+var_98], rax
0x1800209dc  lea     rax, [rbx+r14]
0x1800209e0  mov     [rsp+0E8h+var_88], rax
0x1800209e5  lea     r9, [rbx+r12]
0x1800209e9  mov     rax, rdi
0x1800209ec  shr     rax, 3
0x1800209f0  mov     [rsp+0E8h+var_80], rax
0x1800209f5  test    rax, rax
0x1800209f8  jz      loc_180020BAC
0x1800209fe  mov     rsi, [rsp+0E8h+var_B0]
0x180020a03  xor     r14d, r14d
0x180020a06  mov     r12, [rsp+0E8h+var_98]
0x180020a0b  mov     r13, [rsp+0E8h+var_90]
0x180020a10  mov     r15, [rsp+0E8h+var_80]
0x180020a15  mov     edx, [rsp+0E8h+arg_20]
0x180020a1c  movzx   eax, r8w
0x180020a20  movzx   ebx, si
0x180020a23  movzx   r8d, r10w
0x180020a27  mov     dword ptr [rsp+0E8h+var_B0], ebx
0x180020a2b  mov     [rsp+0E8h+var_C8], eax
0x180020a2f  mov     dword ptr [rsp+0E8h+var_A8], r8d
0x180020a34  nop     dword ptr [rax+00h]
0x180020a38  nop     dword ptr [rax+rax+00000000h]
0x180020a40  mov     rax, [r9]
0x180020a43  add     r9, 8
0x180020a47  mov     [rsp+0E8h+var_80], r9
0x180020a4c  mov     rdi, rax
0x180020a4f  shr     rdi, 20h
0x180020a53  mov     r9d, edi
0x180020a56  xor     r9d, ebp
0x180020a59  mov     ebp, dword ptr [rsp+0E8h+var_A8]
0x180020a5d  mov     r10d, r9d
0x180020a60  ror     r10d, 1
0x180020a63  xor     r10d, [rsp+0E8h+var_C8]
0x180020a68  imul    r10d, ebx
0x180020a6c  xor     r10d, eax
0x180020a6f  xor     r10d, r11d
0x180020a72  mov     r11d, r10d
0x180020a75  mov     r8d, r10d
0x180020a78  ror     r8d, 19h
0x180020a7c  sub     r11d, esi
0x180020a7f  ror     r11d, 0Fh
0x180020a83  imul    r11d, ebp
0x180020a87  xor     r11d, r8d
0x180020a8a  xor     r11d, r9d
0x180020a8d  mov     r9d, r11d
0x180020a90  mov     r8d, r11d
0x180020a93  ror     r8d, 0Ah
0x180020a97  sub     r9d, r12d
0x180020a9a  ror     r9d, 18h
0x180020a9e  imul    r9d, r13d
  ... truncated ...
```
