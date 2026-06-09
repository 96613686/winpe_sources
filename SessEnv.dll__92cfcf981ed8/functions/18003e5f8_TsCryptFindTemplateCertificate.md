# TsCryptFindTemplateCertificate

- ea: `0x18003e5f8`
- end: `0x18003e875`
- name: `TsCryptFindTemplateCertificate`
- size: `637`
- prototype: `__int64 __fastcall(int, int, int, int, void *pvData, DWORD *pcbData)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003860`

## callees

- `0x18003e5f8`
- `0x18003e87c`
- `0x18003e8cc`
- `0x18003f1f4`
- `0x18003f668`
- `0x18003f834`
- `0x18003f91c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e820`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e68e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e820`
- `CRYPT32!CertFreeCertificateContext` at `0x18003e818`
- `CRYPT32!CertFreeCertificateContext` at `0x18003e818`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18003e7e9`
- `CRYPT32!CertGetCertificateContextProperty` at `0x18003e7e9`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003e6c4`
- `CRYPT32!CertEnumCertificatesInStore` at `0x18003e6c4`
- `CRYPT32!CertCloseStore` at `0x18003e857`
- `CRYPT32!CertCloseStore` at `0x18003e857`
- `CRYPT32!CertOpenStore` at `0x18003e680`
- `CRYPT32!CertOpenStore` at `0x18003e680`

## pseudocode

```c
__int64 __fastcall TsCryptFindTemplateCertificate(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        void *pvData,
        DWORD *pcbData)
{
  DWORD *v6; // r14
  CERT_CONTEXT *v7; // rdi
  __int64 v8; // rbx
  HCERTSTORE v9; // r12
  signed int v10; // eax
  signed int IsTemplateCertificate; // ebx
  unsigned int v12; // r13d
  int v13; // esi
  PCCERT_CONTEXT v14; // rax
  unsigned int v15; // ebx
  void *v16; // r8
  signed int LastError; // eax
  signed int v18; // eax
  int v20; // [rsp+30h] [rbp-20h] BYREF
  int v21; // [rsp+34h] [rbp-1Ch] BYREF
  unsigned int v22; // [rsp+38h] [rbp-18h] BYREF
  DWORD v23; // [rsp+3Ch] [rbp-14h]
  _QWORD v24[2]; // [rsp+40h] [rbp-10h] BYREF
  int v28; // [rsp+A8h] [rbp+58h] BYREF

  v6 = pcbData;
  v7 = 0;
  v24[0] = "1.3.6.1.5.5.7.3.1";
  v22 = 0;
  v24[1] = "1.3.6.1.4.1.311.54.1.2";
  v8 = a2;
  v20 = 0;
  v28 = 0;
  v21 = 0;
  if ( pcbData && pvData )
  {
    v23 = *pcbData;
    *pcbData = 0;
    v9 = CertOpenStore("System", 0, 0, 0x24000u, L"MY");
    if ( v9 )
    {
      v12 = 0;
      v13 = 0;
      while ( 1 )
      {
        LODWORD(pcbData) = 0;
        v14 = CertEnumCertificatesInStore(v9, v7);
        v7 = (CERT_CONTEXT *)v14;
        if ( !v14 )
          break;
        IsTemplateCertificate = TsCryptIsTemplateCertificate((__int64)v14, a1, v8, &pcbData);
        if ( IsTemplateCertificate < 0 )
          goto LABEL_27;
        v8 = a2;
        if ( (_DWORD)pcbData )
        {
          IsTemplateCertificate = TsCryptIsSameSubjectName(v7, a3, &v20);
          if ( IsTemplateCertificate < 0 )
            goto LABEL_27;
          v8 = a2;
          if ( v20 )
          {
            if ( (unsigned int)TsCryptCertContainsMachineKeySet(v7) )
            {
              IsTemplateCertificate = TsCryptCertContainsEnhancedKeyUsage(&v28, v7, v24, 2, 1);
              if ( IsTemplateCertificate < 0 )
                goto LABEL_27;
              if ( v28 )
                goto LABEL_18;
              IsTemplateCertificate = TsCryptCertContainsEnhancedKeyUsage(&v28, v7, 0, 0, 0);
              if ( IsTemplateCertificate < 0 )
                goto LABEL_27;
              v8 = a2;
              if ( v28 )
              {
LABEL_18:
                IsTemplateCertificate = TsCryptGetCertTimeStatus(v7, &v21);
                if ( IsTemplateCertificate < 0 )
                  goto LABEL_27;
                v8 = a2;
                if ( !v21 )
                {
                  IsTemplateCertificate = TsCryptGetDaysTillCertExpiry(v7, &v22);
                  if ( IsTemplateCertificate < 0 )
                    goto LABEL_27;
                  v15 = v22;
                  if ( v22 >= 2 && v22 > v12 )
                  {
                    v16 = pvData;
                    *v6 = v23;
                    if ( !CertGetCertificateContextProperty(v7, 3u, v16, v6) )
                    {
                      LastError = GetLastError();
                      IsTemplateCertificate = LastError;
                      if ( LastError > 0 )
                        IsTemplateCertificate = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
                      CertFreeCertificateContext(v7);
                      goto LABEL_33;
                    }
                    v12 = v15;
                    v13 = 1;
                  }
                  v8 = a2;
                }
              }
            }
          }
        }
      }
      v18 = GetLastError();
      IsTemplateCertificate = v18;
      if ( v18 == -2146885628 || v18 == 18 )
      {
        IsTemplateCertificate = v13 == 0 ? 0x80070002 : 0;
      }
      else if ( v18 > 0 )
      {
        IsTemplateCertificate = (unsigned __int16)v18 | 0x80070000;
      }
LABEL_33:
      CertCloseStore(v9, 1u);
    }
    else
    {
      v10 = GetLastError();
      IsTemplateCertificate = v10;
      if ( v10 > 0 )
        return (unsigned __int16)v10 | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)IsTemplateCertificate;
}

```

## disassembly

```asm
0x18003e5f8  mov     r11, rsp
0x18003e5fb  mov     [r11+20h], r9d
0x18003e5ff  mov     [r11+18h], r8
0x18003e603  mov     [r11+10h], rdx
0x18003e607  mov     [r11+8], rcx
0x18003e60b  push    rbp
0x18003e60c  push    rbx
0x18003e60d  push    rsi
0x18003e60e  push    rdi
0x18003e60f  push    r12
0x18003e611  push    r13
0x18003e613  push    r14
0x18003e615  mov     rbp, rsp
0x18003e618  sub     rsp, 50h
0x18003e61c  mov     r14, [rbp+pcbData]
0x18003e620  lea     rax, a136155731; "1.3.6.1.5.5.7.3.1"
0x18003e627  xor     edi, edi
0x18003e629  mov     [rbp+var_10], rax
0x18003e62d  mov     [rbp+var_18], edi
0x18003e630  lea     rax, a1361413115412; "1.3.6.1.4.1.311.54.1.2"
0x18003e637  mov     [rbp+var_8], rax
0x18003e63b  mov     rbx, rdx
0x18003e63e  mov     [rbp+var_20], edi
0x18003e641  mov     [rbp+arg_18], edi
0x18003e644  mov     [rbp+var_1C], edi
0x18003e647  test    r14, r14
0x18003e64a  jz      loc_18003E85F
0x18003e650  cmp     [rbp+pvData], rdi
0x18003e654  jz      loc_18003E85F
0x18003e65a  mov     eax, [r14]
0x18003e65d  lea     rcx, szStoreProvider; "System"
0x18003e664  mov     [rbp+var_14], eax
0x18003e667  mov     r9d, 24000h; dwFlags
0x18003e66d  lea     rax, aMy_0; "MY"
0x18003e674  mov     [r14], edi
0x18003e677  xor     r8d, r8d; hCryptProv
0x18003e67a  mov     [r11-68h], rax
0x18003e67e  xor     edx, edx; dwEncodingType
0x18003e680  call    cs:__imp_CertOpenStore
0x18003e686  mov     r12, rax
0x18003e689  test    rax, rax
0x18003e68c  jnz     short loc_18003E6AC
0x18003e68e  call    cs:__imp_GetLastError
0x18003e694  mov     ebx, eax
0x18003e696  test    eax, eax
0x18003e698  jle     loc_18003E864
0x18003e69e  movzx   ebx, ax
0x18003e6a1  or      ebx, 80070000h
0x18003e6a7  jmp     loc_18003E864
0x18003e6ac  mov     r13d, edi
0x18003e6af  mov     esi, edi
0x18003e6b1  jmp     short loc_18003E6B7
0x18003e6b3  mov     rbx, [rbp+arg_8]
0x18003e6b7  mov     rdx, rdi; pPrevCertContext
0x18003e6ba  mov     dword ptr [rbp+pcbData], 0
0x18003e6c1  mov     rcx, r12; hCertStore
0x18003e6c4  call    cs:__imp_CertEnumCertificatesInStore
0x18003e6ca  mov     rdi, rax
0x18003e6cd  test    rax, rax
0x18003e6d0  jz      loc_18003E820
0x18003e6d6  mov     rdx, [rbp+arg_0]
0x18003e6da  lea     r9, [rbp+pcbData]
0x18003e6de  mov     r8, rbx
0x18003e6e1  mov     rcx, rax
0x18003e6e4  call    TsCryptIsTemplateCertificate
0x18003e6e9  mov     ebx, eax
0x18003e6eb  test    eax, eax
0x18003e6ed  js      loc_18003E815
0x18003e6f3  cmp     dword ptr [rbp+pcbData], 0
0x18003e6f7  mov     rbx, [rbp+arg_8]
0x18003e6fb  jz      short loc_18003E6B7
0x18003e6fd  mov     rdx, [rbp+arg_10]; unsigned __int16 *
0x18003e701  lea     r8, [rbp+var_20]; int *
0x18003e705  mov     rcx, rdi; struct _CERT_CONTEXT *
0x18003e708  call    TsCryptIsSameSubjectName
0x18003e70d  mov     ebx, eax
0x18003e70f  test    eax, eax
0x18003e711  js      loc_18003E815
0x18003e717  cmp     [rbp+var_20], 0
0x18003e71b  mov     rbx, [rbp+arg_8]
0x18003e71f  jz      short loc_18003E6B7
0x18003e721  mov     rcx, rdi; pCert
0x18003e724  call    TsCryptCertContainsMachineKeySet
0x18003e729  test    eax, eax
0x18003e72b  jz      short loc_18003E6B7
0x18003e72d  mov     r9d, 2
0x18003e733  mov     [rsp+50h+var_30], 1
0x18003e73b  lea     r8, [rbp+var_10]
0x18003e73f  mov     rdx, rdi
0x18003e742  lea     rcx, [rbp+arg_18]
0x18003e746  call    TsCryptCertContainsEnhancedKeyUsage
0x18003e74b  mov     ebx, eax
0x18003e74d  test    eax, eax
0x18003e74f  js      loc_18003E815
0x18003e755  cmp     [rbp+arg_18], 0
0x18003e759  jnz     short loc_18003E78D
0x18003e75b  xor     r9d, r9d
0x18003e75e  mov     [rsp+50h+var_30], 0
0x18003e766  xor     r8d, r8d
0x18003e769  lea     rcx, [rbp+arg_18]
0x18003e76d  mov     rdx, rdi
0x18003e770  call    TsCryptCertContainsEnhancedKeyUsage
0x18003e775  mov     ebx, eax
0x18003e777  test    eax, eax
0x18003e779  js      loc_18003E815
0x18003e77f  cmp     [rbp+arg_18], 0
0x18003e783  mov     rbx, [rbp+arg_8]
0x18003e787  jz      loc_18003E6B7
0x18003e78d  lea     rdx, [rbp+var_1C]
0x18003e791  mov     rcx, rdi
0x18003e794  call    TsCryptGetCertTimeStatus
0x18003e799  mov     ebx, eax
0x18003e79b  test    eax, eax
0x18003e79d  js      short loc_18003E815
0x18003e79f  cmp     [rbp+var_1C], 0
0x18003e7a3  mov     rbx, [rbp+arg_8]
0x18003e7a7  jnz     loc_18003E6B7
0x18003e7ad  lea     rdx, [rbp+var_18]
0x18003e7b1  mov     rcx, rdi
0x18003e7b4  call    TsCryptGetDaysTillCertExpiry
0x18003e7b9  mov     ebx, eax
0x18003e7bb  test    eax, eax
0x18003e7bd  js      short loc_18003E815
0x18003e7bf  mov     ebx, [rbp+var_18]
0x18003e7c2  cmp     ebx, 2
0x18003e7c5  jb      loc_18003E6B3
0x18003e7cb  cmp     ebx, r13d
0x18003e7ce  jbe     loc_18003E6B3
0x18003e7d4  mov     eax, [rbp+var_14]
0x18003e7d7  mov     r9, r14; pcbData
0x18003e7da  mov     r8, [rbp+pvData]; pvData
0x18003e7de  mov     edx, 3; dwPropId
0x18003e7e3  mov     rcx, rdi; pCertContext
0x18003e7e6  mov     [r14], eax
0x18003e7e9  call    cs:__imp_CertGetCertificateContextProperty
0x18003e7ef  test    eax, eax
0x18003e7f1  jz      short loc_18003E800
0x18003e7f3  mov     r13d, ebx
0x18003e7f6  mov     esi, 1
0x18003e7fb  jmp     loc_18003E6B3
0x18003e800  call    cs:__imp_GetLastError
0x18003e806  mov     ebx, eax
0x18003e808  test    eax, eax
0x18003e80a  jle     short loc_18003E815
0x18003e80c  movzx   ebx, ax
0x18003e80f  or      ebx, 80070000h
0x18003e815  mov     rcx, rdi; pCertContext
0x18003e818  call    cs:__imp_CertFreeCertificateContext
0x18003e81e  jmp     short loc_18003E84F
0x18003e820  call    cs:__imp_GetLastError
0x18003e826  mov     ebx, eax
0x18003e828  cmp     eax, 80092004h
0x18003e82d  jz      short loc_18003E843
0x18003e82f  cmp     eax, 12h
0x18003e832  jz      short loc_18003E843
0x18003e834  test    eax, eax
0x18003e836  jle     short loc_18003E84F
0x18003e838  movzx   ebx, ax
0x18003e83b  or      ebx, 80070000h
0x18003e841  jmp     short loc_18003E84F
0x18003e843  neg     esi
0x18003e845  sbb     ebx, ebx
0x18003e847  not     ebx
0x18003e849  and     ebx, 80070002h
0x18003e84f  mov     edx, 1; dwFlags
0x18003e854  mov     rcx, r12; hCertStore
0x18003e857  call    cs:__imp_CertCloseStore
0x18003e85d  jmp     short loc_18003E864
0x18003e85f  mov     ebx, 80070057h
0x18003e864  mov     eax, ebx
0x18003e866  add     rsp, 50h
0x18003e86a  pop     r14
0x18003e86c  pop     r13
0x18003e86e  pop     r12
0x18003e870  pop     rdi
0x18003e871  pop     rsi
0x18003e872  pop     rbx
0x18003e873  pop     rbp
0x18003e874  retn
```
