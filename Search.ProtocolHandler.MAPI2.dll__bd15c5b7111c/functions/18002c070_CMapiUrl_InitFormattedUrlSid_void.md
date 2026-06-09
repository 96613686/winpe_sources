# CMapiUrl::InitFormattedUrlSid(void)

- ea: `0x18002c070`
- end: `0x18002c21c`
- name: `?InitFormattedUrlSid@CMapiUrl@@CAJXZ`
- size: `428`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012554`
- `0x180013c20`
- `0x18002c338`

## callees

- `0x18000b9f0`
- `0x18000ee48`
- `0x1800122d8`
- `0x18002c070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c1f7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002c1f7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c1ca`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002c1ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c204`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c204`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c08b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c08b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c0fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c0a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002c0a5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c0b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002c0b5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c14f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c14f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c1bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c1bf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c0f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c13a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c0f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002c13a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c175`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18002c175`

## pseudocode

```c
__int64 CMapiUrl::InitFormattedUrlSid(void)
{
  signed int Error; // ebx
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  void **v3; // rdi
  void *v4; // rcx
  LPWSTR TokenInformationLength; // [rsp+40h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+18h] BYREF

  Error = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&CMapiUrl::s_userSidLock);
  if ( *((_DWORD *)CMapiUrl::s_userSid - 4) )
    goto LABEL_21;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    Error = ResultFromLastError();
    if ( Error < 0 )
      goto LABEL_21;
  }
  if ( !TokenHandle )
    goto LABEL_21;
  LODWORD(TokenInformationLength) = 0;
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&TokenInformationLength);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v3 = (void **)malloc((unsigned int)TokenInformationLength);
    if ( !v3 )
    {
      Error = -2147024882;
      goto LABEL_12;
    }
    goto LABEL_10;
  }
  if ( LastError > 0 )
    Error = (unsigned __int16)LastError | 0x80070000;
  else
    Error = LastError;
  v3 = 0;
  if ( Error >= 0 )
  {
LABEL_10:
    if ( !GetTokenInformation(
            TokenHandle,
            TokenUser,
            v3,
            (DWORD)TokenInformationLength,
            (PDWORD)&TokenInformationLength) )
      Error = ResultFromLastError();
  }
LABEL_12:
  CloseHandle(TokenHandle);
  if ( Error < 0 )
  {
    if ( v3 )
LABEL_20:
      free(v3);
  }
  else if ( v3 )
  {
    v4 = *v3;
    TokenInformationLength = 0;
    if ( ConvertSidToStringSidW(v4, &TokenInformationLength) )
    {
      ATL::CSimpleStringT<wchar_t,0>::SetString(&CMapiUrl::s_userSid, L"{", 1);
      ATL::CSimpleStringT<wchar_t,0>::Append(&CMapiUrl::s_userSid, TokenInformationLength);
      ATL::CSimpleStringT<wchar_t,0>::Append(&CMapiUrl::s_userSid, L"}");
      LocalFree(TokenInformationLength);
    }
    else
    {
      Error = ResultFromLastError();
    }
    goto LABEL_20;
  }
LABEL_21:
  LeaveCriticalSection((LPCRITICAL_SECTION)&CMapiUrl::s_userSidLock);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002c070  mov     [rsp-8+arg_10], rbx
0x18002c075  mov     [rsp-8+arg_18], rdi
0x18002c07a  push    rbp
0x18002c07b  mov     rbp, rsp
0x18002c07e  sub     rsp, 30h
0x18002c082  lea     rcx, ?s_userSidLock@CMapiUrl@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x18002c089  xor     ebx, ebx
0x18002c08b  call    cs:__imp_EnterCriticalSection
0x18002c091  mov     rax, cs:?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x18002c098  cmp     [rax-10h], ebx
0x18002c09b  jnz     loc_18002C1FD
0x18002c0a1  mov     [rbp+TokenHandle], rbx
0x18002c0a5  call    cs:__imp_GetCurrentProcess
0x18002c0ab  mov     rcx, rax; ProcessHandle
0x18002c0ae  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002c0b2  lea     edx, [rbx+8]; DesiredAccess
0x18002c0b5  call    cs:__imp_OpenProcessToken
0x18002c0bb  test    eax, eax
0x18002c0bd  jnz     short loc_18002C0CE
0x18002c0bf  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002c0c4  mov     ebx, eax
0x18002c0c6  test    eax, eax
0x18002c0c8  js      loc_18002C1FD
0x18002c0ce  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002c0d2  test    rcx, rcx
0x18002c0d5  jz      loc_18002C1FD
0x18002c0db  xor     r9d, r9d; TokenInformationLength
0x18002c0de  mov     dword ptr [rbp+TokenInformationLength], 0
0x18002c0e5  lea     rax, [rbp+TokenInformationLength]
0x18002c0e9  xor     r8d, r8d; TokenInformation
0x18002c0ec  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002c0f1  lea     edx, [r9+1]; TokenInformationClass
0x18002c0f5  call    cs:__imp_GetTokenInformation
0x18002c0fb  call    cs:__imp_GetLastError
0x18002c101  cmp     eax, 7Ah ; 'z'
0x18002c104  jz      loc_18002C1C7
0x18002c10a  test    eax, eax
0x18002c10c  jg      short loc_18002C112
0x18002c10e  mov     ebx, eax
0x18002c110  jmp     short loc_18002C11B
0x18002c112  movzx   ebx, ax
0x18002c115  or      ebx, 80070000h
0x18002c11b  xor     edi, edi
0x18002c11d  test    ebx, ebx
0x18002c11f  js      short loc_18002C14B
0x18002c121  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x18002c125  lea     rax, [rbp+TokenInformationLength]
0x18002c129  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002c12d  mov     r8, rdi; TokenInformation
0x18002c130  mov     edx, 1; TokenInformationClass
0x18002c135  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18002c13a  call    cs:__imp_GetTokenInformation
0x18002c140  test    eax, eax
0x18002c142  jnz     short loc_18002C14B
0x18002c144  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002c149  mov     ebx, eax
0x18002c14b  mov     rcx, [rbp+TokenHandle]; hObject
0x18002c14f  call    cs:__imp_CloseHandle
0x18002c155  test    ebx, ebx
0x18002c157  js      loc_18002C1EF
0x18002c15d  test    rdi, rdi
0x18002c160  jz      loc_18002C1FD
0x18002c166  mov     rcx, [rdi]; Sid
0x18002c169  lea     rdx, [rbp+TokenInformationLength]; StringSid
0x18002c16d  mov     [rbp+TokenInformationLength], 0
0x18002c175  call    cs:__imp_ConvertSidToStringSidW
0x18002c17b  test    eax, eax
0x18002c17d  jz      short loc_18002C1E6
0x18002c17f  mov     r8d, 1
0x18002c185  lea     rdx, asc_180049374; "{"
0x18002c18c  lea     rcx, ?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x18002c193  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002c198  mov     rdx, [rbp+TokenInformationLength]
0x18002c19c  lea     rcx, ?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x18002c1a3  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x18002c1a8  lea     rdx, asc_180049370; "}"
0x18002c1af  lea     rcx, ?s_userSid@CMapiUrl@@0V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@A; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> CMapiUrl::s_userSid
0x18002c1b6  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x18002c1bb  mov     rcx, [rbp+TokenInformationLength]; hMem
0x18002c1bf  call    cs:__imp_LocalFree
0x18002c1c5  jmp     short loc_18002C1F4
0x18002c1c7  mov     ecx, dword ptr [rbp+TokenInformationLength]; Size
0x18002c1ca  call    cs:__imp_malloc
0x18002c1d0  mov     rdi, rax
0x18002c1d3  test    rax, rax
0x18002c1d6  jnz     loc_18002C121
0x18002c1dc  mov     ebx, 8007000Eh
0x18002c1e1  jmp     loc_18002C14B
0x18002c1e6  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002c1eb  mov     ebx, eax
0x18002c1ed  jmp     short loc_18002C1F4
0x18002c1ef  test    rdi, rdi
0x18002c1f2  jz      short loc_18002C1FD
0x18002c1f4  mov     rcx, rdi; Block
0x18002c1f7  call    cs:__imp_free
0x18002c1fd  lea     rcx, ?s_userSidLock@CMapiUrl@@0VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x18002c204  call    cs:__imp_LeaveCriticalSection
0x18002c20a  mov     rdi, [rsp+30h+arg_18]
0x18002c20f  mov     eax, ebx
0x18002c211  mov     rbx, [rsp+30h+arg_10]
0x18002c216  add     rsp, 30h
0x18002c21a  pop     rbp
0x18002c21b  retn
```
