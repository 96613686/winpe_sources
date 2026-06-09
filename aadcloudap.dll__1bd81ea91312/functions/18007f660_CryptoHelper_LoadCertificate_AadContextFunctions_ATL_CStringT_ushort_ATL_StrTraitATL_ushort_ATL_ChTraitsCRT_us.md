# CryptoHelper::LoadCertificate(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_CERT_CONTEXT const * *)

- ea: `0x18007f660`
- end: `0x18007f80b`
- name: `?LoadCertificate@CryptoHelper@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `427`
- prototype: `__int64 __fastcall(AadContextFunctions *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002a9a8`
- `0x18002bf70`
- `0x180031f04`

## callees

- `0x1800069c0`
- `0x180006ac4`
- `0x180007a90`
- `0x180071e14`
- `0x180076758`
- `0x18007f660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007f752`
- `CRYPT32!CertCreateCertificateContext` at `0x18007f740`
- `CRYPT32!CertCreateCertificateContext` at `0x18007f740`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CryptoHelper::LoadCertificate(AadContextFunctions *this, _QWORD *a2, PCCERT_CONTEXT *a3)
{
  __int64 v6; // r9
  signed int LastError; // eax
  PCCERT_CONTEXT CertificateContext; // rax
  unsigned int v9; // ebx
  signed int v11; // [rsp+20h] [rbp-29h]
  int v12; // [rsp+20h] [rbp-29h]
  int v13; // [rsp+30h] [rbp-19h]
  int v14; // [rsp+30h] [rbp-19h]
  BYTE *pbCertEncoded[2]; // [rsp+50h] [rbp+7h] BYREF
  const char *v16[6]; // [rsp+60h] [rbp+17h] BYREF
  int v17; // [rsp+B0h] [rbp+67h] BYREF

  v17 = 0;
  *(_OWORD *)pbCertEncoded = 0;
  DbgTracePrintHelper<unsigned long>::DbgTracePrintHelper<unsigned long>(
    (__int64)v16,
    (int)"crypto.cpp",
    (int)"CryptoHelper::LoadCertificate",
    (int)&v17);
  if ( this && a3 && *(_DWORD *)(*a2 - 16LL) )
  {
    *a3 = 0;
    LOBYTE(v6) = 1;
    LastError = StringUtility::Base64UrlDecode(this, a2, pbCertEncoded, v6);
    v17 = LastError;
    if ( LastError >= 0 )
    {
      CertificateContext = CertCreateCertificateContext(0x10001u, pbCertEncoded[1], (DWORD)pbCertEncoded[0]);
      *a3 = CertificateContext;
      if ( CertificateContext )
        goto LABEL_13;
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v17 = LastError;
      if ( LastError >= 0 )
        goto LABEL_13;
      v13 = 985;
    }
    else
    {
      v13 = 975;
    }
    v11 = LastError;
    WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v11, "crypto.cpp", v13, "HRESULT", &base);
LABEL_13:
    AadContextFunctions::LocalFreeApBlob(this, (struct _AP_BLOB *)pbCertEncoded);
    goto LABEL_14;
  }
  v17 = -2147024809;
  v14 = 969;
  v12 = -2147024809;
  WPPTraceLogA(2, 0, "%x 0x%08x %s:%u : %s:%ws", 2, v12, "crypto.cpp", v14, "HRESULT", &base);
  if ( this )
    goto LABEL_13;
LABEL_14:
  v9 = v17;
  DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(v16);
  return v9;
}

```

## disassembly

```asm
0x18007f660  mov     [rsp-8+arg_8], rbx
0x18007f665  mov     [rsp-8+arg_10], rsi
0x18007f66a  push    rbp
0x18007f66b  push    rdi
0x18007f66c  push    r15
0x18007f66e  lea     rbp, [rsp-47h]
0x18007f673  sub     rsp, 90h
0x18007f67a  mov     rbx, r8
0x18007f67d  mov     rsi, rdx
0x18007f680  mov     rdi, rcx
0x18007f683  mov     [rbp+57h+arg_0], 0
0x18007f68a  xorps   xmm0, xmm0
0x18007f68d  movups  xmmword ptr [rbp+57h+pbCertEncoded], xmm0
0x18007f691  lea     r9, [rbp+57h+arg_0]
0x18007f695  lea     r8, aCryptohelperLo; "CryptoHelper::LoadCertificate"
0x18007f69c  lea     r15, aOnecoreuapDsEx_0+20h; "crypto.cpp"
0x18007f6a3  mov     rdx, r15
0x18007f6a6  lea     rcx, [rbp+57h+var_40]
0x18007f6aa  call    ??0?$DbgTracePrintHelper@K@@QEAA@PEBD0AEAKW4AadTracingEventType@@@Z; DbgTracePrintHelper<ulong>::DbgTracePrintHelper<ulong>(char const *,char const *,ulong &,AadTracingEventType)
0x18007f6af  nop
0x18007f6b0  test    rdi, rdi
0x18007f6b3  jz      loc_18007F78D
0x18007f6b9  test    rbx, rbx
0x18007f6bc  jz      loc_18007F78D
0x18007f6c2  mov     rax, [rsi]
0x18007f6c5  cmp     dword ptr [rax-10h], 0
0x18007f6c9  jz      loc_18007F78D
0x18007f6cf  mov     qword ptr [rbx], 0
0x18007f6d6  mov     r9b, 1
0x18007f6d9  lea     r8, [rbp+57h+pbCertEncoded]
0x18007f6dd  mov     rdx, rsi
0x18007f6e0  mov     rcx, rdi
0x18007f6e3  call    ?Base64UrlDecode@StringUtility@@SAJPEAVAadContextFunctions@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAU_AP_BLOB@@_N@Z; StringUtility::Base64UrlDecode(AadContextFunctions *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,_AP_BLOB *,bool)
0x18007f6e8  mov     [rbp+57h+arg_0], eax
0x18007f6eb  test    eax, eax
0x18007f6ed  jns     short loc_18007F733
0x18007f6ef  lea     rcx, base
0x18007f6f6  mov     [rsp+0A0h+var_60], rcx
0x18007f6fb  lea     rcx, aHresult; "HRESULT"
0x18007f702  mov     [rsp+0A0h+var_68], rcx
0x18007f707  mov     [rsp+0A0h+var_70], 3CFh
0x18007f70f  mov     [rsp+0A0h+var_78], r15
0x18007f714  mov     [rsp+0A0h+var_80], eax
0x18007f718  mov     ecx, 2
0x18007f71d  mov     r9d, ecx
0x18007f720  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007f727  xor     edx, edx
0x18007f729  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007f72e  jmp     loc_18007F7D9
0x18007f733  mov     r8d, dword ptr [rbp+57h+pbCertEncoded]; cbCertEncoded
0x18007f737  mov     rdx, [rbp+57h+pbCertEncoded+8]; pbCertEncoded
0x18007f73b  mov     ecx, 10001h; dwCertEncodingType
0x18007f740  call    cs:__imp_CertCreateCertificateContext
0x18007f746  mov     [rbx], rax
0x18007f749  test    rax, rax
0x18007f74c  jnz     loc_18007F7D9
0x18007f752  call    cs:__imp_GetLastError
0x18007f758  test    eax, eax
0x18007f75a  jle     short loc_18007F764
0x18007f75c  movzx   eax, ax
0x18007f75f  or      eax, 80070000h
0x18007f764  mov     [rbp+57h+arg_0], eax
0x18007f767  test    eax, eax
0x18007f769  jns     short loc_18007F7D9
0x18007f76b  lea     rcx, base
0x18007f772  mov     [rsp+0A0h+var_60], rcx
0x18007f777  lea     rcx, aHresult; "HRESULT"
0x18007f77e  mov     [rsp+0A0h+var_68], rcx
0x18007f783  mov     [rsp+0A0h+var_70], 3D9h
0x18007f78b  jmp     short loc_18007F70F
0x18007f78d  mov     eax, 80070057h
0x18007f792  mov     [rbp+57h+arg_0], eax
0x18007f795  lea     rcx, base
0x18007f79c  mov     [rsp+0A0h+var_60], rcx
0x18007f7a1  lea     rcx, aHresult; "HRESULT"
0x18007f7a8  mov     [rsp+0A0h+var_68], rcx
0x18007f7ad  mov     [rsp+0A0h+var_70], 3C9h
0x18007f7b5  mov     [rsp+0A0h+var_78], r15
0x18007f7ba  mov     [rsp+0A0h+var_80], eax
0x18007f7be  mov     ecx, 2
0x18007f7c3  mov     r9d, ecx
0x18007f7c6  lea     r8, aX0x08xSUSWs; "%x 0x%08x %s:%u : %s:%ws"
0x18007f7cd  xor     edx, edx
0x18007f7cf  call    ?WPPTraceLogA@@YAXKW4AadTracingEventType@@PEBDZZ; WPPTraceLogA(ulong,AadTracingEventType,char const *,...)
0x18007f7d4  test    rdi, rdi
0x18007f7d7  jz      short loc_18007F7E5
0x18007f7d9  lea     rdx, [rbp+57h+pbCertEncoded]; struct _AP_BLOB *
0x18007f7dd  mov     rcx, rdi; this
0x18007f7e0  call    ?LocalFreeApBlob@AadContextFunctions@@QEAAXPEAU_AP_BLOB@@@Z; AadContextFunctions::LocalFreeApBlob(_AP_BLOB *)
0x18007f7e5  mov     ebx, [rbp+57h+arg_0]
0x18007f7e8  lea     rcx, [rbp+57h+var_40]
0x18007f7ec  call    ??1?$DbgTracePrintHelper@J@@QEAA@XZ; DbgTracePrintHelper<long>::~DbgTracePrintHelper<long>(void)
0x18007f7f1  mov     eax, ebx
0x18007f7f3  lea     r11, [rsp+0A0h+var_10]
0x18007f7fb  mov     rbx, [r11+28h]
0x18007f7ff  mov     rsi, [r11+30h]
0x18007f803  mov     rsp, r11
0x18007f806  pop     r15
0x18007f808  pop     rdi
0x18007f809  pop     rbp
0x18007f80a  retn
```
