# WaasMedic::CScheduledTasksPlugin::LoadStaticTaskData(void)

- ea: `0x1800555cc`
- end: `0x180055b23`
- name: `?LoadStaticTaskData@CScheduledTasksPlugin@WaasMedic@@QEAAJXZ`
- size: `1367`
- prototype: `__int64 __fastcall(WaasMedic::CScheduledTasksPlugin *__hidden this)`
- caller_count: `2`
- callee_count: `20`
- tags: `reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180054fd0`
- `0x180055b30`

## callees

- `0x1800024a4`
- `0x180003bb0`
- `0x180003bd4`
- `0x180004708`
- `0x1800070cc`
- `0x180007590`
- `0x180016c9c`
- `0x180022210`
- `0x1800250e0`
- `0x18002543c`
- `0x180025828`
- `0x180029e14`
- `0x18002c040`
- `0x18002c8b4`
- `0x180036918`
- `0x180054758`
- `0x1800555cc`
- `0x18005c504`
- `0x18005f7cc`
- `0x18005f9bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005570b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005582d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055ace`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005570b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005582d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180055ace`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005581f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800558ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ac0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800556fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005581f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800558ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180055ac0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055afe`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180055afe`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005577f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18005577f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18005574b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800557b3`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18005574b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800557b3`

## string_xrefs

- `0x180055757`: `Error in PathCchCombine. hr = 0x%08x`
- `0x1800557c2`: `Error in PathCchCombine. hr = 0x%08x`
- `0x180055856`: `Error in initializing task helper library with path %ws`
- `0x1800558c4`: `Error in GetTaskURI.Incorrectly formatted XML?. hr = 0x%08x`
- `0x1800557ff`: `Error in LoadXMLFromFile for file: %s. hr = 0x%08x`
- `0x180055838`: `Microsoft\Windows\WindowsUpdate`
- `0x18005584f`: `Microsoft\Windows\WindowsUpdate`
- `0x180055ae4`: `Failed to load XML file: %s. hr = 0x%08x`
- `0x180055663`: `No Static task XML files found.`
- `0x180055623`: `%windir%\WaaS\Tasks`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall WaasMedic::CScheduledTasksPlugin::LoadStaticTaskData(
        WaasMedic::CScheduledTasksPlugin *this,
        __int64 a2,
        unsigned __int16 **a3)
{
  int v4; // eax
  int v5; // esi
  const struct _tlgProvider_t *v6; // rax
  int v7; // r9d
  HANDLE v8; // rax
  HRESULT v10; // eax
  HRESULT v11; // eax
  unsigned __int16 **v12; // r8
  int XMLFromFile; // eax
  unsigned __int16 *v14; // rbx
  HANDLE v15; // rax
  unsigned __int16 *v16; // r8
  unsigned __int16 **v17; // rax
  int v18; // ecx
  unsigned __int16 **v19; // rbx
  unsigned __int16 *v20; // r15
  int TaskURI; // eax
  unsigned __int16 *v22; // rdx
  __int64 v23; // r8
  __int64 last_of; // rax
  __int64 v25; // rbx
  __int64 v26; // r8
  __int64 v27; // r8
  __int128 *v28; // rdx
  unsigned __int64 v29; // rbx
  __int64 v30; // r8
  __int128 *v31; // rax
  __int64 v32; // r8
  __int64 v33; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v35; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hFindFile; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID ppv[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int128 v42; // [rsp+80h] [rbp-80h] BYREF
  __int128 v43; // [rsp+90h] [rbp-70h]
  _BYTE v44[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v45[32]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v46[2]; // [rsp+E0h] [rbp-20h] BYREF
  char v47; // [rsp+100h] [rbp+0h]
  int v48; // [rsp+101h] [rbp+1h]
  __int16 v49; // [rsp+105h] [rbp+5h]
  char v50; // [rsp+107h] [rbp+7h]
  _OWORD v51[2]; // [rsp+110h] [rbp+10h] BYREF
  _OWORD v52[2]; // [rsp+130h] [rbp+30h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+150h] [rbp+50h] BYREF
  WCHAR v54[264]; // [rsp+3A0h] [rbp+2A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+5B0h] [rbp+4B0h] BYREF

  v40 = 0;
  *(_OWORD *)ppv = 0;
  *((_BYTE *)this + 250) = 1;
  lpMem = 0;
  v4 = WaasMedic::SafeExpandEnvironmentString(L"%windir%\\WaaS\\Tasks", (const unsigned __int16 *)&lpMem, a3);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v10 = PathCchCombine(pszPathOut, 0x104u, (PCWSTR)lpMem, L"*");
    v5 = v10;
    if ( v10 < 0 )
    {
      LogLevelW(2u, L"Error in PathCchCombine. hr = 0x%08x", (unsigned int)v10);
      goto LABEL_3;
    }
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    hFindFile = FindFirstFileW(pszPathOut, &FindFileData);
    if ( hFindFile == (HANDLE)-1LL )
      goto LABEL_3;
    while ( (FindFileData.dwFileAttributes & 0x10) != 0 )
    {
      if ( v5 < 0 )
        goto LABEL_51;
LABEL_52:
      if ( !FindNextFileW(hFindFile, &FindFileData) )
        goto LABEL_3;
    }
    v11 = PathCchCombine(v54, 0x104u, (PCWSTR)lpMem, FindFileData.cFileName);
    v5 = v11;
    if ( v11 < 0 )
    {
      LogLevelW(2u, L"Error in PathCchCombine. hr = 0x%08x", (unsigned int)v11);
LABEL_51:
      LogLevelW(3u, L"Failed to load XML file: %s. hr = 0x%08x", v54, (unsigned int)v5);
      goto LABEL_52;
    }
    v35 = 0;
    XMLFromFile = WaasMedic::LoadXMLFromFile((WaasMedic *)v54, (const unsigned __int16 *)&v35, v12);
    v5 = XMLFromFile;
    if ( XMLFromFile >= 0 )
    {
      v5 = WaasMedic::TasksHelper::Initialize(ppv, (OLECHAR *)L"Microsoft\\Windows\\WindowsUpdate");
      if ( v5 >= 0 )
      {
        v36 = 0;
        v17 = (unsigned __int16 **)operator new(0x18u);
        v19 = v17;
        v36 = (__int64)v17;
        if ( v17 )
        {
          v17[1] = 0;
          *((_DWORD *)v17 + 4) = 1;
          *v17 = 0;
        }
        else
        {
          v19 = 0;
        }
        v36 = (__int64)v19;
        if ( !v19 )
          _com_issue_error(v18);
        v20 = v35;
        TaskURI = WaasMedic::TasksHelper::GetTaskURI((WaasMedic::TasksHelper *)ppv, v35, v19);
        v5 = TaskURI;
        if ( TaskURI >= 0 )
        {
          v22 = *v19;
          v42 = 0;
          v43 = 0;
          v23 = -1;
          do
            ++v23;
          while ( v22[v23] );
          std::wstring::_Construct<1,unsigned short const *>(&v42, v22, v23);
          last_of = std::wstring::find_last_of(&v42);
          v25 = last_of;
          memset(v52, 0, sizeof(v52));
          v26 = v43;
          if ( !(_QWORD)v43 )
            std::_String_val<std::_Simple_types<char>>::_Xran();
          if ( (__int64)v43 - 1 >= (unsigned __int64)(last_of - 1) )
            v26 = last_of;
          v27 = v26 - 1;
          v28 = &v42;
          if ( *((_QWORD *)&v43 + 1) > 7u )
            v28 = (__int128 *)v42;
          std::wstring::_Construct<1,unsigned short const *>(v52, (char *)v28 + 2, v27);
          v29 = v25 + 1;
          memset(v51, 0, sizeof(v51));
          if ( (unsigned __int64)v43 < v29 )
            std::_String_val<std::_Simple_types<char>>::_Xran();
          v30 = -1;
          if ( (_QWORD)v43 - v29 != -1 )
            v30 = v43 - v29;
          v31 = &v42;
          if ( *((_QWORD *)&v43 + 1) > 7u )
            v31 = (__int128 *)v42;
          std::wstring::_Construct<1,unsigned short const *>(v51, (char *)v31 + 2 * v29, v30);
          std::wstring::wstring(v44, v52);
          std::wstring::wstring(v45, v51);
          memset(v46, 0, sizeof(v46));
          v32 = -1;
          do
            ++v32;
          while ( v20[v32] );
          std::wstring::_Construct<1,unsigned short const *>(v46, v20, v32);
          v47 = 0;
          v48 = 0;
          v49 = 0;
          v50 = 0;
          v33 = *((_QWORD *)this + 20);
          if ( v33 == *((_QWORD *)this + 21) )
          {
            std::vector<WaasMedic::StaticTaskInfo>::_Emplace_reallocate<WaasMedic::StaticTaskInfo const &>(
              (char *)this + 152,
              *((_QWORD *)this + 20),
              v44);
          }
          else
          {
            v41 = *((_QWORD *)this + 20);
            std::wstring::wstring(v33, v44);
            std::wstring::wstring(v33 + 32, v45);
            std::wstring::wstring(v33 + 64, v46);
            *(_BYTE *)(v33 + 96) = v47;
            *((_QWORD *)this + 20) += 104LL;
          }
          std::wstring::~wstring(v46);
          std::wstring::~wstring(v45);
          std::wstring::~wstring(v44);
          std::wstring::~wstring(v51);
          std::wstring::~wstring(v52);
          std::wstring::~wstring(&v42);
          _bstr_t::~_bstr_t((_bstr_t *)&v36);
          if ( v20 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v20);
          }
          goto LABEL_52;
        }
        LogLevelW(2u, L"Error in GetTaskURI.Incorrectly formatted XML?. hr = 0x%08x", (unsigned int)TaskURI);
        _bstr_t::~_bstr_t((_bstr_t *)&v36);
        if ( !v20 )
          goto LABEL_51;
        v15 = GetProcessHeap();
        v16 = v20;
        goto LABEL_21;
      }
      LogLevelW(2u, L"Error in initializing task helper library with path %ws", L"Microsoft\\Windows\\WindowsUpdate");
    }
    else
    {
      LogLevelW(2u, L"Error in LoadXMLFromFile for file: %s. hr = 0x%08x", v54, (unsigned int)XMLFromFile);
    }
    v14 = v35;
    if ( !v35 )
      goto LABEL_51;
    v15 = GetProcessHeap();
    v16 = v14;
LABEL_21:
    HeapFree(v15, 0, v16);
    goto LABEL_51;
  }
  LogLevelW(2u, L"Error while expanding environment variable. hr = 0x%08x", (unsigned int)v4);
LABEL_3:
  if ( *((_QWORD *)this + 20) == *((_QWORD *)this + 19) )
  {
    LogLevelW(3u, L"No Static task XML files found.");
    v6 = WaasMedic::TelemetryProvider::Provider();
    if ( *(_DWORD *)v6 > 5u
      && (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0
      && (*((_QWORD *)v6 + 3) & 0x400000000000LL) == *((_QWORD *)v6 + 3) )
    {
      LODWORD(v35) = v5;
      hFindFile = &gc_pszVersionString;
      v36 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v6,
        (unsigned int)&byte_18008A297,
        0,
        v7,
        (__int64)&v36,
        (__int64)&hFindFile,
        (__int64)&v35);
    }
  }
  WaasMedic::TasksHelper::~TasksHelper((WaasMedic::TasksHelper *)ppv);
  if ( lpMem )
  {
    v8 = GetProcessHeap();
    HeapFree(v8, 0, lpMem);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800555cc  push    rbp
0x1800555ce  push    rbx
0x1800555cf  push    rsi
0x1800555d0  push    r12
0x1800555d2  push    r13
0x1800555d4  push    r15
0x1800555d6  lea     rbp, [rsp-6D8h]
0x1800555de  sub     rsp, 7D8h
0x1800555e5  mov     rax, cs:__security_cookie
0x1800555ec  xor     rax, rsp
0x1800555ef  mov     [rbp+700h+var_40], rax
0x1800555f6  mov     r12, rcx
0x1800555f9  xor     r13d, r13d
0x1800555fc  xor     eax, eax
0x1800555fe  mov     [rsp+800h+var_790], rax
0x180055603  xorps   xmm1, xmm1
0x180055606  movdqu  xmmword ptr [rsp+800h+ppv], xmm1
0x18005560c  mov     word ptr [rsp+800h+var_790], r13w
0x180055612  mov     byte ptr [rcx+0FAh], 1
0x180055619  mov     [rsp+800h+lpMem], r13
0x18005561e  lea     rdx, [rsp+800h+lpMem]; unsigned __int16 *
0x180055623  lea     rcx, aWindirWaasTask; "%windir%\\WaaS\\Tasks"
0x18005562a  call    ?SafeExpandEnvironmentString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeExpandEnvironmentString(ushort const *,ushort * *)
0x18005562f  mov     esi, eax
0x180055631  test    eax, eax
0x180055633  jns     loc_180055733
0x180055639  lea     rdx, aErrorWhileExpa; "Error while expanding environment varia"...
0x180055640  mov     r8d, eax
0x180055643  mov     ecx, 2; unsigned __int8
0x180055648  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005564d  mov     rax, [r12+0A0h]
0x180055655  cmp     rax, [r12+98h]
0x18005565d  jnz     loc_1800556E9
0x180055663  lea     rdx, aNoStaticTaskXm; "No Static task XML files found."
0x18005566a  mov     ecx, 3; unsigned __int8
0x18005566f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180055674  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180055679  mov     ecx, [rax]
0x18005567b  cmp     ecx, 5
0x18005567e  jbe     short loc_1800556E9
0x180055680  mov     rdx, [rax+18h]
0x180055684  mov     rcx, [rax+10h]
0x180055688  mov     r8, 400000000000h
0x180055692  test    r8, rcx
0x180055695  jz      short loc_1800556E9
0x180055697  mov     rcx, rdx
0x18005569a  and     rcx, r8
0x18005569d  cmp     rcx, rdx
0x1800556a0  jnz     short loc_1800556E9
0x1800556a2  mov     dword ptr [rsp+800h+var_7C0], esi
0x1800556a6  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800556ad  mov     [rsp+800h+hFindFile], rcx
0x1800556b2  mov     [rsp+800h+var_7B8], 1000000h
0x1800556bb  lea     rcx, [rsp+800h+var_7C0]
0x1800556c0  mov     [rsp+800h+var_7D0], rcx
0x1800556c5  lea     rcx, [rsp+800h+hFindFile]
0x1800556ca  mov     [rsp+800h+var_7D8], rcx
0x1800556cf  lea     rcx, [rsp+800h+var_7B8]
0x1800556d4  mov     [rsp+800h+var_7E0], rcx
0x1800556d9  lea     rdx, byte_18008A297
0x1800556e0  mov     rcx, rax
0x1800556e3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800556e8  nop
0x1800556e9  lea     rcx, [rsp+800h+ppv]; this
0x1800556ee  call    ??1TasksHelper@WaasMedic@@QEAA@XZ; WaasMedic::TasksHelper::~TasksHelper(void)
0x1800556f3  nop
0x1800556f4  cmp     [rsp+800h+lpMem], r13
0x1800556f9  jz      short loc_180055711
0x1800556fb  call    cs:__imp_GetProcessHeap
0x180055701  mov     rcx, rax; hHeap
0x180055704  mov     r8, [rsp+800h+lpMem]; lpMem
0x180055709  xor     edx, edx; dwFlags
0x18005570b  call    cs:__imp_HeapFree
0x180055711  mov     eax, esi
0x180055713  mov     rcx, [rbp+700h+var_40]
0x18005571a  xor     rcx, rsp; StackCookie
0x18005571d  call    __security_check_cookie
0x180055722  add     rsp, 7D8h
0x180055729  pop     r15
0x18005572b  pop     r13
0x18005572d  pop     r12
0x18005572f  pop     rsi
0x180055730  pop     rbx
0x180055731  pop     rbp
0x180055732  retn
0x180055733  lea     r9, pszMore; "*"
0x18005573a  mov     r8, [rsp+800h+lpMem]; pszPathIn
0x18005573f  mov     edx, 104h; cchPathOut
0x180055744  lea     rcx, [rbp+700h+pszPathOut]; pszPathOut
0x18005574b  call    cs:__imp_PathCchCombine
0x180055751  mov     esi, eax
0x180055753  test    eax, eax
0x180055755  jns     short loc_180055763
0x180055757  lea     rdx, aErrorInPathcch; "Error in PathCchCombine. hr = 0x%08x"
0x18005575e  jmp     loc_180055640
0x180055763  xor     edx, edx; Val
0x180055765  mov     r8d, 250h; Size
0x18005576b  lea     rcx, [rbp+700h+FindFileData]; void *
0x18005576f  call    memset_0
0x180055774  lea     rdx, [rbp+700h+FindFileData]; lpFindFileData
0x180055778  lea     rcx, [rbp+700h+pszPathOut]; lpFileName
0x18005577f  call    cs:__imp_FindFirstFileW
0x180055785  mov     [rsp+800h+hFindFile], rax
0x18005578a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005578e  jz      loc_18005564D
0x180055794  test    byte ptr [rbp+700h+FindFileData.dwFileAttributes], 10h
0x180055798  jnz     loc_180055AD6
0x18005579e  lea     r9, [rbp+700h+FindFileData.cFileName]; pszMore
0x1800557a2  mov     r8, [rsp+800h+lpMem]; pszPathIn
0x1800557a7  mov     edx, 104h; cchPathOut
0x1800557ac  lea     rcx, [rbp+700h+var_460]; pszPathOut
0x1800557b3  call    cs:__imp_PathCchCombine
0x1800557b9  mov     esi, eax
0x1800557bb  test    eax, eax
0x1800557bd  jns     short loc_1800557D9
0x1800557bf  mov     r8d, eax
0x1800557c2  lea     rdx, aErrorInPathcch; "Error in PathCchCombine. hr = 0x%08x"
0x1800557c9  mov     ecx, 2; unsigned __int8
0x1800557ce  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800557d3  nop
0x1800557d4  jmp     loc_180055ADA
0x1800557d9  mov     [rsp+800h+var_7C0], r13
0x1800557de  lea     rdx, [rsp+800h+var_7C0]; unsigned __int16 *
0x1800557e3  lea     rcx, [rbp+700h+var_460]; this
0x1800557ea  call    ?LoadXMLFromFile@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::LoadXMLFromFile(ushort const *,ushort * *)
0x1800557ef  mov     esi, eax
0x1800557f1  test    eax, eax
0x1800557f3  jns     short loc_180055838
0x1800557f5  mov     r9d, eax
0x1800557f8  lea     r8, [rbp+700h+var_460]
0x1800557ff  lea     rdx, aErrorInLoadxml; "Error in LoadXMLFromFile for file: %s. "...
0x180055806  mov     ecx, 2; unsigned __int8
0x18005580b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180055810  nop
0x180055811  mov     rbx, [rsp+800h+var_7C0]
0x180055816  test    rbx, rbx
0x180055819  jz      loc_180055ADA
0x18005581f  call    cs:__imp_GetProcessHeap
0x180055825  mov     r8, rbx; lpMem
0x180055828  mov     rcx, rax; hHeap
0x18005582b  xor     edx, edx; dwFlags
0x18005582d  call    cs:__imp_HeapFree
0x180055833  jmp     loc_180055ADA
0x180055838  lea     rdx, aMicrosoftWindo_0; "Microsoft\\Windows\\WindowsUpdate"
0x18005583f  lea     rcx, [rsp+800h+ppv]; ppv
0x180055844  call    ?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z; WaasMedic::TasksHelper::Initialize(ushort const *)
0x180055849  mov     esi, eax
0x18005584b  test    eax, eax
0x18005584d  jns     short loc_180055869
0x18005584f  lea     r8, aMicrosoftWindo_0; "Microsoft\\Windows\\WindowsUpdate"
0x180055856  lea     rdx, aErrorInInitial; "Error in initializing task helper libra"...
0x18005585d  mov     ecx, 2; unsigned __int8
0x180055862  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180055867  jmp     short loc_180055811
0x180055869  mov     [rsp+800h+var_7B8], r13
0x18005586e  mov     ecx, 18h; Size
0x180055873  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180055878  mov     rbx, rax
0x18005587b  mov     [rsp+800h+var_7B8], rax
0x180055880  test    rax, rax
0x180055883  jz      short loc_180055895
0x180055885  mov     [rax+8], r13
0x180055889  mov     dword ptr [rax+10h], 1
0x180055890  mov     [rax], r13
0x180055893  jmp     short loc_180055898
0x180055895  mov     rbx, r13
0x180055898  mov     [rsp+800h+var_7B8], rbx
0x18005589d  test    rbx, rbx
0x1800558a0  jz      loc_180055B17
0x1800558a6  mov     r8, rbx; unsigned __int16 **
0x1800558a9  mov     r15, [rsp+800h+var_7C0]
0x1800558ae  mov     rdx, r15; unsigned __int16 *
0x1800558b1  lea     rcx, [rsp+800h+ppv]; this
0x1800558b6  call    ?GetTaskURI@TasksHelper@WaasMedic@@QEAAJPEBGPEAPEAG@Z; WaasMedic::TasksHelper::GetTaskURI(ushort const *,ushort * *)
0x1800558bb  mov     esi, eax
0x1800558bd  test    eax, eax
0x1800558bf  jns     short loc_1800558F8
0x1800558c1  mov     r8d, eax
0x1800558c4  lea     rdx, aErrorInGettask; "Error in GetTaskURI.Incorrectly formatt"...
0x1800558cb  mov     ecx, 2; unsigned __int8
0x1800558d0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800558d5  nop
0x1800558d6  lea     rcx, [rsp+800h+var_7B8]; this
0x1800558db  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x1800558e0  nop
0x1800558e1  test    r15, r15
0x1800558e4  jz      loc_180055ADA
0x1800558ea  call    cs:__imp_GetProcessHeap
0x1800558f0  mov     r8, r15
0x1800558f3  jmp     loc_180055828
0x1800558f8  mov     rdx, [rbx]
0x1800558fb  xorps   xmm0, xmm0
0x1800558fe  movups  [rbp+700h+var_780], xmm0
0x180055902  xorps   xmm1, xmm1
0x180055905  movdqu  [rbp+700h+var_770], xmm1
0x18005590a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005590e  inc     r8
0x180055911  cmp     [rdx+r8*2], r13w
0x180055916  jnz     short loc_18005590E
0x180055918  lea     rcx, [rbp+700h+var_780]
0x18005591c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180055921  nop
0x180055922  lea     rcx, [rbp+700h+var_780]
0x180055926  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find_last_of(ushort const * const,unsigned __int64)
0x18005592b  mov     rbx, rax
0x18005592e  xorps   xmm0, xmm0
0x180055931  movups  [rbp+700h+var_6D0], xmm0
0x180055935  xorps   xmm1, xmm1
0x180055938  movdqu  [rbp+700h+var_6C0], xmm1
0x18005593d  mov     r8, qword ptr [rbp+700h+var_770]
0x180055941  cmp     r8, 1
0x180055945  jb      loc_180055B11
0x18005594b  lea     rdx, [r8-1]
0x18005594f  lea     rcx, [rax-1]
0x180055953  cmp     rdx, rcx
0x180055956  cmovnb  r8, rax
0x18005595a  dec     r8
0x18005595d  lea     rdx, [rbp+700h+var_780]
0x180055961  cmp     qword ptr [rbp+700h+var_770+8], 7
0x180055966  cmova   rdx, qword ptr [rbp+700h+var_780]
0x18005596b  add     rdx, 2
0x18005596f  lea     rcx, [rbp+700h+var_6D0]
0x180055973  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180055978  nop
0x180055979  inc     rbx
0x18005597c  xorps   xmm0, xmm0
0x18005597f  movups  [rbp+700h+var_6F0], xmm0
0x180055983  xorps   xmm1, xmm1
0x180055986  movdqu  [rbp+700h+var_6E0], xmm1
0x18005598b  mov     rax, qword ptr [rbp+700h+var_770]
0x18005598f  cmp     rax, rbx
0x180055992  jb      loc_180055B1D
0x180055998  sub     rax, rbx
0x18005599b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18005599f  cmp     rax, r8
0x1800559a2  cmovb   r8, rax
0x1800559a6  lea     rax, [rbp+700h+var_780]
0x1800559aa  cmp     qword ptr [rbp+700h+var_770+8], 7
0x1800559af  cmova   rax, qword ptr [rbp+700h+var_780]
0x1800559b4  lea     rdx, [rax+rbx*2]
0x1800559b8  lea     rcx, [rbp+700h+var_6F0]
0x1800559bc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800559c1  nop
0x1800559c2  lea     rdx, [rbp+700h+var_6D0]
0x1800559c6  lea     rcx, [rbp+700h+var_760]
0x1800559ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800559cf  nop
0x1800559d0  lea     rdx, [rbp+700h+var_6F0]
0x1800559d4  lea     rcx, [rbp+700h+var_740]
0x1800559d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800559dd  nop
0x1800559de  xorps   xmm0, xmm0
0x1800559e1  movups  [rbp+700h+var_720], xmm0
0x1800559e5  xorps   xmm1, xmm1
0x1800559e8  movdqa  [rbp+700h+var_710], xmm1
0x1800559ed  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800559f1  inc     r8
0x1800559f4  cmp     [r15+r8*2], r13w
0x1800559f9  jnz     short loc_1800559F1
0x1800559fb  mov     rdx, r15
0x1800559fe  lea     rcx, [rbp+700h+var_720]
0x180055a02  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180055a07  mov     [rbp+700h+var_700], r13b
0x180055a0b  xor     eax, eax
0x180055a0d  mov     [rbp+700h+var_6FF], eax
0x180055a10  mov     [rbp+700h+var_6FB], ax
0x180055a14  mov     [rbp+700h+var_6F9], al
0x180055a17  lea     r13, [r12+98h]
0x180055a1f  mov     rbx, [r13+8]
0x180055a23  cmp     rbx, [r13+10h]
0x180055a27  jz      short loc_180055A63
0x180055a29  mov     [rsp+800h+var_788], rbx
0x180055a2e  lea     rdx, [rbp+700h+var_760]
0x180055a32  mov     rcx, rbx
0x180055a35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180055a3a  nop
0x180055a3b  lea     rcx, [rbx+20h]
0x180055a3f  lea     rdx, [rbp+700h+var_740]
0x180055a43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180055a48  nop
0x180055a49  lea     rcx, [rbx+40h]
0x180055a4d  lea     rdx, [rbp+700h+var_720]
0x180055a51  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180055a56  mov     al, [rbp+700h+var_700]
0x180055a59  mov     [rbx+60h], al
0x180055a5c  add     qword ptr [r13+8], 68h ; 'h'
0x180055a61  jmp     short loc_180055A73
0x180055a63  lea     r8, [rbp+700h+var_760]
0x180055a67  mov     rdx, rbx
0x180055a6a  mov     rcx, r13
0x180055a6d  call    ??$_Emplace_reallocate@AEBUStaticTaskInfo@WaasMedic@@@?$vector@UStaticTaskInfo@WaasMedic@@V?$allocator@UStaticTaskInfo@WaasMedic@@@std@@@std@@AEAAPEAUStaticTaskInfo@WaasMedic@@QEAU23@AEBU23@@Z; std::vector<WaasMedic::StaticTaskInfo>::_Emplace_reallocate<WaasMedic::StaticTaskInfo const &>(WaasMedic::StaticTaskInfo * const,WaasMedic::StaticTaskInfo const &)
0x180055a72  nop
0x180055a73  lea     rcx, [rbp+700h+var_720]; void *
0x180055a77  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055a7c  lea     rcx, [rbp+700h+var_740]; void *
0x180055a80  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055a85  lea     rcx, [rbp+700h+var_760]; void *
0x180055a89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055a8e  nop
0x180055a8f  lea     rcx, [rbp+700h+var_6F0]; void *
  ... truncated ...
```
