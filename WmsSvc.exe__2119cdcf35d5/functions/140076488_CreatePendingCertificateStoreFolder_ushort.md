# CreatePendingCertificateStoreFolder(ushort *)

- ea: `0x140076488`
- end: `0x14007677c`
- name: `?CreatePendingCertificateStoreFolder@@YAJPEAG@Z`
- size: `756`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400595ec`

## callees

- `0x1400016b8`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x140065c64`
- `0x140076488`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14007659a`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x14007659a`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1400766d4`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1400766d4`
- `KERNEL32!CreateDirectoryW` at `0x140076670`
- `KERNEL32!CreateDirectoryW` at `0x140076670`
- `KERNEL32!GetLastError` at `0x1400765a4`
- `KERNEL32!GetLastError` at `0x140076678`
- `KERNEL32!GetLastError` at `0x1400765a4`
- `KERNEL32!GetLastError` at `0x140076678`
- `KERNEL32!IsDebuggerPresent` at `0x14007653b`
- `KERNEL32!IsDebuggerPresent` at `0x140076615`
- `KERNEL32!IsDebuggerPresent` at `0x14007671f`
- `KERNEL32!IsDebuggerPresent` at `0x14007653b`
- `KERNEL32!IsDebuggerPresent` at `0x140076615`
- `KERNEL32!IsDebuggerPresent` at `0x14007671f`

## string_xrefs

- `0x140076518`: `termsrv\wms\src\common\srcutils\diskprotectionutils.cpp`
- `0x1400765d1`: `termsrv\wms\src\common\srcutils\diskprotectionutils.cpp`
- `0x1400765ee`: `termsrv\wms\src\common\srcutils\diskprotectionutils.cpp`
- `0x14007650c`: `CreatePendingCertificateStoreFolder`
- `0x1400765c7`: `CreatePendingCertificateStoreFolder`
- `0x1400765e7`: `CreatePendingCertificateStoreFolder`

## pseudocode

```c
__int64 __fastcall CreatePendingCertificateStoreFolder(LPWSTR pObjectName)
{
  int v2; // eax
  signed int v3; // edi
  const unsigned __int16 *v4; // r9
  signed int v5; // eax
  const unsigned __int16 *v6; // r13
  unsigned int v7; // r15d
  BOOL DirectoryW; // ebx
  signed int LastError; // eax
  signed int v10; // eax
  PACL pSacl; // [rsp+30h] [rbp-40h]
  void *Block; // [rsp+40h] [rbp-30h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+48h] [rbp-28h] BYREF
  __int64 v15; // [rsp+68h] [rbp-8h]
  WINBOOL bDaclPresent; // [rsp+B8h] [rbp+48h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+C0h] [rbp+50h] BYREF
  PACL pDacl; // [rsp+C8h] [rbp+58h] BYREF

  pDacl = 0;
  v15 = 0;
  Block = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v2 = CreateSecurityDescriptorEx(1u, 0, 0, (struct WmsAceEx *)qword_1400EE7C0, 1u, pSecurityDescriptor, &Block);
  v3 = v2;
  if ( v2 >= 0 )
  {
    if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( !bDaclPresent )
      {
        LOGASSERT(
          L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
          0x54u,
          L"CreatePendingCertificateStoreFolder",
          v4,
          L"fPresent");
        if ( IsDebuggerPresent() )
          DEBUGMSGLEVEL(
            2u,
            L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
            L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
            84,
            L"CreatePendingCertificateStoreFolder",
            L"ASSERT",
            L"fPresent");
        else
          DEBUGMSGBOX(
            L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
            L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
            84,
            L"CreatePendingCertificateStoreFolder",
            L"ASSERT",
            L"fPresent");
      }
      DirectoryW = CreateDirectoryW(pObjectName, 0);
      LastError = GetLastError();
      if ( DirectoryW || LastError == 183 )
      {
        v10 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
        if ( !v10 )
          goto LABEL_30;
        if ( v10 > 0 )
          v3 = (unsigned __int16)v10 | 0x80070000;
        else
          v3 = v10;
        v6 = L"dwError == 0L";
        v7 = 92;
      }
      else
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        else
          v3 = LastError;
        v6 = L"fSuccess || dwError == 183L";
        v7 = 88;
      }
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      if ( v5 > 0 )
        v3 = (unsigned __int16)v5 | 0x80070000;
      v6 = L"fResult";
      if ( v3 >= 0 )
        v3 = -2147467259;
      v7 = 83;
    }
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
      v7,
      L"CreatePendingCertificateStoreFolder",
      L"CBRAEx",
      v6,
      v3);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
        v7,
        L"CreatePendingCertificateStoreFolder",
        L"CBRAEx",
        v6,
        v3);
    }
    else
    {
      LODWORD(pSacl) = v3;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
        v7,
        L"CreatePendingCertificateStoreFolder",
        L"CBRAEx",
        v6,
        pSacl);
    }
  }
  else
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
      0x50u,
      L"CreatePendingCertificateStoreFolder",
      L"CHRA",
      L"hr",
      v2);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
        80,
        L"CreatePendingCertificateStoreFolder",
        L"CHRA",
        L"hr",
        v3);
    }
    else
    {
      LODWORD(pSacl) = v3;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\diskprotectionutils.cpp",
        80,
        L"CreatePendingCertificateStoreFolder",
        L"CHRA",
        L"hr",
        pSacl);
    }
  }
LABEL_30:
  operator delete(Block);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140076488  push    rbp
0x14007648a  push    rbx
0x14007648b  push    rsi
0x14007648c  push    rdi
0x14007648d  push    r13
0x14007648f  push    r14
0x140076491  push    r15
0x140076493  mov     rbp, rsp
0x140076496  sub     rsp, 70h
0x14007649a  xor     eax, eax
0x14007649c  mov     [rbp+pDacl], 0
0x1400764a4  mov     [rbp+var_8], rax
0x1400764a8  lea     r9, qword_1400EE7C0; struct WmsAceEx *
0x1400764af  mov     [rbp+Block], rax
0x1400764b3  xorps   xmm0, xmm0
0x1400764b6  lea     rax, [rbp+Block]
0x1400764ba  mov     [rbp+bDaclPresent], 0
0x1400764c1  mov     [rsp+70h+pSacl], rax; void **
0x1400764c6  xor     edx, edx; struct WmsSid *
0x1400764c8  lea     rax, [rbp+pSecurityDescriptor]
0x1400764cc  mov     [rbp+bDaclDefaulted], 0
0x1400764d3  mov     r15, rcx
0x1400764d6  mov     [rsp+70h+var_48], rax; pSecurityDescriptor
0x1400764db  xor     r8d, r8d; struct WmsSid *
0x1400764de  mov     [rsp+70h+psidGroup], 1; unsigned __int64
0x1400764e7  lea     ecx, [rdx+1]; unsigned int
0x1400764ea  movups  [rbp+pSecurityDescriptor], xmm0
0x1400764ee  movups  [rbp+var_18], xmm0
0x1400764f2  call    ?CreateSecurityDescriptorEx@@YAJKPEAUWmsSid@@0PEAUWmsAceEx@@_KPEAU_SECURITY_DESCRIPTOR@@PEAPEAX@Z; CreateSecurityDescriptorEx(ulong,WmsSid *,WmsSid *,WmsAceEx *,unsigned __int64,_SECURITY_DESCRIPTOR *,void * *)
0x1400764f7  mov     edi, eax
0x1400764f9  test    eax, eax
0x1400764fb  jns     loc_14007658A
0x140076501  mov     dword ptr [rsp+70h+var_48], eax; int
0x140076505  lea     r13, aChra; "CHRA"
0x14007650c  lea     r14, aCreatependingc; "CreatePendingCertificateStoreFolder"
0x140076513  mov     ebx, 50h ; 'P'
0x140076518  lea     rsi, aTermsrvWmsSrcC_15; "termsrv\\wms\\src\\common\\srcutils\\di"...
0x14007651f  mov     r9, r13; unsigned __int16 *
0x140076522  lea     r15, aHr; "hr"
0x140076529  mov     r8, r14; unsigned __int16 *
0x14007652c  mov     edx, ebx; unsigned int
0x14007652e  mov     [rsp+70h+psidGroup], r15; unsigned __int16 *
0x140076533  mov     rcx, rsi; unsigned __int16 *
0x140076536  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007653b  call    cs:__imp_IsDebuggerPresent
0x140076541  test    eax, eax
0x140076543  jz      short loc_140076574
0x140076545  mov     [rsp+70h+var_38], edi
0x140076549  mov     r9d, ebx
0x14007654c  mov     [rsp+70h+pSacl], r15
0x140076551  mov     [rsp+70h+var_48], r13
0x140076556  mov     r8, rsi
0x140076559  mov     [rsp+70h+psidGroup], r14
0x14007655e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140076565  mov     ecx, 2; unsigned __int8
0x14007656a  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007656f  jmp     loc_140076762
0x140076574  mov     dword ptr [rsp+70h+pSacl], edi
0x140076578  mov     r8d, ebx
0x14007657b  mov     [rsp+70h+var_48], r15
0x140076580  mov     [rsp+70h+psidGroup], r13
0x140076585  jmp     loc_140076750
0x14007658a  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x14007658e  lea     r8, [rbp+pDacl]; pDacl
0x140076592  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x140076596  lea     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x14007659a  call    cs:__imp_GetSecurityDescriptorDacl
0x1400765a0  test    eax, eax
0x1400765a2  jnz     short loc_1400765E3
0x1400765a4  call    cs:__imp_GetLastError
0x1400765aa  mov     edi, eax
0x1400765ac  test    eax, eax
0x1400765ae  jle     short loc_1400765B9
0x1400765b0  movzx   edi, ax
0x1400765b3  or      edi, 80070000h
0x1400765b9  test    edi, edi
0x1400765bb  lea     r13, aFresult; "fResult"
0x1400765c2  mov     eax, 80004005h
0x1400765c7  lea     r14, aCreatependingc; "CreatePendingCertificateStoreFolder"
0x1400765ce  cmovns  edi, eax
0x1400765d1  lea     rsi, aTermsrvWmsSrcC_15; "termsrv\\wms\\src\\common\\srcutils\\di"...
0x1400765d8  mov     r15d, 53h ; 'S'
0x1400765de  jmp     loc_1400766FE
0x1400765e3  cmp     [rbp+bDaclPresent], 0
0x1400765e7  lea     r14, aCreatependingc; "CreatePendingCertificateStoreFolder"
0x1400765ee  lea     rsi, aTermsrvWmsSrcC_15; "termsrv\\wms\\src\\common\\srcutils\\di"...
0x1400765f5  jnz     short loc_14007666B
0x1400765f7  mov     ebx, 54h ; 'T'
0x1400765fc  lea     r13, aFpresent; "fPresent"
0x140076603  mov     edx, ebx; unsigned int
0x140076605  mov     [rsp+70h+psidGroup], r13; unsigned __int16 *
0x14007660a  mov     r8, r14; unsigned __int16 *
0x14007660d  mov     rcx, rsi; unsigned __int16 *
0x140076610  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140076615  call    cs:__imp_IsDebuggerPresent
0x14007661b  test    eax, eax
0x14007661d  lea     rax, aAssert; "ASSERT"
0x140076624  jz      short loc_14007664C
0x140076626  mov     [rsp+70h+pSacl], r13
0x14007662b  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140076632  mov     [rsp+70h+var_48], rax
0x140076637  lea     ecx, [rbx-52h]; unsigned __int8
0x14007663a  mov     r9d, ebx
0x14007663d  mov     [rsp+70h+psidGroup], r14
0x140076642  mov     r8, rsi
0x140076645  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14007664a  jmp     short loc_14007666B
0x14007664c  mov     [rsp+70h+var_48], r13
0x140076651  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140076658  mov     r9, r14
0x14007665b  mov     [rsp+70h+psidGroup], rax
0x140076660  mov     r8d, ebx
0x140076663  mov     rdx, rsi
0x140076666  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14007666b  xor     edx, edx; lpSecurityAttributes
0x14007666d  mov     rcx, r15; lpPathName
0x140076670  call    cs:__imp_CreateDirectoryW
0x140076676  mov     ebx, eax
0x140076678  call    cs:__imp_GetLastError
0x14007667e  test    ebx, ebx
0x140076680  jnz     short loc_1400766A9
0x140076682  cmp     eax, 0B7h
0x140076687  jz      short loc_1400766A9
0x140076689  test    eax, eax
0x14007668b  jg      short loc_140076691
0x14007668d  mov     edi, eax
0x14007668f  jmp     short loc_14007669A
0x140076691  movzx   edi, ax
0x140076694  or      edi, 80070000h
0x14007669a  lea     r13, aFsuccessDwerro; "fSuccess || dwError == 183L"
0x1400766a1  mov     r15d, 58h ; 'X'
0x1400766a7  jmp     short loc_1400766FE
0x1400766a9  mov     rax, [rbp+pDacl]
0x1400766ad  xor     r9d, r9d; psidOwner
0x1400766b0  mov     [rsp+70h+pSacl], 0; pSacl
0x1400766b9  mov     r8d, 80000004h; SecurityInfo
0x1400766bf  mov     [rsp+70h+var_48], rax; pDacl
0x1400766c4  mov     rcx, r15; pObjectName
0x1400766c7  mov     [rsp+70h+psidGroup], 0; psidGroup
0x1400766d0  lea     edx, [r9+1]; ObjectType
0x1400766d4  call    cs:__imp_SetNamedSecurityInfoW
0x1400766da  test    eax, eax
0x1400766dc  jz      loc_140076762
0x1400766e2  jg      short loc_1400766E8
0x1400766e4  mov     edi, eax
0x1400766e6  jmp     short loc_1400766F1
0x1400766e8  movzx   edi, ax
0x1400766eb  or      edi, 80070000h
0x1400766f1  lea     r13, aDwerror0l; "dwError == 0L"
0x1400766f8  mov     r15d, 5Ch ; '\'
0x1400766fe  lea     rbx, aCbraex; "CBRAEx"
0x140076705  mov     dword ptr [rsp+70h+var_48], edi; int
0x140076709  mov     r9, rbx; unsigned __int16 *
0x14007670c  mov     [rsp+70h+psidGroup], r13; unsigned __int16 *
0x140076711  mov     r8, r14; unsigned __int16 *
0x140076714  mov     edx, r15d; unsigned int
0x140076717  mov     rcx, rsi; unsigned __int16 *
0x14007671a  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007671f  call    cs:__imp_IsDebuggerPresent
0x140076725  test    eax, eax
0x140076727  jz      short loc_14007673F
0x140076729  mov     [rsp+70h+var_38], edi
0x14007672d  mov     r9d, r15d
0x140076730  mov     [rsp+70h+pSacl], r13
0x140076735  mov     [rsp+70h+var_48], rbx
0x14007673a  jmp     loc_140076556
0x14007673f  mov     dword ptr [rsp+70h+pSacl], edi
0x140076743  mov     r8d, r15d
0x140076746  mov     [rsp+70h+var_48], r13
0x14007674b  mov     [rsp+70h+psidGroup], rbx
0x140076750  mov     r9, r14
0x140076753  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14007675a  mov     rdx, rsi
0x14007675d  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140076762  mov     rcx, [rbp+Block]; Block
0x140076766  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14007676b  mov     eax, edi
0x14007676d  add     rsp, 70h
0x140076771  pop     r15
0x140076773  pop     r14
0x140076775  pop     r13
0x140076777  pop     rdi
0x140076778  pop     rsi
0x140076779  pop     rbx
0x14007677a  pop     rbp
0x14007677b  retn
```
