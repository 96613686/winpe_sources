# JoinStatusStorage::GetExistingDeviceKeyPath(int,_CERT_CONTEXT const *,RegistryPath &)

- ea: `0x18007ddc4`
- end: `0x18007df9c`
- name: `?GetExistingDeviceKeyPath@JoinStatusStorage@@CAJHPEBU_CERT_CONTEXT@@AEAVRegistryPath@@@Z`
- size: `472`
- prototype: `static int(int, const struct _CERT_CONTEXT *, struct RegistryPath *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x18007e3c8`

## callees

- `0x180007db4`
- `0x18007cad4`
- `0x18007d1b8`
- `0x18007d1f4`
- `0x18007d2a4`
- `0x18007ddc4`
- `0x18007dfa4`
- `0x1800805c4`
- `0x1800812c0`
- `0x180081f28`

## string_xrefs

- `0x18007de3d`: `JoinStatusStorage::InitJoinStatusRegPath`
- `0x18007df49`: `RegistryPath::Append`
- `0x18007ddf6`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18007de44`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18007de71`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18007de9a`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18007decc`: `JoinStatusStorage::GetExistingDeviceKeyPath`
- `0x18007ded9`: `RegistryPath::SubKeyExists`
- `0x18007df26`: `%s: Registry key based on certificate thumbprint (%s) does not exist. Using registry key based on device ID (%s) ...`

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
  v9 = RegistryPath::Append(a3, L"JoinInfo");
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
    v9 = RegistryPath::Append(a3, v12);
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
  operator delete(v3);
  operator delete(v4);
  return v7;
}

```

## disassembly

```asm
0x18007ddc4  mov     rax, rsp
0x18007ddc7  mov     [rax+8], rbx
0x18007ddcb  mov     [rax+18h], rbp
0x18007ddcf  push    rsi
0x18007ddd0  push    rdi
0x18007ddd1  push    r12
0x18007ddd3  push    r14
0x18007ddd5  push    r15
0x18007ddd7  sub     rsp, 30h
0x18007dddb  xor     ebp, ebp
0x18007dddd  xor     r14d, r14d
0x18007dde0  mov     [rax+20h], rbp
0x18007dde4  mov     r12, r8
0x18007dde7  mov     [rax-38h], r14
0x18007ddeb  mov     r15, rdx
0x18007ddee  mov     [rax+10h], ebp
0x18007ddf1  test    rdx, rdx
0x18007ddf4  jnz     short loc_18007DE2C
0x18007ddf6  lea     rdi, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18007ddfd  mov     ebx, 80070057h
0x18007de02  mov     rdx, rdi
0x18007de05  lea     r8, aPcert; "pCert"
0x18007de0c  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007de13  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007de18  lea     rdx, aPcert; "pCert"
0x18007de1f  mov     rcx, rdi; unsigned __int16 *
0x18007de22  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007de27  jmp     loc_18007DF73
0x18007de2c  mov     rdx, r12; struct RegistryPath *
0x18007de2f  call    ?InitJoinStatusRegPath@JoinStatusStorage@@CAJHAEAVRegistryPath@@@Z; JoinStatusStorage::InitJoinStatusRegPath(int,RegistryPath &)
0x18007de34  mov     ebx, eax
0x18007de36  test    eax, eax
0x18007de38  jns     short loc_18007DE5C
0x18007de3a  mov     r9d, eax
0x18007de3d  lea     r8, aJoinstatusstor_0; "JoinStatusStorage::InitJoinStatusRegPat"...
0x18007de44  lea     rdx, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18007de4b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007de52  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007de57  jmp     loc_18007DF73
0x18007de5c  lea     rdx, aJoininfo; "JoinInfo"
0x18007de63  mov     rcx, r12; this
0x18007de66  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18007de6b  mov     esi, eax
0x18007de6d  test    eax, eax
0x18007de6f  jz      short loc_18007DE7D
0x18007de71  lea     rdi, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18007de78  jmp     loc_18007DF49
0x18007de7d  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x18007de82  mov     rcx, r15; struct _CERT_CONTEXT *
0x18007de85  call    ?GetCertificateThumbprint@CertificateUtil@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; CertificateUtil::GetCertificateThumbprint(_CERT_CONTEXT const *,ushort * *)
0x18007de8a  mov     ebx, eax
0x18007de8c  test    eax, eax
0x18007de8e  jns     short loc_18007DEB7
0x18007de90  mov     r9d, eax
0x18007de93  lea     r8, aCertificateuti_0; "CertificateUtil::GetCertificateThumbpri"...
0x18007de9a  lea     rdx, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18007dea1  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007dea8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007dead  mov     rbp, [rsp+58h+arg_18]
0x18007deb2  jmp     loc_18007DF73
0x18007deb7  mov     rbp, [rsp+58h+arg_18]
0x18007debc  lea     r8, [rsp+58h+arg_8]; int *
0x18007dec1  mov     rdx, rbp; unsigned __int16 *
0x18007dec4  mov     rcx, r12; this
0x18007dec7  call    ?SubKeyExists@RegistryPath@@QEBAKPEBGPEAH@Z; RegistryPath::SubKeyExists(ushort const *,int *)
0x18007decc  lea     rdi, aJoinstatusstor_2; "JoinStatusStorage::GetExistingDeviceKey"...
0x18007ded3  mov     esi, eax
0x18007ded5  test    eax, eax
0x18007ded7  jz      short loc_18007DEE2
0x18007ded9  lea     r8, aRegistrypathSu; "RegistryPath::SubKeyExists"
0x18007dee0  jmp     short loc_18007DF50
0x18007dee2  cmp     [rsp+58h+arg_8], r14d
0x18007dee7  jz      short loc_18007DEEE
0x18007dee9  mov     rdx, rbp
0x18007deec  jmp     short loc_18007DF3B
0x18007deee  lea     rdx, [rsp+58h+var_38]; unsigned __int16 **
0x18007def3  mov     rcx, r15; struct _CERT_CONTEXT *
0x18007def6  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x18007defb  mov     ebx, eax
0x18007defd  mov     rdx, rdi
0x18007df00  test    eax, eax
0x18007df02  jns     short loc_18007DF21
0x18007df04  mov     r9d, eax
0x18007df07  lea     r8, aRegistrationce_4; "RegistrationCertStatus::GetDeviceId"
0x18007df0e  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007df15  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007df1a  mov     r14, [rsp+58h+var_38]
0x18007df1f  jmp     short loc_18007DF73
0x18007df21  mov     r14, [rsp+58h+var_38]
0x18007df26  lea     rcx, aSRegistryKeyBa; "%s: Registry key based on certificate t"...
0x18007df2d  mov     r9, r14
0x18007df30  mov     r8, rbp
0x18007df33  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18007df38  mov     rdx, r14; unsigned __int16 *
0x18007df3b  mov     rcx, r12; this
0x18007df3e  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x18007df43  mov     esi, eax
0x18007df45  test    eax, eax
0x18007df47  jz      short loc_18007DF73
0x18007df49  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x18007df50  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007df57  mov     r9d, esi
0x18007df5a  mov     rdx, rdi
0x18007df5d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007df62  test    esi, esi
0x18007df64  jg      short loc_18007DF6A
0x18007df66  mov     ebx, esi
0x18007df68  jmp     short loc_18007DF73
0x18007df6a  movzx   ebx, si
0x18007df6d  or      ebx, 80070000h
0x18007df73  mov     rcx, rbp; Block
0x18007df76  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007df7b  mov     rcx, r14; Block
0x18007df7e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007df83  mov     rbp, [rsp+58h+arg_10]
0x18007df88  mov     eax, ebx
0x18007df8a  mov     rbx, [rsp+58h+arg_0]
0x18007df8f  add     rsp, 30h
0x18007df93  pop     r15
0x18007df95  pop     r14
0x18007df97  pop     r12
0x18007df99  pop     rdi
0x18007df9a  pop     rsi
0x18007df9b  retn
```
