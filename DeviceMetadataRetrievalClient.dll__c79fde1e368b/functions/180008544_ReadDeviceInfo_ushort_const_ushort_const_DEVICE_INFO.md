# ReadDeviceInfo(ushort const *,ushort const *,_DEVICE_INFO *)

- ea: `0x180008544`
- end: `0x180008d83`
- name: `?ReadDeviceInfo@@YAJPEBG0PEAU_DEVICE_INFO@@@Z`
- size: `2111`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct _DEVICE_INFO *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006904`

## callees

- `0x180001520`
- `0x180002f2c`
- `0x180004e2c`
- `0x180005018`
- `0x1800050b4`
- `0x180005588`
- `0x180008544`
- `0x18000b64c`
- `0x18000bf9c`
- `0x18000c17c`
- `0x18001066c`
- `0x1800107e4`
- `0x180010a84`
- `0x180010bc8`
- `0x180010c40`
- `0x180010ca0`
- `0x180010d18`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800086a7`
- `KERNEL32!GetLastError` at `0x1800086a7`
- `KERNEL32!CreateFileW` at `0x180008693`
- `KERNEL32!CreateFileW` at `0x180008693`
- `KERNEL32!CloseHandle` at `0x180008cc4`
- `KERNEL32!CloseHandle` at `0x180008cc4`

## string_xrefs

- `0x180008613`: `DeviceInfo.xml`
- `0x1800086d2`: `DeviceInfo.xml`
- `0x18000873c`: `DeviceInfo.xml`
- `0x180008798`: `DeviceInfo.xml`
- `0x1800087e9`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x180008838`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x1800088d6`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x1800088f1`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x180008973`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x1800089fa`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x180008a81`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x180008b00`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`
- `0x180008b48`: `http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/`

## pseudocode

```c
__int64 __fastcall ReadDeviceInfo(const unsigned __int16 *a1, const unsigned __int16 *a2, struct _DEVICE_INFO *a3)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  __int64 v8; // rsi
  __int64 v9; // rbx
  signed int LastError; // r15d
  HANDLE FileW; // rax
  void *v12; // r12
  int v13; // r8d
  int v14; // eax
  int v15; // r8d
  TXmlReader *v16; // r12
  _QWORD *v17; // rcx
  int v18; // edx
  const wchar_t *v19; // r9
  signed int StartElement; // eax
  unsigned __int16 *v21; // r15
  signed int ElementString; // eax
  __int64 v23; // r8
  signed int v24; // eax
  __int64 v25; // r8
  signed int v26; // eax
  __int64 v27; // r8
  _QWORD *v28; // rcx
  unsigned __int16 *v30; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v34; // [rsp+60h] [rbp-A0h]
  struct IStream *v35; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  v35 = 0;
  Block = 0;
  v30 = 0;
  v6 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v31 = v6;
  v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v32 = v7;
  v8 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v33 = v8;
  v9 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v37 = v9;
  LastError = StringCchPrintfW(FileName, 0x104u, L"%ws\\%ws\\%ws", a1, a2, L"DeviceInfo.xml");
  if ( LastError < 0 )
    goto LABEL_106;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, FileName);
  FileW = CreateFileW(FileName, 1u, 1u, 0, 3u, 0x8000000u, 0);
  v34 = FileW;
  v12 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        106,
        (unsigned int)&WPP_896b2d51e548366088657dee2fc85ea9_Traceguids,
        (unsigned int)L"DeviceInfo.xml",
        LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_106;
  }
  LastError = TFileStream::Create(FileW, &v35);
  if ( LastError >= 0 )
  {
    v14 = TXmlReader::Create(v35, (struct TXmlReader **)&Block);
    v16 = (TXmlReader *)Block;
    LastError = v14;
    if ( v14 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v18 = 108;
      goto LABEL_19;
    }
    LastError = TXmlReader::ReadXmlDecleration((TXmlReader *)Block);
    if ( LastError )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v18 = 109;
      goto LABEL_19;
    }
    LastError = TXmlReader::ReadStartElement(
                  v16,
                  L"DeviceInfo",
                  L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/");
    if ( LastError )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_100;
      v18 = 110;
      goto LABEL_29;
    }
    StartElement = TXmlReader::ReadStartElement(
                     v16,
                     L"DeviceCategoryList",
                     L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/");
    LastError = StartElement;
    if ( StartElement == 1 )
    {
LABEL_49:
      ElementString = TXmlReader::ReadElementString(
                        v16,
                        L"ModelName",
                        L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/",
                        (const unsigned __int16 **)&v30);
      LastError = ElementString;
      if ( ElementString != 1 )
      {
        if ( ElementString )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_100;
          v18 = 114;
          v19 = L"ModelName";
          goto LABEL_20;
        }
        if ( v30 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v30[v23] );
        }
        else
        {
          v23 = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v32, v30, v23);
        v7 = v32;
      }
      v24 = TXmlReader::ReadElementString(
              v16,
              L"Manufacturer",
              L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/",
              (const unsigned __int16 **)&v30);
      LastError = v24;
      if ( v24 != 1 )
      {
        if ( v24 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_100;
          v18 = 115;
          v19 = L"Manufacturer";
          goto LABEL_20;
        }
        if ( v30 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v30[v25] );
        }
        else
        {
          v25 = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v33, v30, v25);
        v8 = v33;
      }
      v26 = TXmlReader::ReadElementString(
              v16,
              L"DeviceIconFile",
              L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/",
              (const unsigned __int16 **)&v30);
      LastError = v26;
      if ( v26 != 1 )
      {
        if ( v26 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_100;
          v18 = 116;
          v19 = L"DeviceIconFile";
          goto LABEL_20;
        }
        if ( v30 )
        {
          v27 = -1;
          do
            ++v27;
          while ( v30[v27] );
        }
        else
        {
          v27 = 0;
        }
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v37, v30, v27);
        v9 = v37;
      }
      LastError = TXmlReader::SkipAnyOtherNodesInElement(
                    v16,
                    L"DeviceInfo",
                    L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/");
      if ( LastError )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_100;
        v18 = 117;
LABEL_19:
        v19 = L"DeviceInfo.xml";
LABEL_20:
        WPP_SF_Sd(v17[2], v18, v15, (_DWORD)v19, LastError);
        goto LABEL_100;
      }
      LastError = TXmlReader::ReadEndElement(
                    v16,
                    L"DeviceInfo",
                    L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/");
      if ( !LastError )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 119, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v6);
            v28 = WPP_GLOBAL_Control;
          }
          if ( v28 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v28 + 28) & 8) != 0 )
            {
              WPP_SF_S(v28[2], 120, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v7);
              v28 = WPP_GLOBAL_Control;
            }
            if ( v28 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v28 + 28) & 8) != 0 )
              {
                WPP_SF_S(v28[2], 121, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v8);
                v28 = WPP_GLOBAL_Control;
              }
              if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 8) != 0 )
                WPP_SF_S(v28[2], 122, &WPP_896b2d51e548366088657dee2fc85ea9_Traceguids, v9);
            }
          }
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          a3,
          &v31);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (char *)a3 + 8,
          &v32);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
          (char *)a3 + 16,
          &v33);
        *((_DWORD *)a3 + 6) = *(_DWORD *)(v9 - 16) != 0;
        goto LABEL_100;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 118;
LABEL_29:
        v19 = L"DeviceInfo";
        goto LABEL_20;
      }
    }
    else
    {
      if ( !StartElement )
      {
        while ( 1 )
        {
          LastError = TXmlReader::ReadElementString(
                        v16,
                        L"DeviceCategory",
                        L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/",
                        (const unsigned __int16 **)&v30);
          if ( LastError == 1 )
          {
            LastError = TXmlReader::ReadEndElement(
                          v16,
                          L"DeviceCategoryList",
                          L"http://schemas.microsoft.com/windows/DeviceMetadata/DeviceInfo/2007/11/");
            if ( !LastError )
              goto LABEL_49;
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v18 = 113;
              goto LABEL_35;
            }
            goto LABEL_100;
          }
          if ( LastError )
            break;
          v21 = v30;
          if ( *v30 )
          {
            if ( *(_DWORD *)(v6 - 16) )
              ATL::CSimpleStringT<unsigned short,0>::Append(&v31, L";");
            ATL::CSimpleStringT<unsigned short,0>::Append(&v31, v21);
            v6 = v31;
          }
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v18 = 112;
          v19 = L"DeviceCategory";
          goto LABEL_20;
        }
        goto LABEL_100;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 111;
LABEL_35:
        v19 = L"DeviceCategoryList";
        goto LABEL_20;
      }
    }
LABEL_100:
    if ( v16 )
    {
      TXmlReader::~TXmlReader(v16);
      operator delete(v16);
    }
    v12 = v34;
    goto LABEL_103;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, v13, (unsigned int)L"DeviceInfo.xml", LastError);
LABEL_103:
  if ( v35 )
    ((void (__fastcall *)(struct IStream *))v35->lpVtbl->Release)(v35);
  CloseHandle(v12);
LABEL_106:
  if ( _InterlockedDecrement((volatile signed __int32 *)(v9 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v9 - 24) + 8LL))(*(_QWORD *)(v9 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)(v8 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v8 - 24) + 8LL))(*(_QWORD *)(v8 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)(v7 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 - 24) + 8LL))(*(_QWORD *)(v7 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)(v6 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v6 - 24) + 8LL))(*(_QWORD *)(v6 - 24));
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180008544  mov     [rsp-8+arg_18], rbx
0x180008549  push    rbp
0x18000854a  push    rsi
0x18000854b  push    rdi
0x18000854c  push    r12
0x18000854e  push    r13
0x180008550  push    r14
0x180008552  push    r15
0x180008554  lea     rbp, [rsp-1A0h]
0x18000855c  sub     rsp, 2A0h
0x180008563  mov     rax, cs:__security_cookie
0x18000856a  xor     rax, rsp
0x18000856d  mov     [rbp+1D0h+var_40], rax
0x180008574  xor     eax, eax
0x180008576  lea     rbx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000857d  mov     [rsp+2D0h+var_268], rax
0x180008582  mov     r15, rcx
0x180008585  mov     [rsp+2D0h+Block], rax
0x18000858a  mov     rcx, rbx
0x18000858d  mov     [rsp+2D0h+var_290], rax
0x180008592  mov     r13, r8
0x180008595  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000859c  mov     r12, rdx
0x18000859f  mov     rax, [rax+18h]
0x1800085a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085a8  mov     rcx, rbx
0x1800085ab  lea     rdi, [rax+18h]
0x1800085af  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800085b6  mov     [rsp+2D0h+var_288], rdi
0x1800085bb  mov     rax, [rax+18h]
0x1800085bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085c4  mov     rcx, rbx
0x1800085c7  lea     r14, [rax+18h]
0x1800085cb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800085d2  mov     [rsp+2D0h+var_280], r14
0x1800085d7  mov     rax, [rax+18h]
0x1800085db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085e0  mov     rcx, rbx
0x1800085e3  lea     rsi, [rax+18h]
0x1800085e7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800085ee  mov     [rsp+2D0h+var_278], rsi
0x1800085f3  mov     rax, [rax+18h]
0x1800085f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085fc  mov     r9, r15
0x1800085ff  lea     r8, aWsWsWs; "%ws\\%ws\\%ws"
0x180008606  mov     edx, 104h; unsigned __int64
0x18000860b  lea     rcx, [rbp+1D0h+FileName]; unsigned __int16 *
0x18000860f  lea     rbx, [rax+18h]
0x180008613  lea     rax, aDeviceinfoXml; "DeviceInfo.xml"
0x18000861a  mov     [rsp+2D0h+var_258], rbx
0x18000861f  mov     qword ptr [rsp+2D0h+dwFlagsAndAttributes], rax
0x180008624  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r12
0x180008629  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000862e  xor     r12d, r12d
0x180008631  mov     r15d, eax
0x180008634  test    eax, eax
0x180008636  js      loc_180008CCA
0x18000863c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008643  lea     rax, WPP_GLOBAL_Control
0x18000864a  cmp     rcx, rax
0x18000864d  jz      short loc_18000866E
0x18000864f  test    byte ptr [rcx+1Ch], 8
0x180008653  jz      short loc_18000866E
0x180008655  mov     rcx, [rcx+10h]
0x180008659  lea     edx, [r12+69h]
0x18000865e  lea     r9, [rbp+1D0h+FileName]
0x180008662  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x180008669  call    WPP_SF_S
0x18000866e  xor     r9d, r9d; lpSecurityAttributes
0x180008671  mov     [rsp+2D0h+hTemplateFile], r12; hTemplateFile
0x180008676  mov     [rsp+2D0h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x18000867e  lea     rcx, [rbp+1D0h+FileName]; lpFileName
0x180008682  mov     [rsp+2D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000868a  lea     eax, [r9+1]
0x18000868e  mov     r8d, eax; dwShareMode
0x180008691  mov     edx, eax; dwDesiredAccess
0x180008693  call    cs:__imp_CreateFileW
0x180008699  mov     [rsp+2D0h+var_270], rax
0x18000869e  mov     r12, rax
0x1800086a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800086a5  jnz     short loc_180008703
0x1800086a7  call    cs:__imp_GetLastError
0x1800086ad  mov     r15d, eax
0x1800086b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086b7  lea     rax, WPP_GLOBAL_Control
0x1800086be  cmp     rcx, rax
0x1800086c1  jz      short loc_1800086EA
0x1800086c3  test    byte ptr [rcx+1Ch], 1
0x1800086c7  jz      short loc_1800086EA
0x1800086c9  mov     rcx, [rcx+10h]
0x1800086cd  lea     edx, [r12+6Bh]
0x1800086d2  lea     r9, aDeviceinfoXml; "DeviceInfo.xml"
0x1800086d9  mov     [rsp+2D0h+dwCreationDisposition], r15d
0x1800086de  lea     r8, WPP_896b2d51e548366088657dee2fc85ea9_Traceguids
0x1800086e5  call    WPP_SF_SD
0x1800086ea  test    r15d, r15d
0x1800086ed  jle     loc_180008CCA
0x1800086f3  movzx   r15d, r15w
0x1800086f7  or      r15d, 80070000h
0x1800086fe  jmp     loc_180008CCA
0x180008703  lea     rdx, [rsp+2D0h+var_268]; struct IStream **
0x180008708  mov     rcx, rax; hSourceHandle
0x18000870b  call    ?Create@TFileStream@@SAJPEAXPEAPEAUIStream@@@Z; TFileStream::Create(void *,IStream * *)
0x180008710  mov     r15d, eax
0x180008713  test    eax, eax
0x180008715  jns     short loc_180008757
0x180008717  mov     rcx, cs:WPP_GLOBAL_Control
0x18000871e  lea     rax, WPP_GLOBAL_Control
0x180008725  cmp     rcx, rax
0x180008728  jz      loc_180008CAB
0x18000872e  test    byte ptr [rcx+1Ch], 1
0x180008732  jz      loc_180008CAB
0x180008738  mov     rcx, [rcx+10h]
0x18000873c  lea     r9, aDeviceinfoXml; "DeviceInfo.xml"
0x180008743  mov     edx, 6Bh ; 'k'
0x180008748  mov     [rsp+2D0h+dwCreationDisposition], r15d
0x18000874d  call    WPP_SF_Sd
0x180008752  jmp     loc_180008CAB
0x180008757  mov     rcx, [rsp+2D0h+var_268]; struct IStream *
0x18000875c  lea     rdx, [rsp+2D0h+Block]; struct TXmlReader **
0x180008761  call    ?Create@TXmlReader@@SAJPEAUIStream@@PEAPEAV1@@Z; TXmlReader::Create(IStream *,TXmlReader * *)
0x180008766  mov     r12, [rsp+2D0h+Block]
0x18000876b  mov     r15d, eax
0x18000876e  test    eax, eax
0x180008770  jns     short loc_1800087B2
0x180008772  mov     rcx, cs:WPP_GLOBAL_Control
0x180008779  lea     rax, WPP_GLOBAL_Control
0x180008780  cmp     rcx, rax
0x180008783  jz      loc_180008C91
0x180008789  test    byte ptr [rcx+1Ch], 1
0x18000878d  jz      loc_180008C91
0x180008793  mov     edx, 6Ch ; 'l'
0x180008798  lea     r9, aDeviceinfoXml; "DeviceInfo.xml"
0x18000879f  mov     rcx, [rcx+10h]
0x1800087a3  mov     [rsp+2D0h+dwCreationDisposition], r15d
0x1800087a8  call    WPP_SF_Sd
0x1800087ad  jmp     loc_180008C91
0x1800087b2  mov     rcx, r12; this
0x1800087b5  call    ?ReadXmlDecleration@TXmlReader@@QEAAJXZ; TXmlReader::ReadXmlDecleration(void)
0x1800087ba  mov     r15d, eax
0x1800087bd  test    eax, eax
0x1800087bf  jz      short loc_1800087E9
0x1800087c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800087c8  lea     rax, WPP_GLOBAL_Control
0x1800087cf  cmp     rcx, rax
0x1800087d2  jz      loc_180008C91
0x1800087d8  test    byte ptr [rcx+1Ch], 1
0x1800087dc  jz      loc_180008C91
0x1800087e2  mov     edx, 6Dh ; 'm'
0x1800087e7  jmp     short loc_180008798
0x1800087e9  lea     r8, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x1800087f0  mov     rcx, r12; this
0x1800087f3  lea     rdx, aDeviceinfo; "DeviceInfo"
0x1800087fa  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x1800087ff  mov     r15d, eax
0x180008802  test    eax, eax
0x180008804  jz      short loc_180008838
0x180008806  mov     rcx, cs:WPP_GLOBAL_Control
0x18000880d  lea     rax, WPP_GLOBAL_Control
0x180008814  cmp     rcx, rax
0x180008817  jz      loc_180008C91
0x18000881d  test    byte ptr [rcx+1Ch], 1
0x180008821  jz      loc_180008C91
0x180008827  mov     edx, 6Eh ; 'n'
0x18000882c  lea     r9, aDeviceinfo; "DeviceInfo"
0x180008833  jmp     loc_18000879F
0x180008838  lea     r8, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x18000883f  mov     rcx, r12; this
0x180008842  lea     rdx, aDevicecategory_0; "DeviceCategoryList"
0x180008849  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x18000884e  mov     r15d, eax
0x180008851  cmp     eax, 1
0x180008854  jz      loc_18000896B
0x18000885a  test    eax, eax
0x18000885c  jz      short loc_1800088CE
0x18000885e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008865  lea     rax, WPP_GLOBAL_Control
0x18000886c  cmp     rcx, rax
0x18000886f  jz      loc_180008C91
0x180008875  test    byte ptr [rcx+1Ch], 1
0x180008879  jz      loc_180008C91
0x18000887f  mov     edx, 6Fh ; 'o'
0x180008884  lea     r9, aDevicecategory_0; "DeviceCategoryList"
0x18000888b  jmp     loc_18000879F
0x180008890  xor     ecx, ecx
0x180008892  test    r15d, r15d
0x180008895  jnz     loc_180008939
0x18000889b  mov     r15, [rsp+2D0h+var_290]
0x1800088a0  cmp     [r15], cx
0x1800088a4  jz      short loc_1800088CE
0x1800088a6  cmp     [rdi-10h], ecx
0x1800088a9  jz      short loc_1800088BC
0x1800088ab  lea     rdx, asc_1800179B4; ";"
0x1800088b2  lea     rcx, [rsp+2D0h+var_288]
0x1800088b7  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800088bc  mov     rdx, r15
0x1800088bf  lea     rcx, [rsp+2D0h+var_288]
0x1800088c4  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800088c9  mov     rdi, [rsp+2D0h+var_288]
0x1800088ce  lea     r9, [rsp+2D0h+var_290]; unsigned __int16 **
0x1800088d3  mov     rcx, r12; this
0x1800088d6  lea     r8, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x1800088dd  lea     rdx, aDevicecategory; "DeviceCategory"
0x1800088e4  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
0x1800088e9  mov     r15d, eax
0x1800088ec  cmp     eax, 1
0x1800088ef  jnz     short loc_180008890
0x1800088f1  lea     r8, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x1800088f8  mov     rcx, r12; this
0x1800088fb  lea     rdx, aDevicecategory_0; "DeviceCategoryList"
0x180008902  call    ?ReadEndElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadEndElement(ushort const *,ushort const *)
0x180008907  mov     r15d, eax
0x18000890a  test    eax, eax
0x18000890c  jz      short loc_18000896B
0x18000890e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008915  lea     rax, WPP_GLOBAL_Control
0x18000891c  cmp     rcx, rax
0x18000891f  jz      loc_180008C91
0x180008925  test    byte ptr [rcx+1Ch], 1
0x180008929  jz      loc_180008C91
0x18000892f  mov     edx, 71h ; 'q'
0x180008934  jmp     loc_180008884
0x180008939  mov     rcx, cs:WPP_GLOBAL_Control
0x180008940  lea     rax, WPP_GLOBAL_Control
0x180008947  cmp     rcx, rax
0x18000894a  jz      loc_180008C91
0x180008950  test    byte ptr [rcx+1Ch], 1
0x180008954  jz      loc_180008C91
0x18000895a  mov     edx, 70h ; 'p'
0x18000895f  lea     r9, aDevicecategory; "DeviceCategory"
0x180008966  jmp     loc_18000879F
0x18000896b  lea     r9, [rsp+2D0h+var_290]; unsigned __int16 **
0x180008970  mov     rcx, r12; this
0x180008973  lea     r8, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x18000897a  lea     rdx, aModelname; "ModelName"
0x180008981  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
0x180008986  mov     r15d, eax
0x180008989  cmp     eax, 1
0x18000898c  jz      short loc_1800089F2
0x18000898e  xor     ecx, ecx
0x180008990  test    eax, eax
0x180008992  jz      short loc_1800089C6
0x180008994  mov     rcx, cs:WPP_GLOBAL_Control
0x18000899b  lea     rax, WPP_GLOBAL_Control
0x1800089a2  cmp     rcx, rax
0x1800089a5  jz      loc_180008C91
0x1800089ab  test    byte ptr [rcx+1Ch], 1
0x1800089af  jz      loc_180008C91
0x1800089b5  mov     edx, 72h ; 'r'
0x1800089ba  lea     r9, aModelname; "ModelName"
0x1800089c1  jmp     loc_18000879F
0x1800089c6  mov     rdx, [rsp+2D0h+var_290]
0x1800089cb  test    rdx, rdx
0x1800089ce  jnz     short loc_1800089D5
0x1800089d0  mov     r8d, ecx
0x1800089d3  jmp     short loc_1800089E3
0x1800089d5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800089d9  inc     r8
0x1800089dc  cmp     [rdx+r8*2], cx
0x1800089e1  jnz     short loc_1800089D9
0x1800089e3  lea     rcx, [rsp+2D0h+var_280]
0x1800089e8  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800089ed  mov     r14, [rsp+2D0h+var_280]
0x1800089f2  lea     r9, [rsp+2D0h+var_290]; unsigned __int16 **
0x1800089f7  mov     rcx, r12; this
0x1800089fa  lea     r8, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x180008a01  lea     rdx, aManufacturer; "Manufacturer"
0x180008a08  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
0x180008a0d  mov     r15d, eax
0x180008a10  cmp     eax, 1
0x180008a13  jz      short loc_180008A79
0x180008a15  xor     ecx, ecx
0x180008a17  test    eax, eax
0x180008a19  jz      short loc_180008A4D
0x180008a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a22  lea     rax, WPP_GLOBAL_Control
0x180008a29  cmp     rcx, rax
0x180008a2c  jz      loc_180008C91
0x180008a32  test    byte ptr [rcx+1Ch], 1
0x180008a36  jz      loc_180008C91
0x180008a3c  mov     edx, 73h ; 's'
0x180008a41  lea     r9, aManufacturer; "Manufacturer"
0x180008a48  jmp     loc_18000879F
0x180008a4d  mov     rdx, [rsp+2D0h+var_290]
0x180008a52  test    rdx, rdx
0x180008a55  jnz     short loc_180008A5C
0x180008a57  mov     r8d, ecx
0x180008a5a  jmp     short loc_180008A6A
0x180008a5c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008a60  inc     r8
0x180008a63  cmp     [rdx+r8*2], cx
0x180008a68  jnz     short loc_180008A60
0x180008a6a  lea     rcx, [rsp+2D0h+var_278]
0x180008a6f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180008a74  mov     rsi, [rsp+2D0h+var_278]
0x180008a79  lea     r9, [rsp+2D0h+var_290]; unsigned __int16 **
0x180008a7e  mov     rcx, r12; this
0x180008a81  lea     r8, aHttpSchemasMic_3; "http://schemas.microsoft.com/windows/De"...
0x180008a88  lea     rdx, aDeviceiconfile; "DeviceIconFile"
0x180008a8f  call    ?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z; TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)
  ... truncated ...
```
