# NgcUtils::NgcKeyName::ParseNgcKeyNameString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<uchar,std::allocator<uchar>> *,_GUID *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180012ab0`
- end: `0x180013705`
- name: `?ParseNgcKeyNameString@NgcKeyName@NgcUtils@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV?$vector@EV?$allocator@E@std@@@4@PEAU_GUID@@PEAV34@33@Z`
- size: `3157`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800128e4`

## callees

- `0x18000e960`
- `0x180012ab0`
- `0x180016350`
- `0x1800224b0`
- `0x1800266c8`
- `0x180028900`
- `0x18005cab0`
- `0x18005cee0`
- `0x18005d2b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ce1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012ce1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012d9e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012e92`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012fc9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800130f9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800131ea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001336b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001350d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800136da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012d9e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012e92`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012fc9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800130f9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800131ea`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001336b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001350d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800136da`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012dd0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180012dd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012db4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001354d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013615`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012cd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012db4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012ea8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013119`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001354d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013615`
- `RPCRT4!UuidFromStringW` at `0x180013036`
- `RPCRT4!UuidFromStringW` at `0x180013036`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012cad`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180012cad`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall NgcUtils::NgcKeyName::ParseNgcKeyNameString(
        _QWORD *a1,
        __int64 a2,
        UUID *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  unsigned __int64 v9; // rax
  _QWORD *v10; // r14
  char *v11; // rbx
  __int64 trivial_2; // rax
  __int64 v13; // rdx
  __int64 v14; // rsi
  DWORD LengthSid; // r15d
  __int64 v16; // rax
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  const WCHAR *v19; // rcx
  BOOL v20; // r14d
  void *v21; // r8
  signed int LastError; // eax
  unsigned int v23; // edi
  HLOCAL v24; // rcx
  unsigned __int64 v26; // rsi
  HLOCAL v27; // rcx
  unsigned __int64 v28; // rdx
  char *v29; // rcx
  __int64 first_of; // rax
  __int64 v31; // rdx
  __int64 v32; // r14
  __int64 v33; // rax
  unsigned __int16 *v34; // rcx
  RPC_STATUS v35; // eax
  unsigned int v36; // esi
  HLOCAL v37; // rcx
  __int64 v38; // rsi
  __int16 *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rdx
  __int64 v42; // r14
  __int64 v43; // rax
  __int64 v44; // rsi
  char *v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r14
  __int64 v49; // rax
  unsigned __int64 v50; // r14
  HLOCAL v51; // rcx
  bool v52; // zf
  __int64 v53; // rax
  HLOCAL v54; // rcx
  __int64 v55; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v56; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  void *v59[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h]
  unsigned __int64 v61; // [rsp+70h] [rbp-90h]
  PSID Sid[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+88h] [rbp-78h]
  __int64 v64; // [rsp+90h] [rbp-70h]
  RPC_WSTR StringUuid[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v67; // [rsp+B0h] [rbp-50h]
  LPCWSTR StringSid[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v70; // [rsp+D0h] [rbp-30h]
  __int128 v71; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v72; // [rsp+E8h] [rbp-18h]
  __int64 v73; // [rsp+F0h] [rbp-10h]
  UUID Uuid; // [rsp+F8h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+108h] [rbp+8h] BYREF
  char *v76; // [rsp+118h] [rbp+18h]
  int v77; // [rsp+120h] [rbp+20h]
  int v78; // [rsp+124h] [rbp+24h]
  __int64 *v79; // [rsp+128h] [rbp+28h]
  __int64 v80; // [rsp+130h] [rbp+30h]

  v56 = a4;
  v55 = a5;
  *(_QWORD *)&EventDescriptor.Id = a6;
  v9 = a1[2];
  if ( v9 > 0x433 )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v55) = -2147024809;
      v79 = &v55;
      v80 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v76 = byte_180107B55;
      v77 = 46;
      v78 = 1;
      LODWORD(v56) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_91:
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      return 2147942487LL;
    }
    return 2147942487LL;
  }
  if ( a1[3] <= 7u )
    v10 = a1;
  else
    v10 = (_QWORD *)*a1;
  if ( !v9
    || (v11 = (char *)v10 + 2 * v9, trivial_2 = _std_find_trivial_2(v10, v11, 47), (char *)trivial_2 == v11)
    || (v14 = (trivial_2 - (__int64)v10) >> 1, v14 == -1) )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v56) = -2147024809;
      v79 = &v56;
      v80 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v76 = &byte_180107B8F;
      v77 = 36;
      v78 = 1;
      LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      goto LABEL_91;
    }
    return 2147942487LL;
  }
  *(_OWORD *)StringSid = 0;
  v69 = 0;
  v70 = 7;
  LOWORD(StringSid[0]) = 0;
  hMem = 0;
  LengthSid = 0;
  if ( v14 )
  {
    v16 = std::wstring::substr(a1, v59, 0, v14);
    std::wstring::operator=(StringSid, v16);
    if ( v61 > 7 )
    {
      v17 = 2 * v61 + 2;
      if ( v17 < 0x1000 )
      {
        v18 = v59[0];
      }
      else
      {
        v18 = (void *)*((_QWORD *)v59[0] - 1);
        if ( (unsigned __int64)((char *)v59[0] - (char *)v18 - 8) > 0x1F )
          __fastfail(5u);
        v17 = 2 * v61 + 41;
      }
      operator delete(v18, v17);
    }
    v60 = 0;
    v61 = 7;
    LOWORD(v59[0]) = 0;
    Sid[0] = &hMem;
    Sid[1] = 0;
    LOBYTE(v63) = 1;
    v19 = (const WCHAR *)StringSid;
    if ( v70 > 7 )
      v19 = StringSid[0];
    v20 = ConvertStringSidToSidW(v19, &Sid[1]);
    if ( (_BYTE)v63 )
    {
      v21 = *(void **)Sid[0];
      *(_QWORD *)Sid[0] = Sid[1];
      if ( v21 )
        LocalFree(v21);
    }
    if ( !v20 )
    {
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(v56) = v23;
        v79 = &v56;
        v80 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_180122078;
        UserData.Size = *(unsigned __int16 *)off_180122078;
        UserData.Reserved = 2;
        v76 = (char *)&word_180107AE6;
        v77 = 43;
        v78 = 1;
        LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      v24 = hMem;
      hMem = 0;
      if ( v24 )
        LocalFree(v24);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      return v23;
    }
    LengthSid = GetLengthSid(hMem);
  }
  v26 = v14 + 1;
  if ( v26 >= a1[2] )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v56) = -2147024809;
      v79 = &v56;
      v80 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v76 = byte_180107B1D;
      v77 = 44;
      v78 = 1;
      LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v27 = hMem;
    hMem = 0;
    if ( v27 )
      LocalFree(v27);
    if ( v70 > 7 )
    {
      v28 = 2 * v70 + 2;
      if ( v28 < 0x1000 )
      {
        operator delete((void *)StringSid[0], v28);
      }
      else
      {
        v29 = (char *)*((_QWORD *)StringSid[0] - 1);
        if ( (unsigned __int64)((char *)StringSid[0] - v29 - 8) > 0x1F )
          __fastfail(5u);
        operator delete(v29, 2 * v70 + 41);
      }
    }
    return 2147942487LL;
  }
  first_of = std::wstring::find_first_of(a1, v13, v26);
  v32 = first_of;
  if ( first_of == -1 )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v56) = -2147024809;
      v79 = &v56;
      v80 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v76 = (char *)&word_180107AAE;
      v77 = 44;
      v78 = 1;
      LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    goto LABEL_81;
  }
  *(_OWORD *)StringUuid = 0;
  v66 = 0;
  v67 = 7;
  LOWORD(StringUuid[0]) = 0;
  Uuid = 0;
  if ( first_of != v26 )
  {
    v33 = std::wstring::substr(a1, v59, v26, first_of - v26);
    std::wstring::operator=(StringUuid, v33);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v59);
    v34 = (unsigned __int16 *)StringUuid;
    if ( v67 > 7 )
      v34 = StringUuid[0];
    v35 = UuidFromStringW(v34, &Uuid);
    v36 = v35;
    if ( v35 )
    {
      if ( v35 > 0 )
        v36 = (unsigned __int16)v35 | 0x80070000;
      if ( (unsigned int)dword_180122070 > 2 )
      {
        LODWORD(v56) = v36;
        v79 = &v56;
        v80 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_180122078;
        UserData.Size = *(unsigned __int16 *)off_180122078;
        UserData.Reserved = 2;
        v76 = (char *)&dword_180107A3C;
        v77 = 51;
        v78 = 1;
        LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringUuid);
      v37 = hMem;
      hMem = 0;
      if ( v37 )
        LocalFree(v37);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      return v36;
    }
  }
  v38 = v32 + 1;
  if ( (unsigned __int64)(v32 + 1) >= a1[2] )
  {
    if ( (unsigned int)dword_180122070 <= 2 )
    {
LABEL_80:
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringUuid);
LABEL_81:
      v51 = hMem;
      v52 = hMem == 0;
      hMem = 0;
      if ( !v52 )
        LocalFree(v51);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
      return 2147942487LL;
    }
    LODWORD(v56) = -2147024809;
    v79 = &v56;
    v80 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180122078;
    UserData.Size = *(unsigned __int16 *)off_180122078;
    v39 = (__int16 *)byte_180107A7B;
LABEL_60:
    UserData.Reserved = 2;
    v76 = (char *)v39;
    v77 = 39;
    v78 = 1;
    LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    goto LABEL_80;
  }
  v40 = std::wstring::find_first_of(a1, v31, v32 + 1);
  v42 = v40;
  if ( v40 == -1 )
  {
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_80;
    LODWORD(v56) = -2147024809;
    v79 = &v56;
    v80 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180122078;
    UserData.Size = *(unsigned __int16 *)off_180122078;
    v39 = &word_1801079D6;
    goto LABEL_60;
  }
  *(_OWORD *)Sid = 0;
  v63 = 0;
  v64 = 7;
  LOWORD(Sid[0]) = 0;
  if ( v40 != v38 )
  {
    v43 = std::wstring::substr(a1, v59, v38, v40 - v38);
    std::wstring::operator=(Sid, v43);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v59);
  }
  v44 = v42 + 1;
  if ( (unsigned __int64)(v42 + 1) >= a1[2] )
  {
    if ( (unsigned int)dword_180122070 <= 2 )
    {
LABEL_79:
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Sid);
      goto LABEL_80;
    }
    LODWORD(v56) = -2147024809;
    v79 = &v56;
    v80 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180122078;
    UserData.Size = *(unsigned __int16 *)off_180122078;
    v45 = byte_180107A09;
LABEL_69:
    UserData.Reserved = 2;
    v76 = v45;
    v77 = 39;
    v78 = 1;
    LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    goto LABEL_79;
  }
  v46 = std::wstring::find_first_of(a1, v41, v42 + 1);
  v48 = v46;
  if ( v46 == -1 )
  {
    if ( (unsigned int)dword_180122070 <= 2 )
      goto LABEL_79;
    LODWORD(v56) = -2147024809;
    v79 = &v56;
    v80 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180122078;
    UserData.Size = *(unsigned __int16 *)off_180122078;
    v45 = byte_18010796D;
    goto LABEL_69;
  }
  *(_OWORD *)v59 = 0;
  v60 = 0;
  v61 = 7;
  LOWORD(v59[0]) = 0;
  if ( v46 != v44 )
  {
    v49 = std::wstring::substr(a1, &v71, v44, v46 - v44);
    std::wstring::operator=(v59, v49);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v71);
  }
  v50 = v48 + 1;
  v71 = 0;
  v72 = 0;
  v73 = 7;
  LOWORD(v71) = 0;
  if ( std::wstring::find_first_of(a1, v47, v50) != -1 )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v56) = -2147024809;
      v79 = &v56;
      v80 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v76 = (char *)&unk_1801079A0;
      v77 = 42;
      v78 = 1;
      LODWORD(v55) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v71);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v59);
    goto LABEL_79;
  }
  if ( v50 < a1[2] )
  {
    v53 = std::wstring::substr(a1, &UserData, v50, -1);
    std::wstring::operator=(&v71, v53);
    std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&UserData);
  }
  std::vector<unsigned char>::assign<unsigned char *,0>(a2, hMem, (char *)hMem + LengthSid);
  *a3 = Uuid;
  std::wstring::operator=(v56, Sid);
  std::wstring::operator=(v55, v59);
  std::wstring::operator=(*(_QWORD *)&EventDescriptor.Id, &v71);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(&v71);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(v59);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(Sid);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringUuid);
  v54 = hMem;
  hMem = 0;
  if ( v54 )
    LocalFree(v54);
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(StringSid);
  return 0;
}

```

## disassembly

```asm
0x180012ab0  push    rbp
0x180012ab2  push    rbx
0x180012ab3  push    rsi
0x180012ab4  push    rdi
0x180012ab5  push    r12
0x180012ab7  push    r13
0x180012ab9  push    r14
0x180012abb  push    r15
0x180012abd  lea     rbp, [rsp-48h]
0x180012ac2  sub     rsp, 148h
0x180012ac9  mov     rax, cs:__security_cookie
0x180012ad0  xor     rax, rsp
0x180012ad3  mov     [rbp+80h+var_48], rax
0x180012ad7  mov     [rsp+180h+var_148], r9
0x180012adc  mov     r13, r8
0x180012adf  mov     r12, rdx
0x180012ae2  mov     rdi, rcx
0x180012ae5  mov     rax, [rbp+80h+arg_20]
0x180012aec  mov     [rsp+180h+var_150], rax
0x180012af1  mov     rax, [rbp+80h+arg_28]
0x180012af8  mov     qword ptr [rsp+180h+EventDescriptor.Id], rax
0x180012afd  mov     rax, [rcx+10h]
0x180012b01  cmp     rax, 433h
0x180012b07  jbe     loc_180012B9D
0x180012b0d  mov     eax, cs:dword_180122070
0x180012b13  cmp     eax, 2
0x180012b16  jbe     loc_1800136E0
0x180012b1c  mov     dword ptr [rsp+180h+var_150], 80070057h
0x180012b24  lea     rax, [rsp+180h+var_150]
0x180012b29  mov     [rbp+80h+var_58], rax
0x180012b2d  mov     [rbp+80h+var_50], 4
0x180012b35  xor     ebx, ebx
0x180012b37  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180012b3f  movzx   eax, cs:word_180107B4B
0x180012b46  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180012b4a  mov     [rsp+180h+EventDescriptor.Keyword], rbx
0x180012b4f  mov     rax, cs:off_180122078
0x180012b56  mov     [rbp+80h+var_78.Ptr], rax
0x180012b5a  movzx   eax, word ptr [rax]
0x180012b5d  mov     [rbp+80h+var_78.Size], eax
0x180012b60  mov     dword ptr [rbp+80h+var_78.0Ch], 2
0x180012b67  lea     rax, byte_180107B55
0x180012b6e  mov     [rbp+80h+var_68], rax
0x180012b72  mov     [rbp+80h+var_60], 2Eh ; '.'
0x180012b79  mov     [rbp+80h+var_5C], 1
0x180012b80  lea     rax, _TraceLoggingMetadataEnd
0x180012b87  lea     rcx, _TraceLoggingMetadata
0x180012b8e  sub     eax, ecx
0x180012b90  mov     dword ptr [rsp+180h+var_148], eax
0x180012b94  mov     eax, dword ptr [rsp+180h+var_148]
0x180012b98  jmp     loc_1800136B7
0x180012b9d  cmp     qword ptr [rcx+18h], 7
0x180012ba2  jbe     short loc_180012BA9
0x180012ba4  mov     r14, [rcx]
0x180012ba7  jmp     short loc_180012BAC
0x180012ba9  mov     r14, rdi
0x180012bac  test    rax, rax
0x180012baf  jz      loc_18001362C
0x180012bb5  lea     rbx, [r14+rax*2]
0x180012bb9  mov     r8d, 2Fh ; '/'
0x180012bbf  mov     rdx, rbx
0x180012bc2  mov     rcx, r14
0x180012bc5  call    __std_find_trivial_2
0x180012bca  mov     rsi, rax
0x180012bcd  cmp     rax, rbx
0x180012bd0  jz      loc_18001362C
0x180012bd6  sub     rsi, r14
0x180012bd9  sar     rsi, 1
0x180012bdc  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180012be0  jz      loc_18001362C
0x180012be6  xorps   xmm0, xmm0
0x180012be9  movups  xmmword ptr [rbp+80h+StringSid], xmm0
0x180012bed  xor     ebx, ebx
0x180012bef  mov     [rbp+80h+var_B8], rbx
0x180012bf3  mov     [rbp+80h+var_B0], 7
0x180012bfb  mov     word ptr [rbp+80h+StringSid], bx
0x180012bff  mov     [rsp+180h+hMem], rbx
0x180012c04  mov     r15d, ebx
0x180012c07  test    rsi, rsi
0x180012c0a  jz      loc_180012DD9
0x180012c10  mov     r9, rsi
0x180012c13  xor     r8d, r8d
0x180012c16  lea     rdx, [rsp+180h+var_128]
0x180012c1b  mov     rcx, rdi
0x180012c1e  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180012c23  mov     rdx, rax
0x180012c26  lea     rcx, [rbp+80h+StringSid]
0x180012c2a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180012c2f  mov     rdx, [rsp+180h+var_110]
0x180012c34  cmp     rdx, 7
0x180012c38  jbe     short loc_180012C76
0x180012c3a  mov     rax, [rsp+180h+var_128]
0x180012c3f  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180012c47  cmp     rdx, 1000h
0x180012c4e  jb      short loc_180012C6E
0x180012c50  mov     rcx, [rax-8]
0x180012c54  sub     rax, rcx
0x180012c57  sub     rax, 8
0x180012c5b  cmp     rax, 1Fh
0x180012c5f  ja      short loc_180012C67
0x180012c61  add     rdx, 27h ; '''
0x180012c65  jmp     short loc_180012C71
0x180012c67  mov     ecx, 5
0x180012c6c  int     29h; Win8: RtlFailFast(ecx)
0x180012c6e  mov     rcx, rax; void *
0x180012c71  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c76  mov     [rsp+180h+var_118], rbx
0x180012c7b  mov     [rsp+180h+var_110], 7
0x180012c84  mov     word ptr [rsp+180h+var_128], bx
0x180012c89  lea     rax, [rsp+180h+hMem]
0x180012c8e  mov     [rsp+180h+Sid], rax
0x180012c93  mov     [rbp+80h+Sid+8], rbx
0x180012c97  mov     byte ptr [rbp+80h+var_F8], 1
0x180012c9b  lea     rcx, [rbp+80h+StringSid]
0x180012c9f  cmp     [rbp+80h+var_B0], 7
0x180012ca4  cmova   rcx, [rbp+80h+StringSid]; StringSid
0x180012ca9  lea     rdx, [rbp+80h+Sid+8]; Sid
0x180012cad  call    cs:__imp_ConvertStringSidToSidW
0x180012cb3  mov     r14d, eax
0x180012cb6  cmp     byte ptr [rbp+80h+var_F8], bl
0x180012cb9  jz      short loc_180012CD8
0x180012cbb  mov     rdx, [rsp+180h+Sid]
0x180012cc0  mov     r8, [rdx]
0x180012cc3  mov     rcx, [rbp+80h+Sid+8]
0x180012cc7  mov     [rdx], rcx
0x180012cca  test    r8, r8
0x180012ccd  jz      short loc_180012CD8
0x180012ccf  mov     rcx, r8; hMem
0x180012cd2  call    cs:__imp_LocalFree
0x180012cd8  test    r14d, r14d
0x180012cdb  jnz     loc_180012DCB
0x180012ce1  call    cs:__imp_GetLastError
0x180012ce7  mov     edi, eax
0x180012ce9  test    eax, eax
0x180012ceb  jle     short loc_180012CF6
0x180012ced  movzx   edi, ax
0x180012cf0  or      edi, 80070000h
0x180012cf6  mov     eax, cs:dword_180122070
0x180012cfc  cmp     eax, 2
0x180012cff  jbe     loc_180012DA5
0x180012d05  mov     dword ptr [rsp+180h+var_148], edi
0x180012d09  lea     rax, [rsp+180h+var_148]
0x180012d0e  mov     [rbp+80h+var_58], rax
0x180012d12  mov     [rbp+80h+var_50], 4
0x180012d1a  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180012d22  movzx   eax, cs:word_180107ADC
0x180012d29  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180012d2d  mov     [rsp+180h+EventDescriptor.Keyword], rbx
0x180012d32  mov     rax, cs:off_180122078
0x180012d39  mov     [rbp+80h+var_78.Ptr], rax
0x180012d3d  movzx   eax, word ptr [rax]
0x180012d40  mov     [rbp+80h+var_78.Size], eax
0x180012d43  mov     dword ptr [rbp+80h+var_78.0Ch], 2
0x180012d4a  lea     rax, word_180107AE6
0x180012d51  mov     [rbp+80h+var_68], rax
0x180012d55  mov     [rbp+80h+var_60], 2Bh ; '+'
0x180012d5c  mov     [rbp+80h+var_5C], 1
0x180012d63  lea     rax, _TraceLoggingMetadataEnd
0x180012d6a  lea     rcx, _TraceLoggingMetadata
0x180012d71  sub     eax, ecx
0x180012d73  mov     dword ptr [rsp+180h+var_150], eax
0x180012d77  mov     eax, dword ptr [rsp+180h+var_150]
0x180012d7b  lea     rax, [rbp+80h+var_78]
0x180012d7f  mov     [rsp+180h+UserData], rax; UserData
0x180012d84  mov     [rsp+180h+UserDataCount], 3; UserDataCount
0x180012d8c  xor     r9d, r9d; RelatedActivityId
0x180012d8f  xor     r8d, r8d; ActivityId
0x180012d92  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x180012d97  mov     rcx, cs:RegHandle; RegHandle
0x180012d9e  call    cs:__imp_EventWriteTransfer
0x180012da4  nop
0x180012da5  mov     rcx, [rsp+180h+hMem]; hMem
0x180012daa  mov     [rsp+180h+hMem], rbx
0x180012daf  test    rcx, rcx
0x180012db2  jz      short loc_180012DBB
0x180012db4  call    cs:__imp_LocalFree
0x180012dba  nop
0x180012dbb  lea     rcx, [rbp+80h+StringSid]
0x180012dbf  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180012dc4  mov     eax, edi
0x180012dc6  jmp     loc_1800136E5
0x180012dcb  mov     rcx, [rsp+180h+hMem]; pSid
0x180012dd0  call    cs:__imp_GetLengthSid
0x180012dd6  mov     r15d, eax
0x180012dd9  inc     rsi
0x180012ddc  cmp     rsi, [rdi+10h]
0x180012de0  jb      loc_180012F05
0x180012de6  mov     eax, cs:dword_180122070
0x180012dec  cmp     eax, 2
0x180012def  jbe     loc_180012E99
0x180012df5  mov     dword ptr [rsp+180h+var_148], 80070057h
0x180012dfd  lea     rax, [rsp+180h+var_148]
0x180012e02  mov     [rbp+80h+var_58], rax
0x180012e06  mov     [rbp+80h+var_50], 4
0x180012e0e  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180012e16  movzx   eax, cs:word_180107B13
0x180012e1d  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180012e21  mov     [rsp+180h+EventDescriptor.Keyword], rbx
0x180012e26  mov     rax, cs:off_180122078
0x180012e2d  mov     [rbp+80h+var_78.Ptr], rax
0x180012e31  movzx   eax, word ptr [rax]
0x180012e34  mov     [rbp+80h+var_78.Size], eax
0x180012e37  mov     dword ptr [rbp+80h+var_78.0Ch], 2
0x180012e3e  lea     rax, byte_180107B1D
0x180012e45  mov     [rbp+80h+var_68], rax
0x180012e49  mov     [rbp+80h+var_60], 2Ch ; ','
0x180012e50  mov     [rbp+80h+var_5C], 1
0x180012e57  lea     rax, _TraceLoggingMetadataEnd
0x180012e5e  lea     rcx, _TraceLoggingMetadata
0x180012e65  sub     eax, ecx
0x180012e67  mov     dword ptr [rsp+180h+var_150], eax
0x180012e6b  mov     eax, dword ptr [rsp+180h+var_150]
0x180012e6f  lea     rax, [rbp+80h+var_78]
0x180012e73  mov     [rsp+180h+UserData], rax; UserData
0x180012e78  mov     [rsp+180h+UserDataCount], 3; UserDataCount
0x180012e80  xor     r9d, r9d; RelatedActivityId
0x180012e83  xor     r8d, r8d; ActivityId
0x180012e86  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x180012e8b  mov     rcx, cs:RegHandle; RegHandle
0x180012e92  call    cs:__imp_EventWriteTransfer
0x180012e98  nop
0x180012e99  mov     rcx, [rsp+180h+hMem]; hMem
0x180012e9e  mov     [rsp+180h+hMem], rbx
0x180012ea3  test    rcx, rcx
0x180012ea6  jz      short loc_180012EAF
0x180012ea8  call    cs:__imp_LocalFree
0x180012eae  nop
0x180012eaf  mov     rdx, [rbp+80h+var_B0]
0x180012eb3  cmp     rdx, 7
0x180012eb7  jbe     loc_1800136E0
0x180012ebd  mov     rax, [rbp+80h+StringSid]
0x180012ec1  lea     rdx, ds:2[rdx*2]; unsigned __int64
0x180012ec9  cmp     rdx, 1000h
0x180012ed0  jb      short loc_180012EF8
0x180012ed2  mov     rcx, [rax-8]; void *
0x180012ed6  sub     rax, rcx
0x180012ed9  sub     rax, 8
0x180012edd  cmp     rax, 1Fh
0x180012ee1  ja      short loc_180012EF1
0x180012ee3  add     rdx, 27h ; '''; unsigned __int64
0x180012ee7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012eec  jmp     loc_1800136E0
0x180012ef1  mov     ecx, 5
0x180012ef6  int     29h; Win8: RtlFailFast(ecx)
0x180012ef8  mov     rcx, rax; void *
0x180012efb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012f00  jmp     loc_1800136E0
0x180012f05  mov     r8, rsi
0x180012f08  mov     rcx, rdi
0x180012f0b  call    ?find_first_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_first_of(ushort,unsigned __int64)
0x180012f10  mov     r14, rax
0x180012f13  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012f17  jnz     loc_180012FD4
0x180012f1d  mov     eax, cs:dword_180122070
0x180012f23  cmp     eax, 2
0x180012f26  jbe     loc_18001353E
0x180012f2c  mov     dword ptr [rsp+180h+var_148], 80070057h
0x180012f34  lea     rax, [rsp+180h+var_148]
0x180012f39  mov     [rbp+80h+var_58], rax
0x180012f3d  mov     [rbp+80h+var_50], 4
0x180012f45  mov     dword ptr [rsp+180h+EventDescriptor.Id], 0B000000h
0x180012f4d  movzx   eax, cs:word_180107AA4
0x180012f54  mov     dword ptr [rsp+180h+EventDescriptor.Level], eax
0x180012f58  mov     [rsp+180h+EventDescriptor.Keyword], rbx
0x180012f5d  mov     rax, cs:off_180122078
0x180012f64  mov     [rbp+80h+var_78.Ptr], rax
0x180012f68  movzx   eax, word ptr [rax]
0x180012f6b  mov     [rbp+80h+var_78.Size], eax
0x180012f6e  mov     dword ptr [rbp+80h+var_78.0Ch], 2
0x180012f75  lea     rax, word_180107AAE
0x180012f7c  mov     [rbp+80h+var_68], rax
0x180012f80  mov     [rbp+80h+var_60], 2Ch ; ','
0x180012f87  mov     [rbp+80h+var_5C], 1
0x180012f8e  lea     rax, _TraceLoggingMetadataEnd
0x180012f95  lea     rcx, _TraceLoggingMetadata
0x180012f9c  sub     eax, ecx
0x180012f9e  mov     dword ptr [rsp+180h+var_150], eax
0x180012fa2  mov     eax, dword ptr [rsp+180h+var_150]
0x180012fa6  lea     rax, [rbp+80h+var_78]
0x180012faa  mov     [rsp+180h+UserData], rax; UserData
0x180012faf  mov     [rsp+180h+UserDataCount], 3; UserDataCount
0x180012fb7  xor     r9d, r9d; RelatedActivityId
0x180012fba  xor     r8d, r8d; ActivityId
0x180012fbd  lea     rdx, [rsp+180h+EventDescriptor]; EventDescriptor
0x180012fc2  mov     rcx, cs:RegHandle; RegHandle
0x180012fc9  call    cs:__imp_EventWriteTransfer
0x180012fcf  jmp     loc_18001353E
0x180012fd4  xorps   xmm0, xmm0
0x180012fd7  movups  xmmword ptr [rbp+80h+StringUuid], xmm0
0x180012fdb  mov     [rbp+80h+var_D8], rbx
0x180012fdf  mov     [rbp+80h+var_D0], 7
0x180012fe7  mov     word ptr [rbp+80h+StringUuid], bx
0x180012feb  movups  xmmword ptr [rbp+80h+Uuid.Data1], xmm0
0x180012fef  cmp     r14, rsi
0x180012ff2  jz      loc_180013130
0x180012ff8  mov     r9, r14
0x180012ffb  sub     r9, rsi
0x180012ffe  mov     r8, rsi
0x180013001  lea     rdx, [rsp+180h+var_128]
0x180013006  mov     rcx, rdi
  ... truncated ...
```
