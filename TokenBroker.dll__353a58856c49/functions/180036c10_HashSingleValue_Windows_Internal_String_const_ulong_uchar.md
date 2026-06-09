# HashSingleValue(Windows::Internal::String const &,ulong *,uchar * *)

- ea: `0x180036c10`
- end: `0x180036fdd`
- name: `?HashSingleValue@@YAJAEBVString@Internal@Windows@@PEAKPEAPEAE@Z`
- size: `973`
- prototype: `__int64 __fastcall(const struct Windows::Internal::String *, unsigned int *, unsigned __int8 **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180035f70`
- `0x180070660`

## callees

- `0x18000bd40`
- `0x180036c10`
- `0x18007f4cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036ef8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ee5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036c83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036c83`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036cd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036e26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036eb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036fd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036c75`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036cc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036e26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036e76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036eb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036f34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036fd0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180036d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180036d52`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036c4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036c4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180036cb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036fb3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036dd8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036dd8`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180036cdb`
- `api-ms-win-core-string-l2-1-0!CharLowerW` at `0x180036cdb`
- `bcrypt!BCryptHashData` at `0x180036d89`
- `bcrypt!BCryptHashData` at `0x180036d89`
- `bcrypt!BCryptCreateHash` at `0x180036d13`
- `bcrypt!BCryptCreateHash` at `0x180036d13`
- `bcrypt!BCryptFinishHash` at `0x180036df8`
- `bcrypt!BCryptFinishHash` at `0x180036df8`
- `bcrypt!BCryptDestroyHash` at `0x180036e18`
- `bcrypt!BCryptDestroyHash` at `0x180036ea7`
- `bcrypt!BCryptDestroyHash` at `0x180036ef0`
- `bcrypt!BCryptDestroyHash` at `0x180036f26`
- `bcrypt!BCryptDestroyHash` at `0x180036f41`
- `bcrypt!BCryptDestroyHash` at `0x180036fc2`
- `bcrypt!BCryptDestroyHash` at `0x180036e18`
- `bcrypt!BCryptDestroyHash` at `0x180036ea7`
- `bcrypt!BCryptDestroyHash` at `0x180036ef0`
- `bcrypt!BCryptDestroyHash` at `0x180036f26`
- `bcrypt!BCryptDestroyHash` at `0x180036f41`
- `bcrypt!BCryptDestroyHash` at `0x180036fc2`
- `bcrypt!BCryptGetProperty` at `0x180036dc2`
- `bcrypt!BCryptGetProperty` at `0x180036dc2`

## string_xrefs

- `0x180036e4a`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x180036e87`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x180036f07`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x180036f50`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x180036f75`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`
- `0x180036f9a`: `onecore\ds\security\tokenbroker\datastore\lib\utils.cpp`

## pseudocode

```c
__int64 __fastcall HashSingleValue(HSTRING *a1, unsigned int *a2, unsigned __int8 **a3)
{
  unsigned int *v4; // rsi
  HSTRING v6; // rbx
  const WCHAR *StringRawBuffer; // rax
  unsigned __int64 v8; // rdx
  HSTRING v9; // rcx
  WCHAR *v10; // rax
  NTSTATUS v11; // r12d
  BCRYPT_HASH_HANDLE *v12; // rsi
  BCRYPT_HASH_HANDLE v13; // r14
  BCRYPT_HASH_HANDLE v14; // r15
  UINT32 StringLen; // eax
  unsigned __int64 v16; // rdi
  UCHAR *v17; // rax
  NTSTATUS v18; // eax
  NTSTATUS Property; // eax
  UCHAR *v20; // rax
  UCHAR *v21; // rdi
  NTSTATUS v22; // eax
  BCRYPT_HASH_HANDLE v23; // rcx
  ULONG v24; // eax
  signed int v26; // eax
  unsigned int v27; // edi
  BCRYPT_HASH_HANDLE v28; // rcx
  DWORD LastError; // edi
  int v30; // eax
  int v31; // eax
  int v32; // eax
  unsigned int v33; // esi
  int pbSecret; // [rsp+20h] [rbp-50h]
  int pbSecreta; // [rsp+20h] [rbp-50h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+50h] [rbp-20h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+58h] [rbp-18h] BYREF
  char v40; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  ULONG pbOutput; // [rsp+B0h] [rbp+40h] BYREF
  unsigned int *v43; // [rsp+B8h] [rbp+48h]
  ULONG pcbResult; // [rsp+C8h] [rbp+58h] BYREF

  v43 = a2;
  v4 = a2;
  string = 0;
  v6 = 0;
  if ( WindowsCreateString(&word_1801330B0, 0, &string) >= 0 )
  {
    v6 = string;
    WindowsDeleteString(0);
  }
  if ( *a1 )
  {
    if ( v6 )
    {
      WindowsDeleteString(v6);
      v6 = 0;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
    if ( StringRawBuffer )
    {
      string = 0;
      v8 = -1;
      do
        ++v8;
      while ( StringRawBuffer[v8] );
      if ( v8 <= 0xFFFFFFFF && WindowsCreateString(StringRawBuffer, v8, &string) >= 0 )
      {
        v9 = v6;
        v6 = string;
        WindowsDeleteString(v9);
      }
    }
    v10 = (WCHAR *)WindowsGetStringRawBuffer(v6, 0);
    CharLowerW(v10);
  }
  p_hHash = &hHash;
  hHash = 0;
  phHash = 0;
  v40 = 1;
  v11 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0);
  if ( v40 )
  {
    v12 = p_hHash;
    v13 = phHash;
    v14 = *p_hHash;
    if ( *p_hHash )
    {
      LastError = GetLastError();
      BCryptDestroyHash(v14);
      SetLastError(LastError);
    }
    *v12 = v13;
    v4 = v43;
  }
  if ( v11 < 0 )
  {
    v30 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x13A,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\utils.cpp",
            (const char *)(unsigned int)v11,
            pbSecret);
    v28 = hHash;
    v27 = v30;
    if ( !hHash )
      goto LABEL_44;
    goto LABEL_43;
  }
  StringLen = WindowsGetStringLen(v6);
  if ( StringLen + 1 < StringLen )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13D,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\utils.cpp",
      (const char *)0x80070216LL,
      pbSecret);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( v6 )
    {
      WindowsDeleteString(v6);
      return 2147942934LL;
    }
    return 2147942934LL;
  }
  v16 = 2LL * (StringLen + 1);
  if ( v16 > 0xFFFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\utils.cpp",
      (const char *)0x80070216LL,
      pbSecret);
    if ( hHash )
      BCryptDestroyHash(hHash);
    if ( v6 )
      WindowsDeleteString(v6);
    return 2147942934LL;
  }
  v17 = (UCHAR *)WindowsGetStringRawBuffer(v6, 0);
  v18 = BCryptHashData(hHash, v17, v16, 0);
  if ( v18 < 0 )
  {
    v31 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x146,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\utils.cpp",
            (const char *)(unsigned int)v18,
            pbSecret);
    v28 = hHash;
    v27 = v31;
    if ( !hHash )
      goto LABEL_44;
    goto LABEL_43;
  }
  pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hHash, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
  {
    v32 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\utils.cpp",
            (const char *)(unsigned int)Property,
            pbSecreta);
    v28 = hHash;
    v27 = v32;
    if ( !hHash )
      goto LABEL_44;
    goto LABEL_43;
  }
  v20 = (UCHAR *)LocalAlloc(0x40u, pbOutput);
  v21 = v20;
  if ( v20 )
  {
    v22 = BCryptFinishHash(hHash, v20, pbOutput, 0);
    if ( v22 < 0 )
    {
      v33 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x161,
              (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\utils.cpp",
              (const char *)(unsigned int)v22,
              pbSecreta);
      LocalFree(v21);
      if ( hHash )
        BCryptDestroyHash(hHash);
      if ( v6 )
        WindowsDeleteString(v6);
      return v33;
    }
    else
    {
      v23 = hHash;
      v24 = pbOutput;
      *a3 = v21;
      *v4 = v24;
      if ( v23 )
        BCryptDestroyHash(v23);
      if ( v6 )
        WindowsDeleteString(v6);
      return 0;
    }
  }
  v26 = GetLastError();
  v27 = v26;
  if ( v26 > 0 )
    v27 = (unsigned __int16)v26 | 0x80070000;
  v28 = hHash;
  if ( hHash )
LABEL_43:
    BCryptDestroyHash(v28);
LABEL_44:
  if ( v6 )
    WindowsDeleteString(v6);
  return v27;
}

```

## disassembly

```asm
0x180036c10  mov     [rsp-38h+arg_10], rbx
0x180036c15  mov     [rsp-38h+arg_8], rdx
0x180036c1a  push    rbp
0x180036c1b  push    rsi
0x180036c1c  push    rdi
0x180036c1d  push    r12
0x180036c1f  push    r13
0x180036c21  push    r14
0x180036c23  push    r15
0x180036c25  mov     rbp, rsp
0x180036c28  sub     rsp, 70h
0x180036c2c  mov     r13, r8
0x180036c2f  mov     rsi, rdx
0x180036c32  mov     rdi, rcx
0x180036c35  lea     r8, [rbp+string]; string
0x180036c39  xor     r14d, r14d
0x180036c3c  lea     rcx, word_1801330B0; sourceString
0x180036c43  xor     edx, edx; length
0x180036c45  mov     [rbp+string], r14
0x180036c49  mov     ebx, r14d
0x180036c4c  call    cs:__imp_WindowsCreateString
0x180036c52  test    eax, eax
0x180036c54  js      short loc_180036C62
0x180036c56  mov     rbx, [rbp+string]
0x180036c5a  xor     ecx, ecx; string
0x180036c5c  call    cs:__imp_WindowsDeleteString
0x180036c62  mov     r15d, 0FFFFFFFFh
0x180036c68  cmp     [rdi], r14
0x180036c6b  jz      short loc_180036CE1
0x180036c6d  test    rbx, rbx
0x180036c70  jz      short loc_180036C7E
0x180036c72  mov     rcx, rbx; string
0x180036c75  call    cs:__imp_WindowsDeleteString
0x180036c7b  mov     rbx, r14
0x180036c7e  mov     rcx, [rdi]; string
0x180036c81  xor     edx, edx; length
0x180036c83  call    cs:__imp_WindowsGetStringRawBuffer
0x180036c89  test    rax, rax
0x180036c8c  jz      short loc_180036CCD
0x180036c8e  mov     [rbp+string], r14
0x180036c92  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180036c99  nop     dword ptr [rax+00000000h]
0x180036ca0  inc     rdx; length
0x180036ca3  cmp     [rax+rdx*2], r14w
0x180036ca8  jnz     short loc_180036CA0
0x180036caa  cmp     rdx, r15
0x180036cad  ja      short loc_180036CCD
0x180036caf  lea     r8, [rbp+string]; string
0x180036cb3  mov     rcx, rax; sourceString
0x180036cb6  call    cs:__imp_WindowsCreateString
0x180036cbc  test    eax, eax
0x180036cbe  js      short loc_180036CCD
0x180036cc0  mov     rcx, rbx; string
0x180036cc3  mov     rbx, [rbp+string]
0x180036cc7  call    cs:__imp_WindowsDeleteString
0x180036ccd  xor     edx, edx; length
0x180036ccf  mov     rcx, rbx; string
0x180036cd2  call    cs:__imp_WindowsGetStringRawBuffer
0x180036cd8  mov     rcx, rax; lpsz
0x180036cdb  call    cs:__imp_CharLowerW
0x180036ce1  lea     rax, [rbp+hHash]
0x180036ce5  mov     [rsp+70h+dwFlags], r14d; dwFlags
0x180036cea  mov     [rsp+70h+cbSecret], r14d; cbSecret
0x180036cef  lea     rdx, [rbp+phHash]; phHash
0x180036cf3  xor     r9d, r9d; cbHashObject
0x180036cf6  mov     [rbp+var_20], rax
0x180036cfa  xor     r8d, r8d; pbHashObject
0x180036cfd  mov     [rsp+70h+pbSecret], r14; int
0x180036d02  mov     ecx, 31h ; '1'; hAlgorithm
0x180036d07  mov     [rbp+hHash], r14
0x180036d0b  mov     [rbp+phHash], r14
0x180036d0f  mov     [rbp+var_10], 1
0x180036d13  call    cs:__imp_BCryptCreateHash
0x180036d19  mov     r12d, eax
0x180036d1c  cmp     [rbp+var_10], r14b
0x180036d20  jz      short loc_180036D46
0x180036d22  mov     rsi, [rbp+var_20]
0x180036d26  mov     r14, [rbp+phHash]
0x180036d2a  mov     r15, [rsi]
0x180036d2d  test    r15, r15
0x180036d30  jnz     loc_180036EE5
0x180036d36  mov     [rsi], r14
0x180036d39  mov     r15d, 0FFFFFFFFh
0x180036d3f  mov     rsi, [rbp+arg_8]
0x180036d43  xor     r14d, r14d
0x180036d46  test    r12d, r12d
0x180036d49  js      loc_180036F03
0x180036d4f  mov     rcx, rbx; string
0x180036d52  call    cs:__imp_WindowsGetStringLen
0x180036d58  lea     ecx, [rax+1]
0x180036d5b  cmp     ecx, eax
0x180036d5d  jb      loc_180036E83
0x180036d63  mov     edi, ecx
0x180036d65  add     rdi, rdi
0x180036d68  cmp     rdi, r15
0x180036d6b  ja      loc_180036E46
0x180036d71  xor     edx, edx; length
0x180036d73  mov     rcx, rbx; string
0x180036d76  call    cs:__imp_WindowsGetStringRawBuffer
0x180036d7c  mov     rcx, [rbp+hHash]; hHash
0x180036d80  xor     r9d, r9d; dwFlags
0x180036d83  mov     rdx, rax; pbInput
0x180036d86  mov     r8d, edi; cbInput
0x180036d89  call    cs:__imp_BCryptHashData
0x180036d8f  test    eax, eax
0x180036d91  js      loc_180036F4C
0x180036d97  mov     rcx, [rbp+hHash]; hObject
0x180036d9b  lea     rax, [rbp+pcbResult]
0x180036d9f  mov     [rsp+70h+cbSecret], r14d; dwFlags
0x180036da4  lea     r8, [rbp+pbOutput]; pbOutput
0x180036da8  mov     r9d, 4; cbOutput
0x180036dae  mov     [rsp+70h+pbSecret], rax; int
0x180036db3  lea     rdx, pszProperty; "HashDigestLength"
0x180036dba  mov     [rbp+pbOutput], r14d
0x180036dbe  mov     [rbp+pcbResult], r14d
0x180036dc2  call    cs:__imp_BCryptGetProperty
0x180036dc8  test    eax, eax
0x180036dca  js      loc_180036F71
0x180036dd0  mov     edx, [rbp+pbOutput]; uBytes
0x180036dd3  mov     ecx, 40h ; '@'; uFlags
0x180036dd8  call    cs:__imp_LocalAlloc
0x180036dde  mov     rdi, rax
0x180036de1  test    rax, rax
0x180036de4  jz      loc_180036EC5
0x180036dea  mov     r8d, [rbp+pbOutput]; cbOutput
0x180036dee  xor     r9d, r9d; dwFlags
0x180036df1  mov     rcx, [rbp+hHash]; hHash
0x180036df5  mov     rdx, rax; pbOutput
0x180036df8  call    cs:__imp_BCryptFinishHash
0x180036dfe  test    eax, eax
0x180036e00  js      loc_180036F96
0x180036e06  mov     rcx, [rbp+hHash]; hHash
0x180036e0a  mov     eax, [rbp+pbOutput]
0x180036e0d  mov     [r13+0], rdi
0x180036e11  mov     [rsi], eax
0x180036e13  test    rcx, rcx
0x180036e16  jz      short loc_180036E1E
0x180036e18  call    cs:__imp_BCryptDestroyHash
0x180036e1e  test    rbx, rbx
0x180036e21  jz      short loc_180036E2C
0x180036e23  mov     rcx, rbx; string
0x180036e26  call    cs:__imp_WindowsDeleteString
0x180036e2c  xor     eax, eax
0x180036e2e  mov     rbx, [rsp+70h+arg_10]
0x180036e36  add     rsp, 70h
0x180036e3a  pop     r15
0x180036e3c  pop     r14
0x180036e3e  pop     r13
0x180036e40  pop     r12
0x180036e42  pop     rdi
0x180036e43  pop     rsi
0x180036e44  pop     rbp
0x180036e45  retn
0x180036e46  mov     rcx, [rbp+38h]; this
0x180036e4a  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180036e51  mov     r9d, 80070216h; char *
0x180036e57  mov     edx, 13Eh; void *
0x180036e5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e61  mov     rcx, [rbp+hHash]; hHash
0x180036e65  test    rcx, rcx
0x180036e68  jnz     loc_180036F41
0x180036e6e  test    rbx, rbx
0x180036e71  jz      short loc_180036E7C
0x180036e73  mov     rcx, rbx; string
0x180036e76  call    cs:__imp_WindowsDeleteString
0x180036e7c  mov     eax, 80070216h
0x180036e81  jmp     short loc_180036E2E
0x180036e83  mov     rcx, [rbp+38h]; this
0x180036e87  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180036e8e  mov     r9d, 80070216h; char *
0x180036e94  mov     edx, 13Dh; void *
0x180036e99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036e9e  mov     rcx, [rbp+hHash]; hHash
0x180036ea2  test    rcx, rcx
0x180036ea5  jz      short loc_180036EAD
0x180036ea7  call    cs:__imp_BCryptDestroyHash
0x180036ead  test    rbx, rbx
0x180036eb0  jz      short loc_180036E7C
0x180036eb2  mov     rcx, rbx; string
0x180036eb5  call    cs:__imp_WindowsDeleteString
0x180036ebb  mov     eax, 80070216h
0x180036ec0  jmp     loc_180036E2E
0x180036ec5  call    cs:__imp_GetLastError
0x180036ecb  mov     edi, eax
0x180036ecd  test    eax, eax
0x180036ecf  jle     short loc_180036EDA
0x180036ed1  movzx   edi, ax
0x180036ed4  or      edi, 80070000h
0x180036eda  mov     rcx, [rbp+hHash]
0x180036ede  test    rcx, rcx
0x180036ee1  jnz     short loc_180036F26
0x180036ee3  jmp     short loc_180036F2C
0x180036ee5  call    cs:__imp_GetLastError
0x180036eeb  mov     rcx, r15; hHash
0x180036eee  mov     edi, eax
0x180036ef0  call    cs:__imp_BCryptDestroyHash
0x180036ef6  mov     ecx, edi; dwErrCode
0x180036ef8  call    cs:__imp_SetLastError
0x180036efe  jmp     loc_180036D36
0x180036f03  mov     rcx, [rbp+38h]; this
0x180036f07  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180036f0e  mov     r9d, r12d; char *
0x180036f11  mov     edx, 13Ah; void *
0x180036f16  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036f1b  mov     rcx, [rbp+hHash]; hHash
0x180036f1f  mov     edi, eax
0x180036f21  test    rcx, rcx
0x180036f24  jz      short loc_180036F2C
0x180036f26  call    cs:__imp_BCryptDestroyHash
0x180036f2c  test    rbx, rbx
0x180036f2f  jz      short loc_180036F3A
0x180036f31  mov     rcx, rbx; string
0x180036f34  call    cs:__imp_WindowsDeleteString
0x180036f3a  mov     eax, edi
0x180036f3c  jmp     loc_180036E2E
0x180036f41  call    cs:__imp_BCryptDestroyHash
0x180036f47  jmp     loc_180036E6E
0x180036f4c  mov     rcx, [rbp+38h]; this
0x180036f50  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180036f57  mov     r9d, eax; char *
0x180036f5a  mov     edx, 146h; void *
0x180036f5f  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036f64  mov     rcx, [rbp+hHash]
0x180036f68  mov     edi, eax
0x180036f6a  test    rcx, rcx
0x180036f6d  jz      short loc_180036F2C
0x180036f6f  jmp     short loc_180036F26
0x180036f71  mov     rcx, [rbp+38h]; this
0x180036f75  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180036f7c  mov     r9d, eax; char *
0x180036f7f  mov     edx, 158h; void *
0x180036f84  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036f89  mov     rcx, [rbp+hHash]
0x180036f8d  mov     edi, eax
0x180036f8f  test    rcx, rcx
0x180036f92  jz      short loc_180036F2C
0x180036f94  jmp     short loc_180036F26
0x180036f96  mov     rcx, [rbp+38h]; this
0x180036f9a  lea     r8, aOnecoreDsSecur_35; "onecore\\ds\\security\\tokenbroker\\dat"...
0x180036fa1  mov     r9d, eax; char *
0x180036fa4  mov     edx, 161h; void *
0x180036fa9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180036fae  mov     rcx, rdi; hMem
0x180036fb1  mov     esi, eax
0x180036fb3  call    cs:__imp_LocalFree
0x180036fb9  mov     rcx, [rbp+hHash]; hHash
0x180036fbd  test    rcx, rcx
0x180036fc0  jz      short loc_180036FC8
0x180036fc2  call    cs:__imp_BCryptDestroyHash
0x180036fc8  test    rbx, rbx
0x180036fcb  jz      short loc_180036FD6
0x180036fcd  mov     rcx, rbx; string
0x180036fd0  call    cs:__imp_WindowsDeleteString
0x180036fd6  mov     eax, esi
0x180036fd8  jmp     loc_180036E2E
```
