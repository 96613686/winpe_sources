# ScriptUtils::CheckUsersGrpReadOnly(ushort const *)

- ea: `0x14002c950`
- end: `0x14002cbc3`
- name: `?CheckUsersGrpReadOnly@ScriptUtils@@YAJPEBG@Z`
- size: `627`
- prototype: `__int64 __fastcall(LPCWSTR pObjectName, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140030d94`
- `0x1400380cc`

## callees

- `0x14002c950`
- `0x14002cbcc`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x14002c9e1`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x14002c9e1`
- `ADVAPI32!CreateWellKnownSid` at `0x14002caa9`
- `ADVAPI32!CreateWellKnownSid` at `0x14002caa9`
- `KERNEL32!LocalFree` at `0x14002cb8c`
- `KERNEL32!LocalFree` at `0x14002cb8c`
- `KERNEL32!GetLastError` at `0x14002caef`
- `KERNEL32!GetLastError` at `0x14002caef`
- `KERNEL32!IsDebuggerPresent` at `0x14002ca34`
- `KERNEL32!IsDebuggerPresent` at `0x14002cb46`
- `KERNEL32!IsDebuggerPresent` at `0x14002ca34`
- `KERNEL32!IsDebuggerPresent` at `0x14002cb46`

## string_xrefs

- `0x14002ca13`: `ScriptUtils::CheckUsersGrpReadOnly`
- `0x14002cb12`: `ScriptUtils::CheckUsersGrpReadOnly`
- `0x14002cb99`: `ScriptUtils::CheckUsersGrpReadOnly - File "%s" is not readonly for regular users!`

## pseudocode

```c
__int64 __fastcall ScriptUtils::CheckUsersGrpReadOnly(LPCWSTR pObjectName, const unsigned __int16 *a2)
{
  signed int NamedSecurityInfoW; // eax
  signed int AllowedRightsFromAcl; // ebx
  bool v5; // zf
  const unsigned __int16 *v6; // rax
  __int64 v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdi
  unsigned int *v10; // r9
  signed int LastError; // eax
  PACL *ppSacl; // [rsp+30h] [rbp-69h]
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // [rsp+38h] [rbp-61h]
  __int64 cbSid; // [rsp+40h] [rbp-59h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-51h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+50h] [rbp-49h] BYREF
  PSID ppsidOwner; // [rsp+58h] [rbp-41h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-39h] BYREF

  memset_0(pSid, 0, 0x44u);
  cbSid = 0;
  ppsidOwner = 0;
  pAcl = 0;
  hMem = 0;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 5u, &ppsidOwner, 0, &pAcl, 0, &hMem);
  AllowedRightsFromAcl = NamedSecurityInfoW;
  if ( NamedSecurityInfoW )
  {
    if ( NamedSecurityInfoW > 0 )
      AllowedRightsFromAcl = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
      0xD6u,
      L"ScriptUtils::CheckUsersGrpReadOnly",
      L"CBRAEx",
      L"err == 0L",
      AllowedRightsFromAcl);
    v5 = !IsDebuggerPresent();
    v6 = L"err == 0L";
    if ( !v5 )
    {
      v7 = 214;
LABEL_6:
      LODWORD(ppSecurityDescriptor) = AllowedRightsFromAcl;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
        v7,
        L"ScriptUtils::CheckUsersGrpReadOnly",
        L"CBRAEx",
        v6,
        ppSecurityDescriptor,
        cbSid);
      goto LABEL_23;
    }
    v8 = 214;
  }
  else
  {
    v9 = 0;
    while ( 1 )
    {
      memset_0(pSid, 0, 0x44u);
      LODWORD(cbSid) = 68;
      if ( !CreateWellKnownSid(*(WELL_KNOWN_SID_TYPE *)&asc_1400B7E20[2 * v9], 0, pSid, (DWORD *)&cbSid) )
        break;
      AllowedRightsFromAcl = ScriptUtils::GetAllowedRightsFromAcl(pAcl, pSid, (char *)&cbSid + 4, v10);
      if ( AllowedRightsFromAcl < 0 )
        goto LABEL_23;
      if ( (cbSid & 0xD011600000000LL) != 0 )
      {
        AllowedRightsFromAcl = -2147023560;
        goto LABEL_23;
      }
      if ( (unsigned __int64)++v9 >= 4 )
        goto LABEL_23;
    }
    LastError = GetLastError();
    AllowedRightsFromAcl = LastError;
    if ( LastError > 0 )
      AllowedRightsFromAcl = (unsigned __int16)LastError | 0x80070000;
    if ( AllowedRightsFromAcl >= 0 )
      AllowedRightsFromAcl = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
      0xE3u,
      L"ScriptUtils::CheckUsersGrpReadOnly",
      L"CBRAEx",
      L"fSuccess",
      AllowedRightsFromAcl);
    v5 = !IsDebuggerPresent();
    v6 = L"fSuccess";
    if ( !v5 )
    {
      v7 = 227;
      goto LABEL_6;
    }
    v8 = 227;
  }
  LODWORD(ppSacl) = AllowedRightsFromAcl;
  DEBUGMSGBOX(
    L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
    L"termsrv\\wms\\src\\devices\\wmssvc\\scriptutils.cpp",
    v8,
    L"ScriptUtils::CheckUsersGrpReadOnly",
    L"CBRAEx",
    v6,
    ppSacl);
LABEL_23:
  LocalFree(hMem);
  if ( AllowedRightsFromAcl < 0 )
    DEBUGMSG(L"ScriptUtils::CheckUsersGrpReadOnly - File \"%s\" is not readonly for regular users!", pObjectName);
  return (unsigned int)AllowedRightsFromAcl;
}

```

## disassembly

```asm
0x14002c950  push    rbp
0x14002c952  push    rbx
0x14002c953  push    rsi
0x14002c954  push    rdi
0x14002c955  push    r14
0x14002c957  push    r15
0x14002c959  lea     rbp, [rsp-2Fh]
0x14002c95e  sub     rsp, 0C8h
0x14002c965  mov     rax, cs:__security_cookie
0x14002c96c  xor     rax, rsp
0x14002c96f  mov     [rbp+57h+var_40], rax
0x14002c973  mov     r15, rcx
0x14002c976  mov     esi, 44h ; 'D'
0x14002c97b  mov     r8d, esi; Size
0x14002c97e  lea     rcx, [rbp+57h+pSid]; void *
0x14002c982  xor     edx, edx; Val
0x14002c984  call    memset_0
0x14002c989  lea     rax, [rbp+57h+hMem]
0x14002c98d  mov     [rbp+57h+cbSid], 0
0x14002c994  mov     [rsp+0F0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x14002c999  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x14002c99d  lea     rax, [rbp+57h+pAcl]
0x14002c9a1  mov     [rsp+0F0h+ppSacl], 0; ppSacl
0x14002c9aa  mov     [rsp+0F0h+ppDacl], rax; ppDacl
0x14002c9af  lea     edx, [rsi-43h]; ObjectType
0x14002c9b2  lea     r8d, [rsi-3Fh]; SecurityInfo
0x14002c9b6  mov     [rsp+0F0h+ppsidGroup], 0; ppsidGroup
0x14002c9bf  mov     rcx, r15; pObjectName
0x14002c9c2  mov     [rbp+57h+var_AC], 0
0x14002c9c9  mov     [rbp+57h+ppsidOwner], 0
0x14002c9d1  mov     [rbp+57h+pAcl], 0
0x14002c9d9  mov     [rbp+57h+hMem], 0
0x14002c9e1  call    cs:__imp_GetNamedSecurityInfoW
0x14002c9e7  mov     ebx, eax
0x14002c9e9  test    eax, eax
0x14002c9eb  jz      loc_14002CA82
0x14002c9f1  jle     short loc_14002C9FC
0x14002c9f3  movzx   ebx, ax
0x14002c9f6  or      ebx, 80070000h
0x14002c9fc  lea     rax, aErr0l; "err == 0L"
0x14002ca03  mov     dword ptr [rsp+0F0h+ppDacl], ebx; int
0x14002ca07  lea     r14, aCbraex; "CBRAEx"
0x14002ca0e  mov     [rsp+0F0h+ppsidGroup], rax; unsigned __int16 *
0x14002ca13  lea     rsi, aScriptutilsChe_1; "ScriptUtils::CheckUsersGrpReadOnly"
0x14002ca1a  mov     r9, r14; unsigned __int16 *
0x14002ca1d  lea     rdi, aTermsrvWmsSrcD_1; "termsrv\\wms\\src\\devices\\wmssvc\\scr"...
0x14002ca24  mov     r8, rsi; unsigned __int16 *
0x14002ca27  mov     rcx, rdi; unsigned __int16 *
0x14002ca2a  mov     edx, 0D6h; unsigned int
0x14002ca2f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002ca34  call    cs:__imp_IsDebuggerPresent
0x14002ca3a  test    eax, eax
0x14002ca3c  lea     rax, aErr0l; "err == 0L"
0x14002ca43  jz      short loc_14002CA77
0x14002ca45  mov     r9d, 0D6h
0x14002ca4b  mov     dword ptr [rsp+0F0h+ppSecurityDescriptor], ebx
0x14002ca4f  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14002ca56  mov     [rsp+0F0h+ppSacl], rax
0x14002ca5b  mov     r8, rdi
0x14002ca5e  mov     [rsp+0F0h+ppDacl], r14
0x14002ca63  mov     ecx, 2; unsigned __int8
0x14002ca68  mov     [rsp+0F0h+ppsidGroup], rsi
0x14002ca6d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14002ca72  jmp     loc_14002CB88
0x14002ca77  mov     r8d, 0D6h
0x14002ca7d  jmp     loc_14002CB68
0x14002ca82  xor     edi, edi
0x14002ca84  mov     r8, rsi; Size
0x14002ca87  lea     rcx, [rbp+57h+pSid]; void *
0x14002ca8b  xor     edx, edx; Val
0x14002ca8d  call    memset_0
0x14002ca92  lea     rcx, asc_1400B7E20; "\x1B"
0x14002ca99  mov     [rbp+57h+cbSid], esi
0x14002ca9c  mov     ecx, [rcx+rdi*4]; WellKnownSidType
0x14002ca9f  lea     r9, [rbp+57h+cbSid]; cbSid
0x14002caa3  lea     r8, [rbp+57h+pSid]; pSid
0x14002caa7  xor     edx, edx; DomainSid
0x14002caa9  call    cs:__imp_CreateWellKnownSid
0x14002caaf  test    eax, eax
0x14002cab1  jz      short loc_14002CAEF
0x14002cab3  mov     rcx, [rbp+57h+pAcl]; pAcl
0x14002cab7  lea     r8, [rbp+57h+var_AC]; void *
0x14002cabb  lea     rdx, [rbp+57h+pSid]; pSid1
0x14002cabf  call    ?GetAllowedRightsFromAcl@ScriptUtils@@YAJPEAU_ACL@@PEAXPEAK@Z; ScriptUtils::GetAllowedRightsFromAcl(_ACL *,void *,ulong *)
0x14002cac4  mov     ebx, eax
0x14002cac6  test    eax, eax
0x14002cac8  js      loc_14002CB88
0x14002cace  test    [rbp+57h+var_AC], 0D0116h
0x14002cad5  jnz     short loc_14002CAE5
0x14002cad7  inc     rdi
0x14002cada  cmp     rdi, 4
0x14002cade  jb      short loc_14002CA84
0x14002cae0  jmp     loc_14002CB88
0x14002cae5  mov     ebx, 80070538h
0x14002caea  jmp     loc_14002CB88
0x14002caef  call    cs:__imp_GetLastError
0x14002caf5  mov     ebx, eax
0x14002caf7  test    eax, eax
0x14002caf9  jle     short loc_14002CB04
0x14002cafb  movzx   ebx, ax
0x14002cafe  or      ebx, 80070000h
0x14002cb04  mov     eax, 80004005h
0x14002cb09  lea     r14, aCbraex; "CBRAEx"
0x14002cb10  test    ebx, ebx
0x14002cb12  lea     rsi, aScriptutilsChe_1; "ScriptUtils::CheckUsersGrpReadOnly"
0x14002cb19  lea     rdi, aTermsrvWmsSrcD_1; "termsrv\\wms\\src\\devices\\wmssvc\\scr"...
0x14002cb20  mov     r9, r14; unsigned __int16 *
0x14002cb23  cmovns  ebx, eax
0x14002cb26  mov     r8, rsi; unsigned __int16 *
0x14002cb29  lea     rax, aFsuccess; "fSuccess"
0x14002cb30  mov     dword ptr [rsp+0F0h+ppDacl], ebx; int
0x14002cb34  mov     edx, 0E3h; unsigned int
0x14002cb39  mov     [rsp+0F0h+ppsidGroup], rax; unsigned __int16 *
0x14002cb3e  mov     rcx, rdi; unsigned __int16 *
0x14002cb41  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14002cb46  call    cs:__imp_IsDebuggerPresent
0x14002cb4c  test    eax, eax
0x14002cb4e  lea     rax, aFsuccess; "fSuccess"
0x14002cb55  jz      short loc_14002CB62
0x14002cb57  mov     r9d, 0E3h
0x14002cb5d  jmp     loc_14002CA4B
0x14002cb62  mov     r8d, 0E3h
0x14002cb68  mov     dword ptr [rsp+0F0h+ppSacl], ebx
0x14002cb6c  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14002cb73  mov     [rsp+0F0h+ppDacl], rax
0x14002cb78  mov     r9, rsi
0x14002cb7b  mov     rdx, rdi
0x14002cb7e  mov     [rsp+0F0h+ppsidGroup], r14
0x14002cb83  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14002cb88  mov     rcx, [rbp+57h+hMem]; hMem
0x14002cb8c  call    cs:__imp_LocalFree
0x14002cb92  test    ebx, ebx
0x14002cb94  jns     short loc_14002CBA5
0x14002cb96  mov     rdx, r15
0x14002cb99  lea     rcx, aScriptutilsChe_0; "ScriptUtils::CheckUsersGrpReadOnly - Fi"...
0x14002cba0  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x14002cba5  mov     eax, ebx
0x14002cba7  mov     rcx, [rbp+57h+var_40]
0x14002cbab  xor     rcx, rsp; StackCookie
0x14002cbae  call    __security_check_cookie
0x14002cbb3  add     rsp, 0C8h
0x14002cbba  pop     r15
0x14002cbbc  pop     r14
0x14002cbbe  pop     rdi
0x14002cbbf  pop     rsi
0x14002cbc0  pop     rbx
0x14002cbc1  pop     rbp
0x14002cbc2  retn
```
