# RegistrationCertStatus::GetCertificate(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,INFO_KIND,_CERT_CONTEXT const * *)

- ea: `0x18000b08c`
- end: `0x18000b323`
- name: `?GetCertificate@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22W4INFO_KIND@@PEAPEBU_CERT_CONTEXT@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, PCCERT_CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000afd0`

## callees

- `0x18000b08c`
- `0x18000b32c`
- `0x18000b3c4`
- `0x18000b448`
- `0x180019618`
- `0x180019e18`
- `0x18001a380`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b2a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b2e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b2a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b2e2`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000b2ae`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18000b2ae`
- `CRYPT32!CertFreeCertificateContext` at `0x18000b2ca`
- `CRYPT32!CertFreeCertificateContext` at `0x18000b2ca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b1fb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000b1fb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000b223`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000b223`

## string_xrefs

- `0x18000b155`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000b14e`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetCertificate(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        PCCERT_CONTEXT *a7)
{
  unsigned int v7; // esi
  unsigned __int16 *v8; // r14
  unsigned int v9; // r12d
  unsigned int v10; // edi
  __int64 v11; // r8
  unsigned int v12; // eax
  int Certificates; // eax
  int v14; // ebx
  const CERT_CONTEXT *v15; // rax
  const struct _CERT_CONTEXT *v16; // rcx
  unsigned __int16 *v17; // rdi
  unsigned __int16 *v18; // rsi
  PCCERT_CONTEXT v19; // rax
  __int64 v20; // rbx
  unsigned __int16 **v22; // [rsp+28h] [rbp-79h]
  unsigned int *v23; // [rsp+30h] [rbp-71h]
  unsigned int v24; // [rsp+50h] [rbp-51h] BYREF
  unsigned __int16 *v25; // [rsp+58h] [rbp-49h] BYREF
  unsigned int v26; // [rsp+60h] [rbp-41h]
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-39h] BYREF
  _BYTE v28[16]; // [rsp+78h] [rbp-29h] BYREF
  const wchar_t *v29; // [rsp+88h] [rbp-19h]
  __int64 v30; // [rsp+90h] [rbp-11h]
  const unsigned __int16 *v31; // [rsp+98h] [rbp-9h]
  __int64 v32; // [rsp+A0h] [rbp-1h]

  v7 = 0;
  v25 = 0;
  v24 = 0;
  v8 = 0;
  v9 = 0;
  SystemTime = 0;
  if ( !a7 )
  {
    v10 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"RegistrationCertStatus::GetCertificate",
      L"ppCertContext");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v29 = L"RegistrationCertStatus::GetCertificate";
      v30 = 78;
      v31 = L"ppCertContext";
      v32 = 28;
      v12 = McGenEventWrite_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              NullOrEmptyParameterFailureEvent,
              v11,
              3,
              v28);
      if ( v12 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v12);
    }
    goto LABEL_20;
  }
  *a7 = 0;
  v23 = &v24;
  v22 = &v25;
  Certificates = RegistrationCertStatus::GetCertificates();
  v26 = Certificates;
  v10 = Certificates;
  if ( Certificates < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetCertificate",
      L"RegistrationCertStatus::GetCertificates",
      (unsigned int)Certificates);
    v8 = v25;
    v9 = v24;
    goto LABEL_20;
  }
  v9 = v24;
  v8 = v25;
  if ( v24 != 1 )
  {
    v14 = 0;
    if ( !v24 )
      goto LABEL_15;
    while ( 1 )
    {
      v15 = *(const CERT_CONTEXT **)&v8[4 * v14];
      if ( !*a7 )
        goto LABEL_13;
      if ( CompareFileTime(&v15->pCertInfo->NotBefore, &(*a7)->pCertInfo->NotBefore) == -1 )
        break;
LABEL_14:
      if ( ++v14 >= v9 )
        goto LABEL_15;
    }
    v15 = *(const CERT_CONTEXT **)&v8[4 * v14];
LABEL_13:
    *a7 = v15;
    goto LABEL_14;
  }
  *a7 = *(PCCERT_CONTEXT *)v25;
  v26 = 0;
LABEL_15:
  if ( FileTimeToSystemTime(&(*a7)->pCertInfo->NotBefore, &SystemTime) )
  {
    v16 = *a7;
    v25 = 0;
    CertificateUtil::GetCertificateThumbprint(v16, &v25);
    v17 = L"N/A";
    v18 = v25;
    if ( v25 )
      v17 = v25;
    LODWORD(v23) = SystemTime.wMinute;
    LODWORD(v22) = SystemTime.wHour;
    Logger::TraceVerbose(
      L"%s: Returning certificate with UTC timestamp (YYYY-MM-DD HH:MM:SS.sss) %04u-%02u-%02u %02u:%02u:%02u.%03u and thumbprint %s",
      L"RegistrationCertStatus::GetCertificate",
      SystemTime.wYear,
      SystemTime.wMonth,
      SystemTime.wDay,
      v22,
      v23,
      SystemTime.wSecond,
      SystemTime.wMilliseconds,
      v17);
    operator delete(v18);
    v7 = 0;
  }
  v19 = CertDuplicateCertificateContext(*a7);
  v10 = v26;
  *a7 = v19;
LABEL_20:
  if ( v8 && v9 )
  {
    do
    {
      v20 = v7;
      CertFreeCertificateContext(*(PCCERT_CONTEXT *)&v8[4 * v7++]);
      *(_QWORD *)&v8[4 * v20] = 0;
    }
    while ( v7 < v9 );
  }
  operator delete(v8);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"RegistrationCertStatus::GetCertificate", v10);
  return v10;
}

```

## disassembly

```asm
0x18000b08c  mov     [rsp-8+arg_8], rbx
0x18000b091  push    rbp
0x18000b092  push    rsi
0x18000b093  push    rdi
0x18000b094  push    r12
0x18000b096  push    r13
0x18000b098  push    r14
0x18000b09a  push    r15
0x18000b09c  lea     rbp, [rsp-0Fh]
0x18000b0a1  sub     rsp, 0B0h
0x18000b0a8  mov     rax, cs:__security_cookie
0x18000b0af  xor     rax, rsp
0x18000b0b2  mov     [rbp+3Fh+var_38], rax
0x18000b0b6  mov     r15, [rbp+3Fh+arg_30]
0x18000b0ba  xor     esi, esi
0x18000b0bc  mov     [rbp+3Fh+var_88], rsi
0x18000b0c0  xorps   xmm0, xmm0
0x18000b0c3  mov     [rbp+3Fh+var_90], esi
0x18000b0c6  mov     r14d, esi
0x18000b0c9  mov     r12d, esi
0x18000b0cc  movups  xmmword ptr [rbp+3Fh+SystemTime.wYear], xmm0
0x18000b0d0  test    r15, r15
0x18000b0d3  jnz     loc_18000B16D
0x18000b0d9  lea     rbx, aPpcertcontext; "ppCertContext"
0x18000b0e0  mov     edi, 80070057h
0x18000b0e5  lea     r13, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18000b0ec  mov     r8, rbx
0x18000b0ef  mov     rdx, r13
0x18000b0f2  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x18000b0f9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000b0fe  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000b105  jz      loc_18000B2BA
0x18000b10b  lea     rax, [rbp+3Fh+var_68]
0x18000b10f  mov     [rbp+3Fh+var_58], r13
0x18000b113  lea     r9d, [r15+3]
0x18000b117  mov     [rsp+0E0h+var_C0], rax
0x18000b11c  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000b123  mov     [rbp+3Fh+var_50], 4Eh ; 'N'
0x18000b12b  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000b132  mov     [rbp+3Fh+var_48], rbx
0x18000b136  mov     [rbp+3Fh+var_40], 1Ch
0x18000b13e  call    McGenEventWrite_EventWriteTransfer
0x18000b143  test    eax, eax
0x18000b145  jz      loc_18000B2BA
0x18000b14b  mov     r9d, eax
0x18000b14e  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000b155  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000b15c  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000b163  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000b168  jmp     loc_18000B2BA
0x18000b16d  lea     rax, [rbp+3Fh+var_90]
0x18000b171  mov     [r15], rsi
0x18000b174  mov     [rsp+0E0h+var_B0], rax
0x18000b179  lea     rax, [rbp+3Fh+var_88]
0x18000b17d  mov     [rsp+0E0h+var_B8], rax
0x18000b182  call    ?GetCertificates@RegistrationCertStatus@@CAJW4_CERTFICATE_LOCATION@@PEBDPEBG22PEAPEAPEBU_CERT_CONTEXT@@PEAK@Z; RegistrationCertStatus::GetCertificates(_CERTFICATE_LOCATION,char const *,ushort const *,ushort const *,ushort const *,_CERT_CONTEXT const * * *,ulong *)
0x18000b187  mov     [rbp+3Fh+var_80], eax
0x18000b18a  mov     edi, eax
0x18000b18c  test    eax, eax
0x18000b18e  jns     short loc_18000B1BD
0x18000b190  lea     r13, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18000b197  mov     r9d, eax
0x18000b19a  mov     rdx, r13
0x18000b19d  lea     r8, aRegistrationce_2; "RegistrationCertStatus::GetCertificates"
0x18000b1a4  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18000b1ab  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000b1b0  mov     r14, [rbp+3Fh+var_88]
0x18000b1b4  mov     r12d, [rbp+3Fh+var_90]
0x18000b1b8  jmp     loc_18000B2BA
0x18000b1bd  mov     r12d, [rbp+3Fh+var_90]
0x18000b1c1  mov     r14, [rbp+3Fh+var_88]
0x18000b1c5  cmp     r12d, 1
0x18000b1c9  jnz     short loc_18000B1D6
0x18000b1cb  mov     rax, [r14]
0x18000b1ce  mov     [r15], rax
0x18000b1d1  mov     [rbp+3Fh+var_80], esi
0x18000b1d4  jmp     short loc_18000B214
0x18000b1d6  mov     ebx, esi
0x18000b1d8  test    r12d, r12d
0x18000b1db  jz      short loc_18000B214
0x18000b1dd  mov     rdx, [r15]
0x18000b1e0  mov     edi, ebx
0x18000b1e2  mov     rax, [r14+rdi*8]
0x18000b1e6  test    rdx, rdx
0x18000b1e9  jz      short loc_18000B20A
0x18000b1eb  mov     rdx, [rdx+18h]
0x18000b1ef  mov     rcx, [rax+18h]
0x18000b1f3  add     rdx, 40h ; '@'; lpFileTime2
0x18000b1f7  add     rcx, 40h ; '@'; lpFileTime1
0x18000b1fb  call    cs:__imp_CompareFileTime
0x18000b201  cmp     eax, 0FFFFFFFFh
0x18000b204  jnz     short loc_18000B20D
0x18000b206  mov     rax, [r14+rdi*8]
0x18000b20a  mov     [r15], rax
0x18000b20d  inc     ebx
0x18000b20f  cmp     ebx, r12d
0x18000b212  jb      short loc_18000B1DD
0x18000b214  mov     rax, [r15]
0x18000b217  lea     rdx, [rbp+3Fh+SystemTime]; lpSystemTime
0x18000b21b  mov     rcx, [rax+18h]
0x18000b21f  add     rcx, 40h ; '@'; lpFileTime
0x18000b223  call    cs:__imp_FileTimeToSystemTime
0x18000b229  lea     r13, aRegistrationce_1; "RegistrationCertStatus::GetCertificate"
0x18000b230  test    eax, eax
0x18000b232  jz      short loc_18000B2AB
0x18000b234  mov     rcx, [r15]; struct _CERT_CONTEXT *
0x18000b237  lea     rdx, [rbp+3Fh+var_88]; unsigned __int16 **
0x18000b23b  mov     [rbp+3Fh+var_88], rsi
0x18000b23f  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18000b244  movzx   edx, [rbp+3Fh+SystemTime.wSecond]
0x18000b248  lea     rdi, aNA; "N/A"
0x18000b24f  mov     rsi, [rbp+3Fh+var_88]
0x18000b253  lea     rcx, aSReturningCert; "%s: Returning certificate with UTC time"...
0x18000b25a  movzx   eax, [rbp+3Fh+SystemTime.wMilliseconds]
0x18000b25e  test    rsi, rsi
0x18000b261  movzx   r10d, [rbp+3Fh+SystemTime.wMinute]
0x18000b266  movzx   r11d, [rbp+3Fh+SystemTime.wHour]
0x18000b26b  cmovnz  rdi, rsi
0x18000b26f  movzx   ebx, [rbp+3Fh+SystemTime.wDay]
0x18000b273  movzx   r9d, [rbp+3Fh+SystemTime.wMonth]
0x18000b278  movzx   r8d, [rbp+3Fh+SystemTime.wYear]
0x18000b27d  mov     [rsp+0E0h+var_98], rdi
0x18000b282  mov     [rsp+0E0h+var_A0], eax
0x18000b286  mov     [rsp+0E0h+var_A8], edx
0x18000b28a  mov     rdx, r13
0x18000b28d  mov     dword ptr [rsp+0E0h+var_B0], r10d
0x18000b292  mov     dword ptr [rsp+0E0h+var_B8], r11d
0x18000b297  mov     dword ptr [rsp+0E0h+var_C0], ebx
0x18000b29b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000b2a0  mov     rcx, rsi
0x18000b2a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b2a9  xor     esi, esi
0x18000b2ab  mov     rcx, [r15]; pCertContext
0x18000b2ae  call    cs:__imp_CertDuplicateCertificateContext
0x18000b2b4  mov     edi, [rbp+3Fh+var_80]
0x18000b2b7  mov     [r15], rax
0x18000b2ba  test    r14, r14
0x18000b2bd  jz      short loc_18000B2DF
0x18000b2bf  test    r12d, r12d
0x18000b2c2  jz      short loc_18000B2DF
0x18000b2c4  mov     ebx, esi
0x18000b2c6  mov     rcx, [r14+rbx*8]; pCertContext
0x18000b2ca  call    cs:__imp_CertFreeCertificateContext
0x18000b2d0  inc     esi
0x18000b2d2  mov     qword ptr [r14+rbx*8], 0
0x18000b2da  cmp     esi, r12d
0x18000b2dd  jb      short loc_18000B2C4
0x18000b2df  mov     rcx, r14
0x18000b2e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b2e8  mov     r8d, edi
0x18000b2eb  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18000b2f2  mov     rdx, r13
0x18000b2f5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18000b2fa  mov     eax, edi
0x18000b2fc  mov     rcx, [rbp+3Fh+var_38]
0x18000b300  xor     rcx, rsp; StackCookie
0x18000b303  call    __security_check_cookie
0x18000b308  mov     rbx, [rsp+0E0h+arg_8]
0x18000b310  add     rsp, 0B0h
0x18000b317  pop     r15
0x18000b319  pop     r14
0x18000b31b  pop     r13
0x18000b31d  pop     r12
0x18000b31f  pop     rdi
0x18000b320  pop     rsi
0x18000b321  pop     rbp
0x18000b322  retn
```
