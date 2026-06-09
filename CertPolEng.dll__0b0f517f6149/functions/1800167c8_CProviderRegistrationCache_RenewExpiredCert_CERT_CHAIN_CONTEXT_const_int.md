# CProviderRegistrationCache::RenewExpiredCert(_CERT_CHAIN_CONTEXT const *,int *)

- ea: `0x1800167c8`
- end: `0x180016b08`
- name: `?RenewExpiredCert@CProviderRegistrationCache@@AEAAJPEBU_CERT_CHAIN_CONTEXT@@PEAH@Z`
- size: `832`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *__hidden this, const struct _CERT_CHAIN_CONTEXT *, int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000caa0`

## callees

- `0x180003dc0`
- `0x180007b70`
- `0x180007c90`
- `0x180007da0`
- `0x180007ea0`
- `0x180009510`
- `0x18000c2d0`
- `0x18000c344`
- `0x18000c864`
- `0x180013404`
- `0x180015bc4`
- `0x1800167c8`
- `0x180016ec0`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800169de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800169de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016a3d`
- `ntdll!WinSqmAddToStream` at `0x180016aaa`
- `ntdll!WinSqmAddToStream` at `0x180016aaa`
- `ntdll!WinSqmIsOptedIn` at `0x180016a51`
- `ntdll!WinSqmIsOptedIn` at `0x180016a51`
- `ntdll!RtlReleaseResource` at `0x180016905`
- `ntdll!RtlReleaseResource` at `0x180016905`

## string_xrefs

- `0x1800169a1`: `CProviderRegistrationCache::CallProvidersLRPCCertRenewalInterface`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::RenewExpiredCert(
        CProviderRegistrationCache *this,
        const struct _CERT_CHAIN_CONTEXT *a2,
        int *a3)
{
  unsigned int v6; // esi
  PCERT_SIMPLE_CHAIN v7; // rax
  const struct _CERT_CONTEXT *pCertContext; // r15
  unsigned int ProvFromCertificate; // eax
  __int64 v10; // rcx
  int *v11; // r8
  struct CProviderEntry *v12; // rbx
  unsigned __int64 v13; // r11
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  struct CProviderEntry *v18; // rdi
  __int64 v19; // rax
  struct CProviderEntry *v20; // rax
  unsigned int v21; // ebx
  struct CProviderEntry *v22; // rdx
  unsigned int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned __int16 *v26; // rax
  unsigned int v28; // [rsp+30h] [rbp-D0h] BYREF
  struct CProviderEntry *v29; // [rsp+38h] [rbp-C8h] BYREF
  PRTL_RESOURCE Resource; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v31; // [rsp+48h] [rbp-B8h]
  __int64 v32; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v33[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v34[264]; // [rsp+270h] [rbp+170h] BYREF

  v29 = 0;
  v33[0] = 0;
  v6 = 0;
  if ( (a2->TrustStatus.dwErrorStatus & 1) != 0 )
  {
    if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        (_DWORD)this,
        (unsigned int)ExpiredCertFound,
        (_DWORD)a3,
        1,
        (__int64)&Resource);
    *a3 = 1;
    if ( a2->cChain )
    {
      v7 = *a2->rgpChain;
      if ( v7->cElement )
      {
        pCertContext = (*v7->rgpElement)->pCertContext;
        CAutoRtlLock::CAutoRtlLock(&Resource, (char *)this + 16, 0);
        ProvFromCertificate = CProviderRegistrationCache::FindProvFromCertificate(this, pCertContext, 1, &v29);
        v12 = v29;
        if ( ProvFromCertificate )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
            McTemplateU0q_EtwEventWriteTransfer(v10, ProvNotFound, ProvFromCertificate);
        }
        else
        {
          if ( (int)StringCchCopyW(v33, 0x104u, (const unsigned __int16 *)v29 + 272) < 0 )
            v33[0] = 0;
          if ( (int)StringCchCopyW(v34, v13, (const unsigned __int16 *)v12 + 532) < 0 )
            v34[0] = 0;
        }
        if ( (_BYTE)v31 )
          RtlReleaseResource(Resource);
        if ( v12 )
        {
          v14 = 0x49B0E3FCD7F9888FLL - *((_QWORD *)v12 + 1);
          if ( *((_QWORD *)v12 + 1) == 0x49B0E3FCD7F9888FLL )
            v14 = 0x4F2A395F5BA8A69ELL - *((_QWORD *)v12 + 2);
          if ( !v14 )
          {
            v15 = CProviderRegistrationCache::RenewCertificate(this, (const struct _GUID *)((char *)v12 + 8), 1);
            v6 = v15;
            if ( v15 < 0 )
            {
              if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
                McTemplateU0sq_EtwEventWriteTransfer(v17, v16, "RenewCertificate", (unsigned int)v15);
              return 0;
            }
            else
            {
              *a3 = 1;
            }
            return v6;
          }
        }
        if ( !v33[0] )
          return v6;
        if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
          McTemplateU0z_EtwEventWriteTransfer(v10, CallingLRPC, v33);
        v28 = 0;
        v29 = 0;
        v18 = 0;
        CLogETWBlock::CLogETWBlock(
          (CLogETWBlock *)&Resource,
          "CProviderRegistrationCache::CallProvidersLRPCCertRenewalInterface",
          v11,
          0,
          &v28);
        v19 = -1;
        do
          ++v19;
        while ( v33[v19] );
        if ( !v19 )
        {
          v21 = 87;
          goto LABEL_38;
        }
        if ( pCertContext )
        {
          v23 = IntBlobToHexString(&pCertContext->pCertInfo->SerialNumber, (unsigned __int16 **)&v29);
          v18 = v29;
          v21 = v23;
          v28 = v23;
          if ( v23 )
            goto LABEL_39;
          v22 = v29;
        }
        else
        {
          v20 = (struct CProviderEntry *)LocalAlloc(0x40u, 2u);
          v18 = v20;
          if ( !v20 )
          {
            v21 = 14;
LABEL_38:
            v28 = v21;
            goto LABEL_39;
          }
          v22 = v20;
        }
        v21 = PKU2URenewCertificate(v33, (const unsigned __int16 *)v22);
        v28 = v21;
LABEL_39:
        if ( v18 )
        {
          LocalFree(v18);
          v21 = v28;
        }
        CLogETWBlock::~CLogETWBlock((CLogETWBlock *)&Resource);
        if ( (unsigned int)WinSqmIsOptedIn() )
        {
          LODWORD(Resource) = 2;
          v32 = v21;
          v31 = 0;
          v26 = v34;
          DWORD2(v31) = 1;
          if ( !v34[0] )
            v26 = L"(null)";
          *(_QWORD *)&v31 = v26;
          WinSqmAddToStream(0, 4609, 2, &Resource);
        }
        if ( v21 )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
            McTemplateU0sq_EtwEventWriteTransfer(v25, v24, "CallProvidersLRPCCertRenewalInterface", v21);
          if ( v21 == -2147024810 )
          {
            v6 = -1073741718;
            *a3 = 0;
          }
        }
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800167c8  mov     [rsp-8+arg_18], rbx
0x1800167cd  push    rbp
0x1800167ce  push    rsi
0x1800167cf  push    rdi
0x1800167d0  push    r12
0x1800167d2  push    r13
0x1800167d4  push    r14
0x1800167d6  push    r15
0x1800167d8  lea     rbp, [rsp-390h]
0x1800167e0  sub     rsp, 490h
0x1800167e7  mov     rax, cs:__security_cookie
0x1800167ee  xor     rax, rsp
0x1800167f1  mov     [rbp+3C0h+var_40], rax
0x1800167f8  xor     r12d, r12d
0x1800167fb  mov     r14, r8
0x1800167fe  mov     rbx, rdx
0x180016801  mov     [rsp+4C0h+var_488], r12
0x180016806  mov     rdi, rcx
0x180016809  mov     [rsp+4C0h+var_460], r12w
0x18001680f  mov     esi, r12d
0x180016812  lea     r13d, [r12+1]
0x180016817  test    [rdx+4], r13b
0x18001681b  jz      loc_180016ADC
0x180016821  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r13b
0x180016828  jz      short loc_180016843
0x18001682a  lea     rax, [rsp+4C0h+Resource]
0x18001682f  mov     r9d, r13d
0x180016832  lea     rdx, ExpiredCertFound
0x180016839  mov     [rsp+4C0h+var_4A0], rax
0x18001683e  call    McGenEventWrite_EtwEventWriteTransfer
0x180016843  mov     [r14], r13d
0x180016846  cmp     [rbx+0Ch], r12d
0x18001684a  jbe     loc_180016ADC
0x180016850  mov     rax, [rbx+10h]
0x180016854  mov     rax, [rax]
0x180016857  cmp     [rax+0Ch], r12d
0x18001685b  jbe     loc_180016ADC
0x180016861  mov     rax, [rax+10h]
0x180016865  lea     rdx, [rdi+10h]
0x180016869  xor     r8d, r8d
0x18001686c  mov     rcx, [rax]
0x18001686f  mov     r15, [rcx+8]
0x180016873  lea     rcx, [rsp+4C0h+Resource]
0x180016878  call    ??0CAutoRtlLock@@QEAA@PEAU_RTL_RESOURCE@@W4eRTLLockMode@@@Z; CAutoRtlLock::CAutoRtlLock(_RTL_RESOURCE *,eRTLLockMode)
0x18001687d  lea     r9, [rsp+4C0h+var_488]; struct CProviderEntry **
0x180016882  mov     r8d, r13d; int
0x180016885  mov     rdx, r15; struct _CERT_CONTEXT *
0x180016888  mov     rcx, rdi; this
0x18001688b  call    ?FindProvFromCertificate@CProviderRegistrationCache@@QEAAKPEBU_CERT_CONTEXT@@HPEAPEAVCProviderEntry@@@Z; CProviderRegistrationCache::FindProvFromCertificate(_CERT_CONTEXT const *,int,CProviderEntry * *)
0x180016890  mov     rbx, [rsp+4C0h+var_488]
0x180016895  test    eax, eax
0x180016897  jnz     short loc_1800168E1
0x180016899  mov     r11d, 104h
0x18001689f  lea     r8, [rbx+220h]; unsigned __int16 *
0x1800168a6  mov     edx, r11d; unsigned __int64
0x1800168a9  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800168ae  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800168b3  test    eax, eax
0x1800168b5  jns     short loc_1800168BD
0x1800168b7  mov     [rsp+4C0h+var_460], r12w
0x1800168bd  lea     r8, [rbx+428h]; unsigned __int16 *
0x1800168c4  mov     rdx, r11; unsigned __int64
0x1800168c7  lea     rcx, [rbp+3C0h+var_250]; unsigned __int16 *
0x1800168ce  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800168d3  test    eax, eax
0x1800168d5  jns     short loc_1800168F9
0x1800168d7  mov     [rbp+3C0h+var_250], r12w
0x1800168df  jmp     short loc_1800168F9
0x1800168e1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r13b
0x1800168e8  jz      short loc_1800168F9
0x1800168ea  mov     r8d, eax
0x1800168ed  lea     rdx, ProvNotFound
0x1800168f4  call    McTemplateU0q_EtwEventWriteTransfer
0x1800168f9  cmp     byte ptr [rsp+4C0h+var_478], r12b
0x1800168fe  jz      short loc_18001690B
0x180016900  mov     rcx, [rsp+4C0h+Resource]; Resource
0x180016905  call    cs:__imp_RtlReleaseResource
0x18001690b  test    rbx, rbx
0x18001690e  jz      short loc_180016969
0x180016910  mov     rax, cs:qword_180020CB0
0x180016917  lea     rdx, [rbx+8]; struct _GUID *
0x18001691b  sub     rax, [rdx]
0x18001691e  jnz     short loc_18001692B
0x180016920  mov     rax, cs:qword_180020CB8
0x180016927  sub     rax, [rdx+8]
0x18001692b  test    rax, rax
0x18001692e  jnz     short loc_180016969
0x180016930  mov     r8d, r13d; int
0x180016933  mov     rcx, rdi; this
0x180016936  call    ?RenewCertificate@CProviderRegistrationCache@@QEAAJPEBU_GUID@@H@Z; CProviderRegistrationCache::RenewCertificate(_GUID const *,int)
0x18001693b  mov     esi, eax
0x18001693d  test    eax, eax
0x18001693f  js      short loc_180016949
0x180016941  mov     [r14], r13d
0x180016944  jmp     loc_180016ADC
0x180016949  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016950  jz      short loc_180016961
0x180016952  mov     r9d, eax
0x180016955  lea     r8, aRenewcertifica; "RenewCertificate"
0x18001695c  call    McTemplateU0sq_EtwEventWriteTransfer
0x180016961  mov     esi, r12d
0x180016964  jmp     loc_180016ADC
0x180016969  cmp     [rsp+4C0h+var_460], r12w
0x18001696f  jz      loc_180016ADC
0x180016975  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r13b
0x18001697c  jz      short loc_18001698F
0x18001697e  lea     r8, [rsp+4C0h+var_460]
0x180016983  lea     rdx, CallingLRPC
0x18001698a  call    McTemplateU0z_EtwEventWriteTransfer
0x18001698f  lea     rax, [rsp+4C0h+var_490]
0x180016994  mov     [rsp+4C0h+var_490], r12d
0x180016999  xor     r9d, r9d; int *
0x18001699c  mov     [rsp+4C0h+var_4A0], rax; unsigned int *
0x1800169a1  lea     rdx, aCproviderregis_9; "CProviderRegistrationCache::CallProvide"...
0x1800169a8  mov     [rsp+4C0h+var_488], r12
0x1800169ad  lea     rcx, [rsp+4C0h+Resource]; this
0x1800169b2  mov     rdi, r12
0x1800169b5  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x1800169ba  lea     rcx, [rsp+4C0h+var_460]
0x1800169bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800169c3  inc     rax
0x1800169c6  cmp     [rcx+rax*2], r12w
0x1800169cb  jnz     short loc_1800169C3
0x1800169cd  test    rax, rax
0x1800169d0  jz      short loc_180016A2C
0x1800169d2  test    r15, r15
0x1800169d5  jnz     short loc_180016A06
0x1800169d7  lea     edx, [r15+2]; uBytes
0x1800169db  lea     ecx, [rdx+3Eh]; uFlags
0x1800169de  call    cs:__imp_LocalAlloc
0x1800169e4  mov     rdi, rax
0x1800169e7  test    rax, rax
0x1800169ea  jnz     short loc_1800169F1
0x1800169ec  lea     ebx, [rax+0Eh]
0x1800169ef  jmp     short loc_180016A31
0x1800169f1  mov     rdx, rax; unsigned __int16 *
0x1800169f4  lea     rcx, [rsp+4C0h+var_460]; unsigned __int16 *
0x1800169f9  call    ?PKU2URenewCertificate@@YAKPEAGPEBG@Z; PKU2URenewCertificate(ushort *,ushort const *)
0x1800169fe  mov     ebx, eax
0x180016a00  mov     [rsp+4C0h+var_490], eax
0x180016a04  jmp     short loc_180016A35
0x180016a06  mov     rcx, [r15+18h]
0x180016a0a  lea     rdx, [rsp+4C0h+var_488]; unsigned __int16 **
0x180016a0f  add     rcx, 8; struct _CRYPTOAPI_BLOB *
0x180016a13  call    ?IntBlobToHexString@@YAKPEAU_CRYPTOAPI_BLOB@@PEAPEAG@Z; IntBlobToHexString(_CRYPTOAPI_BLOB *,ushort * *)
0x180016a18  mov     rdi, [rsp+4C0h+var_488]
0x180016a1d  mov     ebx, eax
0x180016a1f  mov     [rsp+4C0h+var_490], eax
0x180016a23  test    eax, eax
0x180016a25  jnz     short loc_180016A35
0x180016a27  mov     rdx, rdi
0x180016a2a  jmp     short loc_1800169F4
0x180016a2c  mov     ebx, 57h ; 'W'
0x180016a31  mov     [rsp+4C0h+var_490], ebx
0x180016a35  test    rdi, rdi
0x180016a38  jz      short loc_180016A47
0x180016a3a  mov     rcx, rdi; hMem
0x180016a3d  call    cs:__imp_LocalFree
0x180016a43  mov     ebx, [rsp+4C0h+var_490]
0x180016a47  lea     rcx, [rsp+4C0h+Resource]; this
0x180016a4c  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180016a51  call    cs:__imp_WinSqmIsOptedIn
0x180016a57  test    eax, eax
0x180016a59  jz      short loc_180016AB0
0x180016a5b  xor     eax, eax
0x180016a5d  mov     dword ptr [rsp+4C0h+Resource], 2
0x180016a65  cmp     [rbp+3C0h+var_250], r12w
0x180016a6d  lea     rcx, aNull_0; "(null)"
0x180016a74  mov     [rsp+4C0h+var_468], rax
0x180016a79  lea     r9, [rsp+4C0h+Resource]
0x180016a7e  xorps   xmm0, xmm0
0x180016a81  mov     dword ptr [rsp+4C0h+var_468], ebx
0x180016a85  movups  [rsp+4C0h+var_478], xmm0
0x180016a8a  lea     rax, [rbp+3C0h+var_250]
0x180016a91  mov     dword ptr [rsp+4C0h+var_478+8], r13d
0x180016a96  cmovz   rax, rcx
0x180016a9a  mov     edx, 1201h
0x180016a9f  xor     ecx, ecx
0x180016aa1  mov     qword ptr [rsp+4C0h+var_478], rax
0x180016aa6  lea     r8d, [rcx+2]
0x180016aaa  call    cs:__imp_WinSqmAddToStream
0x180016ab0  test    ebx, ebx
0x180016ab2  jz      short loc_180016ADC
0x180016ab4  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016abb  jz      short loc_180016ACC
0x180016abd  mov     r9d, ebx
0x180016ac0  lea     r8, aCallprovidersl; "CallProvidersLRPCCertRenewalInterface"
0x180016ac7  call    McTemplateU0sq_EtwEventWriteTransfer
0x180016acc  cmp     ebx, 80070056h
0x180016ad2  jnz     short loc_180016ADC
0x180016ad4  mov     esi, 0C000006Ah
0x180016ad9  mov     [r14], r12d
0x180016adc  mov     eax, esi
0x180016ade  mov     rcx, [rbp+3C0h+var_40]
0x180016ae5  xor     rcx, rsp; StackCookie
0x180016ae8  call    __security_check_cookie
0x180016aed  mov     rbx, [rsp+4C0h+arg_18]
0x180016af5  add     rsp, 490h
0x180016afc  pop     r15
0x180016afe  pop     r14
0x180016b00  pop     r13
0x180016b02  pop     r12
0x180016b04  pop     rdi
0x180016b05  pop     rsi
0x180016b06  pop     rbp
0x180016b07  retn
```
