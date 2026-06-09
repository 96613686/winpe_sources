# IsSignedWith2023PCA(ushort const *,int *)

- ea: `0x180038d00`
- end: `0x180039059`
- name: `?IsSignedWith2023PCA@@YAJPEBGPEAH@Z`
- size: `857`
- prototype: `__int64 __fastcall(const unsigned __int16 *pvObject, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180037a04`

## callees

- `0x1800078b0`
- `0x1800085b0`
- `0x180038d00`
- `0x1800394b0`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038fab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038fab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038e72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f9d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038e72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f9d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038e80`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038e0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038f7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fcf`
- `CRYPT32!CryptMsgGetParam` at `0x180038e03`
- `CRYPT32!CryptMsgGetParam` at `0x180038e61`
- `CRYPT32!CryptMsgGetParam` at `0x180038eaa`
- `CRYPT32!CryptMsgGetParam` at `0x180038e03`
- `CRYPT32!CryptMsgGetParam` at `0x180038e61`
- `CRYPT32!CryptMsgGetParam` at `0x180038eaa`
- `CRYPT32!CertCloseStore` at `0x180038ff6`
- `CRYPT32!CertCloseStore` at `0x180038ff6`
- `CRYPT32!CryptQueryObject` at `0x180038dc0`
- `CRYPT32!CryptQueryObject` at `0x180038dc0`
- `CRYPT32!CertFreeCertificateContext` at `0x180038f21`
- `CRYPT32!CertFreeCertificateContext` at `0x180038fb9`
- `CRYPT32!CertFreeCertificateContext` at `0x180038f21`
- `CRYPT32!CertFreeCertificateContext` at `0x180038fb9`
- `CRYPT32!CryptMsgClose` at `0x180039005`
- `CRYPT32!CryptMsgClose` at `0x180039005`
- `CRYPT32!CertCreateCertificateContext` at `0x180038ec4`
- `CRYPT32!CertCreateCertificateContext` at `0x180038ec4`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180038ee6`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180038ee6`

## string_xrefs

- `0x180038f76`: `CertCreateCertificateContext`

## pseudocode

```c
__int64 __fastcall IsSignedWith2023PCA(const unsigned __int16 *pvObject, int *a2)
{
  signed int v3; // eax
  unsigned int v4; // edi
  const unsigned __int16 *v5; // rsi
  signed int v6; // eax
  DWORD v7; // r14d
  DWORD v8; // ebx
  HANDLE ProcessHeap; // rax
  void *v10; // r15
  const CERT_CONTEXT *CertificateContext; // rax
  const CERT_CONTEXT *v12; // rbx
  HANDLE v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  signed int LastError; // eax
  HANDLE v17; // rax
  signed int v18; // eax
  DWORD cbCertEncoded; // [rsp+60h] [rbp-19h] BYREF
  DWORD pvData; // [rsp+64h] [rbp-15h] BYREF
  HCRYPTMSG hCryptMsg; // [rsp+68h] [rbp-11h] BYREF
  DWORD pdwFormatType; // [rsp+70h] [rbp-9h] BYREF
  DWORD pdwContentType; // [rsp+74h] [rbp-5h] BYREF
  DWORD pdwMsgAndCertEncodingType; // [rsp+78h] [rbp-1h] BYREF
  DWORD pcbData; // [rsp+7Ch] [rbp+3h] BYREF
  DWORD v27; // [rsp+80h] [rbp+7h] BYREF
  HCERTSTORE hCertStore; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE Buf1[24]; // [rsp+90h] [rbp+17h] BYREF

  *a2 = 0;
  pdwMsgAndCertEncodingType = 0;
  pdwContentType = 0;
  pdwFormatType = 0;
  hCertStore = 0;
  hCryptMsg = 0;
  pcbData = 4;
  pvData = 0;
  cbCertEncoded = 0;
  if ( CryptQueryObject(
         1u,
         pvObject,
         0x400u,
         2u,
         0,
         &pdwMsgAndCertEncodingType,
         &pdwContentType,
         &pdwFormatType,
         &hCertStore,
         &hCryptMsg,
         0) )
  {
    if ( CryptMsgGetParam(hCryptMsg, 0xBu, 0, &pvData, &pcbData) )
    {
      v4 = 0;
      v5 = L"Passed";
      v7 = 0;
      if ( pvData )
      {
        while ( 1 )
        {
          v27 = 20;
          if ( !CryptMsgGetParam(hCryptMsg, 0xCu, v7, 0, &cbCertEncoded) )
            break;
          v8 = cbCertEncoded;
          ProcessHeap = GetProcessHeap();
          v10 = HeapAlloc(ProcessHeap, 0, v8);
          if ( !v10 )
          {
            v4 = -2147024882;
            v5 = L"CertMemoryAllocFailed";
            goto LABEL_34;
          }
          if ( !CryptMsgGetParam(hCryptMsg, 0xCu, v7, v10, &cbCertEncoded) )
          {
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            v5 = L"CryptMsgGetParamGetCert";
            v12 = 0;
            goto LABEL_28;
          }
          CertificateContext = CertCreateCertificateContext(1u, (const BYTE *)v10, cbCertEncoded);
          v12 = CertificateContext;
          if ( !CertificateContext )
          {
            v15 = GetLastError();
            v4 = v15;
            if ( v15 > 0 )
              v4 = (unsigned __int16)v15 | 0x80070000;
            v5 = L"CertCreateCertificateContext";
            goto LABEL_28;
          }
          if ( !CertGetCertificateContextProperty(CertificateContext, 3u, Buf1, &v27) )
          {
            v14 = GetLastError();
            v4 = v14;
            if ( v14 > 0 )
              v4 = (unsigned __int16)v14 | 0x80070000;
            v5 = L"CertGetCertificateContextPropertyGetHashProperty";
            goto LABEL_28;
          }
          if ( !memcmp_0(Buf1, qword_1800757D0, 0x14u) )
          {
            *a2 = 1;
LABEL_28:
            v17 = GetProcessHeap();
            HeapFree(v17, 0, v10);
            if ( v12 )
              CertFreeCertificateContext(v12);
            goto LABEL_34;
          }
          v13 = GetProcessHeap();
          HeapFree(v13, 0, v10);
          CertFreeCertificateContext(v12);
          if ( ++v7 >= pvData )
            goto LABEL_34;
        }
        v18 = GetLastError();
        v4 = v18;
        if ( v18 > 0 )
          v4 = (unsigned __int16)v18 | 0x80070000;
        v5 = L"CryptMsgGetParamCertSize";
      }
    }
    else
    {
      v6 = GetLastError();
      v4 = v6;
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
      v5 = L"CryptMsgGetParamCertCount";
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v5 = L"CryptQueryObject";
  }
LABEL_34:
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( hCryptMsg )
    CryptMsgClose(hCryptMsg);
  if ( (v4 & 0x80000000) != 0 )
  {
    SBServicingLogMessage((wchar_t *)L"IsSignedWith2023PCA failed with error %x actionString %ls", v4, v5);
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"IsSignedWith2023PCA", v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180038d00  mov     [rsp-8+arg_10], rbx
0x180038d05  mov     [rsp-8+arg_18], rsi
0x180038d0a  push    rbp
0x180038d0b  push    rdi
0x180038d0c  push    r12
0x180038d0e  push    r14
0x180038d10  push    r15
0x180038d12  lea     rbp, [rsp-37h]
0x180038d17  sub     rsp, 0B0h
0x180038d1e  mov     rax, cs:__security_cookie
0x180038d25  xor     rax, rsp
0x180038d28  mov     [rbp+57h+var_28], rax
0x180038d2c  mov     [rsp+0D0h+ppvContext], 0; ppvContext
0x180038d35  lea     rax, [rbp+57h+hCryptMsg]
0x180038d39  mov     [rsp+0D0h+phMsg], rax; phMsg
0x180038d3e  mov     r9d, 2; dwExpectedFormatTypeFlags
0x180038d44  lea     rax, [rbp+57h+hCertStore]
0x180038d48  mov     dword ptr [rdx], 0
0x180038d4e  mov     [rsp+0D0h+phCertStore], rax; phCertStore
0x180038d53  mov     r12, rdx
0x180038d56  lea     rax, [rbp+57h+var_60]
0x180038d5a  mov     [rbp+57h+var_58], 0
0x180038d61  mov     [rsp+0D0h+pdwFormatType], rax; pdwFormatType
0x180038d66  mov     rdx, rcx; pvObject
0x180038d69  lea     rax, [rbp+57h+var_5C]
0x180038d6d  mov     [rbp+57h+var_5C], 0
0x180038d74  mov     [rsp+0D0h+pdwContentType], rax; pdwContentType
0x180038d79  lea     ecx, [r9-1]; dwObjectType
0x180038d7d  lea     rax, [rbp+57h+var_58]
0x180038d81  mov     [rbp+57h+var_60], 0
0x180038d88  mov     [rsp+0D0h+pdwMsgAndCertEncodingType], rax; pdwMsgAndCertEncodingType
0x180038d8d  mov     r8d, 400h; dwExpectedContentTypeFlags
0x180038d93  mov     [rsp+0D0h+dwFlags], 0; dwFlags
0x180038d9b  mov     [rbp+57h+hCertStore], 0
0x180038da3  mov     [rbp+57h+hCryptMsg], 0
0x180038dab  mov     [rbp+57h+pcbData], 4
0x180038db2  mov     [rbp+57h+pvData], 0
0x180038db9  mov     [rbp+57h+cbCertEncoded], 0
0x180038dc0  call    cs:__imp_CryptQueryObject
0x180038dc6  test    eax, eax
0x180038dc8  jnz     short loc_180038DEB
0x180038dca  call    cs:__imp_GetLastError
0x180038dd0  mov     edi, eax
0x180038dd2  test    eax, eax
0x180038dd4  jle     short loc_180038DDF
0x180038dd6  movzx   edi, ax
0x180038dd9  or      edi, 80070000h
0x180038ddf  lea     rsi, aCryptqueryobje_0; "CryptQueryObject"
0x180038de6  jmp     loc_180038FEB
0x180038deb  mov     rcx, [rbp+57h+hCryptMsg]; hCryptMsg
0x180038def  lea     rax, [rbp+57h+pcbData]
0x180038df3  xor     r8d, r8d; dwIndex
0x180038df6  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbData
0x180038dfb  lea     r9, [rbp+57h+pvData]; pvData
0x180038dff  lea     edx, [r8+0Bh]; dwParamType
0x180038e03  call    cs:__imp_CryptMsgGetParam
0x180038e09  test    eax, eax
0x180038e0b  jnz     short loc_180038E2E
0x180038e0d  call    cs:__imp_GetLastError
0x180038e13  mov     edi, eax
0x180038e15  test    eax, eax
0x180038e17  jle     short loc_180038E22
0x180038e19  movzx   edi, ax
0x180038e1c  or      edi, 80070000h
0x180038e22  lea     rsi, aCryptmsggetpar_2; "CryptMsgGetParamCertCount"
0x180038e29  jmp     loc_180038FEB
0x180038e2e  xor     edi, edi
0x180038e30  lea     rsi, aPassed; "Passed"
0x180038e37  xor     r14d, r14d
0x180038e3a  cmp     [rbp+57h+pvData], edi
0x180038e3d  jbe     loc_180038FEB
0x180038e43  mov     rcx, [rbp+57h+hCryptMsg]; hCryptMsg
0x180038e47  lea     rax, [rbp+57h+cbCertEncoded]
0x180038e4b  xor     r9d, r9d; pvData
0x180038e4e  mov     [rbp+57h+var_50], 14h
0x180038e55  mov     r8d, r14d; dwIndex
0x180038e58  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbData
0x180038e5d  lea     edx, [r9+0Ch]; dwParamType
0x180038e61  call    cs:__imp_CryptMsgGetParam
0x180038e67  test    eax, eax
0x180038e69  jz      loc_180038FCF
0x180038e6f  mov     ebx, [rbp+57h+cbCertEncoded]
0x180038e72  call    cs:__imp_GetProcessHeap
0x180038e78  mov     r8d, ebx; dwBytes
0x180038e7b  xor     edx, edx; dwFlags
0x180038e7d  mov     rcx, rax; hHeap
0x180038e80  call    cs:__imp_HeapAlloc
0x180038e86  mov     r15, rax
0x180038e89  test    rax, rax
0x180038e8c  jz      loc_180038FC1
0x180038e92  mov     rcx, [rbp+57h+hCryptMsg]; hCryptMsg
0x180038e96  lea     rax, [rbp+57h+cbCertEncoded]
0x180038e9a  mov     r9, r15; pvData
0x180038e9d  mov     qword ptr [rsp+0D0h+dwFlags], rax; pcbData
0x180038ea2  mov     r8d, r14d; dwIndex
0x180038ea5  mov     edx, 0Ch; dwParamType
0x180038eaa  call    cs:__imp_CryptMsgGetParam
0x180038eb0  test    eax, eax
0x180038eb2  jz      loc_180038F7F
0x180038eb8  mov     r8d, [rbp+57h+cbCertEncoded]; cbCertEncoded
0x180038ebc  mov     rdx, r15; pbCertEncoded
0x180038ebf  mov     ecx, 1; dwCertEncodingType
0x180038ec4  call    cs:__imp_CertCreateCertificateContext
0x180038eca  mov     rbx, rax
0x180038ecd  test    rax, rax
0x180038ed0  jz      loc_180038F61
0x180038ed6  lea     r9, [rbp+57h+var_50]; pcbData
0x180038eda  mov     edx, 3; dwPropId
0x180038edf  lea     r8, [rbp+57h+Buf1]; pvData
0x180038ee3  mov     rcx, rax; pCertContext
0x180038ee6  call    cs:__imp_CertGetCertificateContextProperty
0x180038eec  test    eax, eax
0x180038eee  jz      short loc_180038F43
0x180038ef0  mov     r8d, 14h; Size
0x180038ef6  lea     rdx, qword_1800757D0; Buf2
0x180038efd  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180038f01  call    memcmp_0
0x180038f06  test    eax, eax
0x180038f08  jz      short loc_180038F39
0x180038f0a  call    cs:__imp_GetProcessHeap
0x180038f10  mov     r8, r15; lpMem
0x180038f13  xor     edx, edx; dwFlags
0x180038f15  mov     rcx, rax; hHeap
0x180038f18  call    cs:__imp_HeapFree
0x180038f1e  mov     rcx, rbx; pCertContext
0x180038f21  call    cs:__imp_CertFreeCertificateContext
0x180038f27  inc     r14d
0x180038f2a  cmp     r14d, [rbp+57h+pvData]
0x180038f2e  jb      loc_180038E43
0x180038f34  jmp     loc_180038FEB
0x180038f39  mov     dword ptr [r12], 1
0x180038f41  jmp     short loc_180038F9D
0x180038f43  call    cs:__imp_GetLastError
0x180038f49  mov     edi, eax
0x180038f4b  test    eax, eax
0x180038f4d  jle     short loc_180038F58
0x180038f4f  movzx   edi, ax
0x180038f52  or      edi, 80070000h
0x180038f58  lea     rsi, aCertgetcertifi_0; "CertGetCertificateContextPropertyGetHas"...
0x180038f5f  jmp     short loc_180038F9D
0x180038f61  call    cs:__imp_GetLastError
0x180038f67  mov     edi, eax
0x180038f69  test    eax, eax
0x180038f6b  jle     short loc_180038F76
0x180038f6d  movzx   edi, ax
0x180038f70  or      edi, 80070000h
0x180038f76  lea     rsi, aCertcreatecert_0; "CertCreateCertificateContext"
0x180038f7d  jmp     short loc_180038F9D
0x180038f7f  call    cs:__imp_GetLastError
0x180038f85  mov     edi, eax
0x180038f87  test    eax, eax
0x180038f89  jle     short loc_180038F94
0x180038f8b  movzx   edi, ax
0x180038f8e  or      edi, 80070000h
0x180038f94  lea     rsi, aCryptmsggetpar_0; "CryptMsgGetParamGetCert"
0x180038f9b  xor     ebx, ebx
0x180038f9d  call    cs:__imp_GetProcessHeap
0x180038fa3  mov     r8, r15; lpMem
0x180038fa6  xor     edx, edx; dwFlags
0x180038fa8  mov     rcx, rax; hHeap
0x180038fab  call    cs:__imp_HeapFree
0x180038fb1  test    rbx, rbx
0x180038fb4  jz      short loc_180038FEB
0x180038fb6  mov     rcx, rbx; pCertContext
0x180038fb9  call    cs:__imp_CertFreeCertificateContext
0x180038fbf  jmp     short loc_180038FEB
0x180038fc1  mov     edi, 8007000Eh
0x180038fc6  lea     rsi, aCertmemoryallo; "CertMemoryAllocFailed"
0x180038fcd  jmp     short loc_180038FEB
0x180038fcf  call    cs:__imp_GetLastError
0x180038fd5  mov     edi, eax
0x180038fd7  test    eax, eax
0x180038fd9  jle     short loc_180038FE4
0x180038fdb  movzx   edi, ax
0x180038fde  or      edi, 80070000h
0x180038fe4  lea     rsi, aCryptmsggetpar_1; "CryptMsgGetParamCertSize"
0x180038feb  mov     rcx, [rbp+57h+hCertStore]; hCertStore
0x180038fef  test    rcx, rcx
0x180038ff2  jz      short loc_180038FFC
0x180038ff4  xor     edx, edx; dwFlags
0x180038ff6  call    cs:__imp_CertCloseStore
0x180038ffc  mov     rcx, [rbp+57h+hCryptMsg]; hCryptMsg
0x180039000  test    rcx, rcx
0x180039003  jz      short loc_18003900B
0x180039005  call    cs:__imp_CryptMsgClose
0x18003900b  test    edi, edi
0x18003900d  jns     short loc_18003902F
0x18003900f  mov     r8, rsi
0x180039012  lea     rcx, aIssignedwith20_0; "IsSignedWith2023PCA failed with error %"...
0x180039019  mov     edx, edi
0x18003901b  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180039020  mov     rdx, rsi; unsigned __int16 *
0x180039023  lea     rcx, aIssignedwith20_1; "IsSignedWith2023PCA"
0x18003902a  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x18003902f  mov     eax, edi
0x180039031  mov     rcx, [rbp+57h+var_28]
0x180039035  xor     rcx, rsp; StackCookie
0x180039038  call    __security_check_cookie
0x18003903d  lea     r11, [rsp+0D0h+var_20]
0x180039045  mov     rbx, [r11+40h]
0x180039049  mov     rsi, [r11+48h]
0x18003904d  mov     rsp, r11
0x180039050  pop     r15
0x180039052  pop     r14
0x180039054  pop     r12
0x180039056  pop     rdi
0x180039057  pop     rbp
0x180039058  retn
```
