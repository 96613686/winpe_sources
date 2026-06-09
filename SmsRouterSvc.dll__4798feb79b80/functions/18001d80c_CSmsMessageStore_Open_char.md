# CSmsMessageStore::Open(char *)

- ea: `0x18001d80c`
- end: `0x18001e847`
- name: `?Open@CSmsMessageStore@@QEAAJPEAD@Z`
- size: `4155`
- prototype: `__int64 __fastcall(CSmsMessageStore *__hidden this, char *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fd94`

## callees

- `0x180003a60`
- `0x180003a90`
- `0x18000498c`
- `0x180004998`
- `0x18000659c`
- `0x1800069f0`
- `0x18000d388`
- `0x18000db54`
- `0x180018fe4`
- `0x180019520`
- `0x180019724`
- `0x18001993c`
- `0x180019b74`
- `0x18001a30c`
- `0x18001ad04`
- `0x18001ae24`
- `0x18001c304`
- `0x18001d80c`
- `0x18001e850`
- `0x1800216e4`
- `0x180021778`
- `0x180023498`
- `0x1800237f4`
- `0x180023900`
- `0x180023d9c`
- `0x180024094`
- `0x180024600`
- `0x180024674`
- `0x1800256e4`
- `0x180051420`
- `0x180051628`
- `0x18006b3d8`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e46a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e46a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d91c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001da8b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001d91c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001da8b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d9ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d9ce`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d8d3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001d8d3`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001d9c1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001d9c1`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18001d98a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x18001d98a`

## string_xrefs

- `0x18001d88e`: `SmsInterceptStore.db`
- `0x18001d8a3`: `SmsInterceptStore.db`
- `0x18001d961`: `Failed to delete directory %S`
- `0x18001d922`: `CSmsMessageStore::Open`
- `0x18001db98`: `CSmsMessageStore::Open`
- `0x18001dc61`: `CSmsMessageStore::Open`
- `0x18001dc9d`: `CSmsMessageStore::Open`
- `0x18001de5d`: `CSmsMessageStore::Open`
- `0x18001df08`: `CSmsMessageStore::Open`
- `0x18001dfcf`: `CSmsMessageStore::Open`
- `0x18001e170`: `CSmsMessageStore::Open`
- `0x18001e215`: `CSmsMessageStore::Open`
- `0x18001e2dc`: `CSmsMessageStore::Open`
- `0x18001e592`: `CSmsMessageStore::Open`
- `0x18001e641`: `CSmsMessageStore::Open`
- `0x18001e783`: `CSmsMessageStore::Open`
- `0x18001e774`: `Failed to create directory %S`
- `0x18001db89`: `OpenDatabase %s\%s`
- `0x18001dc55`: `OpenDatabase %s\%s succeeded`
- `0x18001def9`: `m_Database.Messages.Move`
- `0x18001e206`: `m_Database.Process.Move`
- `0x18001e632`: `m_Database.Delivery.Move`
- `0x18001d8cc`: `%ProgramData%\Microsoft\SmsRouter\MessageStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSmsMessageStore::Open(CSmsMessageStore *this, char *a2)
{
  char *v3; // rsi
  __int64 v4; // r8
  const char *v5; // rdi
  char *v6; // rbx
  DWORD v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  int v10; // ebx
  bool v11; // cc
  __int64 v12; // r8
  __int128 *v13; // r8
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // r15d
  int DirectoryDeepNoThrow; // ebx
  const char *v17; // r8
  const char *v18; // rdx
  int v19; // eax
  __int64 v20; // rcx
  const char *v21; // rcx
  const char *v22; // rax
  void (__fastcall ***v23)(_QWORD, __int64); // rax
  const char *v24; // r9
  unsigned int v25; // r9d
  int v26; // eax
  void (__fastcall ***v27)(_QWORD, __int64); // rax
  _QWORD *v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  unsigned int v31; // r8d
  int v32; // eax
  _QWORD *v33; // rax
  int CurrentRecord; // eax
  const char *v35; // rdx
  void (__fastcall ***v36)(_QWORD, __int64); // rax
  void (__fastcall ***v37)(_QWORD, __int64); // rax
  unsigned int v38; // r9d
  int v39; // eax
  void (__fastcall ***v40)(_QWORD, __int64); // rax
  _QWORD *v41; // rax
  unsigned int v42; // r8d
  __int64 v43; // rax
  int v44; // eax
  _QWORD *v45; // rax
  int v46; // eax
  const char *v47; // rdx
  void (__fastcall ***v48)(_QWORD, __int64); // rax
  void (__fastcall ***v49)(_QWORD, __int64); // rax
  unsigned int v50; // r9d
  int v51; // eax
  void (__fastcall ***v52)(_QWORD, __int64); // rax
  _QWORD *v53; // rax
  const char *v54; // rdx
  const OLECHAR *v55; // r9
  void *v56; // r12
  unsigned __int64 v57; // rdx
  void **v58; // rdi
  __int64 v59; // rbx
  unsigned int v60; // r8d
  _QWORD *v61; // rax
  __int64 v62; // rax
  int v63; // eax
  _QWORD *v64; // rax
  void (__fastcall ***v65)(_QWORD, __int64); // rax
  void (__fastcall ***v66)(_QWORD, __int64); // rax
  void (__fastcall ***v67)(_QWORD, __int64); // rax
  void (__fastcall ***v69)(_QWORD, __int64); // rax
  unsigned __int8 v70[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *i; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v72; // [rsp+50h] [rbp-B0h]
  int Data; // [rsp+58h] [rbp-A8h] BYREF
  void *Src; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v77[4]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v78[16]; // [rsp+88h] [rbp-78h] BYREF
  void **v79; // [rsp+98h] [rbp-68h]
  char *v80; // [rsp+A0h] [rbp-60h]
  _BYTE v81[16]; // [rsp+A8h] [rbp-58h] BYREF
  JET_PCSTR szParam[3]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v83; // [rsp+D0h] [rbp-30h]
  unsigned __int64 v84; // [rsp+D8h] [rbp-28h] BYREF
  void *v85[2]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v86; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v87; // [rsp+F8h] [rbp-8h]
  __int128 v88; // [rsp+100h] [rbp+0h] BYREF
  __int128 v89; // [rsp+110h] [rbp+10h]
  _QWORD v90[3]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v91; // [rsp+138h] [rbp+38h]
  _BYTE v92[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v93[64]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR Dst[264]; // [rsp+1A0h] [rbp+A0h] BYREF

  memset_0(Dst, 0, 0x208u);
  v79 = &Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable';
  v3 = (char *)this + 8;
  v80 = (char *)this + 8;
  (**((void (__fastcall ***)(char *))this + 1))((char *)this + 8);
  v5 = (char *)this + 56;
  if ( *((_QWORD *)this + 10) < 0x14u )
  {
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
      (char *)this + 56,
      20,
      v4,
      "SmsInterceptStore.db");
  }
  else
  {
    v6 = *(char **)v5;
    *((_QWORD *)this + 9) = 20;
    memmove_0(v6, "SmsInterceptStore.db", 0x14u);
    v6[20] = 0;
  }
  Data = 0;
  pcbData = 4;
  v7 = ExpandEnvironmentStringsW(L"%ProgramData%\\Microsoft\\SmsRouter\\MessageStore", Dst, 0x104u);
  v8 = v7 - 1;
  if ( (unsigned int)v8 > 0x103 )
  {
    MicrosoftTelemetryAssertTriggeredArgs(v8, v7, 0);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
    return 2147549183LL;
  }
  RegGetValueW(g_SmsRouterKey, L"MessageStore", L"Version", 0x10u, 0, &Data, &pcbData);
  if ( Data != 1 )
  {
    phkResult = 0;
    v9 = wil::RemoveDirectoryRecursiveNoThrow(Dst, 0, -1);
    if ( v9 < 0 )
      LogSmsRouterError("CSmsMessageStore::Open", 0x45u, v9, "Failed to delete directory %S", Dst);
    v10 = RegCreateKeyW(g_SmsRouterKey, L"MessageStore", &phkResult);
    if ( v10 )
    {
      v11 = v10 < 0;
    }
    else
    {
      Data = 1;
      pcbData = 4;
      v10 = RegSetKeyValueW(phkResult, 0, L"Version", 4u, &Data, 4u);
      RegCloseKey(phkResult);
      phkResult = 0;
      v11 = v10 <= 0;
      if ( !v10 )
      {
        LogSmsRouterInfo(
          "CSmsMessageStore::Open",
          0x61u,
          "Database Version %S\\%S = %d succeeded",
          L"MessageStore",
          L"Version",
          1);
        goto LABEL_15;
      }
    }
    if ( !v11 )
      v10 = (unsigned __int16)v10 | 0x80070000;
    LogSmsRouterError(
      "CSmsMessageStore::Open",
      0x56u,
      v10,
      "Database Version %S\\%S = %d failed",
      L"MessageStore",
      L"Version",
      1);
  }
LABEL_15:
  Data = 0;
  pcbData = 4;
  RegGetValueW(g_SmsRouterKey, L"MessageStore", L"MaximumMessages", 0x10u, 0, &Data, &pcbData);
  if ( Data )
    *((_DWORD *)this + 22) = Data;
  v88 = 0;
  v89 = 0;
  v12 = -1;
  do
    ++v12;
  while ( Dst[v12] );
  std::wstring::_Construct<1,unsigned short const *>(&v88, Dst);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v90);
  v13 = &v88;
  if ( *((_QWORD *)&v89 + 1) > 7u )
    v13 = (__int128 *)v88;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
    v90,
    szParam,
    v13,
    (char *)v13 + 2 * v89);
  v15 = 0;
  while ( 1 )
  {
    DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)Dst, v14);
    if ( DirectoryDeepNoThrow < 0 )
    {
      LogSmsRouterError("CSmsMessageStore::Open", 0x79u, DirectoryDeepNoThrow, "Failed to create directory %S", Dst);
      std::string::~string(szParam);
      v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v93);
      std::string::~string(v92);
      if ( v91 )
      {
        v69 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v69 )
          (**v69)(v69, 1);
      }
LABEL_119:
      std::wstring::~wstring(&v88);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
      return (unsigned int)DirectoryDeepNoThrow;
    }
    if ( *((_QWORD *)this + 10) <= 0xFu )
      v17 = (char *)this + 56;
    else
      v17 = *(const char **)v5;
    v18 = (const char *)szParam;
    if ( v83 > 0xF )
      v18 = szParam[0];
    v19 = CSmsJetDB::OpenDatabase(*((CSmsJetDB **)this + 12), v18, v17, (struct TableDefinition *)qword_18008D760, 3u);
    DirectoryDeepNoThrow = v19;
    if ( v19 >= 0 )
      break;
    MicrosoftTelemetryAssertTriggeredArgs(v20, (unsigned int)v19, v15);
    if ( *((_QWORD *)this + 10) <= 0xFu )
      v21 = (char *)this + 56;
    else
      v21 = *(const char **)v5;
    v22 = (const char *)szParam;
    if ( v83 > 0xF )
      v22 = szParam[0];
    LogSmsRouterError("CSmsMessageStore::Open", 0x80u, DirectoryDeepNoThrow, "OpenDatabase %s\\%s", v22, v21);
    wil::RemoveDirectoryRecursiveNoThrow(Dst, 0, -1);
    if ( (int)++v15 >= 2 )
    {
      std::string::~string(szParam);
      v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v93);
      std::string::~string(v92);
      if ( v91 )
      {
        v23 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v23 )
          (**v23)(v23, 1);
      }
      goto LABEL_119;
    }
  }
  if ( *((_QWORD *)this + 10) > 0xFu )
    v5 = *(const char **)v5;
  v24 = (const char *)szParam;
  if ( v83 > 0xF )
    v24 = szParam[0];
  LogSmsRouterInfo("CSmsMessageStore::Open", 0x8Fu, "OpenDatabase %s\\%s succeeded", v24, v5);
  v26 = CSmsJetDB::SetCurrentIndex(*((CSmsJetDB **)this + 12), "Messages", "MessageId", v25);
  DirectoryDeepNoThrow = v26;
  if ( v26 < 0 )
  {
    LogSmsRouterError("CSmsMessageStore::Open", 0x93u, v26, "m_Database.Messages.SetCurrentIndex");
    std::string::~string(szParam);
    v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v93);
    std::string::~string(v92);
    if ( v91 )
    {
      v27 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v27 )
        (**v27)(v27, 1);
    }
    goto LABEL_119;
  }
  v72 = 0;
  v28 = operator new(0x60u);
  *v28 = v28;
  v28[1] = v28;
  v28[2] = v28;
  *((_WORD *)v28 + 12) = 257;
  for ( i = v28; ; i = v33 )
  {
    LODWORD(phkResult) = 0;
    v77[0] = 0;
    Src = 0;
    CurrentRecord = CSmsJetDB::GetCurrentRecord(*((CSmsJetDB **)this + 12), "Messages", (struct SmsJetDBRecord *)&i);
    DirectoryDeepNoThrow = CurrentRecord;
    if ( CurrentRecord < 0 )
    {
      if ( CurrentRecord == -1906440637 )
        goto LABEL_62;
      LogSmsRouterError("CSmsMessageStore::Open", 0xA5u, CurrentRecord, "m_Database.Messages.GetCurrentRecord");
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
      std::string::~string(szParam);
      v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v93);
      std::string::~string(v92);
      if ( v91 )
      {
        v36 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v36 )
          (**v36)(v36, 1);
      }
LABEL_66:
      std::wstring::~wstring(&v88);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
      return (unsigned int)DirectoryDeepNoThrow;
    }
    SmsJetDBRecord::GetUINT64((SmsJetDBRecord *)&i, v35, (unsigned __int64 *)&Src);
    SmsJetDBRecord::GetDword((SmsJetDBRecord *)&i, "MessageType", v77);
    SmsJetDBRecord::GetDword((SmsJetDBRecord *)&i, "Flags", (unsigned int *)&phkResult);
    v29 = std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::_Try_emplace<unsigned __int64 const &,>(
            (char *)this + 112,
            v81,
            &Src);
    *(_DWORD *)(*(_QWORD *)v29 + 28LL) = v77[0];
    v30 = std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageData,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageData>>,0>>::_Try_emplace<unsigned __int64 const &,>(
            (char *)this + 112,
            v78,
            &Src);
    *(_DWORD *)(*(_QWORD *)v30 + 24LL) = (_DWORD)phkResult;
    v32 = CSmsJetDB::Move(*((CSmsJetDB **)this + 12), "Messages", v31);
    DirectoryDeepNoThrow = v32;
    if ( v32 < 0 )
      break;
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
    i = 0;
    v72 = 0;
    v33 = operator new(0x60u);
    *v33 = v33;
    v33[1] = v33;
    v33[2] = v33;
    *((_WORD *)v33 + 12) = 257;
  }
  if ( v32 != -1906440637 )
  {
    LogSmsRouterError("CSmsMessageStore::Open", 0xB5u, v32, "m_Database.Messages.Move");
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
    std::string::~string(szParam);
    v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v93);
    std::string::~string(v92);
    if ( v91 )
    {
      v37 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v37 )
        (**v37)(v37, 1);
    }
    goto LABEL_66;
  }
LABEL_62:
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
  v39 = CSmsJetDB::SetCurrentIndex(*((CSmsJetDB **)this + 12), "Process", "MessageId", v38);
  DirectoryDeepNoThrow = v39;
  if ( v39 < 0 )
  {
    LogSmsRouterError("CSmsMessageStore::Open", 0xBCu, v39, "m_Database.Process.SetCurrentIndex");
    std::string::~string(szParam);
    v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v93);
    std::string::~string(v92);
    if ( v91 )
    {
      v40 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v40 )
        (**v40)(v40, 1);
    }
    goto LABEL_66;
  }
  i = 0;
  v72 = 0;
  v41 = operator new(0x60u);
  *v41 = v41;
  v41[1] = v41;
  v41[2] = v41;
  *((_WORD *)v41 + 12) = 257;
  for ( i = v41; ; i = v45 )
  {
    v70[0] = 0;
    Src = 0;
    v46 = CSmsJetDB::GetCurrentRecord(*((CSmsJetDB **)this + 12), "Process", (struct SmsJetDBRecord *)&i);
    DirectoryDeepNoThrow = v46;
    if ( v46 < 0 )
    {
      if ( v46 == -1906440637 )
        goto LABEL_83;
      LogSmsRouterError("CSmsMessageStore::Open", 0xCDu, v46, "m_Database.Process.GetCurrentRecord");
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
      std::string::~string(szParam);
      v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v93);
      std::string::~string(v92);
      if ( v91 )
      {
        v48 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v48 )
          (**v48)(v48, 1);
      }
LABEL_111:
      std::wstring::~wstring(&v88);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
      return (unsigned int)DirectoryDeepNoThrow;
    }
    SmsJetDBRecord::GetUINT64((SmsJetDBRecord *)&i, v47, (unsigned __int64 *)&Src);
    SmsJetDBRecord::GetByte((SmsJetDBRecord *)&i, "ProcessStatus", v70);
    if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                      (char *)this + 112,
                      v77,
                      &Src) != *((_QWORD *)this + 15) )
    {
      v43 = std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::_Try_emplace<unsigned __int64 const &,>(
              (char *)this + 176,
              v78,
              &Src);
      *(_DWORD *)(*(_QWORD *)v43 + 56LL) = v70[0];
    }
    v44 = CSmsJetDB::Move(*((CSmsJetDB **)this + 12), "Process", v42);
    DirectoryDeepNoThrow = v44;
    if ( v44 < 0 )
      break;
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
    i = 0;
    v72 = 0;
    v45 = operator new(0x60u);
    *v45 = v45;
    v45[1] = v45;
    v45[2] = v45;
    *((_WORD *)v45 + 12) = 257;
  }
  if ( v44 != -1906440637 )
  {
    LogSmsRouterError("CSmsMessageStore::Open", 0xDFu, v44, "m_Database.Process.Move");
    std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
    std::string::~string(szParam);
    v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v93);
    std::string::~string(v92);
    if ( v91 )
    {
      v49 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v49 )
        (**v49)(v49, 1);
    }
    goto LABEL_111;
  }
LABEL_83:
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
  v51 = CSmsJetDB::SetCurrentIndex(*((CSmsJetDB **)this + 12), "Delivery", "RegistrationIdAndMessageId", v50);
  DirectoryDeepNoThrow = v51;
  if ( v51 < 0 )
  {
    LogSmsRouterError("CSmsMessageStore::Open", 0xE6u, v51, "m_Database.Delivery.SetCurrentIndex");
    std::string::~string(szParam);
    v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v93);
    std::string::~string(v92);
    if ( v91 )
    {
      v52 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
      if ( v52 )
        (**v52)(v52, 1);
    }
    goto LABEL_111;
  }
  i = 0;
  v72 = 0;
  v53 = operator new(0x60u);
  *v53 = v53;
  v53[1] = v53;
  v53[2] = v53;
  *((_WORD *)v53 + 12) = 257;
  i = v53;
  v84 = 0;
  *(_OWORD *)v85 = 0;
  v86 = 0;
  v87 = 7;
  LOWORD(v85[0]) = 0;
  v70[0] = 0;
  Src = 0;
  DirectoryDeepNoThrow = CSmsJetDB::GetCurrentRecord(
                           *((CSmsJetDB **)this + 12),
                           "Delivery",
                           (struct SmsJetDBRecord *)&i);
  if ( DirectoryDeepNoThrow < 0 )
  {
LABEL_102:
    if ( DirectoryDeepNoThrow != -1906440637 )
    {
      LogSmsRouterError("CSmsMessageStore::Open", 0xF8u, DirectoryDeepNoThrow, "m_Database.Delivery.GetCurrentRecord");
      std::wstring::~wstring(v85);
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
      std::string::~string(szParam);
      v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v93);
      std::string::~string(v92);
      if ( v91 )
      {
        v65 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v65 )
          (**v65)(v65, 1);
      }
      goto LABEL_111;
    }
  }
  else
  {
    while ( 1 )
    {
      SmsJetDBRecord::GetUINT64((SmsJetDBRecord *)&i, v54, &v84);
      SmsJetDBRecord::GetString((SmsJetDBRecord *)&i, "RegistrationId", (unsigned __int16 **)&Src);
      SmsJetDBRecord::GetByte((SmsJetDBRecord *)&i, "DeliveryType", v70);
      v55 = &LocaleName;
      v56 = Src;
      if ( Src )
        v55 = (const OLECHAR *)Src;
      v57 = -1;
      do
        ++v57;
      while ( v55[v57] );
      if ( v57 > v87 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v85);
      }
      else
      {
        v58 = v85;
        if ( v87 > 7 )
          v58 = (void **)v85[0];
        v86 = v57;
        v59 = 2 * v57;
        memmove_0(v58, v55, 2 * v57);
        *(_WORD *)((char *)v58 + v59) = 0;
      }
      LocalFree(v56);
      if ( *(_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,MessageProcessingState,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,MessageProcessingState>>,0>>::find(
                        (char *)this + 112,
                        &phkResult,
                        &v84) != *((_QWORD *)this + 15) )
      {
        v61 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<unsigned __int64,std::set<std::wstring>,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<std::pair<unsigned __int64 const,std::set<std::wstring>>>,0>>::_Try_emplace<unsigned __int64 const &,>(
                          (char *)this + 240,
                          v78,
                          &v84);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
          *v61 + 24LL,
          v81,
          v85);
        v62 = std::_Hash<stdext::_Hmap_traits<MessageDeliveryPK,enum SmsMessageDeliveryAction,MessageDeliveryPKHashCompare,std::allocator<std::pair<MessageDeliveryPK const,enum SmsMessageDeliveryAction>>,0>>::_Try_emplace<MessageDeliveryPK const &,>(
                (char *)this + 304,
                v77,
                &v84);
        *(_DWORD *)(*(_QWORD *)v62 + 56LL) = v70[0];
      }
      v63 = CSmsJetDB::Move(*((CSmsJetDB **)this + 12), "Delivery", v60);
      DirectoryDeepNoThrow = v63;
      if ( v63 < 0 )
        break;
      std::wstring::~wstring(v85);
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
      i = 0;
      v72 = 0;
      v64 = operator new(0x60u);
      *v64 = v64;
      v64[1] = v64;
      v64[2] = v64;
      *((_WORD *)v64 + 12) = 257;
      i = v64;
      v84 = 0;
      *(_OWORD *)v85 = 0;
      v86 = 0;
      v87 = 7;
      LOWORD(v85[0]) = 0;
      v70[0] = 0;
      Src = 0;
      DirectoryDeepNoThrow = CSmsJetDB::GetCurrentRecord(
                               *((CSmsJetDB **)this + 12),
                               "Delivery",
                               (struct SmsJetDBRecord *)&i);
      if ( DirectoryDeepNoThrow < 0 )
        goto LABEL_102;
    }
    if ( v63 != -1906440637 )
    {
      LogSmsRouterError("CSmsMessageStore::Open", 0x10Eu, v63, "m_Database.Delivery.Move");
      std::wstring::~wstring(v85);
      std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
      std::string::~string(szParam);
      v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v93);
      std::string::~string(v92);
      if ( v91 )
      {
        v66 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
        if ( v66 )
          (**v66)(v66, 1);
      }
      goto LABEL_111;
    }
  }
  std::wstring::~wstring(v85);
  std::_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>::~_Tree<std::_Tmap_traits<std::string,SmsJetDBValue,std::less<std::string>,std::allocator<std::pair<std::string const,SmsJetDBValue>>,0>>(&i);
  std::string::~string(szParam);
  v90[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  std::wstring::~wstring(v93);
  std::string::~string(v92);
  if ( v91 )
  {
    v67 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
    if ( v67 )
      (**v67)(v67, 1);
  }
  std::wstring::~wstring(&v88);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 8LL))((char *)this + 8);
  return 0;
}

```

## disassembly

```asm
0x18001d80c  push    rbp
0x18001d80e  push    rbx
0x18001d80f  push    rsi
0x18001d810  push    rdi
0x18001d811  push    r12
0x18001d813  push    r13
0x18001d815  push    r14
0x18001d817  push    r15
0x18001d819  lea     rbp, [rsp-2C8h]
0x18001d821  sub     rsp, 3C8h
0x18001d828  mov     rax, cs:__security_cookie
0x18001d82f  xor     rax, rsp
0x18001d832  mov     [rbp+300h+var_50], rax
0x18001d839  mov     r14, rcx
0x18001d83c  xor     r12d, r12d
0x18001d83f  xor     edx, edx; Val
0x18001d841  mov     r8d, 208h; Size
0x18001d847  lea     rcx, [rbp+300h+Dst]; void *
0x18001d84e  call    memset_0
0x18001d853  lea     rax, ??_7?$lock_guard@Vrecursive_mutex@Common@Sms@Windows@@@Common@Sms@Windows@@6B@; const Windows::Sms::Common::lock_guard<Windows::Sms::Common::recursive_mutex>::`vftable'
0x18001d85a  mov     [rbp+300h+var_368], rax
0x18001d85e  lea     rsi, [r14+8]
0x18001d862  mov     [rbp+300h+var_360], rsi
0x18001d866  mov     rax, [rsi]
0x18001d869  mov     rcx, rsi
0x18001d86c  mov     rax, [rax]
0x18001d86f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d874  nop
0x18001d875  lea     rdi, [r14+38h]
0x18001d879  lea     edx, [r12+14h]
0x18001d87e  cmp     [rdi+18h], rdx
0x18001d882  jb      short loc_18001D8A3
0x18001d884  mov     rbx, [rdi]
0x18001d887  mov     [rdi+10h], rdx
0x18001d88b  mov     r8d, edx; Size
0x18001d88e  lea     rdx, aSmsinterceptst; "SmsInterceptStore.db"
0x18001d895  mov     rcx, rbx; void *
0x18001d898  call    memmove_0
0x18001d89d  mov     [rbx+14h], r12b
0x18001d8a1  jmp     short loc_18001D8B2
0x18001d8a3  lea     r9, aSmsinterceptst; "SmsInterceptStore.db"
0x18001d8aa  mov     rcx, rdi
0x18001d8ad  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18001d8b2  mov     [rsp+400h+Data], r12d
0x18001d8b7  mov     [rsp+400h+var_390], 4
0x18001d8bf  mov     r8d, 104h; nSize
0x18001d8c5  lea     rdx, [rbp+300h+Dst]; lpDst
0x18001d8cc  lea     rcx, Src; "%ProgramData%\\Microsoft\\SmsRouter\\Me"...
0x18001d8d3  call    cs:__imp_ExpandEnvironmentStringsW
0x18001d8d9  lea     ecx, [rax-1]
0x18001d8dc  cmp     ecx, 103h
0x18001d8e2  ja      loc_18001E804
0x18001d8e8  lea     rax, [rsp+400h+var_390]
0x18001d8ed  mov     [rsp+400h+pcbData], rax; pcbData
0x18001d8f2  lea     rax, [rsp+400h+Data]
0x18001d8f7  mov     [rsp+400h+pvData], rax; pvData
0x18001d8fc  mov     [rsp+400h+pdwType], r12; pdwType
0x18001d901  mov     r9d, 10h; dwFlags
0x18001d907  lea     r8, aVersion; "Version"
0x18001d90e  lea     rdx, aMessagestore; "MessageStore"
0x18001d915  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hkey
0x18001d91c  call    cs:__imp_RegGetValueW
0x18001d922  lea     r15, aCsmsmessagesto_4; "CSmsMessageStore::Open"
0x18001d929  mov     r13d, 1
0x18001d92f  cmp     [rsp+400h+Data], r13d
0x18001d934  jz      loc_18001DA4A
0x18001d93a  mov     [rsp+400h+phkResult], r12
0x18001d93f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d943  xor     edx, edx
0x18001d945  lea     rcx, [rbp+300h+Dst]
0x18001d94c  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18001d951  test    eax, eax
0x18001d953  jns     short loc_18001D977
0x18001d955  lea     rcx, [rbp+300h+Dst]
0x18001d95c  mov     [rsp+400h+pdwType], rcx
0x18001d961  lea     r9, aFailedToDelete; "Failed to delete directory %S"
0x18001d968  mov     r8d, eax; int
0x18001d96b  lea     edx, [r13+44h]; unsigned int
0x18001d96f  mov     rcx, r15; char *
0x18001d972  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001d977  lea     r8, [rsp+400h+phkResult]; phkResult
0x18001d97c  lea     rdx, aMessagestore; "MessageStore"
0x18001d983  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hKey
0x18001d98a  call    cs:__imp_RegCreateKeyW
0x18001d990  mov     ebx, eax
0x18001d992  test    eax, eax
0x18001d994  jnz     short loc_18001DA09
0x18001d996  mov     [rsp+400h+Data], r13d
0x18001d99b  lea     ecx, [rax+4]
0x18001d99e  mov     [rsp+400h+var_390], ecx
0x18001d9a2  mov     dword ptr [rsp+400h+pvData], ecx; cbData
0x18001d9a6  lea     rax, [rsp+400h+Data]
0x18001d9ab  mov     [rsp+400h+pdwType], rax; lpData
0x18001d9b0  mov     r9d, ecx; dwType
0x18001d9b3  lea     r8, aVersion; "Version"
0x18001d9ba  xor     edx, edx; lpSubKey
0x18001d9bc  mov     rcx, [rsp+400h+phkResult]; hKey
0x18001d9c1  call    cs:__imp_RegSetKeyValueW
0x18001d9c7  mov     ebx, eax
0x18001d9c9  mov     rcx, [rsp+400h+phkResult]; hKey
0x18001d9ce  call    cs:__imp_RegCloseKey
0x18001d9d4  mov     [rsp+400h+phkResult], r12
0x18001d9d9  test    ebx, ebx
0x18001d9db  jnz     short loc_18001DA0B
0x18001d9dd  mov     dword ptr [rsp+400h+pvData], r13d
0x18001d9e2  lea     rax, aVersion; "Version"
0x18001d9e9  mov     [rsp+400h+pdwType], rax
0x18001d9ee  lea     r9, aMessagestore; "MessageStore"
0x18001d9f5  lea     r8, aDatabaseVersio; "Database Version %S\\%S = %d succeeded"
0x18001d9fc  lea     edx, [rbx+61h]; unsigned int
0x18001d9ff  mov     rcx, r15; char *
0x18001da02  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001da07  jmp     short loc_18001DA4A
0x18001da09  test    ebx, ebx
0x18001da0b  jle     short loc_18001DA16
0x18001da0d  movzx   ebx, bx
0x18001da10  or      ebx, 80070000h
0x18001da16  mov     dword ptr [rsp+400h+pcbData], r13d
0x18001da1b  lea     rax, aVersion; "Version"
0x18001da22  mov     [rsp+400h+pvData], rax
0x18001da27  lea     rax, aMessagestore; "MessageStore"
0x18001da2e  mov     [rsp+400h+pdwType], rax
0x18001da33  lea     r9, aDatabaseVersio_0; "Database Version %S\\%S = %d failed"
0x18001da3a  mov     r8d, ebx; int
0x18001da3d  mov     edx, 56h ; 'V'; unsigned int
0x18001da42  mov     rcx, r15; char *
0x18001da45  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001da4a  mov     [rsp+400h+Data], r12d
0x18001da4f  mov     [rsp+400h+var_390], 4
0x18001da57  lea     rax, [rsp+400h+var_390]
0x18001da5c  mov     [rsp+400h+pcbData], rax; pcbData
0x18001da61  lea     rax, [rsp+400h+Data]
0x18001da66  mov     [rsp+400h+pvData], rax; pvData
0x18001da6b  mov     [rsp+400h+pdwType], r12; pdwType
0x18001da70  mov     r9d, 10h; dwFlags
0x18001da76  lea     r8, aMaximummessage; "MaximumMessages"
0x18001da7d  lea     rdx, aMessagestore; "MessageStore"
0x18001da84  mov     rcx, cs:?g_SmsRouterKey@@3V?$__AutoHandle@PEAUHKEY__@@VRegkeyDeleter@Common@Sms@Windows@@@Common@Sms@Windows@@A; hkey
0x18001da8b  call    cs:__imp_RegGetValueW
0x18001da91  mov     eax, [rsp+400h+Data]
0x18001da95  test    eax, eax
0x18001da97  jz      short loc_18001DA9D
0x18001da99  mov     [r14+58h], eax
0x18001da9d  xorps   xmm0, xmm0
0x18001daa0  movups  [rbp+300h+var_300], xmm0
0x18001daa4  xorps   xmm1, xmm1
0x18001daa7  movdqu  [rbp+300h+var_2F0], xmm1
0x18001daac  lea     rax, [rbp+300h+Dst]
0x18001dab3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001dab7  inc     r8
0x18001daba  cmp     [rax+r8*2], r12w
0x18001dabf  jnz     short loc_18001DAB7
0x18001dac1  lea     rdx, [rbp+300h+Dst]
0x18001dac8  lea     rcx, [rbp+300h+var_300]
0x18001dacc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001dad1  nop
0x18001dad2  lea     rcx, [rbp+300h+var_2E0]
0x18001dad6  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18001dadb  nop
0x18001dadc  lea     r8, [rbp+300h+var_300]
0x18001dae0  cmp     qword ptr [rbp+300h+var_2F0+8], 7
0x18001dae5  cmova   r8, qword ptr [rbp+300h+var_300]
0x18001daea  mov     rax, qword ptr [rbp+300h+var_2F0]
0x18001daee  lea     r9, [r8+rax*2]
0x18001daf2  lea     rdx, [rbp+300h+szParam]
0x18001daf6  lea     rcx, [rbp+300h+var_2E0]
0x18001dafa  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x18001daff  nop
0x18001db00  mov     r15d, r12d
0x18001db03  lea     rcx, [rbp+300h+Dst]; this
0x18001db0a  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x18001db0f  mov     ebx, eax
0x18001db11  test    eax, eax
0x18001db13  js      loc_18001E768
0x18001db19  cmp     qword ptr [r14+50h], 0Fh
0x18001db1e  jbe     short loc_18001DB25
0x18001db20  mov     r8, [rdi]
0x18001db23  jmp     short loc_18001DB28
0x18001db25  mov     r8, rdi; char *
0x18001db28  lea     rdx, [rbp+300h+szParam]
0x18001db2c  cmp     [rbp+300h+var_330], 0Fh
0x18001db31  cmova   rdx, [rbp+300h+szParam]; szParam
0x18001db36  mov     dword ptr [rsp+400h+pdwType], 3; unsigned int
0x18001db3e  lea     r9, qword_18008D760; struct TableDefinition *
0x18001db45  mov     rcx, [r14+60h]; this
0x18001db49  call    ?OpenDatabase@CSmsJetDB@@QEAAJPEBD0PEAUTableDefinition@@K@Z; CSmsJetDB::OpenDatabase(char const *,char const *,TableDefinition *,ulong)
0x18001db4e  mov     ebx, eax
0x18001db50  test    eax, eax
0x18001db52  jns     loc_18001DC38
0x18001db58  mov     r8d, r15d
0x18001db5b  mov     edx, eax
0x18001db5d  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001db62  cmp     qword ptr [r14+50h], 0Fh
0x18001db67  jbe     short loc_18001DB6E
0x18001db69  mov     rcx, [rdi]
0x18001db6c  jmp     short loc_18001DB71
0x18001db6e  mov     rcx, rdi
0x18001db71  lea     rax, [rbp+300h+szParam]
0x18001db75  cmp     [rbp+300h+var_330], 0Fh
0x18001db7a  cmova   rax, [rbp+300h+szParam]
0x18001db7f  mov     [rsp+400h+pvData], rcx
0x18001db84  mov     [rsp+400h+pdwType], rax
0x18001db89  lea     r9, aOpendatabaseSS; "OpenDatabase %s\\%s"
0x18001db90  mov     r8d, ebx; int
0x18001db93  mov     edx, 80h; unsigned int
0x18001db98  lea     rcx, aCsmsmessagesto_4; "CSmsMessageStore::Open"
0x18001db9f  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001dba4  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001dba8  xor     edx, edx
0x18001dbaa  lea     rcx, [rbp+300h+Dst]
0x18001dbb1  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEBGW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(ushort const *,wil::RemoveDirectoryOptions,void *)
0x18001dbb6  add     r15d, r13d
0x18001dbb9  cmp     r15d, 2
0x18001dbbd  jl      loc_18001DB03
0x18001dbc3  lea     rcx, [rbp+300h+szParam]
0x18001dbc7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001dbcc  nop
0x18001dbcd  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18001dbd4  mov     [rbp+300h+var_2E0], rax
0x18001dbd8  lea     rcx, [rbp+300h+var_2A0]; void *
0x18001dbdc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dbe1  lea     rcx, [rbp+300h+var_2C0]
0x18001dbe5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001dbea  mov     rcx, [rbp+300h+var_2C8]
0x18001dbee  test    rcx, rcx
0x18001dbf1  jz      short loc_18001DC19
0x18001dbf3  mov     rax, [rcx]
0x18001dbf6  mov     rax, [rax+10h]
0x18001dbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbff  mov     r8, rax
0x18001dc02  test    rax, rax
0x18001dc05  jz      short loc_18001DC19
0x18001dc07  mov     rcx, [rax]
0x18001dc0a  mov     rax, [rcx]
0x18001dc0d  mov     edx, r13d
0x18001dc10  mov     rcx, r8
0x18001dc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc18  nop
0x18001dc19  lea     rcx, [rbp+300h+var_300]; void *
0x18001dc1d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dc22  nop
0x18001dc23  mov     rax, [rsi]
0x18001dc26  mov     rcx, rsi
0x18001dc29  mov     rax, [rax+8]
0x18001dc2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc32  nop
0x18001dc33  jmp     loc_18001E800
0x18001dc38  cmp     qword ptr [rdi+18h], 0Fh
0x18001dc3d  jbe     short loc_18001DC42
0x18001dc3f  mov     rdi, [rdi]
0x18001dc42  lea     r9, [rbp+300h+szParam]
0x18001dc46  cmp     [rbp+300h+var_330], 0Fh
0x18001dc4b  cmova   r9, [rbp+300h+szParam]
0x18001dc50  mov     [rsp+400h+pdwType], rdi
0x18001dc55  lea     r8, aOpendatabaseSS_0; "OpenDatabase %s\\%s succeeded"
0x18001dc5c  mov     edx, 8Fh; unsigned int
0x18001dc61  lea     rcx, aCsmsmessagesto_4; "CSmsMessageStore::Open"
0x18001dc68  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x18001dc6d  lea     r8, aMessageid_0; "MessageId"
0x18001dc74  lea     rdx, aMessages; "Messages"
0x18001dc7b  mov     rcx, [r14+60h]; this
0x18001dc7f  call    ?SetCurrentIndex@CSmsJetDB@@QEAAJPEBD0K@Z; CSmsJetDB::SetCurrentIndex(char const *,char const *,ulong)
0x18001dc84  mov     ebx, eax
0x18001dc86  test    eax, eax
0x18001dc88  jns     loc_18001DD1F
0x18001dc8e  lea     r9, aMDatabaseMessa; "m_Database.Messages.SetCurrentIndex"
0x18001dc95  mov     r8d, eax; int
0x18001dc98  mov     edx, 93h; unsigned int
0x18001dc9d  lea     rcx, aCsmsmessagesto_4; "CSmsMessageStore::Open"
0x18001dca4  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18001dca9  nop
0x18001dcaa  lea     rcx, [rbp+300h+szParam]
0x18001dcae  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001dcb3  nop
0x18001dcb4  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18001dcbb  mov     [rbp+300h+var_2E0], rax
0x18001dcbf  lea     rcx, [rbp+300h+var_2A0]; void *
0x18001dcc3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dcc8  lea     rcx, [rbp+300h+var_2C0]
0x18001dccc  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001dcd1  mov     rcx, [rbp+300h+var_2C8]
0x18001dcd5  test    rcx, rcx
0x18001dcd8  jz      short loc_18001DD00
0x18001dcda  mov     rax, [rcx]
0x18001dcdd  mov     rax, [rax+10h]
0x18001dce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dce6  mov     r8, rax
0x18001dce9  test    rax, rax
0x18001dcec  jz      short loc_18001DD00
0x18001dcee  mov     rcx, [rax]
0x18001dcf1  mov     rax, [rcx]
0x18001dcf4  mov     edx, r13d
0x18001dcf7  mov     rcx, r8
0x18001dcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcff  nop
0x18001dd00  lea     rcx, [rbp+300h+var_300]; void *
0x18001dd04  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001dd09  nop
0x18001dd0a  mov     rax, [rsi]
0x18001dd0d  mov     rcx, rsi
  ... truncated ...
```
