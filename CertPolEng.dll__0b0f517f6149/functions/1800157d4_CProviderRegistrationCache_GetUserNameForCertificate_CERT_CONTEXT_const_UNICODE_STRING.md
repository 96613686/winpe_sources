# CProviderRegistrationCache::GetUserNameForCertificate(_CERT_CONTEXT const *,_UNICODE_STRING *)

- ea: `0x1800157d4`
- end: `0x180015af0`
- name: `?GetUserNameForCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z`
- size: `796`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const struct _CERT_CONTEXT *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013a30`

## callees

- `0x180003dc0`
- `0x180003fb0`
- `0x1800061e0`
- `0x180007b70`
- `0x180007c90`
- `0x180007ea0`
- `0x180009510`
- `0x18000c344`
- `0x180013ec8`
- `0x180014088`
- `0x1800157d4`
- `0x180016b10`
- `0x180017d88`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800159d0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800159d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015aa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ab2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015aa4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180015ab2`
- `ntdll!RtlReleaseResource` at `0x18001592d`
- `ntdll!RtlReleaseResource` at `0x18001592d`
- `ntdll!RtlCreateUnicodeString` at `0x180015a2a`
- `ntdll!RtlCreateUnicodeString` at `0x180015a2a`

## string_xrefs

- `0x180015983`: `ConvertIdentityToSid`
- `0x180015849`: `CProviderRegistrationCache::GetUserNameForCertificate`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetUserNameForCertificate(
        CProviderRegistrationCache *this,
        const struct _CERT_CONTEXT *a2,
        struct _UNICODE_STRING *a3)
{
  CProviderRegistrationCache *v5; // rsi
  WCHAR *v6; // rdi
  unsigned __int16 *v7; // rbx
  CProviderRegistrationCache *v8; // rcx
  unsigned int NameFromCert; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int ProvFromCertificate; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // r14d
  unsigned int v16; // eax
  __int64 v17; // rdx
  CProviderRegistrationCache *v18; // rcx
  unsigned __int16 **v19; // r9
  __int64 v20; // rax
  unsigned int v21; // eax
  unsigned __int64 v22; // rax
  unsigned int v23; // esi
  unsigned __int16 *v24; // rax
  __int64 v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // ebx
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v30; // [rsp+34h] [rbp-CCh] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v32; // [rsp+40h] [rbp-C0h] BYREF
  struct CProviderEntry *v33; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34; // [rsp+50h] [rbp-B0h] BYREF
  PRTL_RESOURCE Resource; // [rsp+58h] [rbp-A8h] BYREF
  char v36; // [rsp+60h] [rbp-A0h]
  struct _GUID v37; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int8 v38[40]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 v39[112]; // [rsp+A0h] [rbp-60h] BYREF

  v5 = g_pProvRegCache;
  v33 = 0;
  v29 = 0;
  v6 = 0;
  hMem = 0;
  v7 = 0;
  v32 = 0;
  v30 = 100;
  v37 = 0;
  CLogETWBlock::CLogETWBlock(
    (CLogETWBlock *)v38,
    "CProviderRegistrationCache::GetUserNameForCertificate",
    (int *)a3,
    0,
    &v29);
  if ( !a2 || !a3 )
  {
    v29 = 87;
    goto LABEL_42;
  }
  CProviderRegistrationCache::RefreshProvCache(v5);
  NameFromCert = CProviderRegistrationCache::GetNameFromCert(v8, a2, 1, &hMem, &v34);
  v29 = NameFromCert;
  if ( !NameFromCert )
  {
    CAutoRtlLock::CAutoRtlLock(&Resource, (char *)v5 + 16, 0);
    ProvFromCertificate = CProviderRegistrationCache::FindProvFromCertificate(v5, a2, 1, &v33);
    v29 = ProvFromCertificate;
    if ( ProvFromCertificate )
    {
      v15 = 0;
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0sq_EtwEventWriteTransfer(v14, v13, "FindProvFromCertificate", ProvFromCertificate);
      v29 = 0;
    }
    else
    {
      v37 = *(struct _GUID *)((char *)v33 + 8);
      v15 = 1;
    }
    if ( v36 )
      RtlReleaseResource(Resource);
    v6 = (WCHAR *)hMem;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McTemplateU0z_EtwEventWriteTransfer(v14, CertSubjectName, hMem);
    if ( v15 )
    {
      v16 = ConvertIdentityToSid(v6, &v37, v39, &v30);
      v29 = v16;
      if ( v16 )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v18, v17, "ConvertIdentityToSid", v16);
      }
      else
      {
        if ( *((_DWORD *)v5 + 51) )
          v26 = CProviderRegistrationCache::CallLsarLookupSids(v5, v39, &v32, v19);
        else
          v26 = CProviderRegistrationCache::CallADVAPILookupSids(v18, v39, &v32, 0);
        v29 = v26;
        if ( !v26 )
        {
          v7 = v32;
          goto LABEL_27;
        }
        v7 = 0;
      }
    }
    v20 = -1;
    do
      ++v20;
    while ( v6[v20] );
    v21 = v20 + 9;
    if ( v21 < 9 )
      goto LABEL_40;
    if ( v21 + 3 < v21 )
      goto LABEL_40;
    v22 = 2LL * (v21 + 3);
    if ( v22 > 0xFFFFFFFF )
      goto LABEL_40;
    v23 = v22;
    v24 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)v22);
    v7 = v24;
    if ( !v24 )
    {
LABEL_39:
      v29 = 14;
      goto LABEL_42;
    }
    if ( (int)StringCbPrintfW(v24, v23, L"%s\\%s", L"localhost", v6) < 0 )
    {
LABEL_40:
      v29 = 534;
      goto LABEL_42;
    }
LABEL_27:
    if ( !v7 )
    {
      v29 = 1168;
      goto LABEL_42;
    }
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McTemplateU0z_EtwEventWriteTransfer(v25, UserName, v7);
    if ( RtlCreateUnicodeString(a3, v7) )
    {
      v29 = 0;
      goto LABEL_42;
    }
    goto LABEL_39;
  }
  if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
    McTemplateU0sq_EtwEventWriteTransfer(v11, v10, "GetNameFromCert(Subject)", NameFromCert);
  v6 = (WCHAR *)hMem;
LABEL_42:
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  v27 = v29;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v38);
  return v27;
}

```

## disassembly

```asm
0x1800157d4  mov     [rsp-8+arg_0], rbx
0x1800157d9  mov     [rsp-8+arg_18], rsi
0x1800157de  push    rbp
0x1800157df  push    rdi
0x1800157e0  push    r12
0x1800157e2  push    r14
0x1800157e4  push    r15
0x1800157e6  lea     rbp, [rsp-20h]
0x1800157eb  sub     rsp, 120h
0x1800157f2  mov     rax, cs:__security_cookie
0x1800157f9  xor     rax, rsp
0x1800157fc  mov     [rbp+40h+var_30], rax
0x180015800  mov     r15, r8
0x180015803  mov     r14, rdx
0x180015806  mov     rsi, cs:?g_pProvRegCache@@3PEAVCProviderRegistrationCache@@EA; CProviderRegistrationCache * g_pProvRegCache
0x18001580d  xor     r12d, r12d
0x180015810  mov     [rsp+140h+var_F8], r12
0x180015815  mov     [rsp+140h+var_110], r12d
0x18001581a  mov     edi, r12d
0x18001581d  mov     [rsp+140h+hMem], r12
0x180015822  mov     ebx, r12d
0x180015825  mov     [rsp+140h+var_100], rbx
0x18001582a  lea     eax, [r12+64h]
0x18001582f  mov     [rsp+140h+var_10C], ax
0x180015834  xorps   xmm0, xmm0
0x180015837  movups  xmmword ptr [rsp+140h+var_D8.Data1], xmm0
0x18001583c  lea     rax, [rsp+140h+var_110]
0x180015841  mov     [rsp+140h+var_120], rax; unsigned int *
0x180015846  xor     r9d, r9d; int *
0x180015849  lea     rdx, aCproviderregis_8; "CProviderRegistrationCache::GetUserName"...
0x180015850  lea     rcx, [rsp+140h+var_C8]; this
0x180015855  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x18001585a  nop
0x18001585b  test    r14, r14
0x18001585e  jz      loc_180015A94
0x180015864  test    r15, r15
0x180015867  jz      loc_180015A94
0x18001586d  mov     rcx, rsi; this
0x180015870  call    ?RefreshProvCache@CProviderRegistrationCache@@AEAAKXZ; CProviderRegistrationCache::RefreshProvCache(void)
0x180015875  lea     rax, [rsp+140h+var_F0]
0x18001587a  mov     [rsp+140h+var_120], rax; unsigned int *
0x18001587f  lea     r9, [rsp+140h+hMem]; unsigned __int16 **
0x180015884  lea     r8d, [r12+1]; int
0x180015889  mov     rdx, r14; struct _CERT_CONTEXT *
0x18001588c  call    ?GetNameFromCert@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAGPEAK@Z; CProviderRegistrationCache::GetNameFromCert(_CERT_CONTEXT const *,int,ushort * *,ulong *)
0x180015891  mov     [rsp+140h+var_110], eax
0x180015895  test    eax, eax
0x180015897  jz      short loc_1800158BB
0x180015899  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800158a0  jz      short loc_1800158B1
0x1800158a2  mov     r9d, eax
0x1800158a5  lea     r8, aGetnamefromcer_0; "GetNameFromCert(Subject)"
0x1800158ac  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800158b1  mov     rdi, [rsp+140h+hMem]
0x1800158b6  jmp     loc_180015A9C
0x1800158bb  lea     rdx, [rsi+10h]
0x1800158bf  xor     r8d, r8d
0x1800158c2  lea     rcx, [rsp+140h+Resource]
0x1800158c7  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x1800158cc  lea     r9, [rsp+140h+var_F8]; struct CProviderEntry **
0x1800158d1  mov     r8d, 1; int
0x1800158d7  mov     rdx, r14; struct _CERT_CONTEXT *
0x1800158da  mov     rcx, rsi; this
0x1800158dd  call    ?FindProvFromCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAVCProviderEntry@@@Z; CProviderRegistrationCache::FindProvFromCertificate(_CERT_CONTEXT const *,int,CProviderEntry * *)
0x1800158e2  mov     [rsp+140h+var_110], eax
0x1800158e6  test    eax, eax
0x1800158e8  jz      short loc_18001590C
0x1800158ea  mov     r14d, r12d
0x1800158ed  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800158f4  jz      short loc_180015905
0x1800158f6  mov     r9d, eax
0x1800158f9  lea     r8, aFindprovfromce_0; "FindProvFromCertificate"
0x180015900  call    McTemplateU0sq_EtwEventWriteTransfer
0x180015905  mov     [rsp+140h+var_110], r12d
0x18001590a  jmp     short loc_180015921
0x18001590c  mov     rax, [rsp+140h+var_F8]
0x180015911  movups  xmm0, xmmword ptr [rax+8]
0x180015915  movdqu  xmmword ptr [rsp+140h+var_D8.Data1], xmm0
0x18001591b  mov     r14d, 1
0x180015921  cmp     [rsp+140h+var_E0], r12b
0x180015926  jz      short loc_180015933
0x180015928  mov     rcx, [rsp+140h+Resource]; Resource
0x18001592d  call    cs:__imp_RtlReleaseResource
0x180015933  mov     rdi, [rsp+140h+hMem]
0x180015938  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x18001593f  jz      short loc_180015950
0x180015941  mov     r8, rdi
0x180015944  lea     rdx, CertSubjectName
0x18001594b  call    McTemplateU0z_EtwEventWriteTransfer
0x180015950  test    r14d, r14d
0x180015953  jz      short loc_18001598F
0x180015955  lea     r9, [rsp+140h+var_10C]; unsigned __int16 *
0x18001595a  lea     r8, [rbp+40h+var_A0]; unsigned __int8 *
0x18001595e  lea     rdx, [rsp+140h+var_D8]; struct _GUID *
0x180015963  mov     rcx, rdi; unsigned __int16 *
0x180015966  call    ?ConvertIdentityToSid@@YAKPEBGAEBU_GUID@@PEAEPEAG@Z; ConvertIdentityToSid(ushort const *,_GUID const &,uchar *,ushort *)
0x18001596b  mov     [rsp+140h+var_110], eax
0x18001596f  test    eax, eax
0x180015971  jz      loc_180015A3B
0x180015977  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18001597e  jz      short loc_18001598F
0x180015980  mov     r9d, eax
0x180015983  lea     r8, aConvertidentit; "ConvertIdentityToSid"
0x18001598a  call    McTemplateU0sq_EtwEventWriteTransfer
0x18001598f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015993  inc     rax
0x180015996  cmp     [rdi+rax*2], r12w
0x18001599b  jnz     short loc_180015993
0x18001599d  add     eax, 9
0x1800159a0  cmp     eax, 9
0x1800159a3  jb      loc_180015A8A
0x1800159a9  lea     ecx, [rax+3]
0x1800159ac  cmp     ecx, eax
0x1800159ae  jb      loc_180015A8A
0x1800159b4  mov     eax, ecx
0x1800159b6  add     rax, rax
0x1800159b9  mov     ecx, 0FFFFFFFFh
0x1800159be  cmp     rax, rcx
0x1800159c1  ja      loc_180015A8A
0x1800159c7  mov     esi, eax
0x1800159c9  mov     edx, eax; uBytes
0x1800159cb  mov     ecx, 40h ; '@'; uFlags
0x1800159d0  call    cs:__imp_LocalAlloc
0x1800159d6  mov     rbx, rax
0x1800159d9  test    rax, rax
0x1800159dc  jz      loc_180015A80
0x1800159e2  mov     [rsp+140h+var_120], rdi
0x1800159e7  lea     r9, aLocalhost; "localhost"
0x1800159ee  lea     r8, aSS_0; "%s\\%s"
0x1800159f5  mov     edx, esi; unsigned __int64
0x1800159f7  mov     rcx, rax; unsigned __int16 *
0x1800159fa  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800159ff  test    eax, eax
0x180015a01  js      loc_180015A8A
0x180015a07  test    rbx, rbx
0x180015a0a  jz      short loc_180015A76
0x180015a0c  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x180015a13  jz      short loc_180015A24
0x180015a15  mov     r8, rbx
0x180015a18  lea     rdx, UserName
0x180015a1f  call    McTemplateU0z_EtwEventWriteTransfer
0x180015a24  mov     rdx, rbx; SourceString
0x180015a27  mov     rcx, r15; DestinationString
0x180015a2a  call    cs:__imp_RtlCreateUnicodeString
0x180015a30  test    al, al
0x180015a32  jz      short loc_180015A80
0x180015a34  mov     [rsp+140h+var_110], r12d
0x180015a39  jmp     short loc_180015A9C
0x180015a3b  lea     r8, [rsp+140h+var_100]; unsigned __int16 **
0x180015a40  lea     rdx, [rbp+40h+var_A0]; void *
0x180015a44  cmp     [rsi+0CCh], r12d
0x180015a4b  jz      short loc_180015A57
0x180015a4d  mov     rcx, rsi; this
0x180015a50  call    ?CallLsarLookupSids@CProviderRegistrationCache@@AEAAKPEAXPEAPEAG1@Z; CProviderRegistrationCache::CallLsarLookupSids(void *,ushort * *,ushort * *)
0x180015a55  jmp     short loc_180015A5F
0x180015a57  xor     r9d, r9d; unsigned __int16 **
0x180015a5a  call    ?CallADVAPILookupSids@CProviderRegistrationCache@@AEAAKPEAXPEAPEAG1@Z; CProviderRegistrationCache::CallADVAPILookupSids(void *,ushort * *,ushort * *)
0x180015a5f  mov     [rsp+140h+var_110], eax
0x180015a63  test    eax, eax
0x180015a65  jz      short loc_180015A6F
0x180015a67  mov     rbx, r12
0x180015a6a  jmp     loc_18001598F
0x180015a6f  mov     rbx, [rsp+140h+var_100]
0x180015a74  jmp     short loc_180015A07
0x180015a76  mov     [rsp+140h+var_110], 490h
0x180015a7e  jmp     short loc_180015A9C
0x180015a80  mov     [rsp+140h+var_110], 0Eh
0x180015a88  jmp     short loc_180015A9C
0x180015a8a  mov     [rsp+140h+var_110], 216h
0x180015a92  jmp     short loc_180015A9C
0x180015a94  mov     [rsp+140h+var_110], 57h ; 'W'
0x180015a9c  test    rdi, rdi
0x180015a9f  jz      short loc_180015AAA
0x180015aa1  mov     rcx, rdi; hMem
0x180015aa4  call    cs:__imp_LocalFree
0x180015aaa  test    rbx, rbx
0x180015aad  jz      short loc_180015AB8
0x180015aaf  mov     rcx, rbx; hMem
0x180015ab2  call    cs:__imp_LocalFree
0x180015ab8  mov     ebx, [rsp+140h+var_110]
0x180015abc  lea     rcx, [rsp+140h+var_C8]; this
0x180015ac1  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180015ac6  mov     eax, ebx
0x180015ac8  mov     rcx, [rbp+40h+var_30]
0x180015acc  xor     rcx, rsp; StackCookie
0x180015acf  call    __security_check_cookie
0x180015ad4  lea     r11, [rsp+140h+var_20]
0x180015adc  mov     rbx, [r11+30h]
0x180015ae0  mov     rsi, [r11+48h]
0x180015ae4  mov     rsp, r11
0x180015ae7  pop     r15
0x180015ae9  pop     r14
0x180015aeb  pop     r12
0x180015aed  pop     rdi
0x180015aee  pop     rbp
0x180015aef  retn
```
