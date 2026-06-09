# DeviceRegistrationStateApi::PopulateJoinInfo(_JOIN_TYPE,_CERT_CONTEXT const *,ushort const *,int,int,_DSREG_ACCOUNT_INFO_2 *)

- ea: `0x1800883b0`
- end: `0x180089679`
- name: `?PopulateJoinInfo@DeviceRegistrationStateApi@@SAJW4_JOIN_TYPE@@PEBU_CERT_CONTEXT@@PEBGHHPEAU_DSREG_ACCOUNT_INFO_2@@@Z`
- size: `4809`
- prototype: `__int64 __fastcall(unsigned int, const struct _CERT_CONTEXT *, unsigned __int16 *, int, int, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180087fa4`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x180005f24`
- `0x180084c48`
- `0x180085c44`
- `0x1800873bc`
- `0x180087b30`
- `0x180087b58`
- `0x1800883b0`
- `0x18008970c`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aecc`
- `0x18008d404`
- `0x180090378`
- `0x1800909c4`
- `0x180090da8`
- `0x180090e00`
- `0x180090e78`
- `0x180091264`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800895e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800895f4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180089619`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800895e9`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800895f4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180089619`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088595`
- `RPCRT4!UuidToStringW` at `0x1800894fb`
- `RPCRT4!UuidToStringW` at `0x1800894fb`
- `RPCRT4!RpcStringFreeW` at `0x18008962b`
- `RPCRT4!RpcStringFreeW` at `0x18008962b`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180088570`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180088570`
- `CRYPT32!CertFreeCertificateContext` at `0x1800895de`
- `CRYPT32!CertFreeCertificateContext` at `0x1800895de`

## string_xrefs

- `0x180089297`: `StringCompare`
- `0x18008939a`: `StringCompare`
- `0x1800887a8`: `CopyStringNullSafeW`
- `0x1800887f4`: `CopyStringNullSafeW`
- `0x180088840`: `CopyStringNullSafeW`
- `0x18008888c`: `CopyStringNullSafeW`
- `0x1800888d8`: `CopyStringNullSafeW`
- `0x180088924`: `CopyStringNullSafeW`
- `0x180088970`: `CopyStringNullSafeW`
- `0x1800889bc`: `CopyStringNullSafeW`
- `0x180088a08`: `CopyStringNullSafeW`
- `0x180088a54`: `CopyStringNullSafeW`
- `0x180088aa3`: `CopyStringNullSafeW`
- `0x180088af2`: `CopyStringNullSafeW`
- `0x180088b41`: `CopyStringNullSafeW`
- `0x180088b90`: `CopyStringNullSafeW`
- `0x180088be2`: `CopyStringNullSafeW`
- `0x180088c34`: `CopyStringNullSafeW`
- `0x180088c86`: `CopyStringNullSafeW`
- `0x180088cd8`: `CopyStringNullSafeW`
- `0x180088d2a`: `CopyStringNullSafeW`
- `0x180088d7c`: `CopyStringNullSafeW`
- `0x180088dce`: `CopyStringNullSafeW`
- `0x180088e20`: `CopyStringNullSafeW`
- `0x180088e72`: `CopyStringNullSafeW`
- `0x180088ec4`: `CopyStringNullSafeW`
- `0x180088f18`: `CopyStringNullSafeW`
- `0x180088f94`: `CopyStringNullSafeW`
- `0x180088fe6`: `CopyStringNullSafeW`
- `0x18008903a`: `CopyStringNullSafeW`
- `0x1800890b0`: `CopyStringNullSafeW`
- `0x180089102`: `CopyStringNullSafeW`
- `0x180089154`: `CopyStringNullSafeW`
- `0x1800891a6`: `CopyStringNullSafeW`
- `0x180089208`: `CopyStringNullSafeW`
- `0x180089471`: `CopyStringNullSafeW`
- `0x1800894c4`: `CopyStringNullSafeW`
- `0x18008954b`: `CopyStringNullSafeW`
- `0x180088666`: `JoinStatusStorage::ReadJoinStatus`

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
      &stru_1800C0A68);
    v12 = (const unsigned __int16 *)&stru_1800C0A68;
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
    v33 = (struct_join_status *)operator new[](0x140u, (const struct std::nothrow_t *)std::nothrow);
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
    v10 = (NgcStatusStorage *)operator new[](0x10u, (const struct std::nothrow_t *)std::nothrow);
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
    v78 = &base;
    v79 = *(const unsigned __int16 **)(a6 + 32);
    LODWORD(Block) = 0;
    if ( *(_QWORD *)&Uuid[3].Data1 )
      v78 = *(const unsigned __int16 **)&Uuid[3].Data1;
    JoinStatus = StringCompare(v79, v78, 1u, (int *)&Block);
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
    v84 = &base;
    if ( *(_QWORD *)Uuid[3].Data4 )
      v84 = *(const unsigned __int16 **)Uuid[3].Data4;
    JoinStatus = StringCompare(v82, v84, 1u, (int *)&Block);
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
  free(v13);
  free(v101);
  if ( v9 )
    struct_join_status::`scalar deleting destructor'(v9, v93);
  if ( v10 )
  {
    NgcStatusStorage::Cleanup(v10);
    free(v10);
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
0x1800883b0  push    rbp
0x1800883b2  push    rbx
0x1800883b3  push    rsi
0x1800883b4  push    rdi
0x1800883b5  push    r12
0x1800883b7  push    r13
0x1800883b9  push    r14
0x1800883bb  push    r15
0x1800883bd  lea     rbp, [rsp-158h]
0x1800883c5  sub     rsp, 258h
0x1800883cc  mov     rax, cs:__security_cookie
0x1800883d3  xor     rax, rsp
0x1800883d6  mov     [rbp+190h+var_50], rax
0x1800883dd  mov     r12, [rbp+190h+arg_28]
0x1800883e4  xor     edi, edi
0x1800883e6  mov     [rsp+290h+var_238], r8
0x1800883eb  xorps   xmm0, xmm0
0x1800883ee  mov     [rsp+290h+var_248], ecx
0x1800883f2  mov     eax, edi
0x1800883f4  mov     [rsp+290h+var_260], rax
0x1800883f9  mov     r14d, r9d
0x1800883fc  mov     [rsp+290h+Block], rax
0x180088401  mov     r15, rdx
0x180088404  mov     [rsp+290h+var_230], rdi
0x180088409  mov     r13d, ecx
0x18008840c  mov     [rsp+290h+StringUuid], rdi
0x180088411  mov     ebx, edi
0x180088413  mov     [rbp+190h+Uuid.Data1], edi
0x180088419  mov     esi, edi
0x18008841b  mov     [rsp+290h+var_258], edi
0x18008841f  movups  xmmword ptr [rbp+190h+var_6C], xmm0
0x180088426  movups  xmmword ptr [rbp+190h+Uuid.Data2], xmm0
0x18008842d  movups  [rbp+190h+var_7C], xmm0
0x180088434  movups  xmmword ptr [rbp+190h+var_6C+0Ch], xmm0
0x18008843b  test    r12, r12
0x18008843e  jnz     short loc_18008847B
0x180088440  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x180088447  mov     edi, 80070057h
0x18008844c  mov     rdx, r15
0x18008844f  lea     r8, aPjoininfo; "pJoinInfo"
0x180088456  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008845d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180088462  lea     rdx, aPjoininfo; "pJoinInfo"
0x180088469  mov     rcx, r15; unsigned __int16 *
0x18008846c  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180088471  mov     rcx, [rsp+290h+var_260]
0x180088476  jmp     loc_1800895E9
0x18008847b  xor     edx, edx; Val
0x18008847d  lea     rcx, [rbp+190h+var_1E0]; void *
0x180088481  mov     r8d, 150h; Size
0x180088487  call    memset_0
0x18008848c  mov     edx, 2
0x180088491  lea     rcx, [rbp+190h+var_1E0]
0x180088495  mov     rax, r12
0x180088498  lea     r8d, [rdx+7Eh]
0x18008849c  movups  xmm0, xmmword ptr [rcx]
0x18008849f  movups  xmm1, xmmword ptr [rcx+10h]
0x1800884a3  movups  xmmword ptr [rax], xmm0
0x1800884a6  movups  xmm0, xmmword ptr [rcx+20h]
0x1800884aa  movups  xmmword ptr [rax+10h], xmm1
0x1800884ae  movups  xmm1, xmmword ptr [rcx+30h]
0x1800884b2  movups  xmmword ptr [rax+20h], xmm0
0x1800884b6  movups  xmm0, xmmword ptr [rcx+40h]
0x1800884ba  movups  xmmword ptr [rax+30h], xmm1
0x1800884be  movups  xmm1, xmmword ptr [rcx+50h]
0x1800884c2  movups  xmmword ptr [rax+40h], xmm0
0x1800884c6  movups  xmm0, xmmword ptr [rcx+60h]
0x1800884ca  movups  xmmword ptr [rax+50h], xmm1
0x1800884ce  movups  xmm1, xmmword ptr [rcx+70h]
0x1800884d2  add     rcx, r8
0x1800884d5  movups  xmmword ptr [rax+60h], xmm0
0x1800884d9  movups  xmmword ptr [rax+70h], xmm1
0x1800884dd  add     rax, r8
0x1800884e0  sub     rdx, 1
0x1800884e4  jnz     short loc_18008849C
0x1800884e6  movups  xmm0, xmmword ptr [rcx]
0x1800884e9  movups  xmm1, xmmword ptr [rcx+10h]
0x1800884ed  movups  xmmword ptr [rax], xmm0
0x1800884f0  movups  xmm0, xmmword ptr [rcx+20h]
0x1800884f4  movups  xmmword ptr [rax+10h], xmm1
0x1800884f8  movups  xmm1, xmmword ptr [rcx+30h]
0x1800884fc  movups  xmmword ptr [rax+20h], xmm0
0x180088500  movups  xmm0, xmmword ptr [rcx+40h]
0x180088504  movups  xmmword ptr [rax+30h], xmm1
0x180088508  movups  xmmword ptr [rax+40h], xmm0
0x18008850c  test    r15, r15
0x18008850f  jnz     short loc_18008853F
0x180088511  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x180088518  mov     edi, 80070057h
0x18008851d  mov     rdx, r15
0x180088520  lea     r8, stru_1800C0A68
0x180088527  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x18008852e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180088533  lea     rdx, stru_1800C0A68
0x18008853a  jmp     loc_180088469
0x18008853f  lea     eax, [r13-1]
0x180088543  test    eax, 0FFFFFFFBh
0x180088548  jz      short loc_18008856D
0x18008854a  mov     edi, 80070057h
0x18008854f  lea     rcx, aSInvalidJoinTy; "%s: Invalid join type %d. Only DEVICE a"...
0x180088556  mov     r8d, r13d
0x180088559  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x180088560  mov     rdx, r15
0x180088563  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180088568  jmp     loc_180088471
0x18008856d  mov     rcx, r15; pCertContext
0x180088570  call    cs:__imp_CertDuplicateCertificateContext
0x180088576  mov     [rsp+290h+pCertContext], rax
0x18008857b  test    rax, rax
0x18008857e  jnz     short loc_1800885A7
0x180088580  call    cs:__imp_GetLastError
0x180088586  mov     edi, eax
0x180088588  test    eax, eax
0x18008858a  jle     short loc_180088595
0x18008858c  movzx   edi, ax
0x18008858f  or      edi, 80070000h
0x180088595  call    cs:__imp_GetLastError
0x18008859b  mov     r8d, eax
0x18008859e  lea     rcx, aSCertduplicate; "%s: CertDuplicateCertificateContext fai"...
0x1800885a5  jmp     short loc_180088559
0x1800885a7  lea     r8, [rsp+290h+var_258]; int *
0x1800885ac  mov     rcx, r15; struct _CERT_CONTEXT *
0x1800885af  lea     rdx, [rsp+290h+Block]; unsigned __int16 **
0x1800885b4  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x1800885b9  mov     edi, eax
0x1800885bb  test    eax, eax
0x1800885bd  jns     short loc_1800885E4
0x1800885bf  lea     r8, aRegistrationce_7; "RegistrationCertStatus::GetTenantId"
0x1800885c6  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x1800885cd  mov     r9d, eax
0x1800885d0  mov     rdx, r15
0x1800885d3  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800885da  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800885df  jmp     loc_1800895D9
0x1800885e4  lea     rdx, [rsp+290h+var_230]; unsigned __int16 **
0x1800885e9  mov     rcx, r15; struct _CERT_CONTEXT *
0x1800885ec  call    ?GetDeviceId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAG@Z; RegistrationCertStatus::GetDeviceId(_CERT_CONTEXT const *,ushort * *)
0x1800885f1  mov     edi, eax
0x1800885f3  test    eax, eax
0x1800885f5  jns     short loc_180088600
0x1800885f7  lea     r8, aRegistrationce_8; "RegistrationCertStatus::GetDeviceId"
0x1800885fe  jmp     short loc_1800885C6
0x180088600  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180088607  mov     ecx, 140h; unsigned __int64
0x18008860c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180088611  xor     edx, edx
0x180088613  mov     rbx, rax
0x180088616  test    rax, rax
0x180088619  jz      loc_1800895BC
0x18008861f  mov     rcx, rax; this
0x180088622  call    ?Clear@struct_join_status@@QEAAXXZ; struct_join_status::Clear(void)
0x180088627  mov     eax, [rbp+190h+arg_20]
0x18008862d  mov     ecx, edx
0x18008862f  cmp     r13d, 1
0x180088633  mov     [rsp+290h+var_270], eax; int
0x180088637  mov     r9, rbx; struct struct_join_status *
0x18008863a  mov     r8d, r14d; int
0x18008863d  setz    cl; int
0x180088640  mov     rdx, r15; struct _CERT_CONTEXT *
0x180088643  call    ?ReadJoinStatus@JoinStatusStorage@@SAJHPEBU_CERT_CONTEXT@@HPEAUstruct_join_status@@H@Z; JoinStatusStorage::ReadJoinStatus(int,_CERT_CONTEXT const *,int,struct_join_status *,int)
0x180088648  lea     r15, aDeviceregistra_0; "DeviceRegistrationStateApi::PopulateJoi"...
0x18008864f  mov     edi, eax
0x180088651  lea     rdx, aFalse_0; "FALSE"
0x180088658  lea     r13, aTrue_0; "TRUE"
0x18008865f  test    eax, eax
0x180088661  jns     short loc_180088694
0x180088663  test    r14d, r14d
0x180088666  lea     r8, aJoinstatusstor_5; "JoinStatusStorage::ReadJoinStatus"
0x18008866d  mov     rax, r13
0x180088670  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180088677  cmovz   rax, rdx
0x18008867b  mov     r9d, edi
0x18008867e  mov     rdx, r15
0x180088681  mov     qword ptr [rsp+290h+var_270], rax
0x180088686  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18008868b  test    r14d, r14d
0x18008868e  jz      loc_1800895D9
0x180088694  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008869b  mov     ecx, 10h; unsigned __int64
0x1800886a0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800886a5  mov     rsi, rax
0x1800886a8  xor     eax, eax
0x1800886aa  test    rsi, rsi
0x1800886ad  jz      loc_1800895A4
0x1800886b3  mov     rcx, rsi; this
0x1800886b6  mov     [rsi], rax
0x1800886b9  mov     [rsi+8], rax
0x1800886bd  call    ?Load@NgcStatusStorage@@QEAAJXZ; NgcStatusStorage::Load(void)
0x1800886c2  xor     r8d, r8d
0x1800886c5  mov     edi, eax
0x1800886c7  test    eax, eax
0x1800886c9  jns     short loc_180088706
0x1800886cb  lea     rcx, aFalse_0; "FALSE"
0x1800886d2  test    r14d, r14d
0x1800886d5  mov     rax, r13
0x1800886d8  lea     r8, aNgcstatusstora; "NgcStatusStorage::Load"
0x1800886df  cmovz   rax, rcx
0x1800886e3  mov     r9d, edi
0x1800886e6  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x1800886ed  mov     qword ptr [rsp+290h+var_270], rax
0x1800886f2  mov     rdx, r15
0x1800886f5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800886fa  xor     r8d, r8d
0x1800886fd  test    r14d, r14d
0x180088700  jz      loc_1800895D9
0x180088706  lea     rdx, [rsp+290h+var_220]
0x18008870b  mov     rcx, rsi
0x18008870e  call    ?GetKey@NgcStatusStorage@@QEAA?AUSTRUCT_NGC_REG_KEY@@XZ; NgcStatusStorage::GetKey(void)
0x180088713  cmp     [rsp+290h+var_248], 1
0x180088718  lea     rdx, [r12+18h]; unsigned __int16 **
0x18008871d  mov     rcx, [rsp+290h+pCertContext]
0x180088722  mov     [rsp+290h+var_260], r8
0x180088727  movups  xmm3, xmmword ptr [rax]
0x18008872a  movaps  xmmword ptr [rbp+190h+Uuid.Data1], xmm3
0x180088731  movups  xmm0, xmmword ptr [rax+10h]
0x180088735  movaps  xmmword ptr [rbp+110h], xmm0
0x18008873c  movups  xmm1, xmmword ptr [rax+20h]
0x180088740  movaps  [rbp+190h+var_7C+0Ch], xmm1
0x180088747  movups  xmm0, xmmword ptr [rax+30h]
0x18008874b  mov     eax, r8d
0x18008874e  mov     [r12+8], rcx
0x180088753  setnz   al
0x180088756  inc     eax
0x180088758  movaps  xmmword ptr [rbp+190h+var_6C+0Ch], xmm0
0x18008875f  cmp     [rsp+290h+var_258], r8d
0x180088764  mov     [r12], eax
0x180088768  mov     rax, [rsp+290h+var_230]
0x18008876d  mov     [r12+10h], rax
0x180088772  mov     rax, [rsp+290h+Block]
0x180088777  mov     [r12+20h], rax
0x18008877c  mov     eax, r8d
0x18008877f  setnz   al
0x180088782  mov     [rsp+290h+var_230], r8
0x180088787  mov     [r12+3Ch], eax
0x18008878c  mov     rcx, [rbx+8]; unsigned __int16 *
0x180088790  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180088795  mov     edi, eax
0x180088797  test    eax, eax
0x180088799  jns     short loc_1800887D3
0x18008879b  lea     rcx, aFalse_0; "FALSE"
0x1800887a2  test    r14d, r14d
0x1800887a5  mov     rax, r13
0x1800887a8  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x1800887af  cmovz   rax, rcx
0x1800887b3  mov     r9d, edi
0x1800887b6  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x1800887bd  mov     qword ptr [rsp+290h+var_270], rax
0x1800887c2  mov     rdx, r15
0x1800887c5  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800887ca  test    r14d, r14d
0x1800887cd  jz      loc_180088471
0x1800887d3  mov     rcx, [rbx+18h]; unsigned __int16 *
0x1800887d7  lea     rdx, [r12+28h]; unsigned __int16 **
0x1800887dc  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x1800887e1  mov     edi, eax
0x1800887e3  test    eax, eax
0x1800887e5  jns     short loc_18008881F
0x1800887e7  lea     rcx, aFalse_0; "FALSE"
0x1800887ee  test    r14d, r14d
0x1800887f1  mov     rax, r13
0x1800887f4  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x1800887fb  cmovz   rax, rcx
0x1800887ff  mov     r9d, edi
0x180088802  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180088809  mov     qword ptr [rsp+290h+var_270], rax
0x18008880e  mov     rdx, r15
0x180088811  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180088816  test    r14d, r14d
0x180088819  jz      loc_180088471
0x18008881f  mov     rcx, [rbx+20h]; unsigned __int16 *
0x180088823  lea     rdx, [r12+40h]; unsigned __int16 **
0x180088828  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x18008882d  mov     edi, eax
0x18008882f  test    eax, eax
0x180088831  jns     short loc_18008886B
0x180088833  lea     rcx, aFalse_0; "FALSE"
0x18008883a  test    r14d, r14d
0x18008883d  mov     rax, r13
0x180088840  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180088847  cmovz   rax, rcx
0x18008884b  mov     r9d, edi
0x18008884e  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
0x180088855  mov     qword ptr [rsp+290h+var_270], rax
0x18008885a  mov     rdx, r15
0x18008885d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180088862  test    r14d, r14d
0x180088865  jz      loc_180088471
0x18008886b  mov     rcx, [rbx+28h]; unsigned __int16 *
0x18008886f  lea     rdx, [r12+48h]; unsigned __int16 **
0x180088874  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180088879  mov     edi, eax
0x18008887b  test    eax, eax
0x18008887d  jns     short loc_1800888B7
0x18008887f  lea     rcx, aFalse_0; "FALSE"
0x180088886  test    r14d, r14d
0x180088889  mov     rax, r13
0x18008888c  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180088893  cmovz   rax, rcx
0x180088897  mov     r9d, edi
0x18008889a  lea     rcx, aSSFailedWithEr_0; "%s: %s failed with error code: 0x%08x. "...
  ... truncated ...
```
