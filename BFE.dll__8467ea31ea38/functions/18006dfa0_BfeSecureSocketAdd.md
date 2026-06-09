# BfeSecureSocketAdd

- ea: `0x18006dfa0`
- end: `0x18006e60c`
- name: `BfeSecureSocketAdd`
- size: `1644`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180063e40`

## callees

- `0x18000bc28`
- `0x18000e240`
- `0x18001236c`
- `0x180018b74`
- `0x180020c30`
- `0x180020c60`
- `0x180020c88`
- `0x18002e69c`
- `0x180058b30`
- `0x18006dfa0`
- `0x18006e614`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18006e036`
- `RPCRT4!UuidCreate` at `0x18006e036`

## string_xrefs

- `0x18006e043`: `UuidCreate`
- `0x18006e59c`: `BfeFwpsSecureSocketFiltersCopy`

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
  v10 = BfeObjectAddCopy(6u, (__int64)&v47, 0, 0);
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
            (unsigned int)off_1800954C0[v25],
            word_1800BDD38[v25],
            0,
            *((_QWORD *)&v43 + v24),
            (__int64)off_1800AD840[v25],
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
                (unsigned int)off_1800956E8[v12],
                word_1800BDDC2[v12],
                0,
                (*(_DWORD *)(a1 + 32) >> 11) & 0x20,
                (__int64)off_1800AD8E8[v12],
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
                (unsigned int)off_180095790[v12],
                word_1800BDDEC[v12],
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
                (unsigned int)off_180095790[v12],
                word_1800BDDEC[v12],
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
                (unsigned int)off_180095760[v12],
                word_1800BDDE0[v12],
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
0x18006dfa0  mov     [rsp-8+arg_18], rbx
0x18006dfa5  push    rbp
0x18006dfa6  push    rsi
0x18006dfa7  push    rdi
0x18006dfa8  push    r12
0x18006dfaa  push    r13
0x18006dfac  push    r14
0x18006dfae  push    r15
0x18006dfb0  lea     rbp, [rsp-0B0h]
0x18006dfb8  sub     rsp, 1D0h
0x18006dfbf  mov     rax, cs:__security_cookie
0x18006dfc6  xor     rax, rsp
0x18006dfc9  mov     [rbp+0E0h+var_40], rax
0x18006dfd0  xor     eax, eax
0x18006dfd2  mov     [rbp+0E0h+var_100], r8
0x18006dfd6  xor     r15d, r15d
0x18006dfd9  mov     qword ptr [rbp+0E0h+var_E4], rax
0x18006dfdd  xorps   xmm0, xmm0
0x18006dfe0  mov     [rbp-8], rax
0x18006dfe4  xorps   xmm1, xmm1
0x18006dfe7  mov     [rbp+0E0h+var_140], rdx
0x18006dfeb  mov     rdi, rcx
0x18006dfee  mov     [rbp+0E0h+var_118], r15
0x18006dff2  movups  xmmword ptr [rbp+0E0h+Uuid.Data1], xmm0
0x18006dff6  mov     [rbp+0E0h+var_110], rax
0x18006dffa  mov     r12d, r15d
0x18006dffd  mov     [rbp+0E0h+var_150], r15
0x18006e001  mov     [rbp+0E0h+var_148], rax
0x18006e005  mov     [rbp+0E0h+var_160], r15
0x18006e009  mov     [rbp+0E0h+var_158], rax
0x18006e00d  mov     [rbp+0E0h+var_128], r15
0x18006e011  mov     [rbp+0E0h+var_120], rax
0x18006e015  mov     [rbp+0E0h+var_138], r15
0x18006e019  mov     [rbp+0E0h+var_130], rax
0x18006e01d  movups  [rbp+0E0h+var_F8], xmm0
0x18006e021  movups  [rbp+0E0h+var_C8], xmm1
0x18006e025  movups  [rbp+0E0h+var_B8], xmm1
0x18006e029  call    BfeGuidIsNull
0x18006e02e  test    eax, eax
0x18006e030  jz      short loc_18006E057
0x18006e032  lea     rcx, [rbp+0E0h+Uuid]; Uuid
0x18006e036  call    cs:__imp_UuidCreate
0x18006e03c  test    eax, eax
0x18006e03e  jz      short loc_18006E05F
0x18006e040  mov     r8d, eax
0x18006e043  lea     rdx, aUuidcreate; "UuidCreate"
0x18006e04a  call    WfpReportSysErrorAsWinError
0x18006e04f  mov     rbx, rax
0x18006e052  jmp     loc_18006E5AB
0x18006e057  movups  xmm0, xmmword ptr [rcx]
0x18006e05a  movdqu  xmmword ptr [rbp+0E0h+Uuid.Data1], xmm0
0x18006e05f  mov     ecx, [rdi+20h]
0x18006e062  mov     r14d, 1
0x18006e068  movsxd  rsi, dword ptr [rdi+24h]
0x18006e06c  test    r14b, cl
0x18006e06f  jz      short loc_18006E07B
0x18006e071  mov     al, [rdi+28h]
0x18006e074  mov     byte ptr [rbp+0E0h+var_110], al
0x18006e077  mov     dword ptr [rbp+0E0h+var_118], r14d
0x18006e07b  mov     ebx, 2
0x18006e080  mov     eax, ecx
0x18006e082  and     eax, ebx
0x18006e084  lea     edx, [rbx+1]
0x18006e087  test    esi, esi
0x18006e089  jnz     short loc_18006E0A5
0x18006e08b  test    eax, eax
0x18006e08d  jz      short loc_18006E098
0x18006e08f  mov     eax, [rdi+2Ch]
0x18006e092  mov     dword ptr [rbp+0E0h+var_148], eax
0x18006e095  mov     dword ptr [rbp+0E0h+var_150], edx
0x18006e098  test    cl, 4
0x18006e09b  jz      short loc_18006E0C9
0x18006e09d  mov     eax, [rdi+3Ch]
0x18006e0a0  mov     dword ptr [rbp+0E0h+var_158], eax
0x18006e0a3  jmp     short loc_18006E0C6
0x18006e0a5  mov     edx, 0Bh
0x18006e0aa  test    eax, eax
0x18006e0ac  jz      short loc_18006E0B9
0x18006e0ae  lea     rax, [rdi+2Ch]
0x18006e0b2  mov     dword ptr [rbp+0E0h+var_150], edx
0x18006e0b5  mov     [rbp+0E0h+var_148], rax
0x18006e0b9  test    cl, 4
0x18006e0bc  jz      short loc_18006E0C9
0x18006e0be  lea     rax, [rdi+3Ch]
0x18006e0c2  mov     [rbp+0E0h+var_158], rax
0x18006e0c6  mov     dword ptr [rbp+0E0h+var_160], edx
0x18006e0c9  test    cl, 8
0x18006e0cc  jz      short loc_18006E0D9
0x18006e0ce  movzx   eax, word ptr [rdi+4Ch]
0x18006e0d2  mov     word ptr [rbp+0E0h+var_120], ax
0x18006e0d6  mov     dword ptr [rbp+0E0h+var_128], ebx
0x18006e0d9  test    cl, 10h
0x18006e0dc  jz      short loc_18006E0E9
0x18006e0de  movzx   eax, word ptr [rdi+4Eh]
0x18006e0e2  mov     word ptr [rbp+0E0h+var_130], ax
0x18006e0e6  mov     dword ptr [rbp+0E0h+var_138], ebx
0x18006e0e9  mov     rcx, [rdi+50h]
0x18006e0ed  call    BfeGuidIsNull
0x18006e0f2  test    eax, eax
0x18006e0f4  lea     rdx, FWPM_PROVIDER_CONTEXT_SECURE_SOCKET_AUTHIP
0x18006e0fb  cmovz   rdx, rcx
0x18006e0ff  mov     rcx, [rdi+60h]
0x18006e103  mov     [rbp+0E0h+var_108], rdx
0x18006e107  call    BfeGuidIsNull
0x18006e10c  test    eax, eax
0x18006e10e  lea     r13, FWPM_PROVIDER_CONTEXT_SECURE_SOCKET_IPSEC
0x18006e115  cmovz   r13, rcx
0x18006e119  xor     r8d, r8d
0x18006e11c  mov     rdx, r13
0x18006e11f  mov     ecx, r14d
0x18006e122  call    BfeObjectFindPublicStateByKey
0x18006e127  test    rax, rax
0x18006e12a  jnz     short loc_18006E13E
0x18006e12c  mov     r8d, 80320006h
0x18006e132  lea     rdx, aBfesecuresocke_1; "BfeSecureSocketAdd"
0x18006e139  jmp     loc_18006E04A
0x18006e13e  cmp     dword ptr [rax+40h], 3
0x18006e142  jz      short loc_18006E14C
0x18006e144  mov     r8d, 80320034h
0x18006e14a  jmp     short loc_18006E132
0x18006e14c  mov     rax, [rax+48h]
0x18006e150  mov     r15d, [rax+10h]
0x18006e154  and     r15d, ebx
0x18006e157  jnz     short loc_18006E15F
0x18006e159  test    byte ptr [rax+10h], 4
0x18006e15d  jz      short loc_18006E167
0x18006e15f  mov     qword ptr [rbp+0E0h+var_F8+8], rbx
0x18006e163  mov     qword ptr [rbp+0E0h+var_F8], r14
0x18006e167  movups  xmm0, xmmword ptr [rbp+0E0h+Uuid.Data1]
0x18006e16b  xor     r9d, r9d
0x18006e16e  xor     r8d, r8d
0x18006e171  movups  xmm1, xmmword ptr [rdi+10h]
0x18006e175  lea     rdx, [rbp+0E0h+var_C8]
0x18006e179  movdqu  [rbp+0E0h+var_C8], xmm0
0x18006e17e  lea     r14d, [r9+6]
0x18006e182  mov     ecx, r14d
0x18006e185  movdqu  [rbp+0E0h+var_B8], xmm1
0x18006e18a  call    BfeObjectAddCopy
0x18006e18f  mov     rbx, rax
0x18006e192  test    rax, rax
0x18006e195  jnz     loc_18006E5C8
0x18006e19b  xor     r8d, r8d
0x18006e19e  lea     rdx, [rbp+0E0h+Uuid]
0x18006e1a2  mov     ecx, r14d
0x18006e1a5  call    BfeObjectFindPrivateStateByKey
0x18006e1aa  mov     r12, rax
0x18006e1ad  mov     [rbp+0E0h+var_E8], ebx
0x18006e1b0  lea     rax, [rbp+0E0h+var_A0]
0x18006e1b4  xor     r14d, r14d
0x18006e1b7  mov     qword ptr [rbp+0E0h+var_E4+4], rax
0x18006e1bb  lea     r10, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x18006e1c2  lea     r8, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x18006e1c9  lea     rbx, FWPM_CONDITION_IP_LOCAL_PORT
0x18006e1d0  lea     r11, FWPM_CONDITION_IP_REMOTE_PORT
0x18006e1d7  lea     rdx, __ImageBase
0x18006e1de  cmp     r14d, 2
0x18006e1e2  jge     loc_18006E2AA
0x18006e1e8  movsxd  rcx, r14d
0x18006e1eb  lea     rax, [rbp+0E0h+var_E8]
0x18006e1ef  mov     [rsp+200h+var_170], rax
0x18006e1f7  lea     rax, [rbp+0E0h+var_138]
0x18006e1fb  mov     [rsp+200h+var_178], rax
0x18006e203  lea     rax, [rbp+0E0h+var_128]
0x18006e207  mov     [rsp+200h+var_180], r11
0x18006e20f  mov     [rsp+200h+var_188], rax
0x18006e214  lea     r9, [rsi+rcx*2]
0x18006e218  mov     [rsp+200h+var_190], rbx
0x18006e21d  lea     rax, [rbp+0E0h+var_160]
0x18006e221  mov     [rsp+200h+var_198], rax
0x18006e226  add     r9, rcx
0x18006e229  mov     [rsp+200h+var_1A0], r8
0x18006e22e  lea     rax, [rbp+0E0h+var_150]
0x18006e232  mov     r8, [rbp+0E0h+var_140]
0x18006e236  mov     [rsp+200h+var_1A8], rax
0x18006e23b  lea     rax, [rbp+0E0h+var_118]
0x18006e23f  mov     [rsp+200h+var_1B0], r10
0x18006e244  mov     [rsp+200h+var_1B8], rax
0x18006e249  lea     rax, FWPM_CONDITION_IP_PROTOCOL
0x18006e250  mov     [rsp+200h+var_1C0], rax
0x18006e255  mov     rax, ds:rva off_1800AD840[rdx+r9*8]
0x18006e25d  mov     [rsp+200h+var_1C8], rax
0x18006e262  mov     rax, qword ptr [rbp+rcx*8+0E0h+var_F8]
0x18006e267  mov     rcx, r12
0x18006e26a  mov     [rsp+200h+var_1D0], rax
0x18006e26f  movzx   eax, ds:rva word_1800BDD38[rdx+r9*2]
0x18006e278  mov     r9, ds:rva off_1800954C0[rdx+r9*8]
0x18006e280  mov     rdx, rdi
0x18006e283  mov     [rsp+200h+var_1D8], 0
0x18006e28c  mov     [rsp+200h+var_1E0], ax
0x18006e291  call    BfeSecureSocketAddFilter
0x18006e296  mov     rbx, rax
0x18006e299  test    rax, rax
0x18006e29c  jnz     loc_18006E5B0
0x18006e2a2  inc     r14d
0x18006e2a5  jmp     loc_18006E1BB
0x18006e2aa  mov     r14, [rbp+0E0h+var_140]
0x18006e2ae  test    r15d, r15d
0x18006e2b1  jz      loc_18006E604
0x18006e2b7  mov     ecx, [rdi+20h]
0x18006e2ba  lea     rax, [rbp+0E0h+var_E8]
0x18006e2be  mov     r9, ds:rva off_1800956E8[rdx+rsi*8]
0x18006e2c6  xor     r15d, r15d
0x18006e2c9  mov     [rsp+200h+var_170], rax
0x18006e2d1  lea     rax, [rbp+0E0h+var_138]
0x18006e2d5  mov     [rsp+200h+var_178], rax
0x18006e2dd  lea     rax, [rbp+0E0h+var_128]
0x18006e2e1  mov     [rsp+200h+var_180], r11
0x18006e2e9  mov     [rsp+200h+var_188], rax
0x18006e2ee  lea     rax, [rbp+0E0h+var_160]
0x18006e2f2  mov     [rsp+200h+var_190], rbx
0x18006e2f7  mov     [rsp+200h+var_198], rax
0x18006e2fc  lea     rax, [rbp+0E0h+var_150]
0x18006e300  mov     [rsp+200h+var_1A0], r8
0x18006e305  mov     r8, r14
0x18006e308  mov     [rsp+200h+var_1A8], rax
0x18006e30d  lea     rax, [rbp+0E0h+var_118]
0x18006e311  mov     [rsp+200h+var_1B0], r10
0x18006e316  mov     [rsp+200h+var_1B8], rax
0x18006e31b  lea     rax, FWPM_CONDITION_IP_PROTOCOL
0x18006e322  mov     [rsp+200h+var_1C0], rax
0x18006e327  mov     rax, ds:rva off_1800AD8E8[rdx+rsi*8]
0x18006e32f  mov     [rsp+200h+var_1C8], rax
0x18006e334  movzx   eax, ds:rva word_1800BDDC2[rdx+rsi*2]
0x18006e33c  mov     rdx, rdi
0x18006e33f  shr     rcx, 0Bh
0x18006e343  and     ecx, 20h
0x18006e346  mov     [rsp+200h+var_1D0], rcx
0x18006e34b  mov     rcx, r12
0x18006e34e  mov     [rsp+200h+var_1D8], r15
0x18006e353  mov     [rsp+200h+var_1E0], ax
0x18006e358  call    BfeSecureSocketAddFilter
0x18006e35d  mov     rbx, rax
0x18006e360  test    rax, rax
0x18006e363  jnz     loc_18006E5B0
0x18006e369  lea     rdx, __ImageBase
0x18006e370  lea     r8, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x18006e377  lea     r10, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x18006e37e  mov     r9, ds:rva off_180095790[rdx+rsi*8]
0x18006e386  lea     rax, [rbp+0E0h+var_E8]
0x18006e38a  mov     [rsp+200h+var_170], rax
0x18006e392  mov     rcx, r12
0x18006e395  mov     [rsp+200h+var_178], r15
0x18006e39d  lea     rax, [rbp+0E0h+var_160]
0x18006e3a1  mov     [rsp+200h+var_180], r15
0x18006e3a9  mov     [rsp+200h+var_188], r15
0x18006e3ae  mov     [rsp+200h+var_190], r15
0x18006e3b3  mov     [rsp+200h+var_198], r15
0x18006e3b8  mov     [rsp+200h+var_1A0], r15
0x18006e3bd  mov     [rsp+200h+var_1A8], rax
0x18006e3c2  lea     rax, [rbp+0E0h+var_150]
0x18006e3c6  mov     [rsp+200h+var_1B0], r8
0x18006e3cb  mov     r8, r14
0x18006e3ce  mov     [rsp+200h+var_1B8], rax
0x18006e3d3  mov     rax, [rbp+0E0h+var_108]
0x18006e3d7  mov     [rsp+200h+var_1C0], r10
0x18006e3dc  mov     [rsp+200h+var_1C8], r15
0x18006e3e1  mov     [rsp+200h+var_1D0], r15
0x18006e3e6  mov     [rsp+200h+var_1D8], rax
0x18006e3eb  movzx   eax, ds:rva word_1800BDDEC[rdx+rsi*2]
0x18006e3f3  mov     rdx, rdi
0x18006e3f6  mov     [rsp+200h+var_1E0], ax
0x18006e3fb  call    BfeSecureSocketAddFilter
0x18006e400  mov     rbx, rax
0x18006e403  test    rax, rax
0x18006e406  jnz     loc_18006E5B0
0x18006e40c  mov     rcx, [rdi+58h]
0x18006e410  call    BfeGuidIsNull
0x18006e415  test    eax, eax
0x18006e417  jnz     loc_18006E4BD
0x18006e41d  lea     rax, [rbp+0E0h+var_E8]
0x18006e421  mov     r8, r14
0x18006e424  mov     [rsp+200h+var_170], rax
0x18006e42c  lea     r9, __ImageBase
0x18006e433  mov     [rsp+200h+var_178], r15
0x18006e43b  lea     rax, [rbp+0E0h+var_160]
0x18006e43f  mov     [rsp+200h+var_180], r15
0x18006e447  mov     rdx, rdi
0x18006e44a  mov     [rsp+200h+var_188], r15
0x18006e44f  mov     [rsp+200h+var_190], r15
0x18006e454  mov     [rsp+200h+var_198], r15
0x18006e459  mov     [rsp+200h+var_1A0], r15
0x18006e45e  mov     [rsp+200h+var_1A8], rax
0x18006e463  lea     rax, FWPM_CONDITION_IP_REMOTE_ADDRESS
0x18006e46a  mov     [rsp+200h+var_1B0], rax
0x18006e46f  lea     rax, [rbp+0E0h+var_150]
0x18006e473  mov     [rsp+200h+var_1B8], rax
0x18006e478  lea     rax, FWPM_CONDITION_IP_LOCAL_ADDRESS
0x18006e47f  mov     [rsp+200h+var_1C0], rax
0x18006e484  movzx   eax, ds:rva word_1800BDDEC[r9+rsi*2]
0x18006e48d  mov     r9, ds:rva off_180095790[r9+rsi*8]
0x18006e495  mov     [rsp+200h+var_1C8], r15
0x18006e49a  mov     [rsp+200h+var_1D0], r15
0x18006e49f  mov     [rsp+200h+var_1D8], rcx
0x18006e4a4  mov     rcx, r12
0x18006e4a7  mov     [rsp+200h+var_1E0], ax
0x18006e4ac  call    BfeSecureSocketAddFilter
0x18006e4b1  mov     rbx, rax
0x18006e4b4  test    rax, rax
0x18006e4b7  jnz     loc_18006E5B0
0x18006e4bd  lea     rax, [rbp+0E0h+var_E8]
  ... truncated ...
```
