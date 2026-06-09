# UtilGetTokenIntegrityRid(void *,ulong *)

- ea: `0x1400114c0`
- end: `0x1400115c5`
- name: `?UtilGetTokenIntegrityRid@@YAJPEAXPEAK@Z`
- size: `261`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140011010`

## callees

- `0x140002494`
- `0x140002d24`
- `0x1400114c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001150e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001159e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001150e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140011560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001159e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x14001157a`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x14001157a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011500`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011556`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011500`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011556`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140011588`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x140011588`

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
0x1400114c0  mov     [rsp+arg_0], rbx
0x1400114c5  mov     [rsp+arg_10], rsi
0x1400114ca  push    rdi
0x1400114cb  sub     rsp, 30h
0x1400114cf  mov     rbx, rdx
0x1400114d2  mov     rsi, rcx
0x1400114d5  test    rdx, rdx
0x1400114d8  jnz     short loc_1400114E4
0x1400114da  mov     ebx, 80070057h
0x1400114df  jmp     loc_1400115B3
0x1400114e4  xor     r9d, r9d; TokenInformationLength
0x1400114e7  mov     [rsp+38h+TokenInformationLength], 0
0x1400114ef  lea     rax, [rsp+38h+TokenInformationLength]
0x1400114f4  xor     r8d, r8d; TokenInformation
0x1400114f7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1400114fc  lea     edx, [r9+19h]; TokenInformationClass
0x140011500  call    cs:__imp_GetTokenInformation
0x140011506  test    eax, eax
0x140011508  jnz     loc_14001159E
0x14001150e  call    cs:__imp_GetLastError
0x140011514  cmp     eax, 7Ah ; 'z'
0x140011517  jnz     loc_14001159E
0x14001151d  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x140011521  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140011528  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001152d  mov     rdi, rax
0x140011530  test    rax, rax
0x140011533  jnz     short loc_14001153C
0x140011535  mov     ebx, 8007000Eh
0x14001153a  jmp     short loc_1400115B3
0x14001153c  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140011541  lea     rax, [rsp+38h+TokenInformationLength]
0x140011546  mov     r8, rdi; TokenInformation
0x140011549  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14001154e  mov     edx, 19h; TokenInformationClass
0x140011553  mov     rcx, rsi; TokenHandle
0x140011556  call    cs:__imp_GetTokenInformation
0x14001155c  test    eax, eax
0x14001155e  jnz     short loc_140011577
0x140011560  call    cs:__imp_GetLastError
0x140011566  mov     ebx, eax
0x140011568  test    eax, eax
0x14001156a  jle     short loc_140011594
0x14001156c  movzx   ebx, ax
0x14001156f  or      ebx, 80070000h
0x140011575  jmp     short loc_140011594
0x140011577  mov     rcx, [rdi]; pSid
0x14001157a  call    cs:__imp_GetSidSubAuthorityCount
0x140011580  mov     rcx, [rdi]; pSid
0x140011583  movzx   edx, byte ptr [rax]
0x140011586  dec     edx; nSubAuthority
0x140011588  call    cs:__imp_GetSidSubAuthority
0x14001158e  mov     edx, [rax]
0x140011590  mov     [rbx], edx
0x140011592  xor     ebx, ebx
0x140011594  mov     rcx, rdi; Block
0x140011597  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001159c  jmp     short loc_1400115B3
0x14001159e  call    cs:__imp_GetLastError
0x1400115a4  mov     ebx, eax
0x1400115a6  test    eax, eax
0x1400115a8  jle     short loc_1400115B3
0x1400115aa  movzx   ebx, ax
0x1400115ad  or      ebx, 80070000h
0x1400115b3  mov     rsi, [rsp+38h+arg_10]
0x1400115b8  mov     eax, ebx
0x1400115ba  mov     rbx, [rsp+38h+arg_0]
0x1400115bf  add     rsp, 30h
0x1400115c3  pop     rdi
0x1400115c4  retn
```
