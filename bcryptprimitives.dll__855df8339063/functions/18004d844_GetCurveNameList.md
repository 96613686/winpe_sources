# GetCurveNameList

- ea: `0x18004d844`
- end: `0x18004dc6f`
- name: `GetCurveNameList`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004490c`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x18002bf08`
- `0x18004d844`
- `0x18004dc78`
- `0x180063180`
- `0x18007f790`

## import_xrefs

- `ntdll!_wcsicmp` at `0x180082935`
- `ntdll!_wcsicmp` at `0x180082935`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d97b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004d97b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d904`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004d904`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004d9cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004d9cb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004dc4c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800829cb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004dc4c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800829cb`

## string_xrefs

- `0x18004da2e`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004db25`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x18004db6d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180082903`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall GetCurveNameList(__int64 a1, unsigned int a2, unsigned int *a3)
{
  unsigned int v3; // edi
  __int64 v5; // rcx
  unsigned int v8; // r15d
  _BYTE *v9; // r14
  char v10; // al
  __int64 j; // rdx
  wchar_t *v12; // r8
  __int64 v13; // rax
  unsigned int v14; // ebx
  LSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  LSTATUS v19; // eax
  size_t v20; // rbx
  _BYTE *v21; // rax
  int v22; // edx
  int v23; // r8d
  unsigned int v24; // esi
  wchar_t *v25; // rdi
  unsigned int k; // r11d
  wchar_t *v27; // rcx
  __int64 v28; // rax
  int v29; // edx
  int v30; // r8d
  DWORD i; // ebx
  DWORD m; // ebx
  __int64 v33; // r9
  __int64 v34; // rcx
  const wchar_t *v35; // rcx
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  v3 = 0;
  *a3 = 16;
  hKey = 0;
  v5 = (unsigned int)g_TrustedEnvironment;
  cchName = 0;
  cSubKeys = 0;
  v8 = 0;
  v9 = 0;
  if ( g_TrustedEnvironment )
  {
    v10 = g_TrustedEnvironment;
  }
  else
  {
    v10 = ((__int64 (*)(void))GetTrustedEnvironment)();
    v5 = (unsigned int)g_TrustedEnvironment;
  }
  if ( (v10 & 1) == 0 )
    goto LABEL_4;
  v16 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\ECCParameters",
          0,
          0x20019u,
          &hKey);
  v14 = v16;
  if ( v16 )
  {
    if ( v16 > 0 )
      v14 = (unsigned __int16)v16 | 0xC0070000;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v18,
        (unsigned int)"Status",
        v14,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        115);
  }
  else
  {
    v19 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v14 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v14 = (unsigned __int16)v19 | 0xC0070000;
      v33 = 1403;
      v34 = v14;
      goto LABEL_59;
    }
    v20 = (unsigned __int64)(cSubKeys + 7) >> 3;
    v21 = (_BYTE *)SafeAllocaAllocateFromHeap(v20);
    v9 = v21;
    if ( v21 )
    {
      memset_0(v21, 0, v20);
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = 255;
        if ( !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        {
          while ( 1 )
          {
            if ( v3 >= 0x2D )
              goto LABEL_64;
            v35 = (&off_1800860D0)[3 * v3];
            if ( v35 )
            {
              if ( !_wcsicmp(v35, Name) )
                break;
            }
            ++v3;
          }
          v9[(unsigned __int64)i >> 3] |= 1 << (i & 7);
LABEL_64:
          if ( ((unsigned __int8)(1 << (i & 7)) & v9[(unsigned __int64)i >> 3]) == 0 )
          {
            ++v8;
            *a3 += 2 * cchName + 10;
          }
          v3 = 0;
        }
      }
      v5 = (unsigned int)g_TrustedEnvironment;
LABEL_4:
      for ( j = 0; j != 45; ++j )
      {
        v12 = (&off_1800860D0)[3 * j];
        if ( v12 )
        {
          v13 = -1;
          do
            ++v13;
          while ( v12[v13] );
          cchName = v13;
          ++v8;
          *a3 += 2 * v13 + 10;
        }
      }
      if ( !a1 )
      {
        v14 = 0;
        goto LABEL_12;
      }
      if ( a2 < *a3 )
      {
        v14 = -1073741789;
        goto LABEL_12;
      }
      v24 = 0;
      *(_DWORD *)a1 = v8;
      *(_QWORD *)(a1 + 8) = a1 + 16;
      v25 = (wchar_t *)(a1 + 8 * (v8 + 2LL));
      if ( !(_DWORD)v5 )
        LOBYTE(v5) = GetTrustedEnvironment(v5, 45, v12, &off_1800860D0);
      if ( (v5 & 1) == 0 )
      {
LABEL_28:
        for ( k = 0; ; ++k )
        {
          if ( k >= 0x2D )
          {
            v14 = 0;
            goto LABEL_12;
          }
          v27 = (&off_1800860D0)[3 * k];
          if ( v27 )
          {
            v28 = -1;
            do
              ++v28;
            while ( v27[v28] );
            cchName = v28;
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * v24) = v25;
            if ( StringCchCopyW(v25, cchName + 1, (&off_1800860D0)[3 * k]) < 0 )
            {
              v14 = -1073741595;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  v29,
                  v30,
                  (unsigned int)"Status",
                  229,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
                  14);
              }
              goto LABEL_12;
            }
            ++v24;
            v25 += cchName + 1;
          }
        }
      }
      for ( m = 0; ; ++m )
      {
        if ( m >= cSubKeys )
          goto LABEL_28;
        if ( ((unsigned __int8)(1 << (m & 7)) & v9[(unsigned __int64)m >> 3]) == 0 )
        {
          cchName = 255;
          if ( !RegEnumKeyExW(hKey, m, Name, &cchName, 0, 0, 0, 0) )
          {
            *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * v24) = v25;
            if ( StringCchCopyW(v25, cchName + 1, Name) < 0 )
            {
              v14 = -1073741595;
              v33 = 1524;
              v34 = 3221225701LL;
LABEL_59:
              DebugTraceError(v34, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v33);
              goto LABEL_12;
            }
            ++v24;
            v25 += cchName + 1;
          }
        }
      }
    }
    v14 = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        v23,
        (unsigned int)"Status",
        23,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        132);
  }
LABEL_12:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    MSCryptFree(v9);
  return v14;
}

```

## disassembly

```asm
0x18004d844  mov     [rsp-8+arg_8], rbx
0x18004d849  push    rbp
0x18004d84a  push    rsi
0x18004d84b  push    rdi
0x18004d84c  push    r12
0x18004d84e  push    r13
0x18004d850  push    r14
0x18004d852  push    r15
0x18004d854  lea     rbp, [rsp-180h]
0x18004d85c  sub     rsp, 280h
0x18004d863  mov     rax, cs:__security_cookie
0x18004d86a  xor     rax, rsp
0x18004d86d  mov     [rbp+1B0h+var_40], rax
0x18004d874  xor     edi, edi
0x18004d876  mov     dword ptr [r8], 10h
0x18004d87d  mov     r12, rcx
0x18004d880  mov     [rsp+2B0h+hKey], rdi
0x18004d885  mov     ecx, cs:g_TrustedEnvironment
0x18004d88b  mov     rsi, r8
0x18004d88e  mov     [rsp+2B0h+cchName], edi
0x18004d892  mov     r13d, edx
0x18004d895  mov     [rsp+2B0h+cSubKeys], edi
0x18004d899  mov     r15d, edi
0x18004d89c  mov     r14d, edi
0x18004d89f  test    ecx, ecx
0x18004d8a1  jz      loc_18004D94A
0x18004d8a7  mov     eax, ecx
0x18004d8a9  lea     r9, off_1800860D0; "brainpoolP160r1"
0x18004d8b0  test    al, 1
0x18004d8b2  jnz     loc_18004D95A
0x18004d8b8  mov     rdx, rdi
0x18004d8bb  lea     rax, [rdx+rdx*2]
0x18004d8bf  mov     r8, [r9+rax*8]
0x18004d8c3  test    r8, r8
0x18004d8c6  jz      short loc_18004D8E6
0x18004d8c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d8cc  inc     rax
0x18004d8cf  cmp     [r8+rax*2], di
0x18004d8d4  jnz     short loc_18004D8CC
0x18004d8d6  mov     [rsp+2B0h+cchName], eax
0x18004d8da  inc     r15d
0x18004d8dd  lea     eax, ds:0Ah[rax*2]
0x18004d8e4  add     [rsi], eax
0x18004d8e6  inc     rdx
0x18004d8e9  cmp     rdx, 2Dh ; '-'
0x18004d8ed  jnz     short loc_18004D8BB
0x18004d8ef  test    r12, r12
0x18004d8f2  jnz     loc_18004DA57
0x18004d8f8  mov     ebx, edi
0x18004d8fa  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18004d8ff  test    rcx, rcx
0x18004d902  jz      short loc_18004D910
0x18004d904  call    cs:__imp_RegCloseKey
0x18004d90b  nop     dword ptr [rax+rax+00h]
0x18004d910  test    r14, r14
0x18004d913  jz      short loc_18004D91D
0x18004d915  mov     rcx, r14
0x18004d918  call    MSCryptFree
0x18004d91d  mov     eax, ebx
0x18004d91f  mov     rcx, [rbp+1B0h+var_40]
0x18004d926  xor     rcx, rsp; StackCookie
0x18004d929  call    __security_check_cookie
0x18004d92e  mov     rbx, [rsp+2B0h+arg_8]
0x18004d936  add     rsp, 280h
0x18004d93d  pop     r15
0x18004d93f  pop     r14
0x18004d941  pop     r13
0x18004d943  pop     r12
0x18004d945  pop     rdi
0x18004d946  pop     rsi
0x18004d947  pop     rbp
0x18004d948  retn
0x18004d94a  call    GetTrustedEnvironment
0x18004d94f  mov     ecx, cs:g_TrustedEnvironment
0x18004d955  jmp     loc_18004D8A9
0x18004d95a  lea     rax, [rsp+2B0h+hKey]
0x18004d95f  mov     r9d, 20019h; samDesired
0x18004d965  xor     r8d, r8d; ulOptions
0x18004d968  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18004d96d  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18004d974  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d97b  call    cs:__imp_RegOpenKeyExW
0x18004d982  nop     dword ptr [rax+rax+00h]
0x18004d987  mov     ebx, eax
0x18004d989  test    eax, eax
0x18004d98b  jnz     loc_18004DB3E
0x18004d991  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18004d996  lea     rax, [rsp+2B0h+cSubKeys]
0x18004d99b  mov     [rsp+2B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18004d9a0  xor     r9d, r9d; lpReserved
0x18004d9a3  mov     [rsp+2B0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18004d9a8  xor     r8d, r8d; lpcchClass
0x18004d9ab  mov     [rsp+2B0h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18004d9b0  xor     edx, edx; lpClass
0x18004d9b2  mov     [rsp+2B0h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18004d9b7  mov     [rsp+2B0h+lpcValues], rdi; lpcValues
0x18004d9bc  mov     [rsp+2B0h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18004d9c1  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x18004d9c6  mov     [rsp+2B0h+phkResult], rax; lpcSubKeys
0x18004d9cb  call    cs:__imp_RegQueryInfoKeyW
0x18004d9d2  nop     dword ptr [rax+rax+00h]
0x18004d9d7  mov     ebx, eax
0x18004d9d9  test    eax, eax
0x18004d9db  jnz     loc_18004DC0B
0x18004d9e1  mov     ebx, [rsp+2B0h+cSubKeys]
0x18004d9e5  add     ebx, 7
0x18004d9e8  shr     rbx, 3
0x18004d9ec  mov     rcx, rbx
0x18004d9ef  call    SafeAllocaAllocateFromHeap
0x18004d9f4  mov     r14, rax
0x18004d9f7  test    rax, rax
0x18004d9fa  jnz     loc_18004DB82
0x18004da00  mov     ebx, 0C0000017h
0x18004da05  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da0c  lea     rax, WPP_GLOBAL_Control
0x18004da13  cmp     rcx, rax
0x18004da16  jz      loc_18004D8FA
0x18004da1c  test    byte ptr [rcx+1Ch], 1
0x18004da20  jz      loc_18004D8FA
0x18004da26  mov     dword ptr [rsp+2B0h+lpcbMaxClassLen], 584h
0x18004da2e  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004da35  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax
0x18004da3a  mov     dword ptr [rsp+2B0h+phkResult], 0C0000017h
0x18004da42  mov     rcx, [rcx+10h]
0x18004da46  lea     r9, aStatus; "Status"
0x18004da4d  call    WPP_SF_sDsd
0x18004da52  jmp     loc_18004D8FA
0x18004da57  cmp     r13d, [rsi]
0x18004da5a  jb      loc_18004DC65
0x18004da60  mov     esi, edi
0x18004da62  mov     [r12], r15d
0x18004da66  mov     edi, r15d
0x18004da69  lea     rax, [r12+10h]
0x18004da6e  add     rdi, 2
0x18004da72  mov     [r12+8], rax
0x18004da77  xor     r15d, r15d
0x18004da7a  lea     rdi, [r12+rdi*8]
0x18004da7e  test    ecx, ecx
0x18004da80  jz      loc_18004DBEA
0x18004da86  test    cl, 1
0x18004da89  jnz     loc_18004DBAD
0x18004da8f  mov     r11d, r15d
0x18004da92  cmp     r11d, 2Dh ; '-'
0x18004da96  jnb     loc_18004DBC2
0x18004da9c  mov     eax, r11d
0x18004da9f  lea     r8, [rax+rax*2]
0x18004daa3  mov     rcx, [r9+r8*8]
0x18004daa7  test    rcx, rcx
0x18004daaa  jz      short loc_18004DAF2
0x18004daac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004dab0  inc     rax
0x18004dab3  cmp     [rcx+rax*2], r15w
0x18004dab8  jnz     short loc_18004DAB0
0x18004daba  mov     [rsp+2B0h+cchName], eax
0x18004dabe  mov     rax, [r12+8]
0x18004dac3  mov     ecx, esi
0x18004dac5  mov     [rax+rcx*8], rdi
0x18004dac9  mov     rcx, rdi; pszDest
0x18004dacc  mov     edx, [rsp+2B0h+cchName]
0x18004dad0  mov     r8, [r9+r8*8]; pszSrc
0x18004dad4  inc     edx; cchDest
0x18004dad6  call    StringCchCopyW
0x18004dadb  test    eax, eax
0x18004dadd  js      short loc_18004DAF7
0x18004dadf  mov     eax, [rsp+2B0h+cchName]
0x18004dae3  lea     r9, off_1800860D0; "brainpoolP160r1"
0x18004daea  inc     esi
0x18004daec  inc     eax
0x18004daee  lea     rdi, [rdi+rax*2]
0x18004daf2  inc     r11d
0x18004daf5  jmp     short loc_18004DA92
0x18004daf7  mov     ebx, 0C00000E5h
0x18004dafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db03  lea     rax, WPP_GLOBAL_Control
0x18004db0a  cmp     rcx, rax
0x18004db0d  jz      loc_18004D8FA
0x18004db13  test    byte ptr [rcx+1Ch], 1
0x18004db17  jz      loc_18004D8FA
0x18004db1d  mov     dword ptr [rsp+2B0h+lpcbMaxClassLen], 60Eh
0x18004db25  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004db2c  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax
0x18004db31  mov     dword ptr [rsp+2B0h+phkResult], 0C00000E5h
0x18004db39  jmp     loc_18004DA42
0x18004db3e  jg      loc_18004DBFD
0x18004db44  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db4b  lea     rax, WPP_GLOBAL_Control
0x18004db52  cmp     rcx, rax
0x18004db55  jz      loc_18004D8FA
0x18004db5b  test    byte ptr [rcx+1Ch], 1
0x18004db5f  jz      loc_18004D8FA
0x18004db65  mov     dword ptr [rsp+2B0h+lpcbMaxClassLen], 573h
0x18004db6d  lea     rax, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004db74  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rax
0x18004db79  mov     dword ptr [rsp+2B0h+phkResult], ebx
0x18004db7d  jmp     loc_18004DA42
0x18004db82  mov     r8, rbx; Size
0x18004db85  xor     edx, edx; Val
0x18004db87  mov     rcx, r14; void *
0x18004db8a  call    memset_0
0x18004db8f  mov     ebx, edi
0x18004db91  cmp     [rsp+2B0h+cSubKeys], edi
0x18004db95  ja      loc_18004DC1F
0x18004db9b  mov     ecx, cs:g_TrustedEnvironment
0x18004dba1  lea     r9, off_1800860D0; "brainpoolP160r1"
0x18004dba8  jmp     loc_18004D8B8
0x18004dbad  mov     ebx, r15d
0x18004dbb0  cmp     ebx, [rsp+2B0h+cSubKeys]
0x18004dbb4  jb      short loc_18004DBCA
0x18004dbb6  lea     r9, off_1800860D0; "brainpoolP160r1"
0x18004dbbd  jmp     loc_18004DA8F
0x18004dbc2  mov     ebx, r15d
0x18004dbc5  jmp     loc_18004D8FA
0x18004dbca  mov     eax, ebx
0x18004dbcc  mov     ecx, ebx
0x18004dbce  and     ecx, 7
0x18004dbd1  shr     rax, 3
0x18004dbd5  mov     edx, 1
0x18004dbda  shl     edx, cl
0x18004dbdc  test    [rax+r14], dl
0x18004dbe0  jz      loc_18008299E
0x18004dbe6  inc     ebx
0x18004dbe8  jmp     short loc_18004DBB0
0x18004dbea  call    GetTrustedEnvironment
0x18004dbef  mov     ecx, eax
0x18004dbf1  lea     r9, off_1800860D0; "brainpoolP160r1"
0x18004dbf8  jmp     loc_18004DA86
0x18004dbfd  movzx   ebx, ax
0x18004dc00  or      ebx, 0C0070000h
0x18004dc06  jmp     loc_18004DB44
0x18004dc0b  jle     loc_1800828E2
0x18004dc11  movzx   ebx, ax
0x18004dc14  or      ebx, 0C0070000h
0x18004dc1a  jmp     loc_1800828E2
0x18004dc1f  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18004dc24  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18004dc29  mov     [rsp+2B0h+lpcValues], rdi; lpftLastWriteTime
0x18004dc2e  lea     r8, [rsp+2B0h+Name]; lpName
0x18004dc33  mov     [rsp+2B0h+lpcbMaxClassLen], rdi; lpcchClass
0x18004dc38  mov     edx, ebx; dwIndex
0x18004dc3a  mov     [rsp+2B0h+lpcbMaxSubKeyLen], rdi; lpClass
0x18004dc3f  mov     [rsp+2B0h+phkResult], rdi; lpReserved
0x18004dc44  mov     [rsp+2B0h+cchName], 0FFh
0x18004dc4c  call    cs:__imp_RegEnumKeyExW
0x18004dc53  nop     dword ptr [rax+rax+00h]
0x18004dc58  test    eax, eax
0x18004dc5a  jz      loc_180082915
0x18004dc60  jmp     loc_180082986
0x18004dc65  mov     ebx, 0C0000023h
0x18004dc6a  jmp     loc_18004D8FA
0x1800828e2  mov     r9d, 57Bh
0x1800828e8  mov     ecx, ebx
0x1800828ea  jmp     short loc_1800828FC
0x1800828ec  mov     ebx, 0C00000E5h
0x1800828f1  mov     r9d, 5F4h
0x1800828f7  mov     ecx, 0C00000E5h
0x1800828fc  lea     rdx, aStatus; "Status"
0x180082903  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008290a  call    DebugTraceError
0x18008290f  nop
0x180082910  jmp     loc_18004D8FA
0x180082915  cmp     edi, 2Dh ; '-'
0x180082918  jnb     short loc_18008295C
0x18008291a  mov     eax, edi
0x18008291c  lea     rcx, [rax+rax*2]
0x180082920  lea     rax, off_1800860D0; "brainpoolP160r1"
0x180082927  mov     rcx, [rax+rcx*8]; String1
0x18008292b  test    rcx, rcx
0x18008292e  jz      short loc_180082997
0x180082930  lea     rdx, [rsp+2B0h+Name]; String2
0x180082935  call    cs:__imp__wcsicmp
0x18008293c  nop     dword ptr [rax+rax+00h]
0x180082941  test    eax, eax
0x180082943  jnz     short loc_180082997
0x180082945  mov     edx, ebx
0x180082947  mov     eax, ebx
0x180082949  shr     rdx, 3
0x18008294d  and     eax, 7
0x180082950  movzx   ecx, byte ptr [rdx+r14]
0x180082955  bts     ecx, eax
0x180082958  mov     [rdx+r14], cl
0x18008295c  mov     eax, ebx
0x18008295e  mov     ecx, ebx
0x180082960  and     ecx, 7
0x180082963  shr     rax, 3
0x180082967  mov     edx, 1
0x18008296c  shl     edx, cl
0x18008296e  test    [rax+r14], dl
0x180082972  jnz     short loc_180082984
0x180082974  mov     eax, [rsp+2B0h+cchName]
0x180082978  inc     r15d
0x18008297b  lea     eax, ds:0Ah[rax*2]
0x180082982  add     [rsi], eax
0x180082984  xor     edi, edi
0x180082986  inc     ebx
0x180082988  cmp     ebx, [rsp+2B0h+cSubKeys]
0x18008298c  jb      loc_18004DC1F
0x180082992  jmp     loc_18004DB9B
0x180082997  inc     edi
0x180082999  jmp     loc_180082915
0x18008299e  mov     rcx, [rsp+2B0h+hKey]; hKey
  ... truncated ...
```
