# GetReceiptsConfiguration

- ea: `0x140044a10`
- end: `0x140044ef5`
- name: `GetReceiptsConfiguration`
- size: `1253`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140065504`

## callees

- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x140044900`
- `0x140044a10`
- `0x140065d14`
- `0x140067168`
- `0x1400708c4`
- `0x14007d2d0`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140044e7d`
- `ADVAPI32!RegCloseKey` at `0x140044e7d`
- `ADVAPI32!LogonUserW` at `0x140044dcb`
- `ADVAPI32!LogonUserW` at `0x140044dcb`
- `ADVAPI32!DuplicateToken` at `0x140044e19`
- `ADVAPI32!DuplicateToken` at `0x140044e19`
- `KERNEL32!GetLastError` at `0x140044c34`
- `KERNEL32!GetLastError` at `0x140044dd5`
- `KERNEL32!GetLastError` at `0x140044e23`
- `KERNEL32!GetLastError` at `0x140044c34`
- `KERNEL32!GetLastError` at `0x140044dd5`
- `KERNEL32!GetLastError` at `0x140044e23`
- `KERNEL32!EnterCriticalSection` at `0x140044adf`
- `KERNEL32!EnterCriticalSection` at `0x140044adf`
- `KERNEL32!LeaveCriticalSection` at `0x140044e6f`
- `KERNEL32!LeaveCriticalSection` at `0x140044e6f`
- `credui!CredUIParseUserNameW` at `0x140044d52`
- `credui!CredUIParseUserNameW` at `0x140044d52`

## pseudocode

```c
__int64 __fastcall GetReceiptsConfiguration(_QWORD *a1, int a2)
{
  void *v4; // rax
  void *v5; // rsi
  HKEY v7; // r15
  __int64 v8; // rax
  unsigned int v9; // ebx
  CMapDeviceId *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rax
  HKEY v14; // rax
  DWORD LastError; // eax
  __int64 RegistrySecureString; // rax
  HANDLE v17; // rcx
  DWORD v18; // eax
  CMapDeviceId *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // eax
  HANDLE ExistingTokenHandle; // [rsp+30h] [rbp-D0h] BYREF
  void *DuplicateTokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR domain[344]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR user[520]; // [rsp+2F0h] [rbp+1F0h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
  }
  v4 = (void *)pMemAlloc(0x50u);
  v5 = v4;
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
    }
    return 8;
  }
  v7 = 0;
  memset_0(v4, 0, 0x50u);
  EnterCriticalSection(&g_CsConfig);
  *(_DWORD *)v5 = 80;
  *((_DWORD *)v5 + 16) = dword_1400A1680;
  *((_DWORD *)v5 + 8) = *(_DWORD *)&dword_1400A1660;
  *((_DWORD *)v5 + 1) = dword_1400A1644;
  *((_DWORD *)v5 + 2) = dword_1400A1648;
  *((_QWORD *)v5 + 2) = 0;
  if ( qword_1400A1658 )
  {
    v8 = StringDup(qword_1400A1658);
    *((_QWORD *)v5 + 3) = v8;
    if ( !v8 )
    {
      v9 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v11 = 48;
      goto LABEL_17;
    }
  }
  if ( qword_1400A1668 )
  {
    v12 = StringDup(qword_1400A1668);
    *((_QWORD *)v5 + 5) = v12;
    if ( !v12 )
    {
      v9 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v11 = 49;
      goto LABEL_17;
    }
  }
  if ( UserName )
  {
    v13 = StringDup((unsigned __int16 *)UserName);
    *((_QWORD *)v5 + 6) = v13;
    if ( !v13 )
    {
      v9 = 8;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v11 = 50;
      goto LABEL_17;
    }
  }
  v14 = OpenRegistryKey(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Receipts", 0, 0x2001Fu);
  v7 = v14;
  if ( !v14 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, LastError);
    }
    goto LABEL_62;
  }
  RegistrySecureString = GetRegistrySecureString(v14, 0);
  *((_QWORD *)v5 + 7) = RegistrySecureString;
  if ( !RegistrySecureString )
  {
    v9 = 8;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_62;
    }
    v11 = 52;
LABEL_17:
    WPP_SF_(*((_QWORD *)v10 + 2), v11, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids);
    goto LABEL_62;
  }
  v9 = 0;
  if ( a2 && dword_1400A1648 == 2 )
  {
    v17 = hObject;
    DuplicateTokenHandle = 0;
    if ( !hObject )
    {
      ExistingTokenHandle = 0;
      memset_0(user, 0, 0x402u);
      memset_0(domain, 0, 0x2A2u);
      v18 = CredUIParseUserNameW(UserName, user, 0x201u, domain, 0x151u);
      v9 = v18;
      if ( v18 )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v20 = 53;
        goto LABEL_48;
      }
      if ( !LogonUserW(user, domain, *((LPCWSTR *)v5 + 7), 2u, 0, &ExistingTokenHandle) )
      {
        v18 = GetLastError();
        v9 = v18;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_62;
        }
        v20 = 54;
        goto LABEL_48;
      }
      v17 = ExistingTokenHandle;
      hObject = ExistingTokenHandle;
    }
    if ( !DuplicateToken(v17, SecurityDelegation, &DuplicateTokenHandle) )
    {
      v18 = GetLastError();
      v9 = v18;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_62;
      }
      v20 = 55;
LABEL_48:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v18);
      goto LABEL_62;
    }
    *((_QWORD *)v5 + 9) = DuplicateTokenHandle;
  }
  *a1 = v5;
LABEL_62:
  LeaveCriticalSection(&g_CsConfig);
  if ( v7 )
  {
    v21 = RegCloseKey(v7);
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_4d881010f3a23632d10eb614fe27c918_Traceguids, v21);
      }
    }
  }
  if ( v9 )
    FreeReceiptsConfiguration(v5);
  return v9;
}

```

## disassembly

```asm
0x140044a10  mov     [rsp-8+arg_8], rbx
0x140044a15  mov     [rsp-8+arg_10], rsi
0x140044a1a  push    rbp
0x140044a1b  push    rdi
0x140044a1c  push    r12
0x140044a1e  push    r14
0x140044a20  push    r15
0x140044a22  lea     rbp, [rsp-610h]
0x140044a2a  sub     rsp, 710h
0x140044a31  mov     rax, cs:__security_cookie
0x140044a38  xor     rax, rsp
0x140044a3b  mov     [rbp+630h+var_30], rax
0x140044a42  mov     r14d, edx
0x140044a45  mov     r12, rcx
0x140044a48  mov     rcx, cs:WPP_GLOBAL_Control
0x140044a4f  lea     rbx, WPP_GLOBAL_Control
0x140044a56  cmp     rcx, rbx
0x140044a59  jz      short loc_140044A7C
0x140044a5b  test    byte ptr [rcx+1Ch], 4
0x140044a5f  jz      short loc_140044A7C
0x140044a61  cmp     byte ptr [rcx+19h], 5
0x140044a65  jb      short loc_140044A7C
0x140044a67  mov     rcx, [rcx+10h]
0x140044a6b  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140044a72  mov     edx, 2Eh ; '.'
0x140044a77  call    WPP_SF_
0x140044a7c  mov     edi, 50h ; 'P'
0x140044a81  mov     ecx, edi; dwBytes
0x140044a83  call    pMemAlloc
0x140044a88  mov     rsi, rax
0x140044a8b  test    rax, rax
0x140044a8e  jnz     short loc_140044AC8
0x140044a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140044a97  cmp     rcx, rbx
0x140044a9a  jz      short loc_140044ABE
0x140044a9c  test    byte ptr [rcx+1Ch], 4
0x140044aa0  jz      short loc_140044ABE
0x140044aa2  lea     edi, [rax+2]
0x140044aa5  cmp     [rcx+19h], dil
0x140044aa9  jb      short loc_140044ABE
0x140044aab  mov     rcx, [rcx+10h]
0x140044aaf  lea     edx, [rax+2Fh]
0x140044ab2  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140044ab9  call    WPP_SF_
0x140044abe  mov     eax, 8
0x140044ac3  jmp     loc_140044ECA
0x140044ac8  mov     r8, rdi; Size
0x140044acb  xor     edx, edx; Val
0x140044acd  mov     rcx, rsi; void *
0x140044ad0  xor     r15d, r15d
0x140044ad3  call    memset_0
0x140044ad8  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140044adf  call    cs:__imp_EnterCriticalSection
0x140044ae5  mov     [rsi], edi
0x140044ae7  lea     edi, [r15+2]
0x140044aeb  mov     eax, cs:dword_1400A1680
0x140044af1  mov     [rsi+40h], eax
0x140044af4  mov     eax, cs:dword_1400A1660
0x140044afa  mov     [rsi+20h], eax
0x140044afd  mov     eax, cs:dword_1400A1644
0x140044b03  mov     [rsi+4], eax
0x140044b06  mov     eax, cs:dword_1400A1648
0x140044b0c  mov     [rsi+8], eax
0x140044b0f  mov     [rsi+10h], r15
0x140044b13  mov     rcx, cs:qword_1400A1658; unsigned __int16 *
0x140044b1a  test    rcx, rcx
0x140044b1d  jz      short loc_140044B73
0x140044b1f  call    StringDup
0x140044b24  mov     [rsi+18h], rax
0x140044b28  test    rax, rax
0x140044b2b  jnz     short loc_140044B73
0x140044b2d  lea     ebx, [rdi+6]
0x140044b30  mov     rcx, cs:WPP_GLOBAL_Control
0x140044b37  lea     r14, WPP_GLOBAL_Control
0x140044b3e  cmp     rcx, r14
0x140044b41  jz      loc_140044E68
0x140044b47  test    byte ptr [rcx+1Ch], 4
0x140044b4b  jz      loc_140044E68
0x140044b51  cmp     [rcx+19h], dil
0x140044b55  jb      loc_140044E68
0x140044b5b  lea     edx, [rdi+2Eh]
0x140044b5e  mov     rcx, [rcx+10h]
0x140044b62  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140044b69  call    WPP_SF_
0x140044b6e  jmp     loc_140044E68
0x140044b73  mov     rcx, cs:qword_1400A1668; unsigned __int16 *
0x140044b7a  test    rcx, rcx
0x140044b7d  jz      short loc_140044BC0
0x140044b7f  call    StringDup
0x140044b84  mov     [rsi+28h], rax
0x140044b88  test    rax, rax
0x140044b8b  jnz     short loc_140044BC0
0x140044b8d  lea     ebx, [rax+8]
0x140044b90  mov     rcx, cs:WPP_GLOBAL_Control
0x140044b97  lea     r14, WPP_GLOBAL_Control
0x140044b9e  cmp     rcx, r14
0x140044ba1  jz      loc_140044E68
0x140044ba7  test    byte ptr [rcx+1Ch], 4
0x140044bab  jz      loc_140044E68
0x140044bb1  cmp     [rcx+19h], dil
0x140044bb5  jb      loc_140044E68
0x140044bbb  lea     edx, [rax+31h]
0x140044bbe  jmp     short loc_140044B5E
0x140044bc0  mov     rcx, cs:UserName; unsigned __int16 *
0x140044bc7  test    rcx, rcx
0x140044bca  jz      short loc_140044C10
0x140044bcc  call    StringDup
0x140044bd1  mov     [rsi+30h], rax
0x140044bd5  test    rax, rax
0x140044bd8  jnz     short loc_140044C10
0x140044bda  lea     ebx, [rax+8]
0x140044bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140044be4  lea     r14, WPP_GLOBAL_Control
0x140044beb  cmp     rcx, r14
0x140044bee  jz      loc_140044E68
0x140044bf4  test    byte ptr [rcx+1Ch], 4
0x140044bf8  jz      loc_140044E68
0x140044bfe  cmp     [rcx+19h], dil
0x140044c02  jb      loc_140044E68
0x140044c08  lea     edx, [rax+32h]
0x140044c0b  jmp     loc_140044B5E
0x140044c10  mov     r9d, 2001Fh
0x140044c16  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Fax\\Receipts"
0x140044c1d  xor     r8d, r8d
0x140044c20  mov     rcx, 0FFFFFFFF80000002h
0x140044c27  call    OpenRegistryKey
0x140044c2c  mov     r15, rax
0x140044c2f  test    rax, rax
0x140044c32  jnz     short loc_140044C83
0x140044c34  call    cs:__imp_GetLastError
0x140044c3a  mov     ebx, eax
0x140044c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x140044c43  lea     r14, WPP_GLOBAL_Control
0x140044c4a  cmp     rcx, r14
0x140044c4d  jz      loc_140044E68
0x140044c53  test    byte ptr [rcx+1Ch], 4
0x140044c57  jz      loc_140044E68
0x140044c5d  cmp     [rcx+19h], dil
0x140044c61  jb      loc_140044E68
0x140044c67  mov     rcx, [rcx+10h]
0x140044c6b  lea     edx, [r15+33h]
0x140044c6f  mov     r9d, eax
0x140044c72  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140044c79  call    WPP_SF_d
0x140044c7e  jmp     loc_140044E68
0x140044c83  lea     r8, Class
0x140044c8a  mov     qword ptr [rsp+730h+domainBufferSize], 0; __int64
0x140044c93  mov     rcx, rax; hKey
0x140044c96  call    GetRegistrySecureString
0x140044c9b  mov     [rsi+38h], rax
0x140044c9f  test    rax, rax
0x140044ca2  jnz     short loc_140044CDA
0x140044ca4  lea     ebx, [rax+8]
0x140044ca7  mov     rcx, cs:WPP_GLOBAL_Control
0x140044cae  lea     r14, WPP_GLOBAL_Control
0x140044cb5  cmp     rcx, r14
0x140044cb8  jz      loc_140044E68
0x140044cbe  test    byte ptr [rcx+1Ch], 4
0x140044cc2  jz      loc_140044E68
0x140044cc8  cmp     [rcx+19h], dil
0x140044ccc  jb      loc_140044E68
0x140044cd2  lea     edx, [rax+34h]
0x140044cd5  jmp     loc_140044B5E
0x140044cda  xor     ebx, ebx
0x140044cdc  test    r14d, r14d
0x140044cdf  jz      loc_140044E5D
0x140044ce5  cmp     cs:dword_1400A1648, edi
0x140044ceb  jnz     loc_140044E5D
0x140044cf1  mov     rcx, cs:hObject
0x140044cf8  mov     [rsp+730h+DuplicateTokenHandle], rbx
0x140044cfd  test    rcx, rcx
0x140044d00  jnz     loc_140044E0F
0x140044d06  xor     edx, edx; Val
0x140044d08  mov     [rsp+730h+ExistingTokenHandle], rbx
0x140044d0d  mov     r8d, 402h; Size
0x140044d13  lea     rcx, [rbp+630h+user]; void *
0x140044d1a  call    memset_0
0x140044d1f  xor     edx, edx; Val
0x140044d21  lea     rcx, [rsp+730h+domain]; void *
0x140044d26  mov     r8d, 2A2h; Size
0x140044d2c  call    memset_0
0x140044d31  mov     rcx, cs:UserName; UserName
0x140044d38  lea     r9, [rsp+730h+domain]; domain
0x140044d3d  mov     r8d, 201h; userBufferSize
0x140044d43  mov     [rsp+730h+domainBufferSize], 151h; domainBufferSize
0x140044d4b  lea     rdx, [rbp+630h+user]; user
0x140044d52  call    cs:__imp_CredUIParseUserNameW
0x140044d58  mov     ebx, eax
0x140044d5a  test    eax, eax
0x140044d5c  jz      short loc_140044DA6
0x140044d5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140044d65  lea     r14, WPP_GLOBAL_Control
0x140044d6c  cmp     rcx, r14
0x140044d6f  jz      loc_140044E68
0x140044d75  test    byte ptr [rcx+1Ch], 4
0x140044d79  jz      loc_140044E68
0x140044d7f  cmp     [rcx+19h], dil
0x140044d83  jb      loc_140044E68
0x140044d89  mov     edx, 35h ; '5'
0x140044d8e  mov     rcx, [rcx+10h]
0x140044d92  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140044d99  mov     r9d, eax
0x140044d9c  call    WPP_SF_d
0x140044da1  jmp     loc_140044E68
0x140044da6  mov     r8, [rsi+38h]; lpszPassword
0x140044daa  lea     rax, [rsp+730h+ExistingTokenHandle]
0x140044daf  mov     [rsp+730h+phToken], rax; phToken
0x140044db4  lea     rdx, [rsp+730h+domain]; lpszDomain
0x140044db9  mov     r9d, edi; dwLogonType
0x140044dbc  mov     [rsp+730h+domainBufferSize], 0; dwLogonProvider
0x140044dc4  lea     rcx, [rbp+630h+user]; lpszUsername
0x140044dcb  call    cs:__imp_LogonUserW
0x140044dd1  test    eax, eax
0x140044dd3  jnz     short loc_140044E03
0x140044dd5  call    cs:__imp_GetLastError
0x140044ddb  mov     ebx, eax
0x140044ddd  mov     rcx, cs:WPP_GLOBAL_Control
0x140044de4  lea     r14, WPP_GLOBAL_Control
0x140044deb  cmp     rcx, r14
0x140044dee  jz      short loc_140044E68
0x140044df0  test    byte ptr [rcx+1Ch], 4
0x140044df4  jz      short loc_140044E68
0x140044df6  cmp     [rcx+19h], dil
0x140044dfa  jb      short loc_140044E68
0x140044dfc  mov     edx, 36h ; '6'
0x140044e01  jmp     short loc_140044D8E
0x140044e03  mov     rcx, [rsp+730h+ExistingTokenHandle]; ExistingTokenHandle
0x140044e08  mov     cs:hObject, rcx
0x140044e0f  lea     r8, [rsp+730h+DuplicateTokenHandle]; DuplicateTokenHandle
0x140044e14  mov     edx, 3; ImpersonationLevel
0x140044e19  call    cs:__imp_DuplicateToken
0x140044e1f  test    eax, eax
0x140044e21  jnz     short loc_140044E54
0x140044e23  call    cs:__imp_GetLastError
0x140044e29  mov     ebx, eax
0x140044e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e32  lea     r14, WPP_GLOBAL_Control
0x140044e39  cmp     rcx, r14
0x140044e3c  jz      short loc_140044E68
0x140044e3e  test    byte ptr [rcx+1Ch], 4
0x140044e42  jz      short loc_140044E68
0x140044e44  cmp     [rcx+19h], dil
0x140044e48  jb      short loc_140044E68
0x140044e4a  mov     edx, 37h ; '7'
0x140044e4f  jmp     loc_140044D8E
0x140044e54  mov     rax, [rsp+730h+DuplicateTokenHandle]
0x140044e59  mov     [rsi+48h], rax
0x140044e5d  mov     [r12], rsi
0x140044e61  lea     r14, WPP_GLOBAL_Control
0x140044e68  lea     rcx, ?g_CsConfig@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140044e6f  call    cs:__imp_LeaveCriticalSection
0x140044e75  test    r15, r15
0x140044e78  jz      short loc_140044EB7
0x140044e7a  mov     rcx, r15; hKey
0x140044e7d  call    cs:__imp_RegCloseKey
0x140044e83  test    eax, eax
0x140044e85  jz      short loc_140044EB7
0x140044e87  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e8e  cmp     rcx, r14
0x140044e91  jz      short loc_140044EB7
0x140044e93  test    byte ptr [rcx+1Ch], 4
0x140044e97  jz      short loc_140044EB7
0x140044e99  cmp     [rcx+19h], dil
0x140044e9d  jb      short loc_140044EB7
0x140044e9f  mov     rcx, [rcx+10h]
0x140044ea3  lea     r8, WPP_4d881010f3a23632d10eb614fe27c918_Traceguids
0x140044eaa  mov     edx, 38h ; '8'
0x140044eaf  mov     r9d, eax
0x140044eb2  call    WPP_SF_d
0x140044eb7  test    ebx, ebx
0x140044eb9  jz      short loc_140044EC8
0x140044ebb  mov     edx, 1
0x140044ec0  mov     rcx, rsi; lpMem
0x140044ec3  call    FreeReceiptsConfiguration
0x140044ec8  mov     eax, ebx
0x140044eca  mov     rcx, [rbp+630h+var_30]
0x140044ed1  xor     rcx, rsp; StackCookie
0x140044ed4  call    __security_check_cookie
0x140044ed9  lea     r11, [rsp+730h+var_20]
0x140044ee1  mov     rbx, [r11+38h]
0x140044ee5  mov     rsi, [r11+40h]
0x140044ee9  mov     rsp, r11
0x140044eec  pop     r15
0x140044eee  pop     r14
0x140044ef0  pop     r12
0x140044ef2  pop     rdi
0x140044ef3  pop     rbp
0x140044ef4  retn
```
