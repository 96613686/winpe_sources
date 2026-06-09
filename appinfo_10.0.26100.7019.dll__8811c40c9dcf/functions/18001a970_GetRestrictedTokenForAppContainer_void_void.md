# GetRestrictedTokenForAppContainer(void *,void * *)

- ea: `0x18001a970`
- end: `0x18001ab7b`
- name: `?GetRestrictedTokenForAppContainer@@YAJPEAXPEAPEAX@Z`
- size: `523`
- prototype: `__int64 __fastcall(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002a750`

## callees

- `0x18001a970`
- `0x18001b0c4`
- `0x18001b8cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001aaf8`
- `api-ms-win-security-base-l1-1-0!CreateRestrictedToken` at `0x18001aaf8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a9a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001aa17`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001a9a4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001aa17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a9b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aa47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ab28`

## pseudocode

```c
signed int __fastcall GetRestrictedTokenForAppContainer(HANDLE ExistingTokenHandle, PHANDLE NewTokenHandle)
{
  unsigned int *v3; // rbx
  signed int result; // eax
  unsigned int v6; // edi
  unsigned __int64 v7; // rax
  struct _LUID_AND_ATTRIBUTES *v8; // rax
  DWORD v9; // r9d
  unsigned int v10; // edx
  struct _LUID_AND_ATTRIBUTES *PrivilegesToDelete; // rdi
  struct _LUID_AND_ATTRIBUTES *v12; // r8
  _DWORD *v13; // rcx
  DWORD v14; // eax
  unsigned int LastError; // esi
  DWORD TokenInformationLength; // [rsp+70h] [rbp+18h] BYREF

  TokenInformationLength = 0;
  v3 = 0;
  if ( GetTokenInformation(ExistingTokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) )
    goto LABEL_12;
  result = GetLastError();
  if ( result != 122 )
  {
    if ( result > 0 )
      return (unsigned __int16)result | 0xC0070000;
    return result;
  }
  v3 = (unsigned int *)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v3 )
    return -1073741801;
  if ( GetTokenInformation(ExistingTokenHandle, TokenPrivileges, v3, TokenInformationLength, &TokenInformationLength) )
  {
LABEL_12:
    v7 = 12LL * *v3;
    if ( !is_mul_ok(*v3, 0xCu) )
      v7 = -1;
    v8 = (struct _LUID_AND_ATTRIBUTES *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v9 = 0;
    v10 = 0;
    PrivilegesToDelete = v8;
    if ( *v3 )
    {
      v12 = v8;
      v13 = v3 + 1;
      do
      {
        if ( *v13 != 23 && *v13 != 33 || v13[1] )
        {
          ++v9;
          v14 = v13[2];
          v12->Luid = *(LUID *)v13;
          v12->Attributes = v14;
          ++v12;
        }
        ++v10;
        v13 += 3;
      }
      while ( v10 < *v3 );
    }
    if ( CreateRestrictedToken(ExistingTokenHandle, 0, 0, 0, v9, PrivilegesToDelete, 0, 0, NewTokenHandle) )
    {
      if ( PrivilegesToDelete )
        operator delete(PrivilegesToDelete);
      LastError = 0;
    }
    else
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      if ( PrivilegesToDelete )
        operator delete(PrivilegesToDelete);
    }
    operator delete(v3);
    return LastError;
  }
  else
  {
    if ( (int)GetLastError() > 0 )
      v6 = (unsigned __int16)GetLastError() | 0xC0070000;
    else
      v6 = GetLastError();
    operator delete(v3);
    return v6;
  }
}

```

## disassembly

```asm
0x18001a970  mov     rax, rsp
0x18001a973  mov     [rax+8], rbx
0x18001a977  mov     [rax+10h], rbp
0x18001a97b  mov     [rax+20h], rsi
0x18001a97f  push    rdi
0x18001a980  sub     rsp, 50h
0x18001a984  and     dword ptr [rax+18h], 0
0x18001a988  lea     rax, [rax+18h]
0x18001a98c  mov     rbp, rdx
0x18001a98f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001a994  xor     ebx, ebx
0x18001a996  xor     r9d, r9d; TokenInformationLength
0x18001a999  xor     r8d, r8d; TokenInformation
0x18001a99c  mov     rsi, rcx
0x18001a99f  lea     edi, [rbx+3]
0x18001a9a2  mov     edx, edi; TokenInformationClass
0x18001a9a4  call    cs:__imp_GetTokenInformation
0x18001a9ab  nop     dword ptr [rax+rax+00h]
0x18001a9b0  test    eax, eax
0x18001a9b2  jnz     loc_18001AA6B
0x18001a9b8  call    cs:__imp_GetLastError
0x18001a9bf  nop     dword ptr [rax+rax+00h]
0x18001a9c4  cmp     eax, 7Ah ; 'z'
0x18001a9c7  jz      short loc_18001A9DE
0x18001a9c9  test    eax, eax
0x18001a9cb  jle     loc_18001AB65
0x18001a9d1  movzx   eax, ax
0x18001a9d4  or      eax, 0C0070000h
0x18001a9d9  jmp     loc_18001AB65
0x18001a9de  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18001a9e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a9e9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a9ee  mov     rbx, rax
0x18001a9f1  test    rax, rax
0x18001a9f4  jnz     short loc_18001AA00
0x18001a9f6  mov     eax, 0C0000017h
0x18001a9fb  jmp     loc_18001AB65
0x18001aa00  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18001aa05  lea     rax, [rsp+58h+TokenInformationLength]
0x18001aa0a  mov     r8, rbx; TokenInformation
0x18001aa0d  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001aa12  mov     edx, edi; TokenInformationClass
0x18001aa14  mov     rcx, rsi; TokenHandle
0x18001aa17  call    cs:__imp_GetTokenInformation
0x18001aa1e  nop     dword ptr [rax+rax+00h]
0x18001aa23  test    eax, eax
0x18001aa25  jnz     short loc_18001AA6B
0x18001aa27  call    cs:__imp_GetLastError
0x18001aa2e  nop     dword ptr [rax+rax+00h]
0x18001aa33  test    eax, eax
0x18001aa35  jg      short loc_18001AA47
0x18001aa37  call    cs:__imp_GetLastError
0x18001aa3e  nop     dword ptr [rax+rax+00h]
0x18001aa43  mov     edi, eax
0x18001aa45  jmp     short loc_18001AA5C
0x18001aa47  call    cs:__imp_GetLastError
0x18001aa4e  nop     dword ptr [rax+rax+00h]
0x18001aa53  movzx   edi, ax
0x18001aa56  or      edi, 0C0070000h
0x18001aa5c  mov     rcx, rbx; Block
0x18001aa5f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001aa64  mov     eax, edi
0x18001aa66  jmp     loc_18001AB65
0x18001aa6b  mov     ecx, [rbx]
0x18001aa6d  mov     eax, 0Ch
0x18001aa72  mul     rcx
0x18001aa75  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001aa7c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001aa83  cmovo   rax, rcx
0x18001aa87  mov     rcx, rax; unsigned __int64
0x18001aa8a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001aa8f  xor     r9d, r9d
0x18001aa92  xor     edx, edx
0x18001aa94  mov     rdi, rax
0x18001aa97  cmp     [rbx], edx
0x18001aa99  jbe     short loc_18001AAD3
0x18001aa9b  mov     r8, rax
0x18001aa9e  lea     rcx, [rbx+4]
0x18001aaa2  cmp     dword ptr [rcx], 17h
0x18001aaa5  jz      short loc_18001AAAC
0x18001aaa7  cmp     dword ptr [rcx], 21h ; '!'
0x18001aaaa  jnz     short loc_18001AAB2
0x18001aaac  cmp     dword ptr [rcx+4], 0
0x18001aab0  jz      short loc_18001AAC9
0x18001aab2  movsd   xmm0, qword ptr [rcx]
0x18001aab6  inc     r9d
0x18001aab9  mov     eax, [rcx+8]
0x18001aabc  movsd   qword ptr [r8], xmm0
0x18001aac1  mov     [r8+8], eax
0x18001aac5  add     r8, 0Ch
0x18001aac9  inc     edx
0x18001aacb  add     rcx, 0Ch
0x18001aacf  cmp     edx, [rbx]
0x18001aad1  jb      short loc_18001AAA2
0x18001aad3  mov     [rsp+58h+NewTokenHandle], rbp; NewTokenHandle
0x18001aad8  xor     r8d, r8d; DisableSidCount
0x18001aadb  and     [rsp+58h+var_20], 0
0x18001aae1  xor     edx, edx; Flags
0x18001aae3  and     [rsp+58h+var_28], 0
0x18001aae8  mov     rcx, rsi; ExistingTokenHandle
0x18001aaeb  mov     [rsp+58h+PrivilegesToDelete], rdi; PrivilegesToDelete
0x18001aaf0  mov     dword ptr [rsp+58h+ReturnLength], r9d; DeletePrivilegeCount
0x18001aaf5  xor     r9d, r9d; SidsToDisable
0x18001aaf8  call    cs:__imp_CreateRestrictedToken
0x18001aaff  nop     dword ptr [rax+rax+00h]
0x18001ab04  test    eax, eax
0x18001ab06  jnz     short loc_18001AB4C
0x18001ab08  call    cs:__imp_GetLastError
0x18001ab0f  nop     dword ptr [rax+rax+00h]
0x18001ab14  test    eax, eax
0x18001ab16  jg      short loc_18001AB28
0x18001ab18  call    cs:__imp_GetLastError
0x18001ab1f  nop     dword ptr [rax+rax+00h]
0x18001ab24  mov     esi, eax
0x18001ab26  jmp     short loc_18001AB3D
0x18001ab28  call    cs:__imp_GetLastError
0x18001ab2f  nop     dword ptr [rax+rax+00h]
0x18001ab34  movzx   esi, ax
0x18001ab37  or      esi, 0C0070000h
0x18001ab3d  test    rdi, rdi
0x18001ab40  jz      short loc_18001AB5B
0x18001ab42  mov     rcx, rdi; Block
0x18001ab45  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ab4a  jmp     short loc_18001AB5B
0x18001ab4c  test    rdi, rdi
0x18001ab4f  jz      short loc_18001AB59
0x18001ab51  mov     rcx, rdi; Block
0x18001ab54  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ab59  xor     esi, esi
0x18001ab5b  mov     rcx, rbx; Block
0x18001ab5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ab63  mov     eax, esi
0x18001ab65  mov     rbx, [rsp+58h+arg_0]
0x18001ab6a  mov     rbp, [rsp+58h+arg_8]
0x18001ab6f  mov     rsi, [rsp+58h+arg_18]
0x18001ab74  add     rsp, 50h
0x18001ab78  pop     rdi
0x18001ab79  retn
```
