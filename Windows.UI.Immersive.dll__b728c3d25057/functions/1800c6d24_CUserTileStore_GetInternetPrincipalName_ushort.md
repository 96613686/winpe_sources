# CUserTileStore::_GetInternetPrincipalName(ushort * *)

- ea: `0x1800c6d24`
- end: `0x1800c6ec5`
- name: `?_GetInternetPrincipalName@CUserTileStore@@AEAAJPEAPEAG@Z`
- size: `417`
- prototype: `int(CUserTileStore *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006610`

## callees

- `0x18000684c`
- `0x180030ea4`
- `0x18003aa84`
- `0x1800c6d24`
- `0x1800c6ecc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6d60`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c6d60`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c6d48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c6d48`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c6d87`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800c6d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c6d78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800c6d78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6eb2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c6eb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c6ea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800c6ea8`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800c6e78`
- `api-ms-win-security-base-l1-1-0!GetSidIdentifierAuthority` at `0x1800c6e78`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c6de0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c6e41`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c6de0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c6e41`

## pseudocode

```c
__int64 __fastcall CUserTileStore::_GetInternetPrincipalName(CUserTileStore *this, unsigned __int16 **a2)
{
  HANDLE CurrentThread; // rax
  CUserTileStore *v4; // rcx
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  CUserTileStore *v7; // rcx
  void *v8; // rcx
  unsigned int *v9; // rsi
  unsigned int i; // edi
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  unsigned __int64 v12; // rcx
  CUserTileStore *TokenInformationLength; // [rsp+60h] [rbp+30h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+38h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp+40h] BYREF

  TokenInformationLength = this;
  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_4;
  Error = ResultFromKnownLastError();
  if ( Error != -2147023888 )
    goto LABEL_6;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
LABEL_4:
    Error = 0;
  else
    Error = ResultFromKnownLastError();
LABEL_6:
  if ( Error >= 0 )
  {
    if ( CUserTileStore::_IsDomainUser(v4) )
    {
      LODWORD(TokenInformationLength) = 0;
      if ( GetTokenInformation(TokenHandle, TokenGroups, 0, 0, (PDWORD)&TokenInformationLength) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error == -2147024774 )
        {
          TokenInformation = 0;
          Error = CTLocalAllocPolicy::Alloc(v8, 0x40u, (unsigned int)TokenInformationLength, &TokenInformation);
          if ( Error >= 0 )
          {
            v9 = (unsigned int *)TokenInformation;
            if ( GetTokenInformation(
                   TokenHandle,
                   TokenGroups,
                   TokenInformation,
                   (DWORD)TokenInformationLength,
                   (PDWORD)&TokenInformationLength)
              || (Error = ResultFromKnownLastError(), Error >= 0) )
            {
              Error = -2147467259;
              LODWORD(TokenInformation) = 0;
              WORD2(TokenInformation) = 2816;
              for ( i = 0; i < *v9; ++i )
              {
                SidIdentifierAuthority = GetSidIdentifierAuthority(*(PSID *)&v9[4 * i + 2]);
                v12 = (unsigned int)(*(_DWORD *)SidIdentifierAuthority->Value - (_DWORD)TokenInformation);
                if ( *(_DWORD *)SidIdentifierAuthority->Value == (_DWORD)TokenInformation )
                  v12 = *(unsigned __int16 *)&SidIdentifierAuthority->Value[4] - (unsigned int)WORD2(TokenInformation);
                if ( !(_DWORD)v12 )
                {
                  Error = CUserTileStore::_GetInternetPrincipalNameFromUserToken((CUserTileStore *)v12, TokenHandle, a2);
                  break;
                }
              }
            }
            LocalFree(v9);
          }
        }
      }
    }
    else
    {
      Error = CUserTileStore::_GetInternetPrincipalNameFromUserToken(v7, TokenHandle, a2);
    }
    CloseHandle(TokenHandle);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800c6d24  mov     [rsp-28h+TokenInformationLength], rcx
0x1800c6d29  push    rbp
0x1800c6d2a  push    rbx
0x1800c6d2b  push    rsi
0x1800c6d2c  push    rdi
0x1800c6d2d  push    r14
0x1800c6d2f  mov     rbp, rsp
0x1800c6d32  sub     rsp, 30h
0x1800c6d36  mov     r14, rdx
0x1800c6d39  mov     qword ptr [rdx], 0
0x1800c6d40  mov     [rbp+TokenHandle], 0
0x1800c6d48  call    cs:__imp_GetCurrentThread
0x1800c6d4e  mov     edi, 8
0x1800c6d53  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800c6d57  mov     rcx, rax; ThreadHandle
0x1800c6d5a  mov     edx, edi; DesiredAccess
0x1800c6d5c  lea     r8d, [rdi-7]; OpenAsSelf
0x1800c6d60  call    cs:__imp_OpenThreadToken
0x1800c6d66  test    eax, eax
0x1800c6d68  jnz     short loc_1800C6D91
0x1800c6d6a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c6d6f  mov     ebx, eax
0x1800c6d71  cmp     eax, 800703F0h
0x1800c6d76  jnz     short loc_1800C6D9C
0x1800c6d78  call    cs:__imp_GetCurrentProcess
0x1800c6d7e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1800c6d82  mov     edx, edi; DesiredAccess
0x1800c6d84  mov     rcx, rax; ProcessHandle
0x1800c6d87  call    cs:__imp_OpenProcessToken
0x1800c6d8d  test    eax, eax
0x1800c6d8f  jz      short loc_1800C6D95
0x1800c6d91  xor     ebx, ebx
0x1800c6d93  jmp     short loc_1800C6D9C
0x1800c6d95  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c6d9a  mov     ebx, eax
0x1800c6d9c  test    ebx, ebx
0x1800c6d9e  js      loc_1800C6EB8
0x1800c6da4  call    ?_IsDomainUser@CUserTileStore@@AEAA_NXZ; CUserTileStore::_IsDomainUser(void)
0x1800c6da9  test    al, al
0x1800c6dab  jnz     short loc_1800C6DC0
0x1800c6dad  mov     rdx, [rbp+TokenHandle]; void *
0x1800c6db1  mov     r8, r14; unsigned __int16 **
0x1800c6db4  call    ?_GetInternetPrincipalNameFromUserToken@CUserTileStore@@AEAAJPEAXPEAPEAG@Z; CUserTileStore::_GetInternetPrincipalNameFromUserToken(void *,ushort * *)
0x1800c6db9  mov     ebx, eax
0x1800c6dbb  jmp     loc_1800C6EAE
0x1800c6dc0  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c6dc4  lea     rax, [rbp+TokenInformationLength]
0x1800c6dc8  xor     r9d, r9d; TokenInformationLength
0x1800c6dcb  mov     dword ptr [rbp+TokenInformationLength], 0
0x1800c6dd2  xor     r8d, r8d; TokenInformation
0x1800c6dd5  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800c6dda  lea     edi, [r9+2]
0x1800c6dde  mov     edx, edi; TokenInformationClass
0x1800c6de0  call    cs:__imp_GetTokenInformation
0x1800c6de6  test    eax, eax
0x1800c6de8  jz      short loc_1800C6DF1
0x1800c6dea  xor     ebx, ebx
0x1800c6dec  jmp     loc_1800C6EAE
0x1800c6df1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c6df6  mov     ebx, eax
0x1800c6df8  cmp     eax, 8007007Ah
0x1800c6dfd  jnz     loc_1800C6EAE
0x1800c6e03  mov     r8d, dword ptr [rbp+TokenInformationLength]; unsigned __int64
0x1800c6e07  lea     r9, [rbp+TokenInformation]; void **
0x1800c6e0b  mov     edx, 40h ; '@'; unsigned int
0x1800c6e10  mov     [rbp+TokenInformation], 0
0x1800c6e18  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800c6e1d  mov     ebx, eax
0x1800c6e1f  test    eax, eax
0x1800c6e21  js      loc_1800C6EAE
0x1800c6e27  mov     rsi, [rbp+TokenInformation]
0x1800c6e2b  lea     rax, [rbp+TokenInformationLength]
0x1800c6e2f  mov     r9d, dword ptr [rbp+TokenInformationLength]; TokenInformationLength
0x1800c6e33  mov     r8, rsi; TokenInformation
0x1800c6e36  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800c6e3a  mov     edx, edi; TokenInformationClass
0x1800c6e3c  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x1800c6e41  call    cs:__imp_GetTokenInformation
0x1800c6e47  test    eax, eax
0x1800c6e49  jnz     short loc_1800C6E56
0x1800c6e4b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c6e50  mov     ebx, eax
0x1800c6e52  test    eax, eax
0x1800c6e54  js      short loc_1800C6EA5
0x1800c6e56  mov     ebx, 80004005h
0x1800c6e5b  mov     dword ptr [rbp+TokenInformation], 0
0x1800c6e62  mov     word ptr [rbp+TokenInformation+4], 0B00h
0x1800c6e68  xor     edi, edi
0x1800c6e6a  cmp     edi, [rsi]
0x1800c6e6c  jnb     short loc_1800C6EA5
0x1800c6e6e  mov     ecx, edi
0x1800c6e70  add     rcx, rcx
0x1800c6e73  mov     rcx, [rsi+rcx*8+8]; pSid
0x1800c6e78  call    cs:__imp_GetSidIdentifierAuthority
0x1800c6e7e  mov     ecx, [rax]
0x1800c6e80  sub     ecx, dword ptr [rbp+TokenInformation]
0x1800c6e83  jnz     short loc_1800C6E8F
0x1800c6e85  movzx   ecx, word ptr [rax+4]
0x1800c6e89  movzx   eax, word ptr [rbp+TokenInformation+4]
0x1800c6e8d  sub     ecx, eax; this
0x1800c6e8f  test    ecx, ecx
0x1800c6e91  jz      short loc_1800C6E97
0x1800c6e93  inc     edi
0x1800c6e95  jmp     short loc_1800C6E6A
0x1800c6e97  mov     rdx, [rbp+TokenHandle]; void *
0x1800c6e9b  mov     r8, r14; unsigned __int16 **
0x1800c6e9e  call    ?_GetInternetPrincipalNameFromUserToken@CUserTileStore@@AEAAJPEAXPEAPEAG@Z; CUserTileStore::_GetInternetPrincipalNameFromUserToken(void *,ushort * *)
0x1800c6ea3  mov     ebx, eax
0x1800c6ea5  mov     rcx, rsi; hMem
0x1800c6ea8  call    cs:__imp_LocalFree
0x1800c6eae  mov     rcx, [rbp+TokenHandle]; hObject
0x1800c6eb2  call    cs:__imp_CloseHandle
0x1800c6eb8  mov     eax, ebx
0x1800c6eba  add     rsp, 30h
0x1800c6ebe  pop     r14
0x1800c6ec0  pop     rdi
0x1800c6ec1  pop     rsi
0x1800c6ec2  pop     rbx
0x1800c6ec3  pop     rbp
0x1800c6ec4  retn
```
