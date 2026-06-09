# MdmTaskRequestParserImpl::DecryptCommand(uchar const *,ulong,int,_CRYPTOAPI_BLOB *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)

- ea: `0x180006b24`
- end: `0x1800074db`
- name: `?DecryptCommand@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAU_CRYPTOAPI_BLOB@@KKPEAEK2KPEAH@Z`
- size: `2487`
- prototype: `__int64 __fastcall(MdmTaskRequestParserImpl *this, const unsigned __int8 *, unsigned int, int, struct _CRYPTOAPI_BLOB *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800074e4`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800015b8`
- `0x180001fd4`
- `0x1800065c0`
- `0x180006698`
- `0x18000685c`
- `0x1800069e8`
- `0x180006b24`
- `0x180008438`

## string_xrefs

- `0x180006bca`: `CPR(pbCommand)`
- `0x180006e93`: `CPR(pfUpdateSecret)`
- `0x1800073fc`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x180006bfe`: `CBR(cbCommandSize > 0)`
- `0x180006c88`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_MsgId][1], c_rgdwCommandInfo[CmdInfo_MsgId][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180006d07`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_MsgSize][1], c_rgdwCommandInfo[CmdInfo_MsgSize][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180006f0c`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][1], c_rgdwCommandInfo[CmdInfo_SecKeyId][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180007125`: `CBR(c_rgdwCommandInfo[CmdInfo_Hash][0] < cbCommandSize)`
- `0x180007228`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_Hash][1], c_rgdwCommandInfo[CmdInfo_Hash][0] - dwEncryptOffset, blobHash.pbData, c_rgdwCommandInfo[CmdInfo_Hash][1] ))`
- `0x1800072f1`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][1], c_rgdwCommandInfo[CmdInfo_SecKeyId][0], blobIntegrity.pbData, blobIntegrity.cbData ))`
- `0x180007346`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, blobDecryptedData.cbData - c_rgdwCommandInfo[CmdInfo_Hash][1], c_rgdwCommandInfo[CmdInfo_ProfileId][0] - dwEncryptOffset, blobIntegrity.pbData + c_rgdwCommandInfo[CmdInfo_SecKeyId][1], blobIntegrity.cbData - c_rgdwCommandInfo[CmdInfo_SecKeyId][1] ))`
- `0x180006df1`: `CHR(CopyBytes( pbCommand, cbCommandSize, dwCmdSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][0], blobDecryptedData.pbData, blobDecryptedData.cbData ))`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MdmTaskRequestParserImpl::DecryptCommand(
        MdmTaskRequestParserImpl *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        int a4,
        struct _CRYPTOAPI_BLOB *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned __int8 *a10,
        unsigned int a11,
        int *a12)
{
  int v15; // ebx
  MdmTaskRequestParserImpl *v16; // rcx
  int cbData_low; // r14d
  DWORD v18; // esi
  int v19; // r14d
  BYTE *v20; // rax
  int v21; // ecx
  MdmTaskRequestParserImpl *v22; // rcx
  const void *v23; // r14
  int v24; // ecx
  int v25; // ecx
  DWORD v26; // esi
  BYTE *v27; // rax
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  unsigned __int8 *v31; // rax
  MdmTaskRequestParserImpl *v32; // rcx
  DWORD cbData; // r8d
  BYTE *v34; // rdx
  DWORD v35; // esi
  unsigned __int8 *v36; // rax
  int v37; // ecx
  unsigned __int8 *v38; // r14
  MdmTaskRequestParserImpl *v39; // rcx
  BYTE *pbData; // rax
  struct _CRYPTOAPI_BLOB *v41; // rcx
  __int64 v42; // rax
  _BYTE *v43; // rcx
  unsigned __int64 v44; // rdx
  __int64 v45; // rcx
  BYTE *v46; // rax
  unsigned __int64 v47; // rdx
  __int64 v48; // rcx
  BYTE *v49; // rax
  unsigned __int64 v50; // rdx
  __int64 v51; // rcx
  unsigned __int8 *v52; // rax
  unsigned __int64 v53; // rdx
  __int64 v54; // rcx
  unsigned __int8 *v55; // rax
  char v57; // [rsp+20h] [rbp-D9h]
  const char *v58; // [rsp+28h] [rbp-D1h]
  struct _CRYPTOAPI_BLOB v59; // [rsp+40h] [rbp-B9h] BYREF
  void *Destination[2]; // [rsp+50h] [rbp-A9h] BYREF
  unsigned int DestinationSize; // [rsp+60h] [rbp-99h]
  unsigned int DestinationSize_4; // [rsp+64h] [rbp-95h]
  struct _CRYPTOAPI_BLOB v63; // [rsp+68h] [rbp-91h] BYREF
  unsigned __int8 *v64[2]; // [rsp+80h] [rbp-79h]
  unsigned __int8 *v65[2]; // [rsp+90h] [rbp-69h]
  void *Source[2]; // [rsp+A0h] [rbp-59h] BYREF
  struct _CRYPTOAPI_BLOB v67; // [rsp+B0h] [rbp-49h] BYREF
  struct _CRYPTOAPI_BLOB *v68; // [rsp+C0h] [rbp-39h]
  struct _CRYPTOAPI_BLOB v69; // [rsp+D0h] [rbp-29h] BYREF
  __int128 v70; // [rsp+E0h] [rbp-19h]

  *(_QWORD *)&v67.cbData = a8;
  DestinationSize_4 = a9;
  Source[0] = a10;
  DestinationSize = a11;
  v68 = a5;
  *(_OWORD *)Destination = 0;
  v63 = 0;
  v59 = 0;
  *(_OWORD *)v64 = 0;
  *(_OWORD *)v65 = 0;
  if ( !a2 )
  {
    v15 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        0,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        126,
        (__int64)"CPR(pbCommand)");
    goto LABEL_96;
  }
  if ( !a3 )
  {
    v15 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)a5,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        127,
        (__int64)"CBR(cbCommandSize > 0)");
    goto LABEL_96;
  }
  if ( !a5 )
  {
    v15 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        128,
        (__int64)"CPR(pblobDecryptedData)");
    goto LABEL_96;
  }
  v69 = 0;
  v70 = 0;
  v15 = MdmTaskRequestParserImpl::CopyBytes(
          (MdmTaskRequestParserImpl *)a5,
          a2,
          a3,
          1u,
          0,
          (unsigned __int8 *)&v69,
          0x20u);
  if ( v15 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_96;
    v58 = "CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_MsgId][1], c_rgdwCommandInfo[CmdInfo_MsgId]"
          "[0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))";
    v57 = -107;
LABEL_95:
    McTemplateU0dsqs_EventWriteTransfer(
      (_DWORD)v16,
      (_DWORD)a2,
      v15,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
      v57,
      (__int64)v58);
    goto LABEL_96;
  }
  cbData_low = LOBYTE(v69.cbData);
  if ( (LOBYTE(v69.cbData) != 2 || a4) && (LOBYTE(v69.cbData) != 3 || !a4) )
  {
    v15 = -2147467260;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_96;
    v58 = "CBR((dwMsgFormat == c_bEncryptedNotification && !fIsSecureChannel) || (dwMsgFormat == c_bNon_EncryptedNotifica"
          "tion && fIsSecureChannel))";
    v57 = -101;
    goto LABEL_95;
  }
  v69 = 0;
  v70 = 0;
  v15 = MdmTaskRequestParserImpl::CopyBytes(v16, a2, a3, 2u, 1u, (unsigned __int8 *)&v69, 0x20u);
  if ( v15 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_96;
    v58 = "CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_MsgSize][1], c_rgdwCommandInfo[CmdInfo_MsgS"
          "ize][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))";
    v57 = -89;
    goto LABEL_95;
  }
  v18 = BYTE1(v69.cbData) | (LOBYTE(v69.cbData) << 8);
  if ( v18 > 0x100 )
  {
LABEL_21:
    v15 = -2147467260;
    goto LABEL_96;
  }
  v19 = cbData_low - 2;
  if ( v19 )
  {
    if ( v19 == 1 && v18 >= 9 )
    {
      v20 = (BYTE *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
      v59.pbData = v20;
      if ( !v20 )
      {
        v15 = -2147024882;
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v21,
            (_DWORD)a2,
            -2147024882,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
            53,
            (__int64)"CPR(blobDecryptedData.pbData)");
        goto LABEL_96;
      }
      v59.cbData = v18;
      memset_0(v20, 0, v18);
      v15 = MdmTaskRequestParserImpl::CopyBytes(v22, a2, a3, v18, 3u, v59.pbData, v18);
      if ( v15 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_96;
        v58 = "CHR(CopyBytes( pbCommand, cbCommandSize, dwCmdSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][0], blobDecryptedD"
              "ata.pbData, blobDecryptedData.cbData ))";
        v57 = 64;
        goto LABEL_95;
      }
LABEL_92:
      pbData = v59.pbData;
      v41 = v68;
      v59.pbData = 0;
      v68->pbData = pbData;
      v41->cbData = v59.cbData;
      v59.cbData = 0;
      goto LABEL_96;
    }
LABEL_41:
    v15 = -2147024891;
    goto LABEL_96;
  }
  v23 = *(const void **)&v67.cbData;
  if ( !*(_QWORD *)&v67.cbData )
  {
    v15 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)v16,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        176,
        (__int64)"CPR(pbCurrentSecret)");
    goto LABEL_96;
  }
  if ( !Source[0] )
  {
    v15 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)v16,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        177,
        (__int64)"CPR(pbUpdatingSecret)");
    goto LABEL_96;
  }
  if ( !a12 )
  {
    v15 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        (_DWORD)v16,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        178,
        (__int64)"CPR(pfUpdateSecret)");
    goto LABEL_96;
  }
  *a12 = 0;
  if ( v18 + 3 < 0x2D )
    goto LABEL_41;
  v69 = 0;
  v70 = 0;
  v15 = MdmTaskRequestParserImpl::CopyBytes(v16, a2, a3, 1u, 3u, (unsigned __int8 *)&v69, 0x20u);
  if ( v15 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_96;
    v58 = "CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][1], c_rgdwCommandInfo[CmdInfo_Sec"
          "KeyId][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))";
    v57 = -58;
    goto LABEL_95;
  }
  if ( LOBYTE(v69.cbData) == a6 )
  {
    Destination[1] = operator new[](DestinationSize_4, (const struct std::nothrow_t *)&std::nothrow);
    if ( !Destination[1] )
    {
      v15 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v29,
          (_DWORD)a2,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          208,
          (__int64)"CPR(blobSharedSecret.pbData)");
      goto LABEL_96;
    }
    LODWORD(Destination[0]) = DestinationSize_4;
    if ( memcpy_s(Destination[1], DestinationSize_4, v23, DestinationSize_4) )
    {
      v15 = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v30,
          (_DWORD)a2,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          210,
          (__int64)"CBR(memcpy_s(blobSharedSecret.pbData, cbCurrentSecretSize, pbCurrentSecret, cbCurrentSecretSize) == 0)");
      goto LABEL_96;
    }
  }
  else
  {
    if ( LOBYTE(v69.cbData) != a7 )
    {
      v15 = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v16,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          202,
          (__int64)"CBR(dwSecKeyId == dwCurrentSecretId || dwSecKeyId == dwUpdatingSecretId)");
      goto LABEL_96;
    }
    Destination[1] = operator new[](DestinationSize, (const struct std::nothrow_t *)&std::nothrow);
    if ( !Destination[1] )
    {
      v15 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v24,
          (_DWORD)a2,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          215,
          (__int64)"CPR(blobSharedSecret.pbData)");
      goto LABEL_96;
    }
    LODWORD(Destination[0]) = DestinationSize;
    if ( memcpy_s(Destination[1], DestinationSize, Source[0], DestinationSize) )
    {
      v15 = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v25,
          (_DWORD)a2,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          217,
          (__int64)"CBR(memcpy_s(blobSharedSecret.pbData, cbUpdatingSecretSize, pbUpdatingSecret, cbUpdatingSecretSize) == 0)");
      goto LABEL_96;
    }
    *a12 = 1;
  }
  if ( v18 <= 1 )
    goto LABEL_21;
  v26 = v18 - 1;
  v27 = (BYTE *)operator new[](v26, (const struct std::nothrow_t *)&std::nothrow);
  v63.pbData = v27;
  if ( v27 )
  {
    v63.cbData = v26;
    memset_0(v27, 0, v26);
    if ( a3 <= 4 )
    {
      v15 = -2147467260;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_96;
      v58 = "CBR(c_rgdwCommandInfo[CmdInfo_Hash][0] < cbCommandSize)";
      v57 = -21;
      goto LABEL_95;
    }
    memcpy_s(v63.pbData, v26, a2 + 4, v26);
    v15 = MdmCrypto::DecryptData(&v63, (const struct _CRYPTOAPI_BLOB *)Destination, &v59);
    if ( v15 < 0 )
    {
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_96;
      v58 = "CHR(MdmCrypto::DecryptData(blobEncryptedData, blobSharedSecret, &blobDecryptedData))";
      v57 = -17;
      goto LABEL_95;
    }
    v31 = (unsigned __int8 *)operator new[](0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v64[1] = v31;
    if ( v31 )
    {
      cbData = v59.cbData;
      v34 = v59.pbData;
      *(_OWORD *)v31 = 0;
      *((_OWORD *)v31 + 1) = 0;
      LODWORD(v64[0]) = 32;
      v15 = MdmTaskRequestParserImpl::CopyBytes(v32, v34, cbData, 0x20u, 0, v64[1], 0x20u);
      if ( v15 < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
          goto LABEL_96;
        v58 = "CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_Hash][1], c_r"
              "gdwCommandInfo[CmdInfo_Hash][0] - dwEncryptOffset, blobHash.pbData, c_rgdwCommandInfo[CmdInfo_Hash][1] ))";
        v57 = -2;
        goto LABEL_95;
      }
      if ( v59.cbData + 1 <= 0x20 )
        goto LABEL_21;
      v35 = v59.cbData - 31;
      if ( v59.cbData - 31 <= 1 )
        goto LABEL_21;
      v36 = (unsigned __int8 *)operator new[](v35, (const struct std::nothrow_t *)&std::nothrow);
      v65[1] = v36;
      v38 = v36;
      if ( v36 )
      {
        LODWORD(v65[0]) = v35;
        memset_0(v36, 0, v35);
        v15 = MdmTaskRequestParserImpl::CopyBytes(v39, a2, a3, 1u, 3u, v65[1], v35);
        if ( v15 < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_96;
          v58 = "CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][1], c_rgdwCommandInfo[CmdIn"
                "fo_SecKeyId][0], blobIntegrity.pbData, blobIntegrity.cbData ))";
          v57 = 22;
          goto LABEL_95;
        }
        v15 = MdmTaskRequestParserImpl::CopyBytes(
                (MdmTaskRequestParserImpl *)(v35 - 1),
                v59.pbData,
                v59.cbData,
                v59.cbData - 32,
                0x20u,
                v38 + 1,
                v35 - 1);
        if ( v15 < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_96;
          v58 = "CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, blobDecryptedData.cbData - c_rgdwComm"
                "andInfo[CmdInfo_Hash][1], c_rgdwCommandInfo[CmdInfo_ProfileId][0] - dwEncryptOffset, blobIntegrity.pbDat"
                "a + c_rgdwCommandInfo[CmdInfo_SecKeyId][1], blobIntegrity.cbData - c_rgdwCommandInfo[CmdInfo_SecKeyId][1] ))";
          v57 = 31;
          goto LABEL_95;
        }
        v67 = *(struct _CRYPTOAPI_BLOB *)v65;
        v69 = *(struct _CRYPTOAPI_BLOB *)v64;
        *(_OWORD *)Source = *(_OWORD *)Destination;
        v15 = MdmTaskRequestParserImpl::CheckDataIntegrity(v16, &v69, (struct _CRYPTOAPI_BLOB *)Source, &v67);
        if ( v15 < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
            goto LABEL_96;
          v58 = "CHR(CheckDataIntegrity(blobHash, blobSharedSecret, blobIntegrity))";
          v57 = 34;
          goto LABEL_95;
        }
        goto LABEL_92;
      }
      v15 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v37,
          (_DWORD)a2,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          11,
          (__int64)"CPR(blobIntegrity.pbData)");
    }
    else
    {
      v15 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)v32,
          (_DWORD)a2,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
          243,
          (__int64)"CPR(blobHash.pbData)");
    }
  }
  else
  {
    v15 = -2147024882;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v28,
        (_DWORD)a2,
        -2147024882,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmtaskrequestparserimpl.cpp",
        232,
        (__int64)"CPR(blobEncryptedData.pbData)");
  }
LABEL_96:
  v42 = LODWORD(Destination[0]);
  v43 = Destination[1];
  if ( LODWORD(Destination[0]) )
  {
    do
    {
      *v43++ = 0;
      --v42;
    }
    while ( v42 );
  }
  operator delete(Destination[1], (unsigned __int64)a2);
  v45 = v63.cbData;
  v46 = v63.pbData;
  if ( v63.cbData )
  {
    do
    {
      *v46++ = 0;
      --v45;
    }
    while ( v45 );
  }
  operator delete(v63.pbData, v44);
  v48 = v59.cbData;
  v49 = v59.pbData;
  if ( v59.cbData )
  {
    do
    {
      *v49++ = 0;
      --v48;
    }
    while ( v48 );
  }
  operator delete(v59.pbData, v47);
  v51 = LODWORD(v64[0]);
  v52 = v64[1];
  if ( LODWORD(v64[0]) )
  {
    do
    {
      *v52++ = 0;
      --v51;
    }
    while ( v51 );
  }
  operator delete(v64[1], v50);
  v54 = LODWORD(v65[0]);
  v55 = v65[1];
  if ( LODWORD(v65[0]) )
  {
    do
    {
      *v55++ = 0;
      --v54;
    }
    while ( v54 );
  }
  operator delete(v65[1], v53);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180006b24  mov     [rsp-8+arg_0], rbx
0x180006b29  push    rbp
0x180006b2a  push    rsi
0x180006b2b  push    rdi
0x180006b2c  push    r12
0x180006b2e  push    r13
0x180006b30  push    r14
0x180006b32  push    r15
0x180006b34  lea     rbp, [rsp-7]
0x180006b39  sub     rsp, 100h
0x180006b40  mov     rax, cs:__security_cookie
0x180006b47  xor     rax, rsp
0x180006b4a  mov     [rbp+37h+var_40], rax
0x180006b4e  mov     rax, [rbp+37h+arg_38]
0x180006b52  xorps   xmm0, xmm0
0x180006b55  mov     rcx, [rbp+37h+arg_20]; this
0x180006b59  xorps   xmm1, xmm1
0x180006b5c  mov     r12, [rbp+37h+arg_58]
0x180006b63  mov     esi, r9d
0x180006b66  mov     qword ptr [rbp+37h+var_80.cbData], rax
0x180006b6a  mov     r15d, r8d
0x180006b6d  mov     eax, [rbp+37h+arg_40]
0x180006b73  mov     r13, rdx
0x180006b76  mov     dword ptr [rsp+130h+DestinationSize+4], eax
0x180006b7a  mov     edi, 1
0x180006b7f  mov     rax, [rbp+37h+arg_48]
0x180006b86  mov     [rbp+37h+Source], rax
0x180006b8a  mov     eax, [rbp+37h+arg_50]
0x180006b90  mov     dword ptr [rsp+130h+DestinationSize], eax
0x180006b94  mov     [rbp+37h+var_70], rcx
0x180006b98  movups  xmmword ptr [rsp+130h+Destination], xmm0
0x180006b9d  movups  xmmword ptr [rsp+130h+var_C8.cbData], xmm1
0x180006ba2  movups  xmmword ptr [rsp+130h+var_F0.cbData], xmm0
0x180006ba7  movups  xmmword ptr [rbp+37h+var_B0], xmm1
0x180006bab  movups  xmmword ptr [rbp+37h+var_A0], xmm0
0x180006baf  test    rdx, rdx
0x180006bb2  jnz     short loc_180006BE3
0x180006bb4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006bbb  mov     r8d, 80070057h
0x180006bc1  mov     ebx, r8d
0x180006bc4  jz      loc_180007408
0x180006bca  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180006bd1  mov     [rsp+130h+var_108], rax
0x180006bd6  mov     dword ptr [rsp+130h+var_110], 17Eh
0x180006bde  jmp     loc_1800073FC
0x180006be3  test    r15d, r15d
0x180006be6  jnz     short loc_180006C17
0x180006be8  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006bef  mov     r8d, 80070057h
0x180006bf5  mov     ebx, r8d
0x180006bf8  jz      loc_180007408
0x180006bfe  lea     rax, aCbrCbcommandsi; "CBR(cbCommandSize > 0)"
0x180006c05  mov     [rsp+130h+var_108], rax
0x180006c0a  mov     dword ptr [rsp+130h+var_110], 17Fh
0x180006c12  jmp     loc_1800073FC
0x180006c17  test    rcx, rcx
0x180006c1a  jnz     short loc_180006C4B
0x180006c1c  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006c23  mov     r8d, 80070057h; unsigned int
0x180006c29  mov     ebx, r8d
0x180006c2c  jz      loc_180007408
0x180006c32  lea     rax, aCprPblobdecryp_1; "CPR(pblobDecryptedData)"
0x180006c39  mov     [rsp+130h+var_108], rax
0x180006c3e  mov     dword ptr [rsp+130h+var_110], 180h
0x180006c46  jmp     loc_1800073FC
0x180006c4b  lea     rax, [rbp+37h+var_60]
0x180006c4f  mov     [rsp+130h+var_100], 20h ; ' '; unsigned __int64
0x180006c58  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006c5d  mov     r9d, edi; unsigned int
0x180006c60  mov     dword ptr [rsp+130h+var_110], 0; unsigned int
0x180006c68  movups  xmmword ptr [rbp+37h+var_60.cbData], xmm0
0x180006c6c  movups  [rbp+37h+var_50], xmm0
0x180006c70  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006c75  mov     ebx, eax
0x180006c77  test    eax, eax
0x180006c79  jns     short loc_180006CA1
0x180006c7b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006c82  jz      loc_180007408
0x180006c88  lea     rax, aChrCopybytesPb; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006c8f  mov     [rsp+130h+var_108], rax
0x180006c94  mov     dword ptr [rsp+130h+var_110], 195h
0x180006c9c  jmp     loc_1800073F9
0x180006ca1  movzx   r14d, byte ptr [rbp+37h+var_60.cbData]
0x180006ca6  cmp     r14d, 2
0x180006caa  jnz     short loc_180006CB0
0x180006cac  test    esi, esi
0x180006cae  jz      short loc_180006CC2
0x180006cb0  cmp     r14d, 3
0x180006cb4  jnz     loc_1800073D7
0x180006cba  test    esi, esi
0x180006cbc  jz      loc_1800073D7
0x180006cc2  xorps   xmm0, xmm0
0x180006cc5  mov     [rsp+130h+var_100], 20h ; ' '; unsigned __int64
0x180006cce  lea     rax, [rbp+37h+var_60]
0x180006cd2  mov     r9d, 2; unsigned int
0x180006cd8  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006cdd  mov     r8d, r15d; unsigned int
0x180006ce0  mov     rdx, r13; unsigned __int8 *
0x180006ce3  mov     dword ptr [rsp+130h+var_110], edi; unsigned int
0x180006ce7  movups  xmmword ptr [rbp+37h+var_60.cbData], xmm0
0x180006ceb  movups  [rbp+37h+var_50], xmm0
0x180006cef  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006cf4  mov     ebx, eax
0x180006cf6  test    eax, eax
0x180006cf8  jns     short loc_180006D20
0x180006cfa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006d01  jz      loc_180007408
0x180006d07  lea     rax, aChrCopybytesPb_0; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006d0e  mov     [rsp+130h+var_108], rax
0x180006d13  mov     dword ptr [rsp+130h+var_110], 1A7h
0x180006d1b  jmp     loc_1800073F9
0x180006d20  movzx   esi, byte ptr [rbp+37h+var_60.cbData]
0x180006d24  movzx   eax, byte ptr [rbp+37h+var_60.cbData+1]
0x180006d28  shl     esi, 8
0x180006d2b  or      esi, eax
0x180006d2d  cmp     esi, 100h
0x180006d33  jbe     short loc_180006D3F
0x180006d35  mov     ebx, 80004004h
0x180006d3a  jmp     loc_180007408
0x180006d3f  sub     r14d, 2
0x180006d43  jz      loc_180006E0A
0x180006d49  cmp     r14d, edi
0x180006d4c  jnz     loc_180006EBC
0x180006d52  cmp     esi, 9
0x180006d55  jb      loc_180006EBC
0x180006d5b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006d62  mov     ecx, esi; unsigned __int64
0x180006d64  mov     ebx, esi
0x180006d66  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006d6b  mov     [rsp+130h+var_F0.pbData], rax
0x180006d70  test    rax, rax
0x180006d73  jnz     short loc_180006DA4
0x180006d75  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006d7c  mov     r8d, 8007000Eh
0x180006d82  mov     ebx, r8d
0x180006d85  jz      loc_180007408
0x180006d8b  lea     rax, aCprBlobdecrypt; "CPR(blobDecryptedData.pbData)"
0x180006d92  mov     [rsp+130h+var_108], rax
0x180006d97  mov     dword ptr [rsp+130h+var_110], 235h
0x180006d9f  jmp     loc_1800073FC
0x180006da4  mov     r8, rbx; Size
0x180006da7  mov     [rsp+130h+var_F0.cbData], esi
0x180006dab  xor     edx, edx; Val
0x180006dad  mov     rcx, rax; void *
0x180006db0  call    memset_0
0x180006db5  mov     rax, [rsp+130h+var_F0.pbData]
0x180006dba  mov     r9d, esi; unsigned int
0x180006dbd  mov     [rsp+130h+var_100], rbx; unsigned __int64
0x180006dc2  mov     r8d, r15d; unsigned int
0x180006dc5  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006dca  mov     rdx, r13; unsigned __int8 *
0x180006dcd  mov     dword ptr [rsp+130h+var_110], 3; unsigned int
0x180006dd5  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006dda  mov     ebx, eax
0x180006ddc  test    eax, eax
0x180006dde  jns     loc_1800073B1
0x180006de4  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006deb  jz      loc_180007408
0x180006df1  lea     rax, aChrCopybytesPb_3; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006df8  mov     [rsp+130h+var_108], rax
0x180006dfd  mov     dword ptr [rsp+130h+var_110], 240h
0x180006e05  jmp     loc_1800073F9
0x180006e0a  mov     r14, qword ptr [rbp+37h+var_80.cbData]
0x180006e0e  test    r14, r14
0x180006e11  jnz     short loc_180006E42
0x180006e13  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006e1a  mov     r8d, 80070057h
0x180006e20  mov     ebx, r8d
0x180006e23  jz      loc_180007408
0x180006e29  lea     rax, aCprPbcurrentse; "CPR(pbCurrentSecret)"
0x180006e30  mov     [rsp+130h+var_108], rax
0x180006e35  mov     dword ptr [rsp+130h+var_110], 1B0h
0x180006e3d  jmp     loc_1800073FC
0x180006e42  cmp     [rbp+37h+Source], 0
0x180006e47  jnz     short loc_180006E78
0x180006e49  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006e50  mov     r8d, 80070057h
0x180006e56  mov     ebx, r8d
0x180006e59  jz      loc_180007408
0x180006e5f  lea     rax, aCprPbupdatings; "CPR(pbUpdatingSecret)"
0x180006e66  mov     [rsp+130h+var_108], rax
0x180006e6b  mov     dword ptr [rsp+130h+var_110], 1B1h
0x180006e73  jmp     loc_1800073FC
0x180006e78  test    r12, r12
0x180006e7b  jnz     short loc_180006EAC
0x180006e7d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006e84  mov     r8d, 80070057h
0x180006e8a  mov     ebx, r8d
0x180006e8d  jz      loc_180007408
0x180006e93  lea     rax, aCprPfupdatesec; "CPR(pfUpdateSecret)"
0x180006e9a  mov     [rsp+130h+var_108], rax
0x180006e9f  mov     dword ptr [rsp+130h+var_110], 1B2h
0x180006ea7  jmp     loc_1800073FC
0x180006eac  lea     eax, [rsi+3]
0x180006eaf  mov     dword ptr [r12], 0
0x180006eb7  cmp     eax, 2Dh ; '-'
0x180006eba  jnb     short loc_180006EC6
0x180006ebc  mov     ebx, 80070005h
0x180006ec1  jmp     loc_180007408
0x180006ec6  xorps   xmm0, xmm0
0x180006ec9  mov     [rsp+130h+var_100], 20h ; ' '; unsigned __int64
0x180006ed2  lea     rax, [rbp+37h+var_60]
0x180006ed6  mov     r9d, edi; unsigned int
0x180006ed9  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006ede  mov     r8d, r15d; unsigned int
0x180006ee1  mov     rdx, r13; unsigned __int8 *
0x180006ee4  mov     dword ptr [rsp+130h+var_110], 3; unsigned int
0x180006eec  movups  xmmword ptr [rbp+37h+var_60.cbData], xmm0
0x180006ef0  movups  [rbp+37h+var_50], xmm0
0x180006ef4  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006ef9  mov     ebx, eax
0x180006efb  test    eax, eax
0x180006efd  jns     short loc_180006F25
0x180006eff  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006f06  jz      loc_180007408
0x180006f0c  lea     rax, aChrCopybytesPb_2; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006f13  mov     [rsp+130h+var_108], rax
0x180006f18  mov     dword ptr [rsp+130h+var_110], 1C6h
0x180006f20  jmp     loc_1800073F9
0x180006f25  movzx   eax, byte ptr [rbp+37h+var_60.cbData]
0x180006f29  cmp     eax, [rbp+37h+arg_28]
0x180006f2c  jz      loc_18000705D
0x180006f32  cmp     eax, [rbp+37h+arg_30]
0x180006f35  jz      short loc_180006F66
0x180006f37  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006f3e  mov     r8d, 80070057h
0x180006f44  mov     ebx, r8d
0x180006f47  jz      loc_180007408
0x180006f4d  lea     rax, aCbrDwseckeyidD; "CBR(dwSecKeyId == dwCurrentSecretId || "...
0x180006f54  mov     [rsp+130h+var_108], rax
0x180006f59  mov     dword ptr [rsp+130h+var_110], 1CAh
0x180006f61  jmp     loc_1800073FC
0x180006f66  mov     r14d, dword ptr [rsp+130h+DestinationSize]
0x180006f6b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006f72  mov     ecx, r14d; unsigned __int64
0x180006f75  mov     ebx, r14d
0x180006f78  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006f7d  mov     [rsp+130h+Destination+8], rax
0x180006f82  test    rax, rax
0x180006f85  jnz     short loc_180006FB6
0x180006f87  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006f8e  mov     r8d, 8007000Eh
0x180006f94  mov     ebx, r8d
0x180006f97  jz      loc_180007408
0x180006f9d  lea     rax, aCprBlobshareds; "CPR(blobSharedSecret.pbData)"
0x180006fa4  mov     [rsp+130h+var_108], rax
0x180006fa9  mov     dword ptr [rsp+130h+var_110], 1D7h
0x180006fb1  jmp     loc_1800073FC
0x180006fb6  mov     r8, [rbp+37h+Source]; Source
0x180006fba  mov     r9, rbx; SourceSize
0x180006fbd  mov     rcx, [rsp+130h+Destination+8]; Destination
0x180006fc2  mov     rdx, rbx; DestinationSize
0x180006fc5  mov     dword ptr [rsp+130h+Destination], r14d
0x180006fca  call    memcpy_s
0x180006fcf  test    eax, eax
0x180006fd1  jz      short loc_180007002
0x180006fd3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006fda  mov     r8d, 80004005h
0x180006fe0  mov     ebx, r8d
0x180006fe3  jz      loc_180007408
0x180006fe9  lea     rax, aCbrMemcpySBlob_1; "CBR(memcpy_s(blobSharedSecret.pbData, c"...
0x180006ff0  mov     [rsp+130h+var_108], rax
0x180006ff5  mov     dword ptr [rsp+130h+var_110], 1D9h
0x180006ffd  jmp     loc_1800073FC
0x180007002  mov     [r12], edi
0x180007006  cmp     esi, edi
0x180007008  jbe     loc_180006D35
0x18000700e  dec     esi
0x180007010  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007017  mov     ecx, esi; unsigned __int64
0x180007019  mov     ebx, esi
0x18000701b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007020  mov     [rsp+130h+var_C8.pbData], rax
0x180007025  test    rax, rax
0x180007028  jnz     loc_1800070FC
0x18000702e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180007035  mov     r8d, 8007000Eh
0x18000703b  mov     ebx, r8d
0x18000703e  jz      loc_180007408
0x180007044  lea     rax, aCprBlobencrypt; "CPR(blobEncryptedData.pbData)"
0x18000704b  mov     [rsp+130h+var_108], rax
0x180007050  mov     dword ptr [rsp+130h+var_110], 1E8h
0x180007058  jmp     loc_1800073FC
0x18000705d  mov     r12d, dword ptr [rsp+130h+DestinationSize+4]
0x180007062  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007069  mov     ecx, r12d; unsigned __int64
0x18000706c  mov     ebx, r12d
0x18000706f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007074  mov     [rsp+130h+Destination+8], rax
0x180007079  test    rax, rax
0x18000707c  jnz     short loc_1800070AD
0x18000707e  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180007085  mov     r8d, 8007000Eh
0x18000708b  mov     ebx, r8d
0x18000708e  jz      loc_180007408
0x180007094  lea     rax, aCprBlobshareds; "CPR(blobSharedSecret.pbData)"
0x18000709b  mov     [rsp+130h+var_108], rax
0x1800070a0  mov     dword ptr [rsp+130h+var_110], 1D0h
0x1800070a8  jmp     loc_1800073FC
0x1800070ad  mov     rcx, [rsp+130h+Destination+8]; Destination
  ... truncated ...
```
