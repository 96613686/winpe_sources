# SrSettings::CSrSettings::SetACL(ushort const *)

- ea: `0x18004a3bc`
- end: `0x18004a64a`
- name: `?SetACL@CSrSettings@SrSettings@@AEAAJPEBG@Z`
- size: `654`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800469e0`
- `0x180046ed0`
- `0x180049360`
- `0x18004bfa0`

## callees

- `0x18004a3bc`
- `0x18004a6b8`
- `0x18004c0e8`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004a48f`
- `KERNEL32!GetLastError` at `0x18004a503`
- `KERNEL32!GetLastError` at `0x18004a545`
- `KERNEL32!GetLastError` at `0x18004a5cc`
- `KERNEL32!GetLastError` at `0x18004a48f`
- `KERNEL32!GetLastError` at `0x18004a503`
- `KERNEL32!GetLastError` at `0x18004a545`
- `KERNEL32!GetLastError` at `0x18004a5cc`
- `KERNEL32!HeapFree` at `0x18004a61b`
- `KERNEL32!HeapFree` at `0x18004a61b`
- `KERNEL32!HeapAlloc` at `0x18004a4d1`
- `KERNEL32!HeapAlloc` at `0x18004a4d1`
- `KERNEL32!GetProcessHeap` at `0x18004a4c0`
- `KERNEL32!GetProcessHeap` at `0x18004a60d`
- `KERNEL32!GetProcessHeap` at `0x18004a4c0`
- `KERNEL32!GetProcessHeap` at `0x18004a60d`
- `KERNEL32!SetFileAttributesW` at `0x18004a5c2`
- `KERNEL32!SetFileAttributesW` at `0x18004a5c2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18004a485`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18004a485`
- `ADVAPI32!GetLengthSid` at `0x18004a4b6`
- `ADVAPI32!GetLengthSid` at `0x18004a4b6`
- `ADVAPI32!InitializeAcl` at `0x18004a4f6`
- `ADVAPI32!InitializeAcl` at `0x18004a4f6`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18004a53b`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18004a53b`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18004a587`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18004a587`
- `ADVAPI32!FreeSid` at `0x18004a602`
- `ADVAPI32!FreeSid` at `0x18004a602`

## string_xrefs

- `0x18004a40d`: `Set ACL on [%s]`
- `0x18004a4a4`: `Failed to allocate and initialize SID. Error: 0x%08x`
- `0x18004a4e4`: `Failed to allocate memory for ACL. Error: 0x%08x`
- `0x18004a518`: `Failed to initialize ACL. Error: 0x%08x`
- `0x18004a55a`: `Failed to add access allowed ACE. Error: 0x%08x`
- `0x18004a596`: `Failed to set named security info. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::SetACL(SrSettings::CSrSettings *this, WCHAR *lpFileName)
{
  struct _ACL *v5; // r12
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  unsigned int v8; // edi
  __int64 v9; // r9
  const wchar_t *v10; // r8
  signed int v11; // eax
  DWORD v12; // r13d
  HANDLE ProcessHeap; // rax
  struct _ACL *v14; // rax
  signed int v15; // eax
  signed int v16; // eax
  DWORD v17; // eax
  int v18; // ebx
  signed int LastError; // eax
  HANDLE v20; // rax
  DWORD nSubAuthority2[2]; // [rsp+20h] [rbp-60h]
  PSID psidOwner; // [rsp+60h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  psidOwner = 0;
  if ( !lpFileName )
    return 2147942487LL;
  v5 = 0;
  SrSettings::CSrSettings::Trace(this, 0, L"Set ACL on [%s]", lpFileName);
  v7 = SrSettings::CSrSettings::SetPriviledge(this, v6);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &psidOwner) )
    {
      v12 = GetLengthSid(psidOwner) + 16;
      ProcessHeap = GetProcessHeap();
      v14 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v12);
      v5 = v14;
      if ( v14 )
      {
        if ( InitializeAcl(v14, v12, 2u) )
        {
          if ( AddAccessAllowedAceEx(v5, 2u, 3u, 0x10000000u, psidOwner) )
          {
            v17 = SetNamedSecurityInfoW(lpFileName, SE_FILE_OBJECT, 0x80000005, psidOwner, 0, v5, 0);
            v18 = v17;
            if ( v17 )
            {
              SrSettings::CSrSettings::Trace(this, 2, L"Failed to set named security info. Error: 0x%08x", v17);
              if ( v18 > 0 )
                v8 = (unsigned __int16)v18 | 0x80070000;
              else
                v8 = v18;
            }
            else if ( !SetFileAttributesW(lpFileName, 0x2006u) )
            {
              LastError = GetLastError();
              v8 = LastError;
              if ( LastError > 0 )
                v8 = (unsigned __int16)LastError | 0x80070000;
              nSubAuthority2[0] = v8;
              SrSettings::CSrSettings::Trace(
                this,
                2,
                L"Failed to set file attributes to %s. Error: 0x%08x",
                lpFileName,
                *(_QWORD *)nSubAuthority2);
            }
            goto LABEL_29;
          }
          v16 = GetLastError();
          v8 = v16;
          if ( v16 > 0 )
            v8 = (unsigned __int16)v16 | 0x80070000;
          v10 = L"Failed to add access allowed ACE. Error: 0x%08x";
        }
        else
        {
          v15 = GetLastError();
          v8 = v15;
          if ( v15 > 0 )
            v8 = (unsigned __int16)v15 | 0x80070000;
          v10 = L"Failed to initialize ACL. Error: 0x%08x";
        }
      }
      else
      {
        v8 = -2147024888;
        v10 = L"Failed to allocate memory for ACL. Error: 0x%08x";
      }
    }
    else
    {
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      v10 = L"Failed to allocate and initialize SID. Error: 0x%08x";
    }
    v9 = v8;
  }
  else
  {
    v9 = (unsigned int)v7;
    v10 = L"Failed to set take ownership priviledge. Error: 0x%08x";
  }
  SrSettings::CSrSettings::Trace(this, 2, v10, v9);
LABEL_29:
  if ( psidOwner )
    FreeSid(psidOwner);
  if ( v5 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v5);
  }
  return v8;
}

```

## disassembly

```asm
0x18004a3bc  mov     [rsp-38h+arg_10], rbx
0x18004a3c1  push    rbp
0x18004a3c2  push    rsi
0x18004a3c3  push    rdi
0x18004a3c4  push    r12
0x18004a3c6  push    r13
0x18004a3c8  push    r14
0x18004a3ca  push    r15
0x18004a3cc  mov     rbp, rsp
0x18004a3cf  sub     rsp, 80h
0x18004a3d6  mov     rax, cs:__security_cookie
0x18004a3dd  xor     rax, rsp
0x18004a3e0  mov     [rbp+var_10], rax
0x18004a3e4  xor     r13d, r13d
0x18004a3e7  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18004a3ed  mov     dword ptr [rbp+pIdentifierAuthority.Value], r13d
0x18004a3f1  mov     r15, rdx
0x18004a3f4  mov     [rbp+psidOwner], r13
0x18004a3f8  mov     r14, rcx
0x18004a3fb  test    rdx, rdx
0x18004a3fe  jnz     short loc_18004A40A
0x18004a400  mov     eax, 80070057h
0x18004a405  jmp     loc_18004A623
0x18004a40a  mov     r9, r15
0x18004a40d  lea     r8, aSetAclOnS; "Set ACL on [%s]"
0x18004a414  xor     edx, edx
0x18004a416  mov     r12, r13
0x18004a419  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a41e  mov     rcx, r14; this
0x18004a421  call    ?SetPriviledge@CSrSettings@SrSettings@@AEAAJPEBG@Z; SrSettings::CSrSettings::SetPriviledge(ushort const *)
0x18004a426  mov     edi, eax
0x18004a428  test    eax, eax
0x18004a42a  jns     short loc_18004A448
0x18004a42c  mov     r9d, eax
0x18004a42f  lea     r8, aFailedToSetTak; "Failed to set take ownership priviledge"...
0x18004a436  mov     edx, 2
0x18004a43b  mov     rcx, r14
0x18004a43e  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a443  jmp     loc_18004A5F9
0x18004a448  lea     rax, [rbp+psidOwner]
0x18004a44c  mov     esi, 2
0x18004a451  mov     [rsp+80h+pSid], rax; pSid
0x18004a456  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18004a45a  mov     [rsp+80h+nSubAuthority7], r13d; nSubAuthority7
0x18004a45f  mov     r9d, 220h; nSubAuthority1
0x18004a465  mov     [rsp+80h+nSubAuthority6], r13d; nSubAuthority6
0x18004a46a  mov     dl, sil; nSubAuthorityCount
0x18004a46d  mov     [rsp+80h+nSubAuthority5], r13d; nSubAuthority5
0x18004a472  lea     r8d, [rsi+1Eh]; nSubAuthority0
0x18004a476  mov     [rsp+80h+nSubAuthority4], r13d; nSubAuthority4
0x18004a47b  mov     [rsp+80h+nSubAuthority3], r13d; nSubAuthority3
0x18004a480  mov     [rsp+80h+nSubAuthority2], r13d; nSubAuthority2
0x18004a485  call    cs:__imp_AllocateAndInitializeSid
0x18004a48b  test    eax, eax
0x18004a48d  jnz     short loc_18004A4B2
0x18004a48f  call    cs:__imp_GetLastError
0x18004a495  mov     edi, eax
0x18004a497  test    eax, eax
0x18004a499  jle     short loc_18004A4A4
0x18004a49b  movzx   edi, ax
0x18004a49e  or      edi, 80070000h
0x18004a4a4  lea     r8, aFailedToAlloca_1; "Failed to allocate and initialize SID. "...
0x18004a4ab  mov     r9d, edi
0x18004a4ae  mov     edx, esi
0x18004a4b0  jmp     short loc_18004A43B
0x18004a4b2  mov     rcx, [rbp+psidOwner]; pSid
0x18004a4b6  call    cs:__imp_GetLengthSid
0x18004a4bc  lea     r13d, [rax+10h]
0x18004a4c0  call    cs:__imp_GetProcessHeap
0x18004a4c6  mov     r8d, r13d; dwBytes
0x18004a4c9  mov     edx, 8; dwFlags
0x18004a4ce  mov     rcx, rax; hHeap
0x18004a4d1  call    cs:__imp_HeapAlloc
0x18004a4d7  mov     r12, rax
0x18004a4da  test    rax, rax
0x18004a4dd  jnz     short loc_18004A4ED
0x18004a4df  mov     edi, 80070008h
0x18004a4e4  lea     r8, aFailedToAlloca_3; "Failed to allocate memory for ACL. Erro"...
0x18004a4eb  jmp     short loc_18004A4AB
0x18004a4ed  mov     r8d, esi; dwAclRevision
0x18004a4f0  mov     edx, r13d; nAclLength
0x18004a4f3  mov     rcx, r12; pAcl
0x18004a4f6  call    cs:__imp_InitializeAcl
0x18004a4fc  xor     r13d, r13d
0x18004a4ff  test    eax, eax
0x18004a501  jnz     short loc_18004A521
0x18004a503  call    cs:__imp_GetLastError
0x18004a509  mov     edi, eax
0x18004a50b  test    eax, eax
0x18004a50d  jle     short loc_18004A518
0x18004a50f  movzx   edi, ax
0x18004a512  or      edi, 80070000h
0x18004a518  lea     r8, aFailedToInitia_1; "Failed to initialize ACL. Error: 0x%08x"
0x18004a51f  jmp     short loc_18004A4AB
0x18004a521  mov     rax, [rbp+psidOwner]
0x18004a525  mov     r9d, 10000000h; AccessMask
0x18004a52b  mov     r8d, 3; AceFlags
0x18004a531  mov     qword ptr [rsp+80h+nSubAuthority2], rax; pSid
0x18004a536  mov     edx, esi; dwAceRevision
0x18004a538  mov     rcx, r12; pAcl
0x18004a53b  call    cs:__imp_AddAccessAllowedAceEx
0x18004a541  test    eax, eax
0x18004a543  jnz     short loc_18004A566
0x18004a545  call    cs:__imp_GetLastError
0x18004a54b  mov     edi, eax
0x18004a54d  test    eax, eax
0x18004a54f  jle     short loc_18004A55A
0x18004a551  movzx   edi, ax
0x18004a554  or      edi, 80070000h
0x18004a55a  lea     r8, aFailedToAddAcc; "Failed to add access allowed ACE. Error"...
0x18004a561  jmp     loc_18004A4AB
0x18004a566  mov     r9, [rbp+psidOwner]; psidOwner
0x18004a56a  mov     edx, 1; ObjectType
0x18004a56f  mov     qword ptr [rsp+80h+nSubAuthority4], r13; pSacl
0x18004a574  mov     r8d, 80000005h; SecurityInfo
0x18004a57a  mov     qword ptr [rsp+80h+nSubAuthority3], r12; pDacl
0x18004a57f  mov     rcx, r15; pObjectName
0x18004a582  mov     qword ptr [rsp+80h+nSubAuthority2], r13; psidGroup
0x18004a587  call    cs:__imp_SetNamedSecurityInfoW
0x18004a58d  mov     ebx, eax
0x18004a58f  test    eax, eax
0x18004a591  jz      short loc_18004A5BA
0x18004a593  mov     r9d, eax
0x18004a596  lea     r8, aFailedToSetNam; "Failed to set named security info. Erro"...
0x18004a59d  mov     edx, esi
0x18004a59f  mov     rcx, r14
0x18004a5a2  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a5a7  test    ebx, ebx
0x18004a5a9  jg      short loc_18004A5AF
0x18004a5ab  mov     edi, ebx
0x18004a5ad  jmp     short loc_18004A5F9
0x18004a5af  movzx   edi, bx
0x18004a5b2  or      edi, 80070000h
0x18004a5b8  jmp     short loc_18004A5F9
0x18004a5ba  mov     edx, 2006h; dwFileAttributes
0x18004a5bf  mov     rcx, r15; lpFileName
0x18004a5c2  call    cs:__imp_SetFileAttributesW
0x18004a5c8  test    eax, eax
0x18004a5ca  jnz     short loc_18004A5F9
0x18004a5cc  call    cs:__imp_GetLastError
0x18004a5d2  mov     edi, eax
0x18004a5d4  test    eax, eax
0x18004a5d6  jle     short loc_18004A5E1
0x18004a5d8  movzx   edi, ax
0x18004a5db  or      edi, 80070000h
0x18004a5e1  mov     r9, r15
0x18004a5e4  mov     [rsp+80h+nSubAuthority2], edi
0x18004a5e8  lea     r8, aFailedToSetFil_0; "Failed to set file attributes to %s. Er"...
0x18004a5ef  mov     edx, esi
0x18004a5f1  mov     rcx, r14
0x18004a5f4  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004a5f9  mov     rcx, [rbp+psidOwner]; pSid
0x18004a5fd  test    rcx, rcx
0x18004a600  jz      short loc_18004A608
0x18004a602  call    cs:__imp_FreeSid
0x18004a608  test    r12, r12
0x18004a60b  jz      short loc_18004A621
0x18004a60d  call    cs:__imp_GetProcessHeap
0x18004a613  mov     r8, r12; lpMem
0x18004a616  xor     edx, edx; dwFlags
0x18004a618  mov     rcx, rax; hHeap
0x18004a61b  call    cs:__imp_HeapFree
0x18004a621  mov     eax, edi
0x18004a623  mov     rcx, [rbp+var_10]
0x18004a627  xor     rcx, rsp; StackCookie
0x18004a62a  call    __security_check_cookie
0x18004a62f  mov     rbx, [rsp+80h+arg_10]
0x18004a637  add     rsp, 80h
0x18004a63e  pop     r15
0x18004a640  pop     r14
0x18004a642  pop     r13
0x18004a644  pop     r12
0x18004a646  pop     rdi
0x18004a647  pop     rsi
0x18004a648  pop     rbp
0x18004a649  retn
```
