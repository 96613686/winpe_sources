# CUserManagement::s_GetNameFromLocalKnownSID(WELL_KNOWN_SID_TYPE,ushort * *,ushort * *)

- ea: `0x14006b2d0`
- end: `0x14006b789`
- name: `?s_GetNameFromLocalKnownSID@CUserManagement@@SAJW4WELL_KNOWN_SID_TYPE@@PEAPEAG1@Z`
- size: `1209`
- prototype: `__int64 __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14004e180`
- `0x1400520a0`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14006b2d0`
- `0x14007cb9e`

## import_xrefs

- `ADVAPI32!CreateWellKnownSid` at `0x14006b3e0`
- `ADVAPI32!CreateWellKnownSid` at `0x14006b3e0`
- `ADVAPI32!LookupAccountSidW` at `0x14006b4a4`
- `ADVAPI32!LookupAccountSidW` at `0x14006b6ab`
- `ADVAPI32!LookupAccountSidW` at `0x14006b4a4`
- `ADVAPI32!LookupAccountSidW` at `0x14006b6ab`
- `KERNEL32!LocalFree` at `0x14006b758`
- `KERNEL32!LocalFree` at `0x14006b758`
- `KERNEL32!LocalAlloc` at `0x14006b311`
- `KERNEL32!LocalAlloc` at `0x14006b311`
- `KERNEL32!GetLastError` at `0x14006b3ee`
- `KERNEL32!GetLastError` at `0x14006b4b2`
- `KERNEL32!GetLastError` at `0x14006b6b9`
- `KERNEL32!GetLastError` at `0x14006b3ee`
- `KERNEL32!GetLastError` at `0x14006b4b2`
- `KERNEL32!GetLastError` at `0x14006b6b9`
- `KERNEL32!IsDebuggerPresent` at `0x14006b365`
- `KERNEL32!IsDebuggerPresent` at `0x14006b445`
- `KERNEL32!IsDebuggerPresent` at `0x14006b508`
- `KERNEL32!IsDebuggerPresent` at `0x14006b5b3`
- `KERNEL32!IsDebuggerPresent` at `0x14006b650`
- `KERNEL32!IsDebuggerPresent` at `0x14006b710`
- `KERNEL32!IsDebuggerPresent` at `0x14006b365`
- `KERNEL32!IsDebuggerPresent` at `0x14006b445`
- `KERNEL32!IsDebuggerPresent` at `0x14006b508`
- `KERNEL32!IsDebuggerPresent` at `0x14006b5b3`
- `KERNEL32!IsDebuggerPresent` at `0x14006b650`
- `KERNEL32!IsDebuggerPresent` at `0x14006b710`

## string_xrefs

- `0x14006b33c`: `CUserManagement::s_GetNameFromLocalKnownSID`
- `0x14006b411`: `CUserManagement::s_GetNameFromLocalKnownSID`
- `0x14006b4e7`: `CUserManagement::s_GetNameFromLocalKnownSID`
- `0x14006b58a`: `CUserManagement::s_GetNameFromLocalKnownSID`
- `0x14006b627`: `CUserManagement::s_GetNameFromLocalKnownSID`
- `0x14006b6dc`: `CUserManagement::s_GetNameFromLocalKnownSID`
- `0x14006b348`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b418`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b4f1`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b596`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b633`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006b6e3`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_GetNameFromLocalKnownSID(
        WELL_KNOWN_SID_TYPE WellKnownSidType,
        unsigned __int16 **a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v5; // r12
  HLOCAL v6; // rax
  void *v7; // r13
  signed int v8; // ebx
  bool v9; // zf
  const unsigned __int16 *v10; // rax
  __int64 v11; // r9
  __int64 v12; // r8
  signed int LastError; // eax
  signed int v14; // eax
  unsigned __int16 *v15; // rax
  void *v16; // rax
  WCHAR *ReferencedDomainName; // rsi
  signed int v18; // eax
  PSID_NAME_USE peUse; // [rsp+30h] [rbp-20h]
  PSID_NAME_USE peUsea; // [rsp+30h] [rbp-20h]
  __int64 v22; // [rsp+40h] [rbp-10h] BYREF
  void *Block; // [rsp+48h] [rbp-8h]
  DWORD cchReferencedDomainName; // [rsp+A0h] [rbp+50h] BYREF
  int v25; // [rsp+A4h] [rbp+54h]
  DWORD cchName; // [rsp+A8h] [rbp+58h] BYREF

  v25 = HIDWORD(a3);
  v22 = 0x4400000000LL;
  cchName = 0;
  v5 = 0;
  Block = 0;
  cchReferencedDomainName = 0;
  v6 = LocalAlloc(0, 0x44u);
  v7 = v6;
  if ( !v6 )
  {
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x85u,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CPR",
      L"pSID",
      -2147024882);
    v9 = !IsDebuggerPresent();
    v10 = L"pSID";
    if ( !v9 )
    {
      v11 = 133;
LABEL_4:
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        v11,
        L"CUserManagement::s_GetNameFromLocalKnownSID",
        L"CPR",
        v10,
        -2147024882,
        v22,
        Block);
      goto LABEL_39;
    }
    v12 = 133;
    goto LABEL_6;
  }
  if ( !CreateWellKnownSid(WellKnownSidType, 0, v6, (DWORD *)&v22 + 1) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x88u,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CBRAEx",
      L"fSuccess",
      v8);
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        136,
        L"CUserManagement::s_GetNameFromLocalKnownSID",
        L"CBRAEx",
        L"fSuccess",
        v8,
        v22,
        Block);
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        136,
        L"CUserManagement::s_GetNameFromLocalKnownSID",
        L"CBRAEx",
        L"fSuccess",
        v8);
    goto LABEL_39;
  }
  if ( LookupAccountSidW(0, v7, 0, &cchName, 0, &cchReferencedDomainName, (PSID_NAME_USE)&v22) )
    goto LABEL_38;
  v14 = GetLastError();
  v8 = v14;
  if ( v14 != 122 )
  {
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x8Fu,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CBRAEx",
      L"dwError == 122L",
      v8);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        143,
        L"CUserManagement::s_GetNameFromLocalKnownSID",
        L"CBRAEx",
        L"dwError == 122L",
        v8,
        v22,
        Block);
    }
    else
    {
      LODWORD(peUse) = v8;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        143,
        L"CUserManagement::s_GetNameFromLocalKnownSID",
        L"CBRAEx",
        L"dwError == 122L",
        peUse);
    }
    goto LABEL_39;
  }
  v15 = (unsigned __int16 *)operator new(saturated_mul(cchName, 2u));
  v5 = v15;
  if ( !v15 )
  {
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x93u,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CPR",
      L"pszAccountName",
      -2147024882);
    v9 = !IsDebuggerPresent();
    v10 = L"pszAccountName";
    if ( !v9 )
    {
      v11 = 147;
      goto LABEL_4;
    }
    v12 = 147;
LABEL_6:
    LODWORD(peUse) = -2147024882;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      v12,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CPR",
      v10,
      peUse);
    goto LABEL_39;
  }
  memset_0(v15, 0, 2LL * cchName);
  v16 = operator new(saturated_mul(cchReferencedDomainName, 2u));
  Block = v16;
  ReferencedDomainName = (WCHAR *)v16;
  if ( !v16 )
  {
    v8 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x97u,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CPR",
      L"pszDomainName",
      -2147024882);
    v9 = !IsDebuggerPresent();
    v10 = L"pszDomainName";
    if ( !v9 )
    {
      v11 = 151;
      goto LABEL_4;
    }
    v12 = 151;
    goto LABEL_6;
  }
  memset_0(v16, 0, 2LL * cchReferencedDomainName);
  if ( LookupAccountSidW(0, v7, v5, &cchName, ReferencedDomainName, &cchReferencedDomainName, (PSID_NAME_USE)&v22) )
  {
LABEL_38:
    *a2 = v5;
    v8 = 0;
    v5 = 0;
    goto LABEL_39;
  }
  v18 = GetLastError();
  v8 = v18;
  if ( v18 > 0 )
    v8 = (unsigned __int16)v18 | 0x80070000;
  if ( v8 >= 0 )
    v8 = -2147467259;
  LOGASSERTHR(
    L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
    0x9Du,
    L"CUserManagement::s_GetNameFromLocalKnownSID",
    L"CBRAEx",
    L"fSuccess",
    v8);
  if ( IsDebuggerPresent() )
  {
    DEBUGMSGLEVEL(
      2u,
      L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      157,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CBRAEx",
      L"fSuccess",
      v8,
      v22,
      Block);
  }
  else
  {
    LODWORD(peUsea) = v8;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      157,
      L"CUserManagement::s_GetNameFromLocalKnownSID",
      L"CBRAEx",
      L"fSuccess",
      peUsea);
  }
LABEL_39:
  LocalFree(v7);
  operator delete(v5);
  operator delete(Block);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14006b2d0  mov     [rsp-38h+arg_0], rbx
0x14006b2d5  mov     qword ptr [rsp-38h+arg_10], r8
0x14006b2da  push    rbp
0x14006b2db  push    rsi
0x14006b2dc  push    rdi
0x14006b2dd  push    r12
0x14006b2df  push    r13
0x14006b2e1  push    r14
0x14006b2e3  push    r15
0x14006b2e5  mov     rbp, rsp
0x14006b2e8  sub     rsp, 50h
0x14006b2ec  xor     r15d, r15d
0x14006b2ef  mov     rdi, rdx
0x14006b2f2  mov     edx, 44h ; 'D'; uBytes
0x14006b2f7  mov     [rbp+var_10], r15d
0x14006b2fb  mov     ebx, ecx
0x14006b2fd  mov     [rbp+cbSid], edx
0x14006b300  xor     ecx, ecx; uFlags
0x14006b302  mov     [rbp+cchName], r15d
0x14006b306  mov     r12d, r15d
0x14006b309  mov     [rbp+Block], r15
0x14006b30d  mov     [rbp+arg_10], r15d
0x14006b311  call    cs:__imp_LocalAlloc
0x14006b317  mov     r13, rax
0x14006b31a  test    rax, rax
0x14006b31d  jnz     loc_14006B3D5
0x14006b323  mov     r14d, 8007000Eh
0x14006b329  lea     rax, aPsid; "pSID"
0x14006b330  lea     r15, aCpr; "CPR"
0x14006b337  mov     dword ptr [rsp+50h+cchReferencedDomainName], r14d; int
0x14006b33c  lea     rsi, aCusermanagemen_13; "CUserManagement::s_GetNameFromLocalKnow"...
0x14006b343  mov     [rsp+50h+ReferencedDomainName], rax; unsigned __int16 *
0x14006b348  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b34f  mov     r9, r15; unsigned __int16 *
0x14006b352  mov     r8, rsi; unsigned __int16 *
0x14006b355  mov     rcx, rdi; unsigned __int16 *
0x14006b358  mov     edx, 85h; unsigned int
0x14006b35d  mov     ebx, r14d
0x14006b360  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b365  call    cs:__imp_IsDebuggerPresent
0x14006b36b  test    eax, eax
0x14006b36d  lea     rax, aPsid; "pSID"
0x14006b374  jz      short loc_14006B3A9
0x14006b376  mov     r9d, 85h
0x14006b37c  mov     [rsp+50h+var_18], r14d
0x14006b381  mov     [rsp+50h+peUse], rax
0x14006b386  mov     [rsp+50h+cchReferencedDomainName], r15
0x14006b38b  mov     r8, rdi
0x14006b38e  mov     [rsp+50h+ReferencedDomainName], rsi
0x14006b393  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006b39a  mov     ecx, 2; unsigned __int8
0x14006b39f  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006b3a4  jmp     loc_14006B755
0x14006b3a9  mov     r8d, 85h
0x14006b3af  mov     dword ptr [rsp+50h+peUse], r14d
0x14006b3b4  mov     [rsp+50h+cchReferencedDomainName], rax
0x14006b3b9  mov     [rsp+50h+ReferencedDomainName], r15
0x14006b3be  mov     r9, rsi
0x14006b3c1  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006b3c8  mov     rdx, rdi
0x14006b3cb  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006b3d0  jmp     loc_14006B755
0x14006b3d5  lea     r9, [rbp+cbSid]; cbSid
0x14006b3d9  mov     r8, r13; pSid
0x14006b3dc  xor     edx, edx; DomainSid
0x14006b3de  mov     ecx, ebx; WellKnownSidType
0x14006b3e0  call    cs:__imp_CreateWellKnownSid
0x14006b3e6  test    eax, eax
0x14006b3e8  jnz     loc_14006B481
0x14006b3ee  call    cs:__imp_GetLastError
0x14006b3f4  mov     ebx, eax
0x14006b3f6  test    eax, eax
0x14006b3f8  jle     short loc_14006B403
0x14006b3fa  movzx   ebx, ax
0x14006b3fd  or      ebx, 80070000h
0x14006b403  mov     eax, 80004005h
0x14006b408  lea     r14, aCbraex; "CBRAEx"
0x14006b40f  test    ebx, ebx
0x14006b411  lea     rsi, aCusermanagemen_13; "CUserManagement::s_GetNameFromLocalKnow"...
0x14006b418  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b41f  mov     r9, r14; unsigned __int16 *
0x14006b422  cmovns  ebx, eax
0x14006b425  lea     r15, aFsuccess; "fSuccess"
0x14006b42c  mov     dword ptr [rsp+50h+cchReferencedDomainName], ebx; int
0x14006b430  mov     r8, rsi; unsigned __int16 *
0x14006b433  mov     edx, 88h; unsigned int
0x14006b438  mov     [rsp+50h+ReferencedDomainName], r15; unsigned __int16 *
0x14006b43d  mov     rcx, rdi; unsigned __int16 *
0x14006b440  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b445  call    cs:__imp_IsDebuggerPresent
0x14006b44b  test    eax, eax
0x14006b44d  jz      short loc_14006B468
0x14006b44f  mov     [rsp+50h+var_18], ebx
0x14006b453  mov     r9d, 88h
0x14006b459  mov     [rsp+50h+peUse], r15
0x14006b45e  mov     [rsp+50h+cchReferencedDomainName], r14
0x14006b463  jmp     loc_14006B38B
0x14006b468  mov     dword ptr [rsp+50h+peUse], ebx
0x14006b46c  mov     r8d, 88h
0x14006b472  mov     [rsp+50h+cchReferencedDomainName], r15
0x14006b477  mov     [rsp+50h+ReferencedDomainName], r14
0x14006b47c  jmp     loc_14006B3BE
0x14006b481  lea     rax, [rbp+var_10]
0x14006b485  xor     r8d, r8d; Name
0x14006b488  mov     [rsp+50h+peUse], rax; peUse
0x14006b48d  lea     r9, [rbp+cchName]; cchName
0x14006b491  lea     rax, [rbp+arg_10]
0x14006b495  mov     rdx, r13; Sid
0x14006b498  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14006b49d  xor     ecx, ecx; lpSystemName
0x14006b49f  mov     [rsp+50h+ReferencedDomainName], r15; ReferencedDomainName
0x14006b4a4  call    cs:__imp_LookupAccountSidW
0x14006b4aa  test    eax, eax
0x14006b4ac  jnz     loc_14006B74C
0x14006b4b2  call    cs:__imp_GetLastError
0x14006b4b8  mov     ebx, eax
0x14006b4ba  cmp     eax, 7Ah ; 'z'
0x14006b4bd  jz      loc_14006B54B
0x14006b4c3  test    eax, eax
0x14006b4c5  jle     short loc_14006B4D0
0x14006b4c7  movzx   ebx, ax
0x14006b4ca  or      ebx, 80070000h
0x14006b4d0  lea     rax, aDwerror122l; "dwError == 122L"
0x14006b4d7  mov     dword ptr [rsp+50h+cchReferencedDomainName], ebx; int
0x14006b4db  lea     r14, aCbraex; "CBRAEx"
0x14006b4e2  mov     [rsp+50h+ReferencedDomainName], rax; unsigned __int16 *
0x14006b4e7  lea     rsi, aCusermanagemen_13; "CUserManagement::s_GetNameFromLocalKnow"...
0x14006b4ee  mov     r9, r14; unsigned __int16 *
0x14006b4f1  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b4f8  mov     r8, rsi; unsigned __int16 *
0x14006b4fb  mov     rcx, rdi; unsigned __int16 *
0x14006b4fe  mov     edx, 8Fh; unsigned int
0x14006b503  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b508  call    cs:__imp_IsDebuggerPresent
0x14006b50e  test    eax, eax
0x14006b510  lea     rax, aDwerror122l; "dwError == 122L"
0x14006b517  jz      short loc_14006B532
0x14006b519  mov     [rsp+50h+var_18], ebx
0x14006b51d  mov     r9d, 8Fh
0x14006b523  mov     [rsp+50h+peUse], rax
0x14006b528  mov     [rsp+50h+cchReferencedDomainName], r14
0x14006b52d  jmp     loc_14006B38B
0x14006b532  mov     dword ptr [rsp+50h+peUse], ebx
0x14006b536  mov     r8d, 8Fh
0x14006b53c  mov     [rsp+50h+cchReferencedDomainName], rax
0x14006b541  mov     [rsp+50h+ReferencedDomainName], r14
0x14006b546  jmp     loc_14006B3BE
0x14006b54b  mov     ecx, [rbp+cchName]
0x14006b54e  mov     eax, 2
0x14006b553  mul     rcx
0x14006b556  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14006b55d  cmovb   rax, rbx
0x14006b561  mov     rcx, rax; Size
0x14006b564  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006b569  mov     r12, rax
0x14006b56c  test    rax, rax
0x14006b56f  jnz     short loc_14006B5DA
0x14006b571  mov     r14d, 8007000Eh
0x14006b577  lea     rax, aPszaccountname; "pszAccountName"
0x14006b57e  lea     r15, aCpr; "CPR"
0x14006b585  mov     dword ptr [rsp+50h+cchReferencedDomainName], r14d; int
0x14006b58a  lea     rsi, aCusermanagemen_13; "CUserManagement::s_GetNameFromLocalKnow"...
0x14006b591  mov     [rsp+50h+ReferencedDomainName], rax; unsigned __int16 *
0x14006b596  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b59d  mov     r9, r15; unsigned __int16 *
0x14006b5a0  mov     r8, rsi; unsigned __int16 *
0x14006b5a3  mov     rcx, rdi; unsigned __int16 *
0x14006b5a6  mov     edx, 93h; unsigned int
0x14006b5ab  mov     ebx, r14d
0x14006b5ae  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b5b3  call    cs:__imp_IsDebuggerPresent
0x14006b5b9  test    eax, eax
0x14006b5bb  lea     rax, aPszaccountname; "pszAccountName"
0x14006b5c2  jz      short loc_14006B5CF
0x14006b5c4  mov     r9d, 93h
0x14006b5ca  jmp     loc_14006B37C
0x14006b5cf  mov     r8d, 93h
0x14006b5d5  jmp     loc_14006B3AF
0x14006b5da  mov     r8d, [rbp+cchName]
0x14006b5de  xor     edx, edx; Val
0x14006b5e0  add     r8, r8; Size
0x14006b5e3  mov     rcx, r12; void *
0x14006b5e6  call    memset_0
0x14006b5eb  mov     ecx, [rbp+arg_10]
0x14006b5ee  mov     eax, 2
0x14006b5f3  mul     rcx
0x14006b5f6  cmovb   rax, rbx
0x14006b5fa  mov     rcx, rax; Size
0x14006b5fd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14006b602  mov     [rbp+Block], rax
0x14006b606  mov     rsi, rax
0x14006b609  test    rax, rax
0x14006b60c  jnz     short loc_14006B677
0x14006b60e  mov     r14d, 8007000Eh
0x14006b614  lea     rax, aPszdomainname; "pszDomainName"
0x14006b61b  lea     r15, aCpr; "CPR"
0x14006b622  mov     dword ptr [rsp+50h+cchReferencedDomainName], r14d; int
0x14006b627  lea     rsi, aCusermanagemen_13; "CUserManagement::s_GetNameFromLocalKnow"...
0x14006b62e  mov     [rsp+50h+ReferencedDomainName], rax; unsigned __int16 *
0x14006b633  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b63a  mov     r9, r15; unsigned __int16 *
0x14006b63d  mov     r8, rsi; unsigned __int16 *
0x14006b640  mov     rcx, rdi; unsigned __int16 *
0x14006b643  mov     edx, 97h; unsigned int
0x14006b648  mov     ebx, r14d
0x14006b64b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b650  call    cs:__imp_IsDebuggerPresent
0x14006b656  test    eax, eax
0x14006b658  lea     rax, aPszdomainname; "pszDomainName"
0x14006b65f  jz      short loc_14006B66C
0x14006b661  mov     r9d, 97h
0x14006b667  jmp     loc_14006B37C
0x14006b66c  mov     r8d, 97h
0x14006b672  jmp     loc_14006B3AF
0x14006b677  mov     r8d, [rbp+arg_10]
0x14006b67b  xor     edx, edx; Val
0x14006b67d  add     r8, r8; Size
0x14006b680  mov     rcx, rsi; void *
0x14006b683  call    memset_0
0x14006b688  lea     rax, [rbp+var_10]
0x14006b68c  mov     r8, r12; Name
0x14006b68f  mov     [rsp+50h+peUse], rax; peUse
0x14006b694  lea     r9, [rbp+cchName]; cchName
0x14006b698  lea     rax, [rbp+arg_10]
0x14006b69c  mov     rdx, r13; Sid
0x14006b69f  mov     [rsp+50h+cchReferencedDomainName], rax; cchReferencedDomainName
0x14006b6a4  xor     ecx, ecx; lpSystemName
0x14006b6a6  mov     [rsp+50h+ReferencedDomainName], rsi; ReferencedDomainName
0x14006b6ab  call    cs:__imp_LookupAccountSidW
0x14006b6b1  test    eax, eax
0x14006b6b3  jnz     loc_14006B74C
0x14006b6b9  call    cs:__imp_GetLastError
0x14006b6bf  mov     ebx, eax
0x14006b6c1  test    eax, eax
0x14006b6c3  jle     short loc_14006B6CE
0x14006b6c5  movzx   ebx, ax
0x14006b6c8  or      ebx, 80070000h
0x14006b6ce  mov     eax, 80004005h
0x14006b6d3  lea     r14, aCbraex; "CBRAEx"
0x14006b6da  test    ebx, ebx
0x14006b6dc  lea     rsi, aCusermanagemen_13; "CUserManagement::s_GetNameFromLocalKnow"...
0x14006b6e3  lea     rdi, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006b6ea  mov     r9, r14; unsigned __int16 *
0x14006b6ed  cmovns  ebx, eax
0x14006b6f0  lea     r15, aFsuccess; "fSuccess"
0x14006b6f7  mov     dword ptr [rsp+50h+cchReferencedDomainName], ebx; int
0x14006b6fb  mov     r8, rsi; unsigned __int16 *
0x14006b6fe  mov     edx, 9Dh; unsigned int
0x14006b703  mov     [rsp+50h+ReferencedDomainName], r15; unsigned __int16 *
0x14006b708  mov     rcx, rdi; unsigned __int16 *
0x14006b70b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006b710  call    cs:__imp_IsDebuggerPresent
0x14006b716  test    eax, eax
0x14006b718  jz      short loc_14006B733
0x14006b71a  mov     [rsp+50h+var_18], ebx
0x14006b71e  mov     r9d, 9Dh
0x14006b724  mov     [rsp+50h+peUse], r15
0x14006b729  mov     [rsp+50h+cchReferencedDomainName], r14
0x14006b72e  jmp     loc_14006B38B
0x14006b733  mov     dword ptr [rsp+50h+peUse], ebx
0x14006b737  mov     r8d, 9Dh
0x14006b73d  mov     [rsp+50h+cchReferencedDomainName], r15
0x14006b742  mov     [rsp+50h+ReferencedDomainName], r14
0x14006b747  jmp     loc_14006B3BE
0x14006b74c  mov     [rdi], r12
0x14006b74f  mov     ebx, r15d
0x14006b752  mov     r12, r15
0x14006b755  mov     rcx, r13; hMem
0x14006b758  call    cs:__imp_LocalFree
0x14006b75e  mov     rcx, r12; Block
0x14006b761  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006b766  mov     rcx, [rbp+Block]; Block
0x14006b76a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006b76f  mov     eax, ebx
0x14006b771  mov     rbx, [rsp+50h+arg_0]
0x14006b779  add     rsp, 50h
0x14006b77d  pop     r15
0x14006b77f  pop     r14
0x14006b781  pop     r13
0x14006b783  pop     r12
0x14006b785  pop     rdi
0x14006b786  pop     rsi
0x14006b787  pop     rbp
0x14006b788  retn
```
