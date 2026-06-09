# SrSettings::CSrSettings::SetACL(ushort const *)

- ea: `0x18000e074`
- end: `0x18000e302`
- name: `?SetACL@CSrSettings@SrSettings@@AEAAJPEBG@Z`
- size: `654`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *this, WCHAR *lpFileName)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006a60`
- `0x180006fe0`
- `0x18000b290`
- `0x180010400`

## callees

- `0x18000e074`
- `0x18000ea9c`
- `0x180010a0c`
- `0x180014310`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e147`
- `KERNEL32!GetLastError` at `0x18000e1bb`
- `KERNEL32!GetLastError` at `0x18000e1fd`
- `KERNEL32!GetLastError` at `0x18000e284`
- `KERNEL32!GetLastError` at `0x18000e147`
- `KERNEL32!GetLastError` at `0x18000e1bb`
- `KERNEL32!GetLastError` at `0x18000e1fd`
- `KERNEL32!GetLastError` at `0x18000e284`
- `KERNEL32!GetProcessHeap` at `0x18000e178`
- `KERNEL32!GetProcessHeap` at `0x18000e2c5`
- `KERNEL32!GetProcessHeap` at `0x18000e178`
- `KERNEL32!GetProcessHeap` at `0x18000e2c5`
- `KERNEL32!HeapAlloc` at `0x18000e189`
- `KERNEL32!HeapAlloc` at `0x18000e189`
- `KERNEL32!SetFileAttributesW` at `0x18000e27a`
- `KERNEL32!SetFileAttributesW` at `0x18000e27a`
- `KERNEL32!HeapFree` at `0x18000e2d3`
- `KERNEL32!HeapFree` at `0x18000e2d3`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000e13d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000e13d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000e1ae`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000e1ae`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000e1f3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18000e1f3`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e16e`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e16e`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000e2ba`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000e2ba`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000e23f`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18000e23f`

## string_xrefs

- `0x18000e0c5`: `Set ACL on [%s]`
- `0x18000e15c`: `Failed to allocate and initialize SID. Error: 0x%08x`
- `0x18000e19c`: `Failed to allocate memory for ACL. Error: 0x%08x`
- `0x18000e1d0`: `Failed to initialize ACL. Error: 0x%08x`
- `0x18000e212`: `Failed to add access allowed ACE. Error: 0x%08x`
- `0x18000e24e`: `Failed to set named security info. Error: 0x%08x`

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
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-18h] BYREF

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
0x18000e074  mov     [rsp-38h+arg_10], rbx
0x18000e079  push    rbp
0x18000e07a  push    rsi
0x18000e07b  push    rdi
0x18000e07c  push    r12
0x18000e07e  push    r13
0x18000e080  push    r14
0x18000e082  push    r15
0x18000e084  mov     rbp, rsp
0x18000e087  sub     rsp, 80h
0x18000e08e  mov     rax, cs:__security_cookie
0x18000e095  xor     rax, rsp
0x18000e098  mov     [rbp+var_10], rax
0x18000e09c  xor     r13d, r13d
0x18000e09f  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18000e0a5  mov     dword ptr [rbp+pIdentifierAuthority.Value], r13d
0x18000e0a9  mov     r15, rdx
0x18000e0ac  mov     [rbp+psidOwner], r13
0x18000e0b0  mov     r14, rcx
0x18000e0b3  test    rdx, rdx
0x18000e0b6  jnz     short loc_18000E0C2
0x18000e0b8  mov     eax, 80070057h
0x18000e0bd  jmp     loc_18000E2DB
0x18000e0c2  mov     r9, r15
0x18000e0c5  lea     r8, aSetAclOnS; "Set ACL on [%s]"
0x18000e0cc  xor     edx, edx
0x18000e0ce  mov     r12, r13
0x18000e0d1  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000e0d6  mov     rcx, r14; this
0x18000e0d9  call    ?SetPriviledge@CSrSettings@SrSettings@@AEAAJPEBG@Z; SrSettings::CSrSettings::SetPriviledge(ushort const *)
0x18000e0de  mov     edi, eax
0x18000e0e0  test    eax, eax
0x18000e0e2  jns     short loc_18000E100
0x18000e0e4  mov     r9d, eax
0x18000e0e7  lea     r8, aFailedToSetTak; "Failed to set take ownership priviledge"...
0x18000e0ee  mov     edx, 2
0x18000e0f3  mov     rcx, r14
0x18000e0f6  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000e0fb  jmp     loc_18000E2B1
0x18000e100  lea     rax, [rbp+psidOwner]
0x18000e104  mov     esi, 2
0x18000e109  mov     [rsp+80h+pSid], rax; pSid
0x18000e10e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18000e112  mov     [rsp+80h+nSubAuthority7], r13d; nSubAuthority7
0x18000e117  mov     r9d, 220h; nSubAuthority1
0x18000e11d  mov     [rsp+80h+nSubAuthority6], r13d; nSubAuthority6
0x18000e122  mov     dl, sil; nSubAuthorityCount
0x18000e125  mov     [rsp+80h+nSubAuthority5], r13d; nSubAuthority5
0x18000e12a  lea     r8d, [rsi+1Eh]; nSubAuthority0
0x18000e12e  mov     [rsp+80h+nSubAuthority4], r13d; nSubAuthority4
0x18000e133  mov     [rsp+80h+nSubAuthority3], r13d; nSubAuthority3
0x18000e138  mov     [rsp+80h+nSubAuthority2], r13d; nSubAuthority2
0x18000e13d  call    cs:__imp_AllocateAndInitializeSid
0x18000e143  test    eax, eax
0x18000e145  jnz     short loc_18000E16A
0x18000e147  call    cs:__imp_GetLastError
0x18000e14d  mov     edi, eax
0x18000e14f  test    eax, eax
0x18000e151  jle     short loc_18000E15C
0x18000e153  movzx   edi, ax
0x18000e156  or      edi, 80070000h
0x18000e15c  lea     r8, aFailedToAlloca; "Failed to allocate and initialize SID. "...
0x18000e163  mov     r9d, edi
0x18000e166  mov     edx, esi
0x18000e168  jmp     short loc_18000E0F3
0x18000e16a  mov     rcx, [rbp+psidOwner]; pSid
0x18000e16e  call    cs:__imp_GetLengthSid
0x18000e174  lea     r13d, [rax+10h]
0x18000e178  call    cs:__imp_GetProcessHeap
0x18000e17e  mov     r8d, r13d; dwBytes
0x18000e181  mov     edx, 8; dwFlags
0x18000e186  mov     rcx, rax; hHeap
0x18000e189  call    cs:__imp_HeapAlloc
0x18000e18f  mov     r12, rax
0x18000e192  test    rax, rax
0x18000e195  jnz     short loc_18000E1A5
0x18000e197  mov     edi, 80070008h
0x18000e19c  lea     r8, aFailedToAlloca_0; "Failed to allocate memory for ACL. Erro"...
0x18000e1a3  jmp     short loc_18000E163
0x18000e1a5  mov     r8d, esi; dwAclRevision
0x18000e1a8  mov     edx, r13d; nAclLength
0x18000e1ab  mov     rcx, r12; pAcl
0x18000e1ae  call    cs:__imp_InitializeAcl
0x18000e1b4  xor     r13d, r13d
0x18000e1b7  test    eax, eax
0x18000e1b9  jnz     short loc_18000E1D9
0x18000e1bb  call    cs:__imp_GetLastError
0x18000e1c1  mov     edi, eax
0x18000e1c3  test    eax, eax
0x18000e1c5  jle     short loc_18000E1D0
0x18000e1c7  movzx   edi, ax
0x18000e1ca  or      edi, 80070000h
0x18000e1d0  lea     r8, aFailedToInitia; "Failed to initialize ACL. Error: 0x%08x"
0x18000e1d7  jmp     short loc_18000E163
0x18000e1d9  mov     rax, [rbp+psidOwner]
0x18000e1dd  mov     r9d, 10000000h; AccessMask
0x18000e1e3  mov     r8d, 3; AceFlags
0x18000e1e9  mov     qword ptr [rsp+80h+nSubAuthority2], rax; pSid
0x18000e1ee  mov     edx, esi; dwAceRevision
0x18000e1f0  mov     rcx, r12; pAcl
0x18000e1f3  call    cs:__imp_AddAccessAllowedAceEx
0x18000e1f9  test    eax, eax
0x18000e1fb  jnz     short loc_18000E21E
0x18000e1fd  call    cs:__imp_GetLastError
0x18000e203  mov     edi, eax
0x18000e205  test    eax, eax
0x18000e207  jle     short loc_18000E212
0x18000e209  movzx   edi, ax
0x18000e20c  or      edi, 80070000h
0x18000e212  lea     r8, aFailedToAddAcc; "Failed to add access allowed ACE. Error"...
0x18000e219  jmp     loc_18000E163
0x18000e21e  mov     r9, [rbp+psidOwner]; psidOwner
0x18000e222  mov     edx, 1; ObjectType
0x18000e227  mov     qword ptr [rsp+80h+nSubAuthority4], r13; pSacl
0x18000e22c  mov     r8d, 80000005h; SecurityInfo
0x18000e232  mov     qword ptr [rsp+80h+nSubAuthority3], r12; pDacl
0x18000e237  mov     rcx, r15; pObjectName
0x18000e23a  mov     qword ptr [rsp+80h+nSubAuthority2], r13; psidGroup
0x18000e23f  call    cs:__imp_SetNamedSecurityInfoW
0x18000e245  mov     ebx, eax
0x18000e247  test    eax, eax
0x18000e249  jz      short loc_18000E272
0x18000e24b  mov     r9d, eax
0x18000e24e  lea     r8, aFailedToSetNam; "Failed to set named security info. Erro"...
0x18000e255  mov     edx, esi
0x18000e257  mov     rcx, r14
0x18000e25a  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000e25f  test    ebx, ebx
0x18000e261  jg      short loc_18000E267
0x18000e263  mov     edi, ebx
0x18000e265  jmp     short loc_18000E2B1
0x18000e267  movzx   edi, bx
0x18000e26a  or      edi, 80070000h
0x18000e270  jmp     short loc_18000E2B1
0x18000e272  mov     edx, 2006h; dwFileAttributes
0x18000e277  mov     rcx, r15; lpFileName
0x18000e27a  call    cs:__imp_SetFileAttributesW
0x18000e280  test    eax, eax
0x18000e282  jnz     short loc_18000E2B1
0x18000e284  call    cs:__imp_GetLastError
0x18000e28a  mov     edi, eax
0x18000e28c  test    eax, eax
0x18000e28e  jle     short loc_18000E299
0x18000e290  movzx   edi, ax
0x18000e293  or      edi, 80070000h
0x18000e299  mov     r9, r15
0x18000e29c  mov     [rsp+80h+nSubAuthority2], edi
0x18000e2a0  lea     r8, aFailedToSetFil; "Failed to set file attributes to %s. Er"...
0x18000e2a7  mov     edx, esi
0x18000e2a9  mov     rcx, r14
0x18000e2ac  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000e2b1  mov     rcx, [rbp+psidOwner]; pSid
0x18000e2b5  test    rcx, rcx
0x18000e2b8  jz      short loc_18000E2C0
0x18000e2ba  call    cs:__imp_FreeSid
0x18000e2c0  test    r12, r12
0x18000e2c3  jz      short loc_18000E2D9
0x18000e2c5  call    cs:__imp_GetProcessHeap
0x18000e2cb  mov     r8, r12; lpMem
0x18000e2ce  xor     edx, edx; dwFlags
0x18000e2d0  mov     rcx, rax; hHeap
0x18000e2d3  call    cs:__imp_HeapFree
0x18000e2d9  mov     eax, edi
0x18000e2db  mov     rcx, [rbp+var_10]
0x18000e2df  xor     rcx, rsp; StackCookie
0x18000e2e2  call    __security_check_cookie
0x18000e2e7  mov     rbx, [rsp+80h+arg_10]
0x18000e2ef  add     rsp, 80h
0x18000e2f6  pop     r15
0x18000e2f8  pop     r14
0x18000e2fa  pop     r13
0x18000e2fc  pop     r12
0x18000e2fe  pop     rdi
0x18000e2ff  pop     rsi
0x18000e300  pop     rbp
0x18000e301  retn
```
