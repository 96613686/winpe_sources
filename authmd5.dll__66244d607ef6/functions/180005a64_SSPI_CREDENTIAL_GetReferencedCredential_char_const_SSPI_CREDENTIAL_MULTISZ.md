# SSPI_CREDENTIAL::GetReferencedCredential(char const *,SSPI_CREDENTIAL * *,MULTISZ *)

- ea: `0x180005a64`
- end: `0x180005db4`
- name: `?GetReferencedCredential@SSPI_CREDENTIAL@@SAJPEBDPEAPEAV1@PEAVMULTISZ@@@Z`
- size: `848`
- prototype: `__int64 __fastcall(const char *, struct SSPI_CREDENTIAL **, struct MULTISZ *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001e00`
- `0x180003200`

## callees

- `0x180001024`
- `0x180001064`
- `0x180005a64`
- `0x1800065d2`
- `0x180006600`

## import_xrefs

- `SspiCli!QuerySecurityPackageInfoW` at `0x180005c65`
- `SspiCli!QuerySecurityPackageInfoW` at `0x180005c65`
- `SspiCli!FreeContextBuffer` at `0x180005cbf`
- `SspiCli!FreeContextBuffer` at `0x180005d2c`
- `SspiCli!FreeContextBuffer` at `0x180005cbf`
- `SspiCli!FreeContextBuffer` at `0x180005d2c`
- `SspiCli!AcquireCredentialsHandleW` at `0x180005be6`
- `SspiCli!AcquireCredentialsHandleW` at `0x180005be6`
- `SspiCli!FreeCredentialsHandle` at `0x180005d63`
- `SspiCli!FreeCredentialsHandle` at `0x180005d63`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005d7a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180005d7a`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005d70`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180005d70`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180005ad4`
- `iisutil!?CopyA@STRU@@QEAAJPEBD@Z` at `0x180005ad4`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180005b6b`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180005b6b`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005ab3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005ab3`
- `iisutil!PuDbgPrint` at `0x180005c52`
- `iisutil!PuDbgPrint` at `0x180005c52`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005ba5`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x180005ba5`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005b78`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x180005b78`
- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180005b34`
- `iisutil!?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ` at `0x180005b34`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005d8c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005d8c`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005bfd`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005bfd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005cfd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005d16`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005cfd`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180005d16`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005aee`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180005aee`

## string_xrefs

- `0x180005c46`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\sspi_lib\sspi_lib.cxx`
- `0x180005c8b`: `Error querying security package info, hr = %x\n`

## pseudocode

```c
__int64 __fastcall SSPI_CREDENTIAL::GetReferencedCredential(
        const char *a1,
        struct _LIST_ENTRY **a2,
        struct MULTISZ *a3)
{
  char *v4; // rbx
  signed int v5; // edi
  struct _LIST_ENTRY *i; // rbx
  struct _LIST_ENTRY *v7; // rdi
  char *v8; // rax
  SECURITY_STATUS v9; // eax
  const char *v10; // rax
  __int64 v11; // r8
  SECURITY_STATUS v12; // eax
  struct _LIST_ENTRY *Flink; // rcx
  SEC_GET_KEY_FN pGetKeyFn; // [rsp+28h] [rbp-81h]
  PSecPkgInfoW ppPackageInfo; // [rsp+50h] [rbp-59h] BYREF
  SECURITY_INTEGER ptsExpiry; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v18[32]; // [rsp+60h] [rbp-49h] BYREF
  LPWSTR pszPackage; // [rsp+80h] [rbp-29h]
  _OWORD v20[2]; // [rsp+98h] [rbp-11h] BYREF

  ppPackageInfo = 0;
  ptsExpiry.QuadPart = 0;
  v4 = 0;
  memset(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v18, (unsigned __int16 *)v20, 0x10u);
  if ( a2 )
  {
    *a2 = 0;
    v5 = STRU::CopyA((STRU *)v18, "wdigest");
    if ( v5 < 0 )
      goto LABEL_30;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
    for ( i = SSPI_CREDENTIAL::sm_CredentialListHead.Flink; i != &SSPI_CREDENTIAL::sm_CredentialListHead; i = i->Flink )
    {
      v7 = i - 8;
      if ( !strcmp_0("wdigest", (const char *)i[-6].Blink) && !HIDWORD(v7[12].Flink) )
      {
        _InterlockedIncrement((volatile signed __int32 *)&v7->Flink + 1);
        CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
        *a2 = v7;
        v4 = 0;
        v5 = 0;
        goto LABEL_30;
      }
    }
    CReaderWriterLock3::ConvertSharedToExclusive((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
    v8 = (char *)operator new(0xE0u);
    v4 = v8;
    if ( !v8 )
    {
      v5 = -2147024888;
      v4 = 0;
      goto LABEL_28;
    }
    *(_DWORD *)v8 = 1396917075;
    *((_DWORD *)v8 + 1) = 1;
    STRA::STRA((STRA *)(v8 + 8), v8 + 64, 0x40u);
    MULTISZ::MULTISZ((MULTISZ *)(v4 + 144));
    *((_QWORD *)v4 + 27) = 0;
    *((_QWORD *)v4 + 16) = 0;
    *((_QWORD *)v4 + 26) = -1;
    *((_QWORD *)v4 + 25) = -1;
    v5 = STRA::Copy((STRA *)(v4 + 8), "wdigest");
    if ( v5 < 0 )
    {
LABEL_28:
      CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
      goto LABEL_30;
    }
    v9 = AcquireCredentialsHandleW(0, pszPackage, 1u, 0, 0, 0, 0, (PCredHandle)(v4 + 200), &ptsExpiry);
    if ( v9 )
    {
      if ( v9 > 0 )
        v5 = (unsigned __int16)v9 | 0x80070000;
      else
        v5 = v9;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_28;
      v10 = "Error acquiring credential handle, hr = %x\n";
      v11 = 337;
      goto LABEL_17;
    }
    v12 = QuerySecurityPackageInfoW(pszPackage, &ppPackageInfo);
    if ( v12 )
    {
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      else
        v5 = v12;
      if ( (g_dwDebugFlags & 3) == 0 )
        goto LABEL_28;
      v10 = "Error querying security package info, hr = %x\n";
      v11 = 350;
LABEL_17:
      LODWORD(pGetKeyFn) = v5;
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\sspi_lib\\sspi_lib.cxx",
        v11,
        "SSPI_CREDENTIAL::GetReferencedCredential",
        v10,
        pGetKeyFn);
      goto LABEL_28;
    }
    *((_DWORD *)v4 + 54) = ppPackageInfo->cbMaxToken;
    *((_DWORD *)v4 + 55) = (ppPackageInfo->fCapabilities & 0x4000) == 0;
    FreeContextBuffer(ppPackageInfo);
    Flink = SSPI_CREDENTIAL::sm_CredentialListHead.Flink;
    ppPackageInfo = 0;
    if ( SSPI_CREDENTIAL::sm_CredentialListHead.Flink->Blink != &SSPI_CREDENTIAL::sm_CredentialListHead )
      __fastfail(3u);
    *((_QWORD *)v4 + 16) = SSPI_CREDENTIAL::sm_CredentialListHead.Flink;
    *((_QWORD *)v4 + 17) = &SSPI_CREDENTIAL::sm_CredentialListHead;
    Flink->Blink = (struct _LIST_ENTRY *)(v4 + 128);
    SSPI_CREDENTIAL::sm_CredentialListHead.Flink = (struct _LIST_ENTRY *)(v4 + 128);
    _InterlockedIncrement((volatile signed __int32 *)v4 + 1);
    CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)&SSPI_CREDENTIAL::sm_SSPICredentialLock);
    *a2 = (struct _LIST_ENTRY *)v4;
    v4 = 0;
  }
  else
  {
    v5 = -2147024809;
  }
LABEL_30:
  if ( ppPackageInfo )
  {
    FreeContextBuffer(ppPackageInfo);
    ppPackageInfo = 0;
  }
  if ( v4 && _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 1, 0xFFFFFFFF) == 1 )
  {
    *(_DWORD *)v4 = 1396917094;
    if ( *((_QWORD *)v4 + 25) != -1 && *((_QWORD *)v4 + 26) != -1 )
      FreeCredentialsHandle((PCredHandle)(v4 + 200));
    MULTISZ::~MULTISZ((MULTISZ *)(v4 + 144));
    STRA::~STRA((STRA *)(v4 + 8));
    operator delete(v4);
  }
  STRU::~STRU((STRU *)v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005a64  push    rbp
0x180005a66  push    rbx
0x180005a67  push    rsi
0x180005a68  push    rdi
0x180005a69  push    r12
0x180005a6b  push    r13
0x180005a6d  push    r14
0x180005a6f  push    r15
0x180005a71  lea     rbp, [rsp-1Fh]
0x180005a76  sub     rsp, 0C8h
0x180005a7d  mov     rax, cs:__security_cookie
0x180005a84  xor     rax, rsp
0x180005a87  mov     [rbp+57h+var_48], rax
0x180005a8b  xor     r14d, r14d
0x180005a8e  lea     rcx, [rbp+57h+var_A0]
0x180005a92  xorps   xmm0, xmm0
0x180005a95  mov     [rbp+57h+ppPackageInfo], r14
0x180005a99  mov     rsi, rdx
0x180005a9c  mov     qword ptr [rbp+57h+var_A8], r14
0x180005aa0  lea     rdx, [rbp+57h+var_68]
0x180005aa4  mov     ebx, r14d
0x180005aa7  lea     r8d, [r14+10h]
0x180005aab  movups  [rbp+57h+var_68], xmm0
0x180005aaf  movups  [rbp+57h+var_58], xmm0
0x180005ab3  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005ab9  or      r15, 0FFFFFFFFFFFFFFFFh
0x180005abd  test    rsi, rsi
0x180005ac0  jz      loc_180005D1E
0x180005ac6  lea     rdx, Str1; "wdigest"
0x180005acd  mov     [rsi], r14
0x180005ad0  lea     rcx, [rbp+57h+var_A0]
0x180005ad4  call    cs:__imp_?CopyA@STRU@@QEAAJPEBD@Z; STRU::CopyA(char const *)
0x180005ada  mov     edi, eax
0x180005adc  test    eax, eax
0x180005ade  js      loc_180005D23
0x180005ae4  lea     r12, ?sm_SSPICredentialLock@SSPI_CREDENTIAL@@0VCReaderWriterLock3@@A; CReaderWriterLock3 SSPI_CREDENTIAL::sm_SSPICredentialLock
0x180005aeb  mov     rcx, r12
0x180005aee  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180005af4  mov     rbx, cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005afb  lea     r13, ?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005b02  jmp     short loc_180005B2C
0x180005b04  lea     rdi, [rbx-80h]
0x180005b08  mov     rdx, [rdi+28h]; Str2
0x180005b0c  lea     rcx, Str1; "wdigest"
0x180005b13  call    strcmp_0
0x180005b18  test    eax, eax
0x180005b1a  jnz     short loc_180005B29
0x180005b1c  cmp     [rdi+0C4h], r14d
0x180005b23  jz      loc_180005BF6
0x180005b29  mov     rbx, [rbx]
0x180005b2c  cmp     rbx, r13
0x180005b2f  jnz     short loc_180005B04
0x180005b31  mov     rcx, r12
0x180005b34  call    cs:__imp_?ConvertSharedToExclusive@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ConvertSharedToExclusive(void)
0x180005b3a  mov     ecx, 0E0h; Size
0x180005b3f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005b44  mov     rbx, rax
0x180005b47  test    rax, rax
0x180005b4a  jz      loc_180005D0B
0x180005b50  lea     rdx, [rax+40h]
0x180005b54  mov     dword ptr [rax], 53434353h
0x180005b5a  lea     rcx, [rax+8]
0x180005b5e  mov     dword ptr [rax+4], 1
0x180005b65  mov     r8d, 40h ; '@'
0x180005b6b  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180005b71  lea     rcx, [rbx+90h]
0x180005b78  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180005b7e  lea     rcx, [rbx+8]
0x180005b82  mov     [rbx+0D8h], r14
0x180005b89  lea     rdx, Str1; "wdigest"
0x180005b90  mov     [rbx+80h], r14
0x180005b97  mov     [rbx+0D0h], r15
0x180005b9e  mov     [rbx+0C8h], r15
0x180005ba5  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180005bab  mov     edi, eax
0x180005bad  test    eax, eax
0x180005baf  js      loc_180005D13
0x180005bb5  mov     rdx, [rbp+57h+pszPackage]; pszPackage
0x180005bb9  lea     rcx, [rbp+57h+var_A8]
0x180005bbd  mov     [rsp+100h+ptsExpiry], rcx; ptsExpiry
0x180005bc2  lea     rax, [rbx+0C8h]
0x180005bc9  mov     [rsp+100h+phCredential], rax; phCredential
0x180005bce  xor     r9d, r9d; pvLogonId
0x180005bd1  mov     [rsp+100h+pvGetKeyArgument], r14; pvGetKeyArgument
0x180005bd6  xor     ecx, ecx; pszPrincipal
0x180005bd8  mov     [rsp+100h+pGetKeyFn], r14; pGetKeyFn
0x180005bdd  mov     [rsp+100h+pAuthData], r14; pAuthData
0x180005be2  lea     r8d, [r9+1]; fCredentialUse
0x180005be6  call    cs:__imp_AcquireCredentialsHandleW
0x180005bec  test    eax, eax
0x180005bee  jz      short loc_180005C5D
0x180005bf0  jg      short loc_180005C11
0x180005bf2  mov     edi, eax
0x180005bf4  jmp     short loc_180005C1A
0x180005bf6  lock inc dword ptr [rdi+4]
0x180005bfa  mov     rcx, r12
0x180005bfd  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180005c03  mov     [rsi], rdi
0x180005c06  mov     rbx, r14
0x180005c09  mov     edi, r14d
0x180005c0c  jmp     loc_180005D23
0x180005c11  movzx   edi, ax
0x180005c14  or      edi, 80070000h
0x180005c1a  test    byte ptr cs:g_dwDebugFlags, 3
0x180005c21  jz      loc_180005D13
0x180005c27  lea     rax, aErrorAcquiring; "Error acquiring credential handle, hr ="...
0x180005c2e  mov     r8d, 151h
0x180005c34  mov     rcx, cs:g_pDebug
0x180005c3b  lea     r9, aSspiCredential; "SSPI_CREDENTIAL::GetReferencedCredentia"...
0x180005c42  mov     dword ptr [rsp+100h+pGetKeyFn], edi
0x180005c46  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005c4d  mov     [rsp+100h+pAuthData], rax
0x180005c52  call    cs:__imp_PuDbgPrint
0x180005c58  jmp     loc_180005D13
0x180005c5d  mov     rcx, [rbp+57h+pszPackage]; pszPackageName
0x180005c61  lea     rdx, [rbp+57h+ppPackageInfo]; ppPackageInfo
0x180005c65  call    cs:__imp_QuerySecurityPackageInfoW
0x180005c6b  test    eax, eax
0x180005c6d  jz      short loc_180005C9A
0x180005c6f  jg      short loc_180005C75
0x180005c71  mov     edi, eax
0x180005c73  jmp     short loc_180005C7E
0x180005c75  movzx   edi, ax
0x180005c78  or      edi, 80070000h
0x180005c7e  test    byte ptr cs:g_dwDebugFlags, 3
0x180005c85  jz      loc_180005D13
0x180005c8b  lea     rax, aErrorQueryingS; "Error querying security package info, h"...
0x180005c92  mov     r8d, 15Eh
0x180005c98  jmp     short loc_180005C34
0x180005c9a  mov     rax, [rbp+57h+ppPackageInfo]
0x180005c9e  mov     ecx, [rax+8]
0x180005ca1  mov     [rbx+0D8h], ecx
0x180005ca7  mov     rax, [rbp+57h+ppPackageInfo]
0x180005cab  mov     ecx, [rax]
0x180005cad  shr     ecx, 0Eh
0x180005cb0  not     ecx
0x180005cb2  and     ecx, 1
0x180005cb5  mov     [rbx+0DCh], ecx
0x180005cbb  mov     rcx, [rbp+57h+ppPackageInfo]; pvContextBuffer
0x180005cbf  call    cs:__imp_FreeContextBuffer
0x180005cc5  mov     rcx, cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005ccc  mov     [rbp+57h+ppPackageInfo], r14
0x180005cd0  cmp     [rcx+8], r13
0x180005cd4  jz      short loc_180005CDD
0x180005cd6  mov     ecx, 3
0x180005cdb  int     29h; Win8: RtlFailFast(ecx)
0x180005cdd  lea     rax, [rbx+80h]
0x180005ce4  mov     [rax], rcx
0x180005ce7  mov     [rax+8], r13
0x180005ceb  mov     [rcx+8], rax
0x180005cef  mov     cs:?sm_CredentialListHead@SSPI_CREDENTIAL@@0U_LIST_ENTRY@@A, rax; _LIST_ENTRY SSPI_CREDENTIAL::sm_CredentialListHead
0x180005cf6  lock inc dword ptr [rbx+4]
0x180005cfa  mov     rcx, r12
0x180005cfd  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180005d03  mov     [rsi], rbx
0x180005d06  mov     rbx, r14
0x180005d09  jmp     short loc_180005D23
0x180005d0b  mov     edi, 80070008h
0x180005d10  mov     rbx, r14
0x180005d13  mov     rcx, r12
0x180005d16  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180005d1c  jmp     short loc_180005D23
0x180005d1e  mov     edi, 80070057h
0x180005d23  mov     rcx, [rbp+57h+ppPackageInfo]; pvContextBuffer
0x180005d27  test    rcx, rcx
0x180005d2a  jz      short loc_180005D36
0x180005d2c  call    cs:__imp_FreeContextBuffer
0x180005d32  mov     [rbp+57h+ppPackageInfo], r14
0x180005d36  test    rbx, rbx
0x180005d39  jz      short loc_180005D88
0x180005d3b  mov     eax, r15d
0x180005d3e  lock xadd [rbx+4], eax
0x180005d43  add     eax, r15d
0x180005d46  jnz     short loc_180005D88
0x180005d48  lea     rcx, [rbx+0C8h]; phCredential
0x180005d4f  mov     dword ptr [rbx], 53434366h
0x180005d55  cmp     [rcx], r15
0x180005d58  jz      short loc_180005D69
0x180005d5a  cmp     [rbx+0D0h], r15
0x180005d61  jz      short loc_180005D69
0x180005d63  call    cs:__imp_FreeCredentialsHandle
0x180005d69  lea     rcx, [rbx+90h]
0x180005d70  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180005d76  lea     rcx, [rbx+8]
0x180005d7a  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180005d80  mov     rcx, rbx; Block
0x180005d83  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005d88  lea     rcx, [rbp+57h+var_A0]
0x180005d8c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005d92  mov     eax, edi
0x180005d94  mov     rcx, [rbp+57h+var_48]
0x180005d98  xor     rcx, rsp; StackCookie
0x180005d9b  call    __security_check_cookie
0x180005da0  add     rsp, 0C8h
0x180005da7  pop     r15
0x180005da9  pop     r14
0x180005dab  pop     r13
0x180005dad  pop     r12
0x180005daf  pop     rdi
0x180005db0  pop     rsi
0x180005db1  pop     rbx
0x180005db2  pop     rbp
0x180005db3  retn
```
