# SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)

- ea: `0x18001ce20`
- end: `0x18001d12f`
- name: `?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z`
- size: `783`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, SE_OBJECT_TYPE ObjectType, LPCWSTR StringSecurityDescriptor)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180015f84`
- `0x18001a10c`
- `0x1800737d8`
- `0x180073a3c`
- `0x180073c54`
- `0x180073e68`

## callees

- `0x180003cf0`
- `0x18000d5f4`
- `0x18001aeb8`
- `0x18001ce20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ced4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ce95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ced4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfc4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d0f4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d0f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d113`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d113`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001cf13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001cf13`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001ceca`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x18001ceca`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001cf5d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001cf5d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001cfba`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18001cfba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d0e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d0e4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001ce8b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001ce8b`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001d08a`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001d08a`

## string_xrefs

- `0x18001d027`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x18001d0ba`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x18001cf7c`: `GetSecurityDescriptorDacl failed`
- `0x18001cf32`: `GetSecurityDescriptorGroup failed`
- `0x18001ceaa`: `ConvertStringSecurityDescriptorToSecurityDescriptorW failed`
- `0x18001d0a3`: `SetNamedSecurityInfo failed`
- `0x18001cee9`: `GetSecurityDescriptorOwner failed`
- `0x18001cfd9`: `GetSecurityDescriptorSacl failed`
- `0x18001cf9a`: `SetObjectSddl (com\complus\dtc\shared\util\msdtcsecurity.cpp@210): pSidDacl != NULL`
- `0x18001cffa`: `SetObjectSddl (com\complus\dtc\shared\util\msdtcsecurity.cpp@226): pSidSacl != NULL`
- `0x18001d01b`: `Failed to enable thread security privilege`
- `0x18001d0fe`: `SetObjectSddl (com\complus\dtc\shared\util\msdtcsecurity.cpp@269): Unable to restore thread token`

## pseudocode

```c
__int64 __fastcall SetObjectSddl(LPWSTR pObjectName, SE_OBJECT_TYPE ObjectType, LPCWSTR StringSecurityDescriptor)
{
  HANDLE v5; // rsi
  int v6; // r12d
  signed int LastError; // eax
  signed int v8; // ebx
  const wchar_t *v9; // rax
  __int64 v10; // r9
  signed int v11; // eax
  SECURITY_INFORMATION v12; // edi
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  signed int v16; // eax
  PACL v18; // [rsp+28h] [rbp-51h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-39h] BYREF
  WINBOOL bSaclPresent; // [rsp+48h] [rbp-31h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-29h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+58h] [rbp-21h] BYREF
  WINBOOL bGroupDefaulted; // [rsp+5Ch] [rbp-1Dh] BYREF
  WINBOOL bDaclDefaulted; // [rsp+60h] [rbp-19h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+64h] [rbp-15h] BYREF
  HANDLE Token; // [rsp+68h] [rbp-11h] BYREF
  PSID pGroup; // [rsp+70h] [rbp-9h] BYREF
  PSID pOwner; // [rsp+78h] [rbp-1h] BYREF
  PACL pSacl; // [rsp+80h] [rbp+7h] BYREF
  WINBOOL bDaclPresent; // [rsp+F8h] [rbp+7Fh] BYREF

  SecurityDescriptor = 0;
  pOwner = 0;
  bOwnerDefaulted = 0;
  pGroup = 0;
  bGroupDefaulted = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  v5 = 0;
  pSacl = 0;
  v6 = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  Token = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v9 = L"ConvertStringSecurityDescriptorToSecurityDescriptorW failed";
    v10 = 166;
    goto LABEL_38;
  }
  if ( !GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted) )
  {
    v11 = GetLastError();
    v8 = v11;
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    v9 = L"GetSecurityDescriptorOwner failed";
    v10 = 175;
    goto LABEL_38;
  }
  v12 = pOwner != 0;
  if ( !GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bGroupDefaulted) )
  {
    v13 = GetLastError();
    v8 = v13;
    if ( v13 > 0 )
      v8 = (unsigned __int16)v13 | 0x80070000;
    v9 = L"GetSecurityDescriptorGroup failed";
    v10 = 189;
    goto LABEL_38;
  }
  if ( pGroup )
    v12 |= 2u;
  if ( !GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
  {
    v14 = GetLastError();
    v8 = v14;
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    v9 = L"GetSecurityDescriptorDacl failed";
    v10 = 204;
    goto LABEL_38;
  }
  if ( bDaclPresent )
  {
    if ( !pDacl )
      DtcInternalErrorW(L"SetObjectSddl (com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp@210): pSidDacl != NULL");
    v12 |= 4u;
  }
  if ( !GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
  {
    v15 = GetLastError();
    v8 = v15;
    if ( v15 > 0 )
      v8 = (unsigned __int16)v15 | 0x80070000;
    v9 = L"GetSecurityDescriptorSacl failed";
    v10 = 220;
    goto LABEL_38;
  }
  v8 = 0;
  if ( bSaclPresent )
  {
    if ( !pDacl )
      DtcInternalErrorW(L"SetObjectSddl (com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp@226): pSidSacl != NULL");
    v8 = EnableThreadSecurityPrivilege(&Token);
    if ( v8 < 0 )
    {
      LODWORD(v18) = v8;
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
        237,
        L"SetObjectSddl",
        v18,
        L"Failed to enable thread security privilege");
      v5 = Token;
      goto LABEL_39;
    }
    v5 = Token;
    v12 |= 8u;
    v6 = 1;
  }
  v16 = SetNamedSecurityInfoW(pObjectName, ObjectType, v12, pOwner, pGroup, pDacl, pSacl);
  if ( v16 )
  {
    if ( v16 > 0 )
      v8 = (unsigned __int16)v16 | 0x80070000;
    else
      v8 = v16;
    v9 = L"SetNamedSecurityInfo failed";
    v10 = 256;
LABEL_38:
    LODWORD(v18) = v8;
    TraceStringInline(7, 1, L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp", v10, L"SetObjectSddl", v18, v9);
  }
LABEL_39:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v6 )
  {
    if ( !SetThreadToken(0, v5) )
      DtcInternalErrorW(L"SetObjectSddl (com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp@269): Unable to restore thread token");
    if ( v5 )
      CloseHandle(v5);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ce20  push    rbp
0x18001ce22  push    rbx
0x18001ce23  push    rsi
0x18001ce24  push    rdi
0x18001ce25  push    r12
0x18001ce27  push    r13
0x18001ce29  push    r14
0x18001ce2b  push    r15
0x18001ce2d  lea     rbp, [rsp-1Fh]
0x18001ce32  sub     rsp, 98h
0x18001ce39  xor     r13d, r13d
0x18001ce3c  mov     rax, r8
0x18001ce3f  mov     r14d, edx
0x18001ce42  mov     [rbp+57h+SecurityDescriptor], r13
0x18001ce46  mov     r15, rcx
0x18001ce49  mov     [rbp+57h+pOwner], r13
0x18001ce4d  xor     r9d, r9d; SecurityDescriptorSize
0x18001ce50  mov     [rbp+57h+bOwnerDefaulted], r13d
0x18001ce54  lea     edi, [r13+1]
0x18001ce58  mov     [rbp+57h+pGroup], r13
0x18001ce5c  mov     edx, edi; StringSDRevision
0x18001ce5e  mov     [rbp+57h+bGroupDefaulted], r13d
0x18001ce62  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18001ce66  mov     [rbp+57h+pDacl], r13
0x18001ce6a  mov     rcx, rax; StringSecurityDescriptor
0x18001ce6d  mov     [rbp+57h+bDaclPresent], r13d
0x18001ce71  mov     [rbp+57h+bDaclDefaulted], r13d
0x18001ce75  mov     esi, r13d
0x18001ce78  mov     [rbp+57h+pSacl], r13
0x18001ce7c  mov     r12d, r13d
0x18001ce7f  mov     [rbp+57h+bSaclPresent], r13d
0x18001ce83  mov     [rbp+57h+bSaclDefaulted], r13d
0x18001ce87  mov     [rbp+57h+Token], r13
0x18001ce8b  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001ce91  test    eax, eax
0x18001ce93  jnz     short loc_18001CEBE
0x18001ce95  call    cs:__imp_GetLastError
0x18001ce9b  mov     ebx, eax
0x18001ce9d  test    eax, eax
0x18001ce9f  jle     short loc_18001CEAA
0x18001cea1  movzx   ebx, ax
0x18001cea4  or      ebx, 80070000h
0x18001ceaa  lea     rax, aConvertstrings_0; "ConvertStringSecurityDescriptorToSecuri"...
0x18001ceb1  mov     r9d, 0A6h
0x18001ceb7  mov     edx, edi
0x18001ceb9  jmp     loc_18001D0B5
0x18001cebe  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18001cec2  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x18001cec6  lea     rdx, [rbp+57h+pOwner]; pOwner
0x18001ceca  call    cs:__imp_GetSecurityDescriptorOwner
0x18001ced0  test    eax, eax
0x18001ced2  jnz     short loc_18001CEF8
0x18001ced4  call    cs:__imp_GetLastError
0x18001ceda  mov     ebx, eax
0x18001cedc  test    eax, eax
0x18001cede  jle     short loc_18001CEE9
0x18001cee0  movzx   ebx, ax
0x18001cee3  or      ebx, 80070000h
0x18001cee9  lea     rax, aGetsecuritydes_1; "GetSecurityDescriptorOwner failed"
0x18001cef0  mov     r9d, 0AFh
0x18001cef6  jmp     short loc_18001CEB7
0x18001cef8  cmp     [rbp+57h+pOwner], r13
0x18001cefc  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x18001cf00  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18001cf04  lea     rdx, [rbp+57h+pGroup]; pGroup
0x18001cf08  mov     eax, 1
0x18001cf0d  mov     edi, r13d
0x18001cf10  cmovnz  edi, eax
0x18001cf13  call    cs:__imp_GetSecurityDescriptorGroup
0x18001cf19  test    eax, eax
0x18001cf1b  jnz     short loc_18001CF44
0x18001cf1d  call    cs:__imp_GetLastError
0x18001cf23  mov     ebx, eax
0x18001cf25  test    eax, eax
0x18001cf27  jle     short loc_18001CF32
0x18001cf29  movzx   ebx, ax
0x18001cf2c  or      ebx, 80070000h
0x18001cf32  lea     rax, aGetsecuritydes_0; "GetSecurityDescriptorGroup failed"
0x18001cf39  mov     r9d, 0BDh
0x18001cf3f  jmp     loc_18001D0B0
0x18001cf44  cmp     [rbp+57h+pGroup], r13
0x18001cf48  jz      short loc_18001CF4D
0x18001cf4a  or      edi, 2
0x18001cf4d  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18001cf51  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x18001cf55  lea     r8, [rbp+57h+pDacl]; pDacl
0x18001cf59  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x18001cf5d  call    cs:__imp_GetSecurityDescriptorDacl
0x18001cf63  test    eax, eax
0x18001cf65  jnz     short loc_18001CF8E
0x18001cf67  call    cs:__imp_GetLastError
0x18001cf6d  mov     ebx, eax
0x18001cf6f  test    eax, eax
0x18001cf71  jle     short loc_18001CF7C
0x18001cf73  movzx   ebx, ax
0x18001cf76  or      ebx, 80070000h
0x18001cf7c  lea     rax, aGetsecuritydes_2; "GetSecurityDescriptorDacl failed"
0x18001cf83  mov     r9d, 0CCh
0x18001cf89  jmp     loc_18001D0B0
0x18001cf8e  cmp     [rbp+57h+bDaclPresent], r13d
0x18001cf92  jz      short loc_18001CFAA
0x18001cf94  cmp     [rbp+57h+pDacl], r13
0x18001cf98  jnz     short loc_18001CFA7
0x18001cf9a  lea     rcx, aSetobjectsddlC; "SetObjectSddl (com\\complus\\dtc\\share"...
0x18001cfa1  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001cfa7  or      edi, 4
0x18001cfaa  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x18001cfae  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x18001cfb2  lea     r8, [rbp+57h+pSacl]; pSacl
0x18001cfb6  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x18001cfba  call    cs:__imp_GetSecurityDescriptorSacl
0x18001cfc0  test    eax, eax
0x18001cfc2  jnz     short loc_18001CFEB
0x18001cfc4  call    cs:__imp_GetLastError
0x18001cfca  mov     ebx, eax
0x18001cfcc  test    eax, eax
0x18001cfce  jle     short loc_18001CFD9
0x18001cfd0  movzx   ebx, ax
0x18001cfd3  or      ebx, 80070000h
0x18001cfd9  lea     rax, aGetsecuritydes; "GetSecurityDescriptorSacl failed"
0x18001cfe0  mov     r9d, 0DCh
0x18001cfe6  jmp     loc_18001D0B0
0x18001cfeb  mov     ebx, r13d
0x18001cfee  cmp     [rbp+57h+bSaclPresent], r13d
0x18001cff2  jz      short loc_18001D062
0x18001cff4  cmp     [rbp+57h+pDacl], r13
0x18001cff8  jnz     short loc_18001D007
0x18001cffa  lea     rcx, aSetobjectsddlC_1; "SetObjectSddl (com\\complus\\dtc\\share"...
0x18001d001  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001d007  lea     rcx, [rbp+57h+Token]; void **
0x18001d00b  call    ?EnableThreadSecurityPrivilege@@YAJPEAPEAX@Z; EnableThreadSecurityPrivilege(void * *)
0x18001d010  mov     ebx, eax
0x18001d012  test    eax, eax
0x18001d014  jns     short loc_18001D055
0x18001d016  mov     edx, 1
0x18001d01b  lea     rax, aFailedToEnable; "Failed to enable thread security privil"...
0x18001d022  mov     [rsp+0D0h+var_A0], rax
0x18001d027  lea     r8, aComComplusDtcS_12; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x18001d02e  lea     rax, aSetobjectsddl; "SetObjectSddl"
0x18001d035  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x18001d039  mov     r9d, 0EDh
0x18001d03f  mov     [rsp+0D0h+psidGroup], rax
0x18001d044  lea     ecx, [rdx+6]
0x18001d047  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001d04c  mov     rsi, [rbp+57h+Token]
0x18001d050  jmp     loc_18001D0DB
0x18001d055  mov     rsi, [rbp+57h+Token]
0x18001d059  or      edi, 8
0x18001d05c  mov     r12d, 1
0x18001d062  mov     rax, [rbp+57h+pSacl]
0x18001d066  mov     r8d, edi; SecurityInfo
0x18001d069  mov     r9, [rbp+57h+pOwner]; psidOwner
0x18001d06d  mov     edx, r14d; ObjectType
0x18001d070  mov     [rsp+0D0h+var_A0], rax; pSacl
0x18001d075  mov     rcx, r15; pObjectName
0x18001d078  mov     rax, [rbp+57h+pDacl]
0x18001d07c  mov     [rsp+0D0h+var_A8], rax; pDacl
0x18001d081  mov     rax, [rbp+57h+pGroup]
0x18001d085  mov     [rsp+0D0h+psidGroup], rax; psidGroup
0x18001d08a  call    cs:__imp_SetNamedSecurityInfoW
0x18001d090  test    eax, eax
0x18001d092  jz      short loc_18001D0DB
0x18001d094  jg      short loc_18001D09A
0x18001d096  mov     ebx, eax
0x18001d098  jmp     short loc_18001D0A3
0x18001d09a  movzx   ebx, ax
0x18001d09d  or      ebx, 80070000h
0x18001d0a3  lea     rax, aSetnamedsecuri; "SetNamedSecurityInfo failed"
0x18001d0aa  mov     r9d, 100h
0x18001d0b0  mov     edx, 1
0x18001d0b5  mov     [rsp+0D0h+var_A0], rax
0x18001d0ba  lea     r8, aComComplusDtcS_12; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x18001d0c1  lea     rax, aSetobjectsddl; "SetObjectSddl"
0x18001d0c8  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x18001d0cc  mov     ecx, 7
0x18001d0d1  mov     [rsp+0D0h+psidGroup], rax
0x18001d0d6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001d0db  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18001d0df  test    rcx, rcx
0x18001d0e2  jz      short loc_18001D0EA
0x18001d0e4  call    cs:__imp_LocalFree
0x18001d0ea  test    r12d, r12d
0x18001d0ed  jz      short loc_18001D119
0x18001d0ef  mov     rdx, rsi; Token
0x18001d0f2  xor     ecx, ecx; Thread
0x18001d0f4  call    cs:__imp_SetThreadToken
0x18001d0fa  test    eax, eax
0x18001d0fc  jnz     short loc_18001D10B
0x18001d0fe  lea     rcx, aSetobjectsddlC_0; "SetObjectSddl (com\\complus\\dtc\\share"...
0x18001d105  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001d10b  test    rsi, rsi
0x18001d10e  jz      short loc_18001D119
0x18001d110  mov     rcx, rsi; hObject
0x18001d113  call    cs:__imp_CloseHandle
0x18001d119  mov     eax, ebx
0x18001d11b  add     rsp, 98h
0x18001d122  pop     r15
0x18001d124  pop     r14
0x18001d126  pop     r13
0x18001d128  pop     r12
0x18001d12a  pop     rdi
0x18001d12b  pop     rsi
0x18001d12c  pop     rbx
0x18001d12d  pop     rbp
0x18001d12e  retn
```
