# UnpackDownloadedFile

- ea: `0x18000dabc`
- end: `0x18000ea12`
- name: `UnpackDownloadedFile`
- size: `3926`
- prototype: `DWORD __fastcall(__int64, __int64, const WCHAR *, __int64, const WCHAR **, __int64 *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cc50`

## callees

- `0x180001520`
- `0x18000307c`
- `0x1800030c4`
- `0x1800033c0`
- `0x180003514`
- `0x180004d70`
- `0x180004dc4`
- `0x180004dec`
- `0x180004e2c`
- `0x180005588`
- `0x18000838c`
- `0x18000bd60`
- `0x18000beac`
- `0x18000bf9c`
- `0x18000c014`
- `0x18000c398`
- `0x18000dabc`
- `0x18000ede8`
- `0x18000ef74`
- `0x18001066c`
- `0x1800107e4`
- `0x1800108d8`
- `0x180010a84`
- `0x180010bc8`
- `0x180010c40`
- `0x180010ca0`
- `0x180010d18`
- `0x180010e08`
- `0x1800135cc`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000e3da`
- `KERNEL32!GetProcessHeap` at `0x18000e3fb`
- `KERNEL32!GetProcessHeap` at `0x18000e98d`
- `KERNEL32!GetProcessHeap` at `0x18000e3da`
- `KERNEL32!GetProcessHeap` at `0x18000e3fb`
- `KERNEL32!GetProcessHeap` at `0x18000e98d`
- `KERNEL32!HeapFree` at `0x18000e3e8`
- `KERNEL32!HeapFree` at `0x18000e409`
- `KERNEL32!HeapFree` at `0x18000e99c`
- `KERNEL32!HeapFree` at `0x18000e3e8`
- `KERNEL32!HeapFree` at `0x18000e409`
- `KERNEL32!HeapFree` at `0x18000e99c`
- `KERNEL32!GetLastError` at `0x18000dbcf`
- `KERNEL32!GetLastError` at `0x18000ddc9`
- `KERNEL32!GetLastError` at `0x18000e0b6`
- `KERNEL32!GetLastError` at `0x18000e20e`
- `KERNEL32!GetLastError` at `0x18000e8b1`
- `KERNEL32!GetLastError` at `0x18000dbcf`
- `KERNEL32!GetLastError` at `0x18000ddc9`
- `KERNEL32!GetLastError` at `0x18000e0b6`
- `KERNEL32!GetLastError` at `0x18000e20e`
- `KERNEL32!GetLastError` at `0x18000e8b1`
- `KERNEL32!CreateFileW` at `0x18000ddad`
- `KERNEL32!CreateFileW` at `0x18000ddad`
- `KERNEL32!CloseHandle` at `0x18000e9de`
- `KERNEL32!CloseHandle` at `0x18000e9de`
- `KERNEL32!MoveFileW` at `0x18000e8a3`
- `KERNEL32!MoveFileW` at `0x18000e8a3`

## string_xrefs

- `0x18000daf0`: `Packageinfo.xml`
- `0x18000dce2`: `Packageinfo.xml`
- `0x18000dd5a`: `Packageinfo.xml`
- `0x18000ddee`: `Packageinfo.xml`
- `0x18000db08`: `DeviceInfo.xml`
- `0x18000db1f`: `SoftwareInfo.xml`
- `0x18000dd4b`: `Could not find packageinfo.xml within metadata package`
- `0x18000de53`: `Could not find packageinfo.xml within metadata package`
- `0x18000dc59`: `Windows Metadata Information Service`
- `0x18000dd1e`: `Windows Metadata Information Service`
- `0x18000ddb8`: `Windows Metadata Information Service`
- `0x18000e383`: `Windows Metadata Information Service`
- `0x18000e95d`: `Windows Metadata Information Service`
- `0x18000df53`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e135`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e1aa`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e240`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e288`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e2d7`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e414`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e42e`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e476`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e4ce`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e516`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e55e`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e5a6`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e5c0`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e608`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e622`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e66a`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e6b2`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x18000e3af`: `Could not parse packageinfo.xml`

## pseudocode

```c
DWORD __fastcall UnpackDownloadedFile(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        const WCHAR **a5,
        __int64 *a6)
{
  struct IStream *v8; // r15
  TXmlReader *v9; // rsi
  unsigned int v10; // r13d
  __int64 v12; // rbx
  unsigned int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rax
  char v16; // bl
  int v17; // ecx
  const wchar_t *v18; // r8
  __int64 v19; // rax
  unsigned __int16 *v20; // rax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  __int64 v23; // rax
  __int64 v24; // r13
  int v25; // ecx
  int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  int v30; // eax
  int XmlDecleration; // eax
  int StartElement; // eax
  int v33; // eax
  const unsigned __int16 *const *v34; // r12
  _QWORD *v35; // rcx
  __int64 v36; // rdx
  unsigned int EndElement; // eax
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  DWORD v40; // eax
  const unsigned __int16 *const *v41; // r15
  int IsNodeQName; // eax
  int ElementString; // eax
  unsigned __int16 *v44; // rbx
  __int64 v45; // rax
  int v46; // ecx
  void *v47; // rbx
  HANDLE ProcessHeap; // rax
  void *v49; // rbx
  HANDLE v50; // rax
  int v51; // eax
  int v52; // eax
  _QWORD *v53; // rcx
  __int64 v54; // rdx
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rcx
  unsigned __int16 *v64; // rax
  const WCHAR *v65; // r15
  __int64 v66; // r8
  __int64 v67; // r8
  __int64 v68; // rax
  unsigned __int16 *v69; // rax
  __int64 v70; // r12
  DWORD v71; // eax
  _QWORD *v72; // rcx
  __int64 v73; // rax
  HANDLE v74; // rax
  const unsigned __int16 **dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  __int64 v77; // [rsp+48h] [rbp-B8h]
  unsigned int v78; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v79; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v80; // [rsp+58h] [rbp-A8h]
  struct TXmlReader *v81; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v82; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v83; // [rsp+70h] [rbp-90h]
  struct IStream *v84; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v85; // [rsp+80h] [rbp-80h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-78h]
  LPVOID v87; // [rsp+90h] [rbp-70h]
  const WCHAR **v88; // [rsp+98h] [rbp-68h]
  __int64 *v89; // [rsp+A0h] [rbp-60h]
  LPVOID v90; // [rsp+A8h] [rbp-58h]
  _QWORD v91[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v92[8]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR v93[264]; // [rsp+100h] [rbp+0h] BYREF

  v92[0] = L"Packageinfo.xml";
  v92[2] = L"DeviceInfo.xml";
  v80 = a4;
  v92[4] = L"SoftwareInfo.xml";
  v8 = 0;
  v91[0] = a2;
  v9 = 0;
  v88 = a5;
  v10 = 0;
  v89 = a6;
  v84 = 0;
  v81 = 0;
  v78 = 0;
  v79 = 0;
  v92[1] = 1;
  v92[3] = 1;
  v92[5] = 1;
  v92[6] = 0;
  v92[7] = 0;
  v82 = 1;
  v83 = 0;
  v85 = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !a5 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  *a5 = 0;
  *a6 = 0;
  v93[0] = 0;
  v82 = 3;
  v83 = v92;
  if ( !(unsigned int)FSMakeTempDirPath(v93) )
    return GetLastError();
  v12 = -1;
  v77 = -1;
  v13 = CabUnzip(a3, v93, (enum CAB_COMMAND (__high *)(const unsigned __int16 *, void *))&CabCallback, &v82);
  v14 = v13;
  if ( v13 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
        (_DWORD)a3,
        v13);
    v15 = FSGetFileName(a3);
    v16 = 17;
    (*(void (__fastcall **)(__int64, _QWORD, __int64, const WCHAR *, const wchar_t *, int, __int64))(a1 + 56))(
      1342177297,
      v14,
      v15,
      a3,
      L"Windows Metadata Information Service",
      1,
      v80);
    if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) == 0 )
      goto LABEL_187;
    v18 = L"Failed to unpack metadata package";
    goto LABEL_15;
  }
  if ( (_DWORD)v82 != HIDWORD(v82) && !*((_DWORD *)v83 + 3) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
        L"Packageinfo.xml");
    v14 = 13;
    v19 = FSGetFileName(a3);
    v16 = 33;
    (*(void (__fastcall **)(__int64, __int64, __int64, const WCHAR *, const wchar_t *, int, __int64))(a1 + 56))(
      1342177313,
      13,
      v19,
      a3,
      L"Windows Metadata Information Service",
      1,
      v80);
    if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) == 0 )
      goto LABEL_187;
    v18 = L"Could not find packageinfo.xml within metadata package";
LABEL_15:
    McTemplateU0zzdd_EventWriteTransfer(v17, (unsigned int)DMRC_PACKAGE_ERROR, (_DWORD)v18, (_DWORD)a3, v16, v14);
LABEL_187:
    v12 = v77;
    goto LABEL_188;
  }
  v20 = MemMallocAndCat(v93, L"\\", L"Packageinfo.xml", 0);
  v90 = v20;
  if ( v20 )
  {
    lpMem = 0;
    v87 = 0;
    FileW = CreateFileW(v20, 1u, 1u, 0, 3u, 0x8000000u, 0);
    v77 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v14 = LastError;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
          (unsigned int)L"Packageinfo.xml",
          LastError);
      v23 = FSGetFileName(a3);
      v24 = a1;
      (*(void (__fastcall **)(__int64, _QWORD, __int64, const WCHAR *, const wchar_t *, int, __int64))(a1 + 56))(
        1342177313,
        v14,
        v23,
        a3,
        L"Windows Metadata Information Service",
        1,
        v80);
      if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
        McTemplateU0zzdd_EventWriteTransfer(
          v25,
          (unsigned int)DMRC_PACKAGE_ERROR,
          (unsigned int)L"Could not find packageinfo.xml within metadata package",
          (_DWORD)a3,
          33,
          v14);
      goto LABEL_38;
    }
    v26 = TFileStream::Create(FileW, &v84);
    if ( v26 )
    {
      v14 = (unsigned __int16)v26;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v28 = 37;
      goto LABEL_35;
    }
    v30 = TXmlReader::Create(v84, &v81);
    if ( v30 )
    {
      v14 = (unsigned __int16)v30;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          38,
          &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
          (unsigned __int16)v30);
      v9 = v81;
      goto LABEL_37;
    }
    v9 = v81;
    XmlDecleration = TXmlReader::ReadXmlDecleration(v81);
    if ( XmlDecleration )
    {
      v14 = (unsigned __int16)XmlDecleration;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v28 = 39;
      goto LABEL_35;
    }
    StartElement = TXmlReader::ReadStartElement(
                     v9,
                     L"PackageInfo",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( StartElement )
    {
      v14 = (unsigned __int16)StartElement;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v28 = 40;
      goto LABEL_35;
    }
    v33 = TXmlReader::ReadStartElement(
            v9,
            L"MetadataKey",
            L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( v33 )
    {
      v14 = (unsigned __int16)v33;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v28 = 41;
      goto LABEL_35;
    }
    v34 = 0;
    if ( !(unsigned int)TXmlReader::IsNodeQName(
                          v9,
                          L"HardwareIDList",
                          L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/") )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 160LL))(*(_QWORD *)v9) )
      {
        v14 = 13;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v36 = 42;
LABEL_82:
          WPP_SF_(v35[2], v36, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids);
LABEL_108:
          v24 = a1;
          goto LABEL_109;
        }
        goto LABEL_182;
      }
      EndElement = TXmlReader::ReadStartElement(
                     v9,
                     L"HardwareIDList",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
      if ( EndElement )
      {
        v14 = (unsigned __int16)EndElement;
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v39 = 43;
        goto LABEL_66;
      }
      v34 = (const unsigned __int16 *const *)ReadDeviceIdList(v9, L"HardwareID", &v78);
      if ( !v34 )
      {
        v40 = GetLastError();
        v14 = v40;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v28 = 44;
        goto LABEL_71;
      }
      EndElement = TXmlReader::ReadEndElement(
                     v9,
                     L"HardwareIDList",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
      if ( EndElement )
      {
        v14 = (unsigned __int16)EndElement;
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v39 = 45;
        goto LABEL_66;
      }
      v10 = v78;
    }
    v41 = 0;
    if ( !(unsigned int)TXmlReader::IsNodeQName(
                          v9,
                          L"ModelIDList",
                          L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/") )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 160LL))(*(_QWORD *)v9) )
      {
        v14 = 13;
        v35 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v36 = 46;
          goto LABEL_82;
        }
LABEL_182:
        v24 = a1;
        goto LABEL_183;
      }
      EndElement = TXmlReader::ReadStartElement(
                     v9,
                     L"ModelIDList",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
      if ( EndElement )
      {
        v14 = (unsigned __int16)EndElement;
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v39 = 47;
        goto LABEL_66;
      }
      v41 = (const unsigned __int16 *const *)ReadDeviceIdList(v9, L"ModelID", &v79);
      if ( !v41 )
      {
        v40 = GetLastError();
        v14 = v40;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v28 = 48;
LABEL_71:
        v29 = v40;
        goto LABEL_36;
      }
      EndElement = TXmlReader::ReadEndElement(
                     v9,
                     L"ModelIDList",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
      if ( EndElement )
      {
        v14 = (unsigned __int16)EndElement;
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v39 = 49;
LABEL_66:
        WPP_SF_d(v38[2], v39, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, EndElement);
        goto LABEL_37;
      }
    }
    IsNodeQName = TXmlReader::IsNodeQName(
                    v9,
                    L"Locale",
                    L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( IsNodeQName )
    {
      v14 = (unsigned __int16)IsNodeQName;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v28 = 50;
      goto LABEL_35;
    }
    ElementString = TXmlReader::ReadElementString(
                      v9,
                      L"Locale",
                      L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/",
                      (const unsigned __int16 **)&v85);
    if ( ElementString )
    {
      v14 = (unsigned __int16)ElementString;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v28 = 51;
      goto LABEL_35;
    }
    v44 = v85;
    if ( !v85 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a3);
      v14 = 13;
      goto LABEL_108;
    }
    if ( !(unsigned int)TXmlReader::IsNodeQName(
                          v9,
                          L"LastModifiedDate",
                          L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/") )
    {
      v51 = TXmlReader::SkipElement(
              v9,
              L"LastModifiedDate",
              L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
      if ( v51 )
      {
        v14 = (unsigned __int16)v51;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v28 = 53;
        goto LABEL_35;
      }
    }
    v52 = TXmlReader::SkipAnyOtherNodesInElement(
            v9,
            L"MetadataKey",
            L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( v52 )
    {
      v14 = (unsigned __int16)v52;
      v53 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v54 = 54;
      goto LABEL_124;
    }
    v55 = TXmlReader::ReadEndElement(
            v9,
            L"MetadataKey",
            L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( v55 )
    {
      v14 = (unsigned __int16)v55;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_37;
      v28 = 55;
    }
    else
    {
      v56 = TXmlReader::IsNodeQName(
              v9,
              L"PackageStructure",
              L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
      if ( v56 )
      {
        v14 = (unsigned __int16)v56;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_37;
        v28 = 56;
      }
      else
      {
        v57 = TXmlReader::SkipElement(
                v9,
                L"PackageStructure",
                L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
        if ( v57 )
        {
          v14 = (unsigned __int16)v57;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_37;
          v28 = 57;
        }
        else
        {
          if ( (unsigned int)TXmlReader::IsNodeQName(
                               v9,
                               L"Relationships",
                               L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/")
            || (v58 = TXmlReader::SkipElement(
                        v9,
                        L"Relationships",
                        L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/")) == 0 )
          {
            if ( (unsigned int)TXmlReader::IsNodeQName(
                                 v9,
                                 L"MetadataBuilderInformation",
                                 L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/")
              || (v59 = TXmlReader::SkipElement(
                          v9,
                          L"MetadataBuilderInformation",
                          L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/")) == 0 )
            {
              v60 = TXmlReader::SkipAnyOtherNodesInElement(
                      v9,
                      L"PackageInfo",
                      L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
              if ( v60 )
              {
                v14 = (unsigned __int16)v60;
                v53 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
                  goto LABEL_37;
                }
                v54 = 60;
              }
              else
              {
                v61 = TXmlReader::ReadEndElement(
                        v9,
                        L"PackageInfo",
                        L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
                if ( !v61 )
                {
                  if ( !ValidateDeviceIdsInMetadataPackage(v10, v34, v79, v41, dwCreationDisposition) )
                  {
                    if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 8) != 0 )
                      McTemplateU0z_EventWriteTransfer(v63, v62, v91[0]);
                    v24 = a1;
                    v14 = 1296;
                    goto LABEL_184;
                  }
                  v24 = a1;
                  v64 = MemMallocAndCat(*(const unsigned __int16 **)(a1 + 16), L"\\", v44, L"\\", v91[0], 0);
                  lpMem = v64;
                  v65 = v64;
                  if ( !v64 )
                    goto LABEL_174;
                  if ( !(unsigned int)FSMakeDirPathExist_StringSecurityDescriptor(v64, 0) )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        62,
                        &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
                        v65);
                    }
                    goto LABEL_186;
                  }
                  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
                    McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_START_UNPACK_PACKAGE, v66, 1, v91);
                  v14 = CabUnzip(a3, v65, 0, 0);
                  if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
                    McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_STOP_UNPACK_PACKAGE, v67, 1, v91);
                  if ( v14 )
                  {
                    if ( v14 == 18
                      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    {
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        63,
                        &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
                        a3);
                      goto LABEL_109;
                    }
                    goto LABEL_183;
                  }
                  v68 = FSGetFileName(a3);
                  v69 = MemMallocAndCat(v65, L"\\", v68, 0);
                  v87 = v69;
                  v70 = (__int64)v69;
                  if ( !v69 )
                  {
LABEL_174:
                    v14 = 8;
                    goto LABEL_109;
                  }
                  if ( MoveFileW(a3, v69) )
                  {
                    *v88 = v65;
                    *v89 = v70;
                    goto LABEL_186;
                  }
                  v71 = GetLastError();
                  v14 = v71;
                  v72 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        64,
                        &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
                        v71);
                      v72 = WPP_GLOBAL_Control;
                    }
                    if ( v72 != &WPP_GLOBAL_Control && (*((_BYTE *)v72 + 28) & 1) != 0 )
                      WPP_SF_SS(
                        v72[2],
                        65,
                        (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
                        (_DWORD)a3,
                        v70);
                  }
LABEL_38:
                  if ( v14 )
                  {
LABEL_183:
                    if ( v14 == 1296 )
                    {
LABEL_184:
                      v73 = FSGetFileName(a3);
                      (*(void (__fastcall **)(__int64, __int64, __int64, const WCHAR *, const wchar_t *, int, __int64))(v24 + 56))(
                        1342177296,
                        1296,
                        v73,
                        a3,
                        L"Windows Metadata Information Service",
                        1,
                        v80);
LABEL_111:
                      v47 = lpMem;
                      if ( lpMem )
                      {
                        FSRemoveDirPath(lpMem);
                        ProcessHeap = GetProcessHeap();
                        HeapFree(ProcessHeap, 0, v47);
                      }
                      v49 = v87;
                      if ( v87 )
                      {
                        v50 = GetProcessHeap();
                        HeapFree(v50, 0, v49);
                      }
                      goto LABEL_186;
                    }
LABEL_109:
                    v45 = FSGetFileName(a3);
                    (*(void (__fastcall **)(__int64, _QWORD, __int64, const WCHAR *, const wchar_t *, int, __int64))(v24 + 56))(
                      1342177314,
                      v14,
                      v45,
                      a3,
                      L"Windows Metadata Information Service",
                      1,
                      v80);
                    if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
                      McTemplateU0zzdd_EventWriteTransfer(
                        v46,
                        (unsigned int)DMRC_PACKAGE_ERROR,
                        (unsigned int)L"Could not parse packageinfo.xml",
                        (_DWORD)a3,
                        34,
                        v14);
                    goto LABEL_111;
                  }
LABEL_186:
                  v74 = GetProcessHeap();
                  HeapFree(v74, 0, v90);
                  v8 = v84;
                  goto LABEL_187;
                }
                v14 = (unsigned __int16)v61;
                v53 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                {
LABEL_37:
                  v24 = a1;
                  goto LABEL_38;
                }
                v54 = 61;
              }
            }
            else
            {
              v14 = (unsigned __int16)v59;
              v53 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_37;
              }
              v54 = 59;
            }
LABEL_124:
            WPP_SF_(v53[2], v54, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids);
            goto LABEL_37;
          }
          v14 = (unsigned __int16)v58;
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_37;
          v28 = 58;
        }
      }
    }
LABEL_35:
    v29 = v14;
LABEL_36:
    WPP_SF_d(v27[2], v28, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, v29);
    goto LABEL_37;
  }
  v14 = 8;
LABEL_188:
  if ( v9 )
  {
    TXmlReader::~TXmlReader(v9);
    operator delete(v9);
  }
  if ( v8 )
    ((void (__fastcall *)(struct IStream *))v8->lpVtbl->Release)(v8);
  if ( v12 != -1 )
    CloseHandle((HANDLE)v12);
  FSRemoveDirPath(v93);
  return v14;
}

```

## disassembly

```asm
0x18000dabc  push    rbp
0x18000dabe  push    rbx
0x18000dabf  push    rsi
0x18000dac0  push    rdi
0x18000dac1  push    r12
0x18000dac3  push    r13
0x18000dac5  push    r14
0x18000dac7  push    r15
0x18000dac9  lea     rbp, [rsp-228h]
0x18000dad1  sub     rsp, 328h
0x18000dad8  mov     rax, cs:__security_cookie
0x18000dadf  xor     rax, rsp
0x18000dae2  mov     [rbp+260h+var_50], rax
0x18000dae9  mov     rbx, [rbp+260h+arg_20]
0x18000daf0  lea     rax, aPackageinfoXml; "Packageinfo.xml"
0x18000daf7  mov     rdi, [rbp+260h+arg_28]
0x18000dafe  mov     r12, rcx
0x18000db01  mov     [rbp+260h+var_2A0], rax
0x18000db05  mov     r14, r8
0x18000db08  lea     rax, aDeviceinfoXml; "DeviceInfo.xml"
0x18000db0f  mov     [rsp+360h+var_320], rcx
0x18000db14  xor     ecx, ecx
0x18000db16  mov     [rbp+260h+var_290], rax
0x18000db1a  mov     [rsp+360h+var_308], r9
0x18000db1f  lea     rax, aSoftwareinfoXm; "SoftwareInfo.xml"
0x18000db26  mov     [rbp+260h+var_280], rax
0x18000db2a  mov     r15d, ecx
0x18000db2d  mov     [rbp+260h+var_2B0], rdx
0x18000db31  mov     esi, ecx
0x18000db33  mov     [rbp+260h+var_2C8], rbx
0x18000db37  mov     r13d, ecx
0x18000db3a  mov     [rbp+260h+var_2C0], rdi
0x18000db3e  mov     [rsp+360h+var_2E8], rcx
0x18000db43  mov     [rsp+360h+var_300], rcx
0x18000db48  mov     [rsp+360h+var_310], ecx
0x18000db4c  mov     [rsp+360h+var_30C], ecx
0x18000db50  mov     [rbp+260h+var_298], 1
0x18000db58  mov     [rbp+260h+var_288], 1
0x18000db60  mov     [rbp+260h+var_278], 1
0x18000db68  mov     [rbp+260h+var_270], rcx
0x18000db6c  mov     [rbp+260h+var_268], rcx
0x18000db70  mov     [rsp+360h+var_2F8], 1
0x18000db79  mov     [rsp+360h+var_2F0], rcx
0x18000db7e  mov     [rbp+260h+var_2E0], rcx
0x18000db82  test    r12, r12
0x18000db85  jnz     short loc_18000DB8E
0x18000db87  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000db8c  xor     ecx, ecx
0x18000db8e  test    r14, r14
0x18000db91  jnz     short loc_18000DB9A
0x18000db93  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000db98  xor     ecx, ecx
0x18000db9a  test    rbx, rbx
0x18000db9d  jnz     short loc_18000DBA6
0x18000db9f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000dba4  xor     ecx, ecx
0x18000dba6  mov     [rbx], rcx
0x18000dba9  lea     rax, [rbp+260h+var_2A0]
0x18000dbad  mov     [rdi], rcx
0x18000dbb0  mov     [rbp+260h+var_260], cx
0x18000dbb4  lea     rcx, [rbp+260h+var_260]
0x18000dbb8  mov     [rsp+360h+var_2F8], 3
0x18000dbc1  mov     [rsp+360h+var_2F0], rax
0x18000dbc6  call    FSMakeTempDirPath
0x18000dbcb  test    eax, eax
0x18000dbcd  jnz     short loc_18000DBDA
0x18000dbcf  call    cs:__imp_GetLastError
0x18000dbd5  jmp     loc_18000E9EF
0x18000dbda  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000dbde  lea     r9, [rsp+360h+var_2F8]; void *
0x18000dbe3  lea     r8, ?CabCallback@@YA?AW4CAB_COMMAND@@PEBGPEAX@Z; enum CAB_COMMAND (__high *)(const unsigned __int16 *, void *)
0x18000dbea  mov     [rsp+360h+var_318], rbx
0x18000dbef  lea     rdx, [rbp+260h+var_260]; LPCWSTR
0x18000dbf3  mov     rcx, r14; lpFileName
0x18000dbf6  call    ?CabUnzip@@YAKPEBG0P6A?AW4CAB_COMMAND@@0PEAX@Z1@Z; CabUnzip(ushort const *,ushort const *,CAB_COMMAND (*)(ushort const *,void *),void *)
0x18000dbfb  mov     edi, eax
0x18000dbfd  test    eax, eax
0x18000dbff  jz      loc_18000DCA9
0x18000dc05  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dc0c  lea     rbx, WPP_GLOBAL_Control
0x18000dc13  cmp     rcx, rbx
0x18000dc16  jz      short loc_18000DC3A
0x18000dc18  test    byte ptr [rcx+1Ch], 1
0x18000dc1c  jz      short loc_18000DC3A
0x18000dc1e  mov     rcx, [rcx+10h]
0x18000dc22  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000dc29  mov     edx, 22h ; '"'
0x18000dc2e  mov     [rsp+360h+dwCreationDisposition], eax
0x18000dc32  mov     r9, r14
0x18000dc35  call    WPP_SF_SD
0x18000dc3a  mov     rcx, r14
0x18000dc3d  call    FSGetFileName
0x18000dc42  mov     r8, rax
0x18000dc45  mov     ebx, 50000011h
0x18000dc4a  mov     rax, [rsp+360h+var_308]
0x18000dc4f  mov     r9, r14
0x18000dc52  mov     [rsp+360h+hTemplateFile], rax
0x18000dc57  mov     edx, edi
0x18000dc59  lea     rax, aWindowsMetadat; "Windows Metadata Information Service"
0x18000dc60  mov     [rsp+360h+dwFlagsAndAttributes], 1
0x18000dc68  mov     qword ptr [rsp+360h+dwCreationDisposition], rax
0x18000dc6d  mov     ecx, ebx
0x18000dc6f  mov     rax, [r12+38h]
0x18000dc74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc79  test    cs:Microsoft_Windows_UserPnpEnableBits, 20h
0x18000dc80  jz      loc_18000E9A7
0x18000dc86  lea     r8, aFailedToUnpack; "Failed to unpack metadata package"
0x18000dc8d  mov     [rsp+360h+dwFlagsAndAttributes], edi
0x18000dc91  lea     rdx, DMRC_PACKAGE_ERROR
0x18000dc98  mov     r9, r14
0x18000dc9b  mov     [rsp+360h+dwCreationDisposition], ebx
0x18000dc9f  call    McTemplateU0zzdd_EventWriteTransfer
0x18000dca4  jmp     loc_18000E9A7
0x18000dca9  mov     eax, dword ptr [rsp+360h+var_2F8+4]
0x18000dcad  cmp     dword ptr [rsp+360h+var_2F8], eax
0x18000dcb1  jz      loc_18000DD57
0x18000dcb7  mov     rax, [rsp+360h+var_2F0]
0x18000dcbc  cmp     [rax+0Ch], esi
0x18000dcbf  jnz     loc_18000DD57
0x18000dcc5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dccc  lea     rbx, WPP_GLOBAL_Control
0x18000dcd3  cmp     rcx, rbx
0x18000dcd6  jz      short loc_18000DCFA
0x18000dcd8  test    byte ptr [rcx+1Ch], 8
0x18000dcdc  jz      short loc_18000DCFA
0x18000dcde  mov     rcx, [rcx+10h]
0x18000dce2  lea     r9, aPackageinfoXml; "Packageinfo.xml"
0x18000dce9  mov     edx, 23h ; '#'
0x18000dcee  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000dcf5  call    WPP_SF_S
0x18000dcfa  mov     rcx, r14
0x18000dcfd  mov     edi, 0Dh
0x18000dd02  call    FSGetFileName
0x18000dd07  mov     r8, rax
0x18000dd0a  mov     ebx, 50000021h
0x18000dd0f  mov     rax, [rsp+360h+var_308]
0x18000dd14  mov     r9, r14
0x18000dd17  mov     [rsp+360h+hTemplateFile], rax
0x18000dd1c  mov     edx, edi
0x18000dd1e  lea     rax, aWindowsMetadat; "Windows Metadata Information Service"
0x18000dd25  mov     [rsp+360h+dwFlagsAndAttributes], 1
0x18000dd2d  mov     qword ptr [rsp+360h+dwCreationDisposition], rax
0x18000dd32  mov     ecx, ebx
0x18000dd34  mov     rax, [r12+38h]
0x18000dd39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd3e  test    cs:Microsoft_Windows_UserPnpEnableBits, 20h
0x18000dd45  jz      loc_18000E9A7
0x18000dd4b  lea     r8, aCouldNotFindPa; "Could not find packageinfo.xml within m"...
0x18000dd52  jmp     loc_18000DC8D
0x18000dd57  xor     r9d, r9d
0x18000dd5a  lea     r8, aPackageinfoXml; "Packageinfo.xml"
0x18000dd61  lea     rdx, asc_180016E08; "\\"
0x18000dd68  lea     rcx, [rbp+260h+var_260]; unsigned __int16 *
0x18000dd6c  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000dd71  mov     [rbp+260h+var_2B8], rax
0x18000dd75  test    rax, rax
0x18000dd78  jnz     short loc_18000DD82
0x18000dd7a  lea     edi, [rax+8]
0x18000dd7d  jmp     loc_18000E9AC
0x18000dd82  xor     ebx, ebx
0x18000dd84  xor     r9d, r9d; lpSecurityAttributes
0x18000dd87  mov     [rsp+360h+hTemplateFile], rbx; hTemplateFile
0x18000dd8c  mov     rcx, rax; lpFileName
0x18000dd8f  mov     [rsp+360h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000dd97  mov     [rbp+260h+lpMem], rbx
0x18000dd9b  lea     edx, [rbx+1]; dwDesiredAccess
0x18000dd9e  mov     [rbp+260h+var_2D0], rbx
0x18000dda2  mov     r8d, edx; dwShareMode
0x18000dda5  mov     [rsp+360h+dwCreationDisposition], 3; unsigned __int16 **
0x18000ddad  call    cs:__imp_CreateFileW
0x18000ddb3  mov     [rsp+360h+var_318], rax
0x18000ddb8  lea     r12, aWindowsMetadat; "Windows Metadata Information Service"
0x18000ddbf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ddc3  jnz     loc_18000DE6F
0x18000ddc9  call    cs:__imp_GetLastError
0x18000ddcf  mov     edi, eax
0x18000ddd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddd8  lea     rbx, WPP_GLOBAL_Control
0x18000dddf  cmp     rcx, rbx
0x18000dde2  jz      short loc_18000DE0A
0x18000dde4  test    byte ptr [rcx+1Ch], 1
0x18000dde8  jz      short loc_18000DE0A
0x18000ddea  mov     rcx, [rcx+10h]
0x18000ddee  lea     r9, aPackageinfoXml; "Packageinfo.xml"
0x18000ddf5  mov     edx, 24h ; '$'
0x18000ddfa  mov     [rsp+360h+dwCreationDisposition], eax
0x18000ddfe  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000de05  call    WPP_SF_SD
0x18000de0a  mov     rcx, r14
0x18000de0d  call    FSGetFileName
0x18000de12  mov     r13, [rsp+360h+var_320]
0x18000de17  mov     r8, rax
0x18000de1a  mov     rax, [rsp+360h+var_308]
0x18000de1f  mov     ebx, 50000021h
0x18000de24  mov     [rsp+360h+hTemplateFile], rax
0x18000de29  mov     r9, r14
0x18000de2c  mov     [rsp+360h+dwFlagsAndAttributes], 1
0x18000de34  mov     edx, edi
0x18000de36  mov     rax, [r13+38h]
0x18000de3a  mov     ecx, ebx
0x18000de3c  mov     qword ptr [rsp+360h+dwCreationDisposition], r12
0x18000de41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de46  test    cs:Microsoft_Windows_UserPnpEnableBits, 20h
0x18000de4d  jz      short loc_18000DEB9
0x18000de4f  mov     [rsp+360h+dwFlagsAndAttributes], edi
0x18000de53  lea     r8, aCouldNotFindPa; "Could not find packageinfo.xml within m"...
0x18000de5a  mov     r9, r14
0x18000de5d  mov     [rsp+360h+dwCreationDisposition], ebx
0x18000de61  lea     rdx, DMRC_PACKAGE_ERROR
0x18000de68  call    McTemplateU0zzdd_EventWriteTransfer
0x18000de6d  jmp     short loc_18000DEB9
0x18000de6f  lea     rdx, [rsp+360h+var_2E8]; struct IStream **
0x18000de74  mov     rcx, rax; hSourceHandle
0x18000de77  call    ?Create@TFileStream@@SAJPEAXPEAPEAUIStream@@@Z; TFileStream::Create(void *,IStream * *)
0x18000de7c  test    eax, eax
0x18000de7e  jz      short loc_18000DEC6
0x18000de80  movzx   edi, ax
0x18000de83  mov     rcx, cs:WPP_GLOBAL_Control
0x18000de8a  lea     rbx, WPP_GLOBAL_Control
0x18000de91  cmp     rcx, rbx
0x18000de94  jz      short loc_18000DEB4
0x18000de96  test    byte ptr [rcx+1Ch], 1
0x18000de9a  jz      short loc_18000DEB4
0x18000de9c  mov     edx, 25h ; '%'
0x18000dea1  mov     r9d, edi
0x18000dea4  mov     rcx, [rcx+10h]
0x18000dea8  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000deaf  call    WPP_SF_d
0x18000deb4  mov     r13, [rsp+360h+var_320]
0x18000deb9  test    edi, edi
0x18000debb  jz      loc_18000E98D
0x18000dec1  jmp     loc_18000E92F
0x18000dec6  mov     rcx, [rsp+360h+var_2E8]; struct IStream *
0x18000decb  lea     rdx, [rsp+360h+var_300]; struct TXmlReader **
0x18000ded0  call    ?Create@TXmlReader@@SAJPEAUIStream@@PEAPEAV1@@Z; TXmlReader::Create(IStream *,TXmlReader * *)
0x18000ded5  test    eax, eax
0x18000ded7  jz      short loc_18000DF14
0x18000ded9  movzx   edi, ax
0x18000dedc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dee3  lea     rbx, WPP_GLOBAL_Control
0x18000deea  cmp     rcx, rbx
0x18000deed  jz      short loc_18000DF0D
0x18000deef  test    byte ptr [rcx+1Ch], 1
0x18000def3  jz      short loc_18000DF0D
0x18000def5  mov     rcx, [rcx+10h]
0x18000def9  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000df00  mov     edx, 26h ; '&'
0x18000df05  mov     r9d, edi
0x18000df08  call    WPP_SF_d
0x18000df0d  mov     rsi, [rsp+360h+var_300]
0x18000df12  jmp     short loc_18000DEB4
0x18000df14  mov     rsi, [rsp+360h+var_300]
0x18000df19  mov     rcx, rsi; this
0x18000df1c  call    ?ReadXmlDecleration@TXmlReader@@QEAAJXZ; TXmlReader::ReadXmlDecleration(void)
0x18000df21  test    eax, eax
0x18000df23  jz      short loc_18000DF53
0x18000df25  movzx   edi, ax
0x18000df28  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df2f  lea     rbx, WPP_GLOBAL_Control
0x18000df36  cmp     rcx, rbx
0x18000df39  jz      loc_18000DEB4
0x18000df3f  test    byte ptr [rcx+1Ch], 1
0x18000df43  jz      loc_18000DEB4
0x18000df49  mov     edx, 27h ; '''
0x18000df4e  jmp     loc_18000DEA1
0x18000df53  lea     r15, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x18000df5a  mov     rcx, rsi; this
0x18000df5d  mov     r8, r15; unsigned __int16 *
0x18000df60  lea     rdx, aPackageinfo; "PackageInfo"
0x18000df67  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x18000df6c  test    eax, eax
0x18000df6e  jz      short loc_18000DF9E
0x18000df70  movzx   edi, ax
0x18000df73  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df7a  lea     rbx, WPP_GLOBAL_Control
0x18000df81  cmp     rcx, rbx
0x18000df84  jz      loc_18000DEB4
0x18000df8a  test    byte ptr [rcx+1Ch], 1
0x18000df8e  jz      loc_18000DEB4
0x18000df94  mov     edx, 28h ; '('
0x18000df99  jmp     loc_18000DEA1
0x18000df9e  mov     r8, r15; unsigned __int16 *
0x18000dfa1  lea     rdx, aMetadatakey; "MetadataKey"
0x18000dfa8  mov     rcx, rsi; this
0x18000dfab  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x18000dfb0  test    eax, eax
0x18000dfb2  jz      short loc_18000DFE2
0x18000dfb4  movzx   edi, ax
0x18000dfb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dfbe  lea     rbx, WPP_GLOBAL_Control
0x18000dfc5  cmp     rcx, rbx
0x18000dfc8  jz      loc_18000DEB4
0x18000dfce  test    byte ptr [rcx+1Ch], 1
0x18000dfd2  jz      loc_18000DEB4
0x18000dfd8  mov     edx, 29h ; ')'
0x18000dfdd  jmp     loc_18000DEA1
0x18000dfe2  mov     r8, r15; unsigned __int16 *
0x18000dfe5  lea     rdx, aHardwareidlist; "HardwareIDList"
0x18000dfec  mov     rcx, rsi; this
0x18000dfef  mov     r12, rbx
  ... truncated ...
```
