# BfeSecureSocketAdd

- ea: `0x1800706a0`
- end: `0x180070d13`
- name: `BfeSecureSocketAdd`
- size: `1651`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800661a0`

## callees

- `0x18000c348`
- `0x18000ea30`
- `0x180012d8c`
- `0x1800197d0`
- `0x180023280`
- `0x1800232b4`
- `0x1800232dc`
- `0x180030154`
- `0x18005aa60`
- `0x1800706a0`
- `0x180070d1c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180070736`
- `RPCRT4!UuidCreate` at `0x180070736`

## string_xrefs

- `0x180070749`: `UuidCreate`
- `0x180070ca2`: `BfeFwpsSecureSocketFiltersCopy`

## pseudocode

```c
__int64 __fastcall BfeSecureSocketAdd(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 PrivateStateByKey; // r12
  UUID *v5; // rcx
  unsigned int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  const char *v9; // rdx
  __int64 v10; // rbx
  int v11; // ecx
  __int64 v12; // rsi
  int v13; // edx
  int IsNull; // eax
  const GUID *v15; // rcx
  const GUID *v16; // rdx
  __int64 v17; // rcx
  const GUID *v18; // rcx
  const GUID *v19; // r13
  __int64 PublicStateByKey; // rax
  __int64 v21; // rax
  int v22; // r15d
  __int128 v23; // xmm1
  int v24; // r14d
  __int64 v25; // r9
  int v26; // r14d
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v30; // [rsp+A0h] [rbp-80h] BYREF
  __int64 v31; // [rsp+A8h] [rbp-78h]
  __int64 v32; // [rsp+B0h] [rbp-70h] BYREF
  __int64 v33; // [rsp+B8h] [rbp-68h]
  __int64 v34; // [rsp+C0h] [rbp-60h]
  __int64 v35; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v36; // [rsp+D0h] [rbp-50h]
  __int64 v37; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+E0h] [rbp-40h]
  __int64 v39; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v40; // [rsp+F0h] [rbp-30h]
  const GUID *v41; // [rsp+F8h] [rbp-28h]
  __int64 v42; // [rsp+100h] [rbp-20h]
  __int128 v43; // [rsp+108h] [rbp-18h]
  __int64 v44; // [rsp+118h] [rbp-8h] BYREF
  char *v45; // [rsp+120h] [rbp+0h]
  UUID Uuid; // [rsp+128h] [rbp+8h] BYREF
  UUID v47; // [rsp+138h] [rbp+18h] BYREF
  __int128 v48; // [rsp+148h] [rbp+28h]
  char v49; // [rsp+160h] [rbp+40h] BYREF

  v42 = a3;
  LODWORD(v45) = 0;
  v44 = 0;
  v34 = a2;
  v39 = 0;
  Uuid = 0;
  v40 = 0;
  PrivateStateByKey = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  v37 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  v43 = 0;
  v47 = 0;
  v48 = 0;
  if ( (unsigned int)BfeGuidIsNull(a1) )
  {
    v6 = UuidCreate(&Uuid);
    if ( v6 )
    {
      v8 = v6;
      v9 = "UuidCreate";
LABEL_4:
      v10 = WfpReportSysErrorAsWinError(v7, v9, v8);
      goto LABEL_47;
    }
  }
  else
  {
    Uuid = *v5;
  }
  v11 = *(_DWORD *)(a1 + 32);
  v12 = *(int *)(a1 + 36);
  if ( (v11 & 1) != 0 )
  {
    LOBYTE(v40) = *(_BYTE *)(a1 + 40);
    LODWORD(v39) = 1;
  }
  v13 = 3;
  if ( (_DWORD)v12 )
  {
    v13 = 11;
    if ( (v11 & 2) != 0 )
    {
      LODWORD(v32) = 11;
      v33 = a1 + 44;
    }
    if ( (v11 & 4) != 0 )
    {
      v31 = a1 + 60;
      goto LABEL_17;
    }
  }
  else
  {
    if ( (v11 & 2) != 0 )
    {
      LODWORD(v33) = *(_DWORD *)(a1 + 44);
      LODWORD(v32) = 3;
    }
    if ( (v11 & 4) != 0 )
    {
      LODWORD(v31) = *(_DWORD *)(a1 + 60);
LABEL_17:
      LODWORD(v30) = v13;
    }
  }
  if ( (v11 & 8) != 0 )
  {
    LOWORD(v38) = *(_WORD *)(a1 + 76);
    LODWORD(v37) = 2;
  }
  if ( (v11 & 0x10) != 0 )
  {
    LOWORD(v36) = *(_WORD *)(a1 + 78);
    LODWORD(v35) = 2;
  }
  IsNull = BfeGuidIsNull(*(_QWORD *)(a1 + 80));
  v16 = &FWPM_PROVIDER_CONTEXT_SECURE_SOCKET_AUTHIP;
  if ( !IsNull )
    v16 = v15;
  v17 = *(_QWORD *)(a1 + 96);
  v41 = v16;
  v19 = &FWPM_PROVIDER_CONTEXT_SECURE_SOCKET_IPSEC;
  if ( !(unsigned int)BfeGuidIsNull(v17) )
    v19 = v18;
  PublicStateByKey = BfeObjectFindPublicStateByKey(1, v19, 0);
  if ( !PublicStateByKey )
  {
    v8 = 2150760454LL;
LABEL_28:
    v9 = "BfeSecureSocketAdd";
    goto LABEL_4;
  }
  if ( *(_DWORD *)(PublicStateByKey + 64) != 3 )
  {
    v8 = 2150760500LL;
    goto LABEL_28;
  }
  v21 = *(_QWORD *)(PublicStateByKey + 72);
  v22 = *(_DWORD *)(v21 + 16) & 2;
  if ( v22 || (*(_BYTE *)(v21 + 16) & 4) != 0 )
  {
    *((_QWORD *)&v43 + 1) = 2;
    *(_QWORD *)&v43 = 1;
  }
  v23 = *(_OWORD *)(a1 + 16);
  v47 = Uuid;
  v48 = v23;
  v10 = BfeObjectAddCopy(6, &v47, 0);
  if ( v10 )
    goto LABEL_50;
  PrivateStateByKey = BfeObjectFindPrivateStateByKey(6, &Uuid, 0);
  LODWORD(v44) = 0;
  v24 = 0;
  v45 = &v49;
  while ( v24 < 2 )
  {
    v25 = v24 + v12 + 2LL * v24;
    v10 = BfeSecureSocketAddFilter(
            PrivateStateByKey,
            a1,
            v34,
            (unsigned int)off_1800984B0[v25],
            word_1800C0D28[v25],
            0,
            *((_QWORD *)&v43 + v24),
            (__int64)off_1800B0830[v25],
            (__int64)&FWPM_CONDITION_IP_PROTOCOL,
            (__int64)&v39,
            (__int64)&FWPM_CONDITION_IP_LOCAL_ADDRESS,
            (__int64)&v32,
            (__int64)&FWPM_CONDITION_IP_REMOTE_ADDRESS,
            (__int64)&v30,
            (__int64)&FWPM_CONDITION_IP_LOCAL_PORT,
            (__int64)&v37,
            (__int64)&FWPM_CONDITION_IP_REMOTE_PORT,
            (__int64)&v35,
            (__int64)&v44);
    if ( v10 )
      goto LABEL_48;
    ++v24;
  }
  v26 = v34;
  if ( v22
    && (v10 = BfeSecureSocketAddFilter(
                PrivateStateByKey,
                a1,
                v34,
                (unsigned int)off_1800986D8[v12],
                word_1800C0DB2[v12],
                0,
                (*(_DWORD *)(a1 + 32) >> 11) & 0x20,
                (__int64)off_1800B08D8[v12],
                (__int64)&FWPM_CONDITION_IP_PROTOCOL,
                (__int64)&v39,
                (__int64)&FWPM_CONDITION_IP_LOCAL_ADDRESS,
                (__int64)&v32,
                (__int64)&FWPM_CONDITION_IP_REMOTE_ADDRESS,
                (__int64)&v30,
                (__int64)&FWPM_CONDITION_IP_LOCAL_PORT,
                (__int64)&v37,
                (__int64)&FWPM_CONDITION_IP_REMOTE_PORT,
                (__int64)&v35,
                (__int64)&v44)) != 0
    || (v10 = BfeSecureSocketAddFilter(
                PrivateStateByKey,
                a1,
                v26,
                (unsigned int)off_180098780[v12],
                word_1800C0DDC[v12],
                (__int64)v41,
                0,
                0,
                (__int64)&FWPM_CONDITION_IP_LOCAL_ADDRESS,
                (__int64)&v32,
                (__int64)&FWPM_CONDITION_IP_REMOTE_ADDRESS,
                (__int64)&v30,
                0,
                0,
                0,
                0,
                0,
                0,
                (__int64)&v44)) != 0
    || !(unsigned int)BfeGuidIsNull(*(_QWORD *)(a1 + 88))
    && (v10 = BfeSecureSocketAddFilter(
                PrivateStateByKey,
                a1,
                v26,
                (unsigned int)off_180098780[v12],
                word_1800C0DDC[v12],
                v27,
                0,
                0,
                (__int64)&FWPM_CONDITION_IP_LOCAL_ADDRESS,
                (__int64)&v32,
                (__int64)&FWPM_CONDITION_IP_REMOTE_ADDRESS,
                (__int64)&v30,
                0,
                0,
                0,
                0,
                0,
                0,
                (__int64)&v44)) != 0
    || (v10 = BfeSecureSocketAddFilter(
                PrivateStateByKey,
                a1,
                v26,
                (unsigned int)off_180098750[v12],
                word_1800C0DD0[v12],
                (__int64)v19,
                0,
                0,
                (__int64)&FWPM_CONDITION_IP_PROTOCOL,
                (__int64)&v39,
                (__int64)&FWPM_CONDITION_IP_LOCAL_ADDRESS,
                (__int64)&v32,
                (__int64)&FWPM_CONDITION_IP_REMOTE_ADDRESS,
                (__int64)&v30,
                (__int64)&FWPM_CONDITION_IP_LOCAL_PORT,
                (__int64)&v37,
                (__int64)&FWPM_CONDITION_IP_REMOTE_PORT,
                (__int64)&v35,
                (__int64)&v44)) != 0 )
  {
LABEL_48:
    if ( PrivateStateByKey )
      BfeObjectDeleteByKey(6, &Uuid);
LABEL_50:
    WfpReportError(v10, "BfeSecureSocketAdd");
    return v10;
  }
  v28 = WfpMidlObjectCopy(
          &FWPS_SECURE_SOCKET_FILTERS0_MARSHAL_Encode,
          &v44,
          &FWPS_SECURE_SOCKET_FILTERS0_MARSHAL_Decode,
          v42);
  v10 = v28;
  if ( v28 )
    WfpReportError(v28, "BfeFwpsSecureSocketFiltersCopy");
LABEL_47:
  if ( v10 )
    goto LABEL_48;
  return v10;
}

```

## disassembly

```asm
0x1800706a0  mov     [rsp-8+arg_18], rbx
0x1800706a5  push    rbp
0x1800706a6  push    rsi
0x1800706a7  push    rdi
0x1800706a8  push    r12
0x1800706aa  push    r13
0x1800706ac  push    r14
0x1800706ae  push    r15
0x1800706b0  lea     rbp, [rsp-0B0h]
0x1800706b8  sub     rsp, 1D0h
0x1800706bf  mov     rax, cs:__security_cookie
0x1800706c6  xor     rax, rsp
0x1800706c9  mov     [rbp+0E0h+var_40], rax
0x1800706d0  xor     eax, eax
0x1800706d2  mov     [rbp+0E0h+var_100], r8
0x1800706d6  xor     r15d, r15d
0x1800706d9  mov     qword ptr [rbp+0E0h+var_E4], rax
0x1800706dd  xorps   xmm0, xmm0
0x1800706e0  mov     [rbp-8], rax
0x1800706e4  xorps   xmm1, xmm1
0x1800706e7  mov     [rbp+0E0h+var_140], rdx
0x1800706eb  mov     rdi, rcx
0x1800706ee  mov     [rbp+0E0h+var_118], r15
0x1800706f2  movups  xmmword ptr [rbp+0E0h+Uuid.Data1], xmm0
0x1800706f6  mov     [rbp+0E0h+var_110], rax
0x1800706fa  mov     r12d, r15d
0x1800706fd  mov     [rbp+0E0h+var_150], r15
0x180070701  mov     [rbp+0E0h+var_148], rax
0x180070705  mov     [rbp+0E0h+var_160], r15
0x180070709  mov     [rbp+0E0h+var_158], rax
0x18007070d  mov     [rbp+0E0h+var_128], r15
0x180070711  mov     [rbp+0E0h+var_120], rax
0x180070715  mov     [rbp+0E0h+var_138], r15
0x180070719  mov     [rbp+0E0h+var_130], rax
0x18007071d  movups  [rbp+0E0h+var_F8], xmm0
0x180070721  movups  [rbp+0E0h+var_C8], xmm1
0x180070725  movups  [rbp+0E0h+var_B8], xmm1
0x180070729  call    BfeGuidIsNull
0x18007072e  test    eax, eax
0x180070730  jz      short loc_18007075D
0x180070732  lea     rcx, [rbp+0E0h+Uuid]; Uuid
0x180070736  call    cs:__imp_UuidCreate
0x18007073d  nop     dword ptr [rax+rax+00h]
0x180070742  test    eax, eax
0x180070744  jz      short loc_180070765
0x180070746  mov     r8d, eax
0x180070749  lea     rdx, aUuidcreate; "UuidCreate"
0x180070750  call    WfpReportSysErrorAsWinError
0x180070755  mov     rbx, rax
0x180070758  jmp     loc_180070CB1
0x18007075d  movups  xmm0, xmmword ptr [rcx]
0x180070760  movdqu  xmmword ptr [rbp+0E0h+Uuid.Data1], xmm0
0x180070765  mov     ecx, [rdi+20h]
0x180070768  mov     r14d, 1
0x18007076e  movsxd  rsi, dword ptr [rdi+24h]
0x180070772  test    r14b, cl
0x180070775  jz      short loc_180070781
0x180070777  mov     al, [rdi+28h]
0x18007077a  mov     byte ptr [rbp+0E0h+var_110], al
0x18007077d  mov     dword ptr [rbp+0E0h+var_118], r14d
0x180070781  mov     ebx, 2
0x180070786  mov     eax, ecx
0x180070788  and     eax, ebx
0x18007078a  lea     edx, [rbx+1]
0x18007078d  test    esi, esi
0x18007078f  jnz     short loc_1800707AB
0x180070791  test    eax, eax
0x180070793  jz      short loc_18007079E
0x180070795  mov     eax, [rdi+2Ch]
0x180070798  mov     dword ptr [rbp+0E0h+var_148], eax
0x18007079b  mov     dword ptr [rbp+0E0h+var_150], edx
0x18007079e  test    cl, 4
0x1800707a1  jz      short loc_1800707CF
0x1800707a3  mov     eax, [rdi+3Ch]
0x1800707a6  mov     dword ptr [rbp+0E0h+var_158], eax
0x1800707a9  jmp     short loc_1800707CC
0x1800707ab  mov     edx, 0Bh
0x1800707b0  test    eax, eax
0x1800707b2  jz      short loc_1800707BF
0x1800707b4  lea     rax, [rdi+2Ch]
0x1800707b8  mov     dword ptr [rbp+0E0h+var_150], edx
0x1800707bb  mov     [rbp+0E0h+var_148], rax
0x1800707bf  test    cl, 4
0x1800707c2  jz      short loc_1800707CF
0x1800707c4  lea     rax, [rdi+3Ch]
0x1800707c8  mov     [rbp+0E0h+var_158], rax
0x1800707cc  mov     dword ptr [rbp+0E0h+var_160], edx
0x1800707cf  test    cl, 8
0x1800707d2  jz      short loc_1800707DF
0x1800707d4  movzx   eax, word ptr [rdi+4Ch]
0x1800707d8  mov     word ptr [rbp+0E0h+var_120], ax
0x1800707dc  mov     dword ptr [rbp+0E0h+var_128], ebx
0x1800707df  test    cl, 10h
0x1800707e2  jz      short loc_1800707EF
0x1800707e4  movzx   eax, word ptr [rdi+4Eh]
0x1800707e8  mov     word ptr [rbp+0E0h+var_130], ax
0x1800707ec  mov     dword ptr [rbp+0E0h+var_138], ebx
0x1800707ef  mov     rcx, [rdi+50h]
0x1800707f3  call    BfeGuidIsNull
0x1800707f8  test    eax, eax
0x1800707fa  lea     rdx, FWPM_PROVIDER_CONTEXT_SECURE_SOCKET_AUTHIP
0x180070801  cmovz   rdx, rcx
0x180070805  mov     rcx, [rdi+60h]
0x180070809  mov     [rbp+0E0h+var_108], rdx
0x18007080d  call    BfeGuidIsNull
0x180070812  test    eax, eax
0x180070814  lea     r13, FWPM_PROVIDER_CONTEXT_SECURE_SOCKET_IPSEC
0x18007081b  cmovz   r13, rcx
0x18007081f  xor     r8d, r8d
0x180070822  mov     rdx, r13
0x180070825  mov     ecx, r14d
0x180070828  call    BfeObjectFindPublicStateByKey
0x18007082d  test    rax, rax
0x180070830  jnz     short loc_180070844
0x180070832  mov     r8d, 80320006h
0x180070838  lea     rdx, aBfesecuresocke_1; "BfeSecureSocketAdd"
0x18007083f  jmp     loc_180070750
0x180070844  cmp     dword ptr [rax+40h], 3
0x180070848  jz      short loc_180070852
0x18007084a  mov     r8d, 80320034h
0x180070850  jmp     short loc_180070838
0x180070852  mov     rax, [rax+48h]
0x180070856  mov     r15d, [rax+10h]
0x18007085a  and     r15d, ebx
0x18007085d  jnz     short loc_180070865
0x18007085f  test    byte ptr [rax+10h], 4
0x180070863  jz      short loc_18007086D
0x180070865  mov     qword ptr [rbp+0E0h+var_F8+8], rbx
0x180070869  mov     qword ptr [rbp+0E0h+var_F8], r14
0x18007086d  movups  xmm0, xmmword ptr [rbp+0E0h+Uuid.Data1]
0x180070871  xor     r9d, r9d
0x180070874  xor     r8d, r8d
0x180070877  movups  xmm1, xmmword ptr [rdi+10h]
0x18007087b  lea     rdx, [rbp+0E0h+var_C8]
0x18007087f  movdqu  [rbp+0E0h+var_C8], xmm0
0x180070884  lea     r14d, [r9+6]
0x180070888  mov     ecx, r14d
0x18007088b  movdqu  [rbp+0E0h+var_B8], xmm1
0x180070890  call    BfeObjectAddCopy
0x180070895  mov     rbx, rax
0x180070898  test    rax, rax
0x18007089b  jnz     loc_180070CCE
0x1800708a1  xor     r8d, r8d
0x1800708a4  lea     rdx, [rbp+0E0h+Uuid]
0x1800708a8  mov     ecx, r14d
0x1800708ab  call    BfeObjectFindPrivateStateByKey
0x1800708b0  mov     r12, rax
0x1800708b3  mov     [rbp+0E0h+var_E8], ebx
0x1800708b6  lea     rax, [rbp+0E0h+var_A0]
0x1800708ba  xor     r14d, r14d
0x1800708bd  mov     qword ptr [rbp+0E0h+var_E4+4], rax
0x1800708c1  lea     r10, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x1800708c8  lea     r8, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x1800708cf  lea     rbx, FWPM_CONDITION_IP_LOCAL_PORT
0x1800708d6  lea     r11, FWPM_CONDITION_IP_REMOTE_PORT
0x1800708dd  lea     rdx, __ImageBase
0x1800708e4  cmp     r14d, 2
0x1800708e8  jge     loc_1800709B0
0x1800708ee  movsxd  rcx, r14d
0x1800708f1  lea     rax, [rbp+0E0h+var_E8]
0x1800708f5  mov     [rsp+200h+var_170], rax
0x1800708fd  lea     rax, [rbp+0E0h+var_138]
0x180070901  mov     [rsp+200h+var_178], rax
0x180070909  lea     rax, [rbp+0E0h+var_128]
0x18007090d  mov     [rsp+200h+var_180], r11
0x180070915  mov     [rsp+200h+var_188], rax
0x18007091a  lea     r9, [rsi+rcx*2]
0x18007091e  mov     [rsp+200h+var_190], rbx
0x180070923  lea     rax, [rbp+0E0h+var_160]
0x180070927  mov     [rsp+200h+var_198], rax
0x18007092c  add     r9, rcx
0x18007092f  mov     [rsp+200h+var_1A0], r8
0x180070934  lea     rax, [rbp+0E0h+var_150]
0x180070938  mov     r8, [rbp+0E0h+var_140]
0x18007093c  mov     [rsp+200h+var_1A8], rax
0x180070941  lea     rax, [rbp+0E0h+var_118]
0x180070945  mov     [rsp+200h+var_1B0], r10
0x18007094a  mov     [rsp+200h+var_1B8], rax
0x18007094f  lea     rax, FWPM_CONDITION_IP_PROTOCOL
0x180070956  mov     [rsp+200h+var_1C0], rax
0x18007095b  mov     rax, ds:rva off_1800B0830[rdx+r9*8]
0x180070963  mov     [rsp+200h+var_1C8], rax
0x180070968  mov     rax, qword ptr [rbp+rcx*8+0E0h+var_F8]
0x18007096d  mov     rcx, r12
0x180070970  mov     [rsp+200h+var_1D0], rax
0x180070975  movzx   eax, ds:rva word_1800C0D28[rdx+r9*2]
0x18007097e  mov     r9, ds:rva off_1800984B0[rdx+r9*8]
0x180070986  mov     rdx, rdi
0x180070989  mov     [rsp+200h+var_1D8], 0
0x180070992  mov     [rsp+200h+var_1E0], ax
0x180070997  call    BfeSecureSocketAddFilter
0x18007099c  mov     rbx, rax
0x18007099f  test    rax, rax
0x1800709a2  jnz     loc_180070CB6
0x1800709a8  inc     r14d
0x1800709ab  jmp     loc_1800708C1
0x1800709b0  mov     r14, [rbp+0E0h+var_140]
0x1800709b4  test    r15d, r15d
0x1800709b7  jz      loc_180070D0B
0x1800709bd  mov     ecx, [rdi+20h]
0x1800709c0  lea     rax, [rbp+0E0h+var_E8]
0x1800709c4  mov     r9, ds:rva off_1800986D8[rdx+rsi*8]
0x1800709cc  xor     r15d, r15d
0x1800709cf  mov     [rsp+200h+var_170], rax
0x1800709d7  lea     rax, [rbp+0E0h+var_138]
0x1800709db  mov     [rsp+200h+var_178], rax
0x1800709e3  lea     rax, [rbp+0E0h+var_128]
0x1800709e7  mov     [rsp+200h+var_180], r11
0x1800709ef  mov     [rsp+200h+var_188], rax
0x1800709f4  lea     rax, [rbp+0E0h+var_160]
0x1800709f8  mov     [rsp+200h+var_190], rbx
0x1800709fd  mov     [rsp+200h+var_198], rax
0x180070a02  lea     rax, [rbp+0E0h+var_150]
0x180070a06  mov     [rsp+200h+var_1A0], r8
0x180070a0b  mov     r8, r14
0x180070a0e  mov     [rsp+200h+var_1A8], rax
0x180070a13  lea     rax, [rbp+0E0h+var_118]
0x180070a17  mov     [rsp+200h+var_1B0], r10
0x180070a1c  mov     [rsp+200h+var_1B8], rax
0x180070a21  lea     rax, FWPM_CONDITION_IP_PROTOCOL
0x180070a28  mov     [rsp+200h+var_1C0], rax
0x180070a2d  mov     rax, ds:rva off_1800B08D8[rdx+rsi*8]
0x180070a35  mov     [rsp+200h+var_1C8], rax
0x180070a3a  movzx   eax, ds:rva word_1800C0DB2[rdx+rsi*2]
0x180070a42  mov     rdx, rdi
0x180070a45  shr     rcx, 0Bh
0x180070a49  and     ecx, 20h
0x180070a4c  mov     [rsp+200h+var_1D0], rcx
0x180070a51  mov     rcx, r12
0x180070a54  mov     [rsp+200h+var_1D8], r15
0x180070a59  mov     [rsp+200h+var_1E0], ax
0x180070a5e  call    BfeSecureSocketAddFilter
0x180070a63  mov     rbx, rax
0x180070a66  test    rax, rax
0x180070a69  jnz     loc_180070CB6
0x180070a6f  lea     rdx, __ImageBase
0x180070a76  lea     r8, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x180070a7d  lea     r10, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x180070a84  mov     r9, ds:rva off_180098780[rdx+rsi*8]
0x180070a8c  lea     rax, [rbp+0E0h+var_E8]
0x180070a90  mov     [rsp+200h+var_170], rax
0x180070a98  mov     rcx, r12
0x180070a9b  mov     [rsp+200h+var_178], r15
0x180070aa3  lea     rax, [rbp+0E0h+var_160]
0x180070aa7  mov     [rsp+200h+var_180], r15
0x180070aaf  mov     [rsp+200h+var_188], r15
0x180070ab4  mov     [rsp+200h+var_190], r15
0x180070ab9  mov     [rsp+200h+var_198], r15
0x180070abe  mov     [rsp+200h+var_1A0], r15
0x180070ac3  mov     [rsp+200h+var_1A8], rax
0x180070ac8  lea     rax, [rbp+0E0h+var_150]
0x180070acc  mov     [rsp+200h+var_1B0], r8
0x180070ad1  mov     r8, r14
0x180070ad4  mov     [rsp+200h+var_1B8], rax
0x180070ad9  mov     rax, [rbp+0E0h+var_108]
0x180070add  mov     [rsp+200h+var_1C0], r10
0x180070ae2  mov     [rsp+200h+var_1C8], r15
0x180070ae7  mov     [rsp+200h+var_1D0], r15
0x180070aec  mov     [rsp+200h+var_1D8], rax
0x180070af1  movzx   eax, ds:rva word_1800C0DDC[rdx+rsi*2]
0x180070af9  mov     rdx, rdi
0x180070afc  mov     [rsp+200h+var_1E0], ax
0x180070b01  call    BfeSecureSocketAddFilter
0x180070b06  mov     rbx, rax
0x180070b09  test    rax, rax
0x180070b0c  jnz     loc_180070CB6
0x180070b12  mov     rcx, [rdi+58h]
0x180070b16  call    BfeGuidIsNull
0x180070b1b  test    eax, eax
0x180070b1d  jnz     loc_180070BC3
0x180070b23  lea     rax, [rbp+0E0h+var_E8]
0x180070b27  mov     r8, r14
0x180070b2a  mov     [rsp+200h+var_170], rax
0x180070b32  lea     r9, __ImageBase
0x180070b39  mov     [rsp+200h+var_178], r15
0x180070b41  lea     rax, [rbp+0E0h+var_160]
0x180070b45  mov     [rsp+200h+var_180], r15
0x180070b4d  mov     rdx, rdi
0x180070b50  mov     [rsp+200h+var_188], r15
0x180070b55  mov     [rsp+200h+var_190], r15
0x180070b5a  mov     [rsp+200h+var_198], r15
0x180070b5f  mov     [rsp+200h+var_1A0], r15
0x180070b64  mov     [rsp+200h+var_1A8], rax
0x180070b69  lea     rax, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x180070b70  mov     [rsp+200h+var_1B0], rax
0x180070b75  lea     rax, [rbp+0E0h+var_150]
0x180070b79  mov     [rsp+200h+var_1B8], rax
0x180070b7e  lea     rax, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x180070b85  mov     [rsp+200h+var_1C0], rax
0x180070b8a  movzx   eax, ds:rva word_1800C0DDC[r9+rsi*2]
0x180070b93  mov     r9, ds:rva off_180098780[r9+rsi*8]
0x180070b9b  mov     [rsp+200h+var_1C8], r15
0x180070ba0  mov     [rsp+200h+var_1D0], r15
0x180070ba5  mov     [rsp+200h+var_1D8], rcx
0x180070baa  mov     rcx, r12
0x180070bad  mov     [rsp+200h+var_1E0], ax
0x180070bb2  call    BfeSecureSocketAddFilter
0x180070bb7  mov     rbx, rax
0x180070bba  test    rax, rax
0x180070bbd  jnz     loc_180070CB6
  ... truncated ...
```
