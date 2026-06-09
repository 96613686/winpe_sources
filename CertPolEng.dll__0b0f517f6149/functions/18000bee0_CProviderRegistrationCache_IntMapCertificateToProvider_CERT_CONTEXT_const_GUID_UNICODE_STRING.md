# CProviderRegistrationCache::IntMapCertificateToProvider(_CERT_CONTEXT const *,_GUID *,_UNICODE_STRING *)

- ea: `0x18000bee0`
- end: `0x18000c061`
- name: `?IntMapCertificateToProvider@CProviderRegistrationCache@@QEAAJPEBU_CERT_CONTEXT@@PEAU_GUID@@PEAU_UNICODE_STRING@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *__hidden this, const struct _CERT_CONTEXT *, struct _GUID *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005a90`

## callees

- `0x180003dc0`
- `0x180007b70`
- `0x180007d20`
- `0x180009510`
- `0x18000bee0`
- `0x18000c344`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x18000bfd2`
- `ntdll!RtlReleaseResource` at `0x18000c028`
- `ntdll!RtlReleaseResource` at `0x18000bfd2`
- `ntdll!RtlReleaseResource` at `0x18000c028`
- `ntdll!RtlCreateUnicodeString` at `0x18000bff5`
- `ntdll!RtlCreateUnicodeString` at `0x18000bff5`

## string_xrefs

- `0x18000bf0a`: `CProviderRegistrationCache::IntMapCertificateToProvider`
- `0x18000c015`: `RtlCreateUnicodeString`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::IntMapCertificateToProvider(
        CProviderRegistrationCache *this,
        const struct _CERT_CONTEXT *a2,
        struct _GUID *a3,
        struct _UNICODE_STRING *a4)
{
  int ProvFromCertificate; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r9
  const char *v12; // r8
  struct CProviderEntry *v13; // rdx
  unsigned int v14; // ebx
  struct CProviderEntry *v16; // [rsp+20h] [rbp-40h] BYREF
  PRTL_RESOURCE Resource; // [rsp+28h] [rbp-38h] BYREF
  char v18; // [rsp+30h] [rbp-30h]
  _QWORD v19[5]; // [rsp+38h] [rbp-28h] BYREF
  int v20; // [rsp+88h] [rbp+28h] BYREF

  v20 = 0;
  v16 = 0;
  v19[0] = "CProviderRegistrationCache::IntMapCertificateToProvider";
  v19[1] = 0;
  v19[2] = &v20;
  v19[3] = 0;
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0s_EtwEventWriteTransfer(this, Func_Start, "CProviderRegistrationCache::IntMapCertificateToProvider");
  if ( !a2 || !a3 )
  {
    v20 = -1073741811;
    goto LABEL_25;
  }
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( !*((_DWORD *)this + 2) )
  {
    v20 = -1073283051;
    goto LABEL_25;
  }
  CAutoRtlLock::CAutoRtlLock(&Resource, (char *)this + 16, 0);
  ProvFromCertificate = CProviderRegistrationCache::FindProvFromCertificate(this, a2, 1, &v16);
  if ( ProvFromCertificate )
  {
    if ( ProvFromCertificate > 0 )
      ProvFromCertificate = (unsigned __int16)ProvFromCertificate | 0xC0070000;
    v20 = ProvFromCertificate;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
      goto LABEL_15;
    v11 = (unsigned int)ProvFromCertificate;
    v12 = "FindProvFromCertificate";
    goto LABEL_14;
  }
  v13 = v16;
  *a3 = *(struct _GUID *)((char *)v16 + 8);
  if ( a4 && !RtlCreateUnicodeString(a4, (PCWSTR)v13 + 792) )
  {
    v20 = -1073741801;
    if ( (Microsoft_Windows_CertPolEngEnableBits & 2) == 0 )
    {
LABEL_15:
      if ( v18 )
        RtlReleaseResource(Resource);
      goto LABEL_25;
    }
    v11 = 3221225495LL;
    v12 = "RtlCreateUnicodeString";
LABEL_14:
    McTemplateU0sq_EtwEventWriteTransfer(v10, v9, v12, v11);
    goto LABEL_15;
  }
  if ( v18 )
    RtlReleaseResource(Resource);
  v20 = 0;
LABEL_25:
  v14 = v20;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v19);
  return v14;
}

```

## disassembly

```asm
0x18000bee0  mov     [rsp-18h+arg_0], rbx
0x18000bee5  mov     [rsp-18h+arg_10], rsi
0x18000beea  push    rbp
0x18000beeb  push    rdi
0x18000beec  push    r14
0x18000beee  mov     rbp, rsp
0x18000bef1  sub     rsp, 60h
0x18000bef5  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 1
0x18000befc  lea     rax, [rbp+arg_8]
0x18000bf00  mov     rdi, r8
0x18000bf03  mov     [rbp+arg_8], 0
0x18000bf0a  lea     r8, aCproviderregis_19; "CProviderRegistrationCache::IntMapCerti"...
0x18000bf11  mov     [rbp+var_40], 0
0x18000bf19  mov     [rbp+var_28], r8
0x18000bf1d  mov     rbx, r9
0x18000bf20  mov     r14, rdx
0x18000bf23  mov     [rbp+var_20], 0
0x18000bf2b  mov     rsi, rcx
0x18000bf2e  mov     [rbp+var_18], rax
0x18000bf32  mov     [rbp+var_10], 0
0x18000bf3a  jz      short loc_18000BF48
0x18000bf3c  lea     rdx, Func_Start
0x18000bf43  call    McTemplateU0s_EtwEventWriteTransfer
0x18000bf48  test    r14, r14
0x18000bf4b  jz      loc_18000C037
0x18000bf51  test    rdi, rdi
0x18000bf54  jz      loc_18000C037
0x18000bf5a  xorps   xmm0, xmm0
0x18000bf5d  movups  xmmword ptr [rdi], xmm0
0x18000bf60  test    rbx, rbx
0x18000bf63  jz      short loc_18000BF68
0x18000bf65  movups  xmmword ptr [rbx], xmm0
0x18000bf68  cmp     dword ptr [rsi+8], 0
0x18000bf6c  jnz     short loc_18000BF7A
0x18000bf6e  mov     [rbp+arg_8], 0C0070015h
0x18000bf75  jmp     loc_18000C03E
0x18000bf7a  lea     rdx, [rsi+10h]
0x18000bf7e  xor     r8d, r8d
0x18000bf81  lea     rcx, [rbp+Resource]
0x18000bf85  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x18000bf8a  lea     r9, [rbp+var_40]; struct CProviderEntry **
0x18000bf8e  mov     r8d, 1; int
0x18000bf94  mov     rdx, r14; struct _CERT_CONTEXT *
0x18000bf97  mov     rcx, rsi; this
0x18000bf9a  call    ?FindProvFromCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAVCProviderEntry@@@Z; CProviderRegistrationCache::FindProvFromCertificate(_CERT_CONTEXT const *,int,CProviderEntry * *)
0x18000bf9f  test    eax, eax
0x18000bfa1  jz      short loc_18000BFDA
0x18000bfa3  jle     short loc_18000BFAD
0x18000bfa5  movzx   eax, ax
0x18000bfa8  or      eax, 0C0070000h
0x18000bfad  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000bfb4  mov     [rbp+arg_8], eax
0x18000bfb7  jz      short loc_18000BFC8
0x18000bfb9  mov     r9d, eax
0x18000bfbc  lea     r8, aFindprovfromce_0; "FindProvFromCertificate"
0x18000bfc3  call    McTemplateU0sq_EtwEventWriteTransfer
0x18000bfc8  cmp     [rbp+var_30], 0
0x18000bfcc  jz      short loc_18000C03E
0x18000bfce  mov     rcx, [rbp+Resource]; Resource
0x18000bfd2  call    cs:__imp_RtlReleaseResource
0x18000bfd8  jmp     short loc_18000C03E
0x18000bfda  mov     rdx, [rbp+var_40]
0x18000bfde  movups  xmm0, xmmword ptr [rdx+8]
0x18000bfe2  movdqu  xmmword ptr [rdi], xmm0
0x18000bfe6  test    rbx, rbx
0x18000bfe9  jz      short loc_18000C01E
0x18000bfeb  add     rdx, 630h; SourceString
0x18000bff2  mov     rcx, rbx; DestinationString
0x18000bff5  call    cs:__imp_RtlCreateUnicodeString
0x18000bffb  test    al, al
0x18000bffd  jnz     short loc_18000C01E
0x18000bfff  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x18000c006  mov     [rbp+arg_8], 0C0000017h
0x18000c00d  jz      short loc_18000BFC8
0x18000c00f  mov     r9d, 0C0000017h
0x18000c015  lea     r8, aRtlcreateunico; "RtlCreateUnicodeString"
0x18000c01c  jmp     short loc_18000BFC3
0x18000c01e  cmp     [rbp+var_30], 0
0x18000c022  jz      short loc_18000C02E
0x18000c024  mov     rcx, [rbp+Resource]; Resource
0x18000c028  call    cs:__imp_RtlReleaseResource
0x18000c02e  mov     [rbp+arg_8], 0
0x18000c035  jmp     short loc_18000C03E
0x18000c037  mov     [rbp+arg_8], 0C000000Dh
0x18000c03e  mov     ebx, [rbp+arg_8]
0x18000c041  lea     rcx, [rbp+var_28]; this
0x18000c045  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x18000c04a  lea     r11, [rsp+60h+var_s0]
0x18000c04f  mov     eax, ebx
0x18000c051  mov     rbx, [r11+20h]
0x18000c055  mov     rsi, [r11+30h]
0x18000c059  mov     rsp, r11
0x18000c05c  pop     r14
0x18000c05e  pop     rdi
0x18000c05f  pop     rbp
0x18000c060  retn
```
