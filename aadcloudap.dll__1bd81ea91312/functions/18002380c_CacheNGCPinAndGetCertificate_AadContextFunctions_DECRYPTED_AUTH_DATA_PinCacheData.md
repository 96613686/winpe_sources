# CacheNGCPinAndGetCertificate(AadContextFunctions *,_DECRYPTED_AUTH_DATA *,PinCacheData &)

- ea: `0x18002380c`
- end: `0x180023c9f`
- name: `?CacheNGCPinAndGetCertificate@@YAJPEAVAadContextFunctions@@PEAU_DECRYPTED_AUTH_DATA@@AEAUPinCacheData@@@Z`
- size: `1171`
- prototype: `int(struct AadContextFunctions *, struct _DECRYPTED_AUTH_DATA *, struct PinCacheData *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002bc04`

## callees

- `0x180003c20`
- `0x1800069c0`
- `0x180006ac4`
- `0x18002380c`
- `0x1800256d0`
- `0x180028618`
- `0x180071e14`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023bf3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c35`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023c3f`
- `ncrypt!NCryptGetProperty` at `0x1800239df`
- `ncrypt!NCryptGetProperty` at `0x180023a90`
- `ncrypt!NCryptGetProperty` at `0x1800239df`
- `ncrypt!NCryptGetProperty` at `0x180023a90`
- `ncrypt!NCryptSetProperty` at `0x180023b80`
- `ncrypt!NCryptSetProperty` at `0x180023b80`
- `ncrypt!NCryptOpenKey` at `0x180023991`
- `ncrypt!NCryptOpenKey` at `0x180023991`
- `ncrypt!NCryptFreeObject` at `0x180023c4e`
- `ncrypt!NCryptFreeObject` at `0x180023c4e`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002392a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18002392a`
- `CRYPT32!CertCreateCertificateContext` at `0x180023acd`
- `CRYPT32!CertCreateCertificateContext` at `0x180023acd`
- `CRYPT32!CertCompareCertificateName` at `0x180023b2f`
- `CRYPT32!CertCompareCertificateName` at `0x180023b2f`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180023bd7`
- `CRYPT32!CertSetCertificateContextProperty` at `0x180023bd7`
- `cryptngc!NgcUnpackCredData` at `0x1800238c2`
- `cryptngc!NgcUnpackCredData` at `0x1800238c2`

## string_xrefs

- `0x180023877`: `CacheNGCPinAndGetCertificate`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CacheNGCPinAndGetCertificate(
        struct AadContextFunctions *a1,
        struct _DECRYPTED_AUTH_DATA *a2,
        PCCERT_CONTEXT *a3)
{
  int Property; // ebx
  SECURITY_STATUS v7; // eax
  __int64 v8; // rbx
  BYTE *v9; // rsi
  PCCERT_CONTEXT CertificateContext; // rax
  signed int LastError; // eax
  unsigned int v12; // ebx
  DWORD dwFlags[2]; // [rsp+20h] [rbp-99h]
  int v15; // [rsp+30h] [rbp-89h]
  int v16; // [rsp+30h] [rbp-89h]
  signed int v17; // [rsp+50h] [rbp-69h] BYREF
  DWORD pcbResult; // [rsp+54h] [rbp-65h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-61h] BYREF
  LPCWSTR pszKeyName; // [rsp+60h] [rbp-59h] BYREF
  BYTE pbInput[8]; // [rsp+68h] [rbp-51h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp-49h] BYREF
  BYTE *v23; // [rsp+78h] [rbp-41h] BYREF
  __int64 v24; // [rsp+80h] [rbp-39h]
  struct AadContextFunctions *v25; // [rsp+88h] [rbp-31h]
  __int64 v26; // [rsp+90h] [rbp-29h] BYREF
  const char *v27[6]; // [rsp+98h] [rbp-21h] BYREF
  __int128 pvData; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v29; // [rsp+D8h] [rbp+1Fh]

  v17 = 0;
  phKey = 0;
  v23 = 0;
  v25 = a1;
  v24 = 0;
  pcbResult = 0;
  *(_QWORD *)pbInput = 0;
  v26 = 0;
  pszKeyName = 0;
  hMem = 0;
  pvData = 0;
  v29 = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v27,
    (int)"login.cpp",
    (int)"CacheNGCPinAndGetCertificate",
    (int)&v17);
  PinCacheData::Free((PinCacheData *)a3);
  Property = NgcUnpackCredData(
               *((_QWORD *)a2 + 2) + *(unsigned int *)(*((_QWORD *)a2 + 2) + 20LL),
               *(unsigned __int16 *)(*((_QWORD *)a2 + 2) + 24LL),
               &pszKeyName,
               pbInput,
               &hMem,
               &v26);
  if ( Property < 0 )
  {
    v15 = 787;
LABEL_3:
    dwFlags[0] = Property;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)dwFlags, "login.cpp", v15, "HRESULT", &base);
    v17 = Property & 0xAFFFFFFF | 0x40000000;
    goto LABEL_31;
  }
  v7 = NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)a3, L"Microsoft Passport Key Storage Provider", 0);
  v17 = v7;
  if ( v7 < 0 )
  {
    v16 = 789;
LABEL_6:
    dwFlags[0] = v7;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, *(_QWORD *)dwFlags, "login.cpp", v16, "NTSTATUS", &base);
    goto LABEL_31;
  }
  v7 = NCryptOpenKey((NCRYPT_PROV_HANDLE)*a3, &phKey, pszKeyName, 0, 0x60u);
  v17 = v7;
  if ( v7 < 0 )
  {
    v16 = 796;
    goto LABEL_6;
  }
  Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
  if ( Property < 0 )
  {
    v15 = 798;
    goto LABEL_3;
  }
  v8 = pcbResult;
  v9 = (BYTE *)(*(__int64 (__fastcall **)(struct AadContextFunctions *, __int64, _QWORD))(*(_QWORD *)a1 + 8LL))(
                 a1,
                 64,
                 pcbResult);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v23);
  v23 = v9;
  v24 = v8;
  if ( !v9 )
  {
    v7 = -1073741801;
    v17 = -1073741801;
    v16 = 804;
    goto LABEL_6;
  }
  Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", v9, pcbResult, &pcbResult, 0);
  if ( Property < 0 )
  {
    v15 = 807;
    goto LABEL_3;
  }
  CertificateContext = CertCreateCertificateContext(0x10001u, v9, pcbResult);
  a3[1] = CertificateContext;
  if ( !CertificateContext )
  {
    LastError = GetLastError();
    Property = LastError;
    if ( LastError > 0 )
      Property = (unsigned __int16)LastError | 0x80070000;
    if ( Property < 0 )
    {
      v15 = 813;
      goto LABEL_3;
    }
  }
  if ( CertCompareCertificateName(1u, &a3[1]->pCertInfo->Issuer, &a3[1]->pCertInfo->Subject) )
  {
    v7 = -1073741637;
    v17 = -1073741637;
    v16 = 820;
    goto LABEL_6;
  }
  v7 = NCryptSetProperty(phKey, L"NgcAuthTicket", pbInput, 8u, 0);
  v17 = v7;
  if ( v7 < 0 )
  {
    v16 = 829;
    goto LABEL_6;
  }
  LODWORD(pvData) = 24;
  *((_QWORD *)&pvData + 1) = phKey;
  LODWORD(v29) = -1;
  if ( !CertSetCertificateContextProperty(a3[1], 5u, 0, &pvData) )
  {
    v7 = (int)GetLastError() > 0 ? (unsigned __int16)GetLastError() | 0xC0070000 : GetLastError();
    v17 = v7;
    if ( v7 < 0 )
    {
      v16 = 844;
      goto LABEL_6;
    }
  }
  phKey = 0;
LABEL_31:
  LocalFree((HLOCAL)pszKeyName);
  LocalFree(hMem);
  if ( phKey )
    NCryptFreeObject(phKey);
  v12 = v17;
  if ( v17 < 0 )
  {
    PinCacheData::Free((PinCacheData *)a3);
    v12 = v17;
  }
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v27);
  Auto<unsigned short *,LocalAllocFunctor<unsigned short *>,AadContextFunctions>::Clear(&v23);
  return v12;
}

```

## disassembly

```asm
0x18002380c  mov     [rsp-8+arg_18], rbx
0x180023811  push    rbp
0x180023812  push    rsi
0x180023813  push    rdi
0x180023814  push    r14
0x180023816  push    r15
0x180023818  lea     rbp, [rsp-37h]
0x18002381d  sub     rsp, 0F0h
0x180023824  mov     rax, cs:__security_cookie
0x18002382b  xor     rax, rsp
0x18002382e  mov     [rbp+57h+var_30], rax
0x180023832  mov     rdi, r8
0x180023835  mov     rbx, rdx
0x180023838  mov     rsi, rcx
0x18002383b  xor     r14d, r14d
0x18002383e  mov     [rbp+57h+var_C0], r14d
0x180023842  mov     [rbp+57h+phKey], r14
0x180023846  mov     [rbp+57h+var_98], r14
0x18002384a  mov     [rbp+57h+var_88], rcx
0x18002384e  mov     [rbp+57h+var_90], r14
0x180023852  mov     [rbp+57h+pcbResult], r14d
0x180023856  mov     qword ptr [rbp+57h+pbInput], r14
0x18002385a  mov     [rbp+57h+var_80], r14
0x18002385e  mov     [rbp+57h+pszKeyName], r14
0x180023862  mov     [rbp+57h+hMem], r14
0x180023866  xorps   xmm0, xmm0
0x180023869  xor     eax, eax
0x18002386b  movups  [rbp+57h+pvData], xmm0
0x18002386f  mov     [rbp+57h+var_38], rax
0x180023873  lea     r9, [rbp+57h+var_C0]
0x180023877  lea     r8, aCachengcpinand; "CacheNGCPinAndGetCertificate"
0x18002387e  lea     r15, aOnecoreuapDsEx_25+21h; "login.cpp"
0x180023885  mov     rdx, r15
0x180023888  lea     rcx, [rbp+57h+var_78]
0x18002388c  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x180023891  nop
0x180023892  mov     rcx, rdi; this
0x180023895  call    ?Free@PinCacheData@@QEAAXXZ; PinCacheData::Free(void)
0x18002389a  mov     rax, [rbx+10h]
0x18002389e  movzx   edx, word ptr [rax+18h]
0x1800238a2  mov     ecx, [rax+14h]
0x1800238a5  add     rcx, rax
0x1800238a8  lea     rax, [rbp+57h+var_80]
0x1800238ac  mov     qword ptr [rsp+110h+var_E8], rax
0x1800238b1  lea     rax, [rbp+57h+hMem]
0x1800238b5  mov     qword ptr [rsp+110h+dwFlags], rax
0x1800238ba  lea     r9, [rbp+57h+pbInput]
0x1800238be  lea     r8, [rbp+57h+pszKeyName]
0x1800238c2  call    cs:__imp_NgcUnpackCredData
0x1800238c8  mov     ebx, eax
0x1800238ca  test    eax, eax
0x1800238cc  jns     short loc_18002391D
0x1800238ce  lea     rcx, base
0x1800238d5  mov     [rsp+110h+var_D0], rcx
0x1800238da  lea     rcx, aHresult; "HRESULT"
0x1800238e1  mov     [rsp+110h+var_D8], rcx
0x1800238e6  mov     [rsp+110h+var_E0], 313h
0x1800238ee  mov     qword ptr [rsp+110h+var_E8], r15
0x1800238f3  mov     [rsp+110h+dwFlags], ebx
0x1800238f7  mov     ecx, 2
0x1800238fc  mov     r9d, ecx
0x1800238ff  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x180023906  xor     edx, edx
0x180023908  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18002390d  btr     ebx, 1Ch
0x180023911  bts     ebx, 1Eh
0x180023915  mov     [rbp+57h+var_C0], ebx
0x180023918  jmp     loc_180023C31
0x18002391d  xor     r8d, r8d; dwFlags
0x180023920  lea     rdx, pszProviderName; "Microsoft Passport Key Storage Provider"
0x180023927  mov     rcx, rdi; phProvider
0x18002392a  call    cs:__imp_NCryptOpenStorageProvider
0x180023930  mov     [rbp+57h+var_C0], eax
0x180023933  test    eax, eax
0x180023935  jns     short loc_18002397B
0x180023937  lea     rcx, base
0x18002393e  mov     [rsp+110h+var_D0], rcx
0x180023943  lea     rcx, aNtstatus; "NTSTATUS"
0x18002394a  mov     [rsp+110h+var_D8], rcx
0x18002394f  mov     [rsp+110h+var_E0], 315h
0x180023957  mov     qword ptr [rsp+110h+var_E8], r15
0x18002395c  mov     [rsp+110h+dwFlags], eax
0x180023960  mov     ecx, 2
0x180023965  mov     r9d, ecx
0x180023968  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18002396f  xor     edx, edx
0x180023971  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x180023976  jmp     loc_180023C31
0x18002397b  mov     [rsp+110h+dwFlags], 60h ; '`'; dwFlags
0x180023983  xor     r9d, r9d; dwLegacyKeySpec
0x180023986  mov     r8, [rbp+57h+pszKeyName]; pszKeyName
0x18002398a  lea     rdx, [rbp+57h+phKey]; phKey
0x18002398e  mov     rcx, [rdi]; hProvider
0x180023991  call    cs:__imp_NCryptOpenKey
0x180023997  mov     [rbp+57h+var_C0], eax
0x18002399a  test    eax, eax
0x18002399c  jns     short loc_1800239C0
0x18002399e  lea     rcx, base
0x1800239a5  mov     [rsp+110h+var_D0], rcx
0x1800239aa  lea     rcx, aNtstatus; "NTSTATUS"
0x1800239b1  mov     [rsp+110h+var_D8], rcx
0x1800239b6  mov     [rsp+110h+var_E0], 31Ch
0x1800239be  jmp     short loc_180023957
0x1800239c0  mov     [rsp+110h+var_E8], r14d; dwFlags
0x1800239c5  lea     rax, [rbp+57h+pcbResult]
0x1800239c9  mov     qword ptr [rsp+110h+dwFlags], rax; pcbResult
0x1800239ce  xor     r9d, r9d; cbOutput
0x1800239d1  xor     r8d, r8d; pbOutput
0x1800239d4  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x1800239db  mov     rcx, [rbp+57h+phKey]; hObject
0x1800239df  call    cs:__imp_NCryptGetProperty
0x1800239e5  mov     ebx, eax
0x1800239e7  test    eax, eax
0x1800239e9  jns     short loc_180023A10
0x1800239eb  lea     rcx, base
0x1800239f2  mov     [rsp+110h+var_D0], rcx
0x1800239f7  lea     rcx, aHresult; "HRESULT"
0x1800239fe  mov     [rsp+110h+var_D8], rcx
0x180023a03  mov     [rsp+110h+var_E0], 31Eh
0x180023a0b  jmp     loc_1800238EE
0x180023a10  mov     ebx, [rbp+57h+pcbResult]
0x180023a13  mov     rax, [rsi]
0x180023a16  mov     r8d, ebx
0x180023a19  mov     edx, 40h ; '@'
0x180023a1e  mov     rcx, rsi
0x180023a21  mov     rax, [rax+8]
0x180023a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a2a  mov     rsi, rax
0x180023a2d  lea     rcx, [rbp+57h+var_98]
0x180023a31  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180023a36  mov     [rbp+57h+var_98], rsi
0x180023a3a  mov     [rbp+57h+var_90], rbx
0x180023a3e  test    rsi, rsi
0x180023a41  jnz     short loc_180023A70
0x180023a43  mov     eax, 0C0000017h
0x180023a48  mov     [rbp+57h+var_C0], eax
0x180023a4b  lea     rcx, base
0x180023a52  mov     [rsp+110h+var_D0], rcx
0x180023a57  lea     rcx, aNtstatus; "NTSTATUS"
0x180023a5e  mov     [rsp+110h+var_D8], rcx
0x180023a63  mov     [rsp+110h+var_E0], 324h
0x180023a6b  jmp     loc_180023957
0x180023a70  mov     [rsp+110h+var_E8], r14d; dwFlags
0x180023a75  lea     rax, [rbp+57h+pcbResult]
0x180023a79  mov     qword ptr [rsp+110h+dwFlags], rax; pcbResult
0x180023a7e  mov     r9d, [rbp+57h+pcbResult]; cbOutput
0x180023a82  mov     r8, rsi; pbOutput
0x180023a85  lea     rdx, pszProperty; "SmartCardKeyCertificate"
0x180023a8c  mov     rcx, [rbp+57h+phKey]; hObject
0x180023a90  call    cs:__imp_NCryptGetProperty
0x180023a96  mov     ebx, eax
0x180023a98  test    eax, eax
0x180023a9a  jns     short loc_180023AC1
0x180023a9c  lea     rcx, base
0x180023aa3  mov     [rsp+110h+var_D0], rcx
0x180023aa8  lea     rcx, aHresult; "HRESULT"
0x180023aaf  mov     [rsp+110h+var_D8], rcx
0x180023ab4  mov     [rsp+110h+var_E0], 327h
0x180023abc  jmp     loc_1800238EE
0x180023ac1  mov     r8d, [rbp+57h+pcbResult]; cbCertEncoded
0x180023ac5  mov     rdx, rsi; pbCertEncoded
0x180023ac8  mov     ecx, 10001h; dwCertEncodingType
0x180023acd  call    cs:__imp_CertCreateCertificateContext
0x180023ad3  mov     [rdi+8], rax
0x180023ad7  test    rax, rax
0x180023ada  jnz     short loc_180023B1A
0x180023adc  call    cs:__imp_GetLastError
0x180023ae2  mov     ebx, eax
0x180023ae4  test    eax, eax
0x180023ae6  jle     short loc_180023AF1
0x180023ae8  movzx   ebx, ax
0x180023aeb  or      ebx, 80070000h
0x180023af1  test    ebx, ebx
0x180023af3  jns     short loc_180023B1A
0x180023af5  lea     rcx, base
0x180023afc  mov     [rsp+110h+var_D0], rcx
0x180023b01  lea     rcx, aHresult; "HRESULT"
0x180023b08  mov     [rsp+110h+var_D8], rcx
0x180023b0d  mov     [rsp+110h+var_E0], 32Dh
0x180023b15  jmp     loc_1800238EE
0x180023b1a  mov     rax, [rdi+8]
0x180023b1e  mov     rdx, [rax+18h]
0x180023b22  lea     r8, [rdx+50h]; pCertName2
0x180023b26  add     rdx, 30h ; '0'; pCertName1
0x180023b2a  mov     ecx, 1; dwCertEncodingType
0x180023b2f  call    cs:__imp_CertCompareCertificateName
0x180023b35  test    eax, eax
0x180023b37  jz      short loc_180023B66
0x180023b39  mov     eax, 0C00000BBh
0x180023b3e  mov     [rbp+57h+var_C0], eax
0x180023b41  lea     rcx, base
0x180023b48  mov     [rsp+110h+var_D0], rcx
0x180023b4d  lea     rcx, aNtstatus; "NTSTATUS"
0x180023b54  mov     [rsp+110h+var_D8], rcx
0x180023b59  mov     [rsp+110h+var_E0], 334h
0x180023b61  jmp     loc_180023957
0x180023b66  mov     [rsp+110h+dwFlags], r14d; dwFlags
0x180023b6b  mov     r9d, 8; cbInput
0x180023b71  lea     r8, [rbp+57h+pbInput]; pbInput
0x180023b75  lea     rdx, aNgcauthticket; "NgcAuthTicket"
0x180023b7c  mov     rcx, [rbp+57h+phKey]; hObject
0x180023b80  call    cs:__imp_NCryptSetProperty
0x180023b86  mov     [rbp+57h+var_C0], eax
0x180023b89  test    eax, eax
0x180023b8b  jns     short loc_180023BB2
0x180023b8d  lea     rcx, base
0x180023b94  mov     [rsp+110h+var_D0], rcx
0x180023b99  lea     rcx, aNtstatus; "NTSTATUS"
0x180023ba0  mov     [rsp+110h+var_D8], rcx
0x180023ba5  mov     [rsp+110h+var_E0], 33Dh
0x180023bad  jmp     loc_180023957
0x180023bb2  mov     dword ptr [rbp+57h+pvData], 18h
0x180023bb9  mov     rax, [rbp+57h+phKey]
0x180023bbd  mov     qword ptr [rbp+57h+pvData+8], rax
0x180023bc1  mov     dword ptr [rbp+57h+var_38], 0FFFFFFFFh
0x180023bc8  lea     r9, [rbp+57h+pvData]; pvData
0x180023bcc  xor     r8d, r8d; dwFlags
0x180023bcf  lea     edx, [r8+5]; dwPropId
0x180023bd3  mov     rcx, [rdi+8]; pCertContext
0x180023bd7  call    cs:__imp_CertSetCertificateContextProperty
0x180023bdd  test    eax, eax
0x180023bdf  jnz     short loc_180023C2D
0x180023be1  call    cs:__imp_GetLastError
0x180023be7  test    eax, eax
0x180023be9  jg      short loc_180023BF3
0x180023beb  call    cs:__imp_GetLastError
0x180023bf1  jmp     short loc_180023C01
0x180023bf3  call    cs:__imp_GetLastError
0x180023bf9  movzx   eax, ax
0x180023bfc  or      eax, 0C0070000h
0x180023c01  mov     [rbp+57h+var_C0], eax
0x180023c04  test    eax, eax
0x180023c06  jns     short loc_180023C2D
0x180023c08  lea     rcx, base
0x180023c0f  mov     [rsp+110h+var_D0], rcx
0x180023c14  lea     rcx, aNtstatus; "NTSTATUS"
0x180023c1b  mov     [rsp+110h+var_D8], rcx
0x180023c20  mov     [rsp+110h+var_E0], 34Ch
0x180023c28  jmp     loc_180023957
0x180023c2d  mov     [rbp+57h+phKey], r14
0x180023c31  mov     rcx, [rbp+57h+pszKeyName]; hMem
0x180023c35  call    cs:__imp_LocalFree
0x180023c3b  mov     rcx, [rbp+57h+hMem]; hMem
0x180023c3f  call    cs:__imp_LocalFree
0x180023c45  mov     rcx, [rbp+57h+phKey]; hObject
0x180023c49  test    rcx, rcx
0x180023c4c  jz      short loc_180023C54
0x180023c4e  call    cs:__imp_NCryptFreeObject
0x180023c54  mov     ebx, [rbp+57h+var_C0]
0x180023c57  test    ebx, ebx
0x180023c59  jns     short loc_180023C66
0x180023c5b  mov     rcx, rdi; this
0x180023c5e  call    ?Free@PinCacheData@@QEAAXXZ; PinCacheData::Free(void)
0x180023c63  mov     ebx, [rbp+57h+var_C0]
0x180023c66  lea     rcx, [rbp+57h+var_78]
0x180023c6a  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x180023c6f  nop
0x180023c70  lea     rcx, [rbp+57h+var_98]
0x180023c74  call    ?Clear@?$Auto@PEAGV?$LocalAllocFunctor@PEAG@@VAadContextFunctions@@@@QEAAXXZ; Auto<ushort *,LocalAllocFunctor<ushort *>,AadContextFunctions>::Clear(void)
0x180023c79  nop
0x180023c7a  mov     eax, ebx
0x180023c7c  mov     rcx, [rbp+57h+var_30]
0x180023c80  xor     rcx, rsp; StackCookie
0x180023c83  call    __security_check_cookie
0x180023c88  mov     rbx, [rsp+110h+arg_18]
0x180023c90  add     rsp, 0F0h
0x180023c97  pop     r15
0x180023c99  pop     r14
0x180023c9b  pop     rdi
0x180023c9c  pop     rsi
0x180023c9d  pop     rbp
0x180023c9e  retn
```
