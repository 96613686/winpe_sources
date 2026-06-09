# MSCryptRsaEncrypt

- ea: `0x18003c180`
- end: `0x18003c421`
- name: `MSCryptRsaEncrypt`
- size: `673`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18003c180`
- `0x18003cfd4`
- `0x18003d6a4`
- `0x18003d968`
- `0x18003dbf0`
- `0x180056cf0`
- `0x1800754cc`

## string_xrefs

- `0x18003c2f5`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003c375`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003c3ee`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaEncrypt(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        __int64 a7,
        unsigned int a8,
        _DWORD *a9,
        int a10)
{
  __int64 v11; // rdi
  int v12; // r8d
  __int64 v14; // rax
  _QWORD *v15; // r9
  __int64 v16; // rsi
  __int64 v17; // rcx
  unsigned int v18; // eax
  unsigned int v19; // ebx
  __int64 result; // rax
  _QWORD *v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rcx
  int v24; // [rsp+20h] [rbp-88h]
  int v25; // [rsp+30h] [rbp-78h]
  char v26; // [rsp+30h] [rbp-78h]
  int v27; // [rsp+38h] [rbp-70h]
  __int64 v28[9]; // [rsp+60h] [rbp-48h] BYREF

  LODWORD(v11) = 0;
  v12 = a10;
  if ( (a10 & 0xFFFFFFF8) != 0 )
  {
    v19 = -1073741811;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v26 = -78;
LABEL_23:
    WPP_SF_sDsd(
      v21[2],
      a2,
      v12,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      v26);
    goto LABEL_19;
  }
  v14 = validateMSCryptRsaKey(a1);
  v16 = v14;
  if ( !v14 || !*(_DWORD *)(v14 + 16) )
  {
    v19 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        v12,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        188);
    goto LABEL_19;
  }
  v17 = *(_QWORD *)(v14 + 32);
  v11 = (unsigned int)(*(_DWORD *)(v17 + 16) + 7) >> 3;
  v28[0] = v11;
  if ( !a7 )
  {
LABEL_18:
    v19 = 0;
    goto LABEL_19;
  }
  if ( a8 < (unsigned int)v11 )
  {
    v19 = -1073741789;
    goto LABEL_19;
  }
  if ( !a2 )
  {
    v22 = 1747;
    goto LABEL_43;
  }
  if ( !v12 || (v12 & 1) != 0 )
  {
    if ( a3 >= (unsigned int)v11 )
    {
      if ( a3 > (unsigned int)v11 )
        a3 = v11;
      v18 = SymCryptRsaRawEncrypt(v17, a2, a3, v24, a7, v11);
      goto LABEL_17;
    }
    v22 = 1760;
LABEL_43:
    v19 = -1073741811;
    v23 = 3221225485LL;
    goto LABEL_37;
  }
  if ( (v12 & 2) != 0 )
  {
    v18 = SymCryptRsaPkcs1Encrypt(v17, v24, a7, v11, (__int64)v28);
    goto LABEL_16;
  }
  if ( (v12 & 4) == 0 )
    goto LABEL_18;
  if ( !v15 || !*v15 )
  {
    v19 = -1073741811;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_19;
    v26 = 17;
    goto LABEL_23;
  }
  if ( GetSymCryptHashAlgorithm(*v15) )
  {
    v18 = SymCryptRsaOaepEncrypt(
            *(_QWORD *)(v16 + 32),
            *(_QWORD *)(a4 + 8),
            *(_DWORD *)(a4 + 16),
            v25,
            v27,
            a7,
            v11,
            (__int64)v28);
LABEL_16:
    LODWORD(v11) = v28[0];
LABEL_17:
    if ( !v18 )
      goto LABEL_18;
    v19 = SymcryptErrorCodeToNtStatus(v18);
    v23 = v19;
    v22 = 1839;
LABEL_37:
    DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v22);
    goto LABEL_19;
  }
  v19 = -1073741811;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v26 = 25;
    goto LABEL_23;
  }
LABEL_19:
  result = v19;
  *a9 = v11;
  return result;
}

```

## disassembly

```asm
0x18003c180  push    rbx
0x18003c182  push    rbp
0x18003c183  push    rsi
0x18003c184  push    rdi
0x18003c185  push    r14
0x18003c187  push    r15
0x18003c189  sub     rsp, 78h
0x18003c18d  mov     ebx, r8d
0x18003c190  xor     edi, edi
0x18003c192  mov     r8d, [rsp+0A8h+arg_48]
0x18003c19a  mov     r14, r9
0x18003c19d  mov     rbp, rdx
0x18003c1a0  test    r8d, 0FFFFFFF8h
0x18003c1a7  jnz     loc_18003C2CF
0x18003c1ad  call    validateMSCryptRsaKey
0x18003c1b2  mov     rsi, rax
0x18003c1b5  test    rax, rax
0x18003c1b8  jz      loc_18003C347
0x18003c1be  cmp     [rax+10h], edi
0x18003c1c1  jz      loc_18003C347
0x18003c1c7  mov     rcx, [rax+20h]; int
0x18003c1cb  mov     r15, [rsp+0A8h+arg_30]
0x18003c1d3  mov     edi, [rcx+10h]
0x18003c1d6  add     edi, 7
0x18003c1d9  shr     edi, 3
0x18003c1dc  mov     [rsp+0A8h+var_48], rdi
0x18003c1e1  test    r15, r15
0x18003c1e4  jz      loc_18003C2B3
0x18003c1ea  cmp     [rsp+0A8h+arg_38], edi
0x18003c1f1  jb      loc_18003C3C1
0x18003c1f7  test    rdx, rdx
0x18003c1fa  jz      loc_18003C3CB
0x18003c200  test    r8d, r8d
0x18003c203  jz      loc_18003C3FF
0x18003c209  test    r8b, 1
0x18003c20d  jnz     loc_18003C3FF
0x18003c213  test    r8b, 2
0x18003c217  jnz     short loc_18003C285
0x18003c219  test    r8b, 4
0x18003c21d  jz      loc_18003C2B3
0x18003c223  test    r9, r9
0x18003c226  jz      loc_18003C31B
0x18003c22c  mov     rcx, [r9]
0x18003c22f  test    rcx, rcx
0x18003c232  jz      loc_18003C31B
0x18003c238  call    GetSymCryptHashAlgorithm
0x18003c23d  mov     r9, rax
0x18003c240  test    rax, rax
0x18003c243  jz      loc_18003C38E
0x18003c249  mov     eax, [r14+10h]
0x18003c24d  lea     rcx, [rsp+0A8h+var_48]
0x18003c252  mov     [rsp+0A8h+var_58], rcx; __int64
0x18003c257  cmp     ebx, edi
0x18003c259  mov     rcx, [rsi+20h]; int
0x18003c25d  mov     rdx, rbp
0x18003c260  mov     [rsp+0A8h+var_60], rdi; __int64
0x18003c265  cmova   ebx, edi
0x18003c268  mov     [rsp+0A8h+var_68], r15; __int64
0x18003c26d  mov     [rsp+0A8h+var_80], rax; int
0x18003c272  mov     rax, [r14+8]
0x18003c276  mov     r8d, ebx
0x18003c279  mov     [rsp+0A8h+var_88], rax; __int64
0x18003c27e  call    SymCryptRsaOaepEncrypt
0x18003c283  jmp     short loc_18003C2A6
0x18003c285  cmp     ebx, edi
0x18003c287  lea     rax, [rsp+0A8h+var_48]
0x18003c28c  mov     [rsp+0A8h+var_70], rax; __int64
0x18003c291  cmova   ebx, edi
0x18003c294  mov     [rsp+0A8h+var_78], rdi; __int64
0x18003c299  mov     r8d, ebx
0x18003c29c  mov     [rsp+0A8h+var_80], r15; __int64
0x18003c2a1  call    SymCryptRsaPkcs1Encrypt
0x18003c2a6  mov     rdi, [rsp+0A8h+var_48]
0x18003c2ab  test    eax, eax
0x18003c2ad  jnz     loc_18003C3D6
0x18003c2b3  xor     ebx, ebx
0x18003c2b5  mov     rcx, [rsp+0A8h+arg_40]
0x18003c2bd  mov     eax, ebx
0x18003c2bf  mov     [rcx], edi
0x18003c2c1  add     rsp, 78h
0x18003c2c5  pop     r15
0x18003c2c7  pop     r14
0x18003c2c9  pop     rdi
0x18003c2ca  pop     rsi
0x18003c2cb  pop     rbp
0x18003c2cc  pop     rbx
0x18003c2cd  retn
0x18003c2cf  mov     ebx, 0C000000Dh
0x18003c2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c2db  lea     rax, WPP_GLOBAL_Control
0x18003c2e2  cmp     rcx, rax
0x18003c2e5  jz      short loc_18003C2B5
0x18003c2e7  test    byte ptr [rcx+1Ch], 1
0x18003c2eb  jz      short loc_18003C2B5
0x18003c2ed  mov     dword ptr [rsp+0A8h+var_78], 6B2h
0x18003c2f5  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c2fc  mov     [rsp+0A8h+var_80], rax
0x18003c301  mov     dword ptr [rsp+0A8h+var_88], 0C000000Dh
0x18003c309  mov     rcx, [rcx+10h]
0x18003c30d  lea     r9, aStatus; "Status"
0x18003c314  call    WPP_SF_sDsd
0x18003c319  jmp     short loc_18003C2B5
0x18003c31b  mov     ebx, 0C000000Dh
0x18003c320  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c327  lea     rax, WPP_GLOBAL_Control
0x18003c32e  cmp     rcx, rax
0x18003c331  jz      short loc_18003C2B5
0x18003c333  test    byte ptr [rcx+1Ch], 1
0x18003c337  jz      loc_18003C2B5
0x18003c33d  mov     dword ptr [rsp+0A8h+var_78], 711h
0x18003c345  jmp     short loc_18003C2F5
0x18003c347  mov     ebx, 0C0000008h
0x18003c34c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c353  lea     rax, WPP_GLOBAL_Control
0x18003c35a  cmp     rcx, rax
0x18003c35d  jz      loc_18003C2B5
0x18003c363  test    byte ptr [rcx+1Ch], 1
0x18003c367  jz      loc_18003C2B5
0x18003c36d  mov     dword ptr [rsp+0A8h+var_78], 6BCh
0x18003c375  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c37c  mov     [rsp+0A8h+var_80], rax
0x18003c381  mov     dword ptr [rsp+0A8h+var_88], 0C0000008h
0x18003c389  jmp     loc_18003C309
0x18003c38e  mov     ebx, 0C000000Dh
0x18003c393  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c39a  lea     rax, WPP_GLOBAL_Control
0x18003c3a1  cmp     rcx, rax
0x18003c3a4  jz      loc_18003C2B5
0x18003c3aa  test    byte ptr [rcx+1Ch], 1
0x18003c3ae  jz      loc_18003C2B5
0x18003c3b4  mov     dword ptr [rsp+0A8h+var_78], 719h
0x18003c3bc  jmp     loc_18003C2F5
0x18003c3c1  mov     ebx, 0C0000023h
0x18003c3c6  jmp     loc_18003C2B5
0x18003c3cb  mov     r9d, 6D3h
0x18003c3d1  jmp     loc_180081EC6
0x18003c3d6  mov     ecx, eax
0x18003c3d8  call    SymcryptErrorCodeToNtStatus
0x18003c3dd  mov     ebx, eax
0x18003c3df  mov     ecx, eax
0x18003c3e1  mov     r9d, 72Fh
0x18003c3e7  lea     rdx, aStatus; "Status"
0x18003c3ee  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003c3f5  call    DebugTraceError
0x18003c3fa  jmp     loc_18003C2B5
0x18003c3ff  cmp     ebx, edi
0x18003c401  jb      loc_180081EC0
0x18003c407  cmova   ebx, edi
0x18003c40a  mov     [rsp+0A8h+var_78], rdi; __int64
0x18003c40f  mov     r8d, ebx; int
0x18003c412  mov     [rsp+0A8h+var_80], r15; __int64
0x18003c417  call    SymCryptRsaRawEncrypt
0x18003c41c  jmp     loc_18003C2AB
0x180081ec0  mov     r9d, 6E0h
0x180081ec6  mov     ebx, 0C000000Dh
0x180081ecb  mov     ecx, 0C000000Dh
0x180081ed0  jmp     loc_18003C3E7
```
