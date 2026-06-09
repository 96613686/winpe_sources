# SSPI_CREDENTIAL::GetReferencedCredential(char const *,SSPI_CREDENTIAL * *,MULTISZ *)

- ea: `0x180007d34`
- end: `0x18000831d`
- name: `?GetReferencedCredential@SSPI_CREDENTIAL@@SAJPEBDPEAPEAV1@PEAVMULTISZ@@@Z`
- size: `1513`
- prototype: `__int64 __fastcall(const char *, struct SSPI_CREDENTIAL **, struct MULTISZ *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800021f0`
- `0x18000417c`
- `0x1800048f0`

## callees

- `0x180001024`
- `0x180001064`
- `0x180007d34`
- `0x180008ba0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000800b`
- `msvcrt!_wcsicmp` at `0x180008029`
- `msvcrt!_wcsicmp` at `0x18000800b`
- `msvcrt!_wcsicmp` at `0x180008029`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180008048`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180008190`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180008048`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180008190`
- `SspiCli!AcquireCredentialsHandleW` at `0x180008122`
- `SspiCli!AcquireCredentialsHandleW` at `0x180008122`
- `SspiCli!EnumerateSecurityPackagesW` at `0x180007fb0`
- `SspiCli!EnumerateSecurityPackagesW` at `0x180007fb0`
- `SspiCli!FreeContextBuffer` at `0x18000806a`
- `SspiCli!FreeContextBuffer` at `0x1800080dc`
- `SspiCli!FreeContextBuffer` at `0x1800081e9`
- `SspiCli!FreeContextBuffer` at `0x180008266`
- `SspiCli!FreeContextBuffer` at `0x180008279`
- `SspiCli!FreeContextBuffer` at `0x18000806a`
- `SspiCli!FreeContextBuffer` at `0x1800080dc`
- `SspiCli!FreeContextBuffer` at `0x1800081e9`
- `SspiCli!FreeContextBuffer` at `0x180008266`
- `SspiCli!FreeContextBuffer` at `0x180008279`
- `SspiCli!FreeCredentialsHandle` at `0x1800082c5`
- `SspiCli!FreeCredentialsHandle` at `0x1800082c5`
- `SspiCli!SspiExcludePackage` at `0x18000809e`
- `SspiCli!SspiExcludePackage` at `0x18000809e`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800080b4`
- `SspiCli!SspiFreeAuthIdentity` at `0x18000828c`
- `SspiCli!SspiFreeAuthIdentity` at `0x1800080b4`
- `SspiCli!SspiFreeAuthIdentity` at `0x18000828c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007fc3`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007dbb`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180007dbb`
- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180007ec8`
- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180007ec8`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007e91`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007e91`
- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x180007e5d`
- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x180008081`
- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x180007e5d`
- `iisutil!?FindString@MULTISZ@@QEAAHPEBG@Z` at `0x180008081`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008232`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008250`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008232`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180008250`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007dd2`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180007dd2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800082ee`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800082ee`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007efb`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180007efb`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800082dc`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800082dc`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800082d2`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x1800082d2`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180007f08`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180007f08`
- `iisutil!PuDbgPrint` at `0x18000817d`
- `iisutil!PuDbgPrint` at `0x18000817d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007d98`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007d98`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180007f7f`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180007f7f`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180007e49`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180007f67`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180007e49`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180007f67`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007f3d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180007f3d`

## string_xrefs

- `0x180008171`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x1800081b6`: `Error querying security package info, hr = %x\n`

## pseudocode

```c
__int64 __fastcall SSPI_CREDENTIAL::GetReferencedCredential(
        const char *a1,
        struct SSPI_CREDENTIAL **a2,
        struct MULTISZ *a3)
{
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE v3; // r14
  struct SSPI_CREDENTIAL **v5; // r12
  volatile signed __int32 *v7; // rbx
  signed int v8; // edi
  struct _LIST_ENTRY *i; // rsi
  struct _LIST_ENTRY *v10; // rdi
  int Flink_high; // eax
  const unsigned __int16 *v12; // rbx
  __int64 v13; // rax
  char *v14; // rax
  const unsigned __int16 *v15; // rsi
  __int64 v16; // rax
  int LastError; // eax
  bool v18; // cc
  int v19; // r15d
  unsigned int v20; // r12d
  __int64 v21; // rsi
  SECURITY_STATUS v22; // eax
  const char *v23; // rax
  __int64 v24; // r8
  SECURITY_STATUS v25; // eax
  struct _LIST_ENTRY *Flink; // rcx
  SEC_GET_KEY_FN pGetKeyFn; // [rsp+28h] [rbp-A1h]
  PSecPkgInfoW ppPackageInfo; // [rsp+50h] [rbp-79h] BYREF
  unsigned int pcPackages; // [rsp+58h] [rbp-71h] BYREF
  PSecPkgInfoW v31; // [rsp+60h] [rbp-69h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE ppNewAuthIdentity; // [rsp+68h] [rbp-61h] BYREF
  PSecPkgInfoW v33; // [rsp+70h] [rbp-59h] BYREF
  struct SSPI_CREDENTIAL **v34; // [rsp+78h] [rbp-51h]
  SECURITY_INTEGER ptsExpiry; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v36[32]; // [rsp+88h] [rbp-41h] BYREF
  LPWSTR pszPackage; // [rsp+A8h] [rbp-21h]
  _OWORD v38[2]; // [rsp+C0h] [rbp-9h] BYREF

  v3 = 0;
  v34 = a2;
  v31 = 0;
  ptsExpiry.QuadPart = 0;
  v5 = a2;
  ppPackageInfo = 0;
  ppNewAuthIdentity = 0;
  v7 = 0;
  memset(v38, 0, sizeof(v38));
  STRU::STRU((STRU *)v36, (unsigned __int16 *)v38, 0x10u);
  if ( !a1 || !v5 )
  {
    v8 = -2147024809;
    goto LABEL_74;
  }
  *v5 = 0;
  v8 = STRU::CopyA((STRU *)v36, a1);
  if ( v8 < 0 )
    goto LABEL_74;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
  for ( i = SSPI_CREDENTIAL::sm_CredentialListHead.Flink; i != &SSPI_CREDENTIAL::sm_CredentialListHead; i = i->Flink )
  {
    v10 = i - 8;
    if ( !strcmp(a1, (const char *)i[-6].Blink) )
    {
      Flink_high = HIDWORD(v10[12].Flink);
      if ( Flink_high )
      {
        if ( a3 && Flink_high == *((_DWORD *)a3 + 13) )
        {
          v12 = MULTISZ::First(a3);
          if ( !v12 )
            goto LABEL_17;
          while ( MULTISZ::FindString((MULTISZ *)&v10[9], v12) )
          {
            v13 = -1;
            do
              ++v13;
            while ( v12[v13] );
            v12 += v13 + 1;
            if ( !*v12 )
              goto LABEL_17;
          }
        }
        v3 = 0;
      }
      else
      {
        v3 = 0;
        if ( !a3 || !*((_DWORD *)a3 + 13) )
        {
LABEL_17:
          _InterlockedIncrement((volatile signed __int32 *)&v10->Flink + 1);
          CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
          *v5 = (struct SSPI_CREDENTIAL *)v10;
          v7 = 0;
          v8 = 0;
          goto LABEL_74;
        }
      }
    }
  }
  CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
  v14 = (char *)operator new(0xE0u);
  v7 = (volatile signed __int32 *)v14;
  if ( !v14 )
  {
    v8 = -2147024888;
    v7 = 0;
    goto LABEL_72;
  }
  *(_DWORD *)v14 = 1396917075;
  *((_DWORD *)v14 + 1) = 1;
  STRA::STRA((STRA *)(v14 + 8), v14 + 64, 0x40u);
  MULTISZ::MULTISZ((MULTISZ *)(v7 + 36));
  *((_QWORD *)v7 + 27) = 0;
  *((_QWORD *)v7 + 16) = 0;
  *((_QWORD *)v7 + 26) = -1;
  *((_QWORD *)v7 + 25) = -1;
  v8 = STRA::Copy((STRA *)(v7 + 2), a1);
  if ( v8 < 0 )
    goto LABEL_72;
  pcPackages = 0;
  if ( !a3 || !*((_DWORD *)a3 + 13) )
  {
LABEL_54:
    v22 = AcquireCredentialsHandleW(0, pszPackage, 1u, 0, ppNewAuthIdentity, 0, 0, (PCredHandle)(v7 + 50), &ptsExpiry);
    if ( v22 )
    {
      if ( v22 > 0 )
        v8 = (unsigned __int16)v22 | 0x80070000;
      else
        v8 = v22;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_72;
      v23 = "Error acquiring credential handle, hr = %x\n";
      v24 = 337;
    }
    else
    {
      v25 = QuerySecurityPackageInfoW(pszPackage, &v31);
      if ( !v25 )
      {
        *((_DWORD *)v7 + 54) = v31->cbMaxToken;
        *((_DWORD *)v7 + 55) = ((v31->fCapabilities >> 14) & 1) == 0;
        FreeContextBuffer(v31);
        Flink = SSPI_CREDENTIAL::sm_CredentialListHead.Flink;
        v31 = 0;
        if ( SSPI_CREDENTIAL::sm_CredentialListHead.Flink->Blink != &SSPI_CREDENTIAL::sm_CredentialListHead )
          __fastfail(3u);
        *((_QWORD *)v7 + 16) = SSPI_CREDENTIAL::sm_CredentialListHead.Flink;
        *((_QWORD *)v7 + 17) = &SSPI_CREDENTIAL::sm_CredentialListHead;
        Flink->Blink = (struct _LIST_ENTRY *)(v7 + 32);
        SSPI_CREDENTIAL::sm_CredentialListHead.Flink = (struct _LIST_ENTRY *)(v7 + 32);
        _InterlockedAdd(v7 + 1, 1u);
        CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
        *v5 = (struct SSPI_CREDENTIAL *)v7;
        v7 = 0;
        goto LABEL_74;
      }
      if ( v25 > 0 )
        v8 = (unsigned __int16)v25 | 0x80070000;
      else
        v8 = v25;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_72;
      v23 = "Error querying security package info, hr = %x\n";
      v24 = 350;
    }
    LODWORD(pGetKeyFn) = v8;
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\sspi_lib\\sspi_lib.cxx",
      v24,
      "SSPI_CREDENTIAL::GetReferencedCredential",
      v23,
      pGetKeyFn);
    goto LABEL_72;
  }
  v15 = MULTISZ::First(a3);
  if ( v15 )
  {
    do
    {
      if ( !MULTISZ::Append((MULTISZ *)(v7 + 36), v15) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          goto LABEL_34;
        goto LABEL_72;
      }
      v16 = -1;
      do
        ++v16;
      while ( v15[v16] );
      v15 += v16 + 1;
    }
    while ( *v15 );
    v3 = 0;
  }
  LastError = EnumerateSecurityPackagesW(&pcPackages, &ppPackageInfo);
  v18 = LastError <= 0;
  if ( LastError )
    goto LABEL_31;
  v19 = 0;
  v20 = 0;
  if ( !pcPackages )
  {
LABEL_51:
    if ( ppPackageInfo )
    {
      FreeContextBuffer(ppPackageInfo);
      ppPackageInfo = 0;
    }
    v5 = v34;
    goto LABEL_54;
  }
  while ( 1 )
  {
    v21 = v20;
    if ( !_wcsicmp(L"Negotiate", ppPackageInfo[v21].Name) || !_wcsicmp(L"NegoExtender", ppPackageInfo[v21].Name) )
      goto LABEL_50;
    v33 = 0;
    if ( !QuerySecurityPackageInfoW(ppPackageInfo[v21].Name, &v33) && (v33->fCapabilities & 0x200800) != 0 )
      v19 = 1;
    if ( v33 )
      FreeContextBuffer(v33);
    if ( !v19 )
    {
      v19 = 0;
      goto LABEL_50;
    }
    v19 = 0;
    if ( !MULTISZ::FindString(a3, ppPackageInfo[v21].Name) )
      break;
LABEL_50:
    if ( ++v20 >= pcPackages )
      goto LABEL_51;
  }
  LastError = SspiExcludePackage(v3, ppPackageInfo[v21].Name, &ppNewAuthIdentity);
  if ( !LastError )
  {
    if ( v3 )
      SspiFreeAuthIdentity(v3);
    v3 = ppNewAuthIdentity;
    goto LABEL_50;
  }
  v18 = LastError < 0;
LABEL_31:
  if ( v18 )
  {
    v8 = LastError;
    goto LABEL_72;
  }
LABEL_34:
  v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_72:
  CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
LABEL_74:
  if ( v31 )
  {
    FreeContextBuffer(v31);
    v31 = 0;
  }
  if ( ppPackageInfo )
  {
    FreeContextBuffer(ppPackageInfo);
    ppPackageInfo = 0;
  }
  if ( ppNewAuthIdentity )
  {
    SspiFreeAuthIdentity(ppNewAuthIdentity);
    ppNewAuthIdentity = 0;
  }
  if ( v7 && _InterlockedExchangeAdd(v7 + 1, 0xFFFFFFFF) == 1 )
  {
    *v7 = 1396917094;
    if ( *((_QWORD *)v7 + 25) != -1 && *((_QWORD *)v7 + 26) != -1 )
      FreeCredentialsHandle((PCredHandle)(v7 + 50));
    MULTISZ::~MULTISZ((MULTISZ *)(v7 + 36));
    STRA::~STRA((STRA *)(v7 + 2));
    operator delete((void *)v7);
  }
  STRU::~STRU((STRU *)v36);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007d34  mov     [rsp-8+arg_18], rbx
0x180007d39  push    rbp
0x180007d3a  push    rsi
0x180007d3b  push    rdi
0x180007d3c  push    r12
0x180007d3e  push    r13
0x180007d40  push    r14
0x180007d42  push    r15
0x180007d44  lea     rbp, [rsp-27h]
0x180007d49  sub     rsp, 0F0h
0x180007d50  mov     rax, cs:__security_cookie
0x180007d57  xor     rax, rsp
0x180007d5a  mov     [rbp+57h+var_40], rax
0x180007d5e  xor     r14d, r14d
0x180007d61  mov     [rbp+57h+var_A8], rdx
0x180007d65  xorps   xmm0, xmm0
0x180007d68  mov     [rbp+57h+var_C0], r14
0x180007d6c  mov     r13, r8
0x180007d6f  mov     qword ptr [rbp+57h+var_A0], r14
0x180007d73  mov     r12, rdx
0x180007d76  mov     [rbp+57h+ppPackageInfo], r14
0x180007d7a  mov     r15, rcx
0x180007d7d  mov     [rbp+57h+ppNewAuthIdentity], r14
0x180007d81  lea     r8d, [r14+10h]
0x180007d85  mov     ebx, r14d
0x180007d88  lea     rdx, [rbp+57h+var_60]
0x180007d8c  lea     rcx, [rbp+57h+var_98]
0x180007d90  movups  [rbp+57h+var_60], xmm0
0x180007d94  movups  [rbp+57h+var_50], xmm0
0x180007d98  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007d9e  test    r15, r15
0x180007da1  jz      loc_180008258
0x180007da7  test    r12, r12
0x180007daa  jz      loc_180008258
0x180007db0  mov     rdx, r15
0x180007db3  mov     [r12], r14
0x180007db7  lea     rcx, [rbp+57h+var_98]
0x180007dbb  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180007dc1  mov     edi, eax
0x180007dc3  test    eax, eax
0x180007dc5  js      loc_18000825D
0x180007dcb  lea     rcx, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x180007dd2  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180007dd8  mov     rsi, cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180007ddf  lea     rax, ?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180007de6  lea     edi, [r14+1]
0x180007dea  cmp     rsi, rax
0x180007ded  jz      loc_180007EC1
0x180007df3  lea     rdi, [rsi-80h]
0x180007df7  mov     rax, r15
0x180007dfa  mov     r8, [rdi+28h]
0x180007dfe  sub     r8, r15
0x180007e01  movzx   ecx, byte ptr [rax]
0x180007e04  movzx   edx, byte ptr [rax+r8]
0x180007e09  sub     ecx, edx
0x180007e0b  jnz     short loc_180007E14
0x180007e0d  inc     rax
0x180007e10  test    edx, edx
0x180007e12  jnz     short loc_180007E01
0x180007e14  test    ecx, ecx
0x180007e16  jnz     loc_180007EA9
0x180007e1c  lea     r14, [rdi+90h]
0x180007e23  mov     eax, [r14+34h]
0x180007e27  test    eax, eax
0x180007e29  jnz     short loc_180007E3B
0x180007e2b  xor     r14d, r14d
0x180007e2e  test    r13, r13
0x180007e31  jz      short loc_180007E86
0x180007e33  cmp     [r13+34h], r14d
0x180007e37  jz      short loc_180007E86
0x180007e39  jmp     short loc_180007EA9
0x180007e3b  test    r13, r13
0x180007e3e  jz      short loc_180007EA6
0x180007e40  cmp     eax, [r13+34h]
0x180007e44  jnz     short loc_180007EA6
0x180007e46  mov     rcx, r13
0x180007e49  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180007e4f  mov     rbx, rax
0x180007e52  test    rax, rax
0x180007e55  jz      short loc_180007E83
0x180007e57  mov     rdx, rbx
0x180007e5a  mov     rcx, r14
0x180007e5d  call    cs:__imp_?FindString@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindString(ushort const *)
0x180007e63  xor     ecx, ecx
0x180007e65  test    eax, eax
0x180007e67  jz      short loc_180007EA6
0x180007e69  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007e6d  inc     rax
0x180007e70  cmp     [rbx+rax*2], cx
0x180007e74  jnz     short loc_180007E6D
0x180007e76  lea     rbx, [rbx+rax*2]
0x180007e7a  add     rbx, 2
0x180007e7e  cmp     [rbx], cx
0x180007e81  jnz     short loc_180007E57
0x180007e83  xor     r14d, r14d
0x180007e86  lock inc dword ptr [rdi+4]
0x180007e8a  lea     rcx, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x180007e91  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180007e97  mov     [r12], rdi
0x180007e9b  mov     rbx, r14
0x180007e9e  mov     edi, r14d
0x180007ea1  jmp     loc_18000825D
0x180007ea6  xor     r14d, r14d
0x180007ea9  mov     rsi, [rsi]
0x180007eac  lea     rax, ?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180007eb3  cmp     rsi, rax
0x180007eb6  jnz     loc_180007DF3
0x180007ebc  mov     edi, 1
0x180007ec1  lea     rcx, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x180007ec8  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x180007ece  mov     ecx, 0E0h; Size
0x180007ed3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007ed8  mov     rbx, rax
0x180007edb  test    rax, rax
0x180007ede  jz      loc_180008241
0x180007ee4  lea     rdx, [rax+40h]
0x180007ee8  mov     dword ptr [rax], 53434353h
0x180007eee  lea     rcx, [rax+8]
0x180007ef2  mov     [rax+4], edi
0x180007ef5  mov     r8d, 40h ; '@'
0x180007efb  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180007f01  lea     rcx, [rbx+90h]
0x180007f08  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180007f0e  lea     rcx, [rbx+8]
0x180007f12  mov     qword ptr [rbx+0D8h], 0
0x180007f1d  mov     rdx, r15
0x180007f20  mov     [rbx+80h], r14
0x180007f27  mov     qword ptr [rbx+0D0h], 0FFFFFFFFFFFFFFFFh
0x180007f32  mov     qword ptr [rbx+0C8h], 0FFFFFFFFFFFFFFFFh
0x180007f3d  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180007f43  mov     edi, eax
0x180007f45  test    eax, eax
0x180007f47  js      loc_180008249
0x180007f4d  mov     [rbp+57h+pcPackages], r14d
0x180007f51  test    r13, r13
0x180007f54  jz      loc_1800080EA
0x180007f5a  cmp     [r13+34h], r14d
0x180007f5e  jbe     loc_1800080EA
0x180007f64  mov     rcx, r13
0x180007f67  call    cs:__imp_?First@MULTISZ@@QEBAPEBGXZ; MULTISZ::First(void)
0x180007f6d  mov     rsi, rax
0x180007f70  test    rax, rax
0x180007f73  jz      short loc_180007FA8
0x180007f75  mov     rdx, rsi
0x180007f78  lea     rcx, [rbx+90h]
0x180007f7f  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180007f85  xor     ecx, ecx
0x180007f87  test    eax, eax
0x180007f89  jz      short loc_180007FC3
0x180007f8b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007f8f  inc     rax
0x180007f92  cmp     [rsi+rax*2], cx
0x180007f96  jnz     short loc_180007F8F
0x180007f98  lea     rsi, [rsi+rax*2]
0x180007f9c  add     rsi, 2
0x180007fa0  cmp     [rsi], cx
0x180007fa3  jnz     short loc_180007F75
0x180007fa5  xor     r14d, r14d
0x180007fa8  lea     rdx, [rbp+57h+ppPackageInfo]; ppPackageInfo
0x180007fac  lea     rcx, [rbp+57h+pcPackages]; pcPackages
0x180007fb0  call    cs:__imp_EnumerateSecurityPackagesW
0x180007fb6  test    eax, eax
0x180007fb8  jz      short loc_180007FE4
0x180007fba  jg      short loc_180007FD6
0x180007fbc  mov     edi, eax
0x180007fbe  jmp     loc_180008249
0x180007fc3  call    cs:__imp_GetLastError
0x180007fc9  xor     r14d, r14d
0x180007fcc  mov     edi, eax
0x180007fce  test    eax, eax
0x180007fd0  jle     loc_180008249
0x180007fd6  movzx   edi, ax
0x180007fd9  or      edi, 80070000h
0x180007fdf  jmp     loc_180008249
0x180007fe4  xor     r15d, r15d
0x180007fe7  mov     r12d, r15d
0x180007fea  cmp     [rbp+57h+pcPackages], r15d
0x180007fee  jbe     loc_1800080D0
0x180007ff4  mov     rdx, [rbp+57h+ppPackageInfo]
0x180007ff8  lea     rcx, aNegotiate; "Negotiate"
0x180007fff  mov     esi, r12d
0x180008002  shl     rsi, 5
0x180008006  mov     rdx, [rsi+rdx+10h]; String2
0x18000800b  call    cs:__imp__wcsicmp
0x180008011  test    eax, eax
0x180008013  jz      loc_1800080C3
0x180008019  mov     rdx, [rbp+57h+ppPackageInfo]
0x18000801d  lea     rcx, aNegoextender; "NegoExtender"
0x180008024  mov     rdx, [rsi+rdx+10h]; String2
0x180008029  call    cs:__imp__wcsicmp
0x18000802f  test    eax, eax
0x180008031  jz      loc_1800080C3
0x180008037  mov     rcx, [rbp+57h+ppPackageInfo]
0x18000803b  lea     rdx, [rbp+57h+var_B0]; ppPackageInfo
0x18000803f  mov     [rbp+57h+var_B0], r15
0x180008043  mov     rcx, [rsi+rcx+10h]; pszPackageName
0x180008048  call    cs:__imp_QuerySecurityPackageInfoW
0x18000804e  mov     rcx, [rbp+57h+var_B0]; pvContextBuffer
0x180008052  test    eax, eax
0x180008054  jnz     short loc_180008065
0x180008056  test    dword ptr [rcx], 200800h
0x18000805c  mov     eax, 1
0x180008061  cmovnz  r15d, eax
0x180008065  test    rcx, rcx
0x180008068  jz      short loc_180008070
0x18000806a  call    cs:__imp_FreeContextBuffer
0x180008070  test    r15d, r15d
0x180008073  jz      short loc_1800080C0
0x180008075  mov     rdx, [rbp+57h+ppPackageInfo]
0x180008079  mov     rcx, r13
0x18000807c  mov     rdx, [rsi+rdx+10h]
0x180008081  call    cs:__imp_?FindString@MULTISZ@@QEAAHPEBG@Z; MULTISZ::FindString(ushort const *)
0x180008087  xor     r15d, r15d
0x18000808a  test    eax, eax
0x18000808c  jnz     short loc_1800080C3
0x18000808e  mov     rdx, [rbp+57h+ppPackageInfo]
0x180008092  lea     r8, [rbp+57h+ppNewAuthIdentity]; ppNewAuthIdentity
0x180008096  mov     rcx, r14; AuthIdentity
0x180008099  mov     rdx, [rsi+rdx+10h]; pszPackageName
0x18000809e  call    cs:__imp_SspiExcludePackage
0x1800080a4  test    eax, eax
0x1800080a6  jnz     loc_180008132
0x1800080ac  test    r14, r14
0x1800080af  jz      short loc_1800080BA
0x1800080b1  mov     rcx, r14; AuthData
0x1800080b4  call    cs:__imp_SspiFreeAuthIdentity
0x1800080ba  mov     r14, [rbp+57h+ppNewAuthIdentity]
0x1800080be  jmp     short loc_1800080C3
0x1800080c0  xor     r15d, r15d
0x1800080c3  inc     r12d
0x1800080c6  cmp     r12d, [rbp+57h+pcPackages]
0x1800080ca  jb      loc_180007FF4
0x1800080d0  mov     rcx, [rbp+57h+ppPackageInfo]; pvContextBuffer
0x1800080d4  xor     r14d, r14d
0x1800080d7  test    rcx, rcx
0x1800080da  jz      short loc_1800080E6
0x1800080dc  call    cs:__imp_FreeContextBuffer
0x1800080e2  mov     [rbp+57h+ppPackageInfo], r14
0x1800080e6  mov     r12, [rbp+57h+var_A8]
0x1800080ea  mov     rcx, [rbp+57h+ppNewAuthIdentity]
0x1800080ee  lea     rdx, [rbp+57h+var_A0]
0x1800080f2  mov     [rsp+120h+ptsExpiry], rdx; ptsExpiry
0x1800080f7  lea     rax, [rbx+0C8h]
0x1800080fe  mov     rdx, [rbp+57h+pszPackage]; pszPackage
0x180008102  xor     r9d, r9d; pvLogonId
0x180008105  mov     [rsp+120h+phCredential], rax; phCredential
0x18000810a  mov     [rsp+120h+pvGetKeyArgument], r14; pvGetKeyArgument
0x18000810f  mov     [rsp+120h+pGetKeyFn], r14; pGetKeyFn
0x180008114  lea     esi, [r9+1]
0x180008118  mov     [rsp+120h+pAuthData], rcx; pAuthData
0x18000811d  mov     r8d, esi; fCredentialUse
0x180008120  xor     ecx, ecx; pszPrincipal
0x180008122  call    cs:__imp_AcquireCredentialsHandleW
0x180008128  test    eax, eax
0x18000812a  jz      short loc_180008188
0x18000812c  jg      short loc_18000813C
0x18000812e  mov     edi, eax
0x180008130  jmp     short loc_180008145
0x180008132  xor     r14d, r14d
0x180008135  test    eax, eax
0x180008137  jmp     loc_180007FBA
0x18000813c  movzx   edi, ax
0x18000813f  or      edi, 80070000h
0x180008145  test    byte ptr cs:g_dwDebugFlags, 3
0x18000814c  jz      loc_180008249
0x180008152  lea     rax, aErrorAcquiring; "Error acquiring credential handle, hr ="...
0x180008159  mov     r8d, 151h
0x18000815f  mov     rcx, cs:g_pDebug
0x180008166  lea     r9, aSspiCredential; "SSPI_CREDENTIAL::GetReferencedCredentia"...
0x18000816d  mov     dword ptr [rsp+120h+pGetKeyFn], edi
0x180008171  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180008178  mov     [rsp+120h+pAuthData], rax
0x18000817d  call    cs:__imp_PuDbgPrint
0x180008183  jmp     loc_180008249
0x180008188  mov     rcx, [rbp+57h+pszPackage]; pszPackageName
0x18000818c  lea     rdx, [rbp+57h+var_C0]; ppPackageInfo
0x180008190  call    cs:__imp_QuerySecurityPackageInfoW
0x180008196  test    eax, eax
0x180008198  jz      short loc_1800081C5
0x18000819a  jg      short loc_1800081A0
0x18000819c  mov     edi, eax
0x18000819e  jmp     short loc_1800081A9
0x1800081a0  movzx   edi, ax
0x1800081a3  or      edi, 80070000h
0x1800081a9  test    byte ptr cs:g_dwDebugFlags, 3
0x1800081b0  jz      loc_180008249
0x1800081b6  lea     rax, aErrorQueryingS; "Error querying security package info, h"...
0x1800081bd  mov     r8d, 15Eh
0x1800081c3  jmp     short loc_18000815F
0x1800081c5  mov     rax, [rbp+57h+var_C0]
0x1800081c9  mov     ecx, [rax+8]
0x1800081cc  mov     [rbx+0D8h], ecx
0x1800081d2  mov     rax, [rbp+57h+var_C0]
0x1800081d6  mov     ecx, [rax]
0x1800081d8  shr     ecx, 0Eh
0x1800081db  not     ecx
0x1800081dd  and     ecx, esi
0x1800081df  mov     [rbx+0DCh], ecx
0x1800081e5  mov     rcx, [rbp+57h+var_C0]; pvContextBuffer
0x1800081e9  call    cs:__imp_FreeContextBuffer
  ... truncated ...
```
