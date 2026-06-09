# JoinStatusStorage::ReadTenantKey(struct_join_status *,RegistryPath &,int)

- ea: `0x18008d760`
- end: `0x18008de11`
- name: `?ReadTenantKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z`
- size: `1713`
- prototype: `__int64 __fastcall(struct struct_join_status *, struct RegistryPath *this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008d404`

## callees

- `0x1800871b4`
- `0x18008aa28`
- `0x18008d760`
- `0x18008e9f0`
- `0x180092138`
- `0x180092444`

## string_xrefs

- `0x18008d78c`: `RegistryPath::OpenSubKey`
- `0x18008d7da`: `RegistryPath::ReadStringValue`
- `0x18008d8e0`: `DrsServiceVersion`
- `0x18008d874`: `MdmComplianceUrl`
- `0x18008d9b8`: `AccessTokenUrl`
- `0x18008d9ee`: `CdjServiceVersion`
- `0x18008da96`: `NgcServiceVersion`
- `0x18008db41`: `WebAuthnServiceVersion`
- `0x18008dbec`: `DeviceManagementServiceVersion`
- `0x18008d793`: `JoinStatusStorage::ReadTenantKey`
- `0x18008d7cc`: `JoinStatusStorage::ReadTenantKey`

## pseudocode

```c
__int64 __fastcall JoinStatusStorage::ReadTenantKey(void **a1, struct RegistryPath *this, int a3)
{
  unsigned int v6; // eax
  unsigned int StringValue; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  int v35; // eax

  v6 = RegistryPath::OpenSubKey(this, (unsigned int)this, a3);
  if ( v6 )
  {
    Logger::TraceError(
      L"%s: %s failed with win32 error code: 0x%08x.",
      L"JoinStatusStorage::ReadTenantKey",
      L"RegistryPath::OpenSubKey",
      v6);
  }
  else
  {
    SafeFree(a1[4]);
    a1[4] = 0;
    StringValue = RegistryPath::ReadStringValue(this, L"DisplayName", (unsigned __int16 **)a1 + 4);
    if ( StringValue )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        StringValue);
    SafeFree(a1[5]);
    a1[5] = 0;
    v8 = RegistryPath::ReadStringValue(this, L"MdmEnrollmentUrl", (unsigned __int16 **)a1 + 5);
    if ( v8 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v8);
    SafeFree(a1[6]);
    a1[6] = 0;
    v9 = RegistryPath::ReadStringValue(this, L"MdmTermsOfUseUrl", (unsigned __int16 **)a1 + 6);
    if ( v9 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v9);
    SafeFree(a1[7]);
    a1[7] = 0;
    v10 = RegistryPath::ReadStringValue(this, L"MdmComplianceUrl", (unsigned __int16 **)a1 + 7);
    if ( v10 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v10);
    SafeFree(a1[8]);
    a1[8] = 0;
    v11 = RegistryPath::ReadStringValue(this, L"UserSettingSyncUrl", (unsigned __int16 **)a1 + 8);
    if ( v11 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v11);
    SafeFree(a1[9]);
    a1[9] = 0;
    v12 = RegistryPath::ReadStringValue(this, L"DrsServiceVersion", (unsigned __int16 **)a1 + 9);
    if ( v12 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v12);
    SafeFree(a1[10]);
    a1[10] = 0;
    v13 = RegistryPath::ReadStringValue(this, L"DrsEndpoint", (unsigned __int16 **)a1 + 10);
    if ( v13 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v13);
    SafeFree(a1[11]);
    a1[11] = 0;
    v14 = RegistryPath::ReadStringValue(this, L"DrsResourceId", (unsigned __int16 **)a1 + 11);
    if ( v14 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v14);
    SafeFree(a1[12]);
    a1[12] = 0;
    v15 = RegistryPath::ReadStringValue(this, L"AuthCodeUrl", (unsigned __int16 **)a1 + 12);
    if ( v15 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v15);
    SafeFree(a1[13]);
    a1[13] = 0;
    v16 = RegistryPath::ReadStringValue(this, L"AccessTokenUrl", (unsigned __int16 **)a1 + 13);
    if ( v16 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v16);
    SafeFree(a1[14]);
    a1[14] = 0;
    v17 = RegistryPath::ReadStringValue(this, L"CdjServiceVersion", (unsigned __int16 **)a1 + 14);
    if ( v17 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v17);
    SafeFree(a1[15]);
    a1[15] = 0;
    v18 = RegistryPath::ReadStringValue(this, L"CdjEndpoint", (unsigned __int16 **)a1 + 15);
    if ( v18 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v18);
    SafeFree(a1[16]);
    a1[16] = 0;
    v19 = RegistryPath::ReadStringValue(this, L"CdjResourceId", (unsigned __int16 **)a1 + 16);
    if ( v19 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v19);
    SafeFree(a1[17]);
    a1[17] = 0;
    v20 = RegistryPath::ReadStringValue(this, L"NgcServiceVersion", (unsigned __int16 **)a1 + 17);
    if ( v20 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v20);
    SafeFree(a1[18]);
    a1[18] = 0;
    v21 = RegistryPath::ReadStringValue(this, L"NgcEndpoint", (unsigned __int16 **)a1 + 18);
    if ( v21 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v21);
    SafeFree(a1[19]);
    a1[19] = 0;
    v22 = RegistryPath::ReadStringValue(this, L"NgcResourceId", (unsigned __int16 **)a1 + 19);
    if ( v22 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v22);
    SafeFree(a1[20]);
    a1[20] = 0;
    v23 = RegistryPath::ReadStringValue(this, L"WebAuthnServiceVersion", (unsigned __int16 **)a1 + 20);
    if ( v23 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v23);
    SafeFree(a1[21]);
    a1[21] = 0;
    v24 = RegistryPath::ReadStringValue(this, L"WebAuthnEndpoint", (unsigned __int16 **)a1 + 21);
    if ( v24 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v24);
    SafeFree(a1[22]);
    a1[22] = 0;
    v25 = RegistryPath::ReadStringValue(this, L"WebAuthnResourceId", (unsigned __int16 **)a1 + 22);
    if ( v25 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v25);
    SafeFree(a1[23]);
    a1[23] = 0;
    v26 = RegistryPath::ReadStringValue(this, L"DeviceManagementServiceVersion", (unsigned __int16 **)a1 + 23);
    if ( v26 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v26);
    SafeFree(a1[24]);
    a1[24] = 0;
    v27 = RegistryPath::ReadStringValue(this, L"DeviceManagementEndpoint", (unsigned __int16 **)a1 + 24);
    if ( v27 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v27);
    SafeFree(a1[25]);
    a1[25] = 0;
    v28 = RegistryPath::ReadStringValue(this, L"DeviceManagementResourceId", (unsigned __int16 **)a1 + 25);
    if ( v28 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v28);
    SafeFree(a1[28]);
    a1[28] = 0;
    v29 = RegistryPath::ReadStringValue(this, L"RbacPolicyEndpoint", (unsigned __int16 **)a1 + 28);
    if ( v29 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v29);
    SafeFree(a1[35]);
    a1[35] = 0;
    v30 = RegistryPath::ReadStringValue(this, L"KerbSpn", (unsigned __int16 **)a1 + 35);
    if ( v30 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v30);
    SafeFree(a1[36]);
    a1[36] = 0;
    v31 = RegistryPath::ReadStringValue(this, L"KerbEndpoint", (unsigned __int16 **)a1 + 36);
    if ( v31 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v31);
    SafeFree(a1[37]);
    a1[37] = 0;
    v32 = RegistryPath::ReadStringValue(this, L"CdjEndpointTLS", (unsigned __int16 **)a1 + 37);
    if ( v32 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v32);
    SafeFree(a1[38]);
    a1[38] = 0;
    v33 = RegistryPath::ReadStringValue(this, L"DeviceManagementEndpointTLS", (unsigned __int16 **)a1 + 38);
    if ( v33 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v33);
    SafeFree(a1[39]);
    a1[39] = 0;
    v34 = RegistryPath::ReadStringValue(this, L"DeviceJoinResourceEndpointTLS", (unsigned __int16 **)a1 + 39);
    if ( v34 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"JoinStatusStorage::ReadTenantKey",
        L"RegistryPath::ReadStringValue",
        v34);
    if ( a3 )
    {
      v35 = JoinStatusStorage::SetDefaultDiscoveryMetadata(
              (struct struct_join_status *)a1,
              *(const unsigned __int16 **)this);
      if ( v35 < 0 )
        Logger::TraceError(
          L"%s: JoinStatusStorage::SetDefaultDiscoveryMetadata failed with error code: 0x%08x.",
          L"JoinStatusStorage::ReadTenantKey",
          (unsigned int)v35);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18008d760  push    rbx
0x18008d762  push    rbp
0x18008d763  push    rsi
0x18008d764  push    rdi
0x18008d765  push    r12
0x18008d767  push    r13
0x18008d769  push    r14
0x18008d76b  push    r15
0x18008d76d  sub     rsp, 28h
0x18008d771  mov     rbp, rcx
0x18008d774  mov     r15d, r8d
0x18008d777  mov     rcx, rdx; this
0x18008d77a  mov     r14, rdx
0x18008d77d  call    ?OpenSubKey@RegistryPath@@QEAAKKH@Z; RegistryPath::OpenSubKey(ulong,int)
0x18008d782  xor     r12d, r12d
0x18008d785  test    eax, eax
0x18008d787  jz      short loc_18008D7AB
0x18008d789  mov     r9d, eax
0x18008d78c  lea     r8, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18008d793  lea     rdx, aJoinstatusstor_10; "JoinStatusStorage::ReadTenantKey"
0x18008d79a  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008d7a1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d7a6  jmp     loc_18008DDFE
0x18008d7ab  lea     rbx, [rbp+20h]
0x18008d7af  mov     rcx, [rbx]; void *
0x18008d7b2  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d7b7  mov     r8, rbx; unsigned __int16 **
0x18008d7ba  mov     [rbx], r12
0x18008d7bd  lea     rdx, aDisplayname; "DisplayName"
0x18008d7c4  mov     rcx, r14; this
0x18008d7c7  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d7cc  lea     rdi, aJoinstatusstor_10; "JoinStatusStorage::ReadTenantKey"
0x18008d7d3  lea     rsi, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18008d7da  lea     r13, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18008d7e1  test    eax, eax
0x18008d7e3  jz      short loc_18008D7F6
0x18008d7e5  mov     r9d, eax
0x18008d7e8  mov     r8, r13
0x18008d7eb  mov     rdx, rdi
0x18008d7ee  mov     rcx, rsi; unsigned __int16 *
0x18008d7f1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d7f6  lea     rbx, [rbp+28h]
0x18008d7fa  mov     rcx, [rbx]; void *
0x18008d7fd  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d802  mov     r8, rbx; unsigned __int16 **
0x18008d805  mov     [rbx], r12
0x18008d808  lea     rdx, aMdmenrollmentu; "MdmEnrollmentUrl"
0x18008d80f  mov     rcx, r14; this
0x18008d812  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d817  test    eax, eax
0x18008d819  jz      short loc_18008D82C
0x18008d81b  mov     r9d, eax
0x18008d81e  mov     r8, r13
0x18008d821  mov     rdx, rdi
0x18008d824  mov     rcx, rsi; unsigned __int16 *
0x18008d827  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d82c  lea     rbx, [rbp+30h]
0x18008d830  mov     rcx, [rbx]; void *
0x18008d833  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d838  mov     r8, rbx; unsigned __int16 **
0x18008d83b  mov     [rbx], r12
0x18008d83e  lea     rdx, aMdmtermsofuseu; "MdmTermsOfUseUrl"
0x18008d845  mov     rcx, r14; this
0x18008d848  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d84d  test    eax, eax
0x18008d84f  jz      short loc_18008D862
0x18008d851  mov     r9d, eax
0x18008d854  mov     r8, r13
0x18008d857  mov     rdx, rdi
0x18008d85a  mov     rcx, rsi; unsigned __int16 *
0x18008d85d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d862  lea     rbx, [rbp+38h]
0x18008d866  mov     rcx, [rbx]; void *
0x18008d869  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d86e  mov     r8, rbx; unsigned __int16 **
0x18008d871  mov     [rbx], r12
0x18008d874  lea     rdx, aMdmcomplianceu; "MdmComplianceUrl"
0x18008d87b  mov     rcx, r14; this
0x18008d87e  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d883  test    eax, eax
0x18008d885  jz      short loc_18008D898
0x18008d887  mov     r9d, eax
0x18008d88a  mov     r8, r13
0x18008d88d  mov     rdx, rdi
0x18008d890  mov     rcx, rsi; unsigned __int16 *
0x18008d893  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d898  lea     rbx, [rbp+40h]
0x18008d89c  mov     rcx, [rbx]; void *
0x18008d89f  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d8a4  mov     r8, rbx; unsigned __int16 **
0x18008d8a7  mov     [rbx], r12
0x18008d8aa  lea     rdx, aUsersettingsyn; "UserSettingSyncUrl"
0x18008d8b1  mov     rcx, r14; this
0x18008d8b4  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d8b9  test    eax, eax
0x18008d8bb  jz      short loc_18008D8CE
0x18008d8bd  mov     r9d, eax
0x18008d8c0  mov     r8, r13
0x18008d8c3  mov     rdx, rdi
0x18008d8c6  mov     rcx, rsi; unsigned __int16 *
0x18008d8c9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d8ce  lea     rbx, [rbp+48h]
0x18008d8d2  mov     rcx, [rbx]; void *
0x18008d8d5  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d8da  mov     r8, rbx; unsigned __int16 **
0x18008d8dd  mov     [rbx], r12
0x18008d8e0  lea     rdx, aDrsservicevers; "DrsServiceVersion"
0x18008d8e7  mov     rcx, r14; this
0x18008d8ea  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d8ef  test    eax, eax
0x18008d8f1  jz      short loc_18008D904
0x18008d8f3  mov     r9d, eax
0x18008d8f6  mov     r8, r13
0x18008d8f9  mov     rdx, rdi
0x18008d8fc  mov     rcx, rsi; unsigned __int16 *
0x18008d8ff  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d904  lea     rbx, [rbp+50h]
0x18008d908  mov     rcx, [rbx]; void *
0x18008d90b  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d910  mov     r8, rbx; unsigned __int16 **
0x18008d913  mov     [rbx], r12
0x18008d916  lea     rdx, aDrsendpoint; "DrsEndpoint"
0x18008d91d  mov     rcx, r14; this
0x18008d920  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d925  test    eax, eax
0x18008d927  jz      short loc_18008D93A
0x18008d929  mov     r9d, eax
0x18008d92c  mov     r8, r13
0x18008d92f  mov     rdx, rdi
0x18008d932  mov     rcx, rsi; unsigned __int16 *
0x18008d935  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d93a  lea     rbx, [rbp+58h]
0x18008d93e  mov     rcx, [rbx]; void *
0x18008d941  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d946  mov     r8, rbx; unsigned __int16 **
0x18008d949  mov     [rbx], r12
0x18008d94c  lea     rdx, aDrsresourceid; "DrsResourceId"
0x18008d953  mov     rcx, r14; this
0x18008d956  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d95b  test    eax, eax
0x18008d95d  jz      short loc_18008D970
0x18008d95f  mov     r9d, eax
0x18008d962  mov     r8, r13
0x18008d965  mov     rdx, rdi
0x18008d968  mov     rcx, rsi; unsigned __int16 *
0x18008d96b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d970  lea     rbx, [rbp+60h]
0x18008d974  mov     rcx, [rbx]; void *
0x18008d977  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d97c  mov     r8, rbx; unsigned __int16 **
0x18008d97f  mov     [rbx], r12
0x18008d982  lea     rdx, aAuthcodeurl; "AuthCodeUrl"
0x18008d989  mov     rcx, r14; this
0x18008d98c  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d991  test    eax, eax
0x18008d993  jz      short loc_18008D9A6
0x18008d995  mov     r9d, eax
0x18008d998  mov     r8, r13
0x18008d99b  mov     rdx, rdi
0x18008d99e  mov     rcx, rsi; unsigned __int16 *
0x18008d9a1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d9a6  lea     rbx, [rbp+68h]
0x18008d9aa  mov     rcx, [rbx]; void *
0x18008d9ad  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d9b2  mov     r8, rbx; unsigned __int16 **
0x18008d9b5  mov     [rbx], r12
0x18008d9b8  lea     rdx, aAccesstokenurl; "AccessTokenUrl"
0x18008d9bf  mov     rcx, r14; this
0x18008d9c2  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d9c7  test    eax, eax
0x18008d9c9  jz      short loc_18008D9DC
0x18008d9cb  mov     r9d, eax
0x18008d9ce  mov     r8, r13
0x18008d9d1  mov     rdx, rdi
0x18008d9d4  mov     rcx, rsi; unsigned __int16 *
0x18008d9d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008d9dc  lea     rbx, [rbp+70h]
0x18008d9e0  mov     rcx, [rbx]; void *
0x18008d9e3  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008d9e8  mov     r8, rbx; unsigned __int16 **
0x18008d9eb  mov     [rbx], r12
0x18008d9ee  lea     rdx, aCdjservicevers; "CdjServiceVersion"
0x18008d9f5  mov     rcx, r14; this
0x18008d9f8  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008d9fd  test    eax, eax
0x18008d9ff  jz      short loc_18008DA12
0x18008da01  mov     r9d, eax
0x18008da04  mov     r8, r13
0x18008da07  mov     rdx, rdi
0x18008da0a  mov     rcx, rsi; unsigned __int16 *
0x18008da0d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008da12  lea     rbx, [rbp+78h]
0x18008da16  mov     rcx, [rbx]; void *
0x18008da19  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008da1e  mov     r8, rbx; unsigned __int16 **
0x18008da21  mov     [rbx], r12
0x18008da24  lea     rdx, aCdjendpoint; "CdjEndpoint"
0x18008da2b  mov     rcx, r14; this
0x18008da2e  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008da33  test    eax, eax
0x18008da35  jz      short loc_18008DA48
0x18008da37  mov     r9d, eax
0x18008da3a  mov     r8, r13
0x18008da3d  mov     rdx, rdi
0x18008da40  mov     rcx, rsi; unsigned __int16 *
0x18008da43  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008da48  lea     rbx, [rbp+80h]
0x18008da4f  mov     rcx, [rbx]; void *
0x18008da52  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008da57  mov     r8, rbx; unsigned __int16 **
0x18008da5a  mov     [rbx], r12
0x18008da5d  lea     rdx, aCdjresourceid; "CdjResourceId"
0x18008da64  mov     rcx, r14; this
0x18008da67  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008da6c  test    eax, eax
0x18008da6e  jz      short loc_18008DA81
0x18008da70  mov     r9d, eax
0x18008da73  mov     r8, r13
0x18008da76  mov     rdx, rdi
0x18008da79  mov     rcx, rsi; unsigned __int16 *
0x18008da7c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008da81  lea     rbx, [rbp+88h]
0x18008da88  mov     rcx, [rbx]; void *
0x18008da8b  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008da90  mov     r8, rbx; unsigned __int16 **
0x18008da93  mov     [rbx], r12
0x18008da96  lea     rdx, aNgcservicevers; "NgcServiceVersion"
0x18008da9d  mov     rcx, r14; this
0x18008daa0  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008daa5  test    eax, eax
0x18008daa7  jz      short loc_18008DABA
0x18008daa9  mov     r9d, eax
0x18008daac  mov     r8, r13
0x18008daaf  mov     rdx, rdi
0x18008dab2  mov     rcx, rsi; unsigned __int16 *
0x18008dab5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008daba  lea     rbx, [rbp+90h]
0x18008dac1  mov     rcx, [rbx]; void *
0x18008dac4  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008dac9  mov     r8, rbx; unsigned __int16 **
0x18008dacc  mov     [rbx], r12
0x18008dacf  lea     rdx, aNgcendpoint; "NgcEndpoint"
0x18008dad6  mov     rcx, r14; this
0x18008dad9  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008dade  test    eax, eax
0x18008dae0  jz      short loc_18008DAF3
0x18008dae2  mov     r9d, eax
0x18008dae5  mov     r8, r13
0x18008dae8  mov     rdx, rdi
0x18008daeb  mov     rcx, rsi; unsigned __int16 *
0x18008daee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008daf3  lea     rbx, [rbp+98h]
0x18008dafa  mov     rcx, [rbx]; void *
0x18008dafd  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008db02  mov     r8, rbx; unsigned __int16 **
0x18008db05  mov     [rbx], r12
0x18008db08  lea     rdx, aNgcresourceid; "NgcResourceId"
0x18008db0f  mov     rcx, r14; this
0x18008db12  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008db17  test    eax, eax
0x18008db19  jz      short loc_18008DB2C
0x18008db1b  mov     r9d, eax
0x18008db1e  mov     r8, r13
0x18008db21  mov     rdx, rdi
0x18008db24  mov     rcx, rsi; unsigned __int16 *
0x18008db27  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008db2c  lea     rbx, [rbp+0A0h]
0x18008db33  mov     rcx, [rbx]; void *
0x18008db36  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008db3b  mov     r8, rbx; unsigned __int16 **
0x18008db3e  mov     [rbx], r12
0x18008db41  lea     rdx, aWebauthnservic_0; "WebAuthnServiceVersion"
0x18008db48  mov     rcx, r14; this
0x18008db4b  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008db50  test    eax, eax
0x18008db52  jz      short loc_18008DB65
0x18008db54  mov     r9d, eax
0x18008db57  mov     r8, r13
0x18008db5a  mov     rdx, rdi
0x18008db5d  mov     rcx, rsi; unsigned __int16 *
0x18008db60  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008db65  lea     rbx, [rbp+0A8h]
0x18008db6c  mov     rcx, [rbx]; void *
0x18008db6f  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008db74  mov     r8, rbx; unsigned __int16 **
0x18008db77  mov     [rbx], r12
0x18008db7a  lea     rdx, aWebauthnendpoi; "WebAuthnEndpoint"
0x18008db81  mov     rcx, r14; this
0x18008db84  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18008db89  test    eax, eax
0x18008db8b  jz      short loc_18008DB9E
0x18008db8d  mov     r9d, eax
0x18008db90  mov     r8, r13
0x18008db93  mov     rdx, rdi
0x18008db96  mov     rcx, rsi; unsigned __int16 *
0x18008db99  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008db9e  lea     rbx, [rbp+0B0h]
0x18008dba5  mov     rcx, [rbx]; void *
0x18008dba8  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18008dbad  mov     r8, rbx; unsigned __int16 **
  ... truncated ...
```
