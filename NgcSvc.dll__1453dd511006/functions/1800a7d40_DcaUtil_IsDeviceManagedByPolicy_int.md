# DcaUtil::IsDeviceManagedByPolicy(int *)

- ea: `0x1800a7d40`
- end: `0x1800a7f5d`
- name: `?IsDeviceManagedByPolicy@DcaUtil@@YAJPEAH@Z`
- size: `541`
- prototype: `__int64 __fastcall(DcaUtil *__hidden this, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a7f64`

## callees

- `0x18004826c`
- `0x180048394`
- `0x18004aa08`
- `0x18005cee0`
- `0x18005dd44`
- `0x1800a7ce0`
- `0x1800a7d10`
- `0x1800a7d40`
- `0x1800ab228`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800a7dbc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800a7dbc`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800a7e08`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x1800a7e08`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x1800a7eea`
- `MDMRegistration!IsDeviceRegisteredWithManagement` at `0x1800a7eea`

## string_xrefs

- `0x1800a7dd0`: `onecore\ds\security\devicecredential\service\util\policyutil.cpp`
- `0x1800a7e1c`: `onecore\ds\security\devicecredential\service\util\policyutil.cpp`
- `0x1800a7eb0`: `onecore\ds\security\devicecredential\service\util\policyutil.cpp`
- `0x1800a7f0d`: `onecore\ds\security\devicecredential\service\util\policyutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DcaUtil::IsDeviceManagedByPolicy(DcaUtil *this, int *a2)
{
  NTSTATUS v3; // eax
  NTSTATUS v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  int IsJoined; // eax
  unsigned int v10; // ebx
  unsigned int v11; // eax
  int v12; // [rsp+20h] [rbp-E0h]
  int v13; // [rsp+30h] [rbp-D0h] BYREF
  int v14; // [rsp+34h] [rbp-CCh] BYREF
  PVOID PolicyHandle; // [rsp+38h] [rbp-C8h] BYREF
  PVOID Buffer; // [rsp+40h] [rbp-C0h] BYREF
  PVOID *p_Buffer; // [rsp+48h] [rbp-B8h] BYREF
  __int16 v18; // [rsp+50h] [rbp-B0h]
  PVOID *p_PolicyHandle; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v20; // [rsp+60h] [rbp-A0h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v22[6]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v23[528]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  *(_DWORD *)this = 0;
  v22[2] = 1;
  v22[0] = 12;
  v22[1] = 2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  ObjectAttributes.SecurityQualityOfService = v22;
  PolicyHandle = 0;
  v3 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
  if ( v3 < 0 )
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x30,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\policyutil.cpp",
             (const char *)(unsigned int)v3,
             v12);
  p_PolicyHandle = &PolicyHandle;
  v20 = 256;
  Buffer = 0;
  v5 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
  if ( v5 >= 0 )
  {
    p_Buffer = &Buffer;
    v18 = 256;
    if ( *((_WORD *)Buffer + 8) || *((_WORD *)Buffer + 16) || *((_QWORD *)Buffer + 8) )
      goto LABEL_16;
    v13 = 0;
    IsJoined = DeviceRegistrationStateApi::IsJoined(v7, v6, &v13);
    v10 = IsJoined;
    if ( IsJoined < 0 )
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DsrIsDeviceJoinedEx",
        L"DeviceRegistrationStateApi::IsJoined",
        (unsigned int)IsJoined);
      if ( v10 != -2147024894 )
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\policyutil.cpp",
          (const char *)v10,
          v12);
    }
    if ( v13 )
      goto LABEL_16;
    memset_0(v23, 0, 0x208u);
    v14 = 0;
    v11 = IsDeviceRegisteredWithManagement(&v14, 260, v23);
    if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024894 )
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\policyutil.cpp",
        (const char *)v11,
        v12);
    if ( v14 )
LABEL_16:
      *(_DWORD *)this = 1;
    wil::details::ScopeExitFnGuard__lambda_aafe4c38ed399a0368f1716b4a830146___::operator()(&p_Buffer);
    v8 = 0;
  }
  else
  {
    v8 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x3A,
           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\policyutil.cpp",
           (const char *)(unsigned int)v5,
           v12);
  }
  wil::details::ScopeExitFnGuard__lambda_f2d28925c14ada413682b82bbc3af1ce___::operator()(&p_PolicyHandle);
  return v8;
}

```

## disassembly

```asm
0x1800a7d40  push    rbp
0x1800a7d42  push    rbx
0x1800a7d43  push    rsi
0x1800a7d44  push    rdi
0x1800a7d45  lea     rbp, [rsp-1D8h]
0x1800a7d4d  sub     rsp, 2D8h
0x1800a7d54  mov     rax, cs:__security_cookie
0x1800a7d5b  xor     rax, rsp
0x1800a7d5e  mov     [rbp+1F0h+var_30], rax
0x1800a7d65  mov     rdi, rcx
0x1800a7d68  xor     esi, esi
0x1800a7d6a  mov     [rcx], esi
0x1800a7d6c  mov     [rbp+1F0h+var_250], 1
0x1800a7d73  mov     [rbp+1F0h+var_258], 0Ch
0x1800a7d7a  mov     [rbp+1F0h+var_254], 2
0x1800a7d81  mov     qword ptr [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x1800a7d8a  mov     qword ptr [rbp+1F0h+ObjectAttributes.Attributes], rsi
0x1800a7d8e  lea     ebx, [rsi+30h]
0x1800a7d91  mov     [rsp+2F0h+ObjectAttributes.RootDirectory], rsi
0x1800a7d96  mov     [rsp+2F0h+ObjectAttributes.ObjectName], rsi
0x1800a7d9b  mov     [rbp+1F0h+ObjectAttributes.SecurityDescriptor], rsi
0x1800a7d9f  lea     rax, [rbp+1F0h+var_258]
0x1800a7da3  mov     [rbp+1F0h+ObjectAttributes.SecurityQualityOfService], rax
0x1800a7da7  mov     [rsp+2F0h+PolicyHandle], rsi
0x1800a7dac  lea     r9, [rsp+2F0h+PolicyHandle]; PolicyHandle
0x1800a7db1  lea     r8d, [rsi+1]; DesiredAccess
0x1800a7db5  lea     rdx, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x1800a7dba  xor     ecx, ecx; SystemName
0x1800a7dbc  call    cs:__imp_LsaOpenPolicy
0x1800a7dc2  test    eax, eax
0x1800a7dc4  jns     short loc_1800A7DE3
0x1800a7dc6  mov     rcx, [rbp+1F8h]; this
0x1800a7dcd  mov     r9d, eax; char *
0x1800a7dd0  lea     r8, aOnecoreDsSecur_44; "onecore\\ds\\security\\devicecredential"...
0x1800a7dd7  mov     edx, ebx; void *
0x1800a7dd9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a7dde  jmp     loc_1800A7F42
0x1800a7de3  lea     rax, [rsp+2F0h+PolicyHandle]
0x1800a7de8  mov     [rsp+2F0h+var_298], rax
0x1800a7ded  mov     [rsp+2F0h+var_290], 100h
0x1800a7df4  mov     [rsp+2F0h+Buffer], rsi
0x1800a7df9  lea     r8, [rsp+2F0h+Buffer]; Buffer
0x1800a7dfe  mov     edx, 0Ch; InformationClass
0x1800a7e03  mov     rcx, [rsp+2F0h+PolicyHandle]; PolicyHandle
0x1800a7e08  call    cs:__imp_LsaQueryInformationPolicy
0x1800a7e0e  test    eax, eax
0x1800a7e10  jns     short loc_1800A7E34
0x1800a7e12  mov     rcx, [rbp+1F8h]; this
0x1800a7e19  mov     r9d, eax; char *
0x1800a7e1c  lea     r8, aOnecoreDsSecur_44; "onecore\\ds\\security\\devicecredential"...
0x1800a7e23  mov     edx, 3Ah ; ':'; void *
0x1800a7e28  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a7e2d  mov     ebx, eax
0x1800a7e2f  jmp     loc_1800A7F36
0x1800a7e34  lea     rax, [rsp+2F0h+Buffer]
0x1800a7e39  mov     [rsp+2F0h+var_2A8], rax
0x1800a7e3e  mov     [rsp+2F0h+var_2A0], 100h
0x1800a7e45  mov     rax, [rsp+2F0h+Buffer]
0x1800a7e4a  cmp     [rax+10h], si
0x1800a7e4e  jnz     loc_1800A7F24
0x1800a7e54  cmp     [rax+20h], si
0x1800a7e58  jnz     loc_1800A7F24
0x1800a7e5e  cmp     [rax+40h], rsi
0x1800a7e62  jnz     loc_1800A7F24
0x1800a7e68  mov     [rsp+2F0h+var_2C0], esi
0x1800a7e6c  mov     [rsp+2F0h+var_2C8], rsi
0x1800a7e71  lea     r8, [rsp+2F0h+var_2C0]
0x1800a7e76  call    ?IsJoined@DeviceRegistrationStateApi@@SAJPEBGW4_JOIN_TYPE@@PEAH2PEAPEBU_CERT_CONTEXT@@2@Z; DeviceRegistrationStateApi::IsJoined(ushort const *,_JOIN_TYPE,int *,int *,_CERT_CONTEXT const * *,int *)
0x1800a7e7b  mov     ebx, eax
0x1800a7e7d  test    eax, eax
0x1800a7e7f  jns     short loc_1800A7EC1
0x1800a7e81  mov     r9d, eax
0x1800a7e84  lea     r8, aDeviceregistra_1; "DeviceRegistrationStateApi::IsJoined"
0x1800a7e8b  lea     rdx, aDsrisdevicejoi; "DsrIsDeviceJoinedEx"
0x1800a7e92  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800a7e99  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800a7e9e  cmp     ebx, 80070002h
0x1800a7ea4  jz      short loc_1800A7EC1
0x1800a7ea6  mov     rcx, [rbp+1F8h]; this
0x1800a7ead  mov     r9d, ebx; char *
0x1800a7eb0  lea     r8, aOnecoreDsSecur_44; "onecore\\ds\\security\\devicecredential"...
0x1800a7eb7  mov     edx, 4Eh ; 'N'; void *
0x1800a7ebc  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a7ec1  cmp     [rsp+2F0h+var_2C0], esi
0x1800a7ec5  jnz     short loc_1800A7F24
0x1800a7ec7  xor     edx, edx; Val
0x1800a7ec9  mov     r8d, 208h; Size
0x1800a7ecf  lea     rcx, [rbp+1F0h+var_240]; void *
0x1800a7ed3  call    memset_0
0x1800a7ed8  mov     [rsp+2F0h+var_2BC], esi
0x1800a7edc  lea     r8, [rbp+1F0h+var_240]
0x1800a7ee0  mov     edx, 104h
0x1800a7ee5  lea     rcx, [rsp+2F0h+var_2BC]
0x1800a7eea  call    cs:__imp_IsDeviceRegisteredWithManagement
0x1800a7ef0  mov     edx, 80000000h
0x1800a7ef5  lea     ecx, [rax+rdx]
0x1800a7ef8  test    edx, ecx
0x1800a7efa  jnz     short loc_1800A7F1E
0x1800a7efc  cmp     eax, 80070002h
0x1800a7f01  jz      short loc_1800A7F1E
0x1800a7f03  mov     rcx, [rbp+1F8h]; this
0x1800a7f0a  mov     r9d, eax; char *
0x1800a7f0d  lea     r8, aOnecoreDsSecur_44; "onecore\\ds\\security\\devicecredential"...
0x1800a7f14  mov     edx, 5Ch ; '\'; void *
0x1800a7f19  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800a7f1e  cmp     [rsp+2F0h+var_2BC], esi
0x1800a7f22  jz      short loc_1800A7F2A
0x1800a7f24  mov     dword ptr [rdi], 1
0x1800a7f2a  lea     rcx, [rsp+2F0h+var_2A8]
0x1800a7f2f  call    wil__details__ScopeExitFnGuard__lambda_aafe4c38ed399a0368f1716b4a830146_____operator__
0x1800a7f34  mov     ebx, esi
0x1800a7f36  lea     rcx, [rsp+2F0h+var_298]
0x1800a7f3b  call    wil__details__ScopeExitFnGuard__lambda_f2d28925c14ada413682b82bbc3af1ce_____operator__
0x1800a7f40  mov     eax, ebx
0x1800a7f42  mov     rcx, [rbp+1F0h+var_30]
0x1800a7f49  xor     rcx, rsp; StackCookie
0x1800a7f4c  call    __security_check_cookie
0x1800a7f51  add     rsp, 2D8h
0x1800a7f58  pop     rdi
0x1800a7f59  pop     rsi
0x1800a7f5a  pop     rbx
0x1800a7f5b  pop     rbp
0x1800a7f5c  retn
```
