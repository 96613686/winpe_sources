# WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt(uchar const *,uchar *,unsigned __int64,WarbirdCrypto::CKey,ulong,uchar,int)

- ea: `0x1800213a0`
- end: `0x180021a0d`
- name: `?Decrypt@?$CEncryption@$05V?$CCipherFeistel64@$07$0JI@$0KN@$0HJ@$0P@$0FC@$0EG@$0LP@$0L@$0GK@$0CN@$0JI@$02$0DN@$0ED@$08$0M@$0HL@$0DN@$0GO@$04$0KF@$0PE@$0CJ@$0BM@$0NK@$0CA@$0HN@$0A@$0O@$0EG@$0EI@$0BC@$0JE@$0PJ@$0CA@$08$0IG@$0FF@$0ED@@WarbirdCrypto@@V?$CHashFunctionSCP@$00$01$02$0FLGHJNDFFJOLLCJB@@2@UENCRYPTED_SEGMENT_DATA_CONST_7@WarbirdRuntime@@UENCRYPTED_SEGMENT_DATA_READ_WRITE_7@5@@WarbirdRuntime@@CAXPEBEPEAE_KTCKey@WarbirdCrypto@@KEH@Z`
- size: `1645`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800232d0`

## callees

- `0x1800017b0`
- `0x1800213a0`
- `0x180025230`

## pseudocode

```c
void __fastcall WarbirdRuntime::CEncryption<6,WarbirdCrypto::CCipherFeistel64<8,152,173,121,15,82,70,191,11,106,45,152,3,61,67,9,12,123,61,110,5,165,244,41,28,218,32,125,0,14,70,72,18,148,249,32,9,134,85,67>,WarbirdCrypto::CHashFunctionSCP<1,2,3,6586405832520086161>,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_CONST_7,WarbirdRuntime::ENCRYPTED_SEGMENT_DATA_READ_WRITE_7>::Decrypt(
        char *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        int a5,
        char a6,
        int a7)
{
  _BYTE *v7; // rbp
  __int64 v8; // rdi
  char *v9; // r12
  volatile unsigned int v11; // r14d
  char *v12; // rsi
  unsigned int v13; // r11d
  signed int v14; // r8d
  signed int v15; // r10d
  unsigned int v16; // edx
  unsigned int v17; // ecx
  unsigned int v18; // r13d
  unsigned __int64 v19; // rbx
  volatile unsigned int i; // r10d
  unsigned int v21; // r8d
  unsigned int v22; // ecx
  char *v23; // r11
  signed __int64 v24; // r8
  char v25; // r11
  int v26; // ecx
  _QWORD *v27; // r8
  int v28; // r15d
  int v29; // r8d
  unsigned int v30; // r10d
  int v31; // ecx
  int v32; // r8d
  int v33; // r10d
  int v34; // ecx
  int v35; // r8d
  int v36; // r10d
  unsigned int v37; // r11d
  int v38; // r15d
  __int64 *v39; // r10
  __int64 v40; // rcx
  char *v41; // r8
  char v42; // al
  char *v43; // r8
  __int64 v44; // rax
  __int64 v45; // r8
  char *v46; // r10
  _BYTE *v47; // r11
  char v48; // al
  unsigned __int16 v49; // r10
  __int64 *v50; // rbx
  int v51; // esi
  int v52; // r12d
  int v53; // r9d
  _QWORD *v54; // r13
  unsigned __int64 v55; // rbp
  int v56; // r14d
  int v57; // edx
  __int64 v58; // rax
  int v59; // r11d
  unsigned int v60; // ebx
  int v61; // r10d
  int v62; // r11d
  int v63; // ebx
  int v64; // r10d
  int v65; // r11d
  int v66; // ebx
  unsigned int v67; // r10d
  char *v68; // r10
  unsigned int v69; // r8d
  unsigned int v70; // ecx
  char *v71; // r9
  signed __int64 v72; // r8
  char v73; // [rsp+20h] [rbp-B8h]
  unsigned int v74; // [rsp+24h] [rbp-B4h]
  int v75; // [rsp+24h] [rbp-B4h]
  __int64 v76; // [rsp+28h] [rbp-B0h] BYREF
  unsigned int v77; // [rsp+30h] [rbp-A8h]
  unsigned int v78; // [rsp+34h] [rbp-A4h]
  __int64 v79; // [rsp+38h] [rbp-A0h] BYREF
  unsigned __int64 v80; // [rsp+40h] [rbp-98h]
  int v81; // [rsp+48h] [rbp-90h]
  volatile unsigned int v82; // [rsp+4Ch] [rbp-8Ch]
  unsigned __int64 v83; // [rsp+50h] [rbp-88h]
  _QWORD *v84; // [rsp+58h] [rbp-80h]
  _QWORD *v85; // [rsp+60h] [rbp-78h]
  char *v86; // [rsp+68h] [rbp-70h]
  unsigned __int64 v87; // [rsp+70h] [rbp-68h]
  _BYTE *v88; // [rsp+78h] [rbp-60h]
  char *v89; // [rsp+80h] [rbp-58h]

  v7 = a2;
  v8 = 0;
  v9 = a1;
  v89 = a1;
  v87 = a3;
  v88 = a2;
  if ( a7 )
  {
    v11 = WarbirdRuntime::g_PrivateRelocationsTableCount;
    v12 = (char *)&_ImageBase + WarbirdRuntime::g_PrivateRelocationsTable;
    v13 = (_DWORD)a1 - (unsigned int)&_ImageBase;
    v86 = v12;
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
    v77 = a3 + v13;
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
        v24 = v23 - v9;
        if ( v22 == 3 )
        {
          *(_DWORD *)&v7[v24] = v19 + *(_DWORD *)v23;
        }
        else if ( v22 == 10 )
        {
          *(_QWORD *)&v7[v24] = v19 + *(_QWORD *)v23;
        }
      }
    }
  }
  else
  {
    v18 = v77;
    v12 = 0;
    v11 = 0;
    v16 = v77;
    v78 = v77;
    v86 = 0;
    v82 = 0;
  }
  v25 = 0;
  v73 = 0;
  if ( a3 )
  {
    v74 = a3 & 7;
    v26 = ~a5;
    v76 = 0;
    if ( (a3 & 7) != 0 )
    {
      v84 = (_QWORD *)(a4 >> 16);
      v80 = HIDWORD(a4);
      v29 = v26 ^ (__ROR4__(a5, 6) + WORD1(a4) * __ROL4__(a5 ^ (unsigned __int16)a4, 2));
      v30 = a5 ^ __ROR4__(v29, 2) ^ ((unsigned __int16)a4 * __ROR4__(v29 - HIDWORD(a4), 2));
      v83 = HIWORD(a4);
      v31 = v29 ^ ((v30 >> 11) + HIWORD(a4) * (v30 ^ WORD2(a4)));
      v32 = v30 ^ v31 ^ HIDWORD(a4) ^ a4;
      v33 = v31 ^ (WORD1(a4) * (WORD2(a4) ^ v32)) ^ __ROR4__(v32, 5);
      v34 = v32 ^ (__ROR4__(v33, 18) + (unsigned __int16)a4 * __ROR4__(v33 + HIDWORD(a4), 31));
      v35 = v33 ^ (HIWORD(a4) * (WORD1(a4) ^ v34) + __ROR4__(v34, 8));
      v36 = v34 ^ __ROR4__(v35, 29) ^ (WORD2(a4) * __ROL4__((unsigned __int16)a4 ^ v35, 4));
      v37 = v35 ^ (WORD1(a4) * __ROR4__(v36 + HIDWORD(a4), 9) - __ROR4__(v36, 6));
      v38 = v36 ^ (v37 >> 2) ^ ((unsigned __int16)a4 * __ROL4__(v37 - HIWORD(a4), 6));
      v8 = v74;
      v39 = &v79;
      v40 = v74;
      v79 = 0;
      v41 = v9;
      do
      {
        v42 = *v41++;
        *(_BYTE *)v39 = v42;
        v39 = (__int64 *)((char *)v39 + 1);
        --v40;
      }
      while ( v40 );
      v26 = v79;
      v43 = (char *)&v76 + v74;
      LODWORD(v76) = v79 ^ v37;
      a5 = HIDWORD(v79);
      HIDWORD(v76) = HIDWORD(v79) ^ v38;
      v44 = 8LL - v74;
      do
      {
        *v43++ = 0;
        --v44;
      }
      while ( v44 );
      v28 = HIDWORD(v76);
      v75 = v76;
      v45 = v8;
      v46 = (char *)&v76;
      v47 = v7;
      do
      {
        v48 = *v46++;
        *v47++ = v48;
        --v45;
      }
      while ( v45 );
      LOWORD(v27) = (_WORD)v84;
    }
    else
    {
      v27 = (_QWORD *)(a4 >> 16);
      v80 = HIDWORD(a4);
      v28 = HIDWORD(v76);
      v83 = HIWORD(a4);
      v75 = 0;
    }
    v49 = a4;
    v84 = &v7[v8];
    v50 = (__int64 *)&v9[v8];
    v85 = (_QWORD *)(v87 >> 3);
    if ( v87 >> 3 )
    {
      v51 = v80;
      v52 = v75;
      v53 = v80 ^ a4;
      v54 = v85;
      v55 = 0;
      v56 = a5;
      v57 = v83;
      LODWORD(v27) = (unsigned __int16)v27;
      LODWORD(v80) = (unsigned __int16)v80;
      v81 = v49;
      LODWORD(v79) = (unsigned __int16)v27;
      do
      {
        v58 = *v50;
        v85 = v50 + 1;
        v59 = v52 ^ v58 ^ (__ROR4__(v28 ^ HIDWORD(v58), 6) + (_DWORD)v27 * __ROL4__(v81 ^ v28 ^ HIDWORD(v58), 2));
        v60 = v28 ^ HIDWORD(v58) ^ __ROR4__(v59, 2) ^ (v81 * __ROR4__(v59 - v51, 2));
        v61 = v59 ^ ((v60 >> 11) + v57 * (v80 ^ v60));
        v62 = v60 ^ v61 ^ v53;
        v63 = v61 ^ (v79 * (v62 ^ v80)) ^ __ROR4__(v62, 5);
        v64 = v62 ^ (__ROR4__(v63, 18) + v81 * __ROR4__(v63 + v51, 31));
        v65 = v63 ^ (v57 * (v64 ^ v79) + __ROR4__(v64, 8));
        v66 = v64 ^ __ROR4__(v65, 29) ^ (v80 * __ROL4__(v65 ^ v81, 4));
        v67 = v65 ^ (v79 * __ROR4__(v66 + v51, 9) - __ROR4__(v66, 6));
        v52 = v67 ^ v26;
        LODWORD(v76) = v67 ^ v26;
        v27 = v84;
        v28 = v66 ^ v56 ^ (v67 >> 2) ^ (v81 * __ROL4__(v67 - v57, 6));
        v26 = v58;
        v50 = v85;
        ++v55;
        HIDWORD(v76) = v28;
        v56 = HIDWORD(v58);
        *v84 = v76;
        v84 = v27 + 1;
        LODWORD(v27) = v79;
      }
      while ( v55 < (unsigned __int64)v54 );
      v16 = v78;
      v12 = v86;
      v7 = v88;
      v11 = v82;
      v9 = v89;
      v18 = v77;
    }
    v25 = v7[v87 - 1];
    v73 = v25;
  }
  if ( a7 )
  {
    v68 = (char *)&_ImageBase - WarbirdRuntime::g_preferedImageBase;
    while ( v16 < v11 )
    {
      v69 = *(_DWORD *)&v12[4 * v16];
      if ( (v69 & 0xFFFFFFF) >= v18 )
        break;
      ++v16;
      v70 = v69 >> 28;
      if ( v69 >> 28 )
      {
        v71 = (char *)&_ImageBase + (v69 & 0xFFFFFFF);
        v72 = v71 - v9;
        if ( v70 == 3 )
        {
          *(_DWORD *)&v7[v72] = (_DWORD)v68 + *(_DWORD *)v71;
        }
        else if ( v70 == 10 )
        {
          *(_QWORD *)&v7[v72] = &v68[*(_QWORD *)v71];
        }
      }
    }
    v25 = v73;
  }
  if ( v25 != a6 )
    WarbirdRuntime::CTermination::TrashStack();
}

```

## disassembly

```asm
0x1800213a0  mov     r11, rsp
0x1800213a3  sub     rsp, 0D8h
0x1800213aa  mov     rax, cs:__security_cookie
0x1800213b1  xor     rax, rsp
0x1800213b4  mov     [rsp+0D8h+var_50], rax
0x1800213bc  mov     [r11-8], rbx
0x1800213c0  mov     [r11-10h], rbp
0x1800213c4  mov     rbp, rdx
0x1800213c7  mov     [r11-18h], rsi
0x1800213cb  mov     [r11-20h], rdi
0x1800213cf  xor     edi, edi
0x1800213d1  mov     [r11-28h], r12
0x1800213d5  mov     r12, rcx
0x1800213d8  mov     [r11-30h], r13
0x1800213dc  mov     [r11-38h], r14
0x1800213e0  mov     [r11-40h], r15
0x1800213e4  mov     r15, r8
0x1800213e7  mov     [rsp+0D8h+var_58], rcx
0x1800213ef  lea     rcx, __ImageBase
0x1800213f6  mov     [rsp+0D8h+var_68], r8
0x1800213fb  mov     [rsp+0D8h+var_60], rdx
0x180021400  cmp     [rsp+0D8h+arg_30], edi
0x180021407  jz      loc_1800214FE
0x18002140d  mov     esi, cs:?g_PrivateRelocationsTable@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTable
0x180021413  mov     r11d, r12d
0x180021416  mov     r14d, cs:?g_PrivateRelocationsTableCount@WarbirdRuntime@@3KC; ulong volatile WarbirdRuntime::g_PrivateRelocationsTableCount
0x18002141d  add     rsi, rcx
0x180021420  sub     r11d, ecx
0x180021423  mov     [rsp+0D8h+var_70], rsi
0x180021428  mov     [rsp+0D8h+var_8C], r14d
0x18002142d  mov     r8d, edi
0x180021430  lea     r10d, [r14-1]
0x180021434  test    r10d, r10d
0x180021437  js      short loc_180021472
0x180021439  nop     dword ptr [rax+00000000h]
0x180021440  lea     edx, [r10+r8]
0x180021444  test    edx, edx
0x180021446  jns     short loc_18002144A
0x180021448  inc     edx
0x18002144a  sar     edx, 1
0x18002144c  movsxd  rax, edx
0x18002144f  mov     [rsp+0D8h+var_A4], edx
0x180021453  mov     ecx, [rsi+rax*4]
0x180021456  and     ecx, 0FFFFFFFh
0x18002145c  cmp     r11d, ecx
0x18002145f  jnb     short loc_180021467
0x180021461  lea     r10d, [rdx-1]
0x180021465  jmp     short loc_18002146D
0x180021467  jbe     short loc_180021479
0x180021469  lea     r8d, [rdx+1]
0x18002146d  cmp     r10d, r8d
0x180021470  jge     short loc_180021440
0x180021472  mov     edx, r8d
0x180021475  mov     [rsp+0D8h+var_A4], edx
0x180021479  mov     rbx, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x180021480  lea     r13d, [r15+r11]
0x180021484  lea     r11, __ImageBase
0x18002148b  mov     [rsp+0D8h+var_A8], r13d
0x180021490  sub     rbx, r11
0x180021493  mov     r10d, edx
0x180021496  jmp     short loc_1800214A7
0x1800214a0  lea     r11, __ImageBase
0x1800214a7  cmp     r10d, r14d
0x1800214aa  jnb     short loc_18002151F
0x1800214ac  mov     eax, r10d
0x1800214af  mov     r8d, [rsi+rax*4]
0x1800214b3  mov     eax, r8d
0x1800214b6  and     eax, 0FFFFFFFh
0x1800214bb  cmp     eax, r13d
0x1800214be  jnb     short loc_18002151F
0x1800214c0  mov     ecx, r8d
0x1800214c3  inc     r10d
0x1800214c6  shr     ecx, 1Ch
0x1800214c9  test    ecx, ecx
0x1800214cb  jz      short loc_1800214A7
0x1800214cd  and     r8d, 0FFFFFFFh
0x1800214d4  add     r11, r8
0x1800214d7  mov     r8, r11
0x1800214da  sub     r8, r12
0x1800214dd  cmp     ecx, 3
0x1800214e0  jz      short loc_1800214F3
0x1800214e2  cmp     ecx, 0Ah
0x1800214e5  jnz     short loc_1800214A0
0x1800214e7  mov     rcx, [r11]
0x1800214ea  add     rcx, rbx
0x1800214ed  mov     [r8+rbp], rcx
0x1800214f1  jmp     short loc_1800214A0
0x1800214f3  mov     ecx, [r11]
0x1800214f6  add     ecx, ebx
0x1800214f8  mov     [r8+rbp], ecx
0x1800214fc  jmp     short loc_1800214A0
0x1800214fe  mov     r13d, [rsp+0D8h+var_A8]
0x180021503  mov     rsi, rdi
0x180021506  mov     [rsp+0D8h+var_A8], r13d
0x18002150b  mov     r14d, edi
0x18002150e  mov     edx, [rsp+0D8h+var_A8]
0x180021512  mov     [rsp+0D8h+var_A4], edx
0x180021516  mov     [rsp+0D8h+var_70], rdi
0x18002151b  mov     [rsp+0D8h+var_8C], edi
0x18002151f  xor     r11b, r11b
0x180021522  mov     eax, r15d
0x180021525  mov     [rsp+0D8h+var_B8], r11b
0x18002152a  test    r15, r15
0x18002152d  jz      loc_180021926
0x180021533  mov     r11d, [rsp+0D8h+arg_20]
0x18002153b  and     eax, 7
0x18002153e  mov     ecx, r11d
0x180021541  mov     [rsp+0D8h+var_B4], eax
0x180021545  not     ecx
0x180021547  mov     [rsp+0D8h+var_B0], rdi
0x18002154c  mov     rax, r9
0x18002154f  mov     r15, r9
0x180021552  jnz     short loc_18002157E
0x180021554  shr     r15, 20h
0x180021558  mov     r8, r9
0x18002155b  shr     r8, 10h
0x18002155f  mov     r11d, edi
0x180021562  shr     rax, 30h
0x180021566  mov     [rsp+0D8h+var_98], r15
0x18002156b  mov     r15d, dword ptr [rsp+0D8h+var_B0+4]
0x180021570  mov     [rsp+0D8h+var_88], rax
0x180021575  mov     [rsp+0D8h+var_B4], edi
0x180021579  jmp     loc_18002173A
0x18002157e  shr     rax, 10h
0x180021582  movzx   ebx, ax
0x180021585  mov     [rsp+0D8h+var_80], rax
0x18002158a  mov     eax, r11d
0x18002158d  ror     eax, 6
0x180021590  shr     r15, 20h
0x180021594  movzx   edi, r9w
0x180021598  mov     [rsp+0D8h+var_98], r15
0x18002159d  mov     r8d, edi
0x1800215a0  xor     r8d, r11d
0x1800215a3  rol     r8d, 2
0x1800215a7  imul    r8d, ebx
0x1800215ab  add     r8d, eax
0x1800215ae  xor     r8d, ecx
0x1800215b1  mov     eax, r8d
0x1800215b4  mov     r10d, r8d
0x1800215b7  sub     r10d, r15d
0x1800215ba  ror     eax, 2
0x1800215bd  ror     r10d, 2
0x1800215c1  imul    r10d, edi
0x1800215c5  xor     r10d, eax
0x1800215c8  mov     rax, r9
0x1800215cb  xor     r10d, r11d
0x1800215ce  shr     rax, 30h
0x1800215d2  mov     [rsp+0D8h+var_88], rax
0x1800215d7  movzx   r11d, r15w
0x1800215db  mov     ecx, r11d
0x1800215de  xor     ecx, r10d
0x1800215e1  imul    ecx, eax
0x1800215e4  mov     eax, r10d
0x1800215e7  shr     eax, 0Bh
0x1800215ea  add     ecx, eax
0x1800215ec  xor     ecx, r8d
0x1800215ef  mov     r8d, r9d
0x1800215f2  xor     r8d, r15d
0x1800215f5  xor     r8d, ecx
0x1800215f8  xor     r8d, r10d
0x1800215fb  mov     eax, r8d
0x1800215fe  mov     r10d, r8d
0x180021601  xor     eax, r11d
0x180021604  ror     r10d, 5
0x180021608  imul    eax, ebx
0x18002160b  xor     r10d, eax
0x18002160e  xor     r10d, ecx
0x180021611  mov     eax, r10d
0x180021614  ror     eax, 12h
0x180021617  lea     ecx, [r10+r15]
0x18002161b  ror     ecx, 1Fh
0x18002161e  imul    ecx, edi
0x180021621  add     ecx, eax
0x180021623  xor     ecx, r8d
0x180021626  mov     eax, ecx
0x180021628  mov     r8d, ecx
0x18002162b  xor     eax, ebx
0x18002162d  ror     r8d, 8
0x180021631  imul    eax, dword ptr [rsp+0D8h+var_88]
0x180021636  add     r8d, eax
0x180021639  xor     r8d, r10d
0x18002163c  mov     r10d, r8d
0x18002163f  mov     eax, r8d
0x180021642  ror     eax, 1Dh
0x180021645  xor     r10d, edi
0x180021648  rol     r10d, 4
0x18002164c  imul    r10d, r11d
0x180021650  xor     r10d, eax
0x180021653  xor     r10d, ecx
0x180021656  mov     eax, r10d
0x180021659  ror     eax, 6
0x18002165c  lea     r11d, [r10+r15]
0x180021660  ror     r11d, 9
0x180021664  imul    r11d, ebx
0x180021668  sub     r11d, eax
0x18002166b  xor     r11d, r8d
0x18002166e  mov     r15d, r11d
0x180021671  mov     eax, r11d
0x180021674  sub     r15d, dword ptr [rsp+0D8h+var_88]
0x180021679  rol     r15d, 6
0x18002167d  imul    r15d, edi
0x180021681  shr     eax, 2
0x180021684  xor     r15d, eax
0x180021687  xor     r15d, r10d
0x18002168a  mov     edi, [rsp+0D8h+var_B4]
0x18002168e  lea     r10, [rsp+0D8h+var_A0]
0x180021693  mov     ecx, edi
0x180021695  mov     [rsp+0D8h+var_A0], 0
0x18002169e  mov     r8, r12
0x1800216a1  movzx   eax, byte ptr [r8]
0x1800216a5  lea     r8, [r8+1]
0x1800216a9  mov     [r10], al
0x1800216ac  lea     r10, [r10+1]
0x1800216b0  sub     rcx, 1
0x1800216b4  jnz     short loc_1800216A1
0x1800216b6  mov     rcx, [rsp+0D8h+var_A0]
0x1800216bb  lea     r8, [rsp+0D8h+var_B0]
0x1800216c0  xor     r11d, ecx
0x1800216c3  lea     r8, [r8+rdi]
0x1800216c7  mov     [rsp+0D8h+var_B4], r11d
0x1800216cc  mov     eax, 8
0x1800216d1  mov     dword ptr [rsp+0D8h+var_B0], r11d
0x1800216d6  mov     r11d, dword ptr [rsp+0D8h+var_A0+4]
0x1800216db  xor     r15d, r11d
0x1800216de  mov     [rsp+0D8h+arg_20], r11d
0x1800216e6  mov     dword ptr [rsp+0D8h+var_B0+4], r15d
0x1800216eb  sub     rax, rdi
0x1800216ee  jz      short loc_18002170D
0x1800216f0  mov     byte ptr [r8], 0
0x1800216f4  lea     r8, [r8+1]
0x1800216f8  sub     rax, 1
0x1800216fc  jnz     short loc_1800216F0
0x1800216fe  mov     r11d, dword ptr [rsp+0D8h+var_B0]
0x180021703  mov     r15d, dword ptr [rsp+0D8h+var_B0+4]
0x180021708  mov     [rsp+0D8h+var_B4], r11d
0x18002170d  mov     r8, rdi
0x180021710  lea     r10, [rsp+0D8h+var_B0]
0x180021715  mov     r11, rbp
0x180021718  nop     dword ptr [rax+rax+00000000h]
0x180021720  movzx   eax, byte ptr [r10]
0x180021724  lea     r10, [r10+1]
0x180021728  mov     [r11], al
0x18002172b  lea     r11, [r11+1]
0x18002172f  sub     r8, 1
0x180021733  jnz     short loc_180021720
0x180021735  mov     r8, [rsp+0D8h+var_80]
0x18002173a  lea     rax, [rdi+rbp]
0x18002173e  mov     r10, r9
0x180021741  mov     [rsp+0D8h+var_80], rax
0x180021746  lea     rbx, [rdi+r12]
0x18002174a  mov     rax, [rsp+0D8h+var_68]
0x18002174f  shr     rax, 3
0x180021753  mov     [rsp+0D8h+var_78], rax
0x180021758  test    rax, rax
0x18002175b  jz      loc_180021916
0x180021761  mov     rsi, [rsp+0D8h+var_98]
0x180021766  mov     r12d, [rsp+0D8h+var_B4]
0x18002176b  xor     r9d, esi
0x18002176e  mov     r13, [rsp+0D8h+var_78]
0x180021773  xor     ebp, ebp
0x180021775  mov     r14d, [rsp+0D8h+arg_20]
0x18002177d  mov     rdx, [rsp+0D8h+var_88]
0x180021782  movzx   eax, si
0x180021785  movzx   r11d, r10w
0x180021789  movzx   r8d, r8w
0x18002178d  mov     dword ptr [rsp+0D8h+var_98], eax
0x180021791  mov     [rsp+0D8h+var_90], r11d
0x180021796  mov     dword ptr [rsp+0D8h+var_A0], r8d
0x18002179b  nop     dword ptr [rax+rax+00h]
0x1800217a0  mov     rax, [rbx]
0x1800217a3  add     rbx, 8
0x1800217a7  mov     [rsp+0D8h+var_78], rbx
0x1800217ac  mov     rdi, rax
0x1800217af  shr     rdi, 20h
0x1800217b3  mov     r10d, edi
0x1800217b6  xor     r10d, r15d
0x1800217b9  mov     r15d, [rsp+0D8h+var_90]
0x1800217be  mov     r11d, r10d
0x1800217c1  xor     r11d, r15d
0x1800217c4  rol     r11d, 2
0x1800217c8  imul    r11d, r8d
0x1800217cc  mov     r8d, r10d
0x1800217cf  ror     r8d, 6
0x1800217d3  add     r11d, r8d
0x1800217d6  xor     r11d, eax
0x1800217d9  xor     r11d, r12d
0x1800217dc  mov     r12d, dword ptr [rsp+0D8h+var_A0]
0x1800217e1  mov     ebx, r11d
0x1800217e4  mov     r8d, r11d
0x1800217e7  ror     r8d, 2
0x1800217eb  sub     ebx, esi
0x1800217ed  ror     ebx, 2
0x1800217f0  imul    ebx, r15d
0x1800217f4  xor     ebx, r8d
0x1800217f7  xor     ebx, r10d
0x1800217fa  mov     r10d, ebx
0x1800217fd  mov     r8d, ebx
0x180021800  xor     r10d, dword ptr [rsp+0D8h+var_98]
0x180021805  imul    r10d, edx
0x180021809  shr     r8d, 0Bh
  ... truncated ...
```
