# MSCryptRsaSignHash

- ea: `0x18003d300`
- end: `0x18003d56c`
- name: `MSCryptRsaSignHash`
- size: `620`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, unsigned int, unsigned int *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003ce80`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18000f450`
- `0x180010270`
- `0x18003cfd4`
- `0x18003d300`
- `0x18003d884`
- `0x18003e154`
- `0x180050bcc`
- `0x180056cf0`

## string_xrefs

- `0x18003d364`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d41c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d4eb`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d532`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaSignHash(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        unsigned int *a7,
        int a8)
{
  unsigned int v8; // ebx
  __int64 v12; // rdi
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 v15; // r15
  int HashOidList; // eax
  __int64 v17; // r9
  unsigned int v18; // eax
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // rcx
  int v23; // [rsp+50h] [rbp-28h] BYREF
  __int64 v24; // [rsp+58h] [rbp-20h]
  __int64 v25; // [rsp+60h] [rbp-18h] BYREF
  __int64 v26; // [rsp+68h] [rbp-10h] BYREF

  v8 = 0;
  v26 = 0;
  v12 = 0;
  v25 = 0;
  v23 = 0;
  v13 = 0;
  if ( (a8 & 0xFFFFFFF5) == 0 )
  {
    v14 = validateMSCryptRsaKey();
    v15 = v14;
    if ( v14 && *(_DWORD *)(v14 + 16) )
    {
      v13 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v14 + 32) + 16LL) + 7) >> 3;
      v24 = v13;
      if ( !a5 )
        goto LABEL_34;
      if ( a2 && a3 && a4 )
      {
        if ( a6 < v13 )
        {
          v8 = -1073741789;
          goto LABEL_34;
        }
        if ( (a8 & 2) != 0 )
        {
          HashOidList = GetHashOidList(a2, a4, &v25, &v23);
          v8 = HashOidList;
          if ( HashOidList < 0 )
          {
            DebugTraceError(
              (unsigned int)HashOidList,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
              2064);
            v12 = v25;
            goto LABEL_34;
          }
          v12 = v25;
          if ( v25 )
            v17 = *(_QWORD *)(v25 + 8);
          else
            LODWORD(v17) = 0;
          if ( a4 > v13 )
            a4 = v13;
          v18 = SymCryptRsaPkcs1Sign(*(_QWORD *)(v15 + 32), a3, a4, v17);
LABEL_27:
          if ( v18 )
          {
            v8 = SymcryptErrorCodeToNtStatus(v18);
            DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 2110);
          }
          else
          {
            v8 = 0;
          }
          v13 = v24;
          goto LABEL_34;
        }
        v19 = CheckAndGetPssHashAlgorithm(a2, a4, &v26);
        v8 = v19;
        if ( v19 >= 0 )
        {
          if ( a4 > v13 )
            a4 = v13;
          v18 = SymCryptRsaPssSign(*(_QWORD *)(v15 + 32), a3, a4, v26, *(unsigned int *)(a2 + 8));
          goto LABEL_27;
        }
        v20 = 2090;
        v21 = (unsigned int)v19;
      }
      else
      {
        v8 = -1073741811;
        v20 = 2039;
        v21 = 3221225485LL;
      }
    }
    else
    {
      v8 = -1073741816;
      v20 = 2021;
      v21 = 3221225480LL;
    }
    DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v20);
    goto LABEL_34;
  }
  v8 = -1073741811;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      219);
LABEL_34:
  *a7 = v13;
  if ( v12 )
    MSCryptFree(v12);
  return v8;
}

```

## disassembly

```asm
0x18003d300  push    rbp
0x18003d302  push    rbx
0x18003d303  push    rsi
0x18003d304  push    rdi
0x18003d305  push    r12
0x18003d307  push    r13
0x18003d309  push    r14
0x18003d30b  push    r15
0x18003d30d  mov     rbp, rsp
0x18003d310  sub     rsp, 78h
0x18003d314  xor     ebx, ebx
0x18003d316  mov     r14d, r9d
0x18003d319  test    [rbp+arg_38], 0FFFFFFF5h
0x18003d323  mov     r13, r8
0x18003d326  mov     r12, rdx
0x18003d329  mov     [rbp+var_10], rbx
0x18003d32d  mov     edi, ebx
0x18003d32f  mov     [rbp+var_18], rbx
0x18003d333  mov     [rbp+var_28], ebx
0x18003d336  mov     esi, ebx
0x18003d338  jz      short loc_18003D391
0x18003d33a  mov     ebx, 0C000000Dh
0x18003d33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d346  lea     rax, WPP_GLOBAL_Control
0x18003d34d  cmp     rcx, rax
0x18003d350  jz      loc_18003D545
0x18003d356  test    byte ptr [rcx+1Ch], 1
0x18003d35a  jz      loc_18003D545
0x18003d360  mov     rcx, [rcx+10h]
0x18003d364  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d36b  mov     [rsp+78h+var_48], 7DBh
0x18003d373  lea     r9, aStatus; "Status"
0x18003d37a  mov     [rsp+78h+var_50], r8
0x18003d37f  mov     dword ptr [rsp+78h+var_58], 0C000000Dh
0x18003d387  call    WPP_SF_sDsd
0x18003d38c  jmp     loc_18003D545
0x18003d391  call    validateMSCryptRsaKey
0x18003d396  mov     r15, rax
0x18003d399  test    rax, rax
0x18003d39c  jz      loc_18003D522
0x18003d3a2  cmp     [rax+10h], ebx
0x18003d3a5  jz      loc_18003D522
0x18003d3ab  mov     rax, [rax+20h]
0x18003d3af  mov     esi, [rax+10h]
0x18003d3b2  add     esi, 7
0x18003d3b5  shr     esi, 3
0x18003d3b8  mov     [rbp+var_20], rsi
0x18003d3bc  cmp     [rbp+arg_20], rbx
0x18003d3c0  jz      loc_18003D545
0x18003d3c6  test    r12, r12
0x18003d3c9  jz      loc_18003D510
0x18003d3cf  test    r13, r13
0x18003d3d2  jz      loc_18003D510
0x18003d3d8  test    r14d, r14d
0x18003d3db  jz      loc_18003D510
0x18003d3e1  cmp     [rbp+arg_28], esi
0x18003d3e4  jnb     short loc_18003D3F0
0x18003d3e6  mov     ebx, 0C0000023h
0x18003d3eb  jmp     loc_18003D545
0x18003d3f0  test    byte ptr [rbp+arg_38], 2
0x18003d3f7  mov     edx, r14d
0x18003d3fa  mov     rcx, r12
0x18003d3fd  jz      loc_18003D487
0x18003d403  lea     r9, [rbp+var_28]
0x18003d407  lea     r8, [rbp+var_18]
0x18003d40b  call    GetHashOidList
0x18003d410  mov     ebx, eax
0x18003d412  test    eax, eax
0x18003d414  jns     short loc_18003D43A
0x18003d416  mov     r9d, 810h
0x18003d41c  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d423  lea     rdx, aStatus; "Status"
0x18003d42a  mov     ecx, eax
0x18003d42c  call    DebugTraceError
0x18003d431  mov     rdi, [rbp+var_18]
0x18003d435  jmp     loc_18003D545
0x18003d43a  mov     rdi, [rbp+var_18]
0x18003d43e  xor     eax, eax
0x18003d440  test    rdi, rdi
0x18003d443  setz    al
0x18003d446  test    rdi, rdi
0x18003d449  jz      short loc_18003D451
0x18003d44b  mov     r9, [rdi+8]
0x18003d44f  jmp     short loc_18003D454
0x18003d451  xor     r9d, r9d
0x18003d454  lea     rcx, [rbp+var_20]
0x18003d458  cmp     r14d, esi
0x18003d45b  mov     [rsp+78h+var_30], rcx
0x18003d460  mov     rdx, r13
0x18003d463  mov     rcx, [rbp+arg_20]
0x18003d467  cmova   r14d, esi
0x18003d46b  mov     [rsp+78h+var_38], rsi
0x18003d470  mov     [rsp+78h+var_40], rcx
0x18003d475  mov     rcx, [r15+20h]
0x18003d479  mov     r8d, r14d
0x18003d47c  mov     dword ptr [rsp+78h+var_50], eax
0x18003d480  call    SymCryptRsaPkcs1Sign
0x18003d485  jmp     short loc_18003D4DE
0x18003d487  lea     r8, [rbp+var_10]
0x18003d48b  call    CheckAndGetPssHashAlgorithm
0x18003d490  mov     ebx, eax
0x18003d492  test    eax, eax
0x18003d494  jns     short loc_18003D4A3
0x18003d496  mov     r9d, 82Ah
0x18003d49c  mov     ecx, eax
0x18003d49e  jmp     loc_18003D532
0x18003d4a3  mov     eax, [r12+8]
0x18003d4a8  lea     rcx, [rbp+var_20]
0x18003d4ac  mov     r9, [rbp+var_10]
0x18003d4b0  cmp     r14d, esi
0x18003d4b3  mov     [rsp+78h+var_30], rcx
0x18003d4b8  mov     rdx, r13
0x18003d4bb  mov     rcx, [rbp+arg_20]
0x18003d4bf  cmova   r14d, esi
0x18003d4c3  mov     [rsp+78h+var_38], rsi
0x18003d4c8  mov     [rsp+78h+var_40], rcx
0x18003d4cd  mov     rcx, [r15+20h]
0x18003d4d1  mov     r8d, r14d
0x18003d4d4  mov     [rsp+78h+var_58], rax
0x18003d4d9  call    SymCryptRsaPssSign
0x18003d4de  test    eax, eax
0x18003d4e0  jz      short loc_18003D50C
0x18003d4e2  mov     ecx, eax
0x18003d4e4  call    SymcryptErrorCodeToNtStatus
0x18003d4e9  mov     ecx, eax
0x18003d4eb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d4f2  mov     r9d, 83Eh
0x18003d4f8  lea     rdx, aStatus; "Status"
0x18003d4ff  mov     ebx, eax
0x18003d501  call    DebugTraceError
0x18003d506  mov     rsi, [rbp+var_20]
0x18003d50a  jmp     short loc_18003D545
0x18003d50c  xor     ebx, ebx
0x18003d50e  jmp     short loc_18003D506
0x18003d510  mov     ebx, 0C000000Dh
0x18003d515  mov     r9d, 7F7h
0x18003d51b  mov     ecx, 0C000000Dh
0x18003d520  jmp     short loc_18003D532
0x18003d522  mov     ebx, 0C0000008h
0x18003d527  mov     r9d, 7E5h
0x18003d52d  mov     ecx, 0C0000008h
0x18003d532  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d539  lea     rdx, aStatus; "Status"
0x18003d540  call    DebugTraceError
0x18003d545  mov     rax, [rbp+arg_30]
0x18003d549  mov     [rax], esi
0x18003d54b  test    rdi, rdi
0x18003d54e  jz      short loc_18003D558
0x18003d550  mov     rcx, rdi
0x18003d553  call    MSCryptFree
0x18003d558  mov     eax, ebx
0x18003d55a  add     rsp, 78h
0x18003d55e  pop     r15
0x18003d560  pop     r14
0x18003d562  pop     r13
0x18003d564  pop     r12
0x18003d566  pop     rdi
0x18003d567  pop     rsi
0x18003d568  pop     rbx
0x18003d569  pop     rbp
0x18003d56a  retn
```
