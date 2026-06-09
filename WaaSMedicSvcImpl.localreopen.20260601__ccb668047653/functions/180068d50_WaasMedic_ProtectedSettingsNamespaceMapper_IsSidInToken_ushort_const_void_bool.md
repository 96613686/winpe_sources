# WaasMedic::ProtectedSettingsNamespaceMapper::IsSidInToken(ushort const *,void *,bool &)

- ea: `0x180068d50`
- end: `0x180068ee4`
- name: `?IsSidInToken@ProtectedSettingsNamespaceMapper@WaasMedic@@YAJPEBGPEAXAEA_N@Z`
- size: `404`
- prototype: `__int64 __fastcall(const WCHAR *this, unsigned __int16 *, _BYTE *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180068840`

## callees

- `0x18002e81c`
- `0x180068d50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068daa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068e7f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068df2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180068df2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180068e41`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180068e41`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180068e75`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180068e75`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180068da0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180068da0`

## string_xrefs

- `0x180068dbf`: `Failed to convert the requested SID string representation to a SID object. Error code: 0x%08x`
- `0x180068ebf`: `IsSidInToken needs the caller's token and the SID string to check for in that token.`
- `0x180068eab`: `SID %s was found in the caller's token.`
- `0x180068e94`: `CheckTokenMembership failed to lookup SID in the token. Error code: 0x%08x`
- `0x180068e4d`: `Already impersonating the caller.`

## pseudocode

```c
__int64 __fastcall WaasMedic::ProtectedSettingsNamespaceMapper::IsSidInToken(
        const WCHAR *this,
        unsigned __int16 *a2,
        _BYTE *a3,
        bool *a4)
{
  signed int LastError; // eax
  unsigned int v8; // ebx
  signed int v9; // eax
  signed int v10; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  PSID Sid; // [rsp+38h] [rbp-8h] BYREF
  int TokenInformation; // [rsp+68h] [rbp+28h] BYREF
  WINBOOL IsMember; // [rsp+70h] [rbp+30h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+38h] BYREF

  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  Sid = 0;
  *a3 = 0;
  if ( !a2 || !this )
  {
    LogLevelW(2u, L"IsSidInToken needs the caller's token and the SID string to check for in that token.", a3, a4);
    return (unsigned int)-2147024809;
  }
  if ( !ConvertStringSidToSidW(this, &Sid) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(2u, L"Failed to convert the requested SID string representation to a SID object. Error code: 0x%08x", v8);
    return v8;
  }
  if ( !GetTokenInformation(a2, TokenType, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_8;
  if ( TokenInformation == 2 )
  {
    TokenHandle = a2;
    LogLevelW(5u, L"Already impersonating the caller.");
  }
  else if ( !DuplicateTokenEx(a2, 8u, 0, SecurityIdentification, TokenImpersonation, &TokenHandle) )
  {
LABEL_8:
    v9 = GetLastError();
    v8 = v9;
    if ( v9 > 0 )
      return (unsigned __int16)v9 | 0x80070000;
    return v8;
  }
  IsMember = 0;
  if ( CheckTokenMembership(TokenHandle, Sid, &IsMember) )
  {
    v8 = 0;
    if ( IsMember == 1 )
    {
      LogLevelW(5u, L"SID %s was found in the caller's token.", this);
      *a3 = 1;
    }
  }
  else
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    LogLevelW(2u, L"CheckTokenMembership failed to lookup SID in the token. Error code: 0x%08x", v8);
  }
  return v8;
}

```

## disassembly

```asm
0x180068d50  mov     [rsp-18h+arg_0], rbx
0x180068d55  push    rbp
0x180068d56  push    rsi
0x180068d57  push    rdi
0x180068d58  mov     rbp, rsp
0x180068d5b  sub     rsp, 40h
0x180068d5f  mov     [rbp+TokenHandle], 0
0x180068d67  mov     rsi, r8
0x180068d6a  mov     [rbp+TokenInformation], 0
0x180068d71  mov     rbx, rdx
0x180068d74  mov     [rbp+arg_18], 0
0x180068d7b  mov     rdi, rcx
0x180068d7e  mov     [rbp+Sid], 0
0x180068d86  mov     byte ptr [r8], 0
0x180068d8a  test    rdx, rdx
0x180068d8d  jz      loc_180068EBF
0x180068d93  test    rcx, rcx
0x180068d96  jz      loc_180068EBF
0x180068d9c  lea     rdx, [rbp+Sid]; Sid
0x180068da0  call    cs:__imp_ConvertStringSidToSidW
0x180068da6  test    eax, eax
0x180068da8  jnz     short loc_180068DD8
0x180068daa  call    cs:__imp_GetLastError
0x180068db0  mov     ebx, eax
0x180068db2  test    eax, eax
0x180068db4  jle     short loc_180068DBF
0x180068db6  movzx   ebx, ax
0x180068db9  or      ebx, 80070000h
0x180068dbf  lea     rdx, aFailedToConver_2; "Failed to convert the requested SID str"...
0x180068dc6  mov     r8d, ebx
0x180068dc9  mov     ecx, 2; unsigned __int8
0x180068dce  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180068dd3  jmp     loc_180068ED5
0x180068dd8  mov     r9d, 4; TokenInformationLength
0x180068dde  lea     rax, [rbp+arg_18]
0x180068de2  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180068de6  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180068deb  mov     rcx, rbx; TokenHandle
0x180068dee  lea     edx, [r9+4]; TokenInformationClass
0x180068df2  call    cs:__imp_GetTokenInformation
0x180068df8  test    eax, eax
0x180068dfa  jnz     short loc_180068E1A
0x180068dfc  call    cs:__imp_GetLastError
0x180068e02  mov     ebx, eax
0x180068e04  test    eax, eax
0x180068e06  jle     loc_180068ED5
0x180068e0c  movzx   ebx, ax
0x180068e0f  or      ebx, 80070000h
0x180068e15  jmp     loc_180068ED5
0x180068e1a  cmp     [rbp+TokenInformation], 2
0x180068e1e  jz      short loc_180068E4D
0x180068e20  mov     r9d, 1; ImpersonationLevel
0x180068e26  lea     rax, [rbp+TokenHandle]
0x180068e2a  mov     [rsp+40h+phNewToken], rax; phNewToken
0x180068e2f  xor     r8d, r8d; lpTokenAttributes
0x180068e32  mov     rcx, rbx; hExistingToken
0x180068e35  mov     dword ptr [rsp+40h+ReturnLength], 2; TokenType
0x180068e3d  lea     edx, [r9+7]; dwDesiredAccess
0x180068e41  call    cs:__imp_DuplicateTokenEx
0x180068e47  test    eax, eax
0x180068e49  jnz     short loc_180068E62
0x180068e4b  jmp     short loc_180068DFC
0x180068e4d  lea     rdx, aAlreadyImperso; "Already impersonating the caller."
0x180068e54  mov     [rbp+TokenHandle], rbx
0x180068e58  mov     ecx, 5; unsigned __int8
0x180068e5d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180068e62  mov     rdx, [rbp+Sid]; SidToCheck
0x180068e66  lea     r8, [rbp+IsMember]; IsMember
0x180068e6a  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180068e6e  mov     [rbp+IsMember], 0
0x180068e75  call    cs:__imp_CheckTokenMembership
0x180068e7b  test    eax, eax
0x180068e7d  jnz     short loc_180068EA0
0x180068e7f  call    cs:__imp_GetLastError
0x180068e85  mov     ebx, eax
0x180068e87  test    eax, eax
0x180068e89  jle     short loc_180068E94
0x180068e8b  movzx   ebx, ax
0x180068e8e  or      ebx, 80070000h
0x180068e94  lea     rdx, aChecktokenmemb; "CheckTokenMembership failed to lookup S"...
0x180068e9b  jmp     loc_180068DC6
0x180068ea0  xor     ebx, ebx
0x180068ea2  cmp     [rbp+IsMember], 1
0x180068ea6  jnz     short loc_180068ED5
0x180068ea8  mov     r8, rdi
0x180068eab  lea     rdx, aSidSWasFoundIn; "SID %s was found in the caller's token."
0x180068eb2  lea     ecx, [rbx+5]; unsigned __int8
0x180068eb5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180068eba  mov     byte ptr [rsi], 1
0x180068ebd  jmp     short loc_180068ED5
0x180068ebf  lea     rdx, aIssidintokenNe; "IsSidInToken needs the caller's token a"...
0x180068ec6  mov     ecx, 2; unsigned __int8
0x180068ecb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180068ed0  mov     ebx, 80070057h
0x180068ed5  mov     eax, ebx
0x180068ed7  mov     rbx, [rsp+40h+arg_0]
0x180068edc  add     rsp, 40h
0x180068ee0  pop     rdi
0x180068ee1  pop     rsi
0x180068ee2  pop     rbp
0x180068ee3  retn
```
