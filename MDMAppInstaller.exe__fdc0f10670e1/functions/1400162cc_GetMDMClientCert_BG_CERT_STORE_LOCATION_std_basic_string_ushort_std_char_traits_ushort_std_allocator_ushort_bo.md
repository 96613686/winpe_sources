# GetMDMClientCert(BG_CERT_STORE_LOCATION &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool &,_GUID &,ushort * *)

- ea: `0x1400162cc`
- end: `0x1400165f1`
- name: `?GetMDMClientCert@@YAJAEAW4BG_CERT_STORE_LOCATION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAU_GUID@@PEAPEAG@Z`
- size: `805`
- prototype: `__int64 __fastcall(_DWORD *, _QWORD *, _BYTE *, void *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010a2c`

## callees

- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x1400074d4`
- `0x14000775c`
- `0x14000904c`
- `0x1400162cc`
- `0x1400180b4`
- `0x14001a8d0`
- `0x14001c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1400164b4`
- `msvcrt!memcpy_s` at `0x1400164b4`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1400164d9`
- `dmEnrollEngine!GetEnrollmentSID` at `0x1400164d9`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x140016497`
- `dmEnrollEngine!__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z` at `0x140016497`
- `dmEnrollEngine!__imp_GetEnrollmentsOfTypes` at `0x140016377`
- `dmEnrollEngine!__imp_GetEnrollmentsOfTypes` at `0x140016377`
- `CRYPT32!CertFreeCertificateContext` at `0x1400163ee`
- `CRYPT32!CertFreeCertificateContext` at `0x140016583`
- `CRYPT32!CertFreeCertificateContext` at `0x1400163ee`
- `CRYPT32!CertFreeCertificateContext` at `0x140016583`
- `CRYPT32!CertCloseStore` at `0x1400163d7`
- `CRYPT32!CertCloseStore` at `0x14001659c`
- `CRYPT32!CertCloseStore` at `0x1400163d7`
- `CRYPT32!CertCloseStore` at `0x14001659c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400163be`
- `OLEAUT32!__imp_SysFreeString` at `0x14001656c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400163be`
- `OLEAUT32!__imp_SysFreeString` at `0x14001656c`

## string_xrefs

- `0x1400164e7`: `Failed to get enrollment User SID : 0x%1!x!`

## pseudocode

```c
__int64 __fastcall GetMDMClientCert(_DWORD *a1, _QWORD *a2, _BYTE *a3, void *a4, __int64 a5)
{
  _QWORD *v7; // rbx
  int v9; // edi
  _WORD *v10; // rcx
  _QWORD *v11; // r15
  _WORD *v12; // rcx
  int EnrollmentsOfTypes; // eax
  int v14; // eax
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  _QWORD *v17; // rdx
  unsigned int v18; // edx
  int EnrollmentSID; // eax
  unsigned int v21; // [rsp+20h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-49h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+30h] [rbp-41h] BYREF
  HCERTSTORE hCertStore; // [rsp+38h] [rbp-39h] BYREF
  __int64 v25; // [rsp+40h] [rbp-31h] BYREF
  __int64 v26; // [rsp+48h] [rbp-29h] BYREF
  struct _GUID v27; // [rsp+50h] [rbp-21h] BYREF
  struct _GUID Source; // [rsp+60h] [rbp-11h] BYREF

  v7 = a2;
  v9 = 0;
  pCertContext = 0;
  v26 = 0;
  v25 = 0;
  v21 = 0;
  Source = 0;
  hCertStore = 0;
  bstrString = 0;
  if ( !a5 )
  {
    v9 = -2147024809;
LABEL_45:
    LogError(L"Failed to retrieve client cert store and thumbprint : 0x%1!x!", (unsigned int)v9);
    goto LABEL_46;
  }
  *a1 = 1;
  if ( a2[3] < 8u )
    v10 = a2;
  else
    v10 = (_WORD *)*a2;
  v11 = a2 + 2;
  *v10 = 0;
  *a3 = 0;
  if ( a2[3] < 8u )
    v12 = a2;
  else
    v12 = (_WORD *)*a2;
  *v11 = 0;
  *v12 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_AppCertFix>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_MMPC_AppCertFix>::GetImpl'::`2'::impl,
    a2);
  EnrollmentsOfTypes = GetEnrollmentsOfTypes(8289, &v26);
  if ( EnrollmentsOfTypes >= 0 )
  {
    do
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( (*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v26 + 24LL))(v26, &v25) )
          {
            LogError(L"An enrollment client context was not found.  Falling back to default Local Machine store.");
            *a1 = 1;
            if ( v7[3] >= 8u )
              v7 = (_QWORD *)*v7;
            *v11 = 0;
            *(_WORD *)v7 = 0;
            *a3 = 0;
            goto LABEL_36;
          }
          if ( bstrString )
          {
            SysFreeString(bstrString);
            bstrString = 0;
          }
          if ( hCertStore )
          {
            CertCloseStore(hCertStore, 0);
            hCertStore = 0;
          }
          if ( pCertContext )
          {
            CertFreeCertificateContext(pCertContext);
            pCertContext = 0;
          }
          v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 80LL))(v25, &bstrString);
          if ( v14 >= 0 )
            break;
          LogWarn(L"get_ClientCertThumb Failed with error code 0x%1!x!.", (unsigned int)v14);
        }
        v15 = std::char_traits<unsigned short>::length(bstrString);
        std::wstring::assign(v7, v16, v15);
        v17 = v7[3] < 8u ? v7 : (_QWORD *)*v7;
        LogInfo(L"Found MDM certificate %1.", v17);
        if ( (*(int (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v25 + 24LL))(v25, &Source) >= 0 )
          break;
        LogWarn(L"Failed to find EnrollmentKey");
      }
      v21 = 0;
      *a3 = 0;
      v27 = Source;
    }
    while ( (int)GetEnrollmentClientContext(&v27, &v21, &hCertStore, &pCertContext) < 0 );
    memcpy_s(a4, 0x10u, &Source, 0x10u);
    v18 = v21;
    if ( v21 == 393216 )
    {
      *a3 = 1;
      v27 = Source;
      EnrollmentSID = GetEnrollmentSID(&v27, a5);
      v9 = EnrollmentSID;
      if ( EnrollmentSID < 0 )
      {
        LogError(L"Failed to get enrollment User SID : 0x%1!x!", (unsigned int)EnrollmentSID);
        goto LABEL_36;
      }
      goto LABEL_28;
    }
    *a3 = 0;
    if ( v18 == 0x10000 )
    {
LABEL_28:
      *a1 = 0;
      goto LABEL_36;
    }
    if ( v18 != 0x20000 )
      LogError(L"GetEnrollmentClientContext returned unknowned dwflags=%1!d!.  Falling back to default Local Machine store");
    *a1 = 1;
  }
  else
  {
    LogWarn(
      L"GetEnrollmentsOfTypes Failed with error code 0x%1!x! - falling back to server auth.",
      (unsigned int)EnrollmentsOfTypes);
    v9 = 1;
  }
LABEL_36:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( pCertContext )
  {
    CertFreeCertificateContext(pCertContext);
    pCertContext = 0;
  }
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( v9 < 0 )
    goto LABEL_45;
LABEL_46:
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v25);
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(&v26);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400162cc  push    rbp
0x1400162ce  push    rbx
0x1400162cf  push    rsi
0x1400162d0  push    rdi
0x1400162d1  push    r12
0x1400162d3  push    r13
0x1400162d5  push    r14
0x1400162d7  push    r15
0x1400162d9  lea     rbp, [rsp-17h]
0x1400162de  sub     rsp, 88h
0x1400162e5  mov     rax, cs:__security_cookie
0x1400162ec  xor     rax, rsp
0x1400162ef  mov     [rbp+4Fh+var_50], rax
0x1400162f3  mov     r13, r9
0x1400162f6  mov     r14, r8
0x1400162f9  mov     rbx, rdx
0x1400162fc  mov     rsi, rcx
0x1400162ff  mov     r12, [rbp+4Fh+arg_20]
0x140016303  xor     edi, edi
0x140016305  mov     [rbp+4Fh+pCertContext], rdi
0x140016309  mov     [rbp+4Fh+var_78], rdi
0x14001630d  mov     [rbp+4Fh+var_80], rdi
0x140016311  mov     [rbp+4Fh+var_A0], edi
0x140016314  xorps   xmm0, xmm0
0x140016317  movups  [rbp+4Fh+Source], xmm0
0x14001631b  mov     [rbp+4Fh+hCertStore], rdi
0x14001631f  mov     [rbp+4Fh+bstrString], rdi
0x140016323  test    r12, r12
0x140016326  jz      loc_1400165A8
0x14001632c  mov     dword ptr [rcx], 1
0x140016332  cmp     qword ptr [rdx+18h], 8
0x140016337  jb      short loc_14001633E
0x140016339  mov     rcx, [rdx]
0x14001633c  jmp     short loc_140016341
0x14001633e  mov     rcx, rbx
0x140016341  lea     r15, [rdx+10h]
0x140016345  mov     [rcx], di
0x140016348  mov     [r8], dil
0x14001634b  cmp     qword ptr [rdx+18h], 8
0x140016350  jb      short loc_140016357
0x140016352  mov     rcx, [rdx]
0x140016355  jmp     short loc_14001635A
0x140016357  mov     rcx, rbx
0x14001635a  mov     [r15], rdi
0x14001635d  mov     [rcx], di
0x140016360  mov     dl, 1
0x140016362  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MMPC_AppCertFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_AppCertFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_AppCertFix> `wil::Feature<__WilFeatureTraits_Feature_MMPC_AppCertFix>::GetImpl(void)'::`2'::impl
0x140016369  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_AppCertFix@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_AppCertFix>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14001636e  lea     rdx, [rbp+4Fh+var_78]
0x140016372  mov     ecx, 2061h
0x140016377  call    cs:__imp_GetEnrollmentsOfTypes
0x14001637d  test    eax, eax
0x14001637f  jns     short loc_140016399
0x140016381  mov     edx, eax
0x140016383  lea     rcx, aGetenrollments; "GetEnrollmentsOfTypes Failed with error"...
0x14001638a  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14001638f  mov     edi, 1
0x140016394  jmp     loc_140016563
0x140016399  mov     rcx, [rbp+4Fh+var_78]
0x14001639d  mov     rax, [rcx]
0x1400163a0  lea     rdx, [rbp+4Fh+var_80]
0x1400163a4  mov     rax, [rax+18h]
0x1400163a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400163ad  test    eax, eax
0x1400163af  jnz     loc_140016538
0x1400163b5  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1400163b9  test    rcx, rcx
0x1400163bc  jz      short loc_1400163CC
0x1400163be  call    cs:__imp_SysFreeString
0x1400163c4  mov     [rbp+4Fh+bstrString], 0
0x1400163cc  mov     rcx, [rbp+4Fh+hCertStore]; hCertStore
0x1400163d0  test    rcx, rcx
0x1400163d3  jz      short loc_1400163E5
0x1400163d5  xor     edx, edx; dwFlags
0x1400163d7  call    cs:__imp_CertCloseStore
0x1400163dd  mov     [rbp+4Fh+hCertStore], 0
0x1400163e5  mov     rcx, [rbp+4Fh+pCertContext]; pCertContext
0x1400163e9  test    rcx, rcx
0x1400163ec  jz      short loc_1400163FC
0x1400163ee  call    cs:__imp_CertFreeCertificateContext
0x1400163f4  mov     [rbp+4Fh+pCertContext], 0
0x1400163fc  mov     rcx, [rbp+4Fh+var_80]
0x140016400  mov     rax, [rcx]
0x140016403  lea     rdx, [rbp+4Fh+bstrString]
0x140016407  mov     rax, [rax+50h]
0x14001640b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016410  test    eax, eax
0x140016412  js      loc_1400164F5
0x140016418  mov     rcx, [rbp+4Fh+bstrString]
0x14001641c  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140016421  mov     r8, rax
0x140016424  mov     rdx, rcx
0x140016427  mov     rcx, rbx
0x14001642a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14001642f  cmp     qword ptr [rbx+18h], 8
0x140016434  jb      short loc_14001643B
0x140016436  mov     rdx, [rbx]
0x140016439  jmp     short loc_14001643E
0x14001643b  mov     rdx, rbx
0x14001643e  lea     rcx, aFoundMdmCertif; "Found MDM certificate %1."
0x140016445  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14001644a  mov     rcx, [rbp+4Fh+var_80]
0x14001644e  mov     rax, [rcx]
0x140016451  lea     rdx, [rbp+4Fh+Source]
0x140016455  mov     rax, [rax+18h]
0x140016459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001645e  test    eax, eax
0x140016460  jns     short loc_140016473
0x140016462  lea     rcx, aFailedToFindEn; "Failed to find EnrollmentKey"
0x140016469  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14001646e  jmp     loc_140016399
0x140016473  mov     [rbp+4Fh+var_A0], 0
0x14001647a  mov     byte ptr [r14], 0
0x14001647e  movaps  xmm0, [rbp+4Fh+Source]
0x140016482  movdqa  [rbp+4Fh+var_70], xmm0
0x140016487  lea     r9, [rbp+4Fh+pCertContext]
0x14001648b  lea     r8, [rbp+4Fh+hCertStore]
0x14001648f  lea     rdx, [rbp+4Fh+var_A0]
0x140016493  lea     rcx, [rbp+4Fh+var_70]
0x140016497  call    cs:__imp_?GetEnrollmentClientContext@@YAJU_GUID@@PEAKPEAPEAXPEAPEBU_CERT_CONTEXT@@@Z; GetEnrollmentClientContext(_GUID,ulong *,void * *,_CERT_CONTEXT const * *)
0x14001649d  test    eax, eax
0x14001649f  js      loc_140016399
0x1400164a5  mov     edx, 10h; DestinationSize
0x1400164aa  mov     r9d, edx; SourceSize
0x1400164ad  lea     r8, [rbp+4Fh+Source]; Source
0x1400164b1  mov     rcx, r13; Destination
0x1400164b4  call    cs:__imp_memcpy_s
0x1400164ba  mov     edx, [rbp+4Fh+var_A0]
0x1400164bd  cmp     edx, 60000h
0x1400164c3  jnz     short loc_140016510
0x1400164c5  mov     byte ptr [r14], 1
0x1400164c9  movaps  xmm0, [rbp+4Fh+Source]
0x1400164cd  movdqa  [rbp+4Fh+var_70], xmm0
0x1400164d2  mov     rdx, r12
0x1400164d5  lea     rcx, [rbp+4Fh+var_70]
0x1400164d9  call    cs:__imp_GetEnrollmentSID
0x1400164df  mov     edi, eax
0x1400164e1  test    eax, eax
0x1400164e3  jns     short loc_140016508
0x1400164e5  mov     edx, eax
0x1400164e7  lea     rcx, aFailedToGetEnr; "Failed to get enrollment User SID : 0x%"...
0x1400164ee  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400164f3  jmp     short loc_140016563
0x1400164f5  mov     edx, eax
0x1400164f7  lea     rcx, aGetClientcertt; "get_ClientCertThumb Failed with error c"...
0x1400164fe  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x140016503  jmp     loc_140016399
0x140016508  mov     dword ptr [rsi], 0
0x14001650e  jmp     short loc_140016563
0x140016510  mov     byte ptr [r14], 0
0x140016514  cmp     edx, 10000h
0x14001651a  jz      short loc_140016508
0x14001651c  cmp     edx, 20000h
0x140016522  jz      short loc_140016530
0x140016524  lea     rcx, aGetenrollmentc; "GetEnrollmentClientContext returned unk"...
0x14001652b  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016530  mov     dword ptr [rsi], 1
0x140016536  jmp     short loc_140016563
0x140016538  lea     rcx, aAnEnrollmentCl; "An enrollment client context was not fo"...
0x14001653f  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016544  mov     dword ptr [rsi], 1
0x14001654a  cmp     qword ptr [rbx+18h], 8
0x14001654f  jb      short loc_140016554
0x140016551  mov     rbx, [rbx]
0x140016554  mov     qword ptr [r15], 0
0x14001655b  xor     eax, eax
0x14001655d  mov     [rbx], ax
0x140016560  mov     [r14], al
0x140016563  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x140016567  test    rcx, rcx
0x14001656a  jz      short loc_14001657A
0x14001656c  call    cs:__imp_SysFreeString
0x140016572  mov     [rbp+4Fh+bstrString], 0
0x14001657a  mov     rcx, [rbp+4Fh+pCertContext]; pCertContext
0x14001657e  test    rcx, rcx
0x140016581  jz      short loc_140016591
0x140016583  call    cs:__imp_CertFreeCertificateContext
0x140016589  mov     [rbp+4Fh+pCertContext], 0
0x140016591  mov     rcx, [rbp+4Fh+hCertStore]; hCertStore
0x140016595  test    rcx, rcx
0x140016598  jz      short loc_1400165A2
0x14001659a  xor     edx, edx; dwFlags
0x14001659c  call    cs:__imp_CertCloseStore
0x1400165a2  test    edi, edi
0x1400165a4  jns     short loc_1400165BC
0x1400165a6  jmp     short loc_1400165AD
0x1400165a8  mov     edi, 80070057h
0x1400165ad  mov     edx, edi
0x1400165af  lea     rcx, aFailedToRetrie; "Failed to retrieve client cert store an"...
0x1400165b6  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400165bb  nop
0x1400165bc  lea     rcx, [rbp+4Fh+var_80]
0x1400165c0  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1400165c5  nop
0x1400165c6  lea     rcx, [rbp+4Fh+var_78]
0x1400165ca  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1400165cf  mov     eax, edi
0x1400165d1  mov     rcx, [rbp+4Fh+var_50]
0x1400165d5  xor     rcx, rsp; StackCookie
0x1400165d8  call    __security_check_cookie
0x1400165dd  add     rsp, 88h
0x1400165e4  pop     r15
0x1400165e6  pop     r14
0x1400165e8  pop     r13
0x1400165ea  pop     r12
0x1400165ec  pop     rdi
0x1400165ed  pop     rsi
0x1400165ee  pop     rbx
0x1400165ef  pop     rbp
0x1400165f0  retn
```
