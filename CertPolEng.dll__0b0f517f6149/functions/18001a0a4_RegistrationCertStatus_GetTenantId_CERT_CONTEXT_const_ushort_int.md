# RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)

- ea: `0x18001a0a4`
- end: `0x18001a1be`
- name: `?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z`
- size: `282`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT *, unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180009010`

## callees

- `0x18000ad2c`
- `0x18000ae60`
- `0x18000b32c`
- `0x18000b3c4`
- `0x18001943c`
- `0x18001a0a4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a146`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a192`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a146`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a192`

## string_xrefs

- `0x18001a16d`: `CopyStringW`
- `0x18001a115`: `RegistrationCertStatus::GetTenantIdExtensionValue`

## pseudocode

```c
__int64 __fastcall RegistrationCertStatus::GetTenantId(const struct _CERT_CONTEXT *a1, unsigned __int16 **a2, int *a3)
{
  __int64 ExtensionGuidValueByOid; // rbx
  const wchar_t *v6; // rbp

  if ( a3 )
    *a3 = 0;
  if ( !a2 )
  {
    LODWORD(ExtensionGuidValueByOid) = -2147024809;
    Logger::TraceError(
      (const unsigned __int16 *)&stru_18001E5B8.hCertStore,
      L"RegistrationCertStatus::GetTenantId",
      L"ppszOutBuffer");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"RegistrationCertStatus::GetTenantId", L"ppszOutBuffer");
    goto LABEL_12;
  }
  *a2 = 0;
  v6 = L"RegistrationCertStatus::GetTenantIdExtensionValue";
  ExtensionGuidValueByOid = (unsigned int)CertificateUtil::FindExtensionGuidValueByOid(
                                            "1.2.840.113556.1.5.284.5",
                                            a1,
                                            a2);
  Logger::TraceVerbose(
    L"%s - hr: 0x%08x",
    L"RegistrationCertStatus::GetTenantIdExtensionValue",
    ExtensionGuidValueByOid);
  if ( (_DWORD)ExtensionGuidValueByOid != -2146885628 )
  {
    if ( (int)ExtensionGuidValueByOid >= 0 )
      goto LABEL_12;
LABEL_11:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"RegistrationCertStatus::GetTenantId",
      v6,
      (unsigned int)ExtensionGuidValueByOid);
    operator delete(*a2);
    *a2 = 0;
    goto LABEL_12;
  }
  if ( a3 )
    *a3 = 1;
  operator delete(*a2);
  *a2 = 0;
  LODWORD(ExtensionGuidValueByOid) = CopyStringW(L"383a3889-5bc9-47a3-846c-2b70f0b7fe0e", 36, a2);
  if ( (int)ExtensionGuidValueByOid < 0 )
  {
    v6 = L"CopyStringW";
    goto LABEL_11;
  }
LABEL_12:
  Logger::TraceVerbose(
    L"%s - hr: 0x%08x",
    L"RegistrationCertStatus::GetTenantId",
    (unsigned int)ExtensionGuidValueByOid);
  return (unsigned int)ExtensionGuidValueByOid;
}

```

## disassembly

```asm
0x18001a0a4  push    rbx
0x18001a0a6  push    rbp
0x18001a0a7  push    rsi
0x18001a0a8  push    rdi
0x18001a0a9  push    r15
0x18001a0ab  sub     rsp, 20h
0x18001a0af  mov     rsi, r8
0x18001a0b2  mov     rdi, rdx
0x18001a0b5  test    r8, r8
0x18001a0b8  jz      short loc_18001A0C1
0x18001a0ba  mov     dword ptr [r8], 0
0x18001a0c1  lea     r15, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x18001a0c8  test    rdi, rdi
0x18001a0cb  jnz     short loc_18001A0FC
0x18001a0cd  lea     r8, aPpszoutbuffer; "ppszOutBuffer"
0x18001a0d4  mov     rdx, r15
0x18001a0d7  lea     rcx, stru_18001E5B8.hCertStore; unsigned __int16 *
0x18001a0de  mov     ebx, 80070057h
0x18001a0e3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001a0e8  lea     rdx, aPpszoutbuffer; "ppszOutBuffer"
0x18001a0ef  mov     rcx, r15; unsigned __int16 *
0x18001a0f2  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18001a0f7  jmp     loc_18001A19F
0x18001a0fc  mov     qword ptr [rdx], 0
0x18001a103  mov     r8, rdi; unsigned __int16 **
0x18001a106  mov     rdx, rcx; struct _CERT_CONTEXT *
0x18001a109  lea     rcx, a12840113556152; "1.2.840.113556.1.5.284.5"
0x18001a110  call    ?FindExtensionGuidValueByOid@CertificateUtil@@SAJPEBDPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::FindExtensionGuidValueByOid(char const *,_CERT_CONTEXT const *,ushort * *)
0x18001a115  lea     rbp, aRegistrationce; "RegistrationCertStatus::GetTenantIdExte"...
0x18001a11c  mov     r8d, eax
0x18001a11f  mov     rdx, rbp
0x18001a122  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18001a129  mov     ebx, eax
0x18001a12b  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001a130  cmp     ebx, 80092004h
0x18001a136  jnz     short loc_18001A176
0x18001a138  test    rsi, rsi
0x18001a13b  jz      short loc_18001A143
0x18001a13d  mov     dword ptr [rsi], 1
0x18001a143  mov     rcx, [rdi]
0x18001a146  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a14c  mov     r8, rdi; unsigned __int16 **
0x18001a14f  mov     qword ptr [rdi], 0
0x18001a156  mov     edx, 24h ; '$'; unsigned __int64
0x18001a15b  lea     rcx, Source; "383a3889-5bc9-47a3-846c-2b70f0b7fe0e"
0x18001a162  call    ?CopyStringW@@YAJPEBG_KPEAPEAG@Z; CopyStringW(ushort const *,unsigned __int64,ushort * *)
0x18001a167  mov     ebx, eax
0x18001a169  test    eax, eax
0x18001a16b  jns     short loc_18001A19F
0x18001a16d  lea     rbp, aCopystringw; "CopyStringW"
0x18001a174  jmp     short loc_18001A17A
0x18001a176  test    ebx, ebx
0x18001a178  jns     short loc_18001A19F
0x18001a17a  mov     rdx, r15
0x18001a17d  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x."
0x18001a184  mov     r9d, ebx
0x18001a187  mov     r8, rbp
0x18001a18a  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18001a18f  mov     rcx, [rdi]
0x18001a192  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a198  mov     qword ptr [rdi], 0
0x18001a19f  mov     r8d, ebx
0x18001a1a2  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x18001a1a9  mov     rdx, r15
0x18001a1ac  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18001a1b1  mov     eax, ebx
0x18001a1b3  add     rsp, 20h
0x18001a1b7  pop     r15
0x18001a1b9  pop     rdi
0x18001a1ba  pop     rsi
0x18001a1bb  pop     rbp
0x18001a1bc  pop     rbx
0x18001a1bd  retn
```
