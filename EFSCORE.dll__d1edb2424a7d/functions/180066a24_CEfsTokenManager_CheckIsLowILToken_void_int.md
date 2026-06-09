# CEfsTokenManager::CheckIsLowILToken(void *,int *)

- ea: `0x180066a24`
- end: `0x180066b85`
- name: `?CheckIsLowILToken@CEfsTokenManager@@SAKPEAXPEAH@Z`
- size: `353`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066970`
- `0x180067890`

## callees

- `0x18004a89c`
- `0x180063698`
- `0x180066a24`
- `0x180069c6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066a62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b03`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180066b1b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180066b1b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066a54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066af9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066a54`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180066af9`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180066b29`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180066b29`

## pseudocode

```c
__int64 __fastcall CEfsTokenManager::CheckIsLowILToken(HANDLE TokenHandle, int *a2)
{
  PSID *v2; // rdi
  DWORD LastError; // eax
  DWORD v6; // ebx
  PUCHAR SidSubAuthorityCount; // rax
  DWORD TokenInformationLength; // [rsp+60h] [rbp+18h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp+20h] BYREF

  v2 = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    v6 = 111;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 111, 29, 101);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 122 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 29, 92);
      return v6;
    }
    v6 = EfsxLibAllocZero(TokenInformationLength, &TokenInformation);
    if ( v6 )
    {
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, TokenInformationLength, 29, 108);
      v2 = (PSID *)TokenInformation;
    }
    else
    {
      v2 = (PSID *)TokenInformation;
      if ( GetTokenInformation(
             TokenHandle,
             TokenIntegrityLevel,
             TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        SidSubAuthorityCount = GetSidSubAuthorityCount(*v2);
        *a2 = *GetSidSubAuthority(*v2, (unsigned int)*SidSubAuthorityCount - 1) < 0x2000;
      }
      else
      {
        v6 = GetLastError();
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v6, 29, 116);
      }
    }
  }
  if ( v2 )
    EdppAuditSiteFree(v2);
  return v6;
}

```

## disassembly

```asm
0x180066a24  mov     rax, rsp
0x180066a27  mov     [rax+8], rbx
0x180066a2b  push    rsi
0x180066a2c  push    rdi
0x180066a2d  push    r14
0x180066a2f  sub     rsp, 30h
0x180066a33  xor     edi, edi
0x180066a35  mov     r14, rdx
0x180066a38  mov     [rax+20h], rdi
0x180066a3c  xor     r9d, r9d; TokenInformationLength
0x180066a3f  mov     [rax+18h], edi
0x180066a42  lea     rax, [rax+18h]
0x180066a46  xor     r8d, r8d; TokenInformation
0x180066a49  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180066a4e  lea     edx, [rdi+19h]; TokenInformationClass
0x180066a51  mov     rsi, rcx
0x180066a54  call    cs:__imp_GetTokenInformation
0x180066a5a  test    eax, eax
0x180066a5c  jnz     loc_180066B3F
0x180066a62  call    cs:__imp_GetLastError
0x180066a68  mov     ebx, eax
0x180066a6a  cmp     eax, 7Ah ; 'z'
0x180066a6d  jz      short loc_180066A96
0x180066a6f  mov     rcx, cs:g_hPublisher
0x180066a76  lea     r9d, [rdi+1Dh]
0x180066a7a  mov     r8d, eax
0x180066a7d  mov     dword ptr [rsp+48h+ReturnLength], 15Ch
0x180066a85  lea     rdx, EFS_API_ERROR
0x180066a8c  call    fnEfsLogTrace1
0x180066a91  jmp     loc_180066B75
0x180066a96  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x180066a9a  lea     rdx, [rsp+48h+TokenInformation]; void **
0x180066a9f  call    ?EfsxLibAllocZero@@YAK_KPEAPEAX@Z; EfsxLibAllocZero(unsigned __int64,void * *)
0x180066aa4  mov     ebx, eax
0x180066aa6  test    eax, eax
0x180066aa8  jz      short loc_180066ADA
0x180066aaa  mov     r8d, [rsp+48h+TokenInformationLength]
0x180066aaf  lea     rdx, EFS_ERROR_MEMORY
0x180066ab6  mov     rcx, cs:g_hPublisher
0x180066abd  mov     r9d, 1Dh
0x180066ac3  mov     dword ptr [rsp+48h+ReturnLength], 16Ch
0x180066acb  call    fnEfsLogTrace1
0x180066ad0  mov     rdi, [rsp+48h+TokenInformation]
0x180066ad5  jmp     loc_180066B68
0x180066ada  mov     rdi, [rsp+48h+TokenInformation]
0x180066adf  lea     rax, [rsp+48h+TokenInformationLength]
0x180066ae4  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180066ae9  mov     r8, rdi; TokenInformation
0x180066aec  mov     edx, 19h; TokenInformationClass
0x180066af1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180066af6  mov     rcx, rsi; TokenHandle
0x180066af9  call    cs:__imp_GetTokenInformation
0x180066aff  test    eax, eax
0x180066b01  jnz     short loc_180066B18
0x180066b03  call    cs:__imp_GetLastError
0x180066b09  mov     ebx, eax
0x180066b0b  mov     dword ptr [rsp+48h+ReturnLength], 174h
0x180066b13  mov     r8d, eax
0x180066b16  jmp     short loc_180066B4F
0x180066b18  mov     rcx, [rdi]; pSid
0x180066b1b  call    cs:__imp_GetSidSubAuthorityCount
0x180066b21  mov     rcx, [rdi]; pSid
0x180066b24  movzx   edx, byte ptr [rax]
0x180066b27  dec     edx; nSubAuthority
0x180066b29  call    cs:__imp_GetSidSubAuthority
0x180066b2f  xor     ecx, ecx
0x180066b31  cmp     dword ptr [rax], 2000h
0x180066b37  setb    cl
0x180066b3a  mov     [r14], ecx
0x180066b3d  jmp     short loc_180066B68
0x180066b3f  mov     ebx, 6Fh ; 'o'
0x180066b44  mov     dword ptr [rsp+48h+ReturnLength], 165h
0x180066b4c  mov     r8d, ebx
0x180066b4f  mov     rcx, cs:g_hPublisher
0x180066b56  lea     rdx, EFS_API_ERROR
0x180066b5d  mov     r9d, 1Dh
0x180066b63  call    fnEfsLogTrace1
0x180066b68  test    rdi, rdi
0x180066b6b  jz      short loc_180066B75
0x180066b6d  mov     rcx, rdi; void *
0x180066b70  call    ?EdppAuditSiteFree@@YAXPEAX@Z; EdppAuditSiteFree(void *)
0x180066b75  mov     eax, ebx
0x180066b77  mov     rbx, [rsp+48h+arg_0]
0x180066b7c  add     rsp, 30h
0x180066b80  pop     r14
0x180066b82  pop     rdi
0x180066b83  pop     rsi
0x180066b84  retn
```
