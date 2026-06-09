# RestrictFolder(ushort const *)

- ea: `0x18001d83c`
- end: `0x18001da08`
- name: `?RestrictFolder@@YAJPEBG@Z`
- size: `460`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001d50c`

## callees

- `0x180002e48`
- `0x18001c658`
- `0x18001d83c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9e7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001d9e7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d9d0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d9d9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d9d0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001d9d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8f4`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d8a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d8b8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d8a8`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18001d8b8`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18001d9b8`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18001d9b8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d99e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001d99e`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d983`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18001d983`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d8ea`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18001d8ea`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d93d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d95d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d93d`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18001d95d`

## pseudocode

```c
__int64 __fastcall RestrictFolder(LPCWSTR lpFileName)
{
  unsigned int v1; // r15d
  struct _ACL *v2; // rsi
  int LocalWellKnownSid; // eax
  DWORD LengthSid; // r14d
  DWORD v6; // r12d
  struct _ACL *v7; // rax
  struct _ACL *v8; // r14
  signed int LastError; // eax
  _OWORD pSecurityDescriptor[2]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+50h] [rbp-10h]

  v1 = 0;
  v2 = 0;
  if ( !g_fUnitTestContext )
  {
    LocalWellKnownSid = CreateLocalWellKnownSid(WinLocalSystemSid);
    if ( LocalWellKnownSid < 0
      || (LocalWellKnownSid = CreateLocalWellKnownSid(WinBuiltinAdministratorsSid), LocalWellKnownSid < 0) )
    {
      v1 = LocalWellKnownSid;
    }
    else
    {
      LengthSid = GetLengthSid(0);
      v6 = (LengthSid + GetLengthSid(0) + 27) & 0xFFFFFFFC;
      v7 = (struct _ACL *)operator new[](v6);
      v8 = v7;
      if ( v7 )
      {
        v2 = v7;
        if ( !InitializeAcl(v7, v6, 2u)
          || !AddAccessAllowedAceEx(v8, 2u, 3u, 0x1FFFFFu, 0)
          || !AddAccessAllowedAceEx(v8, 2u, 3u, 0x1FFFFFu, 0)
          || (v12 = 0,
              memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor)),
              !InitializeSecurityDescriptor(pSecurityDescriptor, 1u))
          || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v8, 0)
          || !SetFileSecurityW(lpFileName, 4u, pSecurityDescriptor) )
        {
          LastError = GetLastError();
          v1 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v1 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v1 = -2143748092;
          }
        }
      }
      else
      {
        v1 = -2147024882;
      }
    }
  }
  operator delete[](0);
  operator delete[](0);
  if ( v2 )
    operator delete(v2);
  return v1;
}

```

## disassembly

```asm
0x18001d83c  mov     [rsp-38h+arg_0], rbx
0x18001d841  push    rbp
0x18001d842  push    rsi
0x18001d843  push    rdi
0x18001d844  push    r12
0x18001d846  push    r13
0x18001d848  push    r14
0x18001d84a  push    r15
0x18001d84c  mov     rbp, rsp
0x18001d84f  sub     rsp, 60h
0x18001d853  xor     ebx, ebx
0x18001d855  xor     edi, edi
0x18001d857  xor     r15d, r15d
0x18001d85a  mov     [rbp+arg_8], rbx
0x18001d85e  xor     esi, esi
0x18001d860  mov     [rbp+pSid], rdi
0x18001d864  cmp     cs:?g_fUnitTestContext@@3HA, ebx; int g_fUnitTestContext
0x18001d86a  mov     r13, rcx
0x18001d86d  jnz     loc_18001D9CD
0x18001d873  lea     rdx, [rbp+arg_8]
0x18001d877  lea     ecx, [rsi+16h]; WellKnownSidType
0x18001d87a  call    ?CreateLocalWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z; CreateLocalWellKnownSid(WELL_KNOWN_SID_TYPE,std::unique_ptr<uchar [0]> &)
0x18001d87f  test    eax, eax
0x18001d881  jns     short loc_18001D88F
0x18001d883  mov     rbx, [rbp+arg_8]
0x18001d887  mov     r15d, eax
0x18001d88a  jmp     loc_18001D9CD
0x18001d88f  lea     rdx, [rbp+pSid]
0x18001d893  mov     ecx, 1Ah; WellKnownSidType
0x18001d898  call    ?CreateLocalWellKnownSid@@YAJW4WELL_KNOWN_SID_TYPE@@AEAV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@@Z; CreateLocalWellKnownSid(WELL_KNOWN_SID_TYPE,std::unique_ptr<uchar [0]> &)
0x18001d89d  mov     rdi, [rbp+pSid]
0x18001d8a1  test    eax, eax
0x18001d8a3  js      short loc_18001D883
0x18001d8a5  mov     rcx, rdi; pSid
0x18001d8a8  call    cs:__imp_GetLengthSid
0x18001d8ae  mov     rbx, [rbp+arg_8]
0x18001d8b2  mov     r14d, eax
0x18001d8b5  mov     rcx, rbx; pSid
0x18001d8b8  call    cs:__imp_GetLengthSid
0x18001d8be  lea     ecx, [rax+1Bh]
0x18001d8c1  add     ecx, r14d
0x18001d8c4  and     ecx, 0FFFFFFFCh; unsigned __int64
0x18001d8c7  mov     r12d, ecx
0x18001d8ca  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001d8cf  mov     r14, rax
0x18001d8d2  test    rax, rax
0x18001d8d5  jz      loc_18001D9C7
0x18001d8db  mov     r8d, 2; dwAclRevision
0x18001d8e1  mov     edx, r12d; nAclLength
0x18001d8e4  mov     rcx, rax; pAcl
0x18001d8e7  mov     rsi, rax
0x18001d8ea  call    cs:__imp_InitializeAcl
0x18001d8f0  test    eax, eax
0x18001d8f2  jnz     short loc_18001D922
0x18001d8f4  call    cs:__imp_GetLastError
0x18001d8fa  mov     r15d, eax
0x18001d8fd  test    eax, eax
0x18001d8ff  jz      short loc_18001D917
0x18001d901  jle     loc_18001D9CD
0x18001d907  movzx   r15d, ax
0x18001d90b  or      r15d, 80070000h
0x18001d912  jmp     loc_18001D9CD
0x18001d917  mov     r15d, 80390004h
0x18001d91d  jmp     loc_18001D9CD
0x18001d922  mov     r8d, 3; AceFlags
0x18001d928  mov     [rsp+60h+var_40], rbx; pSid
0x18001d92d  mov     r9d, 1FFFFFh; AccessMask
0x18001d933  mov     rcx, r14; pAcl
0x18001d936  lea     r12d, [r8-1]
0x18001d93a  mov     edx, r12d; dwAceRevision
0x18001d93d  call    cs:__imp_AddAccessAllowedAceEx
0x18001d943  test    eax, eax
0x18001d945  jz      short loc_18001D8F4
0x18001d947  mov     r9d, 1FFFFFh; AccessMask
0x18001d94d  mov     [rsp+60h+var_40], rdi; pSid
0x18001d952  lea     r8d, [r12+1]; AceFlags
0x18001d957  mov     edx, r12d; dwAceRevision
0x18001d95a  mov     rcx, r14; pAcl
0x18001d95d  call    cs:__imp_AddAccessAllowedAceEx
0x18001d963  test    eax, eax
0x18001d965  jz      short loc_18001D8F4
0x18001d967  xor     eax, eax
0x18001d969  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18001d96d  xorps   xmm0, xmm0
0x18001d970  mov     [rbp+var_10], rax
0x18001d974  movups  [rbp+pSecurityDescriptor], xmm0
0x18001d978  lea     r12d, [rax+1]
0x18001d97c  mov     edx, r12d; dwRevision
0x18001d97f  movups  [rbp+var_20], xmm0
0x18001d983  call    cs:__imp_InitializeSecurityDescriptor
0x18001d989  test    eax, eax
0x18001d98b  jz      loc_18001D8F4
0x18001d991  xor     r9d, r9d; bDaclDefaulted
0x18001d994  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18001d998  mov     r8, r14; pDacl
0x18001d99b  mov     edx, r12d; bDaclPresent
0x18001d99e  call    cs:__imp_SetSecurityDescriptorDacl
0x18001d9a4  test    eax, eax
0x18001d9a6  jz      loc_18001D8F4
0x18001d9ac  lea     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18001d9b0  mov     rcx, r13; lpFileName
0x18001d9b3  lea     edx, [r12+3]; SecurityInformation
0x18001d9b8  call    cs:__imp_SetFileSecurityW
0x18001d9be  test    eax, eax
0x18001d9c0  jnz     short loc_18001D9CD
0x18001d9c2  jmp     loc_18001D8F4
0x18001d9c7  mov     r15d, 8007000Eh
0x18001d9cd  mov     rcx, rdi
0x18001d9d0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001d9d6  mov     rcx, rbx
0x18001d9d9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18001d9df  test    rsi, rsi
0x18001d9e2  jz      short loc_18001D9ED
0x18001d9e4  mov     rcx, rsi
0x18001d9e7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001d9ed  mov     rbx, [rsp+60h+arg_0]
0x18001d9f5  mov     eax, r15d
0x18001d9f8  add     rsp, 60h
0x18001d9fc  pop     r15
0x18001d9fe  pop     r14
0x18001da00  pop     r13
0x18001da02  pop     r12
0x18001da04  pop     rdi
0x18001da05  pop     rsi
0x18001da06  pop     rbp
0x18001da07  retn
```
