# MSCryptPqDsaVerifySignature

- ea: `0x18006b6b0`
- end: `0x18006b937`
- name: `MSCryptPqDsaVerifySignature`
- size: `647`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, unsigned int, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x180056cf0`
- `0x18006b6b0`
- `0x18006bb20`
- `0x18006bcf8`
- `0x1800739e4`
- `0x1800741c4`
- `0x180074358`
- `0x180074c28`

## string_xrefs

- `0x18006b90c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\pqc-sign\pqdsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptPqDsaVerifySignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  __int64 v7; // rbp
  __int64 v10; // r9
  __int64 v11; // rax
  __int64 v12; // rdi
  unsigned int v13; // ebx
  __int64 v14; // rcx
  int PqDsaVariant; // eax
  __int64 v16; // r11
  unsigned int v17; // r9d
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v23; // [rsp+70h] [rbp+8h] BYREF
  int v24; // [rsp+78h] [rbp+10h] BYREF

  v7 = a4;
  v23 = 0;
  v24 = 0;
  if ( !a1 )
  {
    v10 = 1791;
LABEL_35:
    v14 = 3221225485LL;
    v13 = -1073741811;
    goto LABEL_36;
  }
  v11 = validatePqDsaKey(a1, 1);
  v12 = v11;
  if ( !v11 )
  {
    v10 = 1799;
LABEL_5:
    v13 = -1073741816;
    v14 = 3221225480LL;
LABEL_36:
    DebugTraceError(v14, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\pqc-sign\\pqdsa.c", v10);
    return v13;
  }
  PqDsaVariant = validateInputAndGetPqDsaVariant(v11, a3, v7, a2, a7, (__int64)&v23, (__int64)&v24);
  v13 = PqDsaVariant;
  if ( PqDsaVariant < 0 )
  {
    v10 = 1806;
LABEL_8:
    v14 = (unsigned int)PqDsaVariant;
    goto LABEL_36;
  }
  if ( !a5 || !a6 )
  {
    v10 = 1813;
    goto LABEL_35;
  }
  if ( a2 )
  {
    v16 = *(_QWORD *)a2;
    v17 = *(_DWORD *)(a2 + 8);
  }
  else
  {
    v16 = 0;
    v17 = 0;
  }
  if ( *(_DWORD *)(v12 + 8) == 196620 )
  {
    if ( a6 != *(_DWORD *)(*(_QWORD *)(v12 + 24) + 20LL) )
    {
      v10 = 1837;
      goto LABEL_35;
    }
    if ( v23 )
    {
      if ( v23 == 1 )
      {
        v20 = SymCryptExternalMuMlDsaVerify(*(_QWORD *)(v12 + 40), a3, v7, a5, a6);
        if ( v20 )
        {
          PqDsaVariant = SymcryptErrorCodeToNtStatus(v20);
          v13 = PqDsaVariant;
          v10 = 1872;
          goto LABEL_8;
        }
      }
      else
      {
        if ( v23 != 2 )
        {
          v10 = 1899;
          goto LABEL_35;
        }
        v19 = SymCryptHashMlDsaVerify(*(_QWORD *)(v12 + 40), v24, a3, v7, v16, v17, a5, a6);
        if ( v19 )
        {
          PqDsaVariant = SymcryptErrorCodeToNtStatus(v19);
          v13 = PqDsaVariant;
          v10 = 1891;
          goto LABEL_8;
        }
      }
    }
    else
    {
      v21 = SymCryptMlDsaVerify(*(_QWORD *)(v12 + 40), a3, v7, v16, v17, a5, a6);
      if ( v21 )
      {
        PqDsaVariant = SymcryptErrorCodeToNtStatus(v21);
        v13 = PqDsaVariant;
        v10 = 1856;
        goto LABEL_8;
      }
    }
  }
  else
  {
    if ( *(_DWORD *)(v12 + 8) != 196621 )
    {
      v10 = 1937;
      goto LABEL_5;
    }
    if ( a6 > *(_DWORD *)(*(_QWORD *)(v12 + 24) + 20LL) )
    {
      v10 = 1912;
      goto LABEL_35;
    }
    v18 = SymCryptCompositeMlDsaVerify(*(_QWORD *)(v12 + 40), a3, v7, v16, v17, a5, a6, v23 == 2);
    if ( v18 )
    {
      PqDsaVariant = SymcryptErrorCodeToNtStatus(v18);
      v13 = PqDsaVariant;
      v10 = 1929;
      goto LABEL_8;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006b6b0  mov     rax, rsp
0x18006b6b3  mov     [rax+18h], rbx
0x18006b6b7  mov     [rax+20h], rbp
0x18006b6bb  push    rsi
0x18006b6bc  push    rdi
0x18006b6bd  push    r14
0x18006b6bf  sub     rsp, 50h
0x18006b6c3  mov     ebp, r9d
0x18006b6c6  mov     r14, r8
0x18006b6c9  mov     dword ptr [rax+8], 0
0x18006b6d0  mov     rsi, rdx
0x18006b6d3  mov     dword ptr [rax+10h], 0
0x18006b6da  test    rcx, rcx
0x18006b6dd  jnz     short loc_18006B6EA
0x18006b6df  mov     r9d, 6FFh
0x18006b6e5  jmp     loc_18006B902
0x18006b6ea  mov     edx, 1
0x18006b6ef  call    validatePqDsaKey
0x18006b6f4  mov     rdi, rax
0x18006b6f7  test    rax, rax
0x18006b6fa  jnz     short loc_18006B711
0x18006b6fc  mov     r9d, 707h
0x18006b702  mov     ebx, 0C0000008h
0x18006b707  mov     ecx, 0C0000008h
0x18006b70c  jmp     loc_18006B90C
0x18006b711  lea     rax, [rsp+68h+arg_8]
0x18006b716  mov     r9, rsi
0x18006b719  mov     [rsp+68h+var_38], rax
0x18006b71e  mov     r8d, ebp
0x18006b721  lea     rax, [rsp+68h+arg_0]
0x18006b726  mov     rdx, r14
0x18006b729  mov     [rsp+68h+var_40], rax
0x18006b72e  mov     rcx, rdi
0x18006b731  mov     eax, [rsp+68h+arg_30]
0x18006b738  mov     dword ptr [rsp+68h+var_48], eax
0x18006b73c  call    validateInputAndGetPqDsaVariant
0x18006b741  mov     ebx, eax
0x18006b743  test    eax, eax
0x18006b745  jns     short loc_18006B754
0x18006b747  mov     r9d, 70Eh
0x18006b74d  mov     ecx, eax
0x18006b74f  jmp     loc_18006B90C
0x18006b754  mov     r10, [rsp+68h+arg_20]
0x18006b75c  test    r10, r10
0x18006b75f  jz      loc_18006B8FC
0x18006b765  mov     r8d, [rsp+68h+arg_28]
0x18006b76d  test    r8d, r8d
0x18006b770  jz      loc_18006B8FC
0x18006b776  test    rsi, rsi
0x18006b779  jnz     short loc_18006B783
0x18006b77b  xor     r11d, r11d
0x18006b77e  xor     r9d, r9d
0x18006b781  jmp     short loc_18006B78A
0x18006b783  mov     r11, [rsi]
0x18006b786  mov     r9d, [rsi+8]
0x18006b78a  mov     ecx, [rdi+8]
0x18006b78d  sub     ecx, 3000Ch
0x18006b793  jz      short loc_18006B80B
0x18006b795  cmp     ecx, 1
0x18006b798  jz      short loc_18006B7A5
0x18006b79a  mov     r9d, 791h
0x18006b7a0  jmp     loc_18006B702
0x18006b7a5  mov     rax, [rdi+18h]
0x18006b7a9  cmp     r8d, [rax+14h]
0x18006b7ad  jbe     short loc_18006B7BA
0x18006b7af  mov     r9d, 778h
0x18006b7b5  jmp     loc_18006B902
0x18006b7ba  xor     edx, edx
0x18006b7bc  mov     ecx, r9d
0x18006b7bf  cmp     [rsp+68h+arg_0], 2
0x18006b7c4  mov     rax, r8
0x18006b7c7  mov     r8, rbp
0x18006b7ca  mov     r9, r11
0x18006b7cd  setz    dl
0x18006b7d0  mov     dword ptr [rsp+68h+var_30], edx
0x18006b7d4  mov     rdx, r14
0x18006b7d7  mov     [rsp+68h+var_38], rax
0x18006b7dc  mov     [rsp+68h+var_40], r10
0x18006b7e1  mov     [rsp+68h+var_48], rcx
0x18006b7e6  mov     rcx, [rdi+28h]
0x18006b7ea  call    SymCryptCompositeMlDsaVerify
0x18006b7ef  test    eax, eax
0x18006b7f1  jz      loc_18006B8F8
0x18006b7f7  mov     ecx, eax
0x18006b7f9  call    SymcryptErrorCodeToNtStatus
0x18006b7fe  mov     ebx, eax
0x18006b800  mov     r9d, 789h
0x18006b806  jmp     loc_18006B74D
0x18006b80b  mov     rax, [rdi+18h]
0x18006b80f  cmp     r8d, [rax+14h]
0x18006b813  jz      short loc_18006B820
0x18006b815  mov     r9d, 72Dh
0x18006b81b  jmp     loc_18006B902
0x18006b820  mov     ecx, [rsp+68h+arg_0]
0x18006b824  test    ecx, ecx
0x18006b826  jz      loc_18006B8B9
0x18006b82c  sub     ecx, 1
0x18006b82f  jz      short loc_18006B887
0x18006b831  cmp     ecx, 1
0x18006b834  jz      short loc_18006B841
0x18006b836  mov     r9d, 76Bh
0x18006b83c  jmp     loc_18006B902
0x18006b841  mov     edx, [rsp+68h+arg_8]
0x18006b845  mov     [rsp+68h+var_30], r8
0x18006b84a  mov     r8, r14
0x18006b84d  mov     ecx, r9d
0x18006b850  mov     r9, rbp
0x18006b853  mov     [rsp+68h+var_38], r10
0x18006b858  mov     [rsp+68h+var_40], rcx
0x18006b85d  mov     rcx, [rdi+28h]
0x18006b861  mov     [rsp+68h+var_48], r11
0x18006b866  call    SymCryptHashMlDsaVerify
0x18006b86b  test    eax, eax
0x18006b86d  jz      loc_18006B8F8
0x18006b873  mov     ecx, eax
0x18006b875  call    SymcryptErrorCodeToNtStatus
0x18006b87a  mov     ebx, eax
0x18006b87c  mov     r9d, 763h
0x18006b882  jmp     loc_18006B74D
0x18006b887  mov     rcx, [rdi+28h]
0x18006b88b  mov     rax, r8
0x18006b88e  mov     r8, rbp
0x18006b891  mov     [rsp+68h+var_48], rax
0x18006b896  mov     r9, r10
0x18006b899  mov     rdx, r14
0x18006b89c  call    SymCryptExternalMuMlDsaVerify
0x18006b8a1  test    eax, eax
0x18006b8a3  jz      short loc_18006B8F8
0x18006b8a5  mov     ecx, eax
0x18006b8a7  call    SymcryptErrorCodeToNtStatus
0x18006b8ac  mov     ebx, eax
0x18006b8ae  mov     r9d, 750h
0x18006b8b4  jmp     loc_18006B74D
0x18006b8b9  mov     ecx, r9d
0x18006b8bc  mov     rax, r8
0x18006b8bf  mov     [rsp+68h+var_38], rax
0x18006b8c4  mov     r8, rbp
0x18006b8c7  mov     [rsp+68h+var_40], r10
0x18006b8cc  mov     r9, r11
0x18006b8cf  mov     [rsp+68h+var_48], rcx
0x18006b8d4  mov     rdx, r14
0x18006b8d7  mov     rcx, [rdi+28h]
0x18006b8db  call    SymCryptMlDsaVerify
0x18006b8e0  test    eax, eax
0x18006b8e2  jz      short loc_18006B8F8
0x18006b8e4  mov     ecx, eax
0x18006b8e6  call    SymcryptErrorCodeToNtStatus
0x18006b8eb  mov     ebx, eax
0x18006b8ed  mov     r9d, 740h
0x18006b8f3  jmp     loc_18006B74D
0x18006b8f8  xor     ebx, ebx
0x18006b8fa  jmp     short loc_18006B91F
0x18006b8fc  mov     r9d, 715h
0x18006b902  mov     ecx, 0C000000Dh
0x18006b907  mov     ebx, 0C000000Dh
0x18006b90c  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18006b913  lea     rdx, aStatus_0; "status"
0x18006b91a  call    DebugTraceError
0x18006b91f  lea     r11, [rsp+68h+var_18]
0x18006b924  mov     eax, ebx
0x18006b926  mov     rbx, [r11+30h]
0x18006b92a  mov     rbp, [r11+38h]
0x18006b92e  mov     rsp, r11
0x18006b931  pop     r14
0x18006b933  pop     rdi
0x18006b934  pop     rsi
0x18006b935  retn
```
