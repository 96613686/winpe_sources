# UtilGetTokenIntegrityRid(void *,ulong *)

- ea: `0x140011c28`
- end: `0x140011d5b`
- name: `?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z`
- size: `307`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140011714`

## callees

- `0x1400024b4`
- `0x140002d74`
- `0x140011c28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011d2d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140011cfd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140011cfd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011c68`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011ccd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011c68`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011ccd`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140011d11`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140011d11`

## pseudocode

```c
__int64 __fastcall UtilGetTokenIntegrityRid(HANDLE TokenHandle, unsigned int *a2)
{
  unsigned int v4; // ebx
  PSID *v5; // rdi
  signed int v6; // eax
  PUCHAR SidSubAuthorityCount; // rax
  signed int LastError; // eax
  DWORD TokenInformationLength; // [rsp+48h] [rbp+10h] BYREF

  if ( a2 )
  {
    TokenInformationLength = 0;
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v5 = (PSID *)operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
      {
        if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
        {
          SidSubAuthorityCount = GetSidSubAuthorityCount(*v5);
          *a2 = *GetSidSubAuthority(*v5, (unsigned int)*SidSubAuthorityCount - 1);
          v4 = 0;
        }
        else
        {
          v6 = GetLastError();
          v4 = v6;
          if ( v6 > 0 )
            v4 = (unsigned __int16)v6 | 0x80070000;
        }
        operator delete(v5);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x140011c28  mov     [rsp+arg_0], rbx
0x140011c2d  mov     [rsp+arg_10], rsi
0x140011c32  push    rdi
0x140011c33  sub     rsp, 30h
0x140011c37  mov     rbx, rdx
0x140011c3a  mov     rsi, rcx
0x140011c3d  test    rdx, rdx
0x140011c40  jnz     short loc_140011C4C
0x140011c42  mov     ebx, 80070057h
0x140011c47  jmp     loc_140011D48
0x140011c4c  xor     r9d, r9d; TokenInformationLength
0x140011c4f  mov     [rsp+38h+TokenInformationLength], 0
0x140011c57  lea     rax, [rsp+38h+TokenInformationLength]
0x140011c5c  xor     r8d, r8d; TokenInformation
0x140011c5f  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140011c64  lea     edx, [r9+19h]; TokenInformationClass
0x140011c68  call    cs:__imp_GetTokenInformation
0x140011c6f  nop     dword ptr [rax+rax+00h]
0x140011c74  test    eax, eax
0x140011c76  jnz     loc_140011D2D
0x140011c7c  call    cs:__imp_GetLastError
0x140011c83  nop     dword ptr [rax+rax+00h]
0x140011c88  cmp     eax, 7Ah ; 'z'
0x140011c8b  jnz     loc_140011D2D
0x140011c91  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x140011c95  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011c9c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140011ca1  mov     rdi, rax
0x140011ca4  test    rax, rax
0x140011ca7  jnz     short loc_140011CB3
0x140011ca9  mov     ebx, 8007000Eh
0x140011cae  jmp     loc_140011D48
0x140011cb3  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140011cb8  lea     rax, [rsp+38h+TokenInformationLength]
0x140011cbd  mov     r8, rdi; TokenInformation
0x140011cc0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140011cc5  mov     edx, 19h; TokenInformationClass
0x140011cca  mov     rcx, rsi; TokenHandle
0x140011ccd  call    cs:__imp_GetTokenInformation
0x140011cd4  nop     dword ptr [rax+rax+00h]
0x140011cd9  test    eax, eax
0x140011cdb  jnz     short loc_140011CFA
0x140011cdd  call    cs:__imp_GetLastError
0x140011ce4  nop     dword ptr [rax+rax+00h]
0x140011ce9  mov     ebx, eax
0x140011ceb  test    eax, eax
0x140011ced  jle     short loc_140011D23
0x140011cef  movzx   ebx, ax
0x140011cf2  or      ebx, 80070000h
0x140011cf8  jmp     short loc_140011D23
0x140011cfa  mov     rcx, [rdi]; pSid
0x140011cfd  call    cs:__imp_GetSidSubAuthorityCount
0x140011d04  nop     dword ptr [rax+rax+00h]
0x140011d09  mov     rcx, [rdi]; pSid
0x140011d0c  movzx   edx, byte ptr [rax]
0x140011d0f  dec     edx; nSubAuthority
0x140011d11  call    cs:__imp_GetSidSubAuthority
0x140011d18  nop     dword ptr [rax+rax+00h]
0x140011d1d  mov     edx, [rax]
0x140011d1f  mov     [rbx], edx
0x140011d21  xor     ebx, ebx
0x140011d23  mov     rcx, rdi; Block
0x140011d26  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140011d2b  jmp     short loc_140011D48
0x140011d2d  call    cs:__imp_GetLastError
0x140011d34  nop     dword ptr [rax+rax+00h]
0x140011d39  mov     ebx, eax
0x140011d3b  test    eax, eax
0x140011d3d  jle     short loc_140011D48
0x140011d3f  movzx   ebx, ax
0x140011d42  or      ebx, 80070000h
0x140011d48  mov     rsi, [rsp+38h+arg_10]
0x140011d4d  mov     eax, ebx
0x140011d4f  mov     rbx, [rsp+38h+arg_0]
0x140011d54  add     rsp, 30h
0x140011d58  pop     rdi
0x140011d59  retn
```
