# MdmTaskRequestParserImpl::DecryptCommand(uchar const *,ulong,int,_CRYPTOAPI_BLOB *,ulong,ulong,uchar *,ulong,uchar *,ulong,int *)

- ea: `0x180006aa0`
- end: `0x180007456`
- name: `?DecryptCommand@MdmTaskRequestParserImpl@@AEAAJPEBEKHPEAU_CRYPTOAPI_BLOB@@KKPEAEK2KPEAH@Z`
- size: `2486`
- prototype: `__int64 __fastcall(MdmTaskRequestParserImpl *this, const unsigned __int8 *, unsigned int, int, struct _CRYPTOAPI_BLOB *, unsigned int, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18000745c`

## callees

- `0x180001520`
- `0x180001544`
- `0x1800015b8`
- `0x180001fd4`
- `0x180006548`
- `0x180006620`
- `0x1800067d8`
- `0x180006964`
- `0x180006aa0`
- `0x180008328`

## string_xrefs

- `0x180006b46`: `CPR(pbCommand)`
- `0x180006e0f`: `CPR(pfUpdateSecret)`
- `0x180007378`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmtaskrequestparserimpl.cpp`
- `0x180006b7a`: `CBR(cbCommandSize > 0)`
- `0x180006c04`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_MsgId][1], c_rgdwCommandInfo[CmdInfo_MsgId][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180006c83`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_MsgSize][1], c_rgdwCommandInfo[CmdInfo_MsgSize][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x180006e88`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][1], c_rgdwCommandInfo[CmdInfo_SecKeyId][0], rgbData, (sizeof(*RtlpNumberOf(rgbData))) ))`
- `0x1800070a1`: `CBR(c_rgdwCommandInfo[CmdInfo_Hash][0] < cbCommandSize)`
- `0x1800071a4`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, c_rgdwCommandInfo[CmdInfo_Hash][1], c_rgdwCommandInfo[CmdInfo_Hash][0] - dwEncryptOffset, blobHash.pbData, c_rgdwCommandInfo[CmdInfo_Hash][1] ))`
- `0x18000726d`: `CHR(CopyBytes( pbCommand, cbCommandSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][1], c_rgdwCommandInfo[CmdInfo_SecKeyId][0], blobIntegrity.pbData, blobIntegrity.cbData ))`
- `0x1800072c2`: `CHR(CopyBytes( blobDecryptedData.pbData, blobDecryptedData.cbData, blobDecryptedData.cbData - c_rgdwCommandInfo[CmdInfo_Hash][1], c_rgdwCommandInfo[CmdInfo_ProfileId][0] - dwEncryptOffset, blobIntegrity.pbData + c_rgdwCommandInfo[CmdInfo_SecKeyId][1], blobIntegrity.cbData - c_rgdwCommandInfo[CmdInfo_SecKeyId][1] ))`
- `0x180006d6d`: `CHR(CopyBytes( pbCommand, cbCommandSize, dwCmdSize, c_rgdwCommandInfo[CmdInfo_SecKeyId][0], blobDecryptedData.pbData, blobDecryptedData.cbData ))`

## pseudocode

```c
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
0x180006aa0  mov     [rsp-8+arg_0], rbx
0x180006aa5  push    rbp
0x180006aa6  push    rsi
0x180006aa7  push    rdi
0x180006aa8  push    r12
0x180006aaa  push    r13
0x180006aac  push    r14
0x180006aae  push    r15
0x180006ab0  lea     rbp, [rsp-7]
0x180006ab5  sub     rsp, 100h
0x180006abc  mov     rax, cs:__security_cookie
0x180006ac3  xor     rax, rsp
0x180006ac6  mov     [rbp+37h+var_40], rax
0x180006aca  mov     rax, [rbp+37h+arg_38]
0x180006ace  xorps   xmm0, xmm0
0x180006ad1  mov     rcx, [rbp+37h+arg_20]; this
0x180006ad5  xorps   xmm1, xmm1
0x180006ad8  mov     r12, [rbp+37h+arg_58]
0x180006adf  mov     esi, r9d
0x180006ae2  mov     qword ptr [rbp+37h+var_80.cbData], rax
0x180006ae6  mov     r15d, r8d
0x180006ae9  mov     eax, [rbp+37h+arg_40]
0x180006aef  mov     r13, rdx
0x180006af2  mov     dword ptr [rsp+130h+DestinationSize+4], eax
0x180006af6  mov     edi, 1
0x180006afb  mov     rax, [rbp+37h+arg_48]
0x180006b02  mov     [rbp+37h+Source], rax
0x180006b06  mov     eax, [rbp+37h+arg_50]
0x180006b0c  mov     dword ptr [rsp+130h+DestinationSize], eax
0x180006b10  mov     [rbp+37h+var_70], rcx
0x180006b14  movups  xmmword ptr [rsp+130h+Destination], xmm0
0x180006b19  movups  xmmword ptr [rsp+130h+var_C8.cbData], xmm1
0x180006b1e  movups  xmmword ptr [rsp+130h+var_F0.cbData], xmm0
0x180006b23  movups  xmmword ptr [rbp+37h+var_B0], xmm1
0x180006b27  movups  xmmword ptr [rbp+37h+var_A0], xmm0
0x180006b2b  test    rdx, rdx
0x180006b2e  jnz     short loc_180006B5F
0x180006b30  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006b37  mov     r8d, 80070057h
0x180006b3d  mov     ebx, r8d
0x180006b40  jz      loc_180007384
0x180006b46  lea     rax, aCprPbcommand; "CPR(pbCommand)"
0x180006b4d  mov     [rsp+130h+var_108], rax
0x180006b52  mov     dword ptr [rsp+130h+var_110], 17Eh
0x180006b5a  jmp     loc_180007378
0x180006b5f  test    r15d, r15d
0x180006b62  jnz     short loc_180006B93
0x180006b64  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006b6b  mov     r8d, 80070057h
0x180006b71  mov     ebx, r8d
0x180006b74  jz      loc_180007384
0x180006b7a  lea     rax, aCbrCbcommandsi; "CBR(cbCommandSize > 0)"
0x180006b81  mov     [rsp+130h+var_108], rax
0x180006b86  mov     dword ptr [rsp+130h+var_110], 17Fh
0x180006b8e  jmp     loc_180007378
0x180006b93  test    rcx, rcx
0x180006b96  jnz     short loc_180006BC7
0x180006b98  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006b9f  mov     r8d, 80070057h; unsigned int
0x180006ba5  mov     ebx, r8d
0x180006ba8  jz      loc_180007384
0x180006bae  lea     rax, aCprPblobdecryp_1; "CPR(pblobDecryptedData)"
0x180006bb5  mov     [rsp+130h+var_108], rax
0x180006bba  mov     dword ptr [rsp+130h+var_110], 180h
0x180006bc2  jmp     loc_180007378
0x180006bc7  lea     rax, [rbp+37h+var_60]
0x180006bcb  mov     [rsp+130h+var_100], 20h ; ' '; unsigned __int64
0x180006bd4  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006bd9  mov     r9d, edi; unsigned int
0x180006bdc  mov     dword ptr [rsp+130h+var_110], 0; unsigned int
0x180006be4  movups  xmmword ptr [rbp+37h+var_60.cbData], xmm0
0x180006be8  movups  [rbp+37h+var_50], xmm0
0x180006bec  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006bf1  mov     ebx, eax
0x180006bf3  test    eax, eax
0x180006bf5  jns     short loc_180006C1D
0x180006bf7  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006bfe  jz      loc_180007384
0x180006c04  lea     rax, aChrCopybytesPb; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006c0b  mov     [rsp+130h+var_108], rax
0x180006c10  mov     dword ptr [rsp+130h+var_110], 195h
0x180006c18  jmp     loc_180007375
0x180006c1d  movzx   r14d, byte ptr [rbp+37h+var_60.cbData]
0x180006c22  cmp     r14d, 2
0x180006c26  jnz     short loc_180006C2C
0x180006c28  test    esi, esi
0x180006c2a  jz      short loc_180006C3E
0x180006c2c  cmp     r14d, 3
0x180006c30  jnz     loc_180007353
0x180006c36  test    esi, esi
0x180006c38  jz      loc_180007353
0x180006c3e  xorps   xmm0, xmm0
0x180006c41  mov     [rsp+130h+var_100], 20h ; ' '; unsigned __int64
0x180006c4a  lea     rax, [rbp+37h+var_60]
0x180006c4e  mov     r9d, 2; unsigned int
0x180006c54  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006c59  mov     r8d, r15d; unsigned int
0x180006c5c  mov     rdx, r13; unsigned __int8 *
0x180006c5f  mov     dword ptr [rsp+130h+var_110], edi; unsigned int
0x180006c63  movups  xmmword ptr [rbp+37h+var_60.cbData], xmm0
0x180006c67  movups  [rbp+37h+var_50], xmm0
0x180006c6b  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006c70  mov     ebx, eax
0x180006c72  test    eax, eax
0x180006c74  jns     short loc_180006C9C
0x180006c76  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006c7d  jz      loc_180007384
0x180006c83  lea     rax, aChrCopybytesPb_0; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006c8a  mov     [rsp+130h+var_108], rax
0x180006c8f  mov     dword ptr [rsp+130h+var_110], 1A7h
0x180006c97  jmp     loc_180007375
0x180006c9c  movzx   esi, byte ptr [rbp+37h+var_60.cbData]
0x180006ca0  movzx   eax, byte ptr [rbp+37h+var_60.cbData+1]
0x180006ca4  shl     esi, 8
0x180006ca7  or      esi, eax
0x180006ca9  cmp     esi, 100h
0x180006caf  jbe     short loc_180006CBB
0x180006cb1  mov     ebx, 80004004h
0x180006cb6  jmp     loc_180007384
0x180006cbb  sub     r14d, 2
0x180006cbf  jz      loc_180006D86
0x180006cc5  cmp     r14d, edi
0x180006cc8  jnz     loc_180006E38
0x180006cce  cmp     esi, 9
0x180006cd1  jb      loc_180006E38
0x180006cd7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006cde  mov     ecx, esi; unsigned __int64
0x180006ce0  mov     ebx, esi
0x180006ce2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006ce7  mov     [rsp+130h+var_F0.pbData], rax
0x180006cec  test    rax, rax
0x180006cef  jnz     short loc_180006D20
0x180006cf1  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006cf8  mov     r8d, 8007000Eh
0x180006cfe  mov     ebx, r8d
0x180006d01  jz      loc_180007384
0x180006d07  lea     rax, aCprBlobdecrypt; "CPR(blobDecryptedData.pbData)"
0x180006d0e  mov     [rsp+130h+var_108], rax
0x180006d13  mov     dword ptr [rsp+130h+var_110], 235h
0x180006d1b  jmp     loc_180007378
0x180006d20  mov     r8, rbx; Size
0x180006d23  mov     [rsp+130h+var_F0.cbData], esi
0x180006d27  xor     edx, edx; Val
0x180006d29  mov     rcx, rax; void *
0x180006d2c  call    memset_0
0x180006d31  mov     rax, [rsp+130h+var_F0.pbData]
0x180006d36  mov     r9d, esi; unsigned int
0x180006d39  mov     [rsp+130h+var_100], rbx; unsigned __int64
0x180006d3e  mov     r8d, r15d; unsigned int
0x180006d41  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006d46  mov     rdx, r13; unsigned __int8 *
0x180006d49  mov     dword ptr [rsp+130h+var_110], 3; unsigned int
0x180006d51  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006d56  mov     ebx, eax
0x180006d58  test    eax, eax
0x180006d5a  jns     loc_18000732D
0x180006d60  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006d67  jz      loc_180007384
0x180006d6d  lea     rax, aChrCopybytesPb_3; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006d74  mov     [rsp+130h+var_108], rax
0x180006d79  mov     dword ptr [rsp+130h+var_110], 240h
0x180006d81  jmp     loc_180007375
0x180006d86  mov     r14, qword ptr [rbp+37h+var_80.cbData]
0x180006d8a  test    r14, r14
0x180006d8d  jnz     short loc_180006DBE
0x180006d8f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006d96  mov     r8d, 80070057h
0x180006d9c  mov     ebx, r8d
0x180006d9f  jz      loc_180007384
0x180006da5  lea     rax, aCprPbcurrentse; "CPR(pbCurrentSecret)"
0x180006dac  mov     [rsp+130h+var_108], rax
0x180006db1  mov     dword ptr [rsp+130h+var_110], 1B0h
0x180006db9  jmp     loc_180007378
0x180006dbe  cmp     [rbp+37h+Source], 0
0x180006dc3  jnz     short loc_180006DF4
0x180006dc5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006dcc  mov     r8d, 80070057h
0x180006dd2  mov     ebx, r8d
0x180006dd5  jz      loc_180007384
0x180006ddb  lea     rax, aCprPbupdatings; "CPR(pbUpdatingSecret)"
0x180006de2  mov     [rsp+130h+var_108], rax
0x180006de7  mov     dword ptr [rsp+130h+var_110], 1B1h
0x180006def  jmp     loc_180007378
0x180006df4  test    r12, r12
0x180006df7  jnz     short loc_180006E28
0x180006df9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006e00  mov     r8d, 80070057h
0x180006e06  mov     ebx, r8d
0x180006e09  jz      loc_180007384
0x180006e0f  lea     rax, aCprPfupdatesec; "CPR(pfUpdateSecret)"
0x180006e16  mov     [rsp+130h+var_108], rax
0x180006e1b  mov     dword ptr [rsp+130h+var_110], 1B2h
0x180006e23  jmp     loc_180007378
0x180006e28  lea     eax, [rsi+3]
0x180006e2b  mov     dword ptr [r12], 0
0x180006e33  cmp     eax, 2Dh ; '-'
0x180006e36  jnb     short loc_180006E42
0x180006e38  mov     ebx, 80070005h
0x180006e3d  jmp     loc_180007384
0x180006e42  xorps   xmm0, xmm0
0x180006e45  mov     [rsp+130h+var_100], 20h ; ' '; unsigned __int64
0x180006e4e  lea     rax, [rbp+37h+var_60]
0x180006e52  mov     r9d, edi; unsigned int
0x180006e55  mov     [rsp+130h+var_108], rax; unsigned __int8 *
0x180006e5a  mov     r8d, r15d; unsigned int
0x180006e5d  mov     rdx, r13; unsigned __int8 *
0x180006e60  mov     dword ptr [rsp+130h+var_110], 3; unsigned int
0x180006e68  movups  xmmword ptr [rbp+37h+var_60.cbData], xmm0
0x180006e6c  movups  [rbp+37h+var_50], xmm0
0x180006e70  call    ?CopyBytes@MdmTaskRequestParserImpl@@AEAAJPEBEKKKPEAE_K@Z; MdmTaskRequestParserImpl::CopyBytes(uchar const *,ulong,ulong,ulong,uchar *,unsigned __int64)
0x180006e75  mov     ebx, eax
0x180006e77  test    eax, eax
0x180006e79  jns     short loc_180006EA1
0x180006e7b  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006e82  jz      loc_180007384
0x180006e88  lea     rax, aChrCopybytesPb_2; "CHR(CopyBytes( pbCommand, cbCommandSize"...
0x180006e8f  mov     [rsp+130h+var_108], rax
0x180006e94  mov     dword ptr [rsp+130h+var_110], 1C6h
0x180006e9c  jmp     loc_180007375
0x180006ea1  movzx   eax, byte ptr [rbp+37h+var_60.cbData]
0x180006ea5  cmp     eax, [rbp+37h+arg_28]
0x180006ea8  jz      loc_180006FD9
0x180006eae  cmp     eax, [rbp+37h+arg_30]
0x180006eb1  jz      short loc_180006EE2
0x180006eb3  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006eba  mov     r8d, 80070057h
0x180006ec0  mov     ebx, r8d
0x180006ec3  jz      loc_180007384
0x180006ec9  lea     rax, aCbrDwseckeyidD; "CBR(dwSecKeyId == dwCurrentSecretId || "...
0x180006ed0  mov     [rsp+130h+var_108], rax
0x180006ed5  mov     dword ptr [rsp+130h+var_110], 1CAh
0x180006edd  jmp     loc_180007378
0x180006ee2  mov     r14d, dword ptr [rsp+130h+DestinationSize]
0x180006ee7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006eee  mov     ecx, r14d; unsigned __int64
0x180006ef1  mov     ebx, r14d
0x180006ef4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006ef9  mov     [rsp+130h+Destination+8], rax
0x180006efe  test    rax, rax
0x180006f01  jnz     short loc_180006F32
0x180006f03  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006f0a  mov     r8d, 8007000Eh
0x180006f10  mov     ebx, r8d
0x180006f13  jz      loc_180007384
0x180006f19  lea     rax, aCprBlobshareds; "CPR(blobSharedSecret.pbData)"
0x180006f20  mov     [rsp+130h+var_108], rax
0x180006f25  mov     dword ptr [rsp+130h+var_110], 1D7h
0x180006f2d  jmp     loc_180007378
0x180006f32  mov     r8, [rbp+37h+Source]; Source
0x180006f36  mov     r9, rbx; SourceSize
0x180006f39  mov     rcx, [rsp+130h+Destination+8]; Destination
0x180006f3e  mov     rdx, rbx; DestinationSize
0x180006f41  mov     dword ptr [rsp+130h+Destination], r14d
0x180006f46  call    memcpy_s
0x180006f4b  test    eax, eax
0x180006f4d  jz      short loc_180006F7E
0x180006f4f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006f56  mov     r8d, 80004005h
0x180006f5c  mov     ebx, r8d
0x180006f5f  jz      loc_180007384
0x180006f65  lea     rax, aCbrMemcpySBlob_1; "CBR(memcpy_s(blobSharedSecret.pbData, c"...
0x180006f6c  mov     [rsp+130h+var_108], rax
0x180006f71  mov     dword ptr [rsp+130h+var_110], 1D9h
0x180006f79  jmp     loc_180007378
0x180006f7e  mov     [r12], edi
0x180006f82  cmp     esi, edi
0x180006f84  jbe     loc_180006CB1
0x180006f8a  dec     esi
0x180006f8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006f93  mov     ecx, esi; unsigned __int64
0x180006f95  mov     ebx, esi
0x180006f97  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006f9c  mov     [rsp+130h+var_C8.pbData], rax
0x180006fa1  test    rax, rax
0x180006fa4  jnz     loc_180007078
0x180006faa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180006fb1  mov     r8d, 8007000Eh
0x180006fb7  mov     ebx, r8d
0x180006fba  jz      loc_180007384
0x180006fc0  lea     rax, aCprBlobencrypt; "CPR(blobEncryptedData.pbData)"
0x180006fc7  mov     [rsp+130h+var_108], rax
0x180006fcc  mov     dword ptr [rsp+130h+var_110], 1E8h
0x180006fd4  jmp     loc_180007378
0x180006fd9  mov     r12d, dword ptr [rsp+130h+DestinationSize+4]
0x180006fde  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006fe5  mov     ecx, r12d; unsigned __int64
0x180006fe8  mov     ebx, r12d
0x180006feb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006ff0  mov     [rsp+130h+Destination+8], rax
0x180006ff5  test    rax, rax
0x180006ff8  jnz     short loc_180007029
0x180006ffa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, dil
0x180007001  mov     r8d, 8007000Eh
0x180007007  mov     ebx, r8d
0x18000700a  jz      loc_180007384
0x180007010  lea     rax, aCprBlobshareds; "CPR(blobSharedSecret.pbData)"
0x180007017  mov     [rsp+130h+var_108], rax
0x18000701c  mov     dword ptr [rsp+130h+var_110], 1D0h
0x180007024  jmp     loc_180007378
0x180007029  mov     rcx, [rsp+130h+Destination+8]; Destination
  ... truncated ...
```
