# JoinStatusStorage::ReadTenantKey(struct_join_status *,RegistryPath &,int)

- ea: `0x18007e710`
- end: `0x18007edc1`
- name: `?ReadTenantKey@JoinStatusStorage@@CAJPEAUstruct_join_status@@AEAVRegistryPath@@H@Z`
- size: `1713`
- prototype: `__int64 __fastcall(struct struct_join_status *, struct RegistryPath *this, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007e3c8`

## callees

- `0x180079de0`
- `0x18007d1b8`
- `0x18007e710`
- `0x18007eee0`
- `0x180081b6c`
- `0x180081db0`

## string_xrefs

- `0x18007e73c`: `RegistryPath::OpenSubKey`
- `0x18007e78a`: `RegistryPath::ReadStringValue`
- `0x18007e890`: `DrsServiceVersion`
- `0x18007e824`: `MdmComplianceUrl`
- `0x18007e968`: `AccessTokenUrl`
- `0x18007ea46`: `NgcServiceVersion`
- `0x18007e99e`: `CdjServiceVersion`
- `0x18007eaf1`: `WebAuthnServiceVersion`
- `0x18007eb9c`: `DeviceManagementServiceVersion`
- `0x18007e743`: `JoinStatusStorage::ReadTenantKey`
- `0x18007e77c`: `JoinStatusStorage::ReadTenantKey`

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
0x18007e710  push    rbx
0x18007e712  push    rbp
0x18007e713  push    rsi
0x18007e714  push    rdi
0x18007e715  push    r12
0x18007e717  push    r13
0x18007e719  push    r14
0x18007e71b  push    r15
0x18007e71d  sub     rsp, 28h
0x18007e721  mov     rbp, rcx
0x18007e724  mov     r15d, r8d
0x18007e727  mov     rcx, rdx; this
0x18007e72a  mov     r14, rdx
0x18007e72d  call    ?OpenSubKey@RegistryPath@@QEAAKKH@Z; RegistryPath::OpenSubKey(ulong,int)
0x18007e732  xor     r12d, r12d
0x18007e735  test    eax, eax
0x18007e737  jz      short loc_18007E75B
0x18007e739  mov     r9d, eax
0x18007e73c  lea     r8, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x18007e743  lea     rdx, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18007e74a  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007e751  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e756  jmp     loc_18007EDAE
0x18007e75b  lea     rbx, [rbp+20h]
0x18007e75f  mov     rcx, [rbx]; void *
0x18007e762  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e767  mov     r8, rbx; unsigned __int16 **
0x18007e76a  mov     [rbx], r12
0x18007e76d  lea     rdx, aDisplayname; "DisplayName"
0x18007e774  mov     rcx, r14; this
0x18007e777  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e77c  lea     rdi, aJoinstatusstor_4; "JoinStatusStorage::ReadTenantKey"
0x18007e783  lea     rsi, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18007e78a  lea     r13, aRegistrypathRe; "RegistryPath::ReadStringValue"
0x18007e791  test    eax, eax
0x18007e793  jz      short loc_18007E7A6
0x18007e795  mov     r9d, eax
0x18007e798  mov     r8, r13
0x18007e79b  mov     rdx, rdi
0x18007e79e  mov     rcx, rsi; unsigned __int16 *
0x18007e7a1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e7a6  lea     rbx, [rbp+28h]
0x18007e7aa  mov     rcx, [rbx]; void *
0x18007e7ad  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e7b2  mov     r8, rbx; unsigned __int16 **
0x18007e7b5  mov     [rbx], r12
0x18007e7b8  lea     rdx, aMdmenrollmentu; "MdmEnrollmentUrl"
0x18007e7bf  mov     rcx, r14; this
0x18007e7c2  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e7c7  test    eax, eax
0x18007e7c9  jz      short loc_18007E7DC
0x18007e7cb  mov     r9d, eax
0x18007e7ce  mov     r8, r13
0x18007e7d1  mov     rdx, rdi
0x18007e7d4  mov     rcx, rsi; unsigned __int16 *
0x18007e7d7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e7dc  lea     rbx, [rbp+30h]
0x18007e7e0  mov     rcx, [rbx]; void *
0x18007e7e3  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e7e8  mov     r8, rbx; unsigned __int16 **
0x18007e7eb  mov     [rbx], r12
0x18007e7ee  lea     rdx, aMdmtermsofuseu; "MdmTermsOfUseUrl"
0x18007e7f5  mov     rcx, r14; this
0x18007e7f8  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e7fd  test    eax, eax
0x18007e7ff  jz      short loc_18007E812
0x18007e801  mov     r9d, eax
0x18007e804  mov     r8, r13
0x18007e807  mov     rdx, rdi
0x18007e80a  mov     rcx, rsi; unsigned __int16 *
0x18007e80d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e812  lea     rbx, [rbp+38h]
0x18007e816  mov     rcx, [rbx]; void *
0x18007e819  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e81e  mov     r8, rbx; unsigned __int16 **
0x18007e821  mov     [rbx], r12
0x18007e824  lea     rdx, aMdmcomplianceu; "MdmComplianceUrl"
0x18007e82b  mov     rcx, r14; this
0x18007e82e  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e833  test    eax, eax
0x18007e835  jz      short loc_18007E848
0x18007e837  mov     r9d, eax
0x18007e83a  mov     r8, r13
0x18007e83d  mov     rdx, rdi
0x18007e840  mov     rcx, rsi; unsigned __int16 *
0x18007e843  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e848  lea     rbx, [rbp+40h]
0x18007e84c  mov     rcx, [rbx]; void *
0x18007e84f  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e854  mov     r8, rbx; unsigned __int16 **
0x18007e857  mov     [rbx], r12
0x18007e85a  lea     rdx, aUsersettingsyn; "UserSettingSyncUrl"
0x18007e861  mov     rcx, r14; this
0x18007e864  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e869  test    eax, eax
0x18007e86b  jz      short loc_18007E87E
0x18007e86d  mov     r9d, eax
0x18007e870  mov     r8, r13
0x18007e873  mov     rdx, rdi
0x18007e876  mov     rcx, rsi; unsigned __int16 *
0x18007e879  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e87e  lea     rbx, [rbp+48h]
0x18007e882  mov     rcx, [rbx]; void *
0x18007e885  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e88a  mov     r8, rbx; unsigned __int16 **
0x18007e88d  mov     [rbx], r12
0x18007e890  lea     rdx, aDrsservicevers; "DrsServiceVersion"
0x18007e897  mov     rcx, r14; this
0x18007e89a  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e89f  test    eax, eax
0x18007e8a1  jz      short loc_18007E8B4
0x18007e8a3  mov     r9d, eax
0x18007e8a6  mov     r8, r13
0x18007e8a9  mov     rdx, rdi
0x18007e8ac  mov     rcx, rsi; unsigned __int16 *
0x18007e8af  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e8b4  lea     rbx, [rbp+50h]
0x18007e8b8  mov     rcx, [rbx]; void *
0x18007e8bb  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e8c0  mov     r8, rbx; unsigned __int16 **
0x18007e8c3  mov     [rbx], r12
0x18007e8c6  lea     rdx, aDrsendpoint; "DrsEndpoint"
0x18007e8cd  mov     rcx, r14; this
0x18007e8d0  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e8d5  test    eax, eax
0x18007e8d7  jz      short loc_18007E8EA
0x18007e8d9  mov     r9d, eax
0x18007e8dc  mov     r8, r13
0x18007e8df  mov     rdx, rdi
0x18007e8e2  mov     rcx, rsi; unsigned __int16 *
0x18007e8e5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e8ea  lea     rbx, [rbp+58h]
0x18007e8ee  mov     rcx, [rbx]; void *
0x18007e8f1  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e8f6  mov     r8, rbx; unsigned __int16 **
0x18007e8f9  mov     [rbx], r12
0x18007e8fc  lea     rdx, aDrsresourceid; "DrsResourceId"
0x18007e903  mov     rcx, r14; this
0x18007e906  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e90b  test    eax, eax
0x18007e90d  jz      short loc_18007E920
0x18007e90f  mov     r9d, eax
0x18007e912  mov     r8, r13
0x18007e915  mov     rdx, rdi
0x18007e918  mov     rcx, rsi; unsigned __int16 *
0x18007e91b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e920  lea     rbx, [rbp+60h]
0x18007e924  mov     rcx, [rbx]; void *
0x18007e927  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e92c  mov     r8, rbx; unsigned __int16 **
0x18007e92f  mov     [rbx], r12
0x18007e932  lea     rdx, aAuthcodeurl; "AuthCodeUrl"
0x18007e939  mov     rcx, r14; this
0x18007e93c  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e941  test    eax, eax
0x18007e943  jz      short loc_18007E956
0x18007e945  mov     r9d, eax
0x18007e948  mov     r8, r13
0x18007e94b  mov     rdx, rdi
0x18007e94e  mov     rcx, rsi; unsigned __int16 *
0x18007e951  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e956  lea     rbx, [rbp+68h]
0x18007e95a  mov     rcx, [rbx]; void *
0x18007e95d  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e962  mov     r8, rbx; unsigned __int16 **
0x18007e965  mov     [rbx], r12
0x18007e968  lea     rdx, aAccesstokenurl; "AccessTokenUrl"
0x18007e96f  mov     rcx, r14; this
0x18007e972  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e977  test    eax, eax
0x18007e979  jz      short loc_18007E98C
0x18007e97b  mov     r9d, eax
0x18007e97e  mov     r8, r13
0x18007e981  mov     rdx, rdi
0x18007e984  mov     rcx, rsi; unsigned __int16 *
0x18007e987  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e98c  lea     rbx, [rbp+70h]
0x18007e990  mov     rcx, [rbx]; void *
0x18007e993  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e998  mov     r8, rbx; unsigned __int16 **
0x18007e99b  mov     [rbx], r12
0x18007e99e  lea     rdx, aCdjservicevers; "CdjServiceVersion"
0x18007e9a5  mov     rcx, r14; this
0x18007e9a8  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e9ad  test    eax, eax
0x18007e9af  jz      short loc_18007E9C2
0x18007e9b1  mov     r9d, eax
0x18007e9b4  mov     r8, r13
0x18007e9b7  mov     rdx, rdi
0x18007e9ba  mov     rcx, rsi; unsigned __int16 *
0x18007e9bd  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e9c2  lea     rbx, [rbp+78h]
0x18007e9c6  mov     rcx, [rbx]; void *
0x18007e9c9  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007e9ce  mov     r8, rbx; unsigned __int16 **
0x18007e9d1  mov     [rbx], r12
0x18007e9d4  lea     rdx, aCdjendpoint; "CdjEndpoint"
0x18007e9db  mov     rcx, r14; this
0x18007e9de  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007e9e3  test    eax, eax
0x18007e9e5  jz      short loc_18007E9F8
0x18007e9e7  mov     r9d, eax
0x18007e9ea  mov     r8, r13
0x18007e9ed  mov     rdx, rdi
0x18007e9f0  mov     rcx, rsi; unsigned __int16 *
0x18007e9f3  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007e9f8  lea     rbx, [rbp+80h]
0x18007e9ff  mov     rcx, [rbx]; void *
0x18007ea02  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007ea07  mov     r8, rbx; unsigned __int16 **
0x18007ea0a  mov     [rbx], r12
0x18007ea0d  lea     rdx, aCdjresourceid; "CdjResourceId"
0x18007ea14  mov     rcx, r14; this
0x18007ea17  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007ea1c  test    eax, eax
0x18007ea1e  jz      short loc_18007EA31
0x18007ea20  mov     r9d, eax
0x18007ea23  mov     r8, r13
0x18007ea26  mov     rdx, rdi
0x18007ea29  mov     rcx, rsi; unsigned __int16 *
0x18007ea2c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ea31  lea     rbx, [rbp+88h]
0x18007ea38  mov     rcx, [rbx]; void *
0x18007ea3b  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007ea40  mov     r8, rbx; unsigned __int16 **
0x18007ea43  mov     [rbx], r12
0x18007ea46  lea     rdx, aNgcservicevers; "NgcServiceVersion"
0x18007ea4d  mov     rcx, r14; this
0x18007ea50  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007ea55  test    eax, eax
0x18007ea57  jz      short loc_18007EA6A
0x18007ea59  mov     r9d, eax
0x18007ea5c  mov     r8, r13
0x18007ea5f  mov     rdx, rdi
0x18007ea62  mov     rcx, rsi; unsigned __int16 *
0x18007ea65  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ea6a  lea     rbx, [rbp+90h]
0x18007ea71  mov     rcx, [rbx]; void *
0x18007ea74  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007ea79  mov     r8, rbx; unsigned __int16 **
0x18007ea7c  mov     [rbx], r12
0x18007ea7f  lea     rdx, aNgcendpoint; "NgcEndpoint"
0x18007ea86  mov     rcx, r14; this
0x18007ea89  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007ea8e  test    eax, eax
0x18007ea90  jz      short loc_18007EAA3
0x18007ea92  mov     r9d, eax
0x18007ea95  mov     r8, r13
0x18007ea98  mov     rdx, rdi
0x18007ea9b  mov     rcx, rsi; unsigned __int16 *
0x18007ea9e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007eaa3  lea     rbx, [rbp+98h]
0x18007eaaa  mov     rcx, [rbx]; void *
0x18007eaad  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007eab2  mov     r8, rbx; unsigned __int16 **
0x18007eab5  mov     [rbx], r12
0x18007eab8  lea     rdx, aNgcresourceid; "NgcResourceId"
0x18007eabf  mov     rcx, r14; this
0x18007eac2  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007eac7  test    eax, eax
0x18007eac9  jz      short loc_18007EADC
0x18007eacb  mov     r9d, eax
0x18007eace  mov     r8, r13
0x18007ead1  mov     rdx, rdi
0x18007ead4  mov     rcx, rsi; unsigned __int16 *
0x18007ead7  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007eadc  lea     rbx, [rbp+0A0h]
0x18007eae3  mov     rcx, [rbx]; void *
0x18007eae6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007eaeb  mov     r8, rbx; unsigned __int16 **
0x18007eaee  mov     [rbx], r12
0x18007eaf1  lea     rdx, aWebauthnservic; "WebAuthnServiceVersion"
0x18007eaf8  mov     rcx, r14; this
0x18007eafb  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007eb00  test    eax, eax
0x18007eb02  jz      short loc_18007EB15
0x18007eb04  mov     r9d, eax
0x18007eb07  mov     r8, r13
0x18007eb0a  mov     rdx, rdi
0x18007eb0d  mov     rcx, rsi; unsigned __int16 *
0x18007eb10  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007eb15  lea     rbx, [rbp+0A8h]
0x18007eb1c  mov     rcx, [rbx]; void *
0x18007eb1f  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007eb24  mov     r8, rbx; unsigned __int16 **
0x18007eb27  mov     [rbx], r12
0x18007eb2a  lea     rdx, aWebauthnendpoi; "WebAuthnEndpoint"
0x18007eb31  mov     rcx, r14; this
0x18007eb34  call    ?ReadStringValue@RegistryPath@@QEBAKPEBGPEAPEAG@Z; RegistryPath::ReadStringValue(ushort const *,ushort * *)
0x18007eb39  test    eax, eax
0x18007eb3b  jz      short loc_18007EB4E
0x18007eb3d  mov     r9d, eax
0x18007eb40  mov     r8, r13
0x18007eb43  mov     rdx, rdi
0x18007eb46  mov     rcx, rsi; unsigned __int16 *
0x18007eb49  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007eb4e  lea     rbx, [rbp+0B0h]
0x18007eb55  mov     rcx, [rbx]; void *
0x18007eb58  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18007eb5d  mov     r8, rbx; unsigned __int16 **
  ... truncated ...
```
