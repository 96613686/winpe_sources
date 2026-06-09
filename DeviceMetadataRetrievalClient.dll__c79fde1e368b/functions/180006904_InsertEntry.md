# InsertEntry

- ea: `0x180006904`
- end: `0x180007378`
- name: `InsertEntry`
- size: `2676`
- prototype: `__int64 __fastcall(struct _INDEX *, unsigned __int16 *, const unsigned __int16 *, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800065e0`

## callees

- `0x180001008`
- `0x180001520`
- `0x18000307c`
- `0x180003514`
- `0x180004d70`
- `0x180004dc4`
- `0x180004dec`
- `0x180004e2c`
- `0x180004ec4`
- `0x180004f44`
- `0x180005588`
- `0x180006714`
- `0x180006904`
- `0x180008544`
- `0x18000913c`
- `0x18000a4c4`
- `0x18000b7a0`
- `0x18000beac`
- `0x18000bf9c`
- `0x18000ede8`
- `0x18001066c`
- `0x1800107e4`
- `0x180010c40`
- `0x180010ca0`
- `0x1800135cc`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000722f`
- `KERNEL32!GetProcessHeap` at `0x18000722f`
- `KERNEL32!HeapFree` at `0x18000723d`
- `KERNEL32!HeapFree` at `0x18000723d`
- `KERNEL32!GetLastError` at `0x180006c4a`
- `KERNEL32!GetLastError` at `0x180006c4a`
- `KERNEL32!CreateFileW` at `0x180006c2f`
- `KERNEL32!CreateFileW` at `0x180006c2f`
- `KERNEL32!CloseHandle` at `0x180007203`
- `KERNEL32!CloseHandle` at `0x180007203`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006e8c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180006e8c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006eeb`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180006eeb`
- `RPCRT4!UuidFromStringW` at `0x180006f01`
- `RPCRT4!UuidFromStringW` at `0x180006f01`

## string_xrefs

- `0x180006b86`: `Packageinfo.xml`
- `0x180006c6f`: `Packageinfo.xml`
- `0x180006c39`: `Windows Metadata Information Service`
- `0x1800072ff`: `Windows Metadata Information Service`
- `0x180006ce0`: `Could not open packageinfo.xml for parsing`
- `0x180006df0`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x180006e35`: `http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/`
- `0x1800072d4`: `Could not parse packageinfo.xml`

## pseudocode

```c
__int64 __fastcall InsertEntry(
        struct _INDEX *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5)
{
  WCHAR *v6; // r13
  struct IStream *v7; // r14
  TXmlReader *v8; // r15
  __int64 (__fastcall *v9)(void ***); // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v19; // r8
  DWORD LastError; // ebx
  WCHAR *v21; // rdi
  HANDLE FileW; // rax
  unsigned __int16 *v23; // r14
  const unsigned __int16 *v24; // rax
  unsigned __int16 *v25; // r8
  int v26; // r10d
  int v27; // ecx
  int v28; // eax
  int v29; // eax
  int XmlDecleration; // eax
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  int StartElement; // eax
  int v34; // eax
  struct _INDEX *v35; // rbx
  __int64 v36; // r8
  int v37; // r8d
  int v38; // r9d
  _QWORD *v39; // rcx
  int DeviceInfo; // eax
  int SoftwareInfo; // eax
  const unsigned __int16 *v42; // rax
  unsigned int v43; // r8d
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v45; // rax
  int v46; // r8d
  int v47; // ecx
  unsigned __int16 *v48; // r14
  const unsigned __int16 *v49; // rax
  int v50; // r8d
  int v51; // ecx
  char v52[4]; // [rsp+A0h] [rbp-80h] BYREF
  int v53; // [rsp+A4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  struct IStream *v55; // [rsp+B0h] [rbp-70h] BYREF
  struct _INDEX *v56; // [rsp+B8h] [rbp-68h]
  WCHAR *v57; // [rsp+C0h] [rbp-60h]
  RPC_WSTR StringUuid; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v59; // [rsp+D0h] [rbp-50h] BYREF
  HANDLE hObject; // [rsp+D8h] [rbp-48h]
  __int64 v61; // [rsp+E0h] [rbp-40h] BYREF
  unsigned __int16 *v62; // [rsp+E8h] [rbp-38h]
  __int64 v63; // [rsp+F0h] [rbp-30h]
  __int64 v64; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v65; // [rsp+100h] [rbp-20h]
  __int64 v66; // [rsp+108h] [rbp-18h]
  int v67; // [rsp+110h] [rbp-10h]
  __int64 v68; // [rsp+118h] [rbp-8h] BYREF
  __int64 v69; // [rsp+120h] [rbp+0h]
  __int64 v70; // [rsp+128h] [rbp+8h]
  __int64 v71; // [rsp+130h] [rbp+10h]
  unsigned __int16 *v72; // [rsp+138h] [rbp+18h]
  unsigned __int16 *v73; // [rsp+140h] [rbp+20h]
  int v74; // [rsp+148h] [rbp+28h]
  __int64 v75; // [rsp+150h] [rbp+30h] BYREF
  __int64 v76; // [rsp+158h] [rbp+38h] BYREF
  __int64 v77; // [rsp+160h] [rbp+40h] BYREF
  __int64 v78; // [rsp+168h] [rbp+48h] BYREF
  __int64 v79; // [rsp+170h] [rbp+50h] BYREF
  __int64 v80; // [rsp+178h] [rbp+58h] BYREF
  __int64 v81; // [rsp+180h] [rbp+60h] BYREF
  __int64 v82; // [rsp+188h] [rbp+68h] BYREF
  UUID *p_Uuid; // [rsp+190h] [rbp+70h] BYREF
  UUID Uuid; // [rsp+198h] [rbp+78h] BYREF
  _QWORD v85[3]; // [rsp+1A8h] [rbp+88h] BYREF
  WCHAR v86[264]; // [rsp+1C0h] [rbp+A0h] BYREF

  v6 = a5;
  v56 = a1;
  v7 = 0;
  v8 = 0;
  StringUuid = a2;
  v9 = (__int64 (__fastcall *)(void ***))ATL::g_strmgr[3];
  v59 = (__int64)a5;
  v55 = 0;
  SRWLock = 0;
  Uuid = 0;
  v68 = v9(&ATL::g_strmgr) + 24;
  v69 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v70 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v71 = 0;
  v72 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v12 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v74 = 0;
  v73 = (unsigned __int16 *)(v12 + 24);
  v64 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v65 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v13 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v67 = 0;
  v66 = v13 + 24;
  v61 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v62 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v63 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v86[0] = 0;
  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14);
  if ( *(_DWORD *)a1 != 1229866053 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14);
  if ( a4 == 2 )
  {
    v53 = 1;
  }
  else
  {
    if ( a4 != 1 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v15, v14);
      MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16);
      _SOFTWARE_INFO::~_SOFTWARE_INFO((_SOFTWARE_INFO *)&v61);
      _SOFTWARE_INFO::~_SOFTWARE_INFO((_SOFTWARE_INFO *)&v64);
      _PACKAGE_INFO::~_PACKAGE_INFO((_PACKAGE_INFO *)&v68);
      return 87;
    }
    v53 = 0;
  }
  hObject = (HANDLE)-1LL;
  if ( !a5 )
  {
    if ( (unsigned int)TempExpandCabFile(a3, v86) )
    {
      v21 = 0;
      v48 = L"Windows Metadata Information Service";
      v6 = 0;
      LastError = 13;
      if ( a4 != 2 )
        v48 = L"Local Metadata Store";
      v49 = (const unsigned __int16 *)FSGetFileName(a3);
      IndexWerReportMetadataPackageError(v56, 0x50000011u, 0xDu, v49, a3, v48, v50);
      if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
        McTemplateU0zzdd_EventWriteTransfer(
          v51,
          (unsigned int)DMRC_PACKAGE_ERROR,
          (unsigned int)L"Could not unpack metadata package",
          (_DWORD)a3,
          17,
          13);
      goto LABEL_85;
    }
    v6 = v86;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v6);
  v57 = MemMallocAndCat(v6, L"\\", L"Packageinfo.xml", 0);
  if ( v57 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v57);
    if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_START_PARSE_PACKAGEINFO, v19, 1, v85);
    FileW = CreateFileW(v57, 1u, 1u, 0, 3u, 0x8000000u, 0);
    hObject = FileW;
    v23 = L"Windows Metadata Information Service";
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_SD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)&WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (unsigned int)L"Packageinfo.xml",
          LastError);
      v24 = (const unsigned __int16 *)FSGetFileName(a3);
      IndexWerReportMetadataPackageError(v56, 0x50000021u, LastError, v24, a3, v25, v26);
      if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
        McTemplateU0zzdd_EventWriteTransfer(
          v27,
          (unsigned int)DMRC_PACKAGE_ERROR,
          (unsigned int)L"Could not open packageinfo.xml for parsing",
          (_DWORD)a3,
          33,
          LastError);
      goto LABEL_79;
    }
    v28 = TFileStream::Create(FileW, &v55);
    if ( v28 )
    {
      LastError = (unsigned __int16)v28;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          44,
          &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (unsigned __int16)v28);
      goto LABEL_79;
    }
    v29 = TXmlReader::Create(v55, (struct TXmlReader **)&SRWLock);
    if ( v29 )
    {
      LastError = (unsigned __int16)v29;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          45,
          &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (unsigned __int16)v29);
      v8 = (TXmlReader *)SRWLock;
      goto LABEL_79;
    }
    v8 = (TXmlReader *)SRWLock;
    XmlDecleration = TXmlReader::ReadXmlDecleration((TXmlReader *)SRWLock);
    if ( XmlDecleration )
    {
      LastError = (unsigned __int16)XmlDecleration;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_79;
      v32 = 46;
      goto LABEL_42;
    }
    StartElement = TXmlReader::ReadStartElement(
                     v8,
                     L"PackageInfo",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( StartElement )
    {
      LastError = (unsigned __int16)StartElement;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_79;
      v32 = 47;
      goto LABEL_42;
    }
    v34 = TXmlReader::ReadStartElement(
            v8,
            L"MetadataKey",
            L"http://schemas.microsoft.com/windows/DeviceMetadata/PackageInfo/2007/11/");
    if ( v34 )
    {
      LastError = (unsigned __int16)v34;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_79;
      v32 = 48;
LABEL_42:
      WPP_SF_(v31[2], v32, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids);
      goto LABEL_79;
    }
    v35 = v56;
    SRWLock = (PSRWLOCK)((char *)v56 + 32);
    AcquireSRWLockExclusive((PSRWLOCK)v56 + 4);
    LastError = ReadMetadataKey(v35, StringUuid, a3, v59, v8, v53, &v68);
    if ( (Microsoft_Windows_UserPnpEnableBits & 4) != 0 )
      McGenEventWrite_EventWriteTransfer(userpnp_Context, DMRC_STOP_PARSE_PACKAGEINFO, v36, 1, v85);
    ReleaseSRWLockExclusive(SRWLock);
    if ( LastError )
      goto LABEL_80;
    LastError = UuidFromStringW(StringUuid, &Uuid);
    if ( LastError )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, LastError);
        v39 = WPP_GLOBAL_Control;
      }
      LastError = 0;
      Uuid = GUID_NULL;
    }
    else
    {
      v39 = WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)v72 - 4) )
    {
      DeviceInfo = ReadDeviceInfo(v6, v72, (struct _DEVICE_INFO *)&v64);
      if ( DeviceInfo >= 0 )
      {
LABEL_65:
        v39 = WPP_GLOBAL_Control;
        goto LABEL_66;
      }
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (unsigned int)DeviceInfo);
        goto LABEL_65;
      }
    }
LABEL_66:
    if ( *((_DWORD *)v73 - 4) )
    {
      SoftwareInfo = ReadSoftwareInfo(v6, v73, (struct _SOFTWARE_INFO *)&v61);
      if ( SoftwareInfo >= 0 )
      {
LABEL_71:
        v39 = WPP_GLOBAL_Control;
        goto LABEL_72;
      }
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
LABEL_75:
        if ( (unsigned int)dword_18001E2A0 > 5
          && (qword_18001E2B0 & 0x400000000000LL) != 0
          && (qword_18001E2B8 & 0x400000000000LL) == qword_18001E2B8 )
        {
          v59 = v63;
          StringUuid = v62;
          v75 = v61;
          v53 = v74;
          LODWORD(SRWLock) = v67;
          v76 = v66;
          v77 = v65;
          v78 = v64;
          v79 = v70;
          v80 = v69;
          v81 = v68;
          v82 = v71;
          p_Uuid = &Uuid;
          v52[0] = a4;
          v85[0] = 2048;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            qword_18001E2B8,
            (unsigned int)byte_18001AA51,
            v37,
            v38,
            (__int64)v85,
            (__int64)&p_Uuid,
            (__int64)v52,
            (__int64)&v82,
            (__int64)&v81,
            (__int64)&v80,
            (__int64)&v79,
            (__int64)&v78,
            (__int64)&v77,
            (__int64)&v76,
            (__int64)&SRWLock,
            (__int64)&v53,
            (__int64)&v75,
            (__int64)&StringUuid,
            (__int64)&v59);
        }
LABEL_79:
        if ( !LastError )
        {
LABEL_84:
          v21 = v57;
LABEL_85:
          v7 = v55;
          goto LABEL_86;
        }
LABEL_80:
        if ( LastError == 1296 )
        {
          if ( a4 != 2 )
            v23 = L"Local Metadata Store";
          v42 = (const unsigned __int16 *)FSGetFileName(a3);
          IndexWerReportMetadataPackageError(v56, 0x50000010u, v43, v42, a3, v23, 1);
        }
        else
        {
          if ( a4 != 2 )
            v23 = L"Local Metadata Store";
          v45 = (const unsigned __int16 *)FSGetFileName(a3);
          IndexWerReportMetadataPackageError(v56, 0x50000022u, LastError, v45, a3, v23, v46);
          if ( (Microsoft_Windows_UserPnpEnableBits & 0x20) != 0 )
            McTemplateU0zzdd_EventWriteTransfer(
              v47,
              (unsigned int)DMRC_PACKAGE_ERROR,
              (unsigned int)L"Could not parse packageinfo.xml",
              (_DWORD)a3,
              34,
              LastError);
        }
        goto LABEL_84;
      }
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
          (unsigned int)SoftwareInfo);
        goto LABEL_71;
      }
    }
LABEL_72:
    if ( v39 != &WPP_GLOBAL_Control && (*((_BYTE *)v39 + 28) & 8) != 0 )
      WPP_SF_S(v39[2], 52, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, StringUuid);
    goto LABEL_75;
  }
  LastError = 8;
  v21 = 0;
LABEL_86:
  if ( v8 )
  {
    TXmlReader::~TXmlReader(v8);
    operator delete(v8);
  }
  if ( v7 )
    ((void (__fastcall *)(struct IStream *))v7->lpVtbl->Release)(v7);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v6 == v86 )
  {
    FSRemoveDirPath(v86);
    v86[0] = 0;
  }
  if ( v21 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v21);
  }
  _SOFTWARE_INFO::~_SOFTWARE_INFO((_SOFTWARE_INFO *)&v61);
  _SOFTWARE_INFO::~_SOFTWARE_INFO((_SOFTWARE_INFO *)&v64);
  _PACKAGE_INFO::~_PACKAGE_INFO((_PACKAGE_INFO *)&v68);
  return LastError;
}

```

## disassembly

```asm
0x180006904  mov     [rsp-8+arg_18], rbx
0x180006909  push    rbp
0x18000690a  push    rsi
0x18000690b  push    rdi
0x18000690c  push    r12
0x18000690e  push    r13
0x180006910  push    r14
0x180006912  push    r15
0x180006914  lea     rbp, [rsp-2C0h]
0x18000691c  sub     rsp, 3E0h
0x180006923  mov     rax, cs:__security_cookie
0x18000692a  xor     rax, rsp
0x18000692d  mov     [rbp+2F0h+var_40], rax
0x180006934  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000693b  mov     rbx, rcx
0x18000693e  mov     r13, [rbp+2F0h+arg_20]
0x180006945  xorps   xmm0, xmm0
0x180006948  mov     [rbp+2F0h+var_358], rcx
0x18000694c  xor     r14d, r14d
0x18000694f  xor     r15d, r15d
0x180006952  mov     [rbp+2F0h+StringUuid], rdx
0x180006956  mov     rax, [rax+18h]
0x18000695a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006961  mov     r12d, r9d
0x180006964  mov     [rbp+2F0h+var_340], r13
0x180006968  mov     rsi, r8
0x18000696b  mov     [rbp+2F0h+var_360], r14
0x18000696f  mov     [rbp+2F0h+SRWLock], r15
0x180006973  movups  xmmword ptr [rbp+2F0h+Uuid.Data1], xmm0
0x180006977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697c  lea     edi, [r14+18h]
0x180006980  add     rax, rdi
0x180006983  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000698a  mov     [rbp+2F0h+var_2F8], rax
0x18000698e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006995  mov     rax, [rax+18h]
0x180006999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699e  add     rax, rdi
0x1800069a1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800069a8  mov     [rbp+2F0h+var_2F0], rax
0x1800069ac  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800069b3  mov     rax, [rax+18h]
0x1800069b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069bc  add     rax, rdi
0x1800069bf  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800069c6  mov     [rbp+2F0h+var_2E8], rax
0x1800069ca  xor     eax, eax
0x1800069cc  mov     [rbp+2F0h+var_2E0], rax
0x1800069d0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800069d7  mov     rax, [rax+18h]
0x1800069db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e0  add     rax, rdi
0x1800069e3  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800069ea  mov     [rbp+2F0h+var_2D8], rax
0x1800069ee  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800069f5  mov     rax, [rax+18h]
0x1800069f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069fe  add     rax, rdi
0x180006a01  mov     [rbp+2F0h+var_2C8], r14d
0x180006a05  mov     [rbp+2F0h+var_2D0], rax
0x180006a09  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a10  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a17  mov     rax, [rax+18h]
0x180006a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a20  add     rax, rdi
0x180006a23  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a2a  mov     [rbp+2F0h+var_318], rax
0x180006a2e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a35  mov     rax, [rax+18h]
0x180006a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a3e  add     rax, rdi
0x180006a41  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a48  mov     [rbp+2F0h+var_310], rax
0x180006a4c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a53  mov     rax, [rax+18h]
0x180006a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a5c  add     rax, rdi
0x180006a5f  mov     [rbp+2F0h+var_300], r14d
0x180006a63  mov     [rbp+2F0h+var_308], rax
0x180006a67  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a6e  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a75  mov     rax, [rax+18h]
0x180006a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7e  add     rax, rdi
0x180006a81  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a88  mov     [rbp+2F0h+var_330], rax
0x180006a8c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006a93  mov     rax, [rax+18h]
0x180006a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9c  add     rax, rdi
0x180006a9f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006aa6  mov     [rbp+2F0h+var_328], rax
0x180006aaa  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180006ab1  mov     rax, [rax+18h]
0x180006ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aba  add     rax, rdi
0x180006abd  mov     [rbp+2F0h+var_320], rax
0x180006ac1  xor     eax, eax
0x180006ac3  mov     [rbp+2F0h+var_250], ax
0x180006aca  test    rbx, rbx
0x180006acd  jnz     short loc_180006AD4
0x180006acf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006ad4  cmp     dword ptr [rbx], 494E4445h
0x180006ada  jz      short loc_180006AE1
0x180006adc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006ae1  mov     edi, 1
0x180006ae6  cmp     r12d, 2
0x180006aea  jz      short loc_180006B24
0x180006aec  cmp     r12d, edi
0x180006aef  jz      short loc_180006B1E
0x180006af1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006af6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180006afb  lea     rcx, [rbp+2F0h+var_330]; this
0x180006aff  call    ??1_SOFTWARE_INFO@@QEAA@XZ; _SOFTWARE_INFO::~_SOFTWARE_INFO(void)
0x180006b04  lea     rcx, [rbp+2F0h+var_318]; this
0x180006b08  call    ??1_SOFTWARE_INFO@@QEAA@XZ; _SOFTWARE_INFO::~_SOFTWARE_INFO(void)
0x180006b0d  lea     rcx, [rbp+2F0h+var_2F8]; this
0x180006b11  call    ??1_PACKAGE_INFO@@QEAA@XZ; _PACKAGE_INFO::~_PACKAGE_INFO(void)
0x180006b16  lea     eax, [rdi+56h]
0x180006b19  jmp     loc_180007260
0x180006b1e  mov     [rbp+2F0h+var_36C], r14d
0x180006b22  jmp     short loc_180006B27
0x180006b24  mov     [rbp+2F0h+var_36C], edi
0x180006b27  mov     [rbp+2F0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180006b2f  test    r13, r13
0x180006b32  jnz     short loc_180006B52
0x180006b34  lea     rdx, [rbp+2F0h+var_250]; LPCWSTR
0x180006b3b  mov     rcx, rsi; lpFileName
0x180006b3e  call    TempExpandCabFile
0x180006b43  test    eax, eax
0x180006b45  jnz     loc_1800072F3
0x180006b4b  lea     r13, [rbp+2F0h+var_250]
0x180006b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b59  lea     rax, WPP_GLOBAL_Control
0x180006b60  cmp     rcx, rax
0x180006b63  jz      short loc_180006B83
0x180006b65  test    byte ptr [rcx+1Ch], 8
0x180006b69  jz      short loc_180006B83
0x180006b6b  mov     rcx, [rcx+10h]
0x180006b6f  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180006b76  mov     edx, 29h ; ')'
0x180006b7b  mov     r9, r13
0x180006b7e  call    WPP_SF_S
0x180006b83  xor     r9d, r9d
0x180006b86  lea     r8, aPackageinfoXml; "Packageinfo.xml"
0x180006b8d  lea     rdx, asc_180016E08; "\\"
0x180006b94  mov     rcx, r13; unsigned __int16 *
0x180006b97  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x180006b9c  mov     [rbp+2F0h+var_350], rax
0x180006ba0  mov     rbx, rax
0x180006ba3  test    rax, rax
0x180006ba6  jnz     short loc_180006BB3
0x180006ba8  lea     ebx, [rax+8]
0x180006bab  mov     rdi, rax
0x180006bae  jmp     loc_1800071CD
0x180006bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bba  lea     rax, WPP_GLOBAL_Control
0x180006bc1  cmp     rcx, rax
0x180006bc4  jz      short loc_180006BE4
0x180006bc6  test    byte ptr [rcx+1Ch], 8
0x180006bca  jz      short loc_180006BE4
0x180006bcc  mov     rcx, [rcx+10h]
0x180006bd0  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180006bd7  mov     edx, 2Ah ; '*'
0x180006bdc  mov     r9, rbx
0x180006bdf  call    WPP_SF_S
0x180006be4  test    cs:Microsoft_Windows_UserPnpEnableBits, 4
0x180006beb  jz      short loc_180006C0F
0x180006bed  lea     rax, [rbp+2F0h+var_268]
0x180006bf4  mov     r9d, edi
0x180006bf7  lea     rdx, DMRC_START_PARSE_PACKAGEINFO
0x180006bfe  mov     qword ptr [rsp+410h+dwCreationDisposition], rax
0x180006c03  lea     rcx, userpnp_Context
0x180006c0a  call    McGenEventWrite_EventWriteTransfer
0x180006c0f  mov     [rsp+410h+hTemplateFile], r14; hTemplateFile
0x180006c14  xor     r9d, r9d; lpSecurityAttributes
0x180006c17  mov     [rsp+410h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180006c1f  mov     r8d, edi; dwShareMode
0x180006c22  mov     edx, edi; dwDesiredAccess
0x180006c24  mov     [rsp+410h+dwCreationDisposition], 3; dwCreationDisposition
0x180006c2c  mov     rcx, rbx; lpFileName
0x180006c2f  call    cs:__imp_CreateFileW
0x180006c35  mov     [rbp+2F0h+hObject], rax
0x180006c39  lea     r14, aWindowsMetadat; "Windows Metadata Information Service"
0x180006c40  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006c44  jnz     loc_180006D03
0x180006c4a  call    cs:__imp_GetLastError
0x180006c50  mov     ebx, eax
0x180006c52  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c59  lea     rax, WPP_GLOBAL_Control
0x180006c60  cmp     rcx, rax
0x180006c63  jz      short loc_180006C8B
0x180006c65  test    [rcx+1Ch], dil
0x180006c69  jz      short loc_180006C8B
0x180006c6b  mov     rcx, [rcx+10h]
0x180006c6f  lea     r9, aPackageinfoXml; "Packageinfo.xml"
0x180006c76  mov     edx, 2Bh ; '+'
0x180006c7b  mov     [rsp+410h+dwCreationDisposition], ebx
0x180006c7f  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180006c86  call    WPP_SF_SD
0x180006c8b  xor     r10d, r10d
0x180006c8e  lea     rax, aLocalMetadataS; "Local Metadata Store"
0x180006c95  cmp     r12d, 2
0x180006c99  mov     r8, r14
0x180006c9c  mov     rcx, rsi
0x180006c9f  setz    r10b
0x180006ca3  cmovnz  r8, rax
0x180006ca7  call    FSGetFileName
0x180006cac  mov     rcx, [rbp+2F0h+var_358]; struct _INDEX *
0x180006cb0  mov     r9, rax; unsigned __int16 *
0x180006cb3  mov     dword ptr [rsp+410h+hTemplateFile], r10d; int
0x180006cb8  mov     edx, 50000021h; unsigned int
0x180006cbd  mov     qword ptr [rsp+410h+dwFlagsAndAttributes], r8; unsigned __int16 *
0x180006cc2  mov     r8d, ebx; unsigned int
0x180006cc5  mov     qword ptr [rsp+410h+dwCreationDisposition], rsi; unsigned __int16 *
0x180006cca  call    ?IndexWerReportMetadataPackageError@@YAXPEAU_INDEX@@KKPEBG1PEAGH@Z; IndexWerReportMetadataPackageError(_INDEX *,ulong,ulong,ushort const *,ushort const *,ushort *,int)
0x180006ccf  test    cs:Microsoft_Windows_UserPnpEnableBits, 20h
0x180006cd6  jz      loc_18000717C
0x180006cdc  mov     [rsp+410h+dwFlagsAndAttributes], ebx
0x180006ce0  lea     r8, aCouldNotOpenPa; "Could not open packageinfo.xml for pars"...
0x180006ce7  mov     r9, rsi
0x180006cea  mov     [rsp+410h+dwCreationDisposition], 50000021h
0x180006cf2  lea     rdx, DMRC_PACKAGE_ERROR
0x180006cf9  call    McTemplateU0zzdd_EventWriteTransfer
0x180006cfe  jmp     loc_18000717C
0x180006d03  lea     rdx, [rbp+2F0h+var_360]; struct IStream **
0x180006d07  mov     rcx, rax; hSourceHandle
0x180006d0a  call    ?Create@TFileStream@@SAJPEAXPEAPEAUIStream@@@Z; TFileStream::Create(void *,IStream * *)
0x180006d0f  test    eax, eax
0x180006d11  jz      short loc_180006D54
0x180006d13  movzx   ebx, ax
0x180006d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d1d  lea     rax, WPP_GLOBAL_Control
0x180006d24  cmp     rcx, rax
0x180006d27  jz      loc_18000717C
0x180006d2d  test    [rcx+1Ch], dil
0x180006d31  jz      loc_18000717C
0x180006d37  mov     rcx, [rcx+10h]
0x180006d3b  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180006d42  mov     edx, 2Ch ; ','
0x180006d47  mov     r9d, ebx
0x180006d4a  call    WPP_SF_d
0x180006d4f  jmp     loc_18000717C
0x180006d54  mov     rcx, [rbp+2F0h+var_360]; struct IStream *
0x180006d58  lea     rdx, [rbp+2F0h+SRWLock]; struct TXmlReader **
0x180006d5c  call    ?Create@TXmlReader@@SAJPEAUIStream@@PEAPEAV1@@Z; TXmlReader::Create(IStream *,TXmlReader * *)
0x180006d61  test    eax, eax
0x180006d63  jz      short loc_180006DA2
0x180006d65  movzx   ebx, ax
0x180006d68  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d6f  lea     rax, WPP_GLOBAL_Control
0x180006d76  cmp     rcx, rax
0x180006d79  jz      short loc_180006D99
0x180006d7b  test    [rcx+1Ch], dil
0x180006d7f  jz      short loc_180006D99
0x180006d81  mov     rcx, [rcx+10h]
0x180006d85  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180006d8c  mov     edx, 2Dh ; '-'
0x180006d91  mov     r9d, ebx
0x180006d94  call    WPP_SF_d
0x180006d99  mov     r15, [rbp+2F0h+SRWLock]
0x180006d9d  jmp     loc_18000717C
0x180006da2  mov     r15, [rbp+2F0h+SRWLock]
0x180006da6  mov     rcx, r15; this
0x180006da9  call    ?ReadXmlDecleration@TXmlReader@@QEAAJXZ; TXmlReader::ReadXmlDecleration(void)
0x180006dae  test    eax, eax
0x180006db0  jz      short loc_180006DF0
0x180006db2  movzx   ebx, ax
0x180006db5  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dbc  lea     rax, WPP_GLOBAL_Control
0x180006dc3  cmp     rcx, rax
0x180006dc6  jz      loc_18000717C
0x180006dcc  test    [rcx+1Ch], dil
0x180006dd0  jz      loc_18000717C
0x180006dd6  mov     edx, 2Eh ; '.'
0x180006ddb  mov     rcx, [rcx+10h]
0x180006ddf  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180006de6  call    WPP_SF_
0x180006deb  jmp     loc_18000717C
0x180006df0  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180006df7  mov     rcx, r15; this
0x180006dfa  lea     rdx, aPackageinfo; "PackageInfo"
0x180006e01  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x180006e06  test    eax, eax
0x180006e08  jz      short loc_180006E35
0x180006e0a  movzx   ebx, ax
0x180006e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e14  lea     rax, WPP_GLOBAL_Control
0x180006e1b  cmp     rcx, rax
0x180006e1e  jz      loc_18000717C
0x180006e24  test    [rcx+1Ch], dil
0x180006e28  jz      loc_18000717C
0x180006e2e  mov     edx, 2Fh ; '/'
0x180006e33  jmp     short loc_180006DDB
0x180006e35  lea     r8, aHttpSchemasMic_0; "http://schemas.microsoft.com/windows/De"...
0x180006e3c  mov     rcx, r15; this
0x180006e3f  lea     rdx, aMetadatakey; "MetadataKey"
0x180006e46  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x180006e4b  test    eax, eax
0x180006e4d  jz      short loc_180006E7D
  ... truncated ...
```
