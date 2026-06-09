# GetHashOfSecruityDescr

- ea: `0x18000b758`
- end: `0x18000b94b`
- name: `GetHashOfSecruityDescr`
- size: `499`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b960`

## callees

- `0x180001630`
- `0x18000b758`
- `0x180010920`
- `0x180010950`
- `0x180010f9c`
- `0x18001a450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b8bf`
- `bcrypt!BCryptDestroyHash` at `0x18000b918`
- `bcrypt!BCryptDestroyHash` at `0x18000b918`
- `bcrypt!BCryptFinishHash` at `0x18000b85a`
- `bcrypt!BCryptFinishHash` at `0x18000b85a`
- `bcrypt!BCryptHashData` at `0x18000b834`
- `bcrypt!BCryptHashData` at `0x18000b834`
- `bcrypt!BCryptCreateHash` at `0x18000b7f9`
- `bcrypt!BCryptCreateHash` at `0x18000b7f9`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b909`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000b909`
- `CRYPT32!CryptBinaryToStringW` at `0x18000b8b5`
- `CRYPT32!CryptBinaryToStringW` at `0x18000b8b5`

## string_xrefs

- `0x18000b7cd`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000b80b`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`
- `0x18000b8cb`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyfilecache.cxx`

## pseudocode

```c
__int64 __fastcall GetHashOfSecruityDescr(PUCHAR pbInput, ULONG cbInput, WCHAR **a3)
{
  WCHAR *v3; // rdi
  int CachedBCryptHandle; // eax
  signed int LastError; // ebx
  unsigned int v9; // r9d
  unsigned int v10; // ecx
  NTSTATUS v11; // esi
  unsigned int v12; // r9d
  DWORD pcchString; // [rsp+40h] [rbp-40h] BYREF
  int v15; // [rsp+44h] [rbp-3Ch] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+48h] [rbp-38h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-30h] BYREF
  UCHAR pbOutput[32]; // [rsp+58h] [rbp-28h] BYREF

  v3 = 0;
  hAlgorithm = 0;
  phHash = 0;
  v15 = 1;
  pcchString = 0;
  CachedBCryptHandle = GetCachedBCryptHandle(L"SHA256", &hAlgorithm, 2u, &v15);
  LastError = CachedBCryptHandle;
  if ( CachedBCryptHandle < 0 )
  {
    v9 = 175;
    v10 = CachedBCryptHandle;
LABEL_3:
    SidKeyDebugTraceError(v10, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", v9);
    goto LABEL_17;
  }
  v11 = BCryptCreateHash(hAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v11 < 0 )
  {
    v12 = 189;
LABEL_6:
    SidKeyDebugTraceError(v11, "status", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx", v12);
    LastError = v11;
    goto LABEL_17;
  }
  v11 = BCryptHashData(phHash, pbInput, cbInput, 0);
  if ( v11 < 0 )
  {
    v12 = 201;
    goto LABEL_6;
  }
  v11 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
  if ( v11 < 0 )
  {
    v12 = 213;
    goto LABEL_6;
  }
  v3 = (WCHAR *)SIDKeyProvAlloc(0x82u);
  if ( !v3 )
  {
    LastError = -2147024882;
    v9 = 223;
    v10 = -2147024882;
    goto LABEL_3;
  }
  pcchString = 65;
  if ( CryptBinaryToStringW(pbOutput, 0x20u, 0x4000000Cu, v3, &pcchString) )
  {
    *a3 = v3;
    v3 = 0;
  }
  else
  {
    LastError = GetLastError();
    SidKeyDebugTraceError(
      LastError,
      "dwReturn",
      "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyfilecache.cxx",
      0xECu);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_17:
  if ( hAlgorithm && !v15 )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v3 )
    SIDKeyProvFree(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000b758  push    rbp
0x18000b75a  push    rbx
0x18000b75b  push    rsi
0x18000b75c  push    rdi
0x18000b75d  push    r12
0x18000b75f  push    r13
0x18000b761  push    r15
0x18000b763  mov     rbp, rsp
0x18000b766  sub     rsp, 80h
0x18000b76d  mov     rax, cs:__security_cookie
0x18000b774  xor     rax, rsp
0x18000b777  mov     [rbp+var_8], rax
0x18000b77b  xor     edi, edi
0x18000b77d  mov     [rbp+hAlgorithm], 0
0x18000b785  mov     r15, r8
0x18000b788  mov     [rbp+phHash], 0
0x18000b790  mov     r13d, edx
0x18000b793  mov     [rbp+var_3C], 1
0x18000b79a  mov     r12, rcx
0x18000b79d  mov     [rbp+pcchString], edi
0x18000b7a0  lea     r8d, [rdi+2]; unsigned int
0x18000b7a4  lea     r9, [rbp+var_3C]; int *
0x18000b7a8  lea     rdx, [rbp+hAlgorithm]; void **
0x18000b7ac  lea     rcx, Src; "SHA256"
0x18000b7b3  call    ?GetCachedBCryptHandle@@YAJPEBGPEAPEAXKPEAH@Z; GetCachedBCryptHandle(ushort const *,void * *,ulong,int *)
0x18000b7b8  mov     ebx, eax
0x18000b7ba  test    eax, eax
0x18000b7bc  jns     short loc_18000B7DE
0x18000b7be  mov     r9d, 0AFh; unsigned int
0x18000b7c4  mov     ecx, eax; unsigned int
0x18000b7c6  lea     rdx, aHr; "hr"
0x18000b7cd  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b7d4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b7d9  jmp     loc_18000B8F6
0x18000b7de  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18000b7e2  lea     rdx, [rbp+phHash]; phHash
0x18000b7e6  mov     [rsp+80h+dwFlags], edi; dwFlags
0x18000b7ea  xor     r9d, r9d; cbHashObject
0x18000b7ed  mov     [rsp+80h+cbSecret], edi; cbSecret
0x18000b7f1  xor     r8d, r8d; pbHashObject
0x18000b7f4  mov     [rsp+80h+pbSecret], rdi; pbSecret
0x18000b7f9  call    cs:__imp_BCryptCreateHash
0x18000b7ff  mov     esi, eax
0x18000b801  test    eax, eax
0x18000b803  jns     short loc_18000B827
0x18000b805  mov     r9d, 0BDh; unsigned int
0x18000b80b  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b812  mov     ecx, esi; unsigned int
0x18000b814  lea     rdx, aStatus; "status"
0x18000b81b  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b820  mov     ebx, esi
0x18000b822  jmp     loc_18000B8F6
0x18000b827  mov     rcx, [rbp+phHash]; hHash
0x18000b82b  xor     r9d, r9d; dwFlags
0x18000b82e  mov     r8d, r13d; cbInput
0x18000b831  mov     rdx, r12; pbInput
0x18000b834  call    cs:__imp_BCryptHashData
0x18000b83a  mov     esi, eax
0x18000b83c  test    eax, eax
0x18000b83e  jns     short loc_18000B848
0x18000b840  mov     r9d, 0C9h
0x18000b846  jmp     short loc_18000B80B
0x18000b848  mov     rcx, [rbp+phHash]; hHash
0x18000b84c  lea     rdx, [rbp+pbOutput]; pbOutput
0x18000b850  xor     r9d, r9d; dwFlags
0x18000b853  lea     r12d, [r9+20h]
0x18000b857  mov     r8d, r12d; cbOutput
0x18000b85a  call    cs:__imp_BCryptFinishHash
0x18000b860  mov     esi, eax
0x18000b862  test    eax, eax
0x18000b864  jns     short loc_18000B86E
0x18000b866  mov     r9d, 0D5h
0x18000b86c  jmp     short loc_18000B80B
0x18000b86e  mov     ecx, 82h; unsigned __int64
0x18000b873  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000b878  mov     rdi, rax
0x18000b87b  test    rax, rax
0x18000b87e  jnz     short loc_18000B895
0x18000b880  mov     ebx, 8007000Eh
0x18000b885  mov     r9d, 0DFh
0x18000b88b  mov     ecx, 8007000Eh
0x18000b890  jmp     loc_18000B7C6
0x18000b895  lea     rax, [rbp+pcchString]
0x18000b899  mov     [rbp+pcchString], 41h ; 'A'
0x18000b8a0  mov     r9, rdi; pszString
0x18000b8a3  mov     [rsp+80h+pbSecret], rax; pcchString
0x18000b8a8  mov     r8d, 4000000Ch; dwFlags
0x18000b8ae  lea     rcx, [rbp+pbOutput]; pbBinary
0x18000b8b2  mov     edx, r12d; cbBinary
0x18000b8b5  call    cs:__imp_CryptBinaryToStringW
0x18000b8bb  test    eax, eax
0x18000b8bd  jnz     short loc_18000B8F1
0x18000b8bf  call    cs:__imp_GetLastError
0x18000b8c5  mov     r9d, 0ECh; unsigned int
0x18000b8cb  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000b8d2  mov     ecx, eax; unsigned int
0x18000b8d4  lea     rdx, aDwreturn; "dwReturn"
0x18000b8db  mov     ebx, eax
0x18000b8dd  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000b8e2  test    ebx, ebx
0x18000b8e4  jle     short loc_18000B8F6
0x18000b8e6  movzx   ebx, bx
0x18000b8e9  or      ebx, 80070000h
0x18000b8ef  jmp     short loc_18000B8F6
0x18000b8f1  mov     [r15], rdi
0x18000b8f4  xor     edi, edi
0x18000b8f6  cmp     [rbp+hAlgorithm], 0
0x18000b8fb  jz      short loc_18000B90F
0x18000b8fd  cmp     [rbp+var_3C], 0
0x18000b901  jnz     short loc_18000B90F
0x18000b903  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x18000b907  xor     edx, edx; dwFlags
0x18000b909  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000b90f  mov     rcx, [rbp+phHash]; hHash
0x18000b913  test    rcx, rcx
0x18000b916  jz      short loc_18000B91E
0x18000b918  call    cs:__imp_BCryptDestroyHash
0x18000b91e  test    rdi, rdi
0x18000b921  jz      short loc_18000B92B
0x18000b923  mov     rcx, rdi; lpMem
0x18000b926  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000b92b  mov     eax, ebx
0x18000b92d  mov     rcx, [rbp+var_8]
0x18000b931  xor     rcx, rsp; StackCookie
0x18000b934  call    __security_check_cookie
0x18000b939  add     rsp, 80h
0x18000b940  pop     r15
0x18000b942  pop     r13
0x18000b944  pop     r12
0x18000b946  pop     rdi
0x18000b947  pop     rsi
0x18000b948  pop     rbx
0x18000b949  pop     rbp
0x18000b94a  retn
```
