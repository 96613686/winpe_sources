# CertificateUtil::DoesExtensionWithValueExist(char const *,ushort const *,_CERT_OID_VALUE_TYPE,_CERT_CONTEXT const *,int *)

- ea: `0x180008360`
- end: `0x18000859c`
- name: `?DoesExtensionWithValueExist@CertificateUtil@@SAJPEBDPEBGW4_CERT_OID_VALUE_TYPE@@PEBU_CERT_CONTEXT@@PEAH@Z`
- size: `572`
- prototype: `__int64 __fastcall(const char *, const WCHAR *, int, const struct _CERT_CONTEXT *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180008950`

## callees

- `0x180007ef0`
- `0x180008360`
- `0x18000ae60`
- `0x18000b3c4`
- `0x18000b448`
- `0x18001943c`
- `0x18001a380`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000857e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000857e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008569`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008569`

## string_xrefs

- `0x180008533`: `CertificateUtil::FindExtensionStrValueByOid`
- `0x18000839f`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180008433`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18000846e`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800084b5`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x1800084f6`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x18000854e`: `CertificateUtil::DoesExtensionWithValueExist`
- `0x180008416`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000840f`: `EventWriteNullOrEmptyParameterFailureEvent`
- `0x18000851d`: `CertificateUtil::FindExtensionGuidValueByOid`

## pseudocode

```c
__int64 __fastcall CertificateUtil::DoesExtensionWithValueExist(
        const char *a1,
        const WCHAR *a2,
        int a3,
        const struct _CERT_CONTEXT *a4,
        _DWORD *a5)
{
  const wchar_t *v6; // rsi
  unsigned int v7; // ebx
  __int64 v8; // r8
  unsigned int v9; // eax
  int ExtensionGuidValueByOid; // eax
  const unsigned __int16 *v11; // r8
  LPCWSTR lpString1; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v14[16]; // [rsp+38h] [rbp-60h] BYREF
  const unsigned __int16 *v15; // [rsp+48h] [rbp-50h]
  __int64 v16; // [rsp+50h] [rbp-48h]
  const wchar_t *v17; // [rsp+58h] [rbp-40h]
  __int64 v18; // [rsp+60h] [rbp-38h]

  lpString1 = 0;
  if ( !a1 )
  {
    v6 = L"pcszOid";
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pcszOid");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_25;
    v18 = 16;
    goto LABEL_4;
  }
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pcszOidValue");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"CertificateUtil::DoesExtensionWithValueExist", L"pcszOidValue");
    goto LABEL_25;
  }
  if ( !a4 )
  {
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::DoesExtensionWithValueExist",
      &stru_18001E5B8);
    Logger::WriteNullOrEmptyParameterFailureEvent(
      L"CertificateUtil::DoesExtensionWithValueExist",
      (const unsigned __int16 *)&stru_18001E5B8);
    goto LABEL_25;
  }
  if ( !a5 )
  {
    v6 = L"pbResult";
    v7 = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"CertificateUtil::DoesExtensionWithValueExist",
      L"pbResult");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) == 0 )
      goto LABEL_25;
    v18 = 18;
LABEL_4:
    v17 = v6;
    v16 = 90;
    v15 = L"CertificateUtil::DoesExtensionWithValueExist";
    v9 = McGenEventWrite_EventWriteTransfer(
           &UserDeviceRegistrationEventProvider_Context,
           NullOrEmptyParameterFailureEvent,
           v8,
           3,
           v14);
    if ( v9 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteNullOrEmptyParameterFailureEvent",
        L"EventWriteNullOrEmptyParameterFailureEvent",
        v9);
    goto LABEL_25;
  }
  *a5 = 0;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      Logger::TraceError(L"%s: Unknown CERT_OID_VALUE_TYPE: %d.", L"CertificateUtil::DoesExtensionWithValueExist");
      v7 = -2147024809;
      goto LABEL_25;
    }
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionGuidValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v11 = L"CertificateUtil::FindExtensionGuidValueByOid";
  }
  else
  {
    ExtensionGuidValueByOid = CertificateUtil::FindExtensionStrValueByOid(a1, a4, (unsigned __int16 **)&lpString1);
    v11 = L"CertificateUtil::FindExtensionStrValueByOid";
  }
  v7 = ExtensionGuidValueByOid;
  if ( ExtensionGuidValueByOid == -2146885628 )
  {
    v7 = 0;
  }
  else if ( ExtensionGuidValueByOid >= 0 )
  {
    if ( !lstrcmpiW(lpString1, a2) )
      *a5 = 1;
  }
  else
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x",
      L"CertificateUtil::DoesExtensionWithValueExist",
      v11,
      (unsigned int)ExtensionGuidValueByOid);
  }
LABEL_25:
  operator delete((void *)lpString1);
  return v7;
}

```

## disassembly

```asm
0x180008360  push    rbx
0x180008362  push    rbp
0x180008363  push    rsi
0x180008364  push    rdi
0x180008365  sub     rsp, 78h
0x180008369  mov     rax, cs:__security_cookie
0x180008370  xor     rax, rsp
0x180008373  mov     [rsp+98h+var_30], rax
0x180008378  mov     rdi, [rsp+98h+arg_20]
0x180008380  xor     ebp, ebp
0x180008382  mov     [rsp+98h+lpString1], rbp
0x180008387  mov     rsi, rdx
0x18000838a  test    rcx, rcx
0x18000838d  jnz     loc_18000842E
0x180008393  lea     rsi, aPcszoid; "pcszOid"
0x18000839a  mov     ebx, 80070057h
0x18000839f  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800083a6  mov     r8, rsi
0x1800083a9  mov     rdx, rdi
0x1800083ac  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x1800083b3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800083b8  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800083bf  jz      loc_180008579
0x1800083c5  mov     [rsp+98h+var_38], 10h
0x1800083ce  lea     rax, [rsp+98h+var_60]
0x1800083d3  mov     [rsp+98h+var_40], rsi
0x1800083d8  mov     r9d, 3
0x1800083de  mov     [rsp+98h+var_78], rax
0x1800083e3  lea     rdx, NullOrEmptyParameterFailureEvent
0x1800083ea  mov     [rsp+98h+var_48], 5Ah ; 'Z'
0x1800083f3  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x1800083fa  mov     [rsp+98h+var_50], rdi
0x1800083ff  call    McGenEventWrite_EventWriteTransfer
0x180008404  test    eax, eax
0x180008406  jz      loc_180008579
0x18000840c  mov     r9d, eax
0x18000840f  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x180008416  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000841d  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x180008424  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008429  jmp     loc_180008579
0x18000842e  test    rsi, rsi
0x180008431  jnz     short loc_180008469
0x180008433  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x18000843a  mov     ebx, 80070057h
0x18000843f  mov     rdx, rdi
0x180008442  lea     r8, aPcszoidvalue; "pcszOidValue"
0x180008449  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x180008450  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008455  lea     rdx, aPcszoidvalue; "pcszOidValue"
0x18000845c  mov     rcx, rdi; unsigned __int16 *
0x18000845f  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180008464  jmp     loc_180008579
0x180008469  test    r9, r9
0x18000846c  jnz     short loc_1800084A4
0x18000846e  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180008475  mov     ebx, 80070057h
0x18000847a  mov     rdx, rdi
0x18000847d  lea     r8, stru_18001E5B8
0x180008484  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x18000848b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008490  lea     rdx, stru_18001E5B8; unsigned __int16 *
0x180008497  mov     rcx, rdi; unsigned __int16 *
0x18000849a  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18000849f  jmp     loc_180008579
0x1800084a4  test    rdi, rdi
0x1800084a7  jnz     short loc_1800084E9
0x1800084a9  lea     rsi, aPbresult; "pbResult"
0x1800084b0  mov     ebx, 80070057h
0x1800084b5  lea     rdi, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800084bc  mov     r8, rsi
0x1800084bf  mov     rdx, rdi
0x1800084c2  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x1800084c9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800084ce  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800084d5  jz      loc_180008579
0x1800084db  mov     [rsp+98h+var_38], 12h
0x1800084e4  jmp     loc_1800083CE
0x1800084e9  mov     [rdi], ebp
0x1800084eb  test    r8d, r8d
0x1800084ee  jz      short loc_180008526
0x1800084f0  cmp     r8d, 1
0x1800084f4  jz      short loc_180008510
0x1800084f6  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x1800084fd  lea     rcx, aSUnknownCertOi; "%s: Unknown CERT_OID_VALUE_TYPE: %d."
0x180008504  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180008509  mov     ebx, 80070057h
0x18000850e  jmp     short loc_180008579
0x180008510  lea     r8, [rsp+98h+lpString1]; unsigned __int16 **
0x180008515  mov     rdx, r9; struct _CERT_CONTEXT *
0x180008518  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18000851d  lea     r8, aCertificateuti_4; "CertificateUtil::FindExtensionGuidValue"...
0x180008524  jmp     short loc_18000853A
0x180008526  lea     r8, [rsp+98h+lpString1]; unsigned __int16 **
0x18000852b  mov     rdx, r9; struct _CERT_CONTEXT *
0x18000852e  call    ?FindExtensionStrValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionStrValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x180008533  lea     r8, aCertificateuti_5; "CertificateUtil::FindExtensionStrValueB"...
0x18000853a  mov     ebx, eax
0x18000853c  cmp     eax, 80092004h
0x180008541  jnz     short loc_180008547
0x180008543  mov     ebx, ebp
0x180008545  jmp     short loc_180008579
0x180008547  test    ebx, ebx
0x180008549  jns     short loc_180008561
0x18000854b  mov     r9d, ebx
0x18000854e  lea     rdx, aCertificateuti_6; "CertificateUtil::DoesExtensionWithValue"...
0x180008555  lea     rcx, aSSFailedWithEr; "%s: %s failed with error code: 0x%08x"
0x18000855c  jmp     loc_180008424
0x180008561  mov     rcx, [rsp+98h+lpString1]; lpString1
0x180008566  mov     rdx, rsi; lpString2
0x180008569  call    cs:__imp_lstrcmpiW
0x18000856f  test    eax, eax
0x180008571  jnz     short loc_180008579
0x180008573  mov     dword ptr [rdi], 1
0x180008579  mov     rcx, [rsp+98h+lpString1]
0x18000857e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008584  mov     eax, ebx
0x180008586  mov     rcx, [rsp+98h+var_30]
0x18000858b  xor     rcx, rsp; StackCookie
0x18000858e  call    __security_check_cookie
0x180008593  add     rsp, 78h
0x180008597  pop     rdi
0x180008598  pop     rsi
0x180008599  pop     rbp
0x18000859a  pop     rbx
0x18000859b  retn
```
