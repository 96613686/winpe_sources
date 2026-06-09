# Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifyUserHasWriteAccess(void *,ushort const *)

- ea: `0x18002de3c`
- end: `0x18002dfd0`
- name: `?VerifyUserHasWriteAccess@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@SAJPEAXPEBG@Z`
- size: `404`
- prototype: `__int64 __fastcall(HANDLE ClientToken, LPCWSTR pObjectName)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18002dfd0`

## callees

- `0x18002de3c`
- `0x18003d864`
- `0x180049b50`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18002df68`
- `KERNEL32!LocalFree` at `0x18002df68`
- `KERNEL32!GetLastError` at `0x18002df72`
- `KERNEL32!GetLastError` at `0x18002df8f`
- `KERNEL32!GetLastError` at `0x18002df72`
- `KERNEL32!GetLastError` at `0x18002df8f`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18002deaf`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18002deaf`
- `ADVAPI32!MapGenericMask` at `0x18002df1c`
- `ADVAPI32!MapGenericMask` at `0x18002df1c`
- `ADVAPI32!AccessCheck` at `0x18002df5c`
- `ADVAPI32!AccessCheck` at `0x18002df5c`

## string_xrefs

- `0x18002debe`: `Failure getting security descriptor . Error Code: %#08x`
- `0x18002decc`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\SecuredDirectory.cpp`
- `0x18002df7a`: `Failure during access check. Error Code: %#08x`
- `0x18002df97`: `Write access denied to directory. Error Code: %#08x`

## pseudocode

```c
__int64 __fastcall Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifyUserHasWriteAccess(
        HANDLE ClientToken,
        LPCWSTR pObjectName)
{
  DWORD NamedSecurityInfoW; // eax
  __int64 LastError; // rbx
  __int64 result; // rax
  BOOL v6; // ebx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp+7h] BYREF
  DWORD AccessMask; // [rsp+50h] [rbp+Fh] BYREF
  DWORD PrivilegeSetLength; // [rsp+54h] [rbp+13h] BYREF
  BOOL AccessStatus; // [rsp+58h] [rbp+17h] BYREF
  GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+1Fh] BYREF
  DWORD GrantedAccess; // [rsp+70h] [rbp+2Fh] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp+37h] BYREF

  if ( !ClientToken || !pObjectName )
    return 2147942487LL;
  pSecurityDescriptor = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 7u, 0, 0, 0, 0, &pSecurityDescriptor);
  LODWORD(LastError) = NamedSecurityInfoW;
  if ( NamedSecurityInfoW )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\SecuredDirectory.cpp",
      L"Failure getting security descriptor . Error Code: %#08x",
      NamedSecurityInfoW);
  }
  else
  {
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    AccessMask = 6;
    MapGenericMask(&AccessMask, &GenericMapping);
    PrivilegeSetLength = 20;
    v6 = AccessCheck(
           pSecurityDescriptor,
           ClientToken,
           AccessMask,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus);
    LocalFree(pSecurityDescriptor);
    if ( v6 )
    {
      if ( AccessStatus )
        return 0;
      LastError = GetLastError();
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\SecuredDirectory.cpp",
        L"Write access denied to directory. Error Code: %#08x",
        LastError);
    }
    else
    {
      LastError = GetLastError();
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\SecuredDirectory.cpp",
        L"Failure during access check. Error Code: %#08x",
        LastError);
    }
  }
  result = (unsigned __int16)LastError | 0x80070000;
  if ( (int)LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x18002de3c  mov     r11, rsp
0x18002de3f  mov     [r11+18h], rbx
0x18002de43  mov     [r11+20h], rdi
0x18002de47  push    rbp
0x18002de48  lea     rbp, [r11-5Fh]
0x18002de4c  sub     rsp, 90h
0x18002de53  mov     rax, cs:__security_cookie
0x18002de5a  xor     rax, rsp
0x18002de5d  mov     [rbp+57h+var_8], rax
0x18002de61  mov     rax, rdx
0x18002de64  mov     rdi, rcx
0x18002de67  test    rcx, rcx
0x18002de6a  jz      loc_18002DFAA
0x18002de70  test    rax, rax
0x18002de73  jz      loc_18002DFAA
0x18002de79  xor     r9d, r9d; ppsidOwner
0x18002de7c  mov     [rbp+57h+pSecurityDescriptor], 0
0x18002de84  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18002de88  mov     [r11-60h], rcx
0x18002de8c  mov     rcx, rax; pObjectName
0x18002de8f  mov     qword ptr [r11-68h], 0
0x18002de97  mov     qword ptr [r11-70h], 0
0x18002de9f  lea     edx, [r9+1]; ObjectType
0x18002dea3  lea     r8d, [r9+7]; SecurityInfo
0x18002dea7  mov     qword ptr [r11-78h], 0
0x18002deaf  call    cs:__imp_GetNamedSecurityInfoW
0x18002deb5  mov     ebx, eax
0x18002deb7  test    eax, eax
0x18002deb9  jz      short loc_18002DEF1
0x18002debb  mov     r9d, eax
0x18002debe  lea     r8, aFailureGetting; "Failure getting security descriptor . E"...
0x18002dec5  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x18002decc  lea     rdx, aDAWork1SSource_5; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x18002ded3  add     rcx, 0A8h; this
0x18002deda  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18002dedf  movzx   eax, bx
0x18002dee2  or      eax, 80070000h
0x18002dee7  test    ebx, ebx
0x18002dee9  cmovle  eax, ebx
0x18002deec  jmp     loc_18002DFAF
0x18002def1  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18002def5  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18002defc  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18002df00  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18002df07  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18002df0e  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18002df15  mov     [rbp+57h+AccessMask], 6
0x18002df1c  call    cs:__imp_MapGenericMask
0x18002df22  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x18002df26  lea     rax, [rbp+57h+var_40]
0x18002df2a  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18002df2e  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18002df32  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x18002df37  mov     rdx, rdi; ClientToken
0x18002df3a  lea     rax, [rbp+57h+var_28]
0x18002df3e  mov     [rbp+57h+var_44], 14h
0x18002df45  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x18002df4a  lea     rax, [rbp+57h+var_44]
0x18002df4e  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18002df53  lea     rax, [rbp+57h+var_20]
0x18002df57  mov     [rsp+90h+PrivilegeSet], rax; PrivilegeSet
0x18002df5c  call    cs:__imp_AccessCheck
0x18002df62  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x18002df66  mov     ebx, eax
0x18002df68  call    cs:__imp_LocalFree
0x18002df6e  test    ebx, ebx
0x18002df70  jnz     short loc_18002DF89
0x18002df72  call    cs:__imp_GetLastError
0x18002df78  mov     ebx, eax
0x18002df7a  lea     r8, aFailureDuringA; "Failure during access check. Error Code"...
0x18002df81  mov     r9d, eax
0x18002df84  jmp     loc_18002DEC5
0x18002df89  cmp     [rbp+57h+var_40], 0
0x18002df8d  jnz     short loc_18002DFA6
0x18002df8f  call    cs:__imp_GetLastError
0x18002df95  mov     ebx, eax
0x18002df97  lea     r8, aWriteAccessDen; "Write access denied to directory. Error"...
0x18002df9e  mov     r9d, eax
0x18002dfa1  jmp     loc_18002DEC5
0x18002dfa6  xor     eax, eax
0x18002dfa8  jmp     short loc_18002DFAF
0x18002dfaa  mov     eax, 80070057h
0x18002dfaf  mov     rcx, [rbp+57h+var_8]
0x18002dfb3  xor     rcx, rsp; StackCookie
0x18002dfb6  call    __security_check_cookie
0x18002dfbb  lea     r11, [rsp+90h+var_s0]
0x18002dfc3  mov     rbx, [r11+20h]
0x18002dfc7  mov     rdi, [r11+28h]
0x18002dfcb  mov     rsp, r11
0x18002dfce  pop     rbp
0x18002dfcf  retn
```
