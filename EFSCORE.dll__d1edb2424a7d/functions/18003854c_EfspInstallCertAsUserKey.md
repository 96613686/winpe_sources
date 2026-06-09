# EfspInstallCertAsUserKey

- ea: `0x18003854c`
- end: `0x180038d0c`
- name: `EfspInstallCertAsUserKey`
- size: `1984`
- prototype: `__int64 __usercall@<rax>(struct _EFS_USER_INFO *@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update`

## callers

- `0x180017ab4`
- `0x18003e5a4`

## callees

- `0x18000505d`
- `0x1800102f0`
- `0x180010bf0`
- `0x180016490`
- `0x18001ee88`
- `0x18001f0fc`
- `0x180022bf4`
- `0x180025cd0`
- `0x180036d20`
- `0x180037000`
- `0x1800380f8`
- `0x180038138`
- `0x18003854c`
- `0x180038e38`
- `0x180039030`
- `0x18003910c`
- `0x180063698`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003862e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003879d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800385bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003862e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003879d`
- `CRYPT32!CertCreateCertificateContext` at `0x1800385a8`
- `CRYPT32!CertCreateCertificateContext` at `0x1800385a8`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180038624`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800386ff`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180038624`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800386ff`
- `CRYPT32!CertFreeCertificateContext` at `0x18003876f`
- `CRYPT32!CertFreeCertificateContext` at `0x180038c7e`
- `CRYPT32!CertFreeCertificateContext` at `0x180038ccf`
- `CRYPT32!CertFreeCertificateContext` at `0x18003876f`
- `CRYPT32!CertFreeCertificateContext` at `0x180038c7e`
- `CRYPT32!CertFreeCertificateContext` at `0x180038ccf`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x180038870`
- `EFSUTIL!EfsUtilCheckCurrentKeyCapabilities` at `0x180038870`
- `EFSUTIL!EfsUtilSetCurrentKey` at `0x180038be8`
- `EFSUTIL!EfsUtilSetCurrentKey` at `0x180038be8`

## pseudocode

```c
__int64 __fastcall EfspInstallCertAsUserKey(
        struct _EFS_USER_INFO *a1,
        __int64 a2,
        unsigned int a3,
        char a4,
        __int64 a5)
{
  void *v7; // r14
  bool v8; // r12
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v10; // rsi
  DWORD LastError; // edi
  int v12; // eax
  int v13; // eax
  void *v14; // rax
  int v15; // eax
  int v16; // eax
  const CERT_CONTEXT *CertContextFromCertHash; // rax
  int v18; // eax
  DWORD PinCacheForCert; // eax
  int v20; // eax
  DWORD v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // r15d
  unsigned int SecondaryKeyInfo; // eax
  int v26; // eax
  DWORD KeyInfoFromCertHash; // eax
  int v28; // eax
  int CurrentHash; // eax
  unsigned int v30; // eax
  int updated; // eax
  DWORD v32; // eax
  int v33; // eax
  DWORD v34; // eax
  int v35; // eax
  DWORD pcbData; // [rsp+44h] [rbp-64h] BYREF
  __int64 v38; // [rsp+48h] [rbp-60h] BYREF
  int v39; // [rsp+50h] [rbp-58h] BYREF
  void *Buf1; // [rsp+58h] [rbp-50h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+60h] [rbp-48h]
  __int64 v42; // [rsp+68h] [rbp-40h] BYREF
  struct _EFS_ECC_SECONDARY_KEY *v43; // [rsp+70h] [rbp-38h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-30h]
  unsigned int v45; // [rsp+C0h] [rbp+18h] BYREF

  v45 = a3;
  pCertContext = 0;
  pcbData = 0;
  v7 = 0;
  lpMem = 0;
  Buf1 = 0;
  v39 = 0;
  v43 = 0;
  v8 = 1;
  v42 = 0;
  CertificateContext = CertCreateCertificateContext(
                         **(_DWORD **)(a2 + 16),
                         *(const BYTE **)(*(_QWORD *)(a2 + 16) + 8LL),
                         *(_DWORD *)(*(_QWORD *)(a2 + 16) + 4LL));
  v10 = CertificateContext;
  pCertContext = CertificateContext;
  if ( !CertificateContext )
  {
    LastError = GetLastError();
    v12 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 1, 5);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v12, 1, 5);
    goto LABEL_46;
  }
  if ( !CertGetCertificateContextProperty(CertificateContext, 3u, 0, &pcbData) )
  {
    LastError = GetLastError();
    v13 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 1, 15);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v13, 1, 15);
    goto LABEL_46;
  }
  v14 = wil::details::heap_allocator::allocate(pcbData);
  v7 = v14;
  lpMem = v14;
  if ( !v14 )
  {
    LastError = 8;
    v15 = fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_ERROR_MEMORY, pcbData, 1, 22);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v15, 1, 22);
    goto LABEL_46;
  }
  if ( !CertGetCertificateContextProperty(v10, 3u, v14, &pcbData) )
  {
    LastError = GetLastError();
    v16 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 1, 32);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v16, 1, 32);
    goto LABEL_46;
  }
  if ( (a4 & 1) == 0 )
  {
    CertFreeCertificateContext(v10);
    pCertContext = 0;
    CertContextFromCertHash = (const CERT_CONTEXT *)GetCertContextFromCertHash(v7, pcbData, 0x10000);
    v10 = CertContextFromCertHash;
    pCertContext = CertContextFromCertHash;
    if ( !CertContextFromCertHash )
    {
      LastError = GetLastError();
      v18 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, LastError, 1, 59);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v18, 1, 59);
      goto LABEL_46;
    }
    if ( a5 )
    {
      PinCacheForCert = EfspMakePinCacheForCert(CertContextFromCertHash, a5);
      LastError = PinCacheForCert;
      if ( PinCacheForCert )
      {
        v20 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, PinCacheForCert, 1, 66);
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v20, 1, 66);
        goto LABEL_46;
      }
    }
    v21 = EfsUtilCheckCurrentKeyCapabilities(v10, 393215, &v45);
    LastError = v21;
    if ( v21 )
    {
      v22 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v21, 1, 82);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v22, 1, 82);
      goto LABEL_46;
    }
    if ( !(unsigned int)EfspIsValidCurrentKey_Capabilities(v45) )
    {
      LastError = 6022;
      v23 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, 6022, 1, 88);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v23, 1, 88);
      goto LABEL_46;
    }
  }
  if ( (v45 & 0x1000) == 0 )
  {
    v24 = 1;
    HIDWORD(v38) = 1;
    if ( (EfsOptions & 2) != 0 )
      v24 = 3;
    goto LABEL_24;
  }
  LOBYTE(v24) = 16;
  HIDWORD(v38) = 16;
  if ( (EfsOptions & 2) != 0 || (v45 & 0x40) == 0 )
  {
    v24 = 48;
LABEL_24:
    HIDWORD(v38) = v24;
  }
  if ( (v24 & 0x20) != 0
    && (SecondaryKeyInfo = EfspEccGetSecondaryKeyInfo(HKEY_USERS, *((LPCWSTR *)a1 + 4), v10, 1, &v43),
        (LastError = SecondaryKeyInfo) != 0) )
  {
    v26 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, SecondaryKeyInfo, 1, 133);
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v26, 1, 133);
  }
  else
  {
    KeyInfoFromCertHash = GetKeyInfoFromCertHash(a1, (__int64)v43, (__int64)&v42, (__int64)&v38);
    LastError = KeyInfoFromCertHash;
    if ( KeyInfoFromCertHash )
    {
      v28 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, KeyInfoFromCertHash, 1, 145);
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v28, 1, 145);
    }
    else
    {
      CurrentHash = GetCurrentHash(a1, &Buf1, &v39);
      if ( CurrentHash )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, CurrentHash, 1, 167);
        Buf1 = 0;
        v39 = 0;
      }
      if ( Buf1 )
      {
        v30 = *(_DWORD *)(v42 + 4);
        if ( v39 == v30 )
          v8 = memcmp_0(Buf1, *(const void **)(v42 + 8), v30) != 0;
      }
      if ( v8 )
      {
        updated = EfsUpdateMasterKeyHistory(a1);
        if ( updated )
          fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, updated, 1, 190);
      }
      if ( Buf1 )
      {
        EfsFreeHeap(Buf1);
        Buf1 = 0;
      }
      if ( v43 && (v32 = EfspEccSaveSecondaryKeyInfo(HKEY_USERS, *((LPCWSTR *)a1 + 4), v43), (LastError = v32) != 0) )
      {
        v33 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v32, 1, 208);
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v33, 1, 208);
      }
      else
      {
        v34 = EfsUtilSetCurrentKey(v7, pcbData, v45, *((_QWORD *)a1 + 4));
        LastError = v34;
        if ( v34 )
        {
          v35 = fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, v34, 1, 217);
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v35, 1, 217);
        }
        else
        {
          EfsPromoteToCurrentKey((_DWORD)a1, v42, v45, (_DWORD)v10, (__int64)L"AddressBook");
        }
      }
    }
  }
LABEL_46:
  if ( v43 )
    EfsEccReleaseSecondaryKeyInfo(v43);
  if ( v10 )
    CertFreeCertificateContext(v10);
  if ( v7 )
    EfsFreeHeap(v7);
  if ( v42 )
    EfsReleaseUserKeyInfo();
  return LastError;
}

```

## disassembly

```asm
0x18003854c  mov     rax, rsp
0x18003854f  mov     [rax+10h], rsi
0x180038553  mov     [rax+18h], r8d
0x180038557  mov     [rax+8], rcx
0x18003855b  push    rdi
0x18003855c  push    r12
0x18003855e  push    r13
0x180038560  push    r14
0x180038562  push    r15
0x180038564  sub     rsp, 80h
0x18003856b  mov     edi, r9d
0x18003856e  mov     r13, rcx
0x180038571  mov     qword ptr [rax-48h], 0
0x180038579  mov     dword ptr [rax-64h], 0
0x180038580  xor     r14d, r14d
0x180038583  mov     [rax-30h], r14
0x180038587  mov     [rax-50h], r14
0x18003858b  mov     [rax-58h], r14d
0x18003858f  mov     [rax-38h], r14
0x180038593  mov     r12b, 1
0x180038596  mov     [rax-40h], r14
0x18003859a  mov     rcx, [rdx+10h]
0x18003859e  mov     r8d, [rcx+4]; cbCertEncoded
0x1800385a2  mov     rdx, [rcx+8]; pbCertEncoded
0x1800385a6  mov     ecx, [rcx]; dwCertEncodingType
0x1800385a8  call    cs:__imp_CertCreateCertificateContext
0x1800385ae  mov     rsi, rax
0x1800385b1  mov     [rsp+0A8h+pCertContext], rax
0x1800385b6  test    rax, rax
0x1800385b9  jnz     short loc_180038612
0x1800385bb  call    cs:__imp_GetLastError
0x1800385c1  mov     edi, eax
0x1800385c3  mov     [rsp+0A8h+var_68], eax
0x1800385c7  mov     r15d, 605h
0x1800385cd  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800385d2  lea     r12d, [r14+1]
0x1800385d6  mov     r9d, r12d
0x1800385d9  mov     r8d, eax
0x1800385dc  lea     rdx, EFS_API_ERROR
0x1800385e3  mov     rcx, cs:g_hPublisher
0x1800385ea  call    fnEfsLogTrace1
0x1800385ef  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800385f4  mov     r9d, r12d
0x1800385f7  mov     r8d, eax
0x1800385fa  lea     rdx, EFS_TRACE_ERROR
0x180038601  mov     rcx, cs:g_hPublisher
0x180038608  call    fnEfsLogTrace1
0x18003860d  jmp     loc_180038CB8
0x180038612  lea     r9, [rsp+0A8h+pcbData]; pcbData
0x180038617  xor     r8d, r8d; pvData
0x18003861a  lea     r15d, [r8+3]
0x18003861e  mov     edx, r15d; dwPropId
0x180038621  mov     rcx, rsi; pCertContext
0x180038624  call    cs:__imp_CertGetCertificateContextProperty
0x18003862a  test    eax, eax
0x18003862c  jnz     short loc_180038687
0x18003862e  call    cs:__imp_GetLastError
0x180038634  mov     edi, eax
0x180038636  mov     [rsp+0A8h+var_68], eax
0x18003863a  mov     r15d, 60Fh
0x180038640  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038645  mov     r12d, 1
0x18003864b  mov     r9d, r12d
0x18003864e  mov     r8d, eax
0x180038651  lea     rdx, EFS_API_ERROR
0x180038658  mov     rcx, cs:g_hPublisher
0x18003865f  call    fnEfsLogTrace1
0x180038664  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038669  mov     r9d, r12d
0x18003866c  mov     r8d, eax
0x18003866f  lea     rdx, EFS_TRACE_ERROR
0x180038676  mov     rcx, cs:g_hPublisher
0x18003867d  call    fnEfsLogTrace1
0x180038682  jmp     loc_180038CB8
0x180038687  mov     ecx, [rsp+0A8h+pcbData]; unsigned __int64
0x18003868b  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x180038690  mov     r14, rax
0x180038693  mov     [rsp+0A8h+lpMem], rax
0x180038698  test    rax, rax
0x18003869b  jnz     short loc_1800386F1
0x18003869d  lea     edi, [rax+8]
0x1800386a0  mov     [rsp+0A8h+var_68], edi
0x1800386a4  mov     r15d, 616h
0x1800386aa  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800386af  lea     r12d, [rax+1]
0x1800386b3  mov     r9d, r12d
0x1800386b6  mov     r8d, [rsp+0A8h+pcbData]
0x1800386bb  lea     rdx, EFS_ERROR_MEMORY
0x1800386c2  mov     rcx, cs:g_hPublisher
0x1800386c9  call    fnEfsLogTrace1
0x1800386ce  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800386d3  mov     r9d, r12d
0x1800386d6  mov     r8d, eax
0x1800386d9  lea     rdx, EFS_TRACE_ERROR
0x1800386e0  mov     rcx, cs:g_hPublisher
0x1800386e7  call    fnEfsLogTrace1
0x1800386ec  jmp     loc_180038CB8
0x1800386f1  lea     r9, [rsp+0A8h+pcbData]; pcbData
0x1800386f6  mov     r8, r14; pvData
0x1800386f9  mov     edx, r15d; dwPropId
0x1800386fc  mov     rcx, rsi; pCertContext
0x1800386ff  call    cs:__imp_CertGetCertificateContextProperty
0x180038705  test    eax, eax
0x180038707  jnz     short loc_180038762
0x180038709  call    cs:__imp_GetLastError
0x18003870f  mov     edi, eax
0x180038711  mov     [rsp+0A8h+var_68], eax
0x180038715  mov     r15d, 620h
0x18003871b  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038720  mov     r12d, 1
0x180038726  mov     r9d, r12d
0x180038729  mov     r8d, eax
0x18003872c  lea     rdx, EFS_API_ERROR
0x180038733  mov     rcx, cs:g_hPublisher
0x18003873a  call    fnEfsLogTrace1
0x18003873f  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038744  mov     r9d, r12d
0x180038747  mov     r8d, eax
0x18003874a  lea     rdx, EFS_TRACE_ERROR
0x180038751  mov     rcx, cs:g_hPublisher
0x180038758  call    fnEfsLogTrace1
0x18003875d  jmp     loc_180038CB8
0x180038762  test    dil, 1
0x180038766  jnz     loc_180038931
0x18003876c  mov     rcx, rsi; pCertContext
0x18003876f  call    cs:__imp_CertFreeCertificateContext
0x180038775  mov     [rsp+0A8h+pCertContext], 0
0x18003877e  mov     r8d, 10000h
0x180038784  mov     edx, [rsp+0A8h+pcbData]
0x180038788  mov     rcx, r14
0x18003878b  call    GetCertContextFromCertHash
0x180038790  mov     rsi, rax
0x180038793  mov     [rsp+0A8h+pCertContext], rax
0x180038798  test    rax, rax
0x18003879b  jnz     short loc_1800387F4
0x18003879d  call    cs:__imp_GetLastError
0x1800387a3  mov     edi, eax
0x1800387a5  mov     [rsp+0A8h+var_68], eax
0x1800387a9  mov     r15d, 63Bh
0x1800387af  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800387b4  lea     r12d, [rsi+1]
0x1800387b8  mov     r9d, r12d
0x1800387bb  mov     r8d, eax
0x1800387be  lea     rdx, EFS_API_ERROR
0x1800387c5  mov     rcx, cs:g_hPublisher
0x1800387cc  call    fnEfsLogTrace1
0x1800387d1  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800387d6  mov     r9d, r12d
0x1800387d9  mov     r8d, eax
0x1800387dc  lea     rdx, EFS_TRACE_ERROR
0x1800387e3  mov     rcx, cs:g_hPublisher
0x1800387ea  call    fnEfsLogTrace1
0x1800387ef  jmp     loc_180038CB8
0x1800387f4  mov     rdx, [rsp+0A8h+arg_20]
0x1800387fc  test    rdx, rdx
0x1800387ff  jz      short loc_180038860
0x180038801  mov     rcx, rsi
0x180038804  call    EfspMakePinCacheForCert
0x180038809  mov     edi, eax
0x18003880b  mov     [rsp+0A8h+var_68], eax
0x18003880f  test    eax, eax
0x180038811  jz      short loc_180038860
0x180038813  mov     r15d, 642h
0x180038819  mov     dword ptr [rsp+0A8h+var_88], r15d
0x18003881e  mov     r12d, 1
0x180038824  mov     r9d, r12d
0x180038827  mov     r8d, eax
0x18003882a  lea     rdx, EFS_API_ERROR
0x180038831  mov     rcx, cs:g_hPublisher
0x180038838  call    fnEfsLogTrace1
0x18003883d  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038842  mov     r9d, r12d
0x180038845  mov     r8d, eax
0x180038848  lea     rdx, EFS_TRACE_ERROR
0x18003884f  mov     rcx, cs:g_hPublisher
0x180038856  call    fnEfsLogTrace1
0x18003885b  jmp     loc_180038CB8
0x180038860  lea     r8, [rsp+0A8h+arg_10]
0x180038868  mov     edx, 5FFFFh
0x18003886d  mov     rcx, rsi
0x180038870  call    cs:__imp_EfsUtilCheckCurrentKeyCapabilities
0x180038876  mov     edi, eax
0x180038878  mov     [rsp+0A8h+var_68], eax
0x18003887c  test    eax, eax
0x18003887e  jz      short loc_1800388CD
0x180038880  mov     r15d, 652h
0x180038886  mov     dword ptr [rsp+0A8h+var_88], r15d
0x18003888b  mov     r12d, 1
0x180038891  mov     r9d, r12d
0x180038894  mov     r8d, eax
0x180038897  lea     rdx, EFS_API_ERROR
0x18003889e  mov     rcx, cs:g_hPublisher
0x1800388a5  call    fnEfsLogTrace1
0x1800388aa  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800388af  mov     r9d, r12d
0x1800388b2  mov     r8d, eax
0x1800388b5  lea     rdx, EFS_TRACE_ERROR
0x1800388bc  mov     rcx, cs:g_hPublisher
0x1800388c3  call    fnEfsLogTrace1
0x1800388c8  jmp     loc_180038CB8
0x1800388cd  mov     ecx, [rsp+0A8h+arg_10]
0x1800388d4  call    EfspIsValidCurrentKey_Capabilities
0x1800388d9  test    eax, eax
0x1800388db  jnz     short loc_180038931
0x1800388dd  mov     edi, 1786h
0x1800388e2  mov     [rsp+0A8h+var_68], edi
0x1800388e6  mov     r15d, 658h
0x1800388ec  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800388f1  lea     r12d, [rax+1]
0x1800388f5  mov     r9d, r12d
0x1800388f8  mov     r8d, edi
0x1800388fb  lea     rdx, EFS_API_ERROR
0x180038902  mov     rcx, cs:g_hPublisher
0x180038909  call    fnEfsLogTrace1
0x18003890e  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038913  mov     r9d, r12d
0x180038916  mov     r8d, eax
0x180038919  lea     rdx, EFS_TRACE_ERROR
0x180038920  mov     rcx, cs:g_hPublisher
0x180038927  call    fnEfsLogTrace1
0x18003892c  jmp     loc_180038CB8
0x180038931  test    [rsp+0A8h+arg_10], 1000h
0x18003893c  jz      short loc_18003896A
0x18003893e  mov     r15d, 10h
0x180038944  mov     dword ptr [rsp+0A8h+var_60+4], r15d
0x180038949  test    byte ptr cs:?EfsOptions@@3KA, 2; ulong EfsOptions
0x180038950  setz    cl
0x180038953  test    byte ptr [rsp+0A8h+arg_10], 40h
0x18003895b  setnz   al
0x18003895e  test    al, cl
0x180038960  jnz     short loc_180038989
0x180038962  mov     r15d, 30h ; '0'
0x180038968  jmp     short loc_180038984
0x18003896a  mov     r15d, 1
0x180038970  mov     dword ptr [rsp+0A8h+var_60+4], r15d
0x180038975  test    byte ptr cs:?EfsOptions@@3KA, 2; ulong EfsOptions
0x18003897c  lea     eax, [r15+2]
0x180038980  cmovnz  r15d, eax
0x180038984  mov     dword ptr [rsp+0A8h+var_60+4], r15d
0x180038989  test    r15b, 20h
0x18003898d  jz      short loc_180038A09
0x18003898f  lea     rax, [rsp+0A8h+var_38]
0x180038994  mov     [rsp+0A8h+var_88], rax; struct _EFS_ECC_SECONDARY_KEY **
0x180038999  mov     r9d, 1; int
0x18003899f  mov     r8, rsi; struct _CERT_CONTEXT *
0x1800389a2  mov     rdx, [r13+20h]; lpSubKey
0x1800389a6  mov     rcx, 0FFFFFFFF80000003h; hkey
0x1800389ad  call    ?EfspEccGetSecondaryKeyInfo@@YAKPEAUHKEY__@@PEBGPEBU_CERT_CONTEXT@@HPEAPEAU_EFS_ECC_SECONDARY_KEY@@@Z; EfspEccGetSecondaryKeyInfo(HKEY__ *,ushort const *,_CERT_CONTEXT const *,int,_EFS_ECC_SECONDARY_KEY * *)
0x1800389b2  mov     edi, eax
0x1800389b4  mov     [rsp+0A8h+var_68], eax
0x1800389b8  test    eax, eax
0x1800389ba  jz      short loc_180038A09
0x1800389bc  mov     r15d, 685h
0x1800389c2  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800389c7  mov     r12d, 1
0x1800389cd  mov     r9d, r12d
0x1800389d0  mov     r8d, eax
0x1800389d3  lea     rdx, EFS_API_ERROR
0x1800389da  mov     rcx, cs:g_hPublisher
0x1800389e1  call    fnEfsLogTrace1
0x1800389e6  mov     dword ptr [rsp+0A8h+var_88], r15d
0x1800389eb  mov     r9d, r12d
0x1800389ee  mov     r8d, eax
0x1800389f1  lea     rdx, EFS_TRACE_ERROR
0x1800389f8  mov     rcx, cs:g_hPublisher
0x1800389ff  call    fnEfsLogTrace1
0x180038a04  jmp     loc_180038CB8
0x180038a09  lea     rax, [rsp+0A8h+var_60]
0x180038a0e  mov     [rsp+0A8h+var_78], rax; __int64
0x180038a13  lea     rax, [rsp+0A8h+var_40]
0x180038a18  mov     [rsp+0A8h+var_80], rax; __int64
0x180038a1d  mov     rax, [rsp+0A8h+var_38]
0x180038a22  mov     [rsp+0A8h+var_88], rax; __int64
0x180038a27  mov     r9d, r15d
0x180038a2a  mov     r8d, [rsp+0A8h+pcbData]
0x180038a2f  mov     rdx, r14
0x180038a32  mov     rcx, r13; struct _EFS_USER_INFO *
0x180038a35  call    GetKeyInfoFromCertHash
0x180038a3a  mov     edi, eax
0x180038a3c  mov     [rsp+0A8h+var_68], eax
0x180038a40  test    eax, eax
0x180038a42  jz      short loc_180038A91
0x180038a44  mov     r15d, 691h
0x180038a4a  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038a4f  mov     r12d, 1
0x180038a55  mov     r9d, r12d
0x180038a58  mov     r8d, eax
0x180038a5b  lea     rdx, EFS_API_ERROR
0x180038a62  mov     rcx, cs:g_hPublisher
0x180038a69  call    fnEfsLogTrace1
0x180038a6e  mov     dword ptr [rsp+0A8h+var_88], r15d
0x180038a73  mov     r9d, r12d
0x180038a76  mov     r8d, eax
0x180038a79  lea     rdx, EFS_TRACE_ERROR
0x180038a80  mov     rcx, cs:g_hPublisher
0x180038a87  call    fnEfsLogTrace1
0x180038a8c  jmp     loc_180038CB8
0x180038a91  lea     r8, [rsp+0A8h+var_58]
0x180038a96  lea     rdx, [rsp+0A8h+Buf1]
0x180038a9b  mov     rcx, r13
  ... truncated ...
```
