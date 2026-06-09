# IsCertInStore(_CERT_CONTEXT const * const,wchar_t *,bool *)

- ea: `0x1800559c4`
- end: `0x180055bb3`
- name: `?IsCertInStore@@YAJQEBU_CERT_CONTEXT@@PEA_WPEA_N@Z`
- size: `495`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *const, wchar_t *, bool *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180056bc8`
- `0x180056ef4`

## callees

- `0x1800110fc`
- `0x1800559c4`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055aa6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055b25`
- `CRYPT32!CertFreeCertificateContext` at `0x180055b89`
- `CRYPT32!CertFreeCertificateContext` at `0x180055b89`
- `CRYPT32!CertControlStore` at `0x180055ae9`
- `CRYPT32!CertControlStore` at `0x180055ae9`
- `CRYPT32!CertCloseStore` at `0x180055b7b`
- `CRYPT32!CertCloseStore` at `0x180055b7b`
- `CRYPT32!CertFindCertificateInStore` at `0x180055b10`
- `CRYPT32!CertFindCertificateInStore` at `0x180055b10`
- `CRYPT32!CertOpenStore` at `0x180055a98`
- `CRYPT32!CertOpenStore` at `0x180055a98`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180055a1c`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180055a1c`

## pseudocode

```c
__int64 __fastcall IsCertInStore(const struct _CERT_CONTEXT *const a1, wchar_t *a2, bool *a3)
{
  signed int v4; // eax
  signed int v5; // ebx
  HCERTSTORE v6; // rax
  void *v7; // rsi
  signed int v8; // eax
  const CERT_CONTEXT *CertificateInStore; // rbp
  signed int LastError; // eax
  void *pvPara; // [rsp+20h] [rbp-68h]
  _QWORD pvFindPara[2]; // [rsp+40h] [rbp-48h] BYREF
  __int128 v14; // [rsp+50h] [rbp-38h] BYREF
  int v15; // [rsp+60h] [rbp-28h]

  pvFindPara[0] = 20;
  *a3 = 0;
  v15 = 0;
  pvFindPara[1] = &v14;
  v14 = 0;
  if ( CertGetCertificateContextProperty(a1, 3u, &v14, (DWORD *)pvFindPara) )
  {
    if ( LODWORD(pvFindPara[0]) != 20 )
      WUTrace(
        0,
        0,
        32,
        3,
        0,
        L"CertGetCertificateContextProperty() with CERT_SHA1_HASH_PROP_ID has size(%d) different than c_hashValSize(%d)",
        LODWORD(pvFindPara[0]),
        20);
    v6 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x2C000u, aTrustedpublish);
    v7 = v6;
    if ( v6 )
    {
      CertControlStore(v6, 0, 4u, 0);
      CertificateInStore = CertFindCertificateInStore(v7, 0, 0, 0x10000u, pvFindPara, 0);
      if ( CertificateInStore )
      {
        v5 = 0;
        *a3 = 1;
      }
      else
      {
        LastError = GetLastError();
        v5 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v5 = LastError;
        if ( v5 < 0 )
        {
          if ( v5 == -2146885628 )
          {
            v5 = 0;
            *a3 = 0;
          }
        }
        else
        {
          v5 = -2147418113;
        }
      }
      LODWORD(pvPara) = v5;
      WUTrace(0, 0, 32, 5, pvPara, L"Exiting IsCertInStore() for %ws with return code", aTrustedpublish);
      CertCloseStore(v7, 0);
      if ( CertificateInStore )
        CertFreeCertificateContext(CertificateInStore);
    }
    else
    {
      v8 = GetLastError();
      v5 = (unsigned __int16)v8 | 0x80070000;
      if ( v8 <= 0 )
        v5 = v8;
      if ( v5 < 0 )
      {
        if ( v5 == -2147024894 )
        {
          v5 = 0;
          *a3 = 0;
        }
      }
      else
      {
        return (unsigned int)-2147418113;
      }
    }
  }
  else
  {
    v4 = GetLastError();
    v5 = (unsigned __int16)v4 | 0x80070000;
    if ( v4 <= 0 )
      v5 = v4;
    if ( v5 >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800559c4  mov     r11, rsp
0x1800559c7  mov     [r11+10h], rbx
0x1800559cb  mov     [r11+20h], rbp
0x1800559cf  push    rsi
0x1800559d0  push    rdi
0x1800559d1  push    r12
0x1800559d3  sub     rsp, 70h
0x1800559d7  mov     rax, cs:__security_cookie
0x1800559de  xor     rax, rsp
0x1800559e1  mov     [rsp+88h+var_20], rax
0x1800559e6  xor     eax, eax
0x1800559e8  mov     qword ptr [r11-48h], 14h
0x1800559f0  mov     [r8], al
0x1800559f3  lea     r9, [r11-48h]; pcbData
0x1800559f7  mov     [rsp+88h+var_28], eax
0x1800559fb  mov     rdi, r8
0x1800559fe  xorps   xmm0, xmm0
0x180055a01  lea     rax, [r11-38h]
0x180055a05  mov     ebx, 14h
0x180055a0a  mov     [r11-40h], rax
0x180055a0e  lea     r8, [r11-38h]; pvData
0x180055a12  movups  [rsp+88h+var_38], xmm0
0x180055a17  lea     esi, [rbx-11h]
0x180055a1a  mov     edx, esi; dwPropId
0x180055a1c  call    cs:__imp_CertGetCertificateContextProperty
0x180055a22  test    eax, eax
0x180055a24  jnz     short loc_180055A49
0x180055a26  call    cs:__imp_GetLastError
0x180055a2c  movzx   ebx, ax
0x180055a2f  or      ebx, 80070000h
0x180055a35  test    eax, eax
0x180055a37  cmovle  ebx, eax
0x180055a3a  mov     eax, 8000FFFFh
0x180055a3f  test    ebx, ebx
0x180055a41  cmovns  ebx, eax
0x180055a44  jmp     loc_180055B8F
0x180055a49  mov     eax, [rsp+88h+pvFindPara]
0x180055a4d  cmp     eax, ebx
0x180055a4f  jz      short loc_180055A7E
0x180055a51  mov     [rsp+88h+var_50], ebx
0x180055a55  xor     edx, edx
0x180055a57  mov     dword ptr [rsp+88h+var_58], eax
0x180055a5b  mov     r9d, esi
0x180055a5e  lea     rax, aCertgetcertifi_1; "CertGetCertificateContextProperty() wit"...
0x180055a65  xor     ecx, ecx
0x180055a67  mov     [rsp+88h+pPrevCertContext], rax
0x180055a6c  lea     r8d, [rdx+20h]
0x180055a70  mov     [rsp+88h+pvPara], 0
0x180055a79  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180055a7e  xor     edx, edx; dwEncodingType
0x180055a80  lea     r12, aTrustedpublish; "TrustedPublisher"
0x180055a87  mov     r9d, 2C000h; dwFlags
0x180055a8d  mov     [rsp+88h+pvPara], r12; pvPara
0x180055a92  xor     r8d, r8d; hCryptProv
0x180055a95  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x180055a98  call    cs:__imp_CertOpenStore
0x180055a9e  mov     rsi, rax
0x180055aa1  test    rax, rax
0x180055aa4  jnz     short loc_180055ADD
0x180055aa6  call    cs:__imp_GetLastError
0x180055aac  movzx   ebx, ax
0x180055aaf  or      ebx, 80070000h
0x180055ab5  test    eax, eax
0x180055ab7  cmovle  ebx, eax
0x180055aba  test    ebx, ebx
0x180055abc  js      short loc_180055AC8
0x180055abe  mov     ebx, 8000FFFFh
0x180055ac3  jmp     loc_180055B8F
0x180055ac8  cmp     ebx, 80070002h
0x180055ace  jnz     loc_180055B8F
0x180055ad4  xor     ebx, ebx
0x180055ad6  mov     [rdi], bl
0x180055ad8  jmp     loc_180055B8F
0x180055add  xor     r9d, r9d; pvCtrlPara
0x180055ae0  xor     edx, edx; dwFlags
0x180055ae2  mov     rcx, rsi; hCertStore
0x180055ae5  lea     r8d, [r9+4]; dwCtrlType
0x180055ae9  call    cs:__imp_CertControlStore
0x180055aef  lea     rax, [rsp+88h+pvFindPara]
0x180055af4  mov     [rsp+88h+pPrevCertContext], 0; pPrevCertContext
0x180055afd  mov     r9d, 10000h; dwFindType
0x180055b03  mov     [rsp+88h+pvPara], rax; pvFindPara
0x180055b08  xor     r8d, r8d; dwFindFlags
0x180055b0b  xor     edx, edx; dwCertEncodingType
0x180055b0d  mov     rcx, rsi; hCertStore
0x180055b10  call    cs:__imp_CertFindCertificateInStore
0x180055b16  mov     rbp, rax
0x180055b19  test    rax, rax
0x180055b1c  jz      short loc_180055B25
0x180055b1e  xor     ebx, ebx
0x180055b20  mov     byte ptr [rdi], 1
0x180055b23  jmp     short loc_180055B50
0x180055b25  call    cs:__imp_GetLastError
0x180055b2b  movzx   ebx, ax
0x180055b2e  or      ebx, 80070000h
0x180055b34  test    eax, eax
0x180055b36  cmovle  ebx, eax
0x180055b39  test    ebx, ebx
0x180055b3b  js      short loc_180055B44
0x180055b3d  mov     ebx, 8000FFFFh
0x180055b42  jmp     short loc_180055B50
0x180055b44  cmp     ebx, 80092004h
0x180055b4a  jnz     short loc_180055B50
0x180055b4c  xor     ebx, ebx
0x180055b4e  mov     [rdi], bl
0x180055b50  xor     edx, edx
0x180055b52  mov     [rsp+88h+var_58], r12
0x180055b57  lea     rax, aExitingIscerti; "Exiting IsCertInStore() for %ws with re"...
0x180055b5e  xor     ecx, ecx
0x180055b60  mov     [rsp+88h+pPrevCertContext], rax
0x180055b65  mov     dword ptr [rsp+88h+pvPara], ebx
0x180055b69  lea     r9d, [rdx+5]
0x180055b6d  lea     r8d, [rdx+20h]
0x180055b71  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180055b76  xor     edx, edx; dwFlags
0x180055b78  mov     rcx, rsi; hCertStore
0x180055b7b  call    cs:__imp_CertCloseStore
0x180055b81  test    rbp, rbp
0x180055b84  jz      short loc_180055B8F
0x180055b86  mov     rcx, rbp; pCertContext
0x180055b89  call    cs:__imp_CertFreeCertificateContext
0x180055b8f  mov     eax, ebx
0x180055b91  mov     rcx, [rsp+88h+var_20]
0x180055b96  xor     rcx, rsp; StackCookie
0x180055b99  call    __security_check_cookie
0x180055b9e  lea     r11, [rsp+88h+var_18]
0x180055ba3  mov     rbx, [r11+28h]
0x180055ba7  mov     rbp, [r11+38h]
0x180055bab  mov     rsp, r11
0x180055bae  pop     r12
0x180055bb0  pop     rdi
0x180055bb1  pop     rsi
0x180055bb2  retn
```
