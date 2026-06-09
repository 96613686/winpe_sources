# JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)

- ea: `0x18008cde4`
- end: `0x18008cfbe`
- name: `?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z`
- size: `474`
- prototype: `static int(int, const struct _CERT_CONTEXT *, struct RegistryPath *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18008d404`

## callees

- `0x18008a340`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aecc`
- `0x18008cde4`
- `0x18008cfc4`
- `0x180090378`
- `0x18009157c`
- `0x180092704`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008cf96`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008cf9f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008cf96`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18008cf9f`

## string_xrefs

- `0x18008ce5d`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x18008ce16`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18008ce64`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18008ce91`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18008ceba`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18008ceec`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18008cf46`: `%s: Registry key based on certificate thumbprint (%s) does not exist. Using registry key based on device ID (%s) ...`
- `0x18008cf69`: `RegistryPath::Append`
- `0x18008cef9`: `RegistryPath::SubKeyExists`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::GetExistingDeviceKeyPath(
        int a1,
        const struct _CERT_CONTEXT *a2,
        struct RegistryPath *a3)
{
  unsigned __int16 *v3; // rbp
  unsigned __int16 *v4; // r14
  unsigned int v7; // ebx
  int inited; // eax
  int v9; // esi
  int CertificateThumbprint; // eax
  const wchar_t *v11; // r8
  const unsigned __int16 *v12; // rdx
  int DeviceId; // eax
  unsigned __int16 *v15; // [rsp+20h] [rbp-38h] BYREF
  int v16; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v17; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v4 = 0;
  v17 = 0;
  v15 = 0;
  v16 = 0;
  if ( !a2 )
  {
    v7 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"JoinStatusStorage::GetExistingDeviceKeyPath", L"pCert");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"JoinStatusStorage::GetExistingDeviceKeyPath", L"pCert");
    goto LABEL_20;
  }
  inited = JoinStatusStorage::InitJoinStatusRegPath(a1, a3);
  v7 = inited;
  if ( inited < 0 )
  {
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"JoinStatusStorage::GetExistingDeviceKeyPath",
      L"JoinStatusStorage::InitJoinStatusRegPath",
      (unsigned int)inited);
    goto LABEL_20;
  }
  v9 = RegistryPath::Append((const wchar_t **)a3, L"JoinInfo");
  if ( !v9 )
  {
    CertificateThumbprint = CertificateUtil::GetCertificateThumbprint(a2, &v17);
    v7 = CertificateThumbprint;
    if ( CertificateThumbprint < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"JoinStatusStorage::GetExistingDeviceKeyPath",
        L"CertificateUtil::GetCertificateThumbprint",
        (unsigned int)CertificateThumbprint);
      v3 = v17;
      goto LABEL_20;
    }
    v3 = v17;
    v9 = RegistryPath::SubKeyExists(a3, v17, &v16);
    if ( v9 )
    {
      v11 = L"RegistryPath::SubKeyExists";
      goto LABEL_17;
    }
    if ( v16 )
    {
      v12 = v3;
    }
    else
    {
      DeviceId = RegistrationCertStatus::GetDeviceId(a2, &v15);
      v7 = DeviceId;
      if ( DeviceId < 0 )
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"JoinStatusStorage::GetExistingDeviceKeyPath",
          L"RegistrationCertStatus::GetDeviceId",
          (unsigned int)DeviceId);
        v4 = v15;
        goto LABEL_20;
      }
      v4 = v15;
      Logger::TraceInformation(
        L"%s: Registry key based on certificate thumbprint (%s) does not exist. Using registry key based on device ID (%s) ...",
        L"JoinStatusStorage::GetExistingDeviceKeyPath",
        v3,
        v15);
      v12 = v4;
    }
    v9 = RegistryPath::Append((const wchar_t **)a3, v12);
    if ( !v9 )
      goto LABEL_20;
  }
  v11 = L"RegistryPath::Append";
LABEL_17:
  Logger::TraceError(
    L"%s: %s failed with win32 error code: 0x%08x.",
    L"JoinStatusStorage::GetExistingDeviceKeyPath",
    v11,
    (unsigned int)v9,
    v15);
  if ( v9 > 0 )
    v7 = (unsigned __int16)v9 | 0x80070000;
  else
    v7 = v9;
LABEL_20:
  free(v3);
  free(v4);
  return v7;
}

```

## disassembly

```asm
0x18008cde4  mov     rax, rsp
0x18008cde7  mov     [rax+8], rbx
0x18008cdeb  mov     [rax+18h], rbp
0x18008cdef  push    rsi
0x18008cdf0  push    rdi
0x18008cdf1  push    r12
0x18008cdf3  push    r14
0x18008cdf5  push    r15
0x18008cdf7  sub     rsp, 30h
0x18008cdfb  xor     ebp, ebp
0x18008cdfd  xor     r14d, r14d
0x18008ce00  mov     [rax+20h], rbp
0x18008ce04  mov     r12, r8
0x18008ce07  mov     [rax-38h], r14
0x18008ce0b  mov     r15, rdx
0x18008ce0e  mov     [rax+10h], ebp
0x18008ce11  test    rdx, rdx
0x18008ce14  jnz     short loc_18008CE4C
0x18008ce16  lea     rdi, aJoinstatusstor_6; "JoinStatusStorage::GetExistingDeviceKey"...
0x18008ce1d  mov     ebx, 80070057h
0x18008ce22  mov     rdx, rdi
0x18008ce25  lea     r8, aPcert; "pCert"
0x18008ce2c  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008ce33  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008ce38  lea     rdx, aPcert; "pCert"
0x18008ce3f  mov     rcx, rdi; unsigned __int16 *
0x18008ce42  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18008ce47  jmp     loc_18008CF93
0x18008ce4c  mov     rdx, r12; struct RegistryPath *
0x18008ce4f  call    ?InitJoinStatusRegPath@JoinStatusStorage@@CAJHAEAVRegistryPath@@@Z; JoinStatusStorage::InitJoinStatusRegPath(int,RegistryPath &)
0x18008ce54  mov     ebx, eax
0x18008ce56  test    eax, eax
0x18008ce58  jns     short loc_18008CE7C
0x18008ce5a  mov     r9d, eax
0x18008ce5d  lea     r8, aJoinstatusstor_4; "JoinStatusStorage::InitJoinStatusRegPat"...
0x18008ce64  lea     rdx, aJoinstatusstor_6; "JoinStatusStorage::GetExistingDeviceKey"...
0x18008ce6b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008ce72  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008ce77  jmp     loc_18008CF93
0x18008ce7c  lea     rdx, aJoininfo; "JoinInfo"
0x18008ce83  mov     rcx, r12; this
0x18008ce86  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18008ce8b  mov     esi, eax
0x18008ce8d  test    eax, eax
0x18008ce8f  jz      short loc_18008CE9D
0x18008ce91  lea     rdi, aJoinstatusstor_6; "JoinStatusStorage::GetExistingDeviceKey"...
0x18008ce98  jmp     loc_18008CF69
0x18008ce9d  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x18008cea2  mov     rcx, r15; struct _CERT_CONTEXT *
0x18008cea5  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18008ceaa  mov     ebx, eax
0x18008ceac  test    eax, eax
0x18008ceae  jns     short loc_18008CED7
0x18008ceb0  mov     r9d, eax
0x18008ceb3  lea     r8, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x18008ceba  lea     rdx, aJoinstatusstor_6; "JoinStatusStorage::GetExistingDeviceKey"...
0x18008cec1  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008cec8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008cecd  mov     rbp, [rsp+58h+arg_18]
0x18008ced2  jmp     loc_18008CF93
0x18008ced7  mov     rbp, [rsp+58h+arg_18]
0x18008cedc  lea     r8, [rsp+58h+arg_8]; int *
0x18008cee1  mov     rdx, rbp; unsigned __int16 *
0x18008cee4  mov     rcx, r12; this
0x18008cee7  call    ?SubKeyExists@RegistryPath@@QEBAKPEBGPEAH@Z; RegistryPath::SubKeyExists(ushort const *,int *)
0x18008ceec  lea     rdi, aJoinstatusstor_6; "JoinStatusStorage::GetExistingDeviceKey"...
0x18008cef3  mov     esi, eax
0x18008cef5  test    eax, eax
0x18008cef7  jz      short loc_18008CF02
0x18008cef9  lea     r8, aRegistrypathSu; "RegistryPath::SubKeyExists"
0x18008cf00  jmp     short loc_18008CF70
0x18008cf02  cmp     [rsp+58h+arg_8], r14d
0x18008cf07  jz      short loc_18008CF0E
0x18008cf09  mov     rdx, rbp
0x18008cf0c  jmp     short loc_18008CF5B
0x18008cf0e  lea     rdx, [rsp+58h+var_38]; unsigned __int16 **
0x18008cf13  mov     rcx, r15; struct _CERT_CONTEXT *
0x18008cf16  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x18008cf1b  mov     ebx, eax
0x18008cf1d  mov     rdx, rdi
0x18008cf20  test    eax, eax
0x18008cf22  jns     short loc_18008CF41
0x18008cf24  mov     r9d, eax
0x18008cf27  lea     r8, aRegistrationce_8; "RegistrationCertStatus::GetDeviceId"
0x18008cf2e  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008cf35  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008cf3a  mov     r14, [rsp+58h+var_38]
0x18008cf3f  jmp     short loc_18008CF93
0x18008cf41  mov     r14, [rsp+58h+var_38]
0x18008cf46  lea     rcx, aSRegistryKeyBa; "%s: Registry key based on certificate t"...
0x18008cf4d  mov     r9, r14
0x18008cf50  mov     r8, rbp
0x18008cf53  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18008cf58  mov     rdx, r14; unsigned __int16 *
0x18008cf5b  mov     rcx, r12; this
0x18008cf5e  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18008cf63  mov     esi, eax
0x18008cf65  test    eax, eax
0x18008cf67  jz      short loc_18008CF93
0x18008cf69  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x18008cf70  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008cf77  mov     r9d, esi
0x18008cf7a  mov     rdx, rdi
0x18008cf7d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008cf82  test    esi, esi
0x18008cf84  jg      short loc_18008CF8A
0x18008cf86  mov     ebx, esi
0x18008cf88  jmp     short loc_18008CF93
0x18008cf8a  movzx   ebx, si
0x18008cf8d  or      ebx, 80070000h
0x18008cf93  mov     rcx, rbp; Block
0x18008cf96  call    cs:__imp_free
0x18008cf9c  mov     rcx, r14; Block
0x18008cf9f  call    cs:__imp_free
0x18008cfa5  mov     rbp, [rsp+58h+arg_10]
0x18008cfaa  mov     eax, ebx
0x18008cfac  mov     rbx, [rsp+58h+arg_0]
0x18008cfb1  add     rsp, 30h
0x18008cfb5  pop     r15
0x18008cfb7  pop     r14
0x18008cfb9  pop     r12
0x18008cfbb  pop     rdi
0x18008cfbc  pop     rsi
0x18008cfbd  retn
```
