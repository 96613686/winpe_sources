# GetBCryptProviderHandle

- ea: `0x18000bf2c`
- end: `0x18000c136`
- name: `GetBCryptProviderHandle`
- size: `522`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b67c`
- `0x18000bc3c`
- `0x18000c13c`

## callees

- `0x18000bd58`
- `0x18000bf2c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfcf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c016`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c11b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bfcf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c016`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c11b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bfa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c108`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000bfa5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf70`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bf70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c0bc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c0bc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c0a4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c0d0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c0a4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c0d0`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000c075`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000c075`

## pseudocode

```c
BCRYPT_ALG_HANDLE __fastcall GetBCryptProviderHandle(int a1, __int64 a2, ULONG a3)
{
  CLinkedList *v3; // rdi
  DWORD v6; // ecx
  bool v8; // zf
  _QWORD *i; // rbx
  const WCHAR *v10; // rdx
  NTSTATUS v11; // eax
  _QWORD *v12; // rax
  BCRYPT_ALG_HANDLE v13; // rcx
  _QWORD *v14; // rdi
  CLinkedList *v15; // rsi
  __int64 v16; // [rsp+20h] [rbp-20h] BYREF
  int v17; // [rsp+28h] [rbp-18h]
  int v18; // [rsp+2Ch] [rbp-14h]
  __int64 v19; // [rsp+30h] [rbp-10h]
  ULONG v20; // [rsp+38h] [rbp-8h]
  int v21; // [rsp+3Ch] [rbp-4h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+88h] [rbp+48h] BYREF

  v3 = g_pBCProvList;
  v21 = 0;
  phAlgorithm = 0;
  if ( !g_pBCProvList )
  {
    v6 = -2146697215;
LABEL_3:
    SetLastError(v6);
    return 0;
  }
  v8 = *((_DWORD *)g_pBCProvList + 2) == 0;
  v16 = 0;
  v17 = a1;
  v18 = -1;
  v19 = 0;
  v20 = a3;
  if ( v8 )
  {
LABEL_10:
    v10 = 0;
    switch ( a1 )
    {
      case 26113:
        v10 = L"DES";
        break;
      case 26115:
        v10 = L"3DES";
        break;
      case 26128:
        v10 = L"AES";
        break;
      case 26625:
        v10 = L"RC4";
        break;
      case 32770:
        v10 = L"MD4";
        break;
      case 32772:
        v10 = L"SHA1";
        break;
      case 32782:
        v10 = L"SHA512";
        break;
      case 41984:
        v10 = L"RSA";
        break;
    }
    v11 = BCryptOpenAlgorithmProvider(&phAlgorithm, v10, L"Microsoft Primitive Provider", a3);
    if ( v11 < 0 )
    {
      v6 = v11 | 0x10000000;
      goto LABEL_3;
    }
    if ( !(unsigned int)FBCryptProviderSupportsAlg(phAlgorithm) )
    {
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      v6 = 50;
      goto LABEL_3;
    }
    v12 = LocalAlloc(0x40u, 0x20u);
    v13 = phAlgorithm;
    v14 = v12;
    if ( !v12 )
    {
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
      v6 = 8;
      goto LABEL_3;
    }
    v15 = g_pBCProvList;
    *v12 = 0;
    *((_DWORD *)v12 + 2) = a1;
    *((_DWORD *)v12 + 3) = -1;
    v12[2] = v13;
    *((_DWORD *)v12 + 6) = a3;
    if ( *((_DWORD *)v15 + 2) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 16));
      *v14 = *(_QWORD *)v15;
      *(_QWORD *)v15 = v14;
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v15 + 16));
    }
    return phAlgorithm;
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pBCProvList + 16));
    for ( i = *(_QWORD **)v3; ; i = (_QWORD *)*i )
    {
      if ( !i )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 16));
        goto LABEL_10;
      }
      if ( (*((unsigned int (__fastcall **)(_QWORD *, __int64 *))v3 + 7))(i, &v16) )
        break;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 16));
    return (BCRYPT_ALG_HANDLE)i[2];
  }
}

```

## disassembly

```asm
0x18000bf2c  mov     [rsp-28h+arg_0], rbx
0x18000bf31  mov     [rsp-28h+arg_8], rdx
0x18000bf36  push    rbp
0x18000bf37  push    rsi
0x18000bf38  push    rdi
0x18000bf39  push    r14
0x18000bf3b  push    r15
0x18000bf3d  mov     rbp, rsp
0x18000bf40  sub     rsp, 40h
0x18000bf44  mov     rdi, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x18000bf4b  or      eax, 0FFFFFFFFh
0x18000bf4e  mov     [rbp+var_4], 0
0x18000bf55  mov     r15d, r8d
0x18000bf58  mov     [rbp+phAlgorithm], 0
0x18000bf60  mov     r14d, ecx
0x18000bf63  mov     dword ptr [rbp+arg_8], eax
0x18000bf66  test    rdi, rdi
0x18000bf69  jnz     short loc_18000BF7D
0x18000bf6b  mov     ecx, 800C0001h; dwErrCode
0x18000bf70  call    cs:__imp_SetLastError
0x18000bf76  xor     eax, eax
0x18000bf78  jmp     loc_18000C125
0x18000bf7d  cmp     dword ptr [rdi+8], 0
0x18000bf81  mov     [rbp+var_20], 0
0x18000bf89  mov     [rbp+var_18], r14d
0x18000bf8d  mov     [rbp+var_14], eax
0x18000bf90  mov     [rbp+var_10], 0
0x18000bf98  mov     [rbp+var_8], r15d
0x18000bf9c  jz      short loc_18000BFD5
0x18000bf9e  lea     rsi, [rdi+10h]
0x18000bfa2  mov     rcx, rsi; lpCriticalSection
0x18000bfa5  call    cs:__imp_EnterCriticalSection
0x18000bfab  mov     rbx, [rdi]
0x18000bfae  jmp     short loc_18000BFC7
0x18000bfb0  mov     rax, [rdi+38h]
0x18000bfb4  lea     rdx, [rbp+var_20]
0x18000bfb8  mov     rcx, rbx
0x18000bfbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc0  test    eax, eax
0x18000bfc2  jnz     short loc_18000C013
0x18000bfc4  mov     rbx, [rbx]
0x18000bfc7  test    rbx, rbx
0x18000bfca  jnz     short loc_18000BFB0
0x18000bfcc  mov     rcx, rsi; lpCriticalSection
0x18000bfcf  call    cs:__imp_LeaveCriticalSection
0x18000bfd5  xor     edx, edx
0x18000bfd7  mov     eax, r14d
0x18000bfda  sub     eax, 6601h
0x18000bfdf  jz      short loc_18000C060
0x18000bfe1  sub     eax, 2
0x18000bfe4  jz      short loc_18000C057
0x18000bfe6  sub     eax, 0Dh
0x18000bfe9  jz      short loc_18000C04E
0x18000bfeb  sub     eax, 1F1h
0x18000bff0  jz      short loc_18000C045
0x18000bff2  sub     eax, 1801h
0x18000bff7  jz      short loc_18000C03C
0x18000bff9  sub     eax, 2
0x18000bffc  jz      short loc_18000C033
0x18000bffe  sub     eax, 0Ah
0x18000c001  jz      short loc_18000C02A
0x18000c003  cmp     eax, 23F2h
0x18000c008  jnz     short loc_18000C067
0x18000c00a  lea     rdx, aRsa; "RSA"
0x18000c011  jmp     short loc_18000C067
0x18000c013  mov     rcx, rsi; lpCriticalSection
0x18000c016  call    cs:__imp_LeaveCriticalSection
0x18000c01c  test    rbx, rbx
0x18000c01f  jz      short loc_18000BFD5
0x18000c021  mov     rax, [rbx+10h]
0x18000c025  jmp     loc_18000C125
0x18000c02a  lea     rdx, aSha512; "SHA512"
0x18000c031  jmp     short loc_18000C067
0x18000c033  lea     rdx, aSha1; "SHA1"
0x18000c03a  jmp     short loc_18000C067
0x18000c03c  lea     rdx, aMd4; "MD4"
0x18000c043  jmp     short loc_18000C067
0x18000c045  lea     rdx, aRc4; "RC4"
0x18000c04c  jmp     short loc_18000C067
0x18000c04e  lea     rdx, aAes; "AES"
0x18000c055  jmp     short loc_18000C067
0x18000c057  lea     rdx, a3des; "3DES"
0x18000c05e  jmp     short loc_18000C067
0x18000c060  lea     rdx, aDes; "DES"
0x18000c067  mov     r9d, r15d; dwFlags
0x18000c06a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000c071  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18000c075  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000c07b  test    eax, eax
0x18000c07d  jns     short loc_18000C08A
0x18000c07f  bts     eax, 1Ch
0x18000c083  mov     ecx, eax
0x18000c085  jmp     loc_18000BF70
0x18000c08a  mov     rcx, [rbp+phAlgorithm]; hObject
0x18000c08e  lea     r8, [rbp+arg_8]
0x18000c092  mov     edx, r14d
0x18000c095  call    FBCryptProviderSupportsAlg
0x18000c09a  test    eax, eax
0x18000c09c  jnz     short loc_18000C0B4
0x18000c09e  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000c0a2  xor     edx, edx; dwFlags
0x18000c0a4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000c0aa  mov     ecx, 32h ; '2'
0x18000c0af  jmp     loc_18000BF70
0x18000c0b4  mov     edx, 20h ; ' '; uBytes
0x18000c0b9  lea     ecx, [rdx+20h]; uFlags
0x18000c0bc  call    cs:__imp_LocalAlloc
0x18000c0c2  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000c0c6  mov     rdi, rax
0x18000c0c9  test    rax, rax
0x18000c0cc  jnz     short loc_18000C0DE
0x18000c0ce  xor     edx, edx; dwFlags
0x18000c0d0  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000c0d6  lea     ecx, [rdi+8]
0x18000c0d9  jmp     loc_18000BF70
0x18000c0de  mov     rsi, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x18000c0e5  mov     qword ptr [rax], 0
0x18000c0ec  mov     [rax+8], r14d
0x18000c0f0  mov     eax, dword ptr [rbp+arg_8]
0x18000c0f3  mov     [rdi+0Ch], eax
0x18000c0f6  mov     [rdi+10h], rcx
0x18000c0fa  mov     [rdi+18h], r15d
0x18000c0fe  cmp     dword ptr [rsi+8], 0
0x18000c102  jz      short loc_18000C121
0x18000c104  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000c108  call    cs:__imp_EnterCriticalSection
0x18000c10e  mov     rax, [rsi]
0x18000c111  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000c115  mov     [rdi], rax
0x18000c118  mov     [rsi], rdi
0x18000c11b  call    cs:__imp_LeaveCriticalSection
0x18000c121  mov     rax, [rbp+phAlgorithm]
0x18000c125  mov     rbx, [rsp+40h+arg_0]
0x18000c12a  add     rsp, 40h
0x18000c12e  pop     r15
0x18000c130  pop     r14
0x18000c132  pop     rdi
0x18000c133  pop     rsi
0x18000c134  pop     rbp
0x18000c135  retn
```
