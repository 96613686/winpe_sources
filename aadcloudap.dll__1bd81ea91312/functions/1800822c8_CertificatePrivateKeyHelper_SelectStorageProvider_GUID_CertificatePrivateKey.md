# CertificatePrivateKeyHelper::SelectStorageProvider(_GUID *,CertificatePrivateKey &)

- ea: `0x1800822c8`
- end: `0x180082411`
- name: `?SelectStorageProvider@CertificatePrivateKeyHelper@@CA_KPEAU_GUID@@AEAVCertificatePrivateKey@@@Z`
- size: `329`
- prototype: `unsigned __int64 __fastcall(PBYTE pbInput, struct CertificatePrivateKey *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180080ccc`

## callees

- `0x1800065e8`
- `0x18000685c`
- `0x1800069c0`
- `0x180006ac4`
- `0x180071e14`
- `0x1800822c8`

## import_xrefs

- `ncrypt!NCryptSetProperty` at `0x18008238a`
- `ncrypt!NCryptSetProperty` at `0x18008238a`
- `ncrypt!NCryptOpenStorageProvider` at `0x180082332`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008235e`
- `ncrypt!NCryptOpenStorageProvider` at `0x180082332`
- `ncrypt!NCryptOpenStorageProvider` at `0x18008235e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
NCRYPT_PROV_HANDLE __fastcall CertificatePrivateKeyHelper::SelectStorageProvider(
        PBYTE pbInput,
        struct CertificatePrivateKey *a2)
{
  LPCWSTR *v4; // rbx
  SECURITY_STATUS v5; // eax
  const WCHAR *v6; // rax
  NCRYPT_PROV_HANDLE v7; // rbx
  int v9; // [rsp+30h] [rbp-50h]
  const char *v10[6]; // [rsp+50h] [rbp-30h] BYREF
  SECURITY_STATUS v11; // [rsp+A8h] [rbp+28h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+B0h] [rbp+30h] BYREF

  v11 = 0;
  phProvider = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v10,
    (int)"certificateprivatekey.cpp",
    (int)"CertificatePrivateKeyHelper::SelectStorageProvider",
    (int)&v11);
  v4 = (LPCWSTR *)((char *)a2 + 8);
  ATL::CSimpleStringT<unsigned short,0>::SetString(v4, L"Microsoft Platform Crypto Provider", 34);
  v5 = NCryptOpenStorageProvider(&phProvider, *v4, 0);
  v11 = v5;
  if ( v5 >= 0 )
  {
    if ( pbInput )
    {
      NCryptSetProperty(phProvider, L"PCP_SESSIONID", pbInput, 0x10u, 0);
      v5 = v11;
    }
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(v4, L"Microsoft Software Key Storage Provider", 39);
    v5 = NCryptOpenStorageProvider(&phProvider, *v4, 0);
    v11 = v5;
  }
  if ( v5 >= 0 )
  {
    v6 = &base;
    if ( *v4 )
      v6 = *v4;
    v9 = 296;
    WPPTraceLogA(4, 0, "%x 0x%08x %s:%u : %s:%ws", 4, 0, "certificateprivatekey.cpp", v9, "Crypto Provider", v6);
  }
  else
  {
    ATL::CSimpleStringT<unsigned short,0>::Empty(v4);
  }
  v7 = phProvider;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v10);
  return v7;
}

```

## disassembly

```asm
0x1800822c8  mov     [rsp-18h+arg_0], rbx
0x1800822cd  push    rbp
0x1800822ce  push    rdi
0x1800822cf  push    r14
0x1800822d1  mov     rbp, rsp
0x1800822d4  sub     rsp, 80h
0x1800822db  mov     rbx, rdx
0x1800822de  mov     rdi, rcx
0x1800822e1  mov     [rbp+arg_8], 0
0x1800822e8  mov     [rbp+phProvider], 0
0x1800822f0  lea     r9, [rbp+arg_8]
0x1800822f4  lea     r8, aCertificatepri_0; "CertificatePrivateKeyHelper::SelectStor"...
0x1800822fb  lea     r14, aOnecoreuapDsEx_63+20h; "certificateprivatekey.cpp"
0x180082302  mov     rdx, r14
0x180082305  lea     rcx, [rbp+var_30]
0x180082309  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18008230e  nop
0x18008230f  add     rbx, 8
0x180082313  mov     r8d, 22h ; '"'
0x180082319  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180082320  mov     rcx, rbx
0x180082323  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180082328  xor     r8d, r8d; dwFlags
0x18008232b  mov     rdx, [rbx]; pszProviderName
0x18008232e  lea     rcx, [rbp+phProvider]; phProvider
0x180082332  call    cs:__imp_NCryptOpenStorageProvider
0x180082338  mov     [rbp+arg_8], eax
0x18008233b  test    eax, eax
0x18008233d  jns     short loc_180082369
0x18008233f  mov     r8d, 27h ; '''
0x180082345  lea     rdx, aMicrosoftSoftw; "Microsoft Software Key Storage Provider"
0x18008234c  mov     rcx, rbx
0x18008234f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180082354  xor     r8d, r8d; dwFlags
0x180082357  mov     rdx, [rbx]; pszProviderName
0x18008235a  lea     rcx, [rbp+phProvider]; phProvider
0x18008235e  call    cs:__imp_NCryptOpenStorageProvider
0x180082364  mov     [rbp+arg_8], eax
0x180082367  jmp     short loc_180082393
0x180082369  test    rdi, rdi
0x18008236c  jz      short loc_180082393
0x18008236e  mov     [rsp+80h+dwFlags], 0; dwFlags
0x180082376  mov     r9d, 10h; cbInput
0x18008237c  mov     r8, rdi; pbInput
0x18008237f  lea     rdx, aPcpSessionid; "PCP_SESSIONID"
0x180082386  mov     rcx, [rbp+phProvider]; hObject
0x18008238a  call    cs:__imp_NCryptSetProperty
0x180082390  mov     eax, [rbp+arg_8]
0x180082393  test    eax, eax
0x180082395  jns     short loc_1800823A1
0x180082397  mov     rcx, rbx
0x18008239a  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18008239f  jmp     short loc_1800823ED
0x1800823a1  lea     rax, base
0x1800823a8  cmp     qword ptr [rbx], 0
0x1800823ac  cmovnz  rax, [rbx]
0x1800823b0  mov     [rsp+80h+var_40], rax
0x1800823b5  lea     rax, aCryptoProvider; "Crypto Provider"
0x1800823bc  mov     [rsp+80h+var_48], rax
0x1800823c1  mov     [rsp+80h+var_50], 128h
0x1800823c9  mov     [rsp+80h+var_58], r14
0x1800823ce  mov     qword ptr [rsp+80h+dwFlags], 0
0x1800823d7  mov     ecx, 4
0x1800823dc  mov     r9d, ecx
0x1800823df  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x1800823e6  xor     edx, edx
0x1800823e8  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x1800823ed  mov     rbx, [rbp+phProvider]
0x1800823f1  lea     rcx, [rbp+var_30]
0x1800823f5  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x1800823fa  mov     rax, rbx
0x1800823fd  mov     rbx, [rsp+80h+arg_0]
0x180082405  add     rsp, 80h
0x18008240c  pop     r14
0x18008240e  pop     rdi
0x18008240f  pop     rbp
0x180082410  retn
```
