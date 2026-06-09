# MSCryptPqDsaImportKeyPair

- ea: `0x18006aeb0`
- end: `0x18006b1a3`
- name: `MSCryptPqDsaImportKeyPair`
- size: `755`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64 *, _DWORD *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180056cf0`
- `0x18006aeb0`
- `0x18006b940`
- `0x18006b9a4`
- `0x18006b9fc`
- `0x18006ba68`
- `0x18006bcc4`
- `0x180073cf8`
- `0x180073db8`
- `0x180073f7c`
- `0x180075078`
- `0x1800750fc`
- `0x1800752d8`

## string_xrefs

- `0x18006aed7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x18006b06b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x18006b0c7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`
- `0x18006b164`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaImportKeyPair(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        _DWORD *a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v8; // r9
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r8
  __int64 v13; // rdi
  __int64 PqDsaBlobInfoFromType; // rax
  __int64 v15; // r14
  unsigned int v16; // esi
  unsigned int v17; // ecx
  unsigned int v18; // edx
  __int64 PqDsaParameterSetInfoFromName; // rbp
  __int64 PqDsaKey; // rax
  __int64 v21; // rdi
  unsigned int v22; // r12d
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rsi
  unsigned int v27; // eax
  __int64 v28; // rax
  unsigned int v29; // eax
  __int64 v30; // rcx
  __int64 v31; // r9

  if ( !a1 )
  {
    v8 = 1376;
LABEL_3:
    LODWORD(v9) = -1073741811;
    v10 = 3221225485LL;
LABEL_4:
    DebugTraceError(v10, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v8);
    return (unsigned int)v9;
  }
  if ( a2 )
  {
    LODWORD(v9) = -1073741637;
    v8 = 1383;
    v10 = 3221225659LL;
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v8 = 1390;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v8 = 1397;
    goto LABEL_3;
  }
  if ( a5 && a6 >= 0xC )
  {
    if ( (a7 & 0xFFFFFFF7) != 0 )
    {
      v8 = 1411;
      goto LABEL_3;
    }
    v11 = validatePqDsaAlgorithm();
    if ( !v11 )
    {
      LODWORD(v9) = -1073741816;
      v8 = 1419;
      v10 = 3221225480LL;
      goto LABEL_4;
    }
    v13 = *(_QWORD *)(v11 + 16);
    PqDsaBlobInfoFromType = getPqDsaBlobInfoFromType(v13, v12);
    v15 = PqDsaBlobInfoFromType;
    if ( !PqDsaBlobInfoFromType )
    {
      v8 = 1427;
      goto LABEL_3;
    }
    if ( *a5 != *(_DWORD *)(PqDsaBlobInfoFromType + 16) )
    {
      v8 = 1436;
      goto LABEL_3;
    }
    v16 = a5[1];
    v17 = v16 + 12;
    if ( v16 >= 0xFFFFFFF4 )
    {
      v8 = 1449;
LABEL_23:
      LODWORD(v9) = -1073741675;
      v10 = 3221225621LL;
      goto LABEL_4;
    }
    v18 = v17 + a5[2];
    if ( v18 < v17 )
    {
      v8 = 1456;
      goto LABEL_23;
    }
    if ( a6 < v18 )
    {
      v8 = 1463;
      goto LABEL_3;
    }
    PqDsaParameterSetInfoFromName = getPqDsaParameterSetInfoFromName(v13, a5 + 3, v16);
    if ( !PqDsaParameterSetInfoFromName )
    {
      v8 = 1474;
      goto LABEL_3;
    }
    PqDsaKey = createPqDsaKey(v13, a7);
    v21 = PqDsaKey;
    if ( !PqDsaKey )
    {
      LODWORD(v9) = -1073741801;
      v8 = 1482;
      v10 = 3221225495LL;
      goto LABEL_4;
    }
    v22 = v16;
    if ( *(_DWORD *)(PqDsaKey + 8) != 196620 )
    {
      if ( *(_DWORD *)(PqDsaKey + 8) != 196621 )
      {
        LODWORD(v9) = -1073741816;
        v23 = 1543;
        v24 = 3221225480LL;
LABEL_35:
        DebugTraceError(v24, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v23);
LABEL_50:
        freePqDsaKey((void *)v21);
        return (unsigned int)v9;
      }
      v25 = SymCryptCompositeMlDsakeyAllocate(*(unsigned int *)(PqDsaParameterSetInfoFromName + 24));
      v26 = v25;
      if ( !v25 )
      {
        v23 = 1519;
LABEL_38:
        LODWORD(v9) = -1073741801;
        v24 = 3221225495LL;
        goto LABEL_35;
      }
      v27 = SymCryptCompositeMlDsakeySetValue(
              v22 + (_DWORD)a5 + 12,
              a5[2],
              *(_DWORD *)(v15 + 32),
              *(_DWORD *)(v21 + 36),
              v25);
      if ( v27 )
      {
        v9 = (unsigned int)SymcryptErrorCodeToNtStatus(v27);
        DebugTraceError(v9, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", 1532);
        SymCryptCompositeMlDsakeyFree(v26);
        goto LABEL_50;
      }
      goto LABEL_45;
    }
    v28 = SymCryptMlDsakeyAllocate(*(unsigned int *)(PqDsaParameterSetInfoFromName + 24));
    v26 = v28;
    if ( !v28 )
    {
      v23 = 1493;
      goto LABEL_38;
    }
    v29 = SymCryptMlDsakeySetValue(v22 + (_DWORD)a5 + 12, a5[2], *(_DWORD *)(v15 + 32), *(_DWORD *)(v21 + 36), v28);
    if ( !v29 )
    {
LABEL_45:
      *(_QWORD *)(v21 + 40) = v26;
      LODWORD(v9) = 0;
      *(_QWORD *)(v21 + 24) = PqDsaParameterSetInfoFromName;
      *(_DWORD *)(v21 + 32) = 1;
      *a4 = v21;
      return (unsigned int)v9;
    }
    v9 = (unsigned int)SymcryptErrorCodeToNtStatus(v29);
    v30 = v9;
    v31 = 1506;
  }
  else
  {
    v21 = 0;
    LODWORD(v9) = -1073741811;
    v26 = 0;
    v30 = 3221225485LL;
    v31 = 1404;
  }
  DebugTraceError(v30, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v31);
  if ( v26 )
    SymCryptMlDsakeyFree(v26);
  if ( v21 )
    goto LABEL_50;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006aeb0  push    rbx
0x18006aeb2  push    rbp
0x18006aeb3  push    rsi
0x18006aeb4  push    rdi
0x18006aeb5  push    r12
0x18006aeb7  push    r14
0x18006aeb9  push    r15
0x18006aebb  sub     rsp, 30h
0x18006aebf  mov     r15, r9
0x18006aec2  test    rcx, rcx
0x18006aec5  jnz     short loc_18006AEEF
0x18006aec7  mov     r9d, 560h
0x18006aecd  mov     ebx, 0C000000Dh
0x18006aed2  mov     ecx, 0C000000Dh
0x18006aed7  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006aede  lea     rdx, aStatus_0; "status"
0x18006aee5  call    DebugTraceError
0x18006aeea  jmp     loc_18006B191
0x18006aeef  test    rdx, rdx
0x18006aef2  jz      short loc_18006AF06
0x18006aef4  mov     ebx, 0C00000BBh
0x18006aef9  mov     r9d, 567h
0x18006aeff  mov     ecx, 0C00000BBh
0x18006af04  jmp     short loc_18006AED7
0x18006af06  test    r8, r8
0x18006af09  jnz     short loc_18006AF13
0x18006af0b  mov     r9d, 56Eh
0x18006af11  jmp     short loc_18006AECD
0x18006af13  test    r15, r15
0x18006af16  jnz     short loc_18006AF20
0x18006af18  mov     r9d, 575h
0x18006af1e  jmp     short loc_18006AECD
0x18006af20  mov     rbx, [rsp+68h+arg_20]
0x18006af28  test    rbx, rbx
0x18006af2b  jz      loc_18006B150
0x18006af31  cmp     [rsp+68h+arg_28], 0Ch
0x18006af39  jb      loc_18006B150
0x18006af3f  test    [rsp+68h+arg_30], 0FFFFFFF7h
0x18006af4a  jz      short loc_18006AF57
0x18006af4c  mov     r9d, 583h
0x18006af52  jmp     loc_18006AECD
0x18006af57  call    validatePqDsaAlgorithm
0x18006af5c  test    rax, rax
0x18006af5f  jnz     short loc_18006AF76
0x18006af61  mov     ebx, 0C0000008h
0x18006af66  mov     r9d, 58Bh
0x18006af6c  mov     ecx, 0C0000008h
0x18006af71  jmp     loc_18006AED7
0x18006af76  mov     rdi, [rax+10h]
0x18006af7a  mov     rdx, r8
0x18006af7d  mov     rcx, rdi
0x18006af80  call    getPqDsaBlobInfoFromType
0x18006af85  mov     r14, rax
0x18006af88  test    rax, rax
0x18006af8b  jnz     short loc_18006AF98
0x18006af8d  mov     r9d, 593h
0x18006af93  jmp     loc_18006AECD
0x18006af98  mov     eax, [rax+10h]
0x18006af9b  cmp     [rbx], eax
0x18006af9d  jz      short loc_18006AFAA
0x18006af9f  mov     r9d, 59Ch
0x18006afa5  jmp     loc_18006AECD
0x18006afaa  mov     esi, [rbx+4]
0x18006afad  lea     ecx, [rsi+0Ch]
0x18006afb0  cmp     ecx, 0Ch
0x18006afb3  jnb     short loc_18006AFCA
0x18006afb5  mov     r9d, 5A9h
0x18006afbb  mov     ebx, 0C0000095h
0x18006afc0  mov     ecx, 0C0000095h
0x18006afc5  jmp     loc_18006AED7
0x18006afca  mov     edx, [rbx+8]
0x18006afcd  add     edx, ecx
0x18006afcf  cmp     edx, ecx
0x18006afd1  jnb     short loc_18006AFDB
0x18006afd3  mov     r9d, 5B0h
0x18006afd9  jmp     short loc_18006AFBB
0x18006afdb  cmp     [rsp+68h+arg_28], edx
0x18006afe2  jnb     short loc_18006AFEF
0x18006afe4  mov     r9d, 5B7h
0x18006afea  jmp     loc_18006AECD
0x18006afef  lea     rdx, [rbx+0Ch]
0x18006aff3  mov     r8d, esi
0x18006aff6  mov     rcx, rdi
0x18006aff9  call    getPqDsaParameterSetInfoFromName
0x18006affe  mov     rbp, rax
0x18006b001  test    rax, rax
0x18006b004  jnz     short loc_18006B011
0x18006b006  mov     r9d, 5C2h
0x18006b00c  jmp     loc_18006AECD
0x18006b011  mov     edx, [rsp+68h+arg_30]
0x18006b018  mov     rcx, rdi
0x18006b01b  call    createPqDsaKey
0x18006b020  mov     rdi, rax
0x18006b023  test    rax, rax
0x18006b026  jnz     short loc_18006B03D
0x18006b028  mov     ebx, 0C0000017h
0x18006b02d  mov     r9d, 5CAh
0x18006b033  mov     ecx, 0C0000017h
0x18006b038  jmp     loc_18006AED7
0x18006b03d  mov     ecx, [rax+8]
0x18006b040  mov     r12, rsi
0x18006b043  sub     ecx, 3000Ch
0x18006b049  jz      loc_18006B0EF
0x18006b04f  cmp     ecx, 1
0x18006b052  jz      short loc_18006B07C
0x18006b054  mov     ebx, 0C0000008h
0x18006b059  mov     r9d, 607h
0x18006b05f  mov     ecx, 0C0000008h
0x18006b064  lea     rdx, aStatus_0; "status"
0x18006b06b  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006b072  call    DebugTraceError
0x18006b077  jmp     loc_18006B189
0x18006b07c  mov     ecx, [rbp+18h]
0x18006b07f  call    SymCryptCompositeMlDsakeyAllocate
0x18006b084  mov     rsi, rax
0x18006b087  test    rax, rax
0x18006b08a  jnz     short loc_18006B09E
0x18006b08c  mov     r9d, 5EFh
0x18006b092  mov     ebx, 0C0000017h
0x18006b097  mov     ecx, 0C0000017h
0x18006b09c  jmp     short loc_18006B064
0x18006b09e  mov     edx, [rbx+8]
0x18006b0a1  lea     rcx, [rbx+0Ch]
0x18006b0a5  mov     r9d, [rdi+24h]
0x18006b0a9  add     rcx, r12
0x18006b0ac  mov     r8d, [r14+20h]
0x18006b0b0  mov     [rsp+68h+var_48], rsi
0x18006b0b5  call    SymCryptCompositeMlDsakeySetValue
0x18006b0ba  test    eax, eax
0x18006b0bc  jz      short loc_18006B13A
0x18006b0be  mov     ecx, eax
0x18006b0c0  call    SymcryptErrorCodeToNtStatus
0x18006b0c5  mov     ecx, eax
0x18006b0c7  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006b0ce  mov     r9d, 5FCh
0x18006b0d4  lea     rdx, aStatus_0; "status"
0x18006b0db  mov     ebx, eax
0x18006b0dd  call    DebugTraceError
0x18006b0e2  mov     rcx, rsi
0x18006b0e5  call    SymCryptCompositeMlDsakeyFree
0x18006b0ea  jmp     loc_18006B189
0x18006b0ef  mov     ecx, [rbp+18h]
0x18006b0f2  call    SymCryptMlDsakeyAllocate
0x18006b0f7  mov     rsi, rax
0x18006b0fa  test    rax, rax
0x18006b0fd  jnz     short loc_18006B107
0x18006b0ff  mov     r9d, 5D5h
0x18006b105  jmp     short loc_18006B092
0x18006b107  mov     edx, [rbx+8]
0x18006b10a  lea     rcx, [rbx+0Ch]
0x18006b10e  mov     r9d, [rdi+24h]
0x18006b112  add     rcx, r12
0x18006b115  mov     r8d, [r14+20h]
0x18006b119  mov     [rsp+68h+var_48], rax
0x18006b11e  call    SymCryptMlDsakeySetValue
0x18006b123  test    eax, eax
0x18006b125  jz      short loc_18006B13A
0x18006b127  mov     ecx, eax
0x18006b129  call    SymcryptErrorCodeToNtStatus
0x18006b12e  mov     ebx, eax
0x18006b130  mov     ecx, eax
0x18006b132  mov     r9d, 5E2h
0x18006b138  jmp     short loc_18006B164
0x18006b13a  mov     [rdi+28h], rsi
0x18006b13e  xor     ebx, ebx
0x18006b140  mov     [rdi+18h], rbp
0x18006b144  mov     dword ptr [rdi+20h], 1
0x18006b14b  mov     [r15], rdi
0x18006b14e  jmp     short loc_18006B191
0x18006b150  xor     edi, edi
0x18006b152  mov     ebx, 0C000000Dh
0x18006b157  xor     esi, esi
0x18006b159  mov     ecx, 0C000000Dh
0x18006b15e  mov     r9d, 57Ch
0x18006b164  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006b16b  lea     rdx, aStatus_0; "status"
0x18006b172  call    DebugTraceError
0x18006b177  test    rsi, rsi
0x18006b17a  jz      short loc_18006B184
0x18006b17c  mov     rcx, rsi
0x18006b17f  call    SymCryptMlDsakeyFree
0x18006b184  test    rdi, rdi
0x18006b187  jz      short loc_18006B191
0x18006b189  mov     rcx, rdi; void *
0x18006b18c  call    freePqDsaKey
0x18006b191  mov     eax, ebx
0x18006b193  add     rsp, 30h
0x18006b197  pop     r15
0x18006b199  pop     r14
0x18006b19b  pop     r12
0x18006b19d  pop     rdi
0x18006b19e  pop     rsi
0x18006b19f  pop     rbp
0x18006b1a0  pop     rbx
0x18006b1a1  retn
```
