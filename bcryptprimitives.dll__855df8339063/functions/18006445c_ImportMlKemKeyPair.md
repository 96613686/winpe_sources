# ImportMlKemKeyPair

- ea: `0x18006445c`
- end: `0x1800645dc`
- name: `ImportMlKemKeyPair`
- size: `384`
- prototype: `__int64 __fastcall(_DWORD *, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180064ff0`

## callees

- `0x180001180`
- `0x180001240`
- `0x1800012f0`
- `0x18000ecb0`
- `0x180056cf0`
- `0x180064130`
- `0x1800641e8`
- `0x18006445c`

## string_xrefs

- `0x1800644a3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`
- `0x18006459b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ImportMlKemKeyPair(_DWORD *a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 v7; // r9
  __int64 v8; // rbx
  __int64 v9; // rcx
  int MlKemBlobInfo; // eax
  __int64 v11; // r13
  __int64 v12; // r14
  unsigned int v13; // eax
  __int64 v14; // r12
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // rsi
  unsigned int v18; // eax
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h]

  v20 = 0;
  v21 = 0;
  if ( a2 < 0xC )
  {
    v7 = 1599;
LABEL_3:
    LODWORD(v8) = -1073741811;
    v9 = 3221225485LL;
LABEL_4:
    DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v7);
    return (unsigned int)v8;
  }
  MlKemBlobInfo = GetMlKemBlobInfo(a3, &v20);
  LODWORD(v8) = MlKemBlobInfo;
  if ( MlKemBlobInfo < 0 )
  {
    v7 = 1606;
LABEL_7:
    v9 = (unsigned int)MlKemBlobInfo;
    goto LABEL_4;
  }
  v11 = v20;
  if ( *a1 != *(_DWORD *)(v20 + 16) )
  {
    v7 = 1615;
    goto LABEL_3;
  }
  v12 = (unsigned int)a1[1];
  v13 = v12 + 12;
  if ( (unsigned int)v12 >= 0xFFFFFFF4 )
  {
    v7 = 1627;
LABEL_12:
    LODWORD(v8) = -1073741675;
    v9 = 3221225621LL;
    goto LABEL_4;
  }
  v14 = (unsigned int)a1[2];
  if ( (unsigned int)v14 + v13 < v13 )
  {
    v7 = 1634;
    goto LABEL_12;
  }
  if ( a2 < (unsigned int)v14 + v13 )
  {
    v7 = 1641;
    goto LABEL_3;
  }
  MlKemBlobInfo = GetMlKemParamSetInfo(a1 + 3, (unsigned int)v12);
  LODWORD(v8) = MlKemBlobInfo;
  if ( MlKemBlobInfo < 0 )
  {
    v7 = 1651;
    goto LABEL_7;
  }
  v15 = v21;
  v16 = SymCryptMlKemkeyAllocate(*(unsigned int *)(v21 + 28));
  v17 = v16;
  if ( !v16 )
  {
    LODWORD(v8) = -1073741801;
    v7 = 1659;
    v9 = 3221225495LL;
    goto LABEL_4;
  }
  v18 = SymCryptMlKemkeySetValue(
          (char *)a1 + v12 + 12,
          v14,
          *(unsigned int *)(v11 + 20),
          *(unsigned int *)(a4 + 12),
          v16);
  if ( v18 )
  {
    v8 = (unsigned int)SymcryptErrorCodeToNtStatus(v18);
    DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 1667);
    SymCryptMlKemkeyFree(v17);
  }
  else
  {
    *(_QWORD *)(a4 + 32) = v17;
    *(_QWORD *)(a4 + 24) = v15;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006445c  push    rbx
0x18006445e  push    rbp
0x18006445f  push    rsi
0x180064460  push    rdi
0x180064461  push    r12
0x180064463  push    r13
0x180064465  push    r14
0x180064467  push    r15
0x180064469  sub     rsp, 48h
0x18006446d  mov     [rsp+88h+var_58], 0
0x180064476  mov     rbp, r9
0x180064479  mov     [rsp+88h+var_50], 0
0x180064482  mov     esi, edx
0x180064484  mov     rdi, rcx
0x180064487  cmp     edx, 0Ch
0x18006448a  jnb     short loc_1800644B4
0x18006448c  mov     r9d, 63Fh
0x180064492  mov     ebx, 0C000000Dh
0x180064497  mov     ecx, 0C000000Dh
0x18006449c  lea     rdx, aStatus; "Status"
0x1800644a3  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800644aa  call    DebugTraceError
0x1800644af  jmp     loc_1800645C8
0x1800644b4  lea     rdx, [rsp+88h+var_58]
0x1800644b9  mov     rcx, r8
0x1800644bc  call    GetMlKemBlobInfo
0x1800644c1  mov     ebx, eax
0x1800644c3  test    eax, eax
0x1800644c5  jns     short loc_1800644D1
0x1800644c7  mov     r9d, 646h
0x1800644cd  mov     ecx, eax
0x1800644cf  jmp     short loc_18006449C
0x1800644d1  mov     r13, [rsp+88h+var_58]
0x1800644d6  mov     eax, [r13+10h]
0x1800644da  cmp     [rdi], eax
0x1800644dc  jz      short loc_1800644E6
0x1800644de  mov     r9d, 64Fh
0x1800644e4  jmp     short loc_180064492
0x1800644e6  mov     r14d, [rdi+4]
0x1800644ea  lea     eax, [r14+0Ch]
0x1800644ee  cmp     eax, 0Ch
0x1800644f1  jnb     short loc_180064505
0x1800644f3  mov     r9d, 65Bh
0x1800644f9  mov     ebx, 0C0000095h
0x1800644fe  mov     ecx, 0C0000095h
0x180064503  jmp     short loc_18006449C
0x180064505  mov     r12d, [rdi+8]
0x180064509  lea     ecx, [r12+rax]
0x18006450d  cmp     ecx, eax
0x18006450f  jnb     short loc_180064519
0x180064511  mov     r9d, 662h
0x180064517  jmp     short loc_1800644F9
0x180064519  cmp     esi, ecx
0x18006451b  jnb     short loc_180064528
0x18006451d  mov     r9d, 669h
0x180064523  jmp     loc_180064492
0x180064528  lea     rcx, [rdi+0Ch]; Buf1
0x18006452c  mov     edx, r14d; Size
0x18006452f  lea     r8, [rsp+88h+var_50]
0x180064534  call    GetMlKemParamSetInfo
0x180064539  mov     ebx, eax
0x18006453b  test    eax, eax
0x18006453d  jns     short loc_180064547
0x18006453f  mov     r9d, 673h
0x180064545  jmp     short loc_1800644CD
0x180064547  mov     r15, [rsp+88h+var_50]
0x18006454c  mov     ecx, [r15+1Ch]
0x180064550  call    SymCryptMlKemkeyAllocate
0x180064555  mov     rsi, rax
0x180064558  test    rax, rax
0x18006455b  jnz     short loc_180064572
0x18006455d  mov     ebx, 0C0000017h
0x180064562  mov     r9d, 67Bh
0x180064568  mov     ecx, 0C0000017h
0x18006456d  jmp     loc_18006449C
0x180064572  mov     r9d, [rbp+0Ch]
0x180064576  lea     rcx, [rdi+0Ch]
0x18006457a  mov     r8d, [r13+14h]
0x18006457e  add     rcx, r14
0x180064581  mov     rdx, r12
0x180064584  mov     [rsp+88h+var_68], rsi
0x180064589  call    SymCryptMlKemkeySetValue
0x18006458e  test    eax, eax
0x180064590  jz      short loc_1800645C0
0x180064592  mov     ecx, eax
0x180064594  call    SymcryptErrorCodeToNtStatus
0x180064599  mov     ecx, eax
0x18006459b  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800645a2  mov     r9d, 683h
0x1800645a8  lea     rdx, aStatus; "Status"
0x1800645af  mov     ebx, eax
0x1800645b1  call    DebugTraceError
0x1800645b6  mov     rcx, rsi
0x1800645b9  call    SymCryptMlKemkeyFree
0x1800645be  jmp     short loc_1800645C8
0x1800645c0  mov     [rbp+20h], rsi
0x1800645c4  mov     [rbp+18h], r15
0x1800645c8  mov     eax, ebx
0x1800645ca  add     rsp, 48h
0x1800645ce  pop     r15
0x1800645d0  pop     r14
0x1800645d2  pop     r13
0x1800645d4  pop     r12
0x1800645d6  pop     rdi
0x1800645d7  pop     rsi
0x1800645d8  pop     rbp
0x1800645d9  pop     rbx
0x1800645da  retn
```
