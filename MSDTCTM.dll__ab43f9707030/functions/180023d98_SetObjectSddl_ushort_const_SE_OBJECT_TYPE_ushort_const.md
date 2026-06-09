# SetObjectSddl(ushort const *,_SE_OBJECT_TYPE,ushort const *)

- ea: `0x180023d98`
- end: `0x1800240a7`
- name: `?SetObjectSddl@@YAJPEBGW4_SE_OBJECT_TYPE@@0@Z`
- size: `783`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, SE_OBJECT_TYPE ObjectType, LPCWSTR StringSecurityDescriptor)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18001facc`
- `0x18008692c`
- `0x180086b44`

## callees

- `0x1800063b0`
- `0x18002213c`
- `0x180023d98`
- `0x1800846c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002406c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002406c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023f3c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002408b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002408b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002405c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002405c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180023e42`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180023e42`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180023e8b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x180023e8b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180023ed5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180023ed5`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180023f32`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180023f32`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023e03`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180023e03`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180024002`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180024002`

## string_xrefs

- `0x180023f9f`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x180024032`: `com\complus\dtc\shared\util\msdtcsecurity.cpp`
- `0x180023ef4`: `GetSecurityDescriptorDacl failed`
- `0x180023eaa`: `GetSecurityDescriptorGroup failed`
- `0x180023e22`: `ConvertStringSecurityDescriptorToSecurityDescriptorW failed`
- `0x18002401b`: `SetNamedSecurityInfo failed`
- `0x180023e61`: `GetSecurityDescriptorOwner failed`
- `0x180023f51`: `GetSecurityDescriptorSacl failed`
- `0x180023f12`: `SetObjectSddl (com\complus\dtc\shared\util\msdtcsecurity.cpp@210): pSidDacl != NULL`
- `0x180023f72`: `SetObjectSddl (com\complus\dtc\shared\util\msdtcsecurity.cpp@226): pSidSacl != NULL`
- `0x180023f93`: `Failed to enable thread security privilege`
- `0x180024076`: `SetObjectSddl (com\complus\dtc\shared\util\msdtcsecurity.cpp@269): Unable to restore thread token`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      TraceStringInline(
        7,
        1,
        L"com\\complus\\dtc\\shared\\util\\msdtcsecurity.cpp",
        237,
        L"SetObjectSddl",
        v8,
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
0x180023d98  push    rbp
0x180023d9a  push    rbx
0x180023d9b  push    rsi
0x180023d9c  push    rdi
0x180023d9d  push    r12
0x180023d9f  push    r13
0x180023da1  push    r14
0x180023da3  push    r15
0x180023da5  lea     rbp, [rsp-1Fh]
0x180023daa  sub     rsp, 98h
0x180023db1  xor     r13d, r13d
0x180023db4  mov     rax, r8
0x180023db7  mov     r14d, edx
0x180023dba  mov     [rbp+57h+SecurityDescriptor], r13
0x180023dbe  mov     r15, rcx
0x180023dc1  mov     [rbp+57h+pOwner], r13
0x180023dc5  xor     r9d, r9d; SecurityDescriptorSize
0x180023dc8  mov     [rbp+57h+bOwnerDefaulted], r13d
0x180023dcc  lea     edi, [r13+1]
0x180023dd0  mov     [rbp+57h+pGroup], r13
0x180023dd4  mov     edx, edi; StringSDRevision
0x180023dd6  mov     [rbp+57h+bGroupDefaulted], r13d
0x180023dda  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180023dde  mov     [rbp+57h+pDacl], r13
0x180023de2  mov     rcx, rax; StringSecurityDescriptor
0x180023de5  mov     [rbp+57h+bDaclPresent], r13d
0x180023de9  mov     [rbp+57h+bDaclDefaulted], r13d
0x180023ded  mov     esi, r13d
0x180023df0  mov     [rbp+57h+pSacl], r13
0x180023df4  mov     r12d, r13d
0x180023df7  mov     [rbp+57h+bSaclPresent], r13d
0x180023dfb  mov     [rbp+57h+bSaclDefaulted], r13d
0x180023dff  mov     [rbp+57h+Token], r13
0x180023e03  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180023e09  test    eax, eax
0x180023e0b  jnz     short loc_180023E36
0x180023e0d  call    cs:__imp_GetLastError
0x180023e13  mov     ebx, eax
0x180023e15  test    eax, eax
0x180023e17  jle     short loc_180023E22
0x180023e19  movzx   ebx, ax
0x180023e1c  or      ebx, 80070000h
0x180023e22  lea     rax, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x180023e29  mov     r9d, 0A6h
0x180023e2f  mov     edx, edi
0x180023e31  jmp     loc_18002402D
0x180023e36  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180023e3a  lea     r8, [rbp+57h+bOwnerDefaulted]; lpbOwnerDefaulted
0x180023e3e  lea     rdx, [rbp+57h+pOwner]; pOwner
0x180023e42  call    cs:__imp_GetSecurityDescriptorOwner
0x180023e48  test    eax, eax
0x180023e4a  jnz     short loc_180023E70
0x180023e4c  call    cs:__imp_GetLastError
0x180023e52  mov     ebx, eax
0x180023e54  test    eax, eax
0x180023e56  jle     short loc_180023E61
0x180023e58  movzx   ebx, ax
0x180023e5b  or      ebx, 80070000h
0x180023e61  lea     rax, aGetsecuritydes_1; "GetSecurityDescriptorOwner failed"
0x180023e68  mov     r9d, 0AFh
0x180023e6e  jmp     short loc_180023E2F
0x180023e70  cmp     [rbp+57h+pOwner], r13
0x180023e74  lea     r8, [rbp+57h+bGroupDefaulted]; lpbGroupDefaulted
0x180023e78  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180023e7c  lea     rdx, [rbp+57h+pGroup]; pGroup
0x180023e80  mov     eax, 1
0x180023e85  mov     edi, r13d
0x180023e88  cmovnz  edi, eax
0x180023e8b  call    cs:__imp_GetSecurityDescriptorGroup
0x180023e91  test    eax, eax
0x180023e93  jnz     short loc_180023EBC
0x180023e95  call    cs:__imp_GetLastError
0x180023e9b  mov     ebx, eax
0x180023e9d  test    eax, eax
0x180023e9f  jle     short loc_180023EAA
0x180023ea1  movzx   ebx, ax
0x180023ea4  or      ebx, 80070000h
0x180023eaa  lea     rax, aGetsecuritydes_0; "GetSecurityDescriptorGroup failed"
0x180023eb1  mov     r9d, 0BDh
0x180023eb7  jmp     loc_180024028
0x180023ebc  cmp     [rbp+57h+pGroup], r13
0x180023ec0  jz      short loc_180023EC5
0x180023ec2  or      edi, 2
0x180023ec5  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180023ec9  lea     r9, [rbp+57h+bDaclDefaulted]; lpbDaclDefaulted
0x180023ecd  lea     r8, [rbp+57h+pDacl]; pDacl
0x180023ed1  lea     rdx, [rbp+57h+bDaclPresent]; lpbDaclPresent
0x180023ed5  call    cs:__imp_GetSecurityDescriptorDacl
0x180023edb  test    eax, eax
0x180023edd  jnz     short loc_180023F06
0x180023edf  call    cs:__imp_GetLastError
0x180023ee5  mov     ebx, eax
0x180023ee7  test    eax, eax
0x180023ee9  jle     short loc_180023EF4
0x180023eeb  movzx   ebx, ax
0x180023eee  or      ebx, 80070000h
0x180023ef4  lea     rax, aGetsecuritydes_2; "GetSecurityDescriptorDacl failed"
0x180023efb  mov     r9d, 0CCh
0x180023f01  jmp     loc_180024028
0x180023f06  cmp     [rbp+57h+bDaclPresent], r13d
0x180023f0a  jz      short loc_180023F22
0x180023f0c  cmp     [rbp+57h+pDacl], r13
0x180023f10  jnz     short loc_180023F1F
0x180023f12  lea     rcx, aSetobjectsddlC; "SetObjectSddl (com\\complus\\dtc\\share"...
0x180023f19  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180023f1f  or      edi, 4
0x180023f22  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180023f26  lea     r9, [rbp+57h+bSaclDefaulted]; lpbSaclDefaulted
0x180023f2a  lea     r8, [rbp+57h+pSacl]; pSacl
0x180023f2e  lea     rdx, [rbp+57h+bSaclPresent]; lpbSaclPresent
0x180023f32  call    cs:__imp_GetSecurityDescriptorSacl
0x180023f38  test    eax, eax
0x180023f3a  jnz     short loc_180023F63
0x180023f3c  call    cs:__imp_GetLastError
0x180023f42  mov     ebx, eax
0x180023f44  test    eax, eax
0x180023f46  jle     short loc_180023F51
0x180023f48  movzx   ebx, ax
0x180023f4b  or      ebx, 80070000h
0x180023f51  lea     rax, aGetsecuritydes; "GetSecurityDescriptorSacl failed"
0x180023f58  mov     r9d, 0DCh
0x180023f5e  jmp     loc_180024028
0x180023f63  mov     ebx, r13d
0x180023f66  cmp     [rbp+57h+bSaclPresent], r13d
0x180023f6a  jz      short loc_180023FDA
0x180023f6c  cmp     [rbp+57h+pDacl], r13
0x180023f70  jnz     short loc_180023F7F
0x180023f72  lea     rcx, aSetobjectsddlC_1; "SetObjectSddl (com\\complus\\dtc\\share"...
0x180023f79  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180023f7f  lea     rcx, [rbp+57h+Token]; void **
0x180023f83  call    ?EnableThreadSecurityPrivilege@@YAJPEAPEAX@Z; EnableThreadSecurityPrivilege(void * *)
0x180023f88  mov     ebx, eax
0x180023f8a  test    eax, eax
0x180023f8c  jns     short loc_180023FCD
0x180023f8e  mov     edx, 1
0x180023f93  lea     rax, aFailedToEnable; "Failed to enable thread security privil"...
0x180023f9a  mov     [rsp+0D0h+var_A0], rax
0x180023f9f  lea     r8, aComComplusDtcS_8; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x180023fa6  lea     rax, aSetobjectsddl; "SetObjectSddl"
0x180023fad  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x180023fb1  mov     r9d, 0EDh
0x180023fb7  mov     [rsp+0D0h+psidGroup], rax
0x180023fbc  lea     ecx, [rdx+6]
0x180023fbf  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180023fc4  mov     rsi, [rbp+57h+Token]
0x180023fc8  jmp     loc_180024053
0x180023fcd  mov     rsi, [rbp+57h+Token]
0x180023fd1  or      edi, 8
0x180023fd4  mov     r12d, 1
0x180023fda  mov     rax, [rbp+57h+pSacl]
0x180023fde  mov     r8d, edi; SecurityInfo
0x180023fe1  mov     r9, [rbp+57h+pOwner]; psidOwner
0x180023fe5  mov     edx, r14d; ObjectType
0x180023fe8  mov     [rsp+0D0h+var_A0], rax; pSacl
0x180023fed  mov     rcx, r15; pObjectName
0x180023ff0  mov     rax, [rbp+57h+pDacl]
0x180023ff4  mov     [rsp+0D0h+var_A8], rax; pDacl
0x180023ff9  mov     rax, [rbp+57h+pGroup]
0x180023ffd  mov     [rsp+0D0h+psidGroup], rax; psidGroup
0x180024002  call    cs:__imp_SetNamedSecurityInfoW
0x180024008  test    eax, eax
0x18002400a  jz      short loc_180024053
0x18002400c  jg      short loc_180024012
0x18002400e  mov     ebx, eax
0x180024010  jmp     short loc_18002401B
0x180024012  movzx   ebx, ax
0x180024015  or      ebx, 80070000h
0x18002401b  lea     rax, aSetnamedsecuri; "SetNamedSecurityInfo failed"
0x180024022  mov     r9d, 100h
0x180024028  mov     edx, 1
0x18002402d  mov     [rsp+0D0h+var_A0], rax
0x180024032  lea     r8, aComComplusDtcS_8; "com\\complus\\dtc\\shared\\util\\msdtcs"...
0x180024039  lea     rax, aSetobjectsddl; "SetObjectSddl"
0x180024040  mov     dword ptr [rsp+0D0h+var_A8], ebx
0x180024044  mov     ecx, 7
0x180024049  mov     [rsp+0D0h+psidGroup], rax
0x18002404e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180024053  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180024057  test    rcx, rcx
0x18002405a  jz      short loc_180024062
0x18002405c  call    cs:__imp_LocalFree
0x180024062  test    r12d, r12d
0x180024065  jz      short loc_180024091
0x180024067  mov     rdx, rsi; Token
0x18002406a  xor     ecx, ecx; Thread
0x18002406c  call    cs:__imp_SetThreadToken
0x180024072  test    eax, eax
0x180024074  jnz     short loc_180024083
0x180024076  lea     rcx, aSetobjectsddlC_0; "SetObjectSddl (com\\complus\\dtc\\share"...
0x18002407d  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180024083  test    rsi, rsi
0x180024086  jz      short loc_180024091
0x180024088  mov     rcx, rsi; hObject
0x18002408b  call    cs:__imp_CloseHandle
0x180024091  mov     eax, ebx
0x180024093  add     rsp, 98h
0x18002409a  pop     r15
0x18002409c  pop     r14
0x18002409e  pop     r13
0x1800240a0  pop     r12
0x1800240a2  pop     rdi
0x1800240a3  pop     rsi
0x1800240a4  pop     rbx
0x1800240a5  pop     rbp
0x1800240a6  retn
```
