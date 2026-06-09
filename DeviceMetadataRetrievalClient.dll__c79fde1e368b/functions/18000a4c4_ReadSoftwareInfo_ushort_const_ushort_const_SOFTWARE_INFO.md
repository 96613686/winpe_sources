# ReadSoftwareInfo(ushort const *,ushort const *,_SOFTWARE_INFO *)

- ea: `0x18000a4c4`
- end: `0x18000af76`
- name: `?ReadSoftwareInfo@@YAJPEBG0PEAU_SOFTWARE_INFO@@@Z`
- size: `2738`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _SOFTWARE_INFO *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180006904`

## callees

- `0x180001520`
- `0x180002f2c`
- `0x180004e2c`
- `0x180005018`
- `0x1800050b4`
- `0x180005588`
- `0x18000a200`
- `0x18000a4c4`
- `0x18000bf9c`
- `0x18000c014`
- `0x18000c0c0`
- `0x18000c17c`
- `0x18001066c`
- `0x1800107e4`
- `0x1800108d8`
- `0x180010bc8`
- `0x180010c40`
- `0x180010ca0`
- `0x180010d18`
- `0x180010e08`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a8a8`
- `KERNEL32!GetProcessHeap` at `0x18000a8c4`
- `KERNEL32!GetProcessHeap` at `0x18000ac18`
- `KERNEL32!GetProcessHeap` at `0x18000ac34`
- `KERNEL32!GetProcessHeap` at `0x18000aeb4`
- `KERNEL32!GetProcessHeap` at `0x18000aecd`
- `KERNEL32!GetProcessHeap` at `0x18000a8a8`
- `KERNEL32!GetProcessHeap` at `0x18000a8c4`
- `KERNEL32!GetProcessHeap` at `0x18000ac18`
- `KERNEL32!GetProcessHeap` at `0x18000ac34`
- `KERNEL32!GetProcessHeap` at `0x18000aeb4`
- `KERNEL32!GetProcessHeap` at `0x18000aecd`
- `KERNEL32!HeapFree` at `0x18000a8b6`
- `KERNEL32!HeapFree` at `0x18000a8d2`
- `KERNEL32!HeapFree` at `0x18000ac26`
- `KERNEL32!HeapFree` at `0x18000ac42`
- `KERNEL32!HeapFree` at `0x18000aec2`
- `KERNEL32!HeapFree` at `0x18000aedb`
- `KERNEL32!HeapFree` at `0x18000a8b6`
- `KERNEL32!HeapFree` at `0x18000a8d2`
- `KERNEL32!HeapFree` at `0x18000ac26`
- `KERNEL32!HeapFree` at `0x18000ac42`
- `KERNEL32!HeapFree` at `0x18000aec2`
- `KERNEL32!HeapFree` at `0x18000aedb`
- `KERNEL32!GetLastError` at `0x18000a61c`
- `KERNEL32!GetLastError` at `0x18000a61c`
- `KERNEL32!CreateFileW` at `0x18000a608`
- `KERNEL32!CreateFileW` at `0x18000a608`
- `KERNEL32!CloseHandle` at `0x18000aea9`
- `KERNEL32!CloseHandle` at `0x18000aea9`

## string_xrefs

- `0x18000a583`: `SoftwareInfo.xml`
- `0x18000a645`: `SoftwareInfo.xml`
- `0x18000a6aa`: `SoftwareInfo.xml`
- `0x18000a702`: `SoftwareInfo.xml`
- `0x18000a751`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a79f`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a8db`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a8fa`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a91a`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a93a`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a95a`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a97b`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000aa7a`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000aac1`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000ac4b`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000ac70`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000ac8c`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000acad`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000ad88`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000adcf`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000ae0e`: `http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo`
- `0x18000a7a9`: `DeviceCompanionApplications`
- `0x18000a7ee`: `DeviceCompanionApplications`
- `0x18000a985`: `DeviceCompanionApplications`
- `0x18000aa84`: `DeviceCompanionApplications`
- `0x18000aacb`: `PrivilegedApplications`
- `0x18000ab10`: `PrivilegedApplications`
- `0x18000acb7`: `PrivilegedApplications`
- `0x18000ad92`: `PrivilegedApplications`

## pseudocode

```c
__int64 __fastcall ReadSoftwareInfo(const unsigned __int16 *a1, const unsigned __int16 *a2, struct _SOFTWARE_INFO *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  void *v8; // r12
  unsigned __int16 *v9; // r15
  __int64 v10; // rbx
  signed int LastError; // esi
  HANDLE FileW; // rax
  void *v13; // r14
  int v14; // r8d
  int v15; // eax
  int v16; // r8d
  TXmlReader *v17; // r14
  _QWORD *v18; // rcx
  int v19; // edx
  const wchar_t *v20; // r9
  signed int StartElement; // eax
  void *v22; // rsi
  unsigned __int16 *v23; // r15
  HANDLE ProcessHeap; // rax
  HANDLE v25; // rax
  signed int v26; // eax
  int v27; // edx
  int v28; // r8d
  void *v29; // rsi
  unsigned __int16 *v30; // r15
  int v31; // r12d
  HANDLE v32; // rax
  HANDLE v33; // rax
  HANDLE v34; // rax
  HANDLE v35; // rax
  _QWORD *v36; // rdx
  LPVOID lpMem; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+60h] [rbp-A0h] BYREF
  int v43; // [rsp+68h] [rbp-98h] BYREF
  HANDLE v44; // [rsp+70h] [rbp-90h]
  struct IStream *v45; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+80h] [rbp-80h] BYREF
  WCHAR FileName[264]; // [rsp+90h] [rbp-70h] BYREF

  v45 = 0;
  Block = 0;
  v40 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v41 = v6;
  v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  v8 = 0;
  v9 = 0;
  lpMem = 0;
  v39 = 0;
  v10 = v7 + 24;
  v43 = 0;
  v42 = v7 + 24;
  LastError = StringCchPrintfW(FileName, 0x104u, L"%ws\\%ws\\%ws", a1, a2, L"SoftwareInfo.xml");
  if ( LastError < 0 )
    goto LABEL_126;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 123, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, FileName);
  FileW = CreateFileW(FileName, 1u, 1u, 0, 3u, 0x8000000u, 0);
  v44 = FileW;
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        124,
        (unsigned int)&WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
        (unsigned int)L"SoftwareInfo.xml",
        LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_126;
  }
  LastError = TFileStream::Create(FileW, &v45);
  if ( LastError >= 0 )
  {
    v15 = TXmlReader::Create(v45, (struct TXmlReader **)&Block);
    v17 = (TXmlReader *)Block;
    LastError = v15;
    if ( v15 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_117;
      v19 = 126;
LABEL_19:
      v20 = L"SoftwareInfo.xml";
      goto LABEL_20;
    }
    LastError = TXmlReader::ReadXmlDecleration((TXmlReader *)Block);
    if ( LastError )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_117;
      v19 = 127;
      goto LABEL_19;
    }
    LastError = TXmlReader::ReadStartElement(
                  v17,
                  L"SoftwareInfo",
                  L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
    if ( LastError )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_117;
      v19 = 128;
      goto LABEL_29;
    }
    StartElement = TXmlReader::ReadStartElement(
                     v17,
                     L"DeviceCompanionApplications",
                     L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
    LastError = StartElement;
    if ( StartElement != 1 )
    {
      if ( StartElement )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_117;
        v19 = 129;
LABEL_35:
        v20 = L"DeviceCompanionApplications";
        goto LABEL_20;
      }
      while ( 1 )
      {
        LastError = TXmlReader::ReadStartElement(
                      v17,
                      L"Package",
                      L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
        if ( LastError == 1 )
          break;
        if ( LastError )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_117;
          v19 = 130;
LABEL_58:
          v20 = L"Package";
          goto LABEL_20;
        }
        LastError = ReadPackageIdentity(v17, (unsigned __int16 **)&lpMem, &v39, 0);
        if ( LastError )
        {
LABEL_100:
          v8 = lpMem;
          v9 = v39;
          goto LABEL_117;
        }
        v22 = lpMem;
        v23 = v39;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            131,
            (unsigned int)&WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
            (_DWORD)lpMem,
            (__int64)v39);
        if ( *(_DWORD *)(v40 - 16) )
          ATL::CSimpleStringT<unsigned short,0>::Append(&v40, L";");
        ATL::CSimpleStringT<unsigned short,0>::Append(&v40, v22);
        ATL::CSimpleStringT<unsigned short,0>::Append(&v40, L" ");
        ATL::CSimpleStringT<unsigned short,0>::Append(&v40, v23);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v22);
        v8 = 0;
        lpMem = 0;
        v25 = GetProcessHeap();
        HeapFree(v25, 0, v23);
        v9 = 0;
        v39 = 0;
        if ( !(unsigned int)TXmlReader::IsNodeQName(
                              v17,
                              L"Applications",
                              L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo") )
        {
          LastError = TXmlReader::SkipElement(
                        v17,
                        L"Applications",
                        L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
          if ( LastError )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 132;
              v20 = L"Applications";
              goto LABEL_20;
            }
            goto LABEL_117;
          }
        }
        LastError = TXmlReader::SkipAnyOtherNodesInElement(
                      v17,
                      L"Package",
                      L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
        if ( LastError )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_117;
          v19 = 133;
          goto LABEL_58;
        }
        LastError = TXmlReader::ReadEndElement(
                      v17,
                      L"Package",
                      L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
        if ( LastError )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_117;
          v19 = 134;
          goto LABEL_58;
        }
      }
      LastError = TXmlReader::SkipAnyOtherNodesInElement(
                    v17,
                    L"DeviceCompanionApplications",
                    L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
      if ( LastError )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 135;
          goto LABEL_35;
        }
        goto LABEL_117;
      }
      LastError = TXmlReader::ReadEndElement(
                    v17,
                    L"DeviceCompanionApplications",
                    L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
      if ( LastError )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_117;
        v19 = 136;
        goto LABEL_35;
      }
    }
    v26 = TXmlReader::ReadStartElement(
            v17,
            L"PrivilegedApplications",
            L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
    LastError = v26;
    if ( v26 != 1 )
    {
      if ( !v26 )
      {
        while ( 1 )
        {
          LastError = TXmlReader::ReadStartElement(
                        v17,
                        L"Package",
                        L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
          if ( LastError == 1 )
            break;
          if ( LastError )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 138;
              goto LABEL_58;
            }
            goto LABEL_117;
          }
          LastError = ReadPackageIdentity(v17, (unsigned __int16 **)&lpMem, &v39, &v43);
          if ( LastError )
            goto LABEL_100;
          v29 = lpMem;
          v30 = v39;
          v31 = v43;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, v28, (_DWORD)lpMem, (__int64)v39, v43);
          if ( v31 )
          {
            if ( *(_DWORD *)(v10 - 16) )
              ATL::CSimpleStringT<unsigned short,0>::Append(&v42, L";");
            ATL::CSimpleStringT<unsigned short,0>::Append(&v42, v29);
            ATL::CSimpleStringT<unsigned short,0>::Append(&v42, L" ");
            ATL::CSimpleStringT<unsigned short,0>::Append(&v42, v30);
            v10 = v42;
          }
          else
          {
            if ( *(_DWORD *)(v6 - 16) )
              ATL::CSimpleStringT<unsigned short,0>::Append(&v41, L";");
            ATL::CSimpleStringT<unsigned short,0>::Append(&v41, v29);
            ATL::CSimpleStringT<unsigned short,0>::Append(&v41, L" ");
            ATL::CSimpleStringT<unsigned short,0>::Append(&v41, v30);
            v6 = v41;
          }
          v32 = GetProcessHeap();
          HeapFree(v32, 0, v29);
          v8 = 0;
          lpMem = 0;
          v33 = GetProcessHeap();
          HeapFree(v33, 0, v30);
          v9 = 0;
          v39 = 0;
          LastError = TXmlReader::SkipAnyOtherNodesInElement(
                        v17,
                        L"Package",
                        L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
          if ( LastError )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 140;
              goto LABEL_58;
            }
            goto LABEL_117;
          }
          LastError = TXmlReader::ReadEndElement(
                        v17,
                        L"Package",
                        L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
          if ( LastError )
          {
            v18 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v19 = 141;
              goto LABEL_58;
            }
            goto LABEL_117;
          }
        }
        LastError = TXmlReader::SkipAnyOtherNodesInElement(
                      v17,
                      L"PrivilegedApplications",
                      L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
        if ( LastError )
        {
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 142;
            goto LABEL_74;
          }
        }
        else
        {
          LastError = TXmlReader::ReadEndElement(
                        v17,
                        L"PrivilegedApplications",
                        L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
          if ( !LastError )
            goto LABEL_108;
          v18 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 143;
            goto LABEL_74;
          }
        }
        goto LABEL_117;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_117;
      v19 = 137;
LABEL_74:
      v20 = L"PrivilegedApplications";
LABEL_20:
      WPP_SF_Sd(v18[2], v19, v16, (_DWORD)v20, LastError);
      goto LABEL_117;
    }
LABEL_108:
    LastError = TXmlReader::SkipAnyOtherNodesInElement(
                  v17,
                  L"SoftwareInfo",
                  L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
    if ( LastError )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_117;
      v19 = 144;
    }
    else
    {
      LastError = TXmlReader::ReadEndElement(
                    v17,
                    L"SoftwareInfo",
                    L"http://schemas.microsoft.com/windows/2010/08/DeviceMetadata/SoftwareInfo");
      if ( !LastError )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          a3,
          &v40);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (char *)a3 + 8,
          &v41);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (char *)a3 + 16,
          &v42);
        goto LABEL_117;
      }
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_117:
        if ( v17 )
        {
          TXmlReader::~TXmlReader(v17);
          operator delete(v17);
        }
        v13 = v44;
        goto LABEL_120;
      }
      v19 = 145;
    }
LABEL_29:
    v20 = L"SoftwareInfo";
    goto LABEL_20;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, v14, (unsigned int)L"SoftwareInfo.xml", LastError);
LABEL_120:
  if ( v45 )
    ((void (__fastcall *)(struct IStream *))v45->lpVtbl->Release)(v45);
  CloseHandle(v13);
  if ( v8 )
  {
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v8);
  }
  if ( v9 )
  {
    v35 = GetProcessHeap();
    HeapFree(v35, 0, v9);
  }
LABEL_126:
  if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v10 - 24) + 8LL))(*(_QWORD *)(v10 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)(v6 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 - 24) + 8LL))(*(_QWORD *)(v6 - 24));
  v36 = (_QWORD *)(v40 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v40 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v36 + 8LL))(*v36);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000a4c4  mov     [rsp-8+arg_18], rbx
0x18000a4c9  push    rbp
0x18000a4ca  push    rsi
0x18000a4cb  push    rdi
0x18000a4cc  push    r12
0x18000a4ce  push    r13
0x18000a4d0  push    r14
0x18000a4d2  push    r15
0x18000a4d4  lea     rbp, [rsp-1B0h]
0x18000a4dc  sub     rsp, 2B0h
0x18000a4e3  mov     rax, cs:__security_cookie
0x18000a4ea  xor     rax, rsp
0x18000a4ed  mov     [rbp+1E0h+var_40], rax
0x18000a4f4  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a4fb  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a502  mov     rsi, rcx
0x18000a505  mov     [rsp+2E0h+var_268], 0
0x18000a50e  mov     rcx, rbx
0x18000a511  mov     [rbp+1E0h+Block], 0
0x18000a519  mov     r13, r8
0x18000a51c  mov     r14, rdx
0x18000a51f  mov     rax, [rax+18h]
0x18000a523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a528  add     rax, 18h
0x18000a52c  mov     rcx, rbx
0x18000a52f  mov     [rsp+2E0h+var_290], rax
0x18000a534  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a53b  mov     rax, [rax+18h]
0x18000a53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a544  mov     rcx, rbx
0x18000a547  lea     rdi, [rax+18h]
0x18000a54b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000a552  mov     [rsp+2E0h+var_288], rdi
0x18000a557  mov     rax, [rax+18h]
0x18000a55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a560  xor     r12d, r12d
0x18000a563  lea     r8, aWsWsWs; "%ws\\%ws\\%ws"
0x18000a56a  xor     r15d, r15d
0x18000a56d  mov     [rsp+2E0h+lpMem], r12
0x18000a572  mov     r9, rsi
0x18000a575  mov     [rsp+2E0h+var_298], r15
0x18000a57a  lea     rbx, [rax+18h]
0x18000a57e  mov     [rsp+2E0h+var_278], r12d
0x18000a583  lea     rax, aSoftwareinfoXm; "SoftwareInfo.xml"
0x18000a58a  mov     [rsp+2E0h+var_280], rbx
0x18000a58f  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax
0x18000a594  lea     rcx, [rbp+1E0h+FileName]; unsigned __int16 *
0x18000a598  mov     edx, 104h; unsigned __int64
0x18000a59d  mov     qword ptr [rsp+2E0h+dwCreationDisposition], r14
0x18000a5a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a5a7  mov     esi, eax
0x18000a5a9  test    eax, eax
0x18000a5ab  js      loc_18000AEE1
0x18000a5b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5b8  lea     rax, WPP_GLOBAL_Control
0x18000a5bf  cmp     rcx, rax
0x18000a5c2  jz      short loc_18000A5E3
0x18000a5c4  test    byte ptr [rcx+1Ch], 8
0x18000a5c8  jz      short loc_18000A5E3
0x18000a5ca  mov     rcx, [rcx+10h]
0x18000a5ce  lea     edx, [r12+7Bh]
0x18000a5d3  lea     r9, [rbp+1E0h+FileName]
0x18000a5d7  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000a5de  call    WPP_SF_S
0x18000a5e3  xor     r9d, r9d; lpSecurityAttributes
0x18000a5e6  mov     [rsp+2E0h+hTemplateFile], r12; hTemplateFile
0x18000a5eb  mov     [rsp+2E0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000a5f3  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x18000a5f7  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a5ff  lea     eax, [r9+1]
0x18000a603  mov     r8d, eax; dwShareMode
0x18000a606  mov     edx, eax; dwDesiredAccess
0x18000a608  call    cs:__imp_CreateFileW
0x18000a60e  mov     [rsp+2E0h+var_270], rax
0x18000a613  mov     r14, rax
0x18000a616  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a61a  jnz     short loc_18000A672
0x18000a61c  call    cs:__imp_GetLastError
0x18000a622  mov     esi, eax
0x18000a624  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a62b  lea     rax, WPP_GLOBAL_Control
0x18000a632  cmp     rcx, rax
0x18000a635  jz      short loc_18000A65C
0x18000a637  test    byte ptr [rcx+1Ch], 1
0x18000a63b  jz      short loc_18000A65C
0x18000a63d  mov     rcx, [rcx+10h]
0x18000a641  lea     edx, [r14+7Dh]
0x18000a645  lea     r9, aSoftwareinfoXm; "SoftwareInfo.xml"
0x18000a64c  mov     [rsp+2E0h+dwCreationDisposition], esi
0x18000a650  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000a657  call    WPP_SF_SD
0x18000a65c  test    esi, esi
0x18000a65e  jle     loc_18000AEE1
0x18000a664  movzx   esi, si
0x18000a667  or      esi, 80070000h
0x18000a66d  jmp     loc_18000AEE1
0x18000a672  lea     rdx, [rsp+2E0h+var_268]; struct IStream **
0x18000a677  mov     rcx, rax; hSourceHandle
0x18000a67a  call    ?Create@TFileStream@@SAJPEAXPEAPEAUIStream@@@Z; TFileStream::Create(void *,IStream * *)
0x18000a67f  mov     esi, eax
0x18000a681  test    eax, eax
0x18000a683  jns     short loc_18000A6C4
0x18000a685  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a68c  lea     rax, WPP_GLOBAL_Control
0x18000a693  cmp     rcx, rax
0x18000a696  jz      loc_18000AE90
0x18000a69c  test    byte ptr [rcx+1Ch], 1
0x18000a6a0  jz      loc_18000AE90
0x18000a6a6  mov     rcx, [rcx+10h]
0x18000a6aa  lea     r9, aSoftwareinfoXm; "SoftwareInfo.xml"
0x18000a6b1  mov     edx, 7Dh ; '}'
0x18000a6b6  mov     [rsp+2E0h+dwCreationDisposition], esi
0x18000a6ba  call    WPP_SF_Sd
0x18000a6bf  jmp     loc_18000AE90
0x18000a6c4  mov     rcx, [rsp+2E0h+var_268]; struct IStream *
0x18000a6c9  lea     rdx, [rbp+1E0h+Block]; struct TXmlReader **
0x18000a6cd  call    ?Create@TXmlReader@@SAJPEAUIStream@@PEAPEAV1@@Z; TXmlReader::Create(IStream *,TXmlReader * *)
0x18000a6d2  mov     r14, [rbp+1E0h+Block]
0x18000a6d6  mov     esi, eax
0x18000a6d8  test    eax, eax
0x18000a6da  jns     short loc_18000A71B
0x18000a6dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6e3  lea     rax, WPP_GLOBAL_Control
0x18000a6ea  cmp     rcx, rax
0x18000a6ed  jz      loc_18000AE76
0x18000a6f3  test    byte ptr [rcx+1Ch], 1
0x18000a6f7  jz      loc_18000AE76
0x18000a6fd  mov     edx, 7Eh ; '~'
0x18000a702  lea     r9, aSoftwareinfoXm; "SoftwareInfo.xml"
0x18000a709  mov     rcx, [rcx+10h]
0x18000a70d  mov     [rsp+2E0h+dwCreationDisposition], esi
0x18000a711  call    WPP_SF_Sd
0x18000a716  jmp     loc_18000AE76
0x18000a71b  mov     rcx, r14; this
0x18000a71e  call    ?ReadXmlDecleration@TXmlReader@@QEAAJXZ; TXmlReader::ReadXmlDecleration(void)
0x18000a723  mov     esi, eax
0x18000a725  test    eax, eax
0x18000a727  jz      short loc_18000A751
0x18000a729  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a730  lea     rax, WPP_GLOBAL_Control
0x18000a737  cmp     rcx, rax
0x18000a73a  jz      loc_18000AE76
0x18000a740  test    byte ptr [rcx+1Ch], 1
0x18000a744  jz      loc_18000AE76
0x18000a74a  mov     edx, 7Fh
0x18000a74f  jmp     short loc_18000A702
0x18000a751  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a758  mov     rcx, r14; this
0x18000a75b  lea     rdx, aSoftwareinfo; "SoftwareInfo"
0x18000a762  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x18000a767  mov     esi, eax
0x18000a769  test    eax, eax
0x18000a76b  jz      short loc_18000A79F
0x18000a76d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a774  lea     rax, WPP_GLOBAL_Control
0x18000a77b  cmp     rcx, rax
0x18000a77e  jz      loc_18000AE76
0x18000a784  test    byte ptr [rcx+1Ch], 1
0x18000a788  jz      loc_18000AE76
0x18000a78e  mov     edx, 80h
0x18000a793  lea     r9, aSoftwareinfo; "SoftwareInfo"
0x18000a79a  jmp     loc_18000A709
0x18000a79f  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a7a6  mov     rcx, r14; this
0x18000a7a9  lea     rdx, aDevicecompanio; "DeviceCompanionApplications"
0x18000a7b0  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x18000a7b5  mov     esi, eax
0x18000a7b7  cmp     eax, 1
0x18000a7ba  jz      loc_18000AAC1
0x18000a7c0  test    eax, eax
0x18000a7c2  jz      loc_18000A95A
0x18000a7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a7cf  lea     rax, WPP_GLOBAL_Control
0x18000a7d6  cmp     rcx, rax
0x18000a7d9  jz      loc_18000AE76
0x18000a7df  test    byte ptr [rcx+1Ch], 1
0x18000a7e3  jz      loc_18000AE76
0x18000a7e9  mov     edx, 81h
0x18000a7ee  lea     r9, aDevicecompanio; "DeviceCompanionApplications"
0x18000a7f5  jmp     loc_18000A709
0x18000a7fa  test    esi, esi
0x18000a7fc  jnz     loc_18000AA52
0x18000a802  xor     r9d, r9d; int *
0x18000a805  lea     r8, [rsp+2E0h+var_298]; unsigned __int16 **
0x18000a80a  lea     rdx, [rsp+2E0h+lpMem]; unsigned __int16 **
0x18000a80f  mov     rcx, r14; this
0x18000a812  call    ?ReadPackageIdentity@@YAJPEAVTXmlReader@@PEAPEAG1PEAH@Z; ReadPackageIdentity(TXmlReader *,ushort * *,ushort * *,int *)
0x18000a817  mov     esi, eax
0x18000a819  test    eax, eax
0x18000a81b  jnz     loc_18000AD4E
0x18000a821  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a828  lea     rax, WPP_GLOBAL_Control
0x18000a82f  mov     rsi, [rsp+2E0h+lpMem]
0x18000a834  mov     r15, [rsp+2E0h+var_298]
0x18000a839  cmp     rcx, rax
0x18000a83c  jz      short loc_18000A861
0x18000a83e  test    byte ptr [rcx+1Ch], 8
0x18000a842  jz      short loc_18000A861
0x18000a844  mov     rcx, [rcx+10h]
0x18000a848  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x18000a84f  mov     edx, 83h
0x18000a854  mov     qword ptr [rsp+2E0h+dwCreationDisposition], r15
0x18000a859  mov     r9, rsi
0x18000a85c  call    WPP_SF_SS
0x18000a861  mov     rax, [rsp+2E0h+var_290]
0x18000a866  cmp     dword ptr [rax-10h], 0
0x18000a86a  jz      short loc_18000A87D
0x18000a86c  lea     rdx, asc_1800179B4; ";"
0x18000a873  lea     rcx, [rsp+2E0h+var_290]
0x18000a878  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18000a87d  mov     rdx, rsi
0x18000a880  lea     rcx, [rsp+2E0h+var_290]
0x18000a885  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18000a88a  lea     rdx, asc_180017E20; " "
0x18000a891  lea     rcx, [rsp+2E0h+var_290]
0x18000a896  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18000a89b  mov     rdx, r15
0x18000a89e  lea     rcx, [rsp+2E0h+var_290]
0x18000a8a3  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18000a8a8  call    cs:__imp_GetProcessHeap
0x18000a8ae  mov     r8, rsi; lpMem
0x18000a8b1  xor     edx, edx; dwFlags
0x18000a8b3  mov     rcx, rax; hHeap
0x18000a8b6  call    cs:__imp_HeapFree
0x18000a8bc  xor     r12d, r12d
0x18000a8bf  mov     [rsp+2E0h+lpMem], r12
0x18000a8c4  call    cs:__imp_GetProcessHeap
0x18000a8ca  mov     r8, r15; lpMem
0x18000a8cd  xor     edx, edx; dwFlags
0x18000a8cf  mov     rcx, rax; hHeap
0x18000a8d2  call    cs:__imp_HeapFree
0x18000a8d8  xor     r15d, r15d
0x18000a8db  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a8e2  lea     rdx, aApplications; "Applications"
0x18000a8e9  mov     [rsp+2E0h+var_298], r15
0x18000a8ee  mov     rcx, r14; this
0x18000a8f1  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x18000a8f6  test    eax, eax
0x18000a8f8  jnz     short loc_18000A91A
0x18000a8fa  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a901  mov     rcx, r14; this
0x18000a904  lea     rdx, aApplications; "Applications"
0x18000a90b  call    ?SkipElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::SkipElement(ushort const *,ushort const *)
0x18000a910  mov     esi, eax
0x18000a912  test    eax, eax
0x18000a914  jnz     loc_18000A9C6
0x18000a91a  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a921  mov     rcx, r14; this
0x18000a924  lea     rdx, aPackage; "Package"
0x18000a92b  call    ?SkipAnyOtherNodesInElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::SkipAnyOtherNodesInElement(ushort const *,ushort const *)
0x18000a930  mov     esi, eax
0x18000a932  test    eax, eax
0x18000a934  jnz     loc_18000AA2A
0x18000a93a  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a941  mov     rcx, r14; this
0x18000a944  lea     rdx, aPackage; "Package"
0x18000a94b  call    ?ReadEndElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadEndElement(ushort const *,ushort const *)
0x18000a950  mov     esi, eax
0x18000a952  test    eax, eax
0x18000a954  jnz     loc_18000A9F8
0x18000a95a  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a961  mov     rcx, r14; this
0x18000a964  lea     rdx, aPackage; "Package"
0x18000a96b  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x18000a970  mov     esi, eax
0x18000a972  cmp     eax, 1
0x18000a975  jnz     loc_18000A7FA
0x18000a97b  lea     r8, aHttpSchemasMic_1; "http://schemas.microsoft.com/windows/20"...
0x18000a982  mov     rcx, r14; this
0x18000a985  lea     rdx, aDevicecompanio; "DeviceCompanionApplications"
0x18000a98c  call    ?SkipAnyOtherNodesInElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::SkipAnyOtherNodesInElement(ushort const *,ushort const *)
0x18000a991  mov     esi, eax
0x18000a993  test    eax, eax
0x18000a995  jz      loc_18000AA7A
0x18000a99b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9a2  lea     rax, WPP_GLOBAL_Control
0x18000a9a9  cmp     rcx, rax
0x18000a9ac  jz      loc_18000AE76
0x18000a9b2  test    byte ptr [rcx+1Ch], 1
0x18000a9b6  jz      loc_18000AE76
0x18000a9bc  mov     edx, 87h
0x18000a9c1  jmp     loc_18000A7EE
0x18000a9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9cd  lea     rax, WPP_GLOBAL_Control
0x18000a9d4  cmp     rcx, rax
0x18000a9d7  jz      loc_18000AE76
0x18000a9dd  test    byte ptr [rcx+1Ch], 1
0x18000a9e1  jz      loc_18000AE76
0x18000a9e7  mov     edx, 84h
0x18000a9ec  lea     r9, aApplications; "Applications"
0x18000a9f3  jmp     loc_18000A709
0x18000a9f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9ff  lea     rax, WPP_GLOBAL_Control
0x18000aa06  cmp     rcx, rax
0x18000aa09  jz      loc_18000AE76
0x18000aa0f  test    byte ptr [rcx+1Ch], 1
0x18000aa13  jz      loc_18000AE76
0x18000aa19  mov     edx, 86h
0x18000aa1e  lea     r9, aPackage; "Package"
0x18000aa25  jmp     loc_18000A709
  ... truncated ...
```
