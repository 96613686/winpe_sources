# CryptoHelper::ComputeSha256Hash(AadContextFunctions *,_AP_BLOB *,_AP_BLOB *)

- ea: `0x18007cdac`
- end: `0x18007d112`
- name: `?ComputeSha256Hash@CryptoHelper@@SAJPEAVAadContextFunctions@@PEAU_AP_BLOB@@1@Z`
- size: `870`
- prototype: `__int64 __fastcall(struct AadContextFunctions *this, struct _AP_BLOB *, struct _AP_BLOB *)`
- caller_count: `12`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800225f4`
- `0x180028760`
- `0x18003d750`
- `0x18003df38`
- `0x18003ff18`
- `0x18004082c`
- `0x18004c174`
- `0x18004d140`
- `0x18004d6fc`
- `0x180054e7c`
- `0x18005ef28`
- `0x18007f9c4`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180007a90`
- `0x180071e14`
- `0x180078b18`
- `0x18007cdac`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ceba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d02c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ceba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cf77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007d02c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007cf04`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18007cf04`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007d0d6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18007d0d6`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007ceb0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18007ceb0`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007ce4c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007ce4c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007cf6d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d01e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007cf6d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18007d01e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18007d0e7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18007d0e7`

## string_xrefs

- `0x18007cde8`: `CryptoHelper::ComputeSha256Hash`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CryptoHelper::ComputeSha256Hash(
        struct AadContextFunctions *this,
        struct _AP_BLOB *a2,
        struct _AP_BLOB *a3)
{
  signed int LastError; // eax
  unsigned int v7; // ecx
  BYTE *v8; // rax
  unsigned int v9; // ebx
  DWORD dwFlags[2]; // [rsp+20h] [rbp-49h]
  int v12; // [rsp+30h] [rbp-39h]
  DWORD pdwDataLen; // [rsp+50h] [rbp-19h] BYREF
  HCRYPTHASH phHash; // [rsp+58h] [rbp-11h] BYREF
  HCRYPTPROV phProv; // [rsp+60h] [rbp-9h] BYREF
  const char *v16[11]; // [rsp+68h] [rbp-1h] BYREF
  int v17; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int pbData; // [rsp+E8h] [rbp+7Fh] BYREF

  v17 = 0;
  phProv = 0;
  phHash = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v16,
    (int)"crypto.cpp",
    (int)"CryptoHelper::ComputeSha256Hash",
    (int)&v17);
  if ( !this || !a3 || !a2 || !IsApBlobDefined(a2) )
  {
    LastError = -2147024809;
    v17 = -2147024809;
    v12 = 731;
    goto LABEL_33;
  }
  *(_QWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  if ( !CryptAcquireContextW(&phProv, 0, 0, 0x18u, 0xF0000000) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v17 = LastError;
    if ( LastError < 0 )
    {
      v12 = 738;
LABEL_33:
      dwFlags[0] = LastError;
      WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)dwFlags, "crypto.cpp", v12, "HRESULT", &base);
      goto LABEL_34;
    }
  }
  if ( !CryptCreateHash(phProv, 0x800Cu, 0, 0, &phHash) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v17 = LastError;
    if ( LastError < 0 )
    {
      v12 = 743;
      goto LABEL_33;
    }
  }
  if ( !CryptHashData(phHash, *((const BYTE **)a2 + 1), *(_DWORD *)a2, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v17 = LastError;
    if ( LastError < 0 )
    {
      v12 = 749;
      goto LABEL_33;
    }
  }
  pbData = 0;
  pdwDataLen = 4;
  if ( !CryptGetHashParam(phHash, 4u, (BYTE *)&pbData, &pdwDataLen, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v17 = LastError;
    if ( LastError < 0 )
    {
      v12 = 759;
      goto LABEL_33;
    }
  }
  v7 = pbData;
  *(_DWORD *)a3 = pbData;
  v8 = (BYTE *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)this + 8LL))(
                 this,
                 64,
                 v7);
  *((_QWORD *)a3 + 1) = v8;
  if ( !v8 )
  {
    LastError = -2147024882;
    v17 = -2147024882;
    v12 = 767;
    goto LABEL_33;
  }
  if ( CryptGetHashParam(phHash, 2u, v8, (DWORD *)a3, 0) )
  {
LABEL_34:
    if ( v17 < 0 && this && a3 )
      AadContextFunctions::LocalFreeApBlob(this, a3);
    goto LABEL_38;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v17 = LastError;
  if ( LastError < 0 )
  {
    v12 = 772;
    goto LABEL_33;
  }
LABEL_38:
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  v9 = v17;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v16);
  return v9;
}

```

## disassembly

```asm
0x18007cdac  mov     [rsp-8+arg_8], rbx
0x18007cdb1  push    rbp
0x18007cdb2  push    rsi
0x18007cdb3  push    rdi
0x18007cdb4  push    r12
0x18007cdb6  push    r15
0x18007cdb8  lea     rbp, [rsp-37h]
0x18007cdbd  sub     rsp, 0A0h
0x18007cdc4  mov     rdi, r8
0x18007cdc7  mov     rbx, rdx
0x18007cdca  mov     rsi, rcx
0x18007cdcd  mov     [rbp+57h+arg_0], 0
0x18007cdd4  mov     [rbp+57h+phProv], 0
0x18007cddc  mov     [rbp+57h+phHash], 0
0x18007cde4  lea     r9, [rbp+57h+arg_0]
0x18007cde8  lea     r8, aCryptohelperCo_0; "CryptoHelper::ComputeSha256Hash"
0x18007cdef  lea     r12, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007cdf6  mov     rdx, r12
0x18007cdf9  lea     rcx, [rbp+57h+var_58]
0x18007cdfd  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18007ce02  nop
0x18007ce03  test    rsi, rsi
0x18007ce06  jz      loc_18007D069
0x18007ce0c  test    rdi, rdi
0x18007ce0f  jz      loc_18007D069
0x18007ce15  test    rbx, rbx
0x18007ce18  jz      loc_18007D069
0x18007ce1e  mov     rcx, rbx; struct _AP_BLOB *
0x18007ce21  call    ?IsApBlobDefined@@YA_NPEAU_AP_BLOB@@@Z; IsApBlobDefined(_AP_BLOB *)
0x18007ce26  test    al, al
0x18007ce28  jz      loc_18007D069
0x18007ce2e  xor     eax, eax
0x18007ce30  mov     [rdi], rax
0x18007ce33  mov     [rdi+8], rax
0x18007ce37  mov     [rsp+0C0h+dwFlags], 0F0000000h; dwFlags
0x18007ce3f  lea     r9d, [rax+18h]; dwProvType
0x18007ce43  xor     r8d, r8d; szProvider
0x18007ce46  xor     edx, edx; szContainer
0x18007ce48  lea     rcx, [rbp+57h+phProv]; phProv
0x18007ce4c  call    cs:__imp_CryptAcquireContextW
0x18007ce52  mov     r15d, 80070000h
0x18007ce58  test    eax, eax
0x18007ce5a  jnz     short loc_18007CE98
0x18007ce5c  call    cs:__imp_GetLastError
0x18007ce62  test    eax, eax
0x18007ce64  jle     short loc_18007CE6C
0x18007ce66  movzx   eax, ax
0x18007ce69  or      eax, r15d
0x18007ce6c  mov     [rbp+57h+arg_0], eax
0x18007ce6f  test    eax, eax
0x18007ce71  jns     short loc_18007CE98
0x18007ce73  lea     rcx, base
0x18007ce7a  mov     [rsp+0C0h+var_80], rcx
0x18007ce7f  lea     rcx, aHresult; "HRESULT"
0x18007ce86  mov     [rsp+0C0h+var_88], rcx
0x18007ce8b  mov     [rsp+0C0h+var_90], 2E2h
0x18007ce93  jmp     loc_18007D091
0x18007ce98  lea     rax, [rbp+57h+phHash]
0x18007ce9c  mov     qword ptr [rsp+0C0h+dwFlags], rax; phHash
0x18007cea1  xor     r9d, r9d; dwFlags
0x18007cea4  xor     r8d, r8d; hKey
0x18007cea7  mov     edx, 800Ch; Algid
0x18007ceac  mov     rcx, [rbp+57h+phProv]; hProv
0x18007ceb0  call    cs:__imp_CryptCreateHash
0x18007ceb6  test    eax, eax
0x18007ceb8  jnz     short loc_18007CEF6
0x18007ceba  call    cs:__imp_GetLastError
0x18007cec0  test    eax, eax
0x18007cec2  jle     short loc_18007CECA
0x18007cec4  movzx   eax, ax
0x18007cec7  or      eax, r15d
0x18007ceca  mov     [rbp+57h+arg_0], eax
0x18007cecd  test    eax, eax
0x18007cecf  jns     short loc_18007CEF6
0x18007ced1  lea     rcx, base
0x18007ced8  mov     [rsp+0C0h+var_80], rcx
0x18007cedd  lea     rcx, aHresult; "HRESULT"
0x18007cee4  mov     [rsp+0C0h+var_88], rcx
0x18007cee9  mov     [rsp+0C0h+var_90], 2E7h
0x18007cef1  jmp     loc_18007D091
0x18007cef6  xor     r9d, r9d; dwFlags
0x18007cef9  mov     r8d, [rbx]; dwDataLen
0x18007cefc  mov     rdx, [rbx+8]; pbData
0x18007cf00  mov     rcx, [rbp+57h+phHash]; hHash
0x18007cf04  call    cs:__imp_CryptHashData
0x18007cf0a  test    eax, eax
0x18007cf0c  jnz     short loc_18007CF4A
0x18007cf0e  call    cs:__imp_GetLastError
0x18007cf14  test    eax, eax
0x18007cf16  jle     short loc_18007CF1E
0x18007cf18  movzx   eax, ax
0x18007cf1b  or      eax, r15d
0x18007cf1e  mov     [rbp+57h+arg_0], eax
0x18007cf21  test    eax, eax
0x18007cf23  jns     short loc_18007CF4A
0x18007cf25  lea     rcx, base
0x18007cf2c  mov     [rsp+0C0h+var_80], rcx
0x18007cf31  lea     rcx, aHresult; "HRESULT"
0x18007cf38  mov     [rsp+0C0h+var_88], rcx
0x18007cf3d  mov     [rsp+0C0h+var_90], 2EDh
0x18007cf45  jmp     loc_18007D091
0x18007cf4a  mov     [rbp+57h+pbData], 0
0x18007cf51  mov     edx, 4; dwParam
0x18007cf56  mov     [rbp+57h+pdwDataLen], edx
0x18007cf59  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18007cf61  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18007cf65  lea     r8, [rbp+57h+pbData]; pbData
0x18007cf69  mov     rcx, [rbp+57h+phHash]; hHash
0x18007cf6d  call    cs:__imp_CryptGetHashParam
0x18007cf73  test    eax, eax
0x18007cf75  jnz     short loc_18007CFB3
0x18007cf77  call    cs:__imp_GetLastError
0x18007cf7d  test    eax, eax
0x18007cf7f  jle     short loc_18007CF87
0x18007cf81  movzx   eax, ax
0x18007cf84  or      eax, r15d
0x18007cf87  mov     [rbp+57h+arg_0], eax
0x18007cf8a  test    eax, eax
0x18007cf8c  jns     short loc_18007CFB3
0x18007cf8e  lea     rcx, base
0x18007cf95  mov     [rsp+0C0h+var_80], rcx
0x18007cf9a  lea     rcx, aHresult; "HRESULT"
0x18007cfa1  mov     [rsp+0C0h+var_88], rcx
0x18007cfa6  mov     [rsp+0C0h+var_90], 2F7h
0x18007cfae  jmp     loc_18007D091
0x18007cfb3  mov     ecx, [rbp+57h+pbData]
0x18007cfb6  mov     [rdi], ecx
0x18007cfb8  mov     rax, [rsi]
0x18007cfbb  mov     r8d, ecx
0x18007cfbe  mov     edx, 40h ; '@'
0x18007cfc3  mov     rcx, rsi
0x18007cfc6  mov     rax, [rax+8]
0x18007cfca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfcf  mov     [rdi+8], rax
0x18007cfd3  mov     ebx, 2
0x18007cfd8  test    rax, rax
0x18007cfdb  jnz     short loc_18007D00A
0x18007cfdd  mov     eax, 8007000Eh
0x18007cfe2  mov     [rbp+57h+arg_0], eax
0x18007cfe5  lea     rcx, base
0x18007cfec  mov     [rsp+0C0h+var_80], rcx
0x18007cff1  lea     rcx, aHresult; "HRESULT"
0x18007cff8  mov     [rsp+0C0h+var_88], rcx
0x18007cffd  mov     [rsp+0C0h+var_90], 2FFh
0x18007d005  jmp     loc_18007D096
0x18007d00a  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18007d012  mov     r9, rdi; pdwDataLen
0x18007d015  mov     r8, rax; pbData
0x18007d018  mov     edx, ebx; dwParam
0x18007d01a  mov     rcx, [rbp+57h+phHash]; hHash
0x18007d01e  call    cs:__imp_CryptGetHashParam
0x18007d024  test    eax, eax
0x18007d026  jnz     loc_18007D0B2
0x18007d02c  call    cs:__imp_GetLastError
0x18007d032  test    eax, eax
0x18007d034  jle     short loc_18007D03C
0x18007d036  movzx   eax, ax
0x18007d039  or      eax, r15d
0x18007d03c  mov     [rbp+57h+arg_0], eax
0x18007d03f  test    eax, eax
0x18007d041  jns     loc_18007D0CD
0x18007d047  lea     rcx, base
0x18007d04e  mov     [rsp+0C0h+var_80], rcx
0x18007d053  lea     rcx, aHresult; "HRESULT"
0x18007d05a  mov     [rsp+0C0h+var_88], rcx
0x18007d05f  mov     [rsp+0C0h+var_90], 304h
0x18007d067  jmp     short loc_18007D096
0x18007d069  mov     eax, 80070057h
0x18007d06e  mov     [rbp+57h+arg_0], eax
0x18007d071  lea     rcx, base
0x18007d078  mov     [rsp+0C0h+var_80], rcx
0x18007d07d  lea     rcx, aHresult; "HRESULT"
0x18007d084  mov     [rsp+0C0h+var_88], rcx
0x18007d089  mov     [rsp+0C0h+var_90], 2DBh
0x18007d091  mov     ebx, 2
0x18007d096  mov     [rsp+0C0h+var_98], r12
0x18007d09b  mov     [rsp+0C0h+dwFlags], eax
0x18007d09f  mov     r9d, ebx
0x18007d0a2  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007d0a9  xor     edx, edx
0x18007d0ab  mov     ecx, ebx
0x18007d0ad  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007d0b2  cmp     [rbp+57h+arg_0], 0
0x18007d0b6  jge     short loc_18007D0CD
0x18007d0b8  test    rsi, rsi
0x18007d0bb  jz      short loc_18007D0CD
0x18007d0bd  test    rdi, rdi
0x18007d0c0  jz      short loc_18007D0CD
0x18007d0c2  mov     rdx, rdi; struct _AP_BLOB *
0x18007d0c5  mov     rcx, rsi; this
0x18007d0c8  call    ?LocalFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LocalFreeApBlob(_AP_BLOB *)
0x18007d0cd  mov     rcx, [rbp+57h+phHash]; hHash
0x18007d0d1  test    rcx, rcx
0x18007d0d4  jz      short loc_18007D0DC
0x18007d0d6  call    cs:__imp_CryptDestroyHash
0x18007d0dc  mov     rcx, [rbp+57h+phProv]; hProv
0x18007d0e0  test    rcx, rcx
0x18007d0e3  jz      short loc_18007D0ED
0x18007d0e5  xor     edx, edx; dwFlags
0x18007d0e7  call    cs:__imp_CryptReleaseContext
0x18007d0ed  mov     ebx, [rbp+57h+arg_0]
0x18007d0f0  lea     rcx, [rbp+57h+var_58]
0x18007d0f4  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18007d0f9  mov     eax, ebx
0x18007d0fb  mov     rbx, [rsp+0C0h+arg_8]
0x18007d103  add     rsp, 0A0h
0x18007d10a  pop     r15
0x18007d10c  pop     r12
0x18007d10e  pop     rdi
0x18007d10f  pop     rsi
0x18007d110  pop     rbp
0x18007d111  retn
```
