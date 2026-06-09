# DeviceRegistrationStateApi::PopulateJoinInfo(_JOIN_TYPE,_CERT_CONTEXT const *,ushort const *,int,int,_DSREG_ACCOUNT_INFO_2 *)

- ea: `0x18007ab58`
- end: `0x18007be12`
- name: `?PopulateJoinInfo@DeviceRegistrationStateApi@@SAJW4_JOIN_TYPE@@PEBU_CERT_CONTEXT@@PEBGHHPEAU_DSREG_ACCOUNT_INFO_2@@@Z`
- size: `4794`
- prototype: `static int __high(enum _JOIN_TYPE, const struct _CERT_CONTEXT *, const unsigned __int16 *, int, int, struct _DSREG_ACCOUNT_INFO_2 *)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007a74c`

## callees

- `0x180007670`
- `0x180007d90`
- `0x180007db4`
- `0x1800084c8`
- `0x180008fdc`
- `0x18007830c`
- `0x18007911c`
- `0x180079fac`
- `0x18007a418`
- `0x18007a440`
- `0x18007ab58`
- `0x18007bea4`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d22c`
- `0x18007d2a4`
- `0x18007e3c8`
- `0x1800805c4`
- `0x180080754`
- `0x180080b30`
- `0x180080b88`
- `0x180080c00`
- `0x180080fec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ad28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ad3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ad28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ad3d`
- `RPCRT4!RpcStringFreeW` at `0x18007bdc4`
- `RPCRT4!RpcStringFreeW` at `0x18007bdc4`
- `RPCRT4!UuidToStringW` at `0x18007bc97`
- `RPCRT4!UuidToStringW` at `0x18007bc97`
- `CRYPT32!CertFreeCertificateContext` at `0x18007bd7a`
- `CRYPT32!CertFreeCertificateContext` at `0x18007bd7a`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007ad18`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18007ad18`

## string_xrefs

- `0x18007ba39`: `StringCompare`
- `0x18007bb36`: `StringCompare`
- `0x18007af50`: `CopyStringNullSafeW`
- `0x18007af9c`: `CopyStringNullSafeW`
- `0x18007afe8`: `CopyStringNullSafeW`
- `0x18007b034`: `CopyStringNullSafeW`
- `0x18007b080`: `CopyStringNullSafeW`
- `0x18007b0cc`: `CopyStringNullSafeW`
- `0x18007b118`: `CopyStringNullSafeW`
- `0x18007b164`: `CopyStringNullSafeW`
- `0x18007b1b0`: `CopyStringNullSafeW`
- `0x18007b1fc`: `CopyStringNullSafeW`
- `0x18007b24b`: `CopyStringNullSafeW`
- `0x18007b29a`: `CopyStringNullSafeW`
- `0x18007b2e9`: `CopyStringNullSafeW`
- `0x18007b338`: `CopyStringNullSafeW`
- `0x18007b38a`: `CopyStringNullSafeW`
- `0x18007b3dc`: `CopyStringNullSafeW`
- `0x18007b42e`: `CopyStringNullSafeW`
- `0x18007b480`: `CopyStringNullSafeW`
- `0x18007b4d2`: `CopyStringNullSafeW`
- `0x18007b524`: `CopyStringNullSafeW`
- `0x18007b576`: `CopyStringNullSafeW`
- `0x18007b5c8`: `CopyStringNullSafeW`
- `0x18007b61a`: `CopyStringNullSafeW`
- `0x18007b66c`: `CopyStringNullSafeW`
- `0x18007b6c0`: `CopyStringNullSafeW`
- `0x18007b73c`: `CopyStringNullSafeW`
- `0x18007b78e`: `CopyStringNullSafeW`
- `0x18007b7e2`: `CopyStringNullSafeW`
- `0x18007b858`: `CopyStringNullSafeW`
- `0x18007b8aa`: `CopyStringNullSafeW`
- `0x18007b8fc`: `CopyStringNullSafeW`
- `0x18007b94e`: `CopyStringNullSafeW`
- `0x18007b9b0`: `CopyStringNullSafeW`
- `0x18007bc0d`: `CopyStringNullSafeW`
- `0x18007bc60`: `CopyStringNullSafeW`
- `0x18007bce7`: `CopyStringNullSafeW`
- `0x18007ae0e`: `JoinStatusStorage::ReadJoinStatus`

## pseudocode

```c
__int64 __fastcall DeviceRegistrationStateApi::PopulateJoinInfo(
        unsigned int a1,
        const struct _CERT_CONTEXT *a2,
        unsigned __int16 *a3,
        int a4,
        int a5,
        __int64 a6)
{
  struct_join_status *v9; // rbx
  NgcStatusStorage *v10; // rsi
  int JoinStatus; // edi
  const unsigned __int16 *v12; // rdx
  void *v13; // rcx
  __int64 v14; // rdx
  _OWORD *v15; // rcx
  _OWORD *v16; // rax
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  const unsigned __int16 *v28; // rcx
  __int64 v29; // r8
  signed int LastError; // eax
  int TenantId; // eax
  const unsigned __int16 *v32; // r8
  struct_join_status *v33; // rax
  int v34; // edx
  int v35; // ecx
  const wchar_t *v36; // r13
  const wchar_t *v37; // rax
  const wchar_t *v38; // rax
  __int64 Key; // rax
  bool v40; // zf
  unsigned __int16 *v41; // r8
  UUID v42; // xmm0
  const wchar_t *v43; // rax
  const wchar_t *v44; // rax
  const wchar_t *v45; // rax
  const wchar_t *v46; // rax
  const wchar_t *v47; // rax
  const wchar_t *v48; // rax
  const wchar_t *v49; // rax
  const wchar_t *v50; // rax
  const wchar_t *v51; // rax
  const wchar_t *v52; // rax
  const wchar_t *v53; // rax
  const wchar_t *v54; // rax
  const wchar_t *v55; // rax
  const wchar_t *v56; // rax
  const wchar_t *v57; // rax
  const wchar_t *v58; // rax
  const wchar_t *v59; // rax
  const wchar_t *v60; // rax
  const wchar_t *v61; // rax
  const wchar_t *v62; // rax
  const wchar_t *v63; // rax
  const wchar_t *v64; // rax
  const wchar_t *v65; // rax
  const wchar_t *v66; // rax
  const wchar_t *v67; // rax
  _WORD *v68; // rax
  int v69; // eax
  const wchar_t *v70; // rax
  const wchar_t *v71; // rax
  const wchar_t *v72; // rax
  const wchar_t *v73; // rax
  const wchar_t *v74; // rax
  const wchar_t *v75; // rax
  const wchar_t *v76; // rax
  const wchar_t *v77; // rax
  const unsigned __int16 *v78; // rdx
  const unsigned __int16 *v79; // rcx
  const wchar_t *v80; // rax
  const wchar_t *v81; // r9
  unsigned __int16 *v82; // rcx
  unsigned __int16 *v83; // rcx
  const unsigned __int16 *v84; // rdx
  const wchar_t *v85; // rax
  const wchar_t *v86; // r9
  _QWORD *v87; // rax
  unsigned __int16 **v88; // rdx
  const unsigned __int16 *v89; // rcx
  const wchar_t *v90; // rax
  const wchar_t *v91; // rax
  unsigned int v92; // eax
  unsigned int v93; // edx
  unsigned __int16 *v95; // [rsp+30h] [rbp-D0h]
  int v96; // [rsp+38h] [rbp-C8h] BYREF
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v98; // [rsp+48h] [rbp-B8h]
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v100; // [rsp+58h] [rbp-A8h]
  unsigned __int16 *v101; // [rsp+60h] [rbp-A0h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+68h] [rbp-98h]
  _BYTE v103[64]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v104[336]; // [rsp+B0h] [rbp-50h] BYREF
  UUID Uuid[4]; // [rsp+200h] [rbp+100h] BYREF

  v100 = a3;
  v98 = a1;
  v95 = 0;
  Block = 0;
  v101 = 0;
  StringUuid = 0;
  v9 = 0;
  memset(Uuid, 0, sizeof(Uuid));
  v10 = 0;
  v96 = 0;
  if ( !a6 )
  {
    JoinStatus = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"DeviceRegistrationStateApi::PopulateJoinInfo", L"pJoinInfo");
    v12 = L"pJoinInfo";
LABEL_3:
    Logger::WriteNullOrEmptyParameterFailureEvent(L"DeviceRegistrationStateApi::PopulateJoinInfo", v12);
LABEL_4:
    v13 = v95;
    goto LABEL_222;
  }
  memset_0(v104, 0, sizeof(v104));
  v14 = 2;
  v15 = v104;
  v16 = (_OWORD *)a6;
  do
  {
    v17 = v15[1];
    *v16 = *v15;
    v18 = v15[2];
    v16[1] = v17;
    v19 = v15[3];
    v16[2] = v18;
    v20 = v15[4];
    v16[3] = v19;
    v21 = v15[5];
    v16[4] = v20;
    v22 = v15[6];
    v16[5] = v21;
    v23 = v15[7];
    v15 += 8;
    v16[6] = v22;
    v16[7] = v23;
    v16 += 8;
    --v14;
  }
  while ( v14 );
  v24 = v15[1];
  *v16 = *v15;
  v25 = v15[2];
  v16[1] = v24;
  v26 = v15[3];
  v16[2] = v25;
  v27 = v15[4];
  v16[3] = v26;
  v16[4] = v27;
  if ( !a2 )
  {
    JoinStatus = -2147024809;
    Logger::TraceError(
      L"%s: \"%s\" should not be null.",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      &stru_18009D3F8);
    v12 = (const unsigned __int16 *)&stru_18009D3F8;
    goto LABEL_3;
  }
  if ( ((a1 - 1) & 0xFFFFFFFB) != 0 )
  {
    JoinStatus = -2147024809;
    v28 = L"%s: Invalid join type %d. Only DEVICE and WORKPLACE are allowed.";
    v29 = a1;
LABEL_11:
    Logger::TraceError(v28, L"DeviceRegistrationStateApi::PopulateJoinInfo", v29);
    goto LABEL_4;
  }
  pCertContext = CertDuplicateCertificateContext(a2);
  if ( !pCertContext )
  {
    LastError = GetLastError();
    JoinStatus = LastError;
    if ( LastError > 0 )
      JoinStatus = (unsigned __int16)LastError | 0x80070000;
    v29 = GetLastError();
    v28 = L"%s: CertDuplicateCertificateContext failed with error code: 0x%08x";
    goto LABEL_11;
  }
  TenantId = RegistrationCertStatus::GetTenantId(a2, (unsigned __int16 **)&Block, &v96);
  JoinStatus = TenantId;
  if ( TenantId >= 0 )
  {
    TenantId = RegistrationCertStatus::GetDeviceId(a2, &v101);
    JoinStatus = TenantId;
    if ( TenantId < 0 )
    {
      v32 = L"RegistrationCertStatus::GetDeviceId";
      goto LABEL_18;
    }
    v33 = (struct_join_status *)operator new(0x140u, (const struct std::nothrow_t *)std::nothrow);
    v9 = v33;
    if ( !v33 )
    {
      JoinStatus = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
      v9 = 0;
      goto LABEL_221;
    }
    struct_join_status::Clear(v33);
    v35 = v34;
    LOBYTE(v35) = a1 == 1;
    JoinStatus = JoinStatusStorage::ReadJoinStatus(v35, a2, a4, v9, a5);
    v36 = L"TRUE";
    if ( JoinStatus < 0 )
    {
      v37 = L"TRUE";
      if ( !a4 )
        v37 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"JoinStatusStorage::ReadJoinStatus",
        (unsigned int)JoinStatus,
        v37);
      if ( !a4 )
        goto LABEL_221;
    }
    v10 = (NgcStatusStorage *)operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    if ( !v10 )
    {
      JoinStatus = -2147024882;
      Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
      v10 = 0;
      goto LABEL_221;
    }
    *(_QWORD *)v10 = 0;
    *((_QWORD *)v10 + 1) = 0;
    JoinStatus = NgcStatusStorage::Load(v10);
    if ( JoinStatus < 0 )
    {
      v38 = L"TRUE";
      if ( !a4 )
        v38 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"NgcStatusStorage::Load",
        (unsigned int)JoinStatus,
        v38);
      if ( !a4 )
        goto LABEL_221;
    }
    Key = NgcStatusStorage::GetKey(v10, v103, 0);
    v40 = v98 == 1;
    v95 = v41;
    Uuid[0] = *(UUID *)Key;
    Uuid[1] = *(UUID *)(Key + 16);
    Uuid[2] = *(UUID *)(Key + 32);
    v42 = *(UUID *)(Key + 48);
    LODWORD(Key) = (_DWORD)v41;
    *(_QWORD *)(a6 + 8) = pCertContext;
    LOBYTE(Key) = !v40;
    Uuid[3] = v42;
    v40 = v96 == (_DWORD)v41;
    *(_DWORD *)a6 = Key + 1;
    *(_QWORD *)(a6 + 16) = v101;
    *(_QWORD *)(a6 + 32) = Block;
    LODWORD(Key) = (_DWORD)v41;
    LOBYTE(Key) = !v40;
    v101 = v41;
    *(_DWORD *)(a6 + 60) = Key;
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 1), (unsigned __int16 **)(a6 + 24));
    if ( JoinStatus < 0 )
    {
      v43 = L"TRUE";
      if ( !a4 )
        v43 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v43);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 3), (unsigned __int16 **)(a6 + 40));
    if ( JoinStatus < 0 )
    {
      v44 = L"TRUE";
      if ( !a4 )
        v44 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v44);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 4), (unsigned __int16 **)(a6 + 64));
    if ( JoinStatus < 0 )
    {
      v45 = L"TRUE";
      if ( !a4 )
        v45 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v45);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 5), (unsigned __int16 **)(a6 + 72));
    if ( JoinStatus < 0 )
    {
      v46 = L"TRUE";
      if ( !a4 )
        v46 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v46);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 6), (unsigned __int16 **)(a6 + 80));
    if ( JoinStatus < 0 )
    {
      v47 = L"TRUE";
      if ( !a4 )
        v47 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v47);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 7), (unsigned __int16 **)(a6 + 88));
    if ( JoinStatus < 0 )
    {
      v48 = L"TRUE";
      if ( !a4 )
        v48 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v48);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 8), (unsigned __int16 **)(a6 + 96));
    if ( JoinStatus < 0 )
    {
      v49 = L"TRUE";
      if ( !a4 )
        v49 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v49);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 9), (unsigned __int16 **)(a6 + 104));
    if ( JoinStatus < 0 )
    {
      v50 = L"TRUE";
      if ( !a4 )
        v50 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v50);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 10), (unsigned __int16 **)(a6 + 112));
    if ( JoinStatus < 0 )
    {
      v51 = L"TRUE";
      if ( !a4 )
        v51 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v51);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 11), (unsigned __int16 **)(a6 + 120));
    if ( JoinStatus < 0 )
    {
      v52 = L"TRUE";
      if ( !a4 )
        v52 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v52);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 12), (unsigned __int16 **)(a6 + 128));
    if ( JoinStatus < 0 )
    {
      v53 = L"TRUE";
      if ( !a4 )
        v53 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v53);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 13), (unsigned __int16 **)(a6 + 136));
    if ( JoinStatus < 0 )
    {
      v54 = L"TRUE";
      if ( !a4 )
        v54 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v54);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 14), (unsigned __int16 **)(a6 + 144));
    if ( JoinStatus < 0 )
    {
      v55 = L"TRUE";
      if ( !a4 )
        v55 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v55);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 15), (unsigned __int16 **)(a6 + 152));
    if ( JoinStatus < 0 )
    {
      v56 = L"TRUE";
      if ( !a4 )
        v56 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v56);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 16), (unsigned __int16 **)(a6 + 160));
    if ( JoinStatus < 0 )
    {
      v57 = L"TRUE";
      if ( !a4 )
        v57 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v57);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 17), (unsigned __int16 **)(a6 + 168));
    if ( JoinStatus < 0 )
    {
      v58 = L"TRUE";
      if ( !a4 )
        v58 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v58);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 18), (unsigned __int16 **)(a6 + 176));
    if ( JoinStatus < 0 )
    {
      v59 = L"TRUE";
      if ( !a4 )
        v59 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v59);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 19), (unsigned __int16 **)(a6 + 184));
    if ( JoinStatus < 0 )
    {
      v60 = L"TRUE";
      if ( !a4 )
        v60 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v60);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 20), (unsigned __int16 **)(a6 + 192));
    if ( JoinStatus < 0 )
    {
      v61 = L"TRUE";
      if ( !a4 )
        v61 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v61);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 21), (unsigned __int16 **)(a6 + 200));
    if ( JoinStatus < 0 )
    {
      v62 = L"TRUE";
      if ( !a4 )
        v62 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v62);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 22), (unsigned __int16 **)(a6 + 208));
    if ( JoinStatus < 0 )
    {
      v63 = L"TRUE";
      if ( !a4 )
        v63 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v63);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 23), (unsigned __int16 **)(a6 + 216));
    if ( JoinStatus < 0 )
    {
      v64 = L"TRUE";
      if ( !a4 )
        v64 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v64);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 24), (unsigned __int16 **)(a6 + 224));
    if ( JoinStatus < 0 )
    {
      v65 = L"TRUE";
      if ( !a4 )
        v65 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v65);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 25), (unsigned __int16 **)(a6 + 232));
    if ( JoinStatus < 0 )
    {
      v66 = L"TRUE";
      if ( !a4 )
        v66 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v66);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 28), (unsigned __int16 **)(a6 + 240));
    if ( JoinStatus < 0 )
    {
      v67 = L"TRUE";
      if ( !a4 )
        v67 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v67);
      if ( !a4 )
        goto LABEL_4;
    }
    *(_DWORD *)(a6 + 248) = 0;
    v68 = (_WORD *)*((_QWORD *)v9 + 29);
    if ( !v68 || (v40 = *v68 == 0, v69 = 1, v40) )
      v69 = 0;
    *(_DWORD *)(a6 + 248) = v69;
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 30), (unsigned __int16 **)(a6 + 256));
    if ( JoinStatus < 0 )
    {
      v70 = L"TRUE";
      if ( !a4 )
        v70 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v70);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 31), (unsigned __int16 **)(a6 + 264));
    if ( JoinStatus < 0 )
    {
      v71 = L"TRUE";
      if ( !a4 )
        v71 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v71);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 34), (unsigned __int16 **)(a6 + 288));
    if ( JoinStatus < 0 )
    {
      v72 = L"TRUE";
      if ( !a4 )
        v72 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v72);
      if ( !a4 )
        goto LABEL_4;
    }
    *(_DWORD *)(a6 + 272) = *((_DWORD *)v9 + 64) != 0;
    *(_QWORD *)(a6 + 280) = *((_QWORD *)v9 + 33);
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 35), (unsigned __int16 **)(a6 + 296));
    if ( JoinStatus < 0 )
    {
      v73 = L"TRUE";
      if ( !a4 )
        v73 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v73);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 36), (unsigned __int16 **)(a6 + 304));
    if ( JoinStatus < 0 )
    {
      v74 = L"TRUE";
      if ( !a4 )
        v74 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v74);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 37), (unsigned __int16 **)(a6 + 312));
    if ( JoinStatus < 0 )
    {
      v75 = L"TRUE";
      if ( !a4 )
        v75 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v75);
      if ( !a4 )
        goto LABEL_4;
    }
    JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 38), (unsigned __int16 **)(a6 + 320));
    if ( JoinStatus < 0 )
    {
      v76 = L"TRUE";
      if ( !a4 )
        v76 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"CopyStringNullSafeW",
        (unsigned int)JoinStatus,
        v76);
      if ( !a4 )
        goto LABEL_4;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RAforMTRW>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RAforMTRW>::GetImpl'::`2'::impl) )
    {
      JoinStatus = CopyStringNullSafeW(*((const unsigned __int16 **)v9 + 39), (unsigned __int16 **)(a6 + 328));
      if ( JoinStatus < 0 )
      {
        v77 = L"TRUE";
        if ( !a4 )
          v77 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          (unsigned int)JoinStatus,
          v77);
        if ( !a4 )
          goto LABEL_4;
      }
    }
    v96 = 0;
    if ( (unsigned int)NgcStatusStorage::IsKeyIdEmpty(Uuid) )
      goto LABEL_213;
    v78 = &LocaleName;
    v79 = *(const unsigned __int16 **)(a6 + 32);
    LODWORD(Block) = 0;
    if ( *(_QWORD *)&Uuid[3].Data1 )
      v78 = *(const unsigned __int16 **)&Uuid[3].Data1;
    JoinStatus = StringCompare(v79, v78, 0, (int *)&Block);
    if ( JoinStatus < 0 )
    {
      v80 = L"TRUE";
      if ( !a4 )
        v80 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"StringCompare",
        (unsigned int)JoinStatus,
        v80);
      if ( !a4 )
        goto LABEL_4;
    }
    if ( !(_DWORD)Block )
    {
      v81 = L"<NULL>";
      if ( *(_QWORD *)&Uuid[3].Data1 )
        v81 = *(const wchar_t **)&Uuid[3].Data1;
      Logger::TraceVerbose(
        L"%s: The NGC key is not for the given tenant %s. Key tenant: %s. Return no key.",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        *(_QWORD *)(a6 + 32),
        v81);
      goto LABEL_213;
    }
    v82 = v100;
    if ( !v100 || !*v100 )
    {
      if ( v98 == 5 )
      {
        v83 = *(unsigned __int16 **)(a6 + 40);
        v100 = v83;
        if ( !v83 || !*v83 )
          goto LABEL_196;
        Logger::TraceVerbose(
          L"%s: No explicit UPN given. Using the work account's UPN for matching. UPN: %s.",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          v83);
        v82 = v100;
      }
      else if ( !v100 )
      {
        goto LABEL_196;
      }
      if ( !*v82 )
        goto LABEL_196;
    }
    v84 = &LocaleName;
    if ( *(_QWORD *)Uuid[3].Data4 )
      v84 = *(const unsigned __int16 **)Uuid[3].Data4;
    JoinStatus = StringCompare(v82, v84, 0, (int *)&Block);
    if ( JoinStatus < 0 )
    {
      v85 = L"TRUE";
      if ( !a4 )
        v85 = L"FALSE";
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
        L"DeviceRegistrationStateApi::PopulateJoinInfo",
        L"StringCompare",
        (unsigned int)JoinStatus,
        v85);
      if ( !a4 )
        goto LABEL_4;
    }
    if ( (_DWORD)Block )
    {
LABEL_197:
      v87 = operator new[](0x18u, (const struct std::nothrow_t *)std::nothrow);
      *(_QWORD *)(a6 + 48) = v87;
      if ( !v87 )
      {
        JoinStatus = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DeviceRegistrationStateApi::PopulateJoinInfo");
        goto LABEL_4;
      }
      *(_OWORD *)v87 = 0;
      v87[2] = 0;
      v88 = *(unsigned __int16 ***)(a6 + 48);
      v89 = *(const unsigned __int16 **)Uuid[3].Data4;
      *(_DWORD *)(a6 + 56) = 1;
      JoinStatus = CopyStringNullSafeW(v89, v88);
      if ( JoinStatus < 0 )
      {
        v90 = L"TRUE";
        if ( !a4 )
          v90 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          (unsigned int)JoinStatus,
          v90);
        if ( !a4 )
          goto LABEL_4;
      }
      JoinStatus = CopyStringNullSafeW(
                     *(const unsigned __int16 **)&Uuid[1].Data1,
                     (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 16LL));
      if ( JoinStatus < 0 )
      {
        v91 = L"TRUE";
        if ( !a4 )
          v91 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          (unsigned int)JoinStatus,
          v91);
        if ( !a4 )
          goto LABEL_4;
      }
      v92 = UuidToStringW(Uuid, &StringUuid);
      v96 = v92;
      JoinStatus = v92;
      if ( v92 )
      {
        Logger::TraceError(
          L"%s: UuidToStringW failed with RPC_STATUS error code: 0x%08x",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          v92);
        if ( !a4 )
        {
LABEL_217:
          if ( JoinStatus > 0 )
            JoinStatus = (unsigned __int16)JoinStatus | 0x80070000;
          goto LABEL_4;
        }
      }
      JoinStatus = CopyStringNullSafeW(StringUuid, (unsigned __int16 **)(*(_QWORD *)(a6 + 48) + 8LL));
      if ( JoinStatus < 0 )
      {
        if ( !a4 )
          v36 = L"FALSE";
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x. Ignore Error: %s",
          L"DeviceRegistrationStateApi::PopulateJoinInfo",
          L"CopyStringNullSafeW",
          (unsigned int)JoinStatus,
          v36);
        if ( !a4 )
        {
LABEL_215:
          if ( !v96 )
            goto LABEL_4;
          JoinStatus = v96;
          goto LABEL_217;
        }
      }
LABEL_213:
      if ( a4 )
      {
        JoinStatus = 0;
        goto LABEL_4;
      }
      goto LABEL_215;
    }
    v86 = L"<NULL>";
    if ( *(_QWORD *)Uuid[3].Data4 )
      v86 = *(const wchar_t **)Uuid[3].Data4;
    Logger::TraceVerbose(
      L"%s: The NGC key is not for the given UPN %s. Key UPN: %s. Return no key.",
      L"DeviceRegistrationStateApi::PopulateJoinInfo",
      v100,
      v86);
LABEL_196:
    if ( !(_DWORD)Block )
      goto LABEL_213;
    goto LABEL_197;
  }
  v32 = L"RegistrationCertStatus::GetTenantId";
LABEL_18:
  Logger::TraceError(
    L"%s: %s failed with error code: 0x%08x.",
    L"DeviceRegistrationStateApi::PopulateJoinInfo",
    v32,
    (unsigned int)TenantId);
LABEL_221:
  CertFreeCertificateContext(pCertContext);
  v13 = Block;
LABEL_222:
  operator delete(v13);
  operator delete(v101);
  if ( v9 )
    struct_join_status::`scalar deleting destructor'(v9, v93);
  if ( v10 )
  {
    NgcStatusStorage::Cleanup(v10);
    operator delete(v10);
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( JoinStatus < 0 )
    DsrFreeAccountInfoContent(a6);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"DeviceRegistrationStateApi::PopulateJoinInfo", (unsigned int)JoinStatus);
  return (unsigned int)JoinStatus;
}

```

## disassembly

```asm
0x18007ab58  push    rbp
0x18007ab5a  push    rbx
0x18007ab5b  push    rsi
0x18007ab5c  push    rdi
0x18007ab5d  push    r12
0x18007ab5f  push    r13
0x18007ab61  push    r14
0x18007ab63  push    r15
0x18007ab65  lea     rbp, [rsp-158h]
0x18007ab6d  sub     rsp, 258h
0x18007ab74  mov     rax, cs:__security_cookie
0x18007ab7b  xor     rax, rsp
0x18007ab7e  mov     [rbp+190h+var_50], rax
0x18007ab85  mov     r12, [rbp+190h+arg_28]
0x18007ab8c  xor     edi, edi
0x18007ab8e  mov     [rsp+290h+var_238], r8
0x18007ab93  xorps   xmm0, xmm0
0x18007ab96  mov     [rsp+290h+var_248], ecx
0x18007ab9a  mov     eax, edi
0x18007ab9c  mov     [rsp+290h+var_260], rax
0x18007aba1  mov     r14d, r9d
0x18007aba4  mov     [rsp+290h+Block], rax
0x18007aba9  mov     r15, rdx
0x18007abac  mov     [rsp+290h+var_230], rdi
0x18007abb1  mov     r13d, ecx
0x18007abb4  mov     [rsp+290h+StringUuid], rdi
0x18007abb9  mov     ebx, edi
0x18007abbb  mov     [rbp+190h+Uuid.Data1], edi
0x18007abc1  mov     esi, edi
0x18007abc3  mov     [rsp+290h+var_258], edi
0x18007abc7  movups  xmmword ptr [rbp+190h+var_6C], xmm0
0x18007abce  movups  xmmword ptr [rbp+190h+Uuid.Data2], xmm0
0x18007abd5  movups  [rbp+190h+var_7C], xmm0
0x18007abdc  movups  xmmword ptr [rbp+190h+var_6C+0Ch], xmm0
0x18007abe3  test    r12, r12
0x18007abe6  jnz     short loc_18007AC23
0x18007abe8  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18007abef  mov     edi, 80070057h
0x18007abf4  mov     rdx, r15
0x18007abf7  lea     r8, aPjoininfo; "pJoinInfo"
0x18007abfe  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007ac05  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ac0a  lea     rdx, aPjoininfo; "pJoinInfo"
0x18007ac11  mov     rcx, r15; unsigned __int16 *
0x18007ac14  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x18007ac19  mov     rcx, [rsp+290h+var_260]
0x18007ac1e  jmp     loc_18007BD85
0x18007ac23  xor     edx, edx; Val
0x18007ac25  lea     rcx, [rbp+190h+var_1E0]; void *
0x18007ac29  mov     r8d, 150h; Size
0x18007ac2f  call    memset_0
0x18007ac34  mov     edx, 2
0x18007ac39  lea     rcx, [rbp+190h+var_1E0]
0x18007ac3d  mov     rax, r12
0x18007ac40  lea     r8d, [rdx+7Eh]
0x18007ac44  movups  xmm0, xmmword ptr [rcx]
0x18007ac47  movups  xmm1, xmmword ptr [rcx+10h]
0x18007ac4b  movups  xmmword ptr [rax], xmm0
0x18007ac4e  movups  xmm0, xmmword ptr [rcx+20h]
0x18007ac52  movups  xmmword ptr [rax+10h], xmm1
0x18007ac56  movups  xmm1, xmmword ptr [rcx+30h]
0x18007ac5a  movups  xmmword ptr [rax+20h], xmm0
0x18007ac5e  movups  xmm0, xmmword ptr [rcx+40h]
0x18007ac62  movups  xmmword ptr [rax+30h], xmm1
0x18007ac66  movups  xmm1, xmmword ptr [rcx+50h]
0x18007ac6a  movups  xmmword ptr [rax+40h], xmm0
0x18007ac6e  movups  xmm0, xmmword ptr [rcx+60h]
0x18007ac72  movups  xmmword ptr [rax+50h], xmm1
0x18007ac76  movups  xmm1, xmmword ptr [rcx+70h]
0x18007ac7a  add     rcx, r8
0x18007ac7d  movups  xmmword ptr [rax+60h], xmm0
0x18007ac81  movups  xmmword ptr [rax+70h], xmm1
0x18007ac85  add     rax, r8
0x18007ac88  sub     rdx, 1
0x18007ac8c  jnz     short loc_18007AC44
0x18007ac8e  movups  xmm0, xmmword ptr [rcx]
0x18007ac91  movups  xmm1, xmmword ptr [rcx+10h]
0x18007ac95  movups  xmmword ptr [rax], xmm0
0x18007ac98  movups  xmm0, xmmword ptr [rcx+20h]
0x18007ac9c  movups  xmmword ptr [rax+10h], xmm1
0x18007aca0  movups  xmm1, xmmword ptr [rcx+30h]
0x18007aca4  movups  xmmword ptr [rax+20h], xmm0
0x18007aca8  movups  xmm0, xmmword ptr [rcx+40h]
0x18007acac  movups  xmmword ptr [rax+30h], xmm1
0x18007acb0  movups  xmmword ptr [rax+40h], xmm0
0x18007acb4  test    r15, r15
0x18007acb7  jnz     short loc_18007ACE7
0x18007acb9  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18007acc0  mov     edi, 80070057h
0x18007acc5  mov     rdx, r15
0x18007acc8  lea     r8, stru_18009D3F8
0x18007accf  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18007acd6  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007acdb  lea     rdx, stru_18009D3F8
0x18007ace2  jmp     loc_18007AC11
0x18007ace7  lea     eax, [r13-1]
0x18007aceb  test    eax, 0FFFFFFFBh
0x18007acf0  jz      short loc_18007AD15
0x18007acf2  mov     edi, 80070057h
0x18007acf7  lea     rcx, aSInvalidJoinTy; "%s: Invalid join type %d. Only DEVICE a"...
0x18007acfe  mov     r8d, r13d
0x18007ad01  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18007ad08  mov     rdx, r15
0x18007ad0b  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ad10  jmp     loc_18007AC19
0x18007ad15  mov     rcx, r15; pCertContext
0x18007ad18  call    cs:__imp_CertDuplicateCertificateContext
0x18007ad1e  mov     [rsp+290h+pCertContext], rax
0x18007ad23  test    rax, rax
0x18007ad26  jnz     short loc_18007AD4F
0x18007ad28  call    cs:__imp_GetLastError
0x18007ad2e  mov     edi, eax
0x18007ad30  test    eax, eax
0x18007ad32  jle     short loc_18007AD3D
0x18007ad34  movzx   edi, ax
0x18007ad37  or      edi, 80070000h
0x18007ad3d  call    cs:__imp_GetLastError
0x18007ad43  mov     r8d, eax
0x18007ad46  lea     rcx, aSCertduplicate; "%s: CertDuplicateCertificateContext fai"...
0x18007ad4d  jmp     short loc_18007AD01
0x18007ad4f  lea     r8, [rsp+290h+var_258]; int *
0x18007ad54  mov     rcx, r15; struct _CERT_CONTEXT *
0x18007ad57  lea     rdx, [rsp+290h+Block]; unsigned __int16 **
0x18007ad5c  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18007ad61  mov     edi, eax
0x18007ad63  test    eax, eax
0x18007ad65  jns     short loc_18007AD8C
0x18007ad67  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x18007ad6e  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18007ad75  mov     r9d, eax
0x18007ad78  mov     rdx, r15
0x18007ad7b  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18007ad82  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ad87  jmp     loc_18007BD75
0x18007ad8c  lea     rdx, [rsp+290h+var_230]; unsigned __int16 **
0x18007ad91  mov     rcx, r15; struct _CERT_CONTEXT *
0x18007ad94  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x18007ad99  mov     edi, eax
0x18007ad9b  test    eax, eax
0x18007ad9d  jns     short loc_18007ADA8
0x18007ad9f  lea     r8, aRegistrationce_4; "RegistrationCertStatus::GetDeviceId"
0x18007ada6  jmp     short loc_18007AD6E
0x18007ada8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007adaf  mov     ecx, 140h; unsigned __int64
0x18007adb4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007adb9  xor     edx, edx
0x18007adbb  mov     rbx, rax
0x18007adbe  test    rax, rax
0x18007adc1  jz      loc_18007BD58
0x18007adc7  mov     rcx, rax; this
0x18007adca  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x18007adcf  mov     eax, [rbp+190h+arg_20]
0x18007add5  mov     ecx, edx
0x18007add7  cmp     r13d, 1
0x18007addb  mov     [rsp+290h+var_270], eax; int
0x18007addf  mov     r9, rbx; struct struct_join_status *
0x18007ade2  mov     r8d, r14d; int
0x18007ade5  setz    cl; int
0x18007ade8  mov     rdx, r15; struct _CERT_CONTEXT *
0x18007adeb  call    ?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z; JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)
0x18007adf0  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18007adf7  mov     edi, eax
0x18007adf9  lea     rdx, aFalse_0; "FALSE"
0x18007ae00  lea     r13, aTrue_0; "TRUE"
0x18007ae07  test    eax, eax
0x18007ae09  jns     short loc_18007AE3C
0x18007ae0b  test    r14d, r14d
0x18007ae0e  lea     r8, aJoinstatusstor_1; "JoinStatusStorage::ReadJoinStatus"
0x18007ae15  mov     rax, r13
0x18007ae18  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18007ae1f  cmovz   rax, rdx
0x18007ae23  mov     r9d, edi
0x18007ae26  mov     rdx, r15
0x18007ae29  mov     qword ptr [rsp+290h+var_270], rax
0x18007ae2e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007ae33  test    r14d, r14d
0x18007ae36  jz      loc_18007BD75
0x18007ae3c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007ae43  mov     ecx, 10h; unsigned __int64
0x18007ae48  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18007ae4d  mov     rsi, rax
0x18007ae50  xor     eax, eax
0x18007ae52  test    rsi, rsi
0x18007ae55  jz      loc_18007BD40
0x18007ae5b  mov     rcx, rsi; this
0x18007ae5e  mov     [rsi], rax
0x18007ae61  mov     [rsi+8], rax
0x18007ae65  call    ?Load@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Load(void)
0x18007ae6a  xor     r8d, r8d
0x18007ae6d  mov     edi, eax
0x18007ae6f  test    eax, eax
0x18007ae71  jns     short loc_18007AEAE
0x18007ae73  lea     rcx, aFalse_0; "FALSE"
0x18007ae7a  test    r14d, r14d
0x18007ae7d  mov     rax, r13
0x18007ae80  lea     r8, aNgcstatusstora; "NgcStatusStorage::Load"
0x18007ae87  cmovz   rax, rcx
0x18007ae8b  mov     r9d, edi
0x18007ae8e  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18007ae95  mov     qword ptr [rsp+290h+var_270], rax
0x18007ae9a  mov     rdx, r15
0x18007ae9d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007aea2  xor     r8d, r8d
0x18007aea5  test    r14d, r14d
0x18007aea8  jz      loc_18007BD75
0x18007aeae  lea     rdx, [rsp+290h+var_220]
0x18007aeb3  mov     rcx, rsi
0x18007aeb6  call    ?GetKey@NgcStatusStorage@@QEAA?AUSTRUCT_NGC_REG_KEY@@XZ; NgcStatusStorage::GetKey(void)
0x18007aebb  cmp     [rsp+290h+var_248], 1
0x18007aec0  lea     rdx, [r12+18h]; unsigned __int16 **
0x18007aec5  mov     rcx, [rsp+290h+pCertContext]
0x18007aeca  mov     [rsp+290h+var_260], r8
0x18007aecf  movups  xmm3, xmmword ptr [rax]
0x18007aed2  movaps  xmmword ptr [rbp+190h+Uuid.Data1], xmm3
0x18007aed9  movups  xmm0, xmmword ptr [rax+10h]
0x18007aedd  movaps  xmmword ptr [rbp+110h], xmm0
0x18007aee4  movups  xmm1, xmmword ptr [rax+20h]
0x18007aee8  movaps  [rbp+190h+var_7C+0Ch], xmm1
0x18007aeef  movups  xmm0, xmmword ptr [rax+30h]
0x18007aef3  mov     eax, r8d
0x18007aef6  mov     [r12+8], rcx
0x18007aefb  setnz   al
0x18007aefe  inc     eax
0x18007af00  movaps  xmmword ptr [rbp+190h+var_6C+0Ch], xmm0
0x18007af07  cmp     [rsp+290h+var_258], r8d
0x18007af0c  mov     [r12], eax
0x18007af10  mov     rax, [rsp+290h+var_230]
0x18007af15  mov     [r12+10h], rax
0x18007af1a  mov     rax, [rsp+290h+Block]
0x18007af1f  mov     [r12+20h], rax
0x18007af24  mov     eax, r8d
0x18007af27  setnz   al
0x18007af2a  mov     [rsp+290h+var_230], r8
0x18007af2f  mov     [r12+3Ch], eax
0x18007af34  mov     rcx, [rbx+8]; unsigned __int16 *
0x18007af38  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18007af3d  mov     edi, eax
0x18007af3f  test    eax, eax
0x18007af41  jns     short loc_18007AF7B
0x18007af43  lea     rcx, aFalse_0; "FALSE"
0x18007af4a  test    r14d, r14d
0x18007af4d  mov     rax, r13
0x18007af50  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x18007af57  cmovz   rax, rcx
0x18007af5b  mov     r9d, edi
0x18007af5e  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18007af65  mov     qword ptr [rsp+290h+var_270], rax
0x18007af6a  mov     rdx, r15
0x18007af6d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007af72  test    r14d, r14d
0x18007af75  jz      loc_18007AC19
0x18007af7b  mov     rcx, [rbx+18h]; unsigned __int16 *
0x18007af7f  lea     rdx, [r12+28h]; unsigned __int16 **
0x18007af84  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18007af89  mov     edi, eax
0x18007af8b  test    eax, eax
0x18007af8d  jns     short loc_18007AFC7
0x18007af8f  lea     rcx, aFalse_0; "FALSE"
0x18007af96  test    r14d, r14d
0x18007af99  mov     rax, r13
0x18007af9c  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x18007afa3  cmovz   rax, rcx
0x18007afa7  mov     r9d, edi
0x18007afaa  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18007afb1  mov     qword ptr [rsp+290h+var_270], rax
0x18007afb6  mov     rdx, r15
0x18007afb9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007afbe  test    r14d, r14d
0x18007afc1  jz      loc_18007AC19
0x18007afc7  mov     rcx, [rbx+20h]; unsigned __int16 *
0x18007afcb  lea     rdx, [r12+40h]; unsigned __int16 **
0x18007afd0  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18007afd5  mov     edi, eax
0x18007afd7  test    eax, eax
0x18007afd9  jns     short loc_18007B013
0x18007afdb  lea     rcx, aFalse_0; "FALSE"
0x18007afe2  test    r14d, r14d
0x18007afe5  mov     rax, r13
0x18007afe8  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x18007afef  cmovz   rax, rcx
0x18007aff3  mov     r9d, edi
0x18007aff6  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x18007affd  mov     qword ptr [rsp+290h+var_270], rax
0x18007b002  mov     rdx, r15
0x18007b005  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007b00a  test    r14d, r14d
0x18007b00d  jz      loc_18007AC19
0x18007b013  mov     rcx, [rbx+28h]; unsigned __int16 *
0x18007b017  lea     rdx, [r12+48h]; unsigned __int16 **
0x18007b01c  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18007b021  mov     edi, eax
0x18007b023  test    eax, eax
0x18007b025  jns     short loc_18007B05F
0x18007b027  lea     rcx, aFalse_0; "FALSE"
0x18007b02e  test    r14d, r14d
0x18007b031  mov     rax, r13
0x18007b034  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x18007b03b  cmovz   rax, rcx
0x18007b03f  mov     r9d, edi
0x18007b042  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
  ... truncated ...
```
