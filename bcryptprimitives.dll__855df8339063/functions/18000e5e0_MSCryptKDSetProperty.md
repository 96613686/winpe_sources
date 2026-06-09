# MSCryptKDSetProperty

- ea: `0x18000e5e0`
- end: `0x18000eca8`
- name: `MSCryptKDSetProperty`
- size: `1736`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000e5e0`
- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x1800593e0`
- `0x180063170`
- `0x180063180`
- `0x18007f765`
- `0x18007f790`
- `0x180083010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000e7cc`
- `ntdll!RtlAllocateHeap` at `0x18000e7cc`

## string_xrefs

- `0x18000e69f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000e991`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000e9d2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000ea46`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000ea8d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000ead1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000eb28`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000eb86`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000ebe1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x18000ec2c`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDSetProperty(__int64 a1, const wchar_t *a2, const wchar_t *a3, unsigned int a4, int a5)
{
  SIZE_T v6; // rbp
  int v9; // edx
  int v10; // r8d
  int v11; // r14d
  __int64 v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v17; // edx
  int v18; // r8d
  int v19; // edx
  int v20; // r8d
  unsigned int (__fastcall **v21)(__int64, __int64, __int64); // rax
  __int64 v22; // r8
  __int64 v23; // rdx
  int v24; // edx
  int v25; // r8d
  __int64 (__fastcall **v26)(); // rax
  PVOID Heap; // rax
  int v28; // edx
  int v29; // r8d
  __int64 v30; // r14
  size_t v31; // rsi
  unsigned int v32; // r15d
  __int64 v33; // r12
  unsigned int (__fastcall **v34)(__int64, _QWORD *, size_t); // rax
  __int64 v35; // rax
  int v36; // edx
  int v37; // r8d
  int v38; // edx
  int v39; // r8d
  _BYTE v40[4]; // [rsp+40h] [rbp-3B8h] BYREF
  int v41; // [rsp+44h] [rbp-3B4h]
  _BYTE v42[544]; // [rsp+150h] [rbp-2A8h] BYREF
  _QWORD Src[8]; // [rsp+370h] [rbp-88h] BYREF

  v6 = a4;
  memset_0(Src, 0, sizeof(Src));
  if ( !a1 )
  {
    v14 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        v10,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        98);
    return v14;
  }
  if ( a5 || !a2 )
  {
    v13 = 1130;
    goto LABEL_12;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        v10,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        84);
    v14 = -1073741816;
    v13 = 1138;
    v15 = 3221225480LL;
    goto LABEL_13;
  }
  v11 = 0;
  if ( wcscmp_0(a2, L"HkdfHashAlgorithm") )
  {
    if ( !wcscmp_0(a2, L"HkdfSaltAndFinalize") )
    {
      if ( *(_DWORD *)(a1 + 48) == 1 || (v30 = *(_QWORD *)(a1 + 72)) == 0 )
      {
        v14 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            v18,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            181);
        return v14;
      }
      v31 = *(_QWORD *)(v30 + 48);
      v41 = 0;
      memset_0(v40, 0, 0x10Cu);
      memset_0(v42, 0, sizeof(v42));
      v32 = *(_DWORD *)(a1 + 16);
      v33 = *(_QWORD *)(a1 + 24);
      if ( (*(unsigned int (__fastcall **)(_BYTE *, const wchar_t *, SIZE_T))v30)(v42, a3, v6) )
      {
        v14 = 0;
        SymCryptWipeAsm(v42, 544);
        return v14;
      }
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(v30 + 8))(v40, v42);
      (*(void (__fastcall **)(_BYTE *, __int64, _QWORD))(v30 + 16))(v40, v33, v32);
      (*(void (__fastcall **)(_BYTE *, _QWORD *))(v30 + 24))(v40, Src);
      SymCryptWipeAsm(v42, 544);
      v34 = *(unsigned int (__fastcall ***)(__int64, _QWORD *, size_t))(a1 + 72);
      *(_QWORD *)(a1 + 624) = v34;
      v11 = 1;
      if ( !(*v34)(a1 + 80, Src, v31) )
      {
        if ( *(unsigned int *)(a1 + 16) < v31 )
        {
          MSCryptFree(*(_QWORD *)(a1 + 24));
          v35 = SafeAllocaAllocateFromHeap(v31);
          *(_QWORD *)(a1 + 24) = v35;
          if ( !v35 )
          {
            v14 = -1073741801;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v36,
                v37,
                (unsigned int)"Status",
                23,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
                217);
            goto LABEL_30;
          }
        }
        memcpy_0(*(void **)(a1 + 24), Src, v31);
        *(_DWORD *)(a1 + 16) = v31;
        *(_DWORD *)(a1 + 48) = 1;
      }
    }
    else
    {
      if ( wcscmp_0(a2, L"HkdfPrkAndFinalize") )
      {
        v14 = -1073741637;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            v20,
            (unsigned int)"Status",
            187,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            22);
        return v14;
      }
      if ( *(_DWORD *)(a1 + 48) == 1
        || (v21 = *(unsigned int (__fastcall ***)(__int64, __int64, __int64))(a1 + 72)) == 0
        || a3
        || (_DWORD)v6 )
      {
        v14 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v19,
            v20,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            251);
        return v14;
      }
      v22 = *(unsigned int *)(a1 + 16);
      v23 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 624) = v21;
      if ( (*v21)(a1 + 80, v23, v22) )
      {
        v14 = -1073741823;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v24,
            v25,
            (unsigned int)"Status",
            1,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            10);
        return v14;
      }
      *(_DWORD *)(a1 + 48) = 1;
    }
    goto LABEL_29;
  }
  if ( *(_DWORD *)(a1 + 48) == 1 )
  {
    v13 = 1150;
    goto LABEL_12;
  }
  if ( (unsigned int)v6 < 2 )
  {
LABEL_11:
    v13 = 1159;
LABEL_12:
    v14 = -1073741811;
    v15 = 3221225485LL;
LABEL_13:
    DebugTraceError(
      v15,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      v13);
    return v14;
  }
  LODWORD(v12) = (unsigned int)v6 >> 1;
  while ( 1 )
  {
    v12 = (unsigned int)(v12 - 1);
    if ( !a3[v12] )
      break;
    if ( !(_DWORD)v12 )
      goto LABEL_11;
  }
  if ( !wcscmp_0(a3, L"SHA1") )
  {
    v26 = (__int64 (__fastcall **)())&SymCryptHmacSha1Algorithm_default;
  }
  else if ( !wcscmp_0(a3, L"SHA256") )
  {
    v26 = (__int64 (__fastcall **)())&SymCryptHmacSha256Algorithm_default;
  }
  else if ( !wcscmp_0(a3, L"SHA384") )
  {
    v26 = (__int64 (__fastcall **)())&SymCryptHmacSha384Algorithm_default;
  }
  else if ( !wcscmp_0(a3, L"SHA512") )
  {
    v26 = (__int64 (__fastcall **)())&SymCryptHmacSha512Algorithm_default;
  }
  else if ( !wcscmp_0(a3, L"AES-CMAC") )
  {
    v26 = SymCryptAesCmacAlgorithm_fast;
  }
  else if ( !wcscmp_0(a3, L"SHA3-256") )
  {
    v26 = SymCryptHmacSha3_256Algorithm_default;
  }
  else if ( !wcscmp_0(a3, L"SHA3-384") )
  {
    v26 = SymCryptHmacSha3_384Algorithm_default;
  }
  else
  {
    if ( wcscmp_0(a3, L"SHA3-512") )
    {
      *(_QWORD *)(a1 + 72) = 0;
      v14 = -1073741637;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v38,
          v39,
          (unsigned int)"Status",
          187,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          147);
      return v14;
    }
    v26 = SymCryptHmacSha3_512Algorithm_default;
  }
  *(_QWORD *)(a1 + 72) = v26;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  *(_QWORD *)(a1 + 56) = Heap;
  if ( !Heap )
  {
    v14 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v29,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        155);
    return v14;
  }
  memcpy_0(Heap, a3, v6);
  *(_DWORD *)(a1 + 64) = v6;
LABEL_29:
  v14 = 0;
  if ( v11 )
LABEL_30:
    memset(Src, 0, sizeof(Src));
  return v14;
}

```

## disassembly

```asm
0x18000e5e0  mov     [rsp+arg_8], rbx
0x18000e5e5  push    rbp
0x18000e5e6  push    rsi
0x18000e5e7  push    rdi
0x18000e5e8  push    r12
0x18000e5ea  push    r13
0x18000e5ec  push    r14
0x18000e5ee  push    r15
0x18000e5f0  sub     rsp, 3C0h
0x18000e5f7  mov     rax, cs:__security_cookie
0x18000e5fe  xor     rax, rsp
0x18000e601  mov     [rsp+3F8h+var_48], rax
0x18000e609  mov     rdi, r8
0x18000e60c  mov     ebp, r9d
0x18000e60f  mov     rsi, rdx
0x18000e612  mov     rbx, rcx
0x18000e615  xor     edx, edx; Val
0x18000e617  lea     rcx, [rsp+3F8h+Src]; void *
0x18000e61f  mov     r8d, 40h ; '@'; Size
0x18000e625  call    memset_0
0x18000e62a  test    rbx, rbx
0x18000e62d  jz      loc_18000EAA3
0x18000e633  cmp     [rsp+3F8h+arg_20], 0
0x18000e63b  jnz     loc_18000EC9D
0x18000e641  test    rsi, rsi
0x18000e644  jz      loc_18000EC9D
0x18000e64a  cmp     dword ptr [rbx+4], 4D534B59h
0x18000e651  jnz     loc_18000E9C4
0x18000e657  xor     r13d, r13d
0x18000e65a  mov     r14d, r13d
0x18000e65d  lea     rdx, aHkdfhashalgori; "HkdfHashAlgorithm"
0x18000e664  mov     rcx, rsi; String1
0x18000e667  call    wcscmp_0
0x18000e66c  test    eax, eax
0x18000e66e  jnz     short loc_18000E6E5
0x18000e670  cmp     dword ptr [rbx+30h], 1
0x18000e674  jz      loc_18000EC6F
0x18000e67a  cmp     ebp, 2
0x18000e67d  jb      short loc_18000E694
0x18000e67f  mov     ecx, ebp
0x18000e681  shr     ecx, 1
0x18000e683  dec     ecx
0x18000e685  cmp     [rdi+rcx*2], r13w
0x18000e68a  jz      loc_18000E76A
0x18000e690  test    ecx, ecx
0x18000e692  jnz     short loc_18000E683
0x18000e694  mov     r9d, 487h
0x18000e69a  mov     ebx, 0C000000Dh
0x18000e69f  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e6a6  mov     ecx, 0C000000Dh
0x18000e6ab  lea     rdx, aStatus; "Status"
0x18000e6b2  call    DebugTraceError
0x18000e6b7  mov     eax, ebx
0x18000e6b9  mov     rcx, [rsp+3F8h+var_48]
0x18000e6c1  xor     rcx, rsp; StackCookie
0x18000e6c4  call    __security_check_cookie
0x18000e6c9  mov     rbx, [rsp+3F8h+arg_8]
0x18000e6d1  add     rsp, 3C0h
0x18000e6d8  pop     r15
0x18000e6da  pop     r14
0x18000e6dc  pop     r13
0x18000e6de  pop     r12
0x18000e6e0  pop     rdi
0x18000e6e1  pop     rsi
0x18000e6e2  pop     rbp
0x18000e6e3  retn
0x18000e6e5  lea     rdx, aHkdfsaltandfin; "HkdfSaltAndFinalize"
0x18000e6ec  mov     rcx, rsi; String1
0x18000e6ef  call    wcscmp_0
0x18000e6f4  test    eax, eax
0x18000e6f6  jz      loc_18000E847
0x18000e6fc  lea     rdx, aHkdfprkandfina; "HkdfPrkAndFinalize"
0x18000e703  mov     rcx, rsi; String1
0x18000e706  call    wcscmp_0
0x18000e70b  test    eax, eax
0x18000e70d  jnz     loc_18000EBB3
0x18000e713  cmp     dword ptr [rbx+30h], 1
0x18000e717  jz      loc_18000EAFA
0x18000e71d  mov     rax, [rbx+48h]
0x18000e721  test    rax, rax
0x18000e724  jz      loc_18000EAFA
0x18000e72a  test    rdi, rdi
0x18000e72d  jnz     loc_18000EAFA
0x18000e733  test    ebp, ebp
0x18000e735  jnz     loc_18000EAFA
0x18000e73b  mov     r8d, [rbx+10h]
0x18000e73f  lea     rcx, [rbx+50h]
0x18000e743  mov     rdx, [rbx+18h]
0x18000e747  mov     [rcx+220h], rax
0x18000e74e  mov     rax, [rax]
0x18000e751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e756  test    eax, eax
0x18000e758  jnz     loc_18000EA5F
0x18000e75e  mov     dword ptr [rbx+30h], 1
0x18000e765  jmp     loc_18000E7F6
0x18000e76a  lea     rdx, aSha1; "SHA1"
0x18000e771  mov     rcx, rdi; String1
0x18000e774  call    wcscmp_0
0x18000e779  test    eax, eax
0x18000e77b  jz      loc_18000EA00
0x18000e781  lea     rdx, aSha256; "SHA256"
0x18000e788  mov     rcx, rdi; String1
0x18000e78b  call    wcscmp_0
0x18000e790  test    eax, eax
0x18000e792  jz      loc_18000EA0C
0x18000e798  lea     rdx, aSha384; "SHA384"
0x18000e79f  mov     rcx, rdi; String1
0x18000e7a2  call    wcscmp_0
0x18000e7a7  test    eax, eax
0x18000e7a9  jnz     loc_18000EC7A
0x18000e7af  lea     rax, SymCryptHmacSha384Algorithm_default
0x18000e7b6  mov     [rbx+48h], rax
0x18000e7ba  mov     r8, rbp; Size
0x18000e7bd  mov     rcx, gs:60h
0x18000e7c6  xor     edx, edx; Flags
0x18000e7c8  mov     rcx, [rcx+30h]; HeapHandle
0x18000e7cc  call    cs:__imp_RtlAllocateHeap
0x18000e7d3  nop     dword ptr [rax+rax+00h]
0x18000e7d8  mov     [rbx+38h], rax
0x18000e7dc  test    rax, rax
0x18000e7df  jz      loc_18000EA18
0x18000e7e5  mov     r8, rbp; Size
0x18000e7e8  mov     rdx, rdi; Src
0x18000e7eb  mov     rcx, rax; void *
0x18000e7ee  call    memcpy_0
0x18000e7f3  mov     [rbx+40h], ebp
0x18000e7f6  mov     ebx, r13d
0x18000e7f9  test    r14d, r14d
0x18000e7fc  jz      loc_18000E6B7
0x18000e802  mov     [rsp+3F8h+Src], r13
0x18000e80a  mov     [rsp+3F8h+var_80], r13
0x18000e812  mov     [rsp+3F8h+var_78], r13
0x18000e81a  mov     [rsp+3F8h+var_70], r13
0x18000e822  mov     [rsp+3F8h+var_68], r13
0x18000e82a  mov     [rsp+3F8h+var_60], r13
0x18000e832  mov     [rsp+3F8h+var_58], r13
0x18000e83a  mov     [rsp+3F8h+var_50], r13
0x18000e842  jmp     loc_18000E6B7
0x18000e847  cmp     dword ptr [rbx+30h], 1
0x18000e84b  jz      loc_18000E963
0x18000e851  mov     r14, [rbx+48h]
0x18000e855  test    r14, r14
0x18000e858  jz      loc_18000E963
0x18000e85e  mov     rsi, [r14+30h]
0x18000e862  lea     rcx, [rsp+3F8h+var_3B8]; void *
0x18000e867  xor     eax, eax
0x18000e869  xor     edx, edx; Val
0x18000e86b  mov     r8d, 10Ch; Size
0x18000e871  mov     [rsp+3F8h+var_3B4], eax
0x18000e875  call    memset_0
0x18000e87a  xor     edx, edx; Val
0x18000e87c  lea     rcx, [rsp+3F8h+var_2A8]; void *
0x18000e884  mov     r8d, 220h; Size
0x18000e88a  call    memset_0
0x18000e88f  mov     rax, [r14]
0x18000e892  lea     rcx, [rsp+3F8h+var_2A8]
0x18000e89a  mov     r15d, [rbx+10h]
0x18000e89e  mov     r8, rbp
0x18000e8a1  mov     r12, [rbx+18h]
0x18000e8a5  mov     rdx, rdi
0x18000e8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8ad  test    eax, eax
0x18000e8af  jnz     loc_18000E9AA
0x18000e8b5  mov     rax, [r14+8]
0x18000e8b9  lea     rdx, [rsp+3F8h+var_2A8]
0x18000e8c1  lea     rcx, [rsp+3F8h+var_3B8]
0x18000e8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8cb  mov     rax, [r14+10h]
0x18000e8cf  lea     rcx, [rsp+3F8h+var_3B8]
0x18000e8d4  mov     r8d, r15d
0x18000e8d7  mov     rdx, r12
0x18000e8da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8df  mov     rax, [r14+18h]
0x18000e8e3  lea     rdx, [rsp+3F8h+Src]
0x18000e8eb  lea     rcx, [rsp+3F8h+var_3B8]
0x18000e8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f5  mov     edx, 220h
0x18000e8fa  lea     rcx, [rsp+3F8h+var_2A8]
0x18000e902  call    SymCryptWipeAsm
0x18000e907  mov     rax, [rbx+48h]
0x18000e90b  lea     rcx, [rbx+50h]
0x18000e90f  mov     [rcx+220h], rax
0x18000e916  lea     rdx, [rsp+3F8h+Src]
0x18000e91e  mov     r8, rsi
0x18000e921  mov     r14d, 1
0x18000e927  mov     rax, [rax]
0x18000e92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e92f  test    eax, eax
0x18000e931  jnz     loc_18000E7F6
0x18000e937  mov     eax, [rbx+10h]
0x18000e93a  cmp     rax, rsi
0x18000e93d  jb      loc_18000EB3E
0x18000e943  mov     rcx, [rbx+18h]; void *
0x18000e947  lea     rdx, [rsp+3F8h+Src]; Src
0x18000e94f  mov     r8, rsi; Size
0x18000e952  call    memcpy_0
0x18000e957  mov     [rbx+10h], esi
0x18000e95a  mov     [rbx+30h], r14d
0x18000e95e  jmp     loc_18000E7F6
0x18000e963  mov     ebx, 0C000000Dh
0x18000e968  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e96f  lea     rax, WPP_GLOBAL_Control
0x18000e976  cmp     rcx, rax
0x18000e979  jz      loc_18000E6B7
0x18000e97f  test    byte ptr [rcx+1Ch], 1
0x18000e983  jz      loc_18000E6B7
0x18000e989  mov     [rsp+3F8h+var_3C8], 4B5h
0x18000e991  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e998  mov     [rsp+3F8h+var_3D0], rdi
0x18000e99d  mov     [rsp+3F8h+var_3D8], 0C000000Dh
0x18000e9a5  jmp     loc_18000EAE5
0x18000e9aa  mov     edx, 220h
0x18000e9af  lea     rcx, [rsp+3F8h+var_2A8]
0x18000e9b7  mov     ebx, r13d
0x18000e9ba  call    SymCryptWipeAsm
0x18000e9bf  jmp     loc_18000E6B7
0x18000e9c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9cb  lea     rax, WPP_GLOBAL_Control
0x18000e9d2  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000e9d9  cmp     rcx, rax
0x18000e9dc  jz      short loc_18000E9E8
0x18000e9de  test    byte ptr [rcx+1Ch], 1
0x18000e9e2  jnz     loc_18000EC45
0x18000e9e8  mov     ebx, 0C0000008h
0x18000e9ed  mov     r9d, 472h
0x18000e9f3  mov     r8, rdi
0x18000e9f6  mov     ecx, 0C0000008h
0x18000e9fb  jmp     loc_18000E6AB
0x18000ea00  lea     rax, SymCryptHmacSha1Algorithm_default
0x18000ea07  jmp     loc_18000E7B6
0x18000ea0c  lea     rax, SymCryptHmacSha256Algorithm_default
0x18000ea13  jmp     loc_18000E7B6
0x18000ea18  mov     ebx, 0C0000017h
0x18000ea1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea24  lea     rax, WPP_GLOBAL_Control
0x18000ea2b  cmp     rcx, rax
0x18000ea2e  jz      loc_18000E6B7
0x18000ea34  test    byte ptr [rcx+1Ch], 1
0x18000ea38  jz      loc_18000E6B7
0x18000ea3e  mov     [rsp+3F8h+var_3C8], 49Bh
0x18000ea46  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ea4d  mov     [rsp+3F8h+var_3D0], rdi
0x18000ea52  mov     [rsp+3F8h+var_3D8], 0C0000017h
0x18000ea5a  jmp     loc_18000EAE5
0x18000ea5f  mov     ebx, 0C0000001h
0x18000ea64  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea6b  lea     rax, WPP_GLOBAL_Control
0x18000ea72  cmp     rcx, rax
0x18000ea75  jz      loc_18000E6B7
0x18000ea7b  test    byte ptr [rcx+1Ch], 1
0x18000ea7f  jz      loc_18000E6B7
0x18000ea85  mov     [rsp+3F8h+var_3C8], 50Ah
0x18000ea8d  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ea94  mov     [rsp+3F8h+var_3D0], rdi
0x18000ea99  mov     [rsp+3F8h+var_3D8], 0C0000001h
0x18000eaa1  jmp     short loc_18000EAE5
0x18000eaa3  mov     ebx, 0C0000008h
0x18000eaa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eaaf  lea     rax, WPP_GLOBAL_Control
0x18000eab6  cmp     rcx, rax
0x18000eab9  jz      loc_18000E6B7
0x18000eabf  test    byte ptr [rcx+1Ch], 1
0x18000eac3  jz      loc_18000E6B7
0x18000eac9  mov     [rsp+3F8h+var_3C8], 462h
0x18000ead1  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ead8  mov     [rsp+3F8h+var_3D0], rdi
0x18000eadd  mov     [rsp+3F8h+var_3D8], 0C0000008h
0x18000eae5  mov     rcx, [rcx+10h]
0x18000eae9  lea     r9, aStatus; "Status"
0x18000eaf0  call    WPP_SF_sDsd
0x18000eaf5  jmp     loc_18000E6B7
0x18000eafa  mov     ebx, 0C000000Dh
0x18000eaff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb06  lea     rax, WPP_GLOBAL_Control
0x18000eb0d  cmp     rcx, rax
0x18000eb10  jz      loc_18000E6B7
0x18000eb16  test    byte ptr [rcx+1Ch], 1
0x18000eb1a  jz      loc_18000E6B7
0x18000eb20  mov     [rsp+3F8h+var_3C8], 4FBh
0x18000eb28  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eb2f  mov     [rsp+3F8h+var_3D0], rdi
0x18000eb34  mov     [rsp+3F8h+var_3D8], 0C000000Dh
0x18000eb3c  jmp     short loc_18000EAE5
0x18000eb3e  mov     rcx, [rbx+18h]
0x18000eb42  call    MSCryptFree
0x18000eb47  mov     rcx, rsi
0x18000eb4a  call    SafeAllocaAllocateFromHeap
0x18000eb4f  mov     [rbx+18h], rax
0x18000eb53  test    rax, rax
0x18000eb56  jnz     loc_18000E943
0x18000eb5c  mov     ebx, 0C0000017h
0x18000eb61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb68  lea     rax, WPP_GLOBAL_Control
0x18000eb6f  cmp     rcx, rax
0x18000eb72  jz      loc_18000E802
0x18000eb78  test    [rcx+1Ch], r14b
0x18000eb7c  jz      loc_18000E802
0x18000eb82  mov     rcx, [rcx+10h]
0x18000eb86  lea     rdi, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000eb8d  mov     [rsp+3F8h+var_3C8], 4D9h
  ... truncated ...
```
