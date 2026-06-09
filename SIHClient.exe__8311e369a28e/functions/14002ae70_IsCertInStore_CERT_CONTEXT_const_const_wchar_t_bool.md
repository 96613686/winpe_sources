# IsCertInStore(_CERT_CONTEXT const * const,wchar_t *,bool *)

- ea: `0x14002ae70`
- end: `0x14002b04b`
- name: `?IsCertInStore@@YAJQEBU_CERT_CONTEXT@@PEA_WPEA_N@Z`
- size: `475`
- prototype: `int(const struct _CERT_CONTEXT *const, wchar_t *, bool *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x14002c094`
- `0x14002c3c4`
- `0x14002cbd8`

## callees

- `0x1400154b4`
- `0x14002ae70`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002aecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002af48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002aecf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002af48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002afc7`
- `CRYPT32!CertOpenStore` at `0x14002af3a`
- `CRYPT32!CertOpenStore` at `0x14002af3a`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14002aec5`
- `CRYPT32!CertGetCertificateContextProperty` at `0x14002aec5`
- `CRYPT32!CertFindCertificateInStore` at `0x14002afb2`
- `CRYPT32!CertFindCertificateInStore` at `0x14002afb2`
- `CRYPT32!CertFreeCertificateContext` at `0x14002b02b`
- `CRYPT32!CertFreeCertificateContext` at `0x14002b02b`
- `CRYPT32!CertControlStore` at `0x14002af8b`
- `CRYPT32!CertControlStore` at `0x14002af8b`
- `CRYPT32!CertCloseStore` at `0x14002b01d`
- `CRYPT32!CertCloseStore` at `0x14002b01d`

## pseudocode

```c
__int64 __fastcall IsCertInStore(const struct _CERT_CONTEXT *const a1, wchar_t *a2, bool *a3)
{
  signed int v5; // eax
  signed int v6; // ebx
  HCERTSTORE v7; // rax
  void *v8; // rsi
  signed int v9; // eax
  const CERT_CONTEXT *CertificateInStore; // rbp
  signed int LastError; // eax
  void *pvPara; // [rsp+20h] [rbp-78h]
  _QWORD pvFindPara[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v15; // [rsp+50h] [rbp-48h] BYREF
  int v16; // [rsp+60h] [rbp-38h]

  pvFindPara[0] = 20;
  *a3 = 0;
  v16 = 0;
  pvFindPara[1] = &v15;
  v15 = 0;
  if ( CertGetCertificateContextProperty(a1, 3u, &v15, (DWORD *)pvFindPara) )
  {
    if ( LODWORD(pvFindPara[0]) != 20 )
      WUTrace(
        0,
        0,
        32,
        3,
        0,
        L"CertGetCertificateContextProperty() with CERT_SHA1_HASH_PROP_ID has size(%d) different than c_hashValSize(%d)");
    v7 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x2C000u, a2);
    v8 = v7;
    if ( v7 )
    {
      CertControlStore(v7, 0, 4u, 0);
      CertificateInStore = CertFindCertificateInStore(v8, 0, 0, 0x10000u, pvFindPara, 0);
      if ( CertificateInStore )
      {
        v6 = 0;
        *a3 = 1;
      }
      else
      {
        LastError = GetLastError();
        v6 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v6 = LastError;
        if ( v6 < 0 )
        {
          if ( v6 == -2146885628 )
          {
            v6 = 0;
            *a3 = 0;
          }
        }
        else
        {
          v6 = -2147418113;
        }
      }
      LODWORD(pvPara) = v6;
      WUTrace(0, 0, 32, 5, pvPara, L"Exiting IsCertInStore() for %ws with return code");
      CertCloseStore(v8, 0);
      if ( CertificateInStore )
        CertFreeCertificateContext(CertificateInStore);
    }
    else
    {
      v9 = GetLastError();
      v6 = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        v6 = v9;
      if ( v6 < 0 )
      {
        if ( v6 == -2147024894 )
        {
          v6 = 0;
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
    v5 = GetLastError();
    v6 = (unsigned __int16)v5 | 0x80070000;
    if ( v5 <= 0 )
      v6 = v5;
    if ( v6 >= 0 )
      return (unsigned int)-2147418113;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14002ae70  mov     r11, rsp
0x14002ae73  push    rbx
0x14002ae74  push    rbp
0x14002ae75  push    rsi
0x14002ae76  push    rdi
0x14002ae77  push    r14
0x14002ae79  sub     rsp, 70h
0x14002ae7d  mov     rax, cs:__security_cookie
0x14002ae84  xor     rax, rsp
0x14002ae87  mov     [rsp+98h+var_30], rax
0x14002ae8c  xor     eax, eax
0x14002ae8e  mov     qword ptr [r11-58h], 14h
0x14002ae96  mov     [r8], al
0x14002ae99  lea     r9, [r11-58h]; pcbData
0x14002ae9d  mov     [rsp+98h+var_38], eax
0x14002aea1  mov     rdi, r8
0x14002aea4  mov     r14, rdx
0x14002aea7  lea     rax, [r11-48h]
0x14002aeab  xorps   xmm0, xmm0
0x14002aeae  mov     [r11-50h], rax
0x14002aeb2  mov     ebx, 14h
0x14002aeb7  lea     r8, [r11-48h]; pvData
0x14002aebb  movups  [rsp+98h+var_48], xmm0
0x14002aec0  lea     esi, [rbx-11h]
0x14002aec3  mov     edx, esi; dwPropId
0x14002aec5  call    cs:__imp_CertGetCertificateContextProperty
0x14002aecb  test    eax, eax
0x14002aecd  jnz     short loc_14002AEF2
0x14002aecf  call    cs:__imp_GetLastError
0x14002aed5  movzx   ebx, ax
0x14002aed8  or      ebx, 80070000h
0x14002aede  test    eax, eax
0x14002aee0  cmovle  ebx, eax
0x14002aee3  mov     eax, 8000FFFFh
0x14002aee8  test    ebx, ebx
0x14002aeea  cmovns  ebx, eax
0x14002aeed  jmp     loc_14002B031
0x14002aef2  mov     eax, [rsp+98h+pvFindPara]
0x14002aef6  cmp     eax, ebx
0x14002aef8  jz      short loc_14002AF27
0x14002aefa  mov     [rsp+98h+var_60], ebx
0x14002aefe  xor     edx, edx
0x14002af00  mov     dword ptr [rsp+98h+var_68], eax
0x14002af04  mov     r9d, esi
0x14002af07  lea     rax, aCertgetcertifi_1; "CertGetCertificateContextProperty() wit"...
0x14002af0e  xor     ecx, ecx
0x14002af10  mov     [rsp+98h+pPrevCertContext], rax
0x14002af15  lea     r8d, [rdx+20h]
0x14002af19  mov     [rsp+98h+pvPara], 0
0x14002af22  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002af27  xor     edx, edx; dwEncodingType
0x14002af29  mov     [rsp+98h+pvPara], r14; pvPara
0x14002af2e  mov     r9d, 2C000h; dwFlags
0x14002af34  xor     r8d, r8d; hCryptProv
0x14002af37  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x14002af3a  call    cs:__imp_CertOpenStore
0x14002af40  mov     rsi, rax
0x14002af43  test    rax, rax
0x14002af46  jnz     short loc_14002AF7F
0x14002af48  call    cs:__imp_GetLastError
0x14002af4e  movzx   ebx, ax
0x14002af51  or      ebx, 80070000h
0x14002af57  test    eax, eax
0x14002af59  cmovle  ebx, eax
0x14002af5c  test    ebx, ebx
0x14002af5e  js      short loc_14002AF6A
0x14002af60  mov     ebx, 8000FFFFh
0x14002af65  jmp     loc_14002B031
0x14002af6a  cmp     ebx, 80070002h
0x14002af70  jnz     loc_14002B031
0x14002af76  xor     ebx, ebx
0x14002af78  mov     [rdi], bl
0x14002af7a  jmp     loc_14002B031
0x14002af7f  xor     r9d, r9d; pvCtrlPara
0x14002af82  xor     edx, edx; dwFlags
0x14002af84  mov     rcx, rsi; hCertStore
0x14002af87  lea     r8d, [r9+4]; dwCtrlType
0x14002af8b  call    cs:__imp_CertControlStore
0x14002af91  lea     rax, [rsp+98h+pvFindPara]
0x14002af96  mov     [rsp+98h+pPrevCertContext], 0; pPrevCertContext
0x14002af9f  mov     r9d, 10000h; dwFindType
0x14002afa5  mov     [rsp+98h+pvPara], rax; pvFindPara
0x14002afaa  xor     r8d, r8d; dwFindFlags
0x14002afad  xor     edx, edx; dwCertEncodingType
0x14002afaf  mov     rcx, rsi; hCertStore
0x14002afb2  call    cs:__imp_CertFindCertificateInStore
0x14002afb8  mov     rbp, rax
0x14002afbb  test    rax, rax
0x14002afbe  jz      short loc_14002AFC7
0x14002afc0  xor     ebx, ebx
0x14002afc2  mov     byte ptr [rdi], 1
0x14002afc5  jmp     short loc_14002AFF2
0x14002afc7  call    cs:__imp_GetLastError
0x14002afcd  movzx   ebx, ax
0x14002afd0  or      ebx, 80070000h
0x14002afd6  test    eax, eax
0x14002afd8  cmovle  ebx, eax
0x14002afdb  test    ebx, ebx
0x14002afdd  js      short loc_14002AFE6
0x14002afdf  mov     ebx, 8000FFFFh
0x14002afe4  jmp     short loc_14002AFF2
0x14002afe6  cmp     ebx, 80092004h
0x14002afec  jnz     short loc_14002AFF2
0x14002afee  xor     ebx, ebx
0x14002aff0  mov     [rdi], bl
0x14002aff2  xor     edx, edx
0x14002aff4  mov     [rsp+98h+var_68], r14
0x14002aff9  lea     rax, aExitingIscerti; "Exiting IsCertInStore() for %ws with re"...
0x14002b000  xor     ecx, ecx
0x14002b002  mov     [rsp+98h+pPrevCertContext], rax
0x14002b007  mov     dword ptr [rsp+98h+pvPara], ebx
0x14002b00b  lea     r9d, [rdx+5]
0x14002b00f  lea     r8d, [rdx+20h]
0x14002b013  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002b018  xor     edx, edx; dwFlags
0x14002b01a  mov     rcx, rsi; hCertStore
0x14002b01d  call    cs:__imp_CertCloseStore
0x14002b023  test    rbp, rbp
0x14002b026  jz      short loc_14002B031
0x14002b028  mov     rcx, rbp; pCertContext
0x14002b02b  call    cs:__imp_CertFreeCertificateContext
0x14002b031  mov     eax, ebx
0x14002b033  mov     rcx, [rsp+98h+var_30]
0x14002b038  xor     rcx, rsp; StackCookie
0x14002b03b  call    __security_check_cookie
0x14002b040  add     rsp, 70h
0x14002b044  pop     r14
0x14002b046  pop     rdi
0x14002b047  pop     rsi
0x14002b048  pop     rbp
0x14002b049  pop     rbx
0x14002b04a  retn
```
