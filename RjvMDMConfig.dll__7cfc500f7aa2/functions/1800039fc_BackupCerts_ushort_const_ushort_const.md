# BackupCerts(ushort const *,ushort const *)

- ea: `0x1800039fc`
- end: `0x180003ae9`
- name: `?BackupCerts@@YAJPEBG0@Z`
- size: `237`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x1800049f8`

## callees

- `0x180003910`
- `0x180003938`
- `0x1800039fc`
- `0x180004df4`
- `0x180004e3c`
- `0x18000533c`
- `0x18000562c`
- `0x180005688`
- `0x180005a74`
- `0x180005dc4`

## string_xrefs

- `0x180003a54`: `GetInstalledCert Client 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BackupCerts(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int v4; // r9d
  unsigned int InstalledCert; // eax
  __int64 v6; // rcx
  const unsigned __int16 *v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int *v12; // [rsp+20h] [rbp-20h]
  struct _CRYPTOAPI_BLOB v13; // [rsp+30h] [rbp-10h] BYREF
  void *v14; // [rsp+60h] [rbp+20h] BYREF
  struct _CERT_CONTEXT *v15; // [rsp+68h] [rbp+28h] BYREF

  v13 = 0;
  v15 = 0;
  v14 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
    &v15,
    0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v14,
    0);
  InstalledCert = GetInstalledCert(a2, &v14, (const struct _CERT_CONTEXT **)&v15, v4, v12);
  WdsSetupLogMessageW(0x2000000u, L"GetInstalledCert Client 0x%x", InstalledCert);
  v8 = ExportCert(v6, v15, v7, &v13);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = SaveFile(a1, &v13);
    v9 = v10;
    if ( v10 >= 0 )
    {
      SafeHeapFree(v13.pbData);
      v13.pbData = 0;
    }
    else
    {
      WdsSetupLogMessageW(0x2000000u, L"SaveFile 0x%x", (unsigned int)v10);
    }
  }
  else
  {
    WdsSetupLogMessageW(0x2000000u, L"ExportCert Client 0x%x", (unsigned int)v8);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v14);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v15);
  SafeHeapFree(v13.pbData);
  return v9;
}

```

## disassembly

```asm
0x1800039fc  mov     [rsp-8+arg_0], rbx
0x180003a01  mov     [rsp-8+arg_8], rdi
0x180003a06  push    rbp
0x180003a07  mov     rbp, rsp
0x180003a0a  sub     rsp, 40h
0x180003a0e  mov     rbx, rdx
0x180003a11  mov     rdi, rcx
0x180003a14  xorps   xmm0, xmm0
0x180003a17  movups  xmmword ptr [rbp+var_10.cbData], xmm0
0x180003a1b  mov     [rbp+arg_18], 0
0x180003a23  mov     [rbp+arg_10], 0
0x180003a2b  xor     edx, edx
0x180003a2d  lea     rcx, [rbp+arg_18]
0x180003a31  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180003a36  xor     edx, edx
0x180003a38  lea     rcx, [rbp+arg_10]
0x180003a3c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003a41  lea     r8, [rbp+arg_18]; struct _CERT_CONTEXT **
0x180003a45  lea     rdx, [rbp+arg_10]; void **
0x180003a49  mov     rcx, rbx; unsigned __int16 *
0x180003a4c  call    ?GetInstalledCert@@YAJPEBGPEAPEAXPEAPEBU_CERT_CONTEXT@@HPEAK@Z; GetInstalledCert(ushort const *,void * *,_CERT_CONTEXT const * *,int,ulong *)
0x180003a51  mov     r8d, eax
0x180003a54  lea     rdx, aGetinstalledce; "GetInstalledCert Client 0x%x"
0x180003a5b  mov     ecx, 2000000h; unsigned int
0x180003a60  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x180003a65  lea     r9, [rbp+var_10]; struct _CRYPTOAPI_BLOB *
0x180003a69  mov     rdx, [rbp+arg_18]; struct _CERT_CONTEXT *
0x180003a6d  call    ?ExportCert@@YAJHPEBU_CERT_CONTEXT@@PEBGPEAU_CRYPTOAPI_BLOB@@@Z; ExportCert(int,_CERT_CONTEXT const *,ushort const *,_CRYPTOAPI_BLOB *)
0x180003a72  mov     ebx, eax
0x180003a74  test    eax, eax
0x180003a76  jns     short loc_180003A8E
0x180003a78  lea     rdx, aExportcertClie; "ExportCert Client 0x%x"
0x180003a7f  mov     r8d, eax
0x180003a82  mov     ecx, 2000000h; unsigned int
0x180003a87  call    ?WdsSetupLogMessageW@@YAXKPEBGZZ; WdsSetupLogMessageW(ulong,ushort const *,...)
0x180003a8c  jmp     short loc_180003ABA
0x180003a8e  lea     rdx, [rbp+var_10]; struct _CRYPTOAPI_BLOB *
0x180003a92  mov     rcx, rdi; unsigned __int16 *
0x180003a95  call    ?SaveFile@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z; SaveFile(ushort const *,_CRYPTOAPI_BLOB *)
0x180003a9a  mov     ebx, eax
0x180003a9c  test    eax, eax
0x180003a9e  jns     short loc_180003AA9
0x180003aa0  lea     rdx, aSavefile0xX; "SaveFile 0x%x"
0x180003aa7  jmp     short loc_180003A7F
0x180003aa9  mov     rcx, [rbp+var_10.pbData]; void *
0x180003aad  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180003ab2  mov     [rbp+var_10.pbData], 0
0x180003aba  lea     rcx, [rbp+arg_10]
0x180003abe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180003ac3  nop
0x180003ac4  lea     rcx, [rbp+arg_18]
0x180003ac8  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180003acd  mov     rcx, [rbp+var_10.pbData]; void *
0x180003ad1  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x180003ad6  mov     eax, ebx
0x180003ad8  mov     rbx, [rsp+40h+arg_0]
0x180003add  mov     rdi, [rsp+40h+arg_8]
0x180003ae2  add     rsp, 40h
0x180003ae6  pop     rbp
0x180003ae7  retn
```
