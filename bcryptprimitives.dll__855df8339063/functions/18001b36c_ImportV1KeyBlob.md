# ImportV1KeyBlob

- ea: `0x18001b36c`
- end: `0x18001b676`
- name: `ImportV1KeyBlob`
- size: `778`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180069c80`

## callees

- `0x18000ecb0`
- `0x180010270`
- `0x1800102a0`
- `0x18001b36c`
- `0x18001b67c`
- `0x18001bf34`
- `0x18001bf88`
- `0x18001c380`
- `0x18001c420`
- `0x18001c464`
- `0x18001c878`
- `0x1800215e4`
- `0x180056cf0`
- `0x18005723c`
- `0x1800581c0`
- `0x180058288`

## string_xrefs

- `0x18001b5b9`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x18001b637`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`
- `0x18008145e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\dsa\dsa.c`

## pseudocode

```c
__int64 __fastcall ImportV1KeyBlob(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, unsigned int a5, _QWORD *a6)
{
  int v8; // eax
  __int64 v9; // rdi
  unsigned int v10; // edi
  __int64 v11; // rax
  unsigned int *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // r14
  int v17; // r13d
  __int64 v18; // r11
  char *v19; // rdx
  char *v20; // rcx
  unsigned int v21; // eax
  char v22; // al
  unsigned int v23; // r12d
  int v24; // r15d
  int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rbp
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  __int64 v34; // r11
  __int64 v35; // r10
  int v36; // eax
  int v37; // r10d
  unsigned int v38; // eax
  __int64 v40; // rax
  _BYTE *v41; // rcx
  __int64 v42; // r9
  __int64 v43; // rcx
  __int64 v44; // r9
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // [rsp+20h] [rbp-A8h]
  int v49[22]; // [rsp+70h] [rbp-58h] BYREF
  int v50; // [rsp+E8h] [rbp+20h] BYREF

  v50 = 0;
  v49[0] = 0;
  v8 = ValidateDSAKeyBlobV1Format(a3, a4, a2, &v50);
  LODWORD(v9) = v8;
  if ( v8 < 0 )
  {
    v42 = 1620;
    v43 = (unsigned int)v8;
LABEL_25:
    DebugTraceError(v43, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v42);
    return (unsigned int)v9;
  }
  v10 = *(_DWORD *)(a3 + 4);
  v11 = SafeAllocaAllocateFromHeap(48);
  v12 = (unsigned int *)v11;
  if ( !v11 )
  {
    LODWORD(v9) = -1073741801;
    v42 = 1635;
    v43 = 3221225495LL;
    goto LABEL_25;
  }
  *(_OWORD *)v11 = 0;
  *(_OWORD *)(v11 + 16) = 0;
  *(_OWORD *)(v11 + 32) = 0;
  *(_DWORD *)v11 = 48;
  *(_DWORD *)(v11 + 12) = v10;
  SetKeyPropertiesBasedOnKeyLength(v10, v11);
  v14 = SymCryptDlgroupAllocate(8 * v12[3], (unsigned int)(8 * *(_DWORD *)(v13 + 16)));
  *((_QWORD *)v12 + 4) = v14;
  v15 = v14;
  if ( !v14 )
  {
    v44 = 1653;
LABEL_28:
    LODWORD(v9) = -1073741801;
    v45 = 3221225495LL;
LABEL_38:
    DebugTraceError(v45, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", v44);
    goto LABEL_39;
  }
  if ( v50 )
  {
    v17 = 20;
    v16 = a3 + 3 * v10 + 52LL;
  }
  else
  {
    v16 = 0;
    v17 = 0;
  }
  v18 = v12[3];
  v19 = (char *)(a3 + 8);
  v12[1] = 1297304409;
  v20 = (char *)v49 + 3;
  v21 = *(_DWORD *)(a1 + 8);
  v12[7] |= 1u;
  v12[2] = v21;
  do
  {
    v22 = *v19++;
    *v20-- = v22;
  }
  while ( v20 >= (char *)v49 );
  v23 = a5;
  v24 = a5 & 8;
  if ( (a5 & 8) != 0 || (v25 = v24 + 1, v49[0] == -1) )
    v25 = 0;
  v26 = SymCryptDlgroupSetValue(
          (int)a3 + 52,
          v18,
          (int)a3 + 32,
          v12[4],
          v18 + a3 + 52,
          v18,
          2,
          0,
          a3 + 12,
          0x14u,
          v49[0],
          v25,
          v15);
  if ( v26 )
  {
    v9 = (unsigned int)SymcryptErrorCodeToNtStatus(v26);
    v45 = v9;
    v44 = 1706;
    goto LABEL_38;
  }
  v28 = SymCryptDlkeyAllocate(*((_QWORD *)v12 + 4), v27);
  *((_QWORD *)v12 + 5) = v28;
  v29 = v28;
  if ( !v28 )
  {
    v44 = 1714;
    goto LABEL_28;
  }
  v30 = IsAllZeros(a3 + 2 * v10 + 52LL, v10);
  if ( v30 )
    v10 = 0;
  v35 = 0;
  if ( !v30 )
    v35 = v34;
  if ( (v23 & 0x20) != 0 && (!v16 || !v35) )
  {
    LODWORD(v9) = -1073741811;
    v44 = 1732;
    v45 = 3221225485LL;
    goto LABEL_38;
  }
  v36 = BCryptFlagsToSymCryptKeyValidationFlags(v23, v31, v32, v33);
  v38 = SymCryptDlkeySetValue(v16, v17, v37, v10, v48, v36 | 0x1000u, v29);
  if ( !v38 )
  {
    LODWORD(v9) = 0;
    *a6 = v12;
    return (unsigned int)v9;
  }
  v9 = (unsigned int)SymcryptErrorCodeToNtStatus(v38);
  DebugTraceError(v9, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\dsa\\dsa.c", 1750);
  if ( !v24 )
    MSCryptAuditPrimitiveFailure(v46, L"DSA", 2450, (unsigned int)v9);
LABEL_39:
  if ( *((_QWORD *)v12 + 5) )
  {
    SymCryptDlkeyFree();
    *((_QWORD *)v12 + 5) = 0;
  }
  v47 = *((_QWORD *)v12 + 4);
  if ( v47 )
  {
    SymCryptMlDsaTemporariesFree(v47);
    *((_QWORD *)v12 + 4) = 0;
  }
  v40 = *v12;
  v41 = v12;
  if ( *v12 )
  {
    do
    {
      *v41++ = 0;
      --v40;
    }
    while ( v40 );
  }
  MSCryptFree(v12);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001b36c  mov     r11, rsp
0x18001b36f  push    rbx
0x18001b370  push    rbp
0x18001b371  push    rsi
0x18001b372  push    rdi
0x18001b373  push    r12
0x18001b375  push    r13
0x18001b377  push    r14
0x18001b379  push    r15
0x18001b37b  sub     rsp, 88h
0x18001b382  mov     eax, r9d
0x18001b385  mov     dword ptr [r11+20h], 0
0x18001b38d  mov     rsi, r8
0x18001b390  mov     [rsp+0C8h+var_58], 0
0x18001b398  mov     r8, rdx
0x18001b39b  lea     r9, [r11+20h]
0x18001b39f  mov     rbp, rcx
0x18001b3a2  mov     edx, eax
0x18001b3a4  mov     rcx, rsi
0x18001b3a7  call    ValidateDSAKeyBlobV1Format
0x18001b3ac  mov     edi, eax
0x18001b3ae  test    eax, eax
0x18001b3b0  js      loc_18001B598
0x18001b3b6  mov     edi, [rsi+4]
0x18001b3b9  mov     r14d, 30h ; '0'
0x18001b3bf  mov     ecx, r14d
0x18001b3c2  call    SafeAllocaAllocateFromHeap
0x18001b3c7  mov     rbx, rax
0x18001b3ca  test    rax, rax
0x18001b3cd  jz      loc_18001B5A2
0x18001b3d3  xorps   xmm0, xmm0
0x18001b3d6  mov     rdx, rax
0x18001b3d9  movups  xmmword ptr [rax], xmm0
0x18001b3dc  mov     ecx, edi
0x18001b3de  movups  xmmword ptr [rax+10h], xmm0
0x18001b3e2  movups  xmmword ptr [rax+20h], xmm0
0x18001b3e6  mov     [rax], r14d
0x18001b3e9  mov     [rax+0Ch], edi
0x18001b3ec  call    SetKeyPropertiesBasedOnKeyLength
0x18001b3f1  mov     edx, [rdx+10h]
0x18001b3f4  mov     ecx, [rbx+0Ch]
0x18001b3f7  shl     edx, 3
0x18001b3fa  shl     ecx, 3
0x18001b3fd  call    SymCryptDlgroupAllocate
0x18001b402  mov     [rbx+20h], rax
0x18001b406  mov     r8, rax
0x18001b409  test    rax, rax
0x18001b40c  jz      loc_18001B5C7
0x18001b412  cmp     [rsp+0C8h+arg_18], 0
0x18001b41a  jnz     loc_18001B5E4
0x18001b420  xor     r14d, r14d
0x18001b423  xor     r13d, r13d
0x18001b426  mov     r11d, [rbx+0Ch]
0x18001b42a  lea     rdx, [rsi+8]
0x18001b42e  mov     dword ptr [rbx+4], 4D534B59h
0x18001b435  lea     rcx, [rsp+0C8h+var_58+3]
0x18001b43a  mov     eax, [rbp+8]
0x18001b43d  lea     rbp, [rsi+34h]
0x18001b441  or      dword ptr [rbx+1Ch], 1
0x18001b445  mov     [rbx+8], eax
0x18001b448  mov     al, [rdx]
0x18001b44a  inc     rdx
0x18001b44d  mov     [rcx], al
0x18001b44f  dec     rcx
0x18001b452  lea     rax, [rsp+0C8h+var_58]
0x18001b457  cmp     rcx, rax
0x18001b45a  jnb     short loc_18001B448
0x18001b45c  mov     r12d, [rsp+0C8h+arg_20]
0x18001b464  mov     r15d, r12d
0x18001b467  mov     r10d, [rsp+0C8h+var_58]
0x18001b46c  and     r15d, 8
0x18001b470  jnz     loc_18001B5FA
0x18001b476  lea     eax, [r15+1]
0x18001b47a  cmp     r10d, 0FFFFFFFFh
0x18001b47e  jz      loc_18001B5FA
0x18001b484  mov     r9d, [rbx+10h]; int
0x18001b488  mov     rdx, r11; int
0x18001b48b  mov     [rsp+0C8h+var_68], r8; __int64
0x18001b490  mov     rcx, rbp; int
0x18001b493  mov     [rsp+0C8h+var_70], eax; int
0x18001b497  lea     r8, [rsi+20h]; int
0x18001b49b  mov     [rsp+0C8h+var_78], r10d; int
0x18001b4a0  lea     rax, [rsi+0Ch]
0x18001b4a4  mov     [rsp+0C8h+Size], 14h; Size
0x18001b4ad  mov     [rsp+0C8h+var_88], rax; __int64
0x18001b4b2  lea     rax, [r11+rbp]
0x18001b4b6  mov     [rsp+0C8h+var_90], 0; __int64
0x18001b4bf  mov     [rsp+0C8h+var_98], 2; int
0x18001b4c7  mov     qword ptr [rsp+0C8h+var_A0], r11; int
0x18001b4cc  mov     [rsp+0C8h+var_A8], rax; __int64
0x18001b4d1  call    SymCryptDlgroupSetValue
0x18001b4d6  test    eax, eax
0x18001b4d8  jnz     loc_18001B601
0x18001b4de  mov     rcx, [rbx+20h]
0x18001b4e2  call    SymCryptDlkeyAllocate
0x18001b4e7  mov     [rbx+28h], rax
0x18001b4eb  mov     rbp, rax
0x18001b4ee  test    rax, rax
0x18001b4f1  jz      loc_18001B5CF
0x18001b4f7  lea     r11d, [rdi+rdi]
0x18001b4fb  mov     edx, edi
0x18001b4fd  add     r11, 34h ; '4'
0x18001b501  add     r11, rsi
0x18001b504  mov     rcx, r11
0x18001b507  call    IsAllZeros
0x18001b50c  xor     ecx, ecx
0x18001b50e  test    eax, eax
0x18001b510  cmovnz  edi, ecx
0x18001b513  xor     r10d, r10d
0x18001b516  test    eax, eax
0x18001b518  cmovz   r10, r11
0x18001b51c  test    r12b, 20h
0x18001b520  jnz     loc_18001B617
0x18001b526  mov     ecx, r12d
0x18001b529  call    BCryptFlagsToSymCryptKeyValidationFlags
0x18001b52e  bts     eax, 0Ch
0x18001b532  mov     r9d, edi
0x18001b535  mov     qword ptr [rsp+0C8h+var_98], rbp
0x18001b53a  mov     r8, r10
0x18001b53d  mov     rdx, r13
0x18001b540  mov     [rsp+0C8h+var_A0], eax
0x18001b544  mov     rcx, r14
0x18001b547  call    SymCryptDlkeySetValue
0x18001b54c  test    eax, eax
0x18001b54e  jnz     loc_18001B62E
0x18001b554  mov     rax, [rsp+0C8h+arg_28]
0x18001b55c  xor     edi, edi
0x18001b55e  mov     [rax], rbx
0x18001b561  mov     eax, edi
0x18001b563  add     rsp, 88h
0x18001b56a  pop     r15
0x18001b56c  pop     r14
0x18001b56e  pop     r13
0x18001b570  pop     r12
0x18001b572  pop     rdi
0x18001b573  pop     rsi
0x18001b574  pop     rbp
0x18001b575  pop     rbx
0x18001b576  retn
0x18001b578  mov     eax, [rbx]
0x18001b57a  mov     rcx, rbx
0x18001b57d  test    rax, rax
0x18001b580  jz      short loc_18001B58E
0x18001b582  mov     byte ptr [rcx], 0
0x18001b585  inc     rcx
0x18001b588  sub     rax, 1
0x18001b58c  jnz     short loc_18001B582
0x18001b58e  mov     rcx, rbx
0x18001b591  call    MSCryptFree
0x18001b596  jmp     short loc_18001B561
0x18001b598  mov     r9d, 654h
0x18001b59e  mov     ecx, eax
0x18001b5a0  jmp     short loc_18001B5B2
0x18001b5a2  mov     edi, 0C0000017h
0x18001b5a7  mov     r9d, 663h
0x18001b5ad  mov     ecx, 0C0000017h
0x18001b5b2  lea     rdx, aStatus; "Status"
0x18001b5b9  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b5c0  call    DebugTraceError
0x18001b5c5  jmp     short loc_18001B561
0x18001b5c7  mov     r9d, 675h
0x18001b5cd  jmp     short loc_18001B5D5
0x18001b5cf  mov     r9d, 6B2h
0x18001b5d5  mov     edi, 0C0000017h
0x18001b5da  mov     ecx, 0C0000017h
0x18001b5df  jmp     loc_18008145E
0x18001b5e4  lea     r14d, [rdi+rdi*2]
0x18001b5e8  mov     r13d, 14h
0x18001b5ee  add     r14, 34h ; '4'
0x18001b5f2  add     r14, rsi
0x18001b5f5  jmp     loc_18001B426
0x18001b5fa  xor     eax, eax
0x18001b5fc  jmp     loc_18001B484
0x18001b601  mov     ecx, eax
0x18001b603  call    SymcryptErrorCodeToNtStatus
0x18001b608  mov     edi, eax
0x18001b60a  mov     ecx, eax
0x18001b60c  mov     r9d, 6AAh
0x18001b612  jmp     loc_18008145E
0x18001b617  test    r14, r14
0x18001b61a  jz      loc_18008144E
0x18001b620  test    r10, r10
0x18001b623  jnz     loc_18001B526
0x18001b629  jmp     loc_18008144E
0x18001b62e  mov     ecx, eax
0x18001b630  call    SymcryptErrorCodeToNtStatus
0x18001b635  mov     ecx, eax
0x18001b637  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001b63e  mov     r9d, 6D6h
0x18001b644  lea     rdx, aStatus; "Status"
0x18001b64b  mov     edi, eax
0x18001b64d  call    DebugTraceError
0x18001b652  test    r15d, r15d
0x18001b655  jnz     loc_180081471
0x18001b65b  mov     r9d, edi
0x18001b65e  lea     rdx, aDsa; "DSA"
0x18001b665  mov     r8d, 992h
0x18001b66b  call    MSCryptAuditPrimitiveFailure
0x18001b670  nop
0x18001b671  jmp     loc_180081471
0x18008144e  mov     edi, 0C000000Dh
0x180081453  mov     r9d, 6C4h
0x180081459  mov     ecx, 0C000000Dh
0x18008145e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180081465  lea     rdx, aStatus; "Status"
0x18008146c  call    DebugTraceError
0x180081471  mov     rcx, [rbx+28h]
0x180081475  test    rcx, rcx
0x180081478  jz      short loc_180081487
0x18008147a  call    SymCryptDlkeyFree
0x18008147f  mov     qword ptr [rbx+28h], 0
0x180081487  mov     rcx, [rbx+20h]
0x18008148b  test    rcx, rcx
0x18008148e  jz      loc_18001B578
0x180081494  call    SymCryptMlDsaTemporariesFree
0x180081499  mov     qword ptr [rbx+20h], 0
0x1800814a1  jmp     loc_18001B578
```
