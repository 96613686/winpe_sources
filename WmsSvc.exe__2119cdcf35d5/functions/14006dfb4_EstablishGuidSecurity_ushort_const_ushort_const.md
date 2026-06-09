# EstablishGuidSecurity(ushort const *,ushort const *)

- ea: `0x14006dfb4`
- end: `0x14006e195`
- name: `?EstablishGuidSecurity@@YAKPEBG0@Z`
- size: `481`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006e6d0`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006dfb4`
- `0x14006e330`

## import_xrefs

- `ADVAPI32!SetNamedSecurityInfoW` at `0x14006e0be`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x14006e0be`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14006e010`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14006e010`
- `KERNEL32!LocalFree` at `0x14006e174`
- `KERNEL32!LocalFree` at `0x14006e174`
- `KERNEL32!GetLastError` at `0x14006e01a`
- `KERNEL32!GetLastError` at `0x14006e01a`
- `KERNEL32!IsDebuggerPresent` at `0x14006e117`
- `KERNEL32!IsDebuggerPresent` at `0x14006e117`

## string_xrefs

- `0x14006e0ff`: `termsrv\wms\src\common\srcutils\srcdriverinstaller.cpp`
- `0x14006e0f3`: `EstablishGuidSecurity`
- `0x14006e08a`: `pDacl != 0`

## pseudocode

```c
__int64 __fastcall EstablishGuidSecurity(LPWSTR pObjectName, LPCWSTR StringSecurityDescriptor)
{
  signed int LastError; // eax
  signed int v4; // ebx
  const unsigned __int16 *v5; // r13
  unsigned int v6; // r12d
  signed int v7; // eax
  PACL pSacl; // [rsp+30h] [rbp-30h]
  PACL pDacl; // [rsp+40h] [rbp-20h] BYREF
  struct _ACL *v11; // [rsp+48h] [rbp-18h] BYREF
  void *v12; // [rsp+50h] [rbp-10h] BYREF
  void *v13; // [rsp+58h] [rbp-8h] BYREF
  unsigned int v14; // [rsp+A0h] [rbp+40h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A8h] [rbp+48h] BYREF

  pDacl = 0;
  v11 = 0;
  v13 = 0;
  v12 = 0;
  v14 = 0;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    v4 = ParseSecurityDescriptor(SecurityDescriptor, &v14, &v13, &v12, &pDacl, &v11);
    if ( v4 < 0 )
      goto LABEL_18;
    if ( pDacl )
    {
      v7 = SetNamedSecurityInfoW(pObjectName, SE_WMIGUID_OBJECT, 4u, 0, 0, pDacl, 0);
      if ( !v7 )
        goto LABEL_18;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      else
        v4 = v7;
      v5 = L"err == 0L";
      v6 = 1230;
    }
    else
    {
      v4 = -2147024809;
      v5 = L"pDacl != 0";
      v6 = 1217;
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = L"fSuccess";
    v6 = 1203;
    if ( v4 >= 0 )
      v4 = -2147467259;
  }
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
    v6,
    L"EstablishGuidSecurity",
    L"CBRAEx",
    v5,
    v4);
  if ( IsDebuggerPresent() )
  {
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
      v6,
      L"EstablishGuidSecurity",
      L"CBRAEx",
      v5,
      v4);
  }
  else
  {
    LODWORD(pSacl) = v4;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\srcdriverinstaller.cpp",
      v6,
      L"EstablishGuidSecurity",
      L"CBRAEx",
      v5,
      pSacl);
  }
LABEL_18:
  LocalFree(SecurityDescriptor);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14006dfb4  mov     [rsp-28h+arg_0], rbx
0x14006dfb9  mov     [rsp-28h+arg_8], rsi
0x14006dfbe  push    rbp
0x14006dfbf  push    rdi
0x14006dfc0  push    r12
0x14006dfc2  push    r13
0x14006dfc4  push    r14
0x14006dfc6  mov     rbp, rsp
0x14006dfc9  sub     rsp, 60h
0x14006dfcd  mov     rax, rdx
0x14006dfd0  mov     [rbp+var_20], 0
0x14006dfd8  xor     r9d, r9d; SecurityDescriptorSize
0x14006dfdb  mov     [rbp+var_18], 0
0x14006dfe3  mov     rdi, rcx
0x14006dfe6  mov     [rbp+var_8], 0
0x14006dfee  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14006dff2  mov     [rbp+var_10], 0
0x14006dffa  mov     rcx, rax; StringSecurityDescriptor
0x14006dffd  mov     [rbp+arg_10], 0
0x14006e004  lea     edx, [r9+1]; StringSDRevision
0x14006e008  mov     [rbp+SecurityDescriptor], 0
0x14006e010  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14006e016  test    eax, eax
0x14006e018  jnz     short loc_14006E04B
0x14006e01a  call    cs:__imp_GetLastError
0x14006e020  mov     ebx, eax
0x14006e022  test    eax, eax
0x14006e024  jle     short loc_14006E02F
0x14006e026  movzx   ebx, ax
0x14006e029  or      ebx, 80070000h
0x14006e02f  test    ebx, ebx
0x14006e031  lea     r13, aFsuccess; "fSuccess"
0x14006e038  mov     eax, 80004005h
0x14006e03d  mov     r12d, 4B3h
0x14006e043  cmovns  ebx, eax
0x14006e046  jmp     loc_14006E0E8
0x14006e04b  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x14006e04f  lea     rax, [rbp+var_18]
0x14006e053  mov     [rsp+60h+pDacl], rax; struct _ACL **
0x14006e058  lea     r9, [rbp+var_10]; void **
0x14006e05c  lea     rax, [rbp+var_20]
0x14006e060  lea     r8, [rbp+var_8]; void **
0x14006e064  mov     [rsp+60h+psidGroup], rax; struct _ACL **
0x14006e069  lea     rdx, [rbp+arg_10]; unsigned int *
0x14006e06d  call    ?ParseSecurityDescriptor@@YAJPEAXPEAKPEAPEAX2PEAPEAU_ACL@@3@Z; ParseSecurityDescriptor(void *,ulong *,void * *,void * *,_ACL * *,_ACL * *)
0x14006e072  mov     ebx, eax
0x14006e074  test    eax, eax
0x14006e076  js      loc_14006E170
0x14006e07c  mov     rax, [rbp+var_20]
0x14006e080  test    rax, rax
0x14006e083  jnz     short loc_14006E099
0x14006e085  mov     ebx, 80070057h
0x14006e08a  lea     r13, aPdacl0; "pDacl != 0"
0x14006e091  mov     r12d, 4C1h
0x14006e097  jmp     short loc_14006E0E8
0x14006e099  xor     r9d, r9d; psidOwner
0x14006e09c  mov     [rsp+60h+pSacl], 0; pSacl
0x14006e0a5  mov     [rsp+60h+pDacl], rax; pDacl
0x14006e0aa  mov     rcx, rdi; pObjectName
0x14006e0ad  mov     [rsp+60h+psidGroup], 0; psidGroup
0x14006e0b6  lea     edx, [r9+0Bh]; ObjectType
0x14006e0ba  lea     r8d, [r9+4]; SecurityInfo
0x14006e0be  call    cs:__imp_SetNamedSecurityInfoW
0x14006e0c4  test    eax, eax
0x14006e0c6  jz      loc_14006E170
0x14006e0cc  jg      short loc_14006E0D2
0x14006e0ce  mov     ebx, eax
0x14006e0d0  jmp     short loc_14006E0DB
0x14006e0d2  movzx   ebx, ax
0x14006e0d5  or      ebx, 80070000h
0x14006e0db  lea     r13, aErr0l; "err == 0L"
0x14006e0e2  mov     r12d, 4CEh
0x14006e0e8  lea     r14, aCbraex; "CBRAEx"
0x14006e0ef  mov     dword ptr [rsp+60h+pDacl], ebx; int
0x14006e0f3  lea     rsi, aEstablishguids; "EstablishGuidSecurity"
0x14006e0fa  mov     [rsp+60h+psidGroup], r13; unsigned __int16 *
0x14006e0ff  lea     rdi, aTermsrvWmsSrcC_27; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x14006e106  mov     r9, r14; unsigned __int16 *
0x14006e109  mov     r8, rsi; unsigned __int16 *
0x14006e10c  mov     rcx, rdi; unsigned __int16 *
0x14006e10f  mov     edx, r12d; unsigned int
0x14006e112  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006e117  call    cs:__imp_IsDebuggerPresent
0x14006e11d  test    eax, eax
0x14006e11f  jz      short loc_14006E14D
0x14006e121  mov     [rsp+60h+var_28], ebx
0x14006e125  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006e12c  mov     [rsp+60h+pSacl], r13
0x14006e131  mov     r9d, r12d
0x14006e134  mov     [rsp+60h+pDacl], r14
0x14006e139  mov     r8, rdi
0x14006e13c  mov     ecx, 2; unsigned __int8
0x14006e141  mov     [rsp+60h+psidGroup], rsi
0x14006e146  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006e14b  jmp     short loc_14006E170
0x14006e14d  mov     dword ptr [rsp+60h+pSacl], ebx
0x14006e151  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006e158  mov     [rsp+60h+pDacl], r13
0x14006e15d  mov     r9, rsi
0x14006e160  mov     r8d, r12d
0x14006e163  mov     [rsp+60h+psidGroup], r14
0x14006e168  mov     rdx, rdi
0x14006e16b  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006e170  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x14006e174  call    cs:__imp_LocalFree
0x14006e17a  lea     r11, [rsp+60h+var_s0]
0x14006e17f  mov     eax, ebx
0x14006e181  mov     rbx, [r11+30h]
0x14006e185  mov     rsi, [r11+38h]
0x14006e189  mov     rsp, r11
0x14006e18c  pop     r14
0x14006e18e  pop     r13
0x14006e190  pop     r12
0x14006e192  pop     rdi
0x14006e193  pop     rbp
0x14006e194  retn
```
