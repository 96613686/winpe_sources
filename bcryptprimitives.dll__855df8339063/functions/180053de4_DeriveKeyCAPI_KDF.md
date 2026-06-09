# DeriveKeyCAPI_KDF

- ea: `0x180053de4`
- end: `0x180054119`
- name: `DeriveKeyCAPI_KDF`
- size: `821`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180012060`

## callees

- `0x18000ecb0`
- `0x18000ed00`
- `0x18000ee60`
- `0x18000ef70`
- `0x18000f810`
- `0x180010270`
- `0x1800102a0`
- `0x180012a80`
- `0x180013a50`
- `0x180013b70`
- `0x1800173f0`
- `0x180053de4`
- `0x180063170`
- `0x18006c5c4`

## string_xrefs

- `0x180053e57`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180053f15`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180053f7f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800540a4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`

## pseudocode

```c
__int64 __fastcall DeriveKeyCAPI_KDF(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int *a5,
        unsigned int a6)
{
  void *v7; // rdi
  __int64 v8; // rsi
  const wchar_t *v9; // r14
  unsigned int v10; // ebx
  __int64 v11; // r9
  int ParameterList; // eax
  __int64 v13; // r11
  int v14; // ecx
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // r15
  size_t v18; // r13
  const wchar_t *v19; // rdx
  wchar_t *v20; // rax
  unsigned int v21; // eax
  unsigned int HashProperty; // eax
  __int64 v23; // rcx
  unsigned int v24; // r15d
  __int64 v25; // rax
  _BYTE *v26; // rdx
  size_t Size; // [rsp+30h] [rbp-38h]
  int v29; // [rsp+40h] [rbp-28h]
  unsigned int v30; // [rsp+44h] [rbp-24h] BYREF
  int v31[2]; // [rsp+48h] [rbp-20h] BYREF
  int v32[2]; // [rsp+50h] [rbp-18h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v35; // [rsp+C0h] [rbp+58h]
  unsigned int v36; // [rsp+C8h] [rbp+60h]

  v36 = a4;
  v35 = a3;
  *(_QWORD *)v31 = 0;
  *(_QWORD *)v32 = 0;
  v7 = 0;
  LODWORD(v34) = 0;
  v8 = 0;
  v30 = 0;
  v9 = 0;
  if ( a2 )
  {
    if ( (a6 & 0xFFFFFFEF) != 0 )
    {
      v11 = 1441;
LABEL_30:
      v10 = -1073741811;
      v23 = 3221225485LL;
      goto LABEL_31;
    }
    *a5 = 0;
    ParameterList = QueryParameterList(a2, 0, 0);
    if ( ParameterList < 0 )
    {
      v11 = 1467;
      goto LABEL_30;
    }
    v14 = *(_DWORD *)(v13 + 32);
    v29 = v14;
    _mm_lfence();
    v15 = ParameterList;
    v16 = *(_QWORD *)(a2 + 8);
    v17 = 2 * v15;
    if ( (*(_BYTE *)(v16 + 8 * v17) & 1) != 0 || *(_DWORD *)(v16 + 8 * v17) < 2u )
    {
      v11 = 1478;
      goto LABEL_30;
    }
    v18 = *(unsigned int *)(v16 + 8 * v17);
    v19 = *(const wchar_t **)(v16 + 8 * v17 + 8);
    if ( v19[(v18 >> 1) - 1] )
    {
      v20 = (wchar_t *)SafeAllocaAllocateFromHeap(v18 + 2);
      v9 = v20;
      if ( !v20 )
      {
        v10 = -1073741801;
        DebugTraceError(
          3221225495LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
          1493);
        goto LABEL_32;
      }
      memcpy_0(v20, *(const void **)(*(_QWORD *)(a2 + 8) + 8 * v17 + 8), v18);
      v14 = v29;
      v9[v18 >> 1] = 0;
      v19 = v9;
    }
    v21 = MSCryptOpenHashProvider(v32, v19, (unsigned int)(v14 != 0) + 32);
    v10 = v21;
    if ( v21 )
    {
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", 1517);
      v7 = *(void **)v32;
      goto LABEL_32;
    }
    v7 = *(void **)v32;
    HashProperty = MSCryptGetHashProperty(*(__int64 *)v32, L"ObjectLength", &v34, 4u, &v30, 0);
    v10 = HashProperty;
    if ( HashProperty )
    {
      v11 = 1531;
    }
    else
    {
      v8 = SafeAllocaAllocateFromHeap((unsigned int)v34);
      if ( !v8 )
      {
        v10 = -1073741801;
        v11 = 1539;
        v23 = 3221225495LL;
        goto LABEL_31;
      }
      LODWORD(Size) = 0;
      HashProperty = MSCryptCreateMultiHash((int)v7, (int)v31, 0, v8, v34, 0, Size, 0);
      v10 = HashProperty;
      if ( HashProperty )
      {
        v11 = 1555;
      }
      else
      {
        HashProperty = MSCryptHashData(*(_QWORD *)v31, *(_QWORD *)(a1 + 24), *(unsigned int *)(a1 + 16), 0);
        v10 = HashProperty;
        if ( HashProperty )
        {
          v11 = 1566;
        }
        else
        {
          v24 = v36;
          HashProperty = CapiKDF(*(_QWORD *)v31, v35, v36, a6);
          v10 = HashProperty;
          if ( !HashProperty )
          {
            v10 = 0;
            *a5 = v24;
            goto LABEL_32;
          }
          v11 = 1578;
        }
      }
    }
    v23 = HashProperty;
LABEL_31:
    DebugTraceError(v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c", v11);
    goto LABEL_32;
  }
  v10 = -1073741811;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v10;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    0,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
    (unsigned int)"Status",
    13,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
    154);
LABEL_32:
  if ( *(_QWORD *)v31 )
    MSCryptDestroyHash();
  if ( v8 )
  {
    v25 = (unsigned int)v34;
    v26 = (_BYTE *)v8;
    if ( (_DWORD)v34 )
    {
      do
      {
        *v26++ = 0;
        --v25;
      }
      while ( v25 );
    }
    MSCryptFree(v8);
  }
  if ( v7 )
    MSCryptCloseHashProvider(v7);
  if ( v9 )
    MSCryptFree(v9);
  return v10;
}

```

## disassembly

```asm
0x180053de4  mov     [rsp-40h+arg_18], r9d
0x180053de9  mov     [rsp-40h+arg_10], r8
0x180053dee  mov     [rsp-40h+arg_0], rcx
0x180053df3  push    rbp
0x180053df4  push    rbx
0x180053df5  push    rsi
0x180053df6  push    rdi
0x180053df7  push    r12
0x180053df9  push    r13
0x180053dfb  push    r14
0x180053dfd  push    r15
0x180053dff  mov     rbp, rsp
0x180053e02  sub     rsp, 68h
0x180053e06  xor     r12d, r12d
0x180053e09  mov     rbx, rdx
0x180053e0c  mov     qword ptr [rbp+var_20], r12
0x180053e10  mov     r11, rcx
0x180053e13  mov     qword ptr [rbp+var_18], r12
0x180053e17  mov     edi, r12d
0x180053e1a  mov     dword ptr [rbp+arg_8], r12d
0x180053e1e  mov     esi, r12d
0x180053e21  mov     [rbp+var_24], r12d
0x180053e25  mov     r14d, r12d
0x180053e28  test    rdx, rdx
0x180053e2b  jnz     short loc_180053E84
0x180053e2d  mov     ebx, 0C000000Dh
0x180053e32  mov     rcx, cs:WPP_GLOBAL_Control
0x180053e39  lea     rax, WPP_GLOBAL_Control
0x180053e40  cmp     rcx, rax
0x180053e43  jz      loc_180054105
0x180053e49  test    byte ptr [rcx+1Ch], 1
0x180053e4d  jz      loc_180054105
0x180053e53  mov     rcx, [rcx+10h]
0x180053e57  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180053e5e  mov     dword ptr [rsp+68h+Size], 59Ah
0x180053e66  lea     r9, aStatus; "Status"
0x180053e6d  mov     [rsp+68h+Src], r8
0x180053e72  mov     [rsp+68h+var_48], 0C000000Dh
0x180053e7a  call    WPP_SF_sDsd
0x180053e7f  jmp     loc_1800540B7
0x180053e84  test    [rbp+arg_28], 0FFFFFFEFh
0x180053e8b  jz      short loc_180053E98
0x180053e8d  mov     r9d, 5A1h
0x180053e93  jmp     loc_18005409A
0x180053e98  mov     rax, [rbp+arg_20]
0x180053e9c  xor     r8d, r8d
0x180053e9f  xor     edx, edx
0x180053ea1  mov     rcx, rbx
0x180053ea4  mov     [rax], r12d
0x180053ea7  call    QueryParameterList
0x180053eac  test    eax, eax
0x180053eae  jns     short loc_180053EBB
0x180053eb0  mov     r9d, 5BBh
0x180053eb6  jmp     loc_18005409A
0x180053ebb  mov     ecx, [r11+20h]
0x180053ebf  mov     [rbp+var_28], ecx
0x180053ec2  lfence
0x180053ec5  movsxd  r15, eax
0x180053ec8  mov     rax, [rbx+8]
0x180053ecc  add     r15, r15
0x180053ecf  test    byte ptr [rax+r15*8], 1
0x180053ed4  jnz     loc_180054094
0x180053eda  cmp     dword ptr [rax+r15*8], 2
0x180053edf  jb      loc_180054094
0x180053ee5  mov     r13d, [rax+r15*8]
0x180053ee9  mov     rdx, [rax+r15*8+8]
0x180053eee  mov     r12d, r13d
0x180053ef1  shr     r12, 1
0x180053ef4  xor     eax, eax
0x180053ef6  cmp     ax, [rdx+r12*2-2]
0x180053efc  jz      short loc_180053F5B
0x180053efe  lea     rcx, [r13+2]
0x180053f02  call    SafeAllocaAllocateFromHeap
0x180053f07  mov     r14, rax
0x180053f0a  test    rax, rax
0x180053f0d  jnz     short loc_180053F3A
0x180053f0f  mov     r9d, 5D5h
0x180053f15  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180053f1c  lea     rdx, aStatus; "Status"
0x180053f23  mov     ecx, 0C0000017h
0x180053f28  mov     ebx, 0C0000017h
0x180053f2d  call    DebugTraceError
0x180053f32  xor     r12d, r12d
0x180053f35  jmp     loc_1800540B7
0x180053f3a  mov     rdx, [rbx+8]
0x180053f3e  mov     r8, r13; Size
0x180053f41  mov     rcx, r14; void *
0x180053f44  mov     rdx, [rdx+r15*8+8]; Src
0x180053f49  call    memcpy_0
0x180053f4e  mov     ecx, [rbp+var_28]
0x180053f51  xor     eax, eax
0x180053f53  mov     [r14+r12*2], ax
0x180053f58  mov     rdx, r14
0x180053f5b  neg     ecx
0x180053f5d  lea     rcx, [rbp+var_18]
0x180053f61  sbb     r8d, r8d
0x180053f64  neg     r8d
0x180053f67  add     r8d, 20h ; ' '
0x180053f6b  call    MSCryptOpenHashProvider
0x180053f70  xor     r12d, r12d
0x180053f73  mov     ebx, eax
0x180053f75  test    eax, eax
0x180053f77  jz      short loc_180053F9D
0x180053f79  mov     r9d, 5EDh
0x180053f7f  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180053f86  lea     rdx, aStatus; "Status"
0x180053f8d  mov     ecx, eax
0x180053f8f  call    DebugTraceError
0x180053f94  mov     rdi, qword ptr [rbp+var_18]
0x180053f98  jmp     loc_1800540B7
0x180053f9d  mov     rdi, qword ptr [rbp+var_18]
0x180053fa1  lea     rax, [rbp+var_24]
0x180053fa5  mov     rcx, rdi
0x180053fa8  mov     dword ptr [rsp+68h+Src], r12d
0x180053fad  mov     r9d, 4
0x180053fb3  mov     qword ptr [rsp+68h+var_48], rax
0x180053fb8  lea     r8, [rbp+arg_8]
0x180053fbc  lea     rdx, aObjectlength; "ObjectLength"
0x180053fc3  call    MSCryptGetHashProperty
0x180053fc8  mov     ebx, eax
0x180053fca  test    eax, eax
0x180053fcc  jz      short loc_180053FDB
0x180053fce  mov     r9d, 5FBh
0x180053fd4  mov     ecx, eax
0x180053fd6  jmp     loc_1800540A4
0x180053fdb  mov     ecx, dword ptr [rbp+arg_8]
0x180053fde  call    SafeAllocaAllocateFromHeap
0x180053fe3  mov     rsi, rax
0x180053fe6  test    rax, rax
0x180053fe9  jnz     short loc_180054000
0x180053feb  mov     ebx, 0C0000017h
0x180053ff0  mov     r9d, 603h
0x180053ff6  mov     ecx, 0C0000017h
0x180053ffb  jmp     loc_1800540A4
0x180054000  mov     eax, dword ptr [rbp+arg_8]
0x180054003  lea     rdx, [rbp+var_20]; int
0x180054007  mov     [rsp+68h+var_30], r12d; int
0x18005400c  mov     r9, rsi; int
0x18005400f  mov     dword ptr [rsp+68h+Size], r12d; Size
0x180054014  xor     r8d, r8d; int
0x180054017  mov     [rsp+68h+Src], r12; Src
0x18005401c  mov     rcx, rdi; int
0x18005401f  mov     [rsp+68h+var_48], eax; int
0x180054023  call    MSCryptCreateMultiHash
0x180054028  mov     ebx, eax
0x18005402a  test    eax, eax
0x18005402c  jz      short loc_180054036
0x18005402e  mov     r9d, 613h
0x180054034  jmp     short loc_180053FD4
0x180054036  mov     rdx, [rbp+arg_0]
0x18005403a  xor     r9d, r9d
0x18005403d  mov     rcx, qword ptr [rbp+var_20]
0x180054041  mov     r8d, [rdx+10h]
0x180054045  mov     rdx, [rdx+18h]
0x180054049  call    MSCryptHashData
0x18005404e  mov     ebx, eax
0x180054050  test    eax, eax
0x180054052  jz      short loc_18005405F
0x180054054  mov     r9d, 61Eh
0x18005405a  jmp     loc_180053FD4
0x18005405f  mov     r15d, [rbp+arg_18]
0x180054063  mov     r8d, r15d
0x180054066  mov     r9d, [rbp+arg_28]
0x18005406a  mov     rdx, [rbp+arg_10]
0x18005406e  mov     rcx, qword ptr [rbp+var_20]
0x180054072  call    _CapiKDF
0x180054077  mov     ebx, eax
0x180054079  test    eax, eax
0x18005407b  jz      short loc_180054088
0x18005407d  mov     r9d, 62Ah
0x180054083  jmp     loc_180053FD4
0x180054088  mov     rax, [rbp+arg_20]
0x18005408c  mov     ebx, r12d
0x18005408f  mov     [rax], r15d
0x180054092  jmp     short loc_1800540B7
0x180054094  mov     r9d, 5C6h
0x18005409a  mov     ebx, 0C000000Dh
0x18005409f  mov     ecx, 0C000000Dh
0x1800540a4  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800540ab  lea     rdx, aStatus; "Status"
0x1800540b2  call    DebugTraceError
0x1800540b7  mov     rcx, qword ptr [rbp+var_20]
0x1800540bb  test    rcx, rcx
0x1800540be  jz      short loc_1800540C5
0x1800540c0  call    MSCryptDestroyHash
0x1800540c5  test    rsi, rsi
0x1800540c8  jz      short loc_1800540E9
0x1800540ca  mov     eax, dword ptr [rbp+arg_8]
0x1800540cd  mov     rdx, rsi
0x1800540d0  test    rax, rax
0x1800540d3  jz      short loc_1800540E1
0x1800540d5  mov     [rdx], r12b
0x1800540d8  inc     rdx
0x1800540db  sub     rax, 1
0x1800540df  jnz     short loc_1800540D5
0x1800540e1  mov     rcx, rsi
0x1800540e4  call    MSCryptFree
0x1800540e9  test    rdi, rdi
0x1800540ec  jz      short loc_1800540F8
0x1800540ee  xor     edx, edx
0x1800540f0  mov     rcx, rdi; P
0x1800540f3  call    MSCryptCloseHashProvider
0x1800540f8  test    r14, r14
0x1800540fb  jz      short loc_180054105
0x1800540fd  mov     rcx, r14
0x180054100  call    MSCryptFree
0x180054105  mov     eax, ebx
0x180054107  add     rsp, 68h
0x18005410b  pop     r15
0x18005410d  pop     r14
0x18005410f  pop     r13
0x180054111  pop     r12
0x180054113  pop     rdi
0x180054114  pop     rsi
0x180054115  pop     rbx
0x180054116  pop     rbp
0x180054117  retn
```
