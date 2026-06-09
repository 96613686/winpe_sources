# CManagedAppProcessor::CreateAndSecureScriptDir(void)

- ea: `0x18000e8e8`
- end: `0x18000edb8`
- name: `?CreateAndSecureScriptDir@CManagedAppProcessor@@AEAAKXZ`
- size: `1232`
- prototype: `unsigned int __fastcall(CManagedAppProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000df00`

## callees

- `0x1800016d0`
- `0x1800016f4`
- `0x18000e8e8`
- `0x180012750`
- `0x180012a7c`
- `0x180012dac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ec1c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ec33`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ec1c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000ec33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed5e`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18000eca9`
- `api-ms-win-security-base-l1-1-0!DeleteAce` at `0x18000eca9`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000ec86`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000ed33`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000ec86`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18000ed33`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000eb6d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ebac`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ece3`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000eb6d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ebac`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18000ece3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000eb56`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000eb90`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000ebd2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000eccd`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000eb56`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000eb90`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000ebd2`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000eccd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ed73`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ed7d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ed87`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ed73`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ed7d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000ed87`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000ec00`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18000ec00`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000ebe6`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18000ebe6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000eb2a`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18000eb2a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ead9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000eae5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000eb02`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ead9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000eae5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000eb02`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ea39`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ea7b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000eac7`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ea39`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000ea7b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000eac7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ed69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ed90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ed69`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ed90`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eb10`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000eb10`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ed46`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000ed46`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ec5f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ed08`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ec5f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000ed08`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e959`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e959`

## pseudocode

```c
unsigned int __fastcall CManagedAppProcessor::CreateAndSecureScriptDir(CManagedAppProcessor *this)
{
  const WCHAR *v2; // rcx
  DWORD FileAttributesW; // eax
  unsigned int result; // eax
  DWORD LastError; // edi
  const unsigned __int16 *v6; // rdx
  void *v7; // rcx
  unsigned int v8; // ebx
  void *UserSid; // r12
  DWORD LengthSid; // ebx
  DWORD v11; // eax
  PSID v12; // rcx
  DWORD v13; // ebx
  struct _ACL *v14; // rax
  struct _ACL *v15; // r14
  wchar_t *v16; // r13
  const WCHAR *v17; // rcx
  BOOL Ace; // ebx
  unsigned __int16 *v19; // rax
  BOOL v20; // eax
  LPVOID pAce; // [rsp+60h] [rbp-69h] BYREF
  PSID pSid; // [rsp+68h] [rbp-61h] BYREF
  PSID v23; // [rsp+70h] [rbp-59h] BYREF
  PSID v24; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int16 *v25; // [rsp+80h] [rbp-49h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+88h] [rbp-41h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-9h]
  struct _SID_IDENTIFIER_AUTHORITY v29; // [rsp+C8h] [rbp-1h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+D0h] [rbp+7h] BYREF

  *(_WORD *)&v29.Value[4] = 1280;
  *(_DWORD *)v29.Value = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v28 = 0;
  v2 = (const WCHAR *)*((_QWORD *)this + 32);
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  pSid = 0;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v23 = 0;
  v24 = 0;
  pAce = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  FileAttributesW = GetFileAttributesW(v2);
  if ( FileAttributesW != -1 && (FileAttributesW & 4) != 0 )
    return 0;
  LastError = 0;
  if ( FileAttributesW == -1 && *((_DWORD *)this + 74) )
  {
    v6 = (const unsigned __int16 *)*((_QWORD *)this + 32);
    v7 = (void *)*((_QWORD *)this + 33);
    v25 = 0;
    result = GetPreviousSid(v7, v6, &v25);
    LastError = result;
    if ( result )
      return result;
    if ( v25 )
    {
      v8 = RenameScriptDir(v25, *((const unsigned __int16 **)this + 32));
      operator delete(v25, 2u);
      return v8;
    }
  }
  UserSid = 0;
  pSid = 0;
  v23 = 0;
  v24 = 0;
  if ( *((_DWORD *)this + 74) )
  {
    UserSid = AppmgmtGetUserSid(*((void **)this + 33));
    if ( !UserSid )
      return 14;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid)
    || !AllocateAndInitializeSid(&v29, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &v23)
    || !AllocateAndInitializeSid(&v29, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v24) )
  {
    v15 = 0;
    goto LABEL_45;
  }
  LengthSid = GetLengthSid(v24);
  v11 = GetLengthSid(v23);
  v12 = UserSid;
  if ( !*((_DWORD *)this + 74) )
    v12 = pSid;
  v13 = LengthSid + v11 + 32 + GetLengthSid(v12);
  v14 = (struct _ACL *)LocalAlloc(0, v13);
  v15 = v14;
  if ( !v14 )
  {
    LastError = 14;
    goto LABEL_46;
  }
  if ( !InitializeAcl(v14, v13, 2u) )
  {
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_46;
  }
  if ( !AddAccessAllowedAce(v15, 2u, 0x1F01FFu, v23) )
    goto LABEL_45;
  if ( !GetAce(v15, 0, &pAce) )
    goto LABEL_45;
  *((_BYTE *)pAce + 1) |= 3u;
  if ( !AddAccessAllowedAce(v15, 2u, 0x1F01FFu, v24) )
    goto LABEL_45;
  if ( !GetAce(v15, 1u, &pAce) )
    goto LABEL_45;
  *((_BYTE *)pAce + 1) |= 3u;
  if ( !AddAccessAllowedAce(v15, 2u, 0x1200A9u, pSid)
    || !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    || !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v15, 0) )
  {
    goto LABEL_45;
  }
  v16 = wcsrchr(*((const wchar_t **)this + 32), 0x5Cu);
  *v16 = 0;
  v25 = wcsrchr(*((const wchar_t **)this + 32), 0x5Cu);
  *v25 = 0;
  SecurityAttributes.bInheritHandle = 0;
  v17 = (const WCHAR *)*((_QWORD *)this + 32);
  SecurityAttributes.lpSecurityDescriptor = pSecurityDescriptor;
  SecurityAttributes.nLength = 24;
  Ace = CreateDirectoryW(v17, &SecurityAttributes);
  if ( !Ace && GetLastError() == 183 )
    Ace = SetFileSecurityW(*((LPCWSTR *)this + 32), 4u, pSecurityDescriptor);
  v19 = v25;
  *v16 = 92;
  *v19 = 92;
  if ( Ace )
  {
    v20 = DeleteAce(v15, 2u);
    Ace = v20;
    if ( *((_DWORD *)this + 74) )
    {
      if ( !v20 )
        goto LABEL_38;
      Ace = AddAccessAllowedAce(v15, 2u, 0x1200A9u, UserSid);
      if ( !Ace )
        goto LABEL_38;
      Ace = GetAce(v15, 2u, &pAce);
      if ( !Ace )
        goto LABEL_38;
      *((_BYTE *)pAce + 1) |= 3u;
    }
    else if ( !v20 )
    {
      goto LABEL_38;
    }
    Ace = CreateDirectoryW(*((LPCWSTR *)this + 32), &SecurityAttributes);
    if ( Ace )
      goto LABEL_46;
  }
LABEL_38:
  if ( GetLastError() != 183 )
    goto LABEL_41;
  if ( !SetFileSecurityW(*((LPCWSTR *)this + 32), 4u, pSecurityDescriptor) )
  {
LABEL_45:
    LastError = GetLastError();
    goto LABEL_46;
  }
  Ace = SetFileAttributesW(*((LPCWSTR *)this + 32), 4u);
LABEL_41:
  if ( !Ace )
    goto LABEL_45;
LABEL_46:
  LocalFree(UserSid);
  FreeSid(pSid);
  FreeSid(v23);
  FreeSid(v24);
  LocalFree(v15);
  return LastError;
}

```

## disassembly

```asm
0x18000e8e8  push    rbp
0x18000e8ea  push    rbx
0x18000e8eb  push    rsi
0x18000e8ec  push    rdi
0x18000e8ed  push    r12
0x18000e8ef  push    r13
0x18000e8f1  push    r14
0x18000e8f3  push    r15
0x18000e8f5  lea     rbp, [rsp-1Fh]
0x18000e8fa  sub     rsp, 0E8h
0x18000e901  mov     rax, cs:__security_cookie
0x18000e908  xor     rax, rsp
0x18000e90b  mov     [rbp+57h+var_48], rax
0x18000e90f  xor     r13d, r13d
0x18000e912  mov     word ptr [rbp+57h+var_58.Value+4], 500h
0x18000e918  xorps   xmm0, xmm0
0x18000e91b  mov     dword ptr [rbp+57h+var_58.Value], r13d
0x18000e91f  xor     eax, eax
0x18000e921  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], r13d
0x18000e925  mov     rsi, rcx
0x18000e928  mov     [rbp+57h+var_60], rax
0x18000e92c  mov     rcx, [rcx+100h]; lpFileName
0x18000e933  movups  [rbp+57h+pSecurityDescriptor], xmm0
0x18000e937  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], rax
0x18000e93b  movups  [rbp+57h+var_70], xmm0
0x18000e93f  mov     [rbp+57h+var_B8], r13
0x18000e943  movups  xmmword ptr [rbp+57h+SecurityAttributes.nLength], xmm0
0x18000e947  mov     [rbp+57h+var_B0], r13
0x18000e94b  mov     [rbp+57h+var_A8], r13
0x18000e94f  mov     [rbp+57h+pAce], r13
0x18000e953  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 100h
0x18000e959  call    cs:__imp_GetFileAttributesW
0x18000e95f  or      ecx, 0FFFFFFFFh
0x18000e962  cmp     eax, ecx
0x18000e964  jz      short loc_18000E971
0x18000e966  test    al, 4
0x18000e968  jz      short loc_18000E971
0x18000e96a  xor     eax, eax
0x18000e96c  jmp     loc_18000ED98
0x18000e971  mov     edi, r13d
0x18000e974  cmp     eax, ecx
0x18000e976  jnz     short loc_18000E9D0
0x18000e978  cmp     [rsi+128h], r13d
0x18000e97f  jz      short loc_18000E9D0
0x18000e981  mov     rdx, [rsi+100h]; unsigned __int16 *
0x18000e988  lea     r8, [rbp+57h+var_A0]; unsigned __int16 **
0x18000e98c  mov     rcx, [rsi+108h]; void *
0x18000e993  mov     [rbp+57h+var_A0], r13
0x18000e997  call    ?GetPreviousSid@@YAKPEAXPEBGPEAPEAG@Z; GetPreviousSid(void *,ushort const *,ushort * *)
0x18000e99c  mov     edi, eax
0x18000e99e  test    eax, eax
0x18000e9a0  jnz     loc_18000ED98
0x18000e9a6  mov     rcx, [rbp+57h+var_A0]; unsigned __int16 *
0x18000e9aa  test    rcx, rcx
0x18000e9ad  jz      short loc_18000E9D0
0x18000e9af  mov     rdx, [rsi+100h]; Src
0x18000e9b6  call    ?RenameScriptDir@@YAKPEBG0@Z; RenameScriptDir(ushort const *,ushort const *)
0x18000e9bb  mov     rcx, [rbp+57h+var_A0]; void *
0x18000e9bf  lea     edx, [rdi+2]; unsigned __int64
0x18000e9c2  mov     ebx, eax
0x18000e9c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e9c9  mov     eax, ebx
0x18000e9cb  jmp     loc_18000ED98
0x18000e9d0  mov     r12, r13
0x18000e9d3  mov     [rbp+57h+var_B8], r13
0x18000e9d7  mov     [rbp+57h+var_B0], r13
0x18000e9db  mov     [rbp+57h+var_A8], r13
0x18000e9df  cmp     [rsi+128h], r13d
0x18000e9e6  jz      short loc_18000EA06
0x18000e9e8  mov     rcx, [rsi+108h]; void *
0x18000e9ef  call    ?AppmgmtGetUserSid@@YAPEAXPEAX@Z; AppmgmtGetUserSid(void *)
0x18000e9f4  mov     r12, rax
0x18000e9f7  test    rax, rax
0x18000e9fa  jnz     short loc_18000EA06
0x18000e9fc  lea     eax, [r12+0Eh]
0x18000ea01  jmp     loc_18000ED98
0x18000ea06  lea     rax, [rbp+57h+var_B8]
0x18000ea0a  xor     r9d, r9d; nSubAuthority1
0x18000ea0d  mov     [rsp+120h+pSid], rax; pSid
0x18000ea12  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x18000ea16  mov     [rsp+120h+nSubAuthority7], r13d; nSubAuthority7
0x18000ea1b  xor     r8d, r8d; nSubAuthority0
0x18000ea1e  mov     [rsp+120h+nSubAuthority6], r13d; nSubAuthority6
0x18000ea23  mov     dl, 1; nSubAuthorityCount
0x18000ea25  mov     [rsp+120h+nSubAuthority5], r13d; nSubAuthority5
0x18000ea2a  mov     [rsp+120h+nSubAuthority4], r13d; nSubAuthority4
0x18000ea2f  mov     [rsp+120h+nSubAuthority3], r13d; nSubAuthority3
0x18000ea34  mov     [rsp+120h+nSubAuthority2], r13d; nSubAuthority2
0x18000ea39  call    cs:__imp_AllocateAndInitializeSid
0x18000ea3f  test    eax, eax
0x18000ea41  jz      loc_18000ED5B
0x18000ea47  lea     rax, [rbp+57h+var_B0]
0x18000ea4b  xor     r9d, r9d; nSubAuthority1
0x18000ea4e  mov     [rsp+120h+pSid], rax; pSid
0x18000ea53  lea     rcx, [rbp+57h+var_58]; pIdentifierAuthority
0x18000ea57  mov     [rsp+120h+nSubAuthority7], r13d; nSubAuthority7
0x18000ea5c  mov     dl, 1; nSubAuthorityCount
0x18000ea5e  mov     [rsp+120h+nSubAuthority6], r13d; nSubAuthority6
0x18000ea63  mov     [rsp+120h+nSubAuthority5], r13d; nSubAuthority5
0x18000ea68  lea     r8d, [r9+12h]; nSubAuthority0
0x18000ea6c  mov     [rsp+120h+nSubAuthority4], r13d; nSubAuthority4
0x18000ea71  mov     [rsp+120h+nSubAuthority3], r13d; nSubAuthority3
0x18000ea76  mov     [rsp+120h+nSubAuthority2], r13d; nSubAuthority2
0x18000ea7b  call    cs:__imp_AllocateAndInitializeSid
0x18000ea81  test    eax, eax
0x18000ea83  jz      loc_18000ED5B
0x18000ea89  lea     rax, [rbp+57h+var_A8]
0x18000ea8d  mov     r8d, 20h ; ' '; nSubAuthority0
0x18000ea93  mov     [rsp+120h+pSid], rax; pSid
0x18000ea98  lea     rcx, [rbp+57h+var_58]; pIdentifierAuthority
0x18000ea9c  mov     [rsp+120h+nSubAuthority7], r13d; nSubAuthority7
0x18000eaa1  mov     r9d, 220h; nSubAuthority1
0x18000eaa7  mov     [rsp+120h+nSubAuthority6], r13d; nSubAuthority6
0x18000eaac  mov     [rsp+120h+nSubAuthority5], r13d; nSubAuthority5
0x18000eab1  lea     r15d, [r8-1Eh]
0x18000eab5  mov     [rsp+120h+nSubAuthority4], r13d; nSubAuthority4
0x18000eaba  mov     dl, r15b; nSubAuthorityCount
0x18000eabd  mov     [rsp+120h+nSubAuthority3], r13d; nSubAuthority3
0x18000eac2  mov     [rsp+120h+nSubAuthority2], r13d; nSubAuthority2
0x18000eac7  call    cs:__imp_AllocateAndInitializeSid
0x18000eacd  test    eax, eax
0x18000eacf  jz      loc_18000ED5B
0x18000ead5  mov     rcx, [rbp+57h+var_A8]; pSid
0x18000ead9  call    cs:__imp_GetLengthSid
0x18000eadf  mov     rcx, [rbp+57h+var_B0]; pSid
0x18000eae3  mov     ebx, eax
0x18000eae5  call    cs:__imp_GetLengthSid
0x18000eaeb  mov     rcx, r12
0x18000eaee  lea     r14d, [rax+20h]
0x18000eaf2  add     r14d, ebx
0x18000eaf5  cmp     [rsi+128h], r13d
0x18000eafc  jnz     short loc_18000EB02
0x18000eafe  mov     rcx, [rbp+57h+var_B8]; pSid
0x18000eb02  call    cs:__imp_GetLengthSid
0x18000eb08  xor     ecx, ecx; uFlags
0x18000eb0a  lea     ebx, [r14+rax]
0x18000eb0e  mov     edx, ebx; uBytes
0x18000eb10  call    cs:__imp_LocalAlloc
0x18000eb16  mov     r14, rax
0x18000eb19  test    rax, rax
0x18000eb1c  jz      loc_18000ED54
0x18000eb22  mov     r8d, r15d; dwAclRevision
0x18000eb25  mov     edx, ebx; nAclLength
0x18000eb27  mov     rcx, rax; pAcl
0x18000eb2a  call    cs:__imp_InitializeAcl
0x18000eb30  test    eax, eax
0x18000eb32  jnz     short loc_18000EB44
0x18000eb34  call    cs:__imp_GetLastError
0x18000eb3a  mov     edi, eax
0x18000eb3c  test    eax, eax
0x18000eb3e  jnz     loc_18000ED66
0x18000eb44  mov     r9, [rbp+57h+var_B0]; pSid
0x18000eb48  mov     ebx, 1F01FFh
0x18000eb4d  mov     r8d, ebx; AccessMask
0x18000eb50  mov     edx, r15d; dwAceRevision
0x18000eb53  mov     rcx, r14; pAcl
0x18000eb56  call    cs:__imp_AddAccessAllowedAce
0x18000eb5c  test    eax, eax
0x18000eb5e  jz      loc_18000ED5E
0x18000eb64  lea     r8, [rbp+57h+pAce]; pAce
0x18000eb68  xor     edx, edx; dwAceIndex
0x18000eb6a  mov     rcx, r14; pAcl
0x18000eb6d  call    cs:__imp_GetAce
0x18000eb73  test    eax, eax
0x18000eb75  jz      loc_18000ED5E
0x18000eb7b  mov     rax, [rbp+57h+pAce]
0x18000eb7f  mov     r8d, ebx; AccessMask
0x18000eb82  mov     edx, r15d; dwAceRevision
0x18000eb85  mov     rcx, r14; pAcl
0x18000eb88  or      byte ptr [rax+1], 3
0x18000eb8c  mov     r9, [rbp+57h+var_A8]; pSid
0x18000eb90  call    cs:__imp_AddAccessAllowedAce
0x18000eb96  test    eax, eax
0x18000eb98  jz      loc_18000ED5E
0x18000eb9e  mov     ebx, 1
0x18000eba3  lea     r8, [rbp+57h+pAce]; pAce
0x18000eba7  mov     edx, ebx; dwAceIndex
0x18000eba9  mov     rcx, r14; pAcl
0x18000ebac  call    cs:__imp_GetAce
0x18000ebb2  test    eax, eax
0x18000ebb4  jz      loc_18000ED5E
0x18000ebba  mov     rax, [rbp+57h+pAce]
0x18000ebbe  mov     r8d, 1200A9h; AccessMask
0x18000ebc4  mov     edx, r15d; dwAceRevision
0x18000ebc7  mov     rcx, r14; pAcl
0x18000ebca  or      byte ptr [rax+1], 3
0x18000ebce  mov     r9, [rbp+57h+var_B8]; pSid
0x18000ebd2  call    cs:__imp_AddAccessAllowedAce
0x18000ebd8  test    eax, eax
0x18000ebda  jz      loc_18000ED5E
0x18000ebe0  mov     edx, ebx; dwRevision
0x18000ebe2  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000ebe6  call    cs:__imp_InitializeSecurityDescriptor
0x18000ebec  test    eax, eax
0x18000ebee  jz      loc_18000ED5E
0x18000ebf4  xor     r9d, r9d; bDaclDefaulted
0x18000ebf7  lea     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000ebfb  mov     r8, r14; pDacl
0x18000ebfe  mov     edx, ebx; bDaclPresent
0x18000ec00  call    cs:__imp_SetSecurityDescriptorDacl
0x18000ec06  test    eax, eax
0x18000ec08  jz      loc_18000ED5E
0x18000ec0e  mov     rcx, [rsi+100h]; Str
0x18000ec15  mov     ebx, 5Ch ; '\'
0x18000ec1a  mov     edx, ebx; Ch
0x18000ec1c  call    cs:__imp_wcsrchr
0x18000ec22  xor     ecx, ecx
0x18000ec24  mov     edx, ebx; Ch
0x18000ec26  mov     r13, rax
0x18000ec29  mov     [rax], cx
0x18000ec2c  mov     rcx, [rsi+100h]; Str
0x18000ec33  call    cs:__imp_wcsrchr
0x18000ec39  xor     ecx, ecx
0x18000ec3b  mov     [rbp+57h+var_A0], rax
0x18000ec3f  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18000ec43  mov     [rax], cx
0x18000ec46  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18000ec4a  mov     [rbp+57h+SecurityAttributes.bInheritHandle], ecx
0x18000ec4d  mov     rcx, [rsi+100h]; lpPathName
0x18000ec54  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x18000ec58  mov     [rbp+57h+SecurityAttributes.nLength], 18h
0x18000ec5f  call    cs:__imp_CreateDirectoryW
0x18000ec65  mov     ebx, eax
0x18000ec67  test    eax, eax
0x18000ec69  jnz     short loc_18000EC8E
0x18000ec6b  call    cs:__imp_GetLastError
0x18000ec71  cmp     eax, 0B7h
0x18000ec76  jnz     short loc_18000EC8E
0x18000ec78  mov     rcx, [rsi+100h]; lpFileName
0x18000ec7f  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000ec83  lea     edx, [rbx+4]; SecurityInformation
0x18000ec86  call    cs:__imp_SetFileSecurityW
0x18000ec8c  mov     ebx, eax
0x18000ec8e  mov     rax, [rbp+57h+var_A0]
0x18000ec92  mov     ecx, 5Ch ; '\'
0x18000ec97  mov     [r13+0], cx
0x18000ec9c  mov     [rax], cx
0x18000ec9f  test    ebx, ebx
0x18000eca1  jz      short loc_18000ED14
0x18000eca3  mov     edx, r15d; dwAceIndex
0x18000eca6  mov     rcx, r14; pAcl
0x18000eca9  call    cs:__imp_DeleteAce
0x18000ecaf  cmp     dword ptr [rsi+128h], 0
0x18000ecb6  mov     ebx, eax
0x18000ecb8  jz      short loc_18000ECF9
0x18000ecba  test    eax, eax
0x18000ecbc  jz      short loc_18000ED14
0x18000ecbe  mov     r9, r12; pSid
0x18000ecc1  mov     r8d, 1200A9h; AccessMask
0x18000ecc7  mov     edx, r15d; dwAceRevision
0x18000ecca  mov     rcx, r14; pAcl
0x18000eccd  call    cs:__imp_AddAccessAllowedAce
0x18000ecd3  mov     ebx, eax
0x18000ecd5  test    eax, eax
0x18000ecd7  jz      short loc_18000ED14
0x18000ecd9  lea     r8, [rbp+57h+pAce]; pAce
0x18000ecdd  mov     edx, r15d; dwAceIndex
0x18000ece0  mov     rcx, r14; pAcl
0x18000ece3  call    cs:__imp_GetAce
0x18000ece9  mov     ebx, eax
0x18000eceb  test    eax, eax
0x18000eced  jz      short loc_18000ED14
0x18000ecef  mov     rax, [rbp+57h+pAce]
0x18000ecf3  or      byte ptr [rax+1], 3
0x18000ecf7  jmp     short loc_18000ECFD
0x18000ecf9  test    eax, eax
0x18000ecfb  jz      short loc_18000ED14
0x18000ecfd  mov     rcx, [rsi+100h]; lpPathName
0x18000ed04  lea     rdx, [rbp+57h+SecurityAttributes]; lpSecurityAttributes
0x18000ed08  call    cs:__imp_CreateDirectoryW
0x18000ed0e  mov     ebx, eax
0x18000ed10  test    eax, eax
0x18000ed12  jnz     short loc_18000ED66
0x18000ed14  call    cs:__imp_GetLastError
0x18000ed1a  cmp     eax, 0B7h
0x18000ed1f  jnz     short loc_18000ED4E
0x18000ed21  mov     rcx, [rsi+100h]; lpFileName
0x18000ed28  lea     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18000ed2c  mov     ebx, 4
0x18000ed31  mov     edx, ebx; SecurityInformation
0x18000ed33  call    cs:__imp_SetFileSecurityW
0x18000ed39  test    eax, eax
0x18000ed3b  jz      short loc_18000ED5E
0x18000ed3d  mov     rcx, [rsi+100h]; lpFileName
0x18000ed44  mov     edx, ebx; dwFileAttributes
0x18000ed46  call    cs:__imp_SetFileAttributesW
0x18000ed4c  mov     ebx, eax
0x18000ed4e  test    ebx, ebx
0x18000ed50  jnz     short loc_18000ED66
0x18000ed52  jmp     short loc_18000ED5E
0x18000ed54  mov     edi, 0Eh
0x18000ed59  jmp     short loc_18000ED66
0x18000ed5b  mov     r14, r13
0x18000ed5e  call    cs:__imp_GetLastError
0x18000ed64  mov     edi, eax
0x18000ed66  mov     rcx, r12; hMem
0x18000ed69  call    cs:__imp_LocalFree
0x18000ed6f  mov     rcx, [rbp+57h+var_B8]; pSid
0x18000ed73  call    cs:__imp_FreeSid
0x18000ed79  mov     rcx, [rbp+57h+var_B0]; pSid
  ... truncated ...
```
