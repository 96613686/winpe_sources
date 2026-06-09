# WorkflowSessionCommon::CreateTemporaryFileHandles(void)

- ea: `0x1800239c8`
- end: `0x180023f06`
- name: `?CreateTemporaryFileHandles@WorkflowSessionCommon@@QEAAJXZ`
- size: `1342`
- prototype: `__int64 __fastcall(WorkflowSessionCommon *this, __int64, int, int)`
- caller_count: `3`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016b40`
- `0x18003e420`
- `0x180044b94`

## callees

- `0x180001614`
- `0x180002620`
- `0x180003ca0`
- `0x18000495c`
- `0x180008610`
- `0x1800113d4`
- `0x1800114a4`
- `0x1800127a4`
- `0x18001a7c0`
- `0x180020e8c`
- `0x18002141c`
- `0x180021c14`
- `0x180023664`
- `0x1800239c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180023b36`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x180023b36`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180023b9a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180023b9a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180023b5e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180023b5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023afe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023cdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023d42`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180023aab`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x180023aab`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023c61`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023cc6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023d2b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023c61`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023cc6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023d2b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023aec`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180023aec`

## string_xrefs

- `0x180023ab9`: `WorkflowTemp`
- `0x180023e0b`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023e1b`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023e30`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023e41`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023e5b`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023e72`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023e86`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023e97`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023ea8`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023eb9`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023ecd`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x180023ef3`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`

## pseudocode

```c
__int64 __fastcall WorkflowSessionCommon::CreateTemporaryFileHandles(
        WorkflowSessionCommon *this,
        __int64 a2,
        int a3,
        int a4)
{
  int CallerIntegrityLevel; // eax
  int v6; // r8d
  int v7; // r9d
  unsigned int v8; // r14d
  const char *v9; // r9
  int v10; // eax
  const char *v11; // r9
  __int16 i; // di
  HRESULT v13; // eax
  int v14; // eax
  __int64 v15; // r8
  HANDLE FileW; // rax
  const char *v17; // r9
  HANDLE v18; // rax
  const char *v19; // r9
  HANDLE v20; // rax
  int v21; // r8d
  const char *v22; // r9
  int v23; // ecx
  int v24; // eax
  __int64 result; // rax
  unsigned int v26; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-518h]
  unsigned int v28; // [rsp+40h] [rbp-4F8h] BYREF
  int v29; // [rsp+44h] [rbp-4F4h] BYREF
  WCHAR *v30; // [rsp+48h] [rbp-4F0h] BYREF
  GUID pguid; // [rsp+50h] [rbp-4E8h] BYREF
  int v32[4]; // [rsp+60h] [rbp-4D8h] BYREF
  __int16 v33; // [rsp+70h] [rbp-4C8h]
  OLECHAR sz[40]; // [rsp+80h] [rbp-4B8h] BYREF
  WCHAR FileName[264]; // [rsp+D0h] [rbp-468h] BYREF
  WCHAR PathName[264]; // [rsp+2E0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+538h] [rbp+0h]

  if ( (unsigned int)dword_180083038 > 5 )
  {
    v28 = *((_DWORD *)this + 18);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_180083038,
      (unsigned int)byte_180072C89,
      a3,
      a4,
      (__int64)&v28);
  }
  v28 = 4096;
  CallerIntegrityLevel = GetCallerIntegrityLevel(&v28);
  try
  {
    if ( CallerIntegrityLevel < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        (const char *)(unsigned int)CallerIntegrityLevel,
        dwCreationDisposition);
    v8 = v28;
    if ( (unsigned int)dword_180083038 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180083038,
        (unsigned int)&byte_180072C1F,
        v6,
        v7,
        (__int64)&v28);
    memset_0(PathName, 0, 0x208u);
    if ( !(unsigned int)GetTempPath2W(260, PathName) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x44,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        v9);
    v10 = StringCchCatW(PathName, 0x104u, L"WorkflowTemp");
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        (const char *)(unsigned int)v10,
        dwCreationDisposition);
    if ( !CreateDirectoryW(PathName, 0) && GetLastError() != 183 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        v11);
    *(_OWORD *)v32 = 0;
    v33 = 0;
    if ( (unsigned int)_o__itow_s(*((unsigned int *)this + 18), v32, 9, 16) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x50,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        (const char *)0x80004005LL,
        dwCreationDisposition);
    for ( i = 0; ; ++i )
    {
      if ( i >= 5 )
      {
        v26 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x95,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
          (const char *)v26,
          dwCreationDisposition);
      }
      pguid = 0;
      v13 = CoCreateGuid(&pguid);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
          (const char *)(unsigned int)v13,
          dwCreationDisposition);
      memset_0(sz, 0, 0x4Eu);
      if ( StringFromGUID2(&pguid, sz, 39) )
      {
        memset_0(FileName, 0, 0x208u);
        sz[37] = 0;
        v14 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s_%s.tmp", PathName);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x62,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
            (const char *)(unsigned int)v14,
            (int)v32);
        v15 = -1;
        do
          ++v15;
        while ( FileName[v15] );
        std::wstring::_Assign<unsigned short>((char *)this + 40, FileName);
        FileW = CreateFileW(FileName, 0xC0000000, 5u, 0, 1u, 0x4000100u, 0);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          (char *)this + 16,
          FileW);
        if ( *((_QWORD *)this + 2) != -1 || GetLastError() != 5 )
        {
          if ( *((_QWORD *)this + 2) == -1 )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x6E,
              (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
              v17);
          v18 = CreateFileW(FileName, 0x80000000, 7u, 0, 3u, 0x4000100u, 0);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
            (char *)this + 24,
            v18);
          if ( *((_QWORD *)this + 3) != -1 || GetLastError() != 5 )
          {
            if ( *((_QWORD *)this + 3) == -1 )
              wil::details::in1diag3::_Throw_GetLastError(
                retaddr,
                (void *)0x79,
                (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
                v19);
            v20 = CreateFileW(FileName, 0x80000000, 7u, 0, 3u, 0x4000100u, 0);
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
              (char *)this + 32,
              v20);
            if ( *((_QWORD *)this + 4) != -1 || GetLastError() != 5 )
              break;
          }
        }
      }
    }
    v23 = (int)retaddr;
    if ( *((_QWORD *)this + 4) == -1 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x84,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        v22);
    if ( v8 <= 0x1000 )
    {
      v24 = ApplyLowSecurityLabel(FileName);
      v23 = (int)retaddr;
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8A,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
          (const char *)(unsigned int)v24,
          dwCreationDisposition);
    }
    if ( (unsigned int)dword_180083038 > 5 )
    {
      LOWORD(v28) = i;
      v29 = *((_DWORD *)this + 18);
      v30 = FileName;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(
        v23,
        (unsigned int)&word_180072BA6,
        v21,
        (_DWORD)v22,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x97,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
                           v22);
  }
  return result;
}

```

## disassembly

```asm
0x1800239c8  push    rbx
0x1800239ca  push    rsi
0x1800239cb  push    rdi
0x1800239cc  push    r12
0x1800239ce  push    r14
0x1800239d0  push    r15
0x1800239d2  sub     rsp, 508h
0x1800239d9  mov     rax, cs:__security_cookie
0x1800239e0  xor     rax, rsp
0x1800239e3  mov     [rsp+538h+var_48], rax
0x1800239eb  mov     rbx, rcx
0x1800239ee  mov     eax, cs:dword_180083038
0x1800239f4  mov     r12d, 5
0x1800239fa  cmp     eax, r12d
0x1800239fd  jbe     short loc_180023A23
0x1800239ff  mov     eax, [rcx+48h]
0x180023a02  mov     [rsp+538h+var_4F8], eax
0x180023a06  lea     rax, [rsp+538h+var_4F8]
0x180023a0b  mov     qword ptr [rsp+538h+dwCreationDisposition], rax; int
0x180023a10  lea     rdx, byte_180072C89
0x180023a17  lea     rcx, dword_180083038
0x180023a1e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023a23  mov     [rsp+538h+var_4F8], 1000h
0x180023a2b  lea     rcx, [rsp+538h+var_4F8]; unsigned int *
0x180023a30  call    ?GetCallerIntegrityLevel@@YAJAEAK@Z; GetCallerIntegrityLevel(ulong &)
0x180023a35  mov     rcx, [rsp+538h]; this
0x180023a3d  xor     r15d, r15d
0x180023a40  test    eax, eax
0x180023a42  js      loc_180023E08
0x180023a48  mov     eax, cs:dword_180083038
0x180023a4e  cmp     eax, r12d
0x180023a51  jbe     short loc_180023A7C
0x180023a53  mov     r14d, [rsp+538h+var_4F8]
0x180023a58  mov     [rsp+538h+var_4F8], r14d
0x180023a5d  lea     rax, [rsp+538h+var_4F8]
0x180023a62  mov     qword ptr [rsp+538h+dwCreationDisposition], rax
0x180023a67  lea     rdx, byte_180072C1F
0x180023a6e  lea     rcx, dword_180083038
0x180023a75  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180023a7a  jmp     short loc_180023A81
0x180023a7c  mov     r14d, [rsp+538h+var_4F8]
0x180023a81  xor     edx, edx; Val
0x180023a83  mov     r8d, 208h; Size
0x180023a89  lea     rcx, [rsp+538h+PathName]; void *
0x180023a91  call    memset_0
0x180023a96  mov     rdi, [rsp+538h]
0x180023a9e  lea     rdx, [rsp+538h+PathName]
0x180023aa6  mov     ecx, 104h
0x180023aab  call    cs:__imp_GetTempPath2W
0x180023ab1  test    eax, eax
0x180023ab3  jz      loc_180023E1B
0x180023ab9  lea     r8, aWorkflowtemp; "WorkflowTemp"
0x180023ac0  mov     edx, 104h; unsigned __int64
0x180023ac5  lea     rcx, [rsp+538h+PathName]; unsigned __int16 *
0x180023acd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023ad2  mov     rcx, [rsp+538h]; this
0x180023ada  test    eax, eax
0x180023adc  js      loc_180023E2D
0x180023ae2  xor     edx, edx; lpSecurityAttributes
0x180023ae4  lea     rcx, [rsp+538h+PathName]; lpPathName
0x180023aec  call    cs:__imp_CreateDirectoryW
0x180023af2  test    eax, eax
0x180023af4  jnz     short loc_180023B0F
0x180023af6  mov     rdi, [rsp+538h]
0x180023afe  call    cs:__imp_GetLastError
0x180023b04  cmp     eax, 0B7h
0x180023b09  jnz     loc_180023E41
0x180023b0f  xorps   xmm0, xmm0
0x180023b12  xor     eax, eax
0x180023b14  movups  xmmword ptr [rsp+538h+var_4D8], xmm0
0x180023b19  mov     [rsp+538h+var_4C8], ax
0x180023b1e  mov     rdi, [rsp+538h]
0x180023b26  lea     r9d, [rax+10h]
0x180023b2a  lea     r8d, [rax+9]
0x180023b2e  lea     rdx, [rsp+538h+var_4D8]
0x180023b33  mov     ecx, [rbx+48h]
0x180023b36  call    cs:__imp__o__itow_s
0x180023b3c  test    eax, eax
0x180023b3e  jnz     loc_180023E55
0x180023b44  mov     edi, r15d
0x180023b47  cmp     di, r12w
0x180023b4b  jge     loc_180023EDE
0x180023b51  xorps   xmm0, xmm0
0x180023b54  movups  xmmword ptr [rsp+538h+pguid.Data1], xmm0
0x180023b59  lea     rcx, [rsp+538h+pguid]; pguid
0x180023b5e  call    cs:__imp_CoCreateGuid
0x180023b64  mov     rcx, [rsp+538h]; this
0x180023b6c  test    eax, eax
0x180023b6e  js      loc_180023E6F
0x180023b74  xor     edx, edx; Val
0x180023b76  lea     r8d, [rdx+4Eh]; Size
0x180023b7a  lea     rcx, [rsp+538h+sz]; void *
0x180023b82  call    memset_0
0x180023b87  mov     r8d, 27h ; '''; cchMax
0x180023b8d  lea     rdx, [rsp+538h+sz]; lpsz
0x180023b95  lea     rcx, [rsp+538h+pguid]; rguid
0x180023b9a  call    cs:__imp_StringFromGUID2
0x180023ba0  test    eax, eax
0x180023ba2  jz      loc_180023DDB
0x180023ba8  xor     edx, edx; Val
0x180023baa  mov     r8d, 208h; Size
0x180023bb0  lea     rcx, [rsp+538h+FileName]; void *
0x180023bb8  call    memset_0
0x180023bbd  mov     [rsp+538h+var_46E], r15w
0x180023bc6  lea     rax, [rsp+538h+var_4B6]
0x180023bce  mov     qword ptr [rsp+538h+dwFlagsAndAttributes], rax
0x180023bd3  lea     rax, [rsp+538h+var_4D8]
0x180023bd8  mov     qword ptr [rsp+538h+dwCreationDisposition], rax; int
0x180023bdd  lea     r9, [rsp+538h+PathName]
0x180023be5  lea     r8, aSSSTmp; "%s\\%s_%s.tmp"
0x180023bec  mov     edx, 104h; unsigned __int64
0x180023bf1  lea     rcx, [rsp+538h+FileName]; unsigned __int16 *
0x180023bf9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023bfe  mov     rcx, [rsp+538h]; this
0x180023c06  test    eax, eax
0x180023c08  js      loc_180023E83
0x180023c0e  lea     rax, [rsp+538h+FileName]
0x180023c16  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023c1a  inc     r8
0x180023c1d  cmp     [rax+r8*2], r15w
0x180023c22  jnz     short loc_180023C1A
0x180023c24  lea     rcx, [rbx+28h]
0x180023c28  lea     rdx, [rsp+538h+FileName]
0x180023c30  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180023c35  lea     rsi, [rbx+10h]
0x180023c39  mov     [rsp+538h+hTemplateFile], r15; hTemplateFile
0x180023c3e  mov     [rsp+538h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180023c46  mov     [rsp+538h+dwCreationDisposition], 1; dwCreationDisposition
0x180023c4e  xor     r9d, r9d; lpSecurityAttributes
0x180023c51  mov     r8d, r12d; dwShareMode
0x180023c54  mov     edx, 0C0000000h; dwDesiredAccess
0x180023c59  lea     rcx, [rsp+538h+FileName]; lpFileName
0x180023c61  call    cs:__imp_CreateFileW
0x180023c67  mov     rdx, rax
0x180023c6a  mov     rcx, rsi
0x180023c6d  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180023c72  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180023c76  jnz     short loc_180023C87
0x180023c78  call    cs:__imp_GetLastError
0x180023c7e  cmp     eax, r12d
0x180023c81  jz      loc_180023DDB
0x180023c87  mov     rcx, [rsp+538h]; this
0x180023c8f  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180023c93  jz      loc_180023E97
0x180023c99  lea     rsi, [rbx+18h]
0x180023c9d  mov     [rsp+538h+hTemplateFile], r15; hTemplateFile
0x180023ca2  mov     [rsp+538h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180023caa  mov     [rsp+538h+dwCreationDisposition], 3; dwCreationDisposition
0x180023cb2  xor     r9d, r9d; lpSecurityAttributes
0x180023cb5  mov     edx, 80000000h; dwDesiredAccess
0x180023cba  lea     r8d, [r9+7]; dwShareMode
0x180023cbe  lea     rcx, [rsp+538h+FileName]; lpFileName
0x180023cc6  call    cs:__imp_CreateFileW
0x180023ccc  mov     rdx, rax
0x180023ccf  mov     rcx, rsi
0x180023cd2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180023cd7  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180023cdb  jnz     short loc_180023CEC
0x180023cdd  call    cs:__imp_GetLastError
0x180023ce3  cmp     eax, r12d
0x180023ce6  jz      loc_180023DDB
0x180023cec  mov     rcx, [rsp+538h]; this
0x180023cf4  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180023cf8  jz      loc_180023EA8
0x180023cfe  lea     rsi, [rbx+20h]
0x180023d02  mov     [rsp+538h+hTemplateFile], r15; hTemplateFile
0x180023d07  mov     [rsp+538h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180023d0f  mov     [rsp+538h+dwCreationDisposition], 3; int
0x180023d17  xor     r9d, r9d; lpSecurityAttributes
0x180023d1a  mov     edx, 80000000h; dwDesiredAccess
0x180023d1f  lea     r8d, [r9+7]; dwShareMode
0x180023d23  lea     rcx, [rsp+538h+FileName]; lpFileName
0x180023d2b  call    cs:__imp_CreateFileW
0x180023d31  mov     rdx, rax
0x180023d34  mov     rcx, rsi
0x180023d37  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180023d3c  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180023d40  jnz     short loc_180023D51
0x180023d42  call    cs:__imp_GetLastError
0x180023d48  cmp     eax, r12d
0x180023d4b  jz      loc_180023DDB
0x180023d51  mov     rcx, [rsp+538h]; this
0x180023d59  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180023d5d  jz      loc_180023EB9
0x180023d63  cmp     r14d, 1000h
0x180023d6a  ja      short loc_180023D89
0x180023d6c  lea     rcx, [rsp+538h+FileName]; pObjectName
0x180023d74  call    ?ApplyLowSecurityLabel@@YAJPEBG@Z; ApplyLowSecurityLabel(ushort const *)
0x180023d79  mov     rcx, [rsp+538h]; this
0x180023d81  test    eax, eax
0x180023d83  js      loc_180023ECA
0x180023d89  mov     eax, cs:dword_180083038
0x180023d8f  cmp     eax, r12d
0x180023d92  jbe     short loc_180023DD7
0x180023d94  mov     word ptr [rsp+538h+var_4F8], di
0x180023d99  mov     eax, [rbx+48h]
0x180023d9c  mov     [rsp+538h+var_4F4], eax
0x180023da0  lea     rax, [rsp+538h+FileName]
0x180023da8  mov     [rsp+538h+var_4F0], rax
0x180023dad  lea     rax, [rsp+538h+var_4F8]
0x180023db2  mov     [rsp+538h+hTemplateFile], rax
0x180023db7  lea     rax, [rsp+538h+var_4F4]
0x180023dbc  mov     qword ptr [rsp+538h+dwFlagsAndAttributes], rax
0x180023dc1  lea     rax, [rsp+538h+var_4F0]
0x180023dc6  mov     qword ptr [rsp+538h+dwCreationDisposition], rax
0x180023dcb  lea     rdx, word_180072BA6
0x180023dd2  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$01@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$01@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &)
0x180023dd7  xor     eax, eax
0x180023dd9  jmp     short loc_180023DE7
0x180023ddb  inc     di
0x180023dde  jmp     loc_180023B47
0x180023de3  mov     eax, [rsp+538h+var_4F4]
0x180023de7  mov     rcx, [rsp+538h+var_48]
0x180023def  xor     rcx, rsp; StackCookie
0x180023df2  call    __security_check_cookie
0x180023df7  add     rsp, 508h
0x180023dfe  pop     r15
0x180023e00  pop     r14
0x180023e02  pop     r12
0x180023e04  pop     rdi
0x180023e05  pop     rsi
0x180023e06  pop     rbx
0x180023e07  retn
0x180023e08  mov     r9d, eax; char *
0x180023e0b  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e12  lea     edx, [r15+3Ah]; void *
0x180023e16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023e1b  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e22  lea     edx, [rax+44h]; void *
0x180023e25  mov     rcx, rdi; this
0x180023e28  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180023e2d  mov     r9d, eax; char *
0x180023e30  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e37  mov     edx, 47h ; 'G'; void *
0x180023e3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023e41  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e48  mov     edx, 4Ah ; 'J'; void *
0x180023e4d  mov     rcx, rdi; this
0x180023e50  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180023e55  mov     r9d, 80004005h; char *
0x180023e5b  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e62  mov     edx, 50h ; 'P'; void *
0x180023e67  mov     rcx, rdi; this
0x180023e6a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023e6f  mov     r9d, eax; char *
0x180023e72  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e79  mov     edx, 58h ; 'X'; void *
0x180023e7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023e83  mov     r9d, eax; char *
0x180023e86  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e8d  mov     edx, 62h ; 'b'; void *
0x180023e92  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023e97  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023e9e  mov     edx, 6Eh ; 'n'; void *
0x180023ea3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180023ea8  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023eaf  mov     edx, 79h ; 'y'; void *
0x180023eb4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180023eb9  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023ec0  mov     edx, 84h; void *
0x180023ec5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180023eca  mov     r9d, eax; char *
0x180023ecd  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023ed4  mov     edx, 8Ah; void *
0x180023ed9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023ede  mov     ecx, 80004005h
0x180023ee3  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180023ee8  mov     r9d, eax; char *
0x180023eeb  mov     rcx, [rsp+538h]; this
0x180023ef3  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x180023efa  mov     edx, 95h; void *
0x180023eff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
