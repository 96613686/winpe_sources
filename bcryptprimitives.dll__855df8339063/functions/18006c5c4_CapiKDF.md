# _CapiKDF

- ea: `0x18006c5c4`
- end: `0x18006c81a`
- name: `_CapiKDF`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180053de4`

## callees

- `0x18000ecb0`
- `0x18000f810`
- `0x180010270`
- `0x1800102a0`
- `0x180017240`
- `0x1800173f0`
- `0x180063170`
- `0x180063180`
- `0x18006c5c4`
- `0x18007f790`

## string_xrefs

- `0x18006c69a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x18006c7e6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall CapiKDF(__int64 a1, void *a2, unsigned int a3, char a4)
{
  size_t v5; // r14
  unsigned int HashProperty; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  _BYTE *v14; // rdi
  unsigned int v15; // eax
  __int64 v16; // r9
  BOOL v17; // eax
  __int64 i; // rdx
  char v19; // al
  __int64 v20; // rcx
  _BYTE *v21; // rax
  _QWORD v23[2]; // [rsp+30h] [rbp-79h] BYREF
  _BYTE v24[64]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE v25[64]; // [rsp+80h] [rbp-29h] BYREF

  v5 = a3;
  v23[0] = 0;
  HashProperty = MSCryptGetHashProperty(a1, L"HashDigestLength", v23, 4u, (unsigned int *)v23 + 1, 0);
  v9 = HashProperty;
  if ( HashProperty )
  {
    v10 = 1224;
    v11 = HashProperty;
LABEL_30:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v10);
    return v9;
  }
  v12 = (unsigned int)(2 * LODWORD(v23[0]));
  if ( (unsigned int)v12 < (unsigned int)v5 || LODWORD(v23[0]) > 0x40 )
  {
    v9 = -1073741811;
    v10 = 1232;
    v11 = 3221225485LL;
    goto LABEL_30;
  }
  v13 = SafeAllocaAllocateFromHeap(v12);
  v14 = (_BYTE *)v13;
  if ( !v13 )
  {
    v9 = -1073741801;
    v10 = 1245;
    v11 = 3221225495LL;
    goto LABEL_30;
  }
  v15 = MSCryptFinishHash(a1, v13, v23[0], 0);
  v9 = v15;
  if ( !v15 )
  {
    v17 = LODWORD(v23[0]) < (unsigned int)v5;
    if ( (a4 & 0x10) != 0 && (_DWORD)v5 == 16 && LODWORD(v23[0]) < 0x20 )
      v17 = 1;
    if ( v17 )
    {
      memset_0(v24, 54, sizeof(v24));
      memset_0(v25, 92, sizeof(v25));
      for ( i = 0; (unsigned int)i < LODWORD(v23[0]); i = (unsigned int)(i + 1) )
      {
        v19 = v14[i];
        v24[i] ^= v19;
        v25[i] ^= v19;
      }
      v15 = MSCryptHashData(a1, (__int64)v24, 64, 0);
      v9 = v15;
      if ( v15 )
      {
        v16 = 1319;
        goto LABEL_9;
      }
      v15 = MSCryptFinishHash(a1, (__int64)v14, v23[0], 0);
      v9 = v15;
      if ( v15 )
      {
        v16 = 1330;
        goto LABEL_9;
      }
      v15 = MSCryptHashData(a1, (__int64)v25, 64, 0);
      v9 = v15;
      if ( v15 )
      {
        v16 = 1342;
        goto LABEL_9;
      }
      v15 = MSCryptFinishHash(a1, (__int64)&v14[LODWORD(v23[0])], v23[0], 0);
      v9 = v15;
      if ( v15 )
      {
        v16 = 1353;
        goto LABEL_9;
      }
    }
    memcpy_0(a2, v14, v5);
    v9 = 0;
    goto LABEL_26;
  }
  v16 = 1256;
LABEL_9:
  DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v16);
LABEL_26:
  v20 = (unsigned int)(2 * LODWORD(v23[0]));
  v21 = v14;
  if ( 2 * LODWORD(v23[0]) )
  {
    do
    {
      *v21++ = 0;
      --v20;
    }
    while ( v20 );
  }
  MSCryptFree(v14);
  return v9;
}

```

## disassembly

```asm
0x18006c5c4  push    rbp
0x18006c5c6  push    rbx
0x18006c5c7  push    rsi
0x18006c5c8  push    rdi
0x18006c5c9  push    r12
0x18006c5cb  push    r14
0x18006c5cd  push    r15
0x18006c5cf  lea     rbp, [rsp-27h]
0x18006c5d4  sub     rsp, 0D0h
0x18006c5db  mov     rax, cs:__security_cookie
0x18006c5e2  xor     rax, rsp
0x18006c5e5  mov     [rbp+57h+var_40], rax
0x18006c5e9  mov     r15d, r9d
0x18006c5ec  mov     r14d, r8d
0x18006c5ef  mov     r12, rdx
0x18006c5f2  mov     [rsp+100h+var_D8], 0
0x18006c5fa  lea     rax, [rbp+57h+var_CC]
0x18006c5fe  mov     [rbp+57h+var_D0], 0
0x18006c605  mov     r9d, 4
0x18006c60b  mov     [rsp+100h+var_E0], rax
0x18006c610  lea     r8, [rbp+57h+var_D0]
0x18006c614  mov     [rbp+57h+var_CC], 0
0x18006c61b  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18006c622  mov     rsi, rcx
0x18006c625  call    MSCryptGetHashProperty
0x18006c62a  mov     ebx, eax
0x18006c62c  test    eax, eax
0x18006c62e  jz      short loc_18006C63D
0x18006c630  mov     r9d, 4C8h
0x18006c636  mov     ecx, eax
0x18006c638  jmp     loc_18006C7E6
0x18006c63d  mov     eax, [rbp+57h+var_D0]
0x18006c640  lea     ecx, [rax+rax]
0x18006c643  cmp     ecx, r14d
0x18006c646  jb      loc_18006C7D6
0x18006c64c  cmp     eax, 40h ; '@'
0x18006c64f  ja      loc_18006C7D6
0x18006c655  call    SafeAllocaAllocateFromHeap
0x18006c65a  mov     rdi, rax
0x18006c65d  test    rax, rax
0x18006c660  jnz     short loc_18006C677
0x18006c662  mov     ebx, 0C0000017h
0x18006c667  mov     r9d, 4DDh
0x18006c66d  mov     ecx, 0C0000017h
0x18006c672  jmp     loc_18006C7E6
0x18006c677  mov     r8d, [rbp+57h+var_D0]
0x18006c67b  xor     r9d, r9d
0x18006c67e  mov     rdx, rdi
0x18006c681  mov     rcx, rsi
0x18006c684  call    MSCryptFinishHash
0x18006c689  mov     ebx, eax
0x18006c68b  mov     ecx, 1
0x18006c690  test    eax, eax
0x18006c692  jz      short loc_18006C6B4
0x18006c694  mov     r9d, 4E8h
0x18006c69a  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c6a1  mov     ecx, eax
0x18006c6a3  lea     rdx, aStatus; "Status"
0x18006c6aa  call    DebugTraceError
0x18006c6af  jmp     loc_18006C7B4
0x18006c6b4  xor     eax, eax
0x18006c6b6  cmp     [rbp+57h+var_D0], r14d
0x18006c6ba  cmovb   eax, ecx
0x18006c6bd  test    r15b, 10h
0x18006c6c1  jz      short loc_18006C6D0
0x18006c6c3  cmp     r14d, 10h
0x18006c6c7  jnz     short loc_18006C6D0
0x18006c6c9  cmp     [rbp+57h+var_D0], 20h ; ' '
0x18006c6cd  cmovb   eax, ecx
0x18006c6d0  cmp     eax, ecx
0x18006c6d2  jnz     loc_18006C7A4
0x18006c6d8  mov     r15d, 40h ; '@'
0x18006c6de  lea     rcx, [rbp+57h+var_C0]; void *
0x18006c6e2  mov     r8d, r15d; Size
0x18006c6e5  lea     edx, [r15-0Ah]; Val
0x18006c6e9  call    memset_0
0x18006c6ee  mov     r8d, r15d; Size
0x18006c6f1  lea     edx, [r15+1Ch]; Val
0x18006c6f5  lea     rcx, [rbp+57h+var_80]; void *
0x18006c6f9  call    memset_0
0x18006c6fe  xor     edx, edx
0x18006c700  cmp     [rbp+57h+var_D0], edx
0x18006c703  jbe     short loc_18006C717
0x18006c705  mov     al, [rdx+rdi]
0x18006c708  xor     [rbp+rdx+57h+var_C0], al
0x18006c70c  xor     [rbp+rdx+57h+var_80], al
0x18006c710  inc     edx
0x18006c712  cmp     edx, [rbp+57h+var_D0]
0x18006c715  jb      short loc_18006C705
0x18006c717  xor     r9d, r9d
0x18006c71a  lea     rdx, [rbp+57h+var_C0]
0x18006c71e  mov     r8d, r15d
0x18006c721  mov     rcx, rsi
0x18006c724  call    MSCryptHashData
0x18006c729  mov     ebx, eax
0x18006c72b  test    eax, eax
0x18006c72d  jz      short loc_18006C73A
0x18006c72f  mov     r9d, 527h
0x18006c735  jmp     loc_18006C69A
0x18006c73a  mov     r8d, [rbp+57h+var_D0]
0x18006c73e  xor     r9d, r9d
0x18006c741  mov     rdx, rdi
0x18006c744  mov     rcx, rsi
0x18006c747  call    MSCryptFinishHash
0x18006c74c  mov     ebx, eax
0x18006c74e  test    eax, eax
0x18006c750  jz      short loc_18006C75D
0x18006c752  mov     r9d, 532h
0x18006c758  jmp     loc_18006C69A
0x18006c75d  xor     r9d, r9d
0x18006c760  lea     rdx, [rbp+57h+var_80]
0x18006c764  mov     r8d, r15d
0x18006c767  mov     rcx, rsi
0x18006c76a  call    MSCryptHashData
0x18006c76f  mov     ebx, eax
0x18006c771  test    eax, eax
0x18006c773  jz      short loc_18006C780
0x18006c775  mov     r9d, 53Eh
0x18006c77b  jmp     loc_18006C69A
0x18006c780  mov     r8d, [rbp+57h+var_D0]
0x18006c784  xor     r9d, r9d
0x18006c787  mov     rcx, rsi
0x18006c78a  lea     rdx, [rdi+r8]
0x18006c78e  call    MSCryptFinishHash
0x18006c793  mov     ebx, eax
0x18006c795  test    eax, eax
0x18006c797  jz      short loc_18006C7A4
0x18006c799  mov     r9d, 549h
0x18006c79f  jmp     loc_18006C69A
0x18006c7a4  mov     r8, r14; Size
0x18006c7a7  mov     rdx, rdi; Src
0x18006c7aa  mov     rcx, r12; void *
0x18006c7ad  call    memcpy_0
0x18006c7b2  xor     ebx, ebx
0x18006c7b4  mov     eax, [rbp+57h+var_D0]
0x18006c7b7  add     eax, eax
0x18006c7b9  mov     ecx, eax
0x18006c7bb  mov     rax, rdi
0x18006c7be  jz      short loc_18006C7CC
0x18006c7c0  mov     byte ptr [rax], 0
0x18006c7c3  inc     rax
0x18006c7c6  sub     rcx, 1
0x18006c7ca  jnz     short loc_18006C7C0
0x18006c7cc  mov     rcx, rdi
0x18006c7cf  call    MSCryptFree
0x18006c7d4  jmp     short loc_18006C7F9
0x18006c7d6  mov     ebx, 0C000000Dh
0x18006c7db  mov     r9d, 4D0h
0x18006c7e1  mov     ecx, 0C000000Dh
0x18006c7e6  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006c7ed  lea     rdx, aStatus; "Status"
0x18006c7f4  call    DebugTraceError
0x18006c7f9  mov     eax, ebx
0x18006c7fb  mov     rcx, [rbp+57h+var_40]
0x18006c7ff  xor     rcx, rsp; StackCookie
0x18006c802  call    __security_check_cookie
0x18006c807  add     rsp, 0D0h
0x18006c80e  pop     r15
0x18006c810  pop     r14
0x18006c812  pop     r12
0x18006c814  pop     rdi
0x18006c815  pop     rsi
0x18006c816  pop     rbx
0x18006c817  pop     rbp
0x18006c818  retn
```
