# GetLocalAccountNameFromToken

- ea: `0x1800a69f0`
- end: `0x1800a6b2c`
- name: `GetLocalAccountNameFromToken`
- size: `316`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004b854`

## callees

- `0x18000782c`
- `0x180007964`
- `0x18002db44`
- `0x180048304`
- `0x1800a6868`
- `0x1800a69f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6a56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6a56`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6a27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6ae2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6a27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800a6ae2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6aae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6b14`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6aae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6b14`

## string_xrefs

- `0x1800a6a40`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6a6a`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6af1`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalAccountNameFromToken(HANDLE TokenHandle, WCHAR **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  DWORD LastError; // eax
  PSID **unique_hlocal; // rax
  PSID *v9; // rbx
  HLOCAL v10; // rcx
  const char *v11; // r9
  unsigned int LocalAccountNameFromSid; // eax
  unsigned int v13; // edi
  unsigned int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  *a2 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    v4 = -2147418113;
    v5 = 1638;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
      (const char *)v4,
      ReturnLength);
    return v4;
  }
  LastError = GetLastError();
  if ( LastError != 122 && LastError )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x66A,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
             (const char *)LastError,
             ReturnLength);
  unique_hlocal = (PSID **)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, TokenInformationLength);
  v9 = *unique_hlocal;
  *unique_hlocal = 0;
  v10 = hMem;
  hMem = 0;
  if ( v10 )
    LocalFree(v10);
  if ( !v9 )
  {
    v4 = -2147024882;
    v5 = 1648;
    goto LABEL_3;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
    LocalAccountNameFromSid = GetLocalAccountNameFromSid(*v9, a2);
  else
    LocalAccountNameFromSid = wil::details::in1diag3::Return_GetLastError(
                                retaddr,
                                (void *)0x677,
                                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                                v11);
  v13 = LocalAccountNameFromSid;
  LocalFree(v9);
  return v13;
}

```

## disassembly

```asm
0x1800a69f0  mov     rax, rsp
0x1800a69f3  mov     [rax+8], rbx
0x1800a69f7  mov     [rax+20h], rsi
0x1800a69fb  push    rdi
0x1800a69fc  sub     rsp, 30h
0x1800a6a00  xor     r9d, r9d; TokenInformationLength
0x1800a6a03  mov     dword ptr [rax+10h], 0
0x1800a6a0a  mov     rdi, rdx
0x1800a6a0d  mov     qword ptr [rdx], 0
0x1800a6a14  lea     rax, [rax+10h]
0x1800a6a18  xor     r8d, r8d; TokenInformation
0x1800a6a1b  mov     rsi, rcx
0x1800a6a1e  mov     qword ptr [rsp+38h+ReturnLength], rax; unsigned int
0x1800a6a23  lea     edx, [r9+1]; TokenInformationClass
0x1800a6a27  call    cs:__imp_GetTokenInformation
0x1800a6a2d  test    eax, eax
0x1800a6a2f  jz      short loc_1800A6A56
0x1800a6a31  mov     ebx, 8000FFFFh
0x1800a6a36  mov     edx, 666h; void *
0x1800a6a3b  mov     rcx, [rsp+38h]; this
0x1800a6a40  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6a47  mov     r9d, ebx; char *
0x1800a6a4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6a4f  mov     eax, ebx
0x1800a6a51  jmp     loc_1800A6B1C
0x1800a6a56  call    cs:__imp_GetLastError
0x1800a6a5c  cmp     eax, 7Ah ; 'z'
0x1800a6a5f  jz      short loc_1800A6A83
0x1800a6a61  test    eax, eax
0x1800a6a63  jz      short loc_1800A6A83
0x1800a6a65  mov     rcx, [rsp+38h]; this
0x1800a6a6a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6a71  mov     r9d, eax; char *
0x1800a6a74  mov     edx, 66Ah; void *
0x1800a6a79  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a6a7e  jmp     loc_1800A6B1C
0x1800a6a83  mov     edx, [rsp+38h+TokenInformationLength]
0x1800a6a87  lea     rcx, [rsp+38h+hMem]
0x1800a6a8c  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800a6a91  mov     rbx, [rax]
0x1800a6a94  mov     qword ptr [rax], 0
0x1800a6a9b  mov     rcx, [rsp+38h+hMem]; hMem
0x1800a6aa0  mov     [rsp+38h+hMem], 0
0x1800a6aa9  test    rcx, rcx
0x1800a6aac  jz      short loc_1800A6AB4
0x1800a6aae  call    cs:__imp_LocalFree
0x1800a6ab4  test    rbx, rbx
0x1800a6ab7  jnz     short loc_1800A6AC8
0x1800a6ab9  mov     ebx, 8007000Eh
0x1800a6abe  mov     edx, 670h
0x1800a6ac3  jmp     loc_1800A6A3B
0x1800a6ac8  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800a6acd  lea     rax, [rsp+38h+TokenInformationLength]
0x1800a6ad2  mov     r8, rbx; TokenInformation
0x1800a6ad5  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800a6ada  mov     edx, 1; TokenInformationClass
0x1800a6adf  mov     rcx, rsi; TokenHandle
0x1800a6ae2  call    cs:__imp_GetTokenInformation
0x1800a6ae8  test    eax, eax
0x1800a6aea  jnz     short loc_1800A6B04
0x1800a6aec  mov     rcx, [rsp+38h]; this
0x1800a6af1  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6af8  mov     edx, 677h; void *
0x1800a6afd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6b02  jmp     short loc_1800A6B0F
0x1800a6b04  mov     rcx, [rbx]; Sid
0x1800a6b07  mov     rdx, rdi
0x1800a6b0a  call    GetLocalAccountNameFromSid
0x1800a6b0f  mov     rcx, rbx; hMem
0x1800a6b12  mov     edi, eax
0x1800a6b14  call    cs:__imp_LocalFree
0x1800a6b1a  mov     eax, edi
0x1800a6b1c  mov     rbx, [rsp+38h+arg_0]
0x1800a6b21  mov     rsi, [rsp+38h+arg_18]
0x1800a6b26  add     rsp, 30h
0x1800a6b2a  pop     rdi
0x1800a6b2b  retn
```
