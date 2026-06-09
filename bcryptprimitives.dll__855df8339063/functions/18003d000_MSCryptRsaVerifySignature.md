# MSCryptRsaVerifySignature

- ea: `0x18003d000`
- end: `0x18003d2f2`
- name: `MSCryptRsaVerifySignature`
- size: `754`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, __int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003cf30`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18000f450`
- `0x180010270`
- `0x180024210`
- `0x18003cfd4`
- `0x18003d000`
- `0x18003d884`
- `0x18003e2a0`
- `0x180056cf0`

## string_xrefs

- `0x18003d055`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d12c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d1e6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d27c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`
- `0x18003d2ac`: `onecore\ds\security\cryptoapi\ncrypt\msprim\rsa\rsa.c`

## pseudocode

```c
__int64 __fastcall MSCryptRsaVerifySignature(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int *v7; // rdi
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // r15
  unsigned int v15; // esi
  int HashOidList; // eax
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // eax
  int v20; // edx
  int v21; // edx
  int v23; // [rsp+28h] [rbp-70h]
  int v24; // [rsp+50h] [rbp-48h] BYREF
  unsigned int *v25; // [rsp+58h] [rbp-40h] BYREF
  __int64 v26; // [rsp+60h] [rbp-38h] BYREF

  v7 = 0;
  v26 = 0;
  v25 = 0;
  v24 = 0;
  if ( (a7 & 0xFFFFFFE5) != 0 )
  {
    v10 = 2190;
LABEL_3:
    v11 = -1073741811;
    v12 = 3221225485LL;
LABEL_4:
    DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", v10);
    return v11;
  }
  if ( !a2 || !a3 || !a5 || !a4 )
  {
    v11 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c", 2198);
LABEL_39:
    if ( v7 )
      MSCryptFree(v7);
    return v11;
  }
  v13 = validateMSCryptRsaKey();
  v14 = v13;
  if ( !v13 )
  {
    v10 = 2207;
LABEL_11:
    v11 = -1073741816;
    v12 = 3221225480LL;
    goto LABEL_4;
  }
  if ( !*(_DWORD *)(v13 + 16) )
  {
    v10 = 2215;
    goto LABEL_11;
  }
  v15 = (unsigned int)(*(_DWORD *)(*(_QWORD *)(v13 + 32) + 16LL) + 7) >> 3;
  if ( a6 < v15 )
  {
    v10 = 2224;
    goto LABEL_3;
  }
  if ( (a7 & 0x12) != 0 )
  {
    if ( a6 > v15 )
    {
      v11 = -1073700864;
      v10 = 2245;
      v12 = 3221266432LL;
      goto LABEL_4;
    }
    HashOidList = GetHashOidList(a2, a4, &v25, &v24);
    v11 = HashOidList;
    if ( HashOidList < 0 )
    {
      DebugTraceError(
        (unsigned int)HashOidList,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
        2252);
      v7 = v25;
      goto LABEL_39;
    }
    v7 = v25;
    if ( v25 )
      v17 = *v25;
    else
      v17 = 0;
    if ( v25 )
      v18 = *((_QWORD *)v25 + 1);
    else
      v18 = 0;
    v19 = SymCryptRsaPkcs1Verify(*(_QWORD *)(v14 + 32), v15, v23, v18, v17, (a7 >> 3) & 2);
LABEL_33:
    if ( v19 )
    {
      v11 = SymcryptErrorCodeToNtStatus(v19);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          (unsigned int)"Status",
          v11,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
          248);
    }
    else
    {
      v11 = 0;
    }
    goto LABEL_39;
  }
  v11 = CheckAndGetPssHashAlgorithm(a2, a4, &v26);
  if ( (v11 & 0x80000000) == 0 )
  {
    v19 = SymCryptRsaPssVerify(*(_QWORD *)(v14 + 32), a6, v23, v26, *(unsigned int *)(a2 + 8));
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      (unsigned int)"Status",
      v11,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\rsa\\rsa.c",
      229);
  return v11;
}

```

## disassembly

```asm
0x18003d000  mov     r11, rsp
0x18003d003  mov     [r11+8], rbx
0x18003d007  mov     [r11+10h], rbp
0x18003d00b  mov     [r11+18h], r8
0x18003d00f  push    rsi
0x18003d010  push    rdi
0x18003d011  push    r12
0x18003d013  push    r14
0x18003d015  push    r15
0x18003d017  sub     rsp, 70h
0x18003d01b  mov     ebp, [rsp+98h+arg_30]
0x18003d022  xor     edi, edi
0x18003d024  mov     qword ptr [r11-38h], 0
0x18003d02c  mov     r14d, r9d
0x18003d02f  mov     [r11-40h], rdi
0x18003d033  mov     rax, r8
0x18003d036  mov     [rsp+98h+var_48], edi
0x18003d03a  mov     r12, rdx
0x18003d03d  test    ebp, 0FFFFFFE5h
0x18003d043  jz      short loc_18003D06D
0x18003d045  mov     r9d, 88Eh
0x18003d04b  mov     ebx, 0C000000Dh
0x18003d050  mov     ecx, 0C000000Dh
0x18003d055  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d05c  lea     rdx, aStatus; "Status"
0x18003d063  call    DebugTraceError
0x18003d068  jmp     loc_18003D2D6
0x18003d06d  test    r12, r12
0x18003d070  jz      loc_18003D2A6
0x18003d076  test    rax, rax
0x18003d079  jz      loc_18003D2A6
0x18003d07f  cmp     [rsp+98h+arg_20], rdi
0x18003d087  jz      loc_18003D2A6
0x18003d08d  test    r14d, r14d
0x18003d090  jz      loc_18003D2A6
0x18003d096  call    validateMSCryptRsaKey
0x18003d09b  mov     r15, rax
0x18003d09e  test    rax, rax
0x18003d0a1  jnz     short loc_18003D0B5
0x18003d0a3  mov     r9d, 89Fh
0x18003d0a9  mov     ebx, 0C0000008h
0x18003d0ae  mov     ecx, 0C0000008h
0x18003d0b3  jmp     short loc_18003D055
0x18003d0b5  cmp     [rax+10h], edi
0x18003d0b8  jnz     short loc_18003D0C2
0x18003d0ba  mov     r9d, 8A7h
0x18003d0c0  jmp     short loc_18003D0A9
0x18003d0c2  mov     rax, [rax+20h]
0x18003d0c6  mov     esi, [rax+10h]
0x18003d0c9  add     esi, 7
0x18003d0cc  shr     esi, 3
0x18003d0cf  cmp     [rsp+98h+arg_28], esi
0x18003d0d6  jnb     short loc_18003D0E3
0x18003d0d8  mov     r9d, 8B0h
0x18003d0de  jmp     loc_18003D04B
0x18003d0e3  test    bpl, 12h
0x18003d0e7  jz      loc_18003D1AB
0x18003d0ed  cmp     [rsp+98h+arg_28], esi
0x18003d0f4  jbe     short loc_18003D10B
0x18003d0f6  mov     ebx, 0C000A000h
0x18003d0fb  mov     r9d, 8C5h
0x18003d101  mov     ecx, 0C000A000h
0x18003d106  jmp     loc_18003D055
0x18003d10b  lea     r9, [rsp+98h+var_48]
0x18003d110  mov     edx, r14d
0x18003d113  lea     r8, [rsp+98h+var_40]
0x18003d118  mov     rcx, r12
0x18003d11b  call    GetHashOidList
0x18003d120  mov     ebx, eax
0x18003d122  test    eax, eax
0x18003d124  jns     short loc_18003D14B
0x18003d126  mov     r9d, 8CCh
0x18003d12c  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d133  lea     rdx, aStatus; "Status"
0x18003d13a  mov     ecx, eax
0x18003d13c  call    DebugTraceError
0x18003d141  mov     rdi, [rsp+98h+var_40]
0x18003d146  jmp     loc_18003D2C9
0x18003d14b  mov     rdi, [rsp+98h+var_40]
0x18003d150  shr     ebp, 3
0x18003d153  and     ebp, 2
0x18003d156  test    rdi, rdi
0x18003d159  jz      short loc_18003D15F
0x18003d15b  mov     eax, [rdi]
0x18003d15d  jmp     short loc_18003D161
0x18003d15f  xor     eax, eax
0x18003d161  test    rdi, rdi
0x18003d164  jz      short loc_18003D16C
0x18003d166  mov     rdx, [rdi+8]
0x18003d16a  jmp     short loc_18003D16E
0x18003d16c  xor     edx, edx
0x18003d16e  mov     r9, [rsp+98h+arg_20]
0x18003d176  cmp     r14d, esi
0x18003d179  mov     [rsp+98h+var_58], ebp; int
0x18003d17d  mov     [rsp+98h+var_60], rax; __int64
0x18003d182  cmova   r14d, esi
0x18003d186  mov     [rsp+98h+var_68], rdx; __int64
0x18003d18b  mov     rdx, [rsp+98h+arg_10]
0x18003d193  mov     ecx, esi
0x18003d195  mov     qword ptr [rsp+98h+var_78], rcx; int
0x18003d19a  mov     rcx, [r15+20h]; int
0x18003d19e  mov     r8d, r14d
0x18003d1a1  call    SymCryptRsaPkcs1Verify
0x18003d1a6  jmp     loc_18003D252
0x18003d1ab  lea     r8, [rsp+98h+var_38]
0x18003d1b0  mov     edx, r14d
0x18003d1b3  mov     rcx, r12
0x18003d1b6  call    CheckAndGetPssHashAlgorithm
0x18003d1bb  mov     ebx, eax
0x18003d1bd  test    eax, eax
0x18003d1bf  jns     short loc_18003D20F
0x18003d1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d1c8  lea     rax, WPP_GLOBAL_Control
0x18003d1cf  cmp     rcx, rax
0x18003d1d2  jz      loc_18003D2D6
0x18003d1d8  test    byte ptr [rcx+1Ch], 1
0x18003d1dc  jz      loc_18003D2D6
0x18003d1e2  mov     rcx, [rcx+10h]
0x18003d1e6  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d1ed  mov     dword ptr [rsp+98h+var_68], 8E5h
0x18003d1f5  lea     r9, aStatus; "Status"
0x18003d1fc  mov     [rsp+98h+var_70], r8
0x18003d201  mov     [rsp+98h+var_78], ebx
0x18003d205  call    WPP_SF_sDsd
0x18003d20a  jmp     loc_18003D2D6
0x18003d20f  mov     eax, [r12+8]
0x18003d214  cmp     r14d, esi
0x18003d217  mov     ecx, [rsp+98h+arg_28]
0x18003d21e  mov     r9, [rsp+98h+arg_20]
0x18003d226  cmova   r14d, esi
0x18003d22a  mov     rdx, [rsp+98h+arg_10]
0x18003d232  mov     [rsp+98h+var_60], rax; __int64
0x18003d237  mov     rax, [rsp+98h+var_38]
0x18003d23c  mov     [rsp+98h+var_68], rax; __int64
0x18003d241  mov     qword ptr [rsp+98h+var_78], rcx; int
0x18003d246  mov     rcx, [r15+20h]; int
0x18003d24a  mov     r8d, r14d
0x18003d24d  call    SymCryptRsaPssVerify
0x18003d252  test    eax, eax
0x18003d254  jz      short loc_18003D2A2
0x18003d256  mov     ecx, eax
0x18003d258  call    SymcryptErrorCodeToNtStatus
0x18003d25d  mov     ebx, eax
0x18003d25f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003d266  lea     rax, WPP_GLOBAL_Control
0x18003d26d  cmp     rcx, rax
0x18003d270  jz      short loc_18003D2C9
0x18003d272  test    byte ptr [rcx+1Ch], 1
0x18003d276  jz      short loc_18003D2C9
0x18003d278  mov     rcx, [rcx+10h]
0x18003d27c  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d283  mov     dword ptr [rsp+98h+var_68], 8F8h
0x18003d28b  lea     r9, aStatus; "Status"
0x18003d292  mov     [rsp+98h+var_70], r8
0x18003d297  mov     [rsp+98h+var_78], ebx
0x18003d29b  call    WPP_SF_sDsd
0x18003d2a0  jmp     short loc_18003D2C9
0x18003d2a2  xor     ebx, ebx
0x18003d2a4  jmp     short loc_18003D2C9
0x18003d2a6  mov     r9d, 896h
0x18003d2ac  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003d2b3  lea     rdx, aStatus; "Status"
0x18003d2ba  mov     ecx, 0C000000Dh
0x18003d2bf  mov     ebx, 0C000000Dh
0x18003d2c4  call    DebugTraceError
0x18003d2c9  test    rdi, rdi
0x18003d2cc  jz      short loc_18003D2D6
0x18003d2ce  mov     rcx, rdi
0x18003d2d1  call    MSCryptFree
0x18003d2d6  lea     r11, [rsp+98h+var_28]
0x18003d2db  mov     eax, ebx
0x18003d2dd  mov     rbx, [r11+30h]
0x18003d2e1  mov     rbp, [r11+38h]
0x18003d2e5  mov     rsp, r11
0x18003d2e8  pop     r15
0x18003d2ea  pop     r14
0x18003d2ec  pop     r12
0x18003d2ee  pop     rdi
0x18003d2ef  pop     rsi
0x18003d2f0  retn
```
