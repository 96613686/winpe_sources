# CUserManagement::s_AddAceToObject(ushort *,_SE_OBJECT_TYPE,ushort *,_TRUSTEE_FORM,ulong,_ACCESS_MODE,ulong)

- ea: `0x14006ab08`
- end: `0x14006ad9b`
- name: `?s_AddAceToObject@CUserManagement@@SAJPEAGW4_SE_OBJECT_TYPE@@0W4_TRUSTEE_FORM@@KW4_ACCESS_MODE@@K@Z`
- size: `659`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, enum _SE_OBJECT_TYPE, unsigned __int16 *, enum _TRUSTEE_FORM)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14006c434`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006ab08`

## import_xrefs

- `ADVAPI32!GetNamedSecurityInfoW` at `0x14006ab8c`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x14006ab8c`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14006ace5`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14006ace5`
- `ADVAPI32!SetEntriesInAclW` at `0x14006ac55`
- `ADVAPI32!SetEntriesInAclW` at `0x14006ac55`
- `KERNEL32!LocalFree` at `0x14006ad79`
- `KERNEL32!LocalFree` at `0x14006ad83`
- `KERNEL32!LocalFree` at `0x14006ad79`
- `KERNEL32!LocalFree` at `0x14006ad83`
- `KERNEL32!IsDebuggerPresent` at `0x14006abdf`
- `KERNEL32!IsDebuggerPresent` at `0x14006aca4`
- `KERNEL32!IsDebuggerPresent` at `0x14006ad3a`
- `KERNEL32!IsDebuggerPresent` at `0x14006abdf`
- `KERNEL32!IsDebuggerPresent` at `0x14006aca4`
- `KERNEL32!IsDebuggerPresent` at `0x14006ad3a`

## string_xrefs

- `0x14006abbc`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006ac81`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006ad17`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_AddAceToObject(
        LPWSTR pObjectName,
        enum _SE_OBJECT_TYPE a2,
        unsigned __int16 *a3,
        enum _TRUSTEE_FORM a4)
{
  signed int NamedSecurityInfoW; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // r8
  signed int v11; // eax
  signed int v12; // eax
  PACL *ppSacl; // [rsp+30h] [rbp-41h]
  PSECURITY_DESCRIPTOR *ppSecurityDescriptor; // [rsp+38h] [rbp-39h]
  PACL OldAcl; // [rsp+40h] [rbp-31h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+48h] [rbp-29h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+50h] [rbp-21h] BYREF
  PACL NewAcl; // [rsp+C0h] [rbp+4Fh] BYREF

  OldAcl = 0;
  NewAcl = 0;
  hMem = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  if ( !pObjectName )
    return 87;
  NamedSecurityInfoW = GetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  v8 = NamedSecurityInfoW;
  if ( !NamedSecurityInfoW )
  {
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    pListOfExplicitEntries.grfInheritance = 3;
    pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
    pListOfExplicitEntries.Trustee.ptstrName = a3;
    v11 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
    v8 = v11;
    if ( v11 )
    {
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        0x75Cu,
        L"CUserManagement::s_AddAceToObject",
        L"CBRAEx",
        L"dwError == 0L",
        v8);
      if ( IsDebuggerPresent() )
      {
        v9 = 1884;
        goto LABEL_8;
      }
      v10 = 1884;
    }
    else
    {
      v8 = 0;
      v12 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
      if ( !v12 )
        goto LABEL_24;
      if ( v12 > 0 )
        v8 = (unsigned __int16)v12 | 0x80070000;
      else
        v8 = v12;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        0x761u,
        L"CUserManagement::s_AddAceToObject",
        L"CBRAEx",
        L"dwError == 0L",
        v8);
      if ( IsDebuggerPresent() )
      {
        v9 = 1889;
        goto LABEL_8;
      }
      v10 = 1889;
    }
LABEL_23:
    LODWORD(ppSacl) = v8;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v10,
      L"CUserManagement::s_AddAceToObject",
      L"CBRAEx",
      L"dwError == 0L",
      ppSacl);
    goto LABEL_24;
  }
  if ( NamedSecurityInfoW > 0 )
    v8 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
    0x74Eu,
    L"CUserManagement::s_AddAceToObject",
    L"CBRAEx",
    L"dwError == 0L",
    v8);
  if ( !IsDebuggerPresent() )
  {
    v10 = 1870;
    goto LABEL_23;
  }
  v9 = 1870;
LABEL_8:
  LODWORD(ppSecurityDescriptor) = v8;
  DEBUGMSGLEVEL(
    2u,
    L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
    L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
    v9,
    L"CUserManagement::s_AddAceToObject",
    L"CBRAEx",
    L"dwError == 0L",
    ppSecurityDescriptor);
LABEL_24:
  LocalFree(hMem);
  LocalFree(NewAcl);
  return v8;
}

```

## disassembly

```asm
0x14006ab08  push    rbp
0x14006ab0a  push    rbx
0x14006ab0b  push    rsi
0x14006ab0c  push    rdi
0x14006ab0d  push    r14
0x14006ab0f  push    r15
0x14006ab11  lea     rbp, [rsp-17h]
0x14006ab16  sub     rsp, 88h
0x14006ab1d  mov     [rbp+3Fh+OldAcl], 0
0x14006ab25  xorps   xmm0, xmm0
0x14006ab28  mov     [rbp+3Fh+NewAcl], 0
0x14006ab30  mov     rsi, r8
0x14006ab33  mov     [rbp+3Fh+hMem], 0
0x14006ab3b  mov     rdi, rcx
0x14006ab3e  movups  xmmword ptr [rbp+3Fh+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x14006ab42  movups  xmmword ptr [rbp+3Fh+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x14006ab46  movups  xmmword ptr [rbp+3Fh+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x14006ab4a  test    rcx, rcx
0x14006ab4d  jnz     short loc_14006AB57
0x14006ab4f  lea     eax, [rcx+57h]
0x14006ab52  jmp     loc_14006AD8B
0x14006ab57  xor     r9d, r9d; ppsidOwner
0x14006ab5a  lea     rax, [rbp+3Fh+hMem]
0x14006ab5e  mov     [rsp+0B0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x14006ab63  lea     rax, [rbp+3Fh+OldAcl]
0x14006ab67  mov     [rsp+0B0h+ppSacl], 0; ppSacl
0x14006ab70  mov     [rsp+0B0h+ppDacl], rax; ppDacl
0x14006ab75  lea     r15d, [r9+4]
0x14006ab79  mov     [rsp+0B0h+ppsidGroup], 0; ppsidGroup
0x14006ab82  lea     r14d, [r9+1]
0x14006ab86  mov     r8d, r15d; SecurityInfo
0x14006ab89  mov     edx, r14d; ObjectType
0x14006ab8c  call    cs:__imp_GetNamedSecurityInfoW
0x14006ab92  mov     ebx, eax
0x14006ab94  test    eax, eax
0x14006ab96  jz      loc_14006AC26
0x14006ab9c  jle     short loc_14006ABA7
0x14006ab9e  movzx   ebx, ax
0x14006aba1  or      ebx, 80070000h
0x14006aba7  lea     r15, aCbraex; "CBRAEx"
0x14006abae  mov     dword ptr [rsp+0B0h+ppDacl], ebx; int
0x14006abb2  lea     rsi, aCusermanagemen_5; "CUserManagement::s_AddAceToObject"
0x14006abb9  mov     r9, r15; unsigned __int16 *
0x14006abbc  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006abc3  mov     r8, rsi; unsigned __int16 *
0x14006abc6  lea     r14, aDwerror0l; "dwError == 0L"
0x14006abcd  mov     rcx, rdi; unsigned __int16 *
0x14006abd0  mov     edx, 74Eh; unsigned int
0x14006abd5  mov     [rsp+0B0h+ppsidGroup], r14; unsigned __int16 *
0x14006abda  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006abdf  call    cs:__imp_IsDebuggerPresent
0x14006abe5  test    eax, eax
0x14006abe7  jz      short loc_14006AC1B
0x14006abe9  mov     r9d, 74Eh
0x14006abef  mov     dword ptr [rsp+0B0h+ppSecurityDescriptor], ebx
0x14006abf3  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006abfa  mov     [rsp+0B0h+ppSacl], r14
0x14006abff  mov     r8, rdi
0x14006ac02  mov     [rsp+0B0h+ppDacl], r15
0x14006ac07  mov     ecx, 2; unsigned __int8
0x14006ac0c  mov     [rsp+0B0h+ppsidGroup], rsi
0x14006ac11  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006ac16  jmp     loc_14006AD75
0x14006ac1b  mov     r8d, 74Eh
0x14006ac21  jmp     loc_14006AD55
0x14006ac26  mov     r8, [rbp+3Fh+OldAcl]; OldAcl
0x14006ac2a  lea     r9, [rbp+3Fh+NewAcl]; NewAcl
0x14006ac2e  lea     rdx, [rbp+3Fh+pListOfExplicitEntries]; pListOfExplicitEntries
0x14006ac32  mov     [rbp+3Fh+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x14006ac39  mov     ecx, r14d; cCountOfExplicitEntries
0x14006ac3c  mov     [rbp+3Fh+pListOfExplicitEntries.grfAccessMode], 2
0x14006ac43  mov     [rbp+3Fh+pListOfExplicitEntries.grfInheritance], 3
0x14006ac4a  mov     [rbp+3Fh+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x14006ac51  mov     [rbp+3Fh+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x14006ac55  call    cs:__imp_SetEntriesInAclW
0x14006ac5b  mov     ebx, eax
0x14006ac5d  test    eax, eax
0x14006ac5f  jz      short loc_14006ACC4
0x14006ac61  jle     short loc_14006AC6C
0x14006ac63  movzx   ebx, ax
0x14006ac66  or      ebx, 80070000h
0x14006ac6c  lea     r15, aCbraex; "CBRAEx"
0x14006ac73  mov     dword ptr [rsp+0B0h+ppDacl], ebx; int
0x14006ac77  lea     rsi, aCusermanagemen_5; "CUserManagement::s_AddAceToObject"
0x14006ac7e  mov     r9, r15; unsigned __int16 *
0x14006ac81  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006ac88  mov     r8, rsi; unsigned __int16 *
0x14006ac8b  lea     r14, aDwerror0l; "dwError == 0L"
0x14006ac92  mov     rcx, rdi; unsigned __int16 *
0x14006ac95  mov     edx, 75Ch; unsigned int
0x14006ac9a  mov     [rsp+0B0h+ppsidGroup], r14; unsigned __int16 *
0x14006ac9f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006aca4  call    cs:__imp_IsDebuggerPresent
0x14006acaa  test    eax, eax
0x14006acac  jz      short loc_14006ACB9
0x14006acae  mov     r9d, 75Ch
0x14006acb4  jmp     loc_14006ABEF
0x14006acb9  mov     r8d, 75Ch
0x14006acbf  jmp     loc_14006AD55
0x14006acc4  mov     rax, [rbp+3Fh+NewAcl]
0x14006acc8  xor     ebx, ebx
0x14006acca  mov     [rsp+0B0h+ppSacl], rbx; pSacl
0x14006accf  xor     r9d, r9d; psidOwner
0x14006acd2  mov     [rsp+0B0h+ppDacl], rax; pDacl
0x14006acd7  mov     r8d, r15d; SecurityInfo
0x14006acda  mov     edx, r14d; ObjectType
0x14006acdd  mov     [rsp+0B0h+ppsidGroup], rbx; psidGroup
0x14006ace2  mov     rcx, rdi; pObjectName
0x14006ace5  call    cs:__imp_SetNamedSecurityInfoW
0x14006aceb  test    eax, eax
0x14006aced  jz      loc_14006AD75
0x14006acf3  jg      short loc_14006ACF9
0x14006acf5  mov     ebx, eax
0x14006acf7  jmp     short loc_14006AD02
0x14006acf9  movzx   ebx, ax
0x14006acfc  or      ebx, 80070000h
0x14006ad02  lea     r15, aCbraex; "CBRAEx"
0x14006ad09  mov     dword ptr [rsp+0B0h+ppDacl], ebx; int
0x14006ad0d  lea     rsi, aCusermanagemen_5; "CUserManagement::s_AddAceToObject"
0x14006ad14  mov     r9, r15; unsigned __int16 *
0x14006ad17  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006ad1e  mov     r8, rsi; unsigned __int16 *
0x14006ad21  lea     r14, aDwerror0l; "dwError == 0L"
0x14006ad28  mov     rcx, rdi; unsigned __int16 *
0x14006ad2b  mov     edx, 761h; unsigned int
0x14006ad30  mov     [rsp+0B0h+ppsidGroup], r14; unsigned __int16 *
0x14006ad35  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006ad3a  call    cs:__imp_IsDebuggerPresent
0x14006ad40  test    eax, eax
0x14006ad42  jz      short loc_14006AD4F
0x14006ad44  mov     r9d, 761h
0x14006ad4a  jmp     loc_14006ABEF
0x14006ad4f  mov     r8d, 761h
0x14006ad55  mov     dword ptr [rsp+0B0h+ppSacl], ebx
0x14006ad59  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006ad60  mov     [rsp+0B0h+ppDacl], r14
0x14006ad65  mov     r9, rsi
0x14006ad68  mov     rdx, rdi
0x14006ad6b  mov     [rsp+0B0h+ppsidGroup], r15
0x14006ad70  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006ad75  mov     rcx, [rbp+3Fh+hMem]; hMem
0x14006ad79  call    cs:__imp_LocalFree
0x14006ad7f  mov     rcx, [rbp+3Fh+NewAcl]; hMem
0x14006ad83  call    cs:__imp_LocalFree
0x14006ad89  mov     eax, ebx
0x14006ad8b  add     rsp, 88h
0x14006ad92  pop     r15
0x14006ad94  pop     r14
0x14006ad96  pop     rdi
0x14006ad97  pop     rsi
0x14006ad98  pop     rbx
0x14006ad99  pop     rbp
0x14006ad9a  retn
```
