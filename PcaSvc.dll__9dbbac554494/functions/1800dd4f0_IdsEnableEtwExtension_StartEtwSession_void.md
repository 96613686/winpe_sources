# IdsEnableEtwExtension::StartEtwSession(void)

- ea: `0x1800dd4f0`
- end: `0x1800ddbb4`
- name: `?StartEtwSession@IdsEnableEtwExtension@@AEAAKXZ`
- size: `1732`
- prototype: `__int64 __fastcall(IdsEnableEtwExtension *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800dd420`

## callees

- `0x18000c018`
- `0x180012920`
- `0x1800182e0`
- `0x180018684`
- `0x180018768`
- `0x180018864`
- `0x180056bb8`
- `0x18007a9cf`
- `0x180098234`
- `0x18009cb6c`
- `0x1800a684c`
- `0x1800c3c58`
- `0x1800c3d64`
- `0x1800c3de8`
- `0x1800c3e0c`
- `0x1800c4dd4`
- `0x1800dd4f0`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800dd794`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800dd85b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800dd8f8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ddae1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ddb70`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800dd794`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800dd85b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800dd8f8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ddae1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800ddb70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd6ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd6ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd71e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd7bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dd7c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800dd5ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800dd5ad`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800dd7b2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800dd7b2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800dd6f1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800dd6f1`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800dd6b0`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800dd6b0`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800dda08`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800dda08`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800dd87d`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800dd87d`

## string_xrefs

- `0x1800dd72d`: `Failed to create folder %d, %ws`
- `0x1800ddb0c`: `String copy failed: 0x%08X / 0x%08X`
- `0x1800dd5c1`: `\appcompat\pca\`
- `0x1800dd7d1`: `IdsEnableEtwExtension: Failed to delete file %d`
- `0x1800dd582`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dd6d2`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dd73a`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dd7de`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dd804`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dd89e`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dda23`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dda95`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800ddb19`: `IdsEnableEtwExtension::StartEtwSession`
- `0x1800dd577`: `IdsEnableEtwExtension: AlsoRealtime is set`
- `0x1800dda88`: `IdsEnableEtwExtension: failed to enable %zu/%zu ETW providers`
- `0x1800dda16`: `IdsEnableEtwExtension: EnableTraceEx2 failed %d`
- `0x1800dd7f7`: `IdsEnableEtwExtension: ETW provider list is empty, no session started`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall IdsEnableEtwExtension::StartEtwSession(IdsEnableEtwExtension *this)
{
  int v2; // r15d
  ULONG v3; // edi
  PEVENT_TRACE_PROPERTIES v4; // rsi
  unsigned __int16 *p_Data2; // rbx
  int v6; // edi
  unsigned __int64 v7; // r11
  const unsigned __int16 *v8; // r8
  int v9; // eax
  ULONG v10; // eax
  const WCHAR *v11; // rcx
  LPCWSTR *v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rdx
  unsigned int v15; // ebx
  const WCHAR *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  ULONG started; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v24; // r15
  __int64 v25; // rbx
  __int64 v26; // rdi
  __int64 v27; // rsi
  unsigned int v28; // r12d
  __int64 v29; // r8
  unsigned __int16 i; // r9
  struct _EVENT_FILTER_DESCRIPTOR *v31; // rcx
  ULONG v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  ULONGLONG MatchAnyKeyword; // [rsp+20h] [rbp-E0h]
  ULONGLONG MatchAnyKeyworda; // [rsp+20h] [rbp-E0h]
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+48h] [rbp-B8h] BYREF
  ULONG64 TraceHandle[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v41[56]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v43[6]; // [rsp+A0h] [rbp-60h] BYREF
  char v44; // [rsp+D0h] [rbp-30h]
  struct _ENABLE_TRACE_PARAMETERS EnableParameters; // [rsp+D8h] [rbp-28h] BYREF
  LPCWSTR lpPathName[3]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int64 v47; // [rsp+120h] [rbp+20h]
  LPCWSTR lpFileName[2]; // [rsp+128h] [rbp+28h] BYREF
  int v49; // [rsp+138h] [rbp+38h]
  unsigned __int64 v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h] BYREF
  unsigned int v52; // [rsp+150h] [rbp+50h]
  int v53; // [rsp+154h] [rbp+54h]
  WCHAR Buffer[264]; // [rsp+160h] [rbp+60h] BYREF

  Properties = 0;
  tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>>((struct wil::details::IFailureCallback *)v41);
  tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(
    &v38,
    &v42);
  v43[3] = &v38;
  v43[4] = v41;
  v43[5] = &Properties;
  v44 = 1;
  v2 = 2;
  if ( *((_BYTE *)this + 24) )
  {
    v2 = 258;
    AslLogCallPrintf(
      3,
      (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
      220,
      (unsigned int)"IdsEnableEtwExtension: AlsoRealtime is set");
  }
  memset_0(Buffer, 0, 0x208u);
  GetWindowsDirectoryW(Buffer, 0x104u);
  std::wstring::wstring(lpPathName, Buffer);
  std::wstring::append(lpPathName, L"\\appcompat\\pca\\");
  std::operator+<unsigned short>(lpFileName, lpPathName, L"PcaEtwLog.etl");
  v3 = 2 * v49 + 150;
  Properties = (PEVENT_TRACE_PROPERTIES)operator new[](v3);
  memset_0(Properties, 0, v3);
  v4 = Properties;
  Properties->Wnode.BufferSize = v3;
  v4->Wnode.Guid = GUID_NULL;
  v4->Wnode.ClientContext = 1;
  v4->Wnode.Flags = 0x20000;
  v4->LogFileMode = v2;
  v4->MaximumFileSize = *((_DWORD *)this + 5);
  v4->FlushTimer = 3;
  v4->LoggerNameOffset = 120;
  v4->LogFileNameOffset = 148;
  p_Data2 = &Properties[1].Wnode.Guid.Data2;
  v6 = StringCchCopyW((unsigned __int16 *)&Properties[1], (unsigned __int64)(v3 - 120) >> 1, L"PcaEtwSession");
  v8 = (const unsigned __int16 *)lpFileName;
  if ( v50 >= 8 )
    v8 = lpFileName[0];
  v9 = StringCchCopyW(p_Data2, v7, v8);
  if ( v6 < 0 || v9 < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
      264,
      (unsigned int)"String copy failed: 0x%08X / 0x%08X",
      v6,
      v9);
    *(_DWORD *)(v38 + 272) = 3;
    LOBYTE(v34) = 1;
    std::wstring::_Tidy(lpFileName, v34, 0);
    LOBYTE(v35) = 1;
    std::wstring::_Tidy(lpPathName, v35, 0);
    tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(&v38);
    tip2::details::shared_data<1,0,0>::complete_without_lock(v42 + 8);
    operator delete[](Properties);
    tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(&v38);
    tip2::test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(v41);
    return 11;
  }
  else
  {
    v10 = ControlTraceW(0, L"PcaEtwSession", v4, 1u);
    if ( v10 && v10 != 4201 )
      AslLogCallPrintf(
        1,
        (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
        273,
        (unsigned int)"Failed to stop existing session %d",
        v10);
    v11 = (const WCHAR *)lpPathName;
    if ( v47 >= 8 )
      v11 = lpPathName[0];
    if ( !CreateDirectoryW(v11, 0) && GetLastError() != 183 )
    {
      v12 = lpPathName;
      if ( v47 >= 8 )
        v12 = (LPCWSTR *)lpPathName[0];
      LODWORD(MatchAnyKeyword) = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
        278,
        (unsigned int)"Failed to create folder %d, %ws",
        MatchAnyKeyword,
        v12);
      *(_DWORD *)(v38 + 272) = 7;
      LOBYTE(v13) = 1;
      std::wstring::_Tidy(lpFileName, v13, 0);
      LOBYTE(v14) = 1;
      std::wstring::_Tidy(lpPathName, v14, 0);
      tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(&v38);
      tip2::details::shared_data<1,0,0>::complete_without_lock(v42 + 8);
      operator delete[](Properties);
      v15 = 10;
      goto LABEL_26;
    }
    v16 = (const WCHAR *)lpFileName;
    if ( v50 >= 8 )
      v16 = lpFileName[0];
    if ( !DeleteFileW(v16) && GetLastError() != 2 )
    {
      LODWORD(MatchAnyKeyword) = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
        285,
        (unsigned int)"IdsEnableEtwExtension: Failed to delete file %d",
        MatchAnyKeyword);
    }
    if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
        290,
        (unsigned int)"IdsEnableEtwExtension: ETW provider list is empty, no session started");
      *(_DWORD *)(v38 + 272) = 0;
      LOBYTE(v17) = 1;
      std::wstring::_Tidy(lpFileName, v17, 0);
      LOBYTE(v18) = 1;
      std::wstring::_Tidy(lpPathName, v18, 0);
      tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(&v38);
      tip2::details::shared_data<1,0,0>::complete_without_lock(v42 + 8);
      operator delete[](Properties);
      v15 = 0;
LABEL_26:
      tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(&v38);
      tip2::test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(v41);
      return v15;
    }
    TraceHandle[0] = 0;
    started = StartTraceW(TraceHandle, L"PcaEtwSession", v4);
    v15 = started;
    if ( started )
    {
      LODWORD(MatchAnyKeyword) = started;
      AslLogCallPrintf(
        1,
        (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
        299,
        (unsigned int)"Failed to StartTraceW %d",
        MatchAnyKeyword);
      *(_DWORD *)(v38 + 272) = 6;
      LOBYTE(v21) = 1;
      std::wstring::_Tidy(lpFileName, v21, 0);
      LOBYTE(v22) = 1;
      std::wstring::_Tidy(lpPathName, v22, 0);
      tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(&v38);
      tip2::details::shared_data<1,0,0>::complete_without_lock(v42 + 8);
      operator delete[](Properties);
      goto LABEL_26;
    }
    v24 = 0;
    v25 = *((_QWORD *)this + 4);
    v26 = *((_QWORD *)this + 5);
    while ( v25 != v26 )
    {
      v27 = (__int64)(*(_QWORD *)(v25 + 24) - *(_QWORD *)(v25 + 16)) >> 1;
      v28 = 6;
      if ( (_DWORD)v27 )
        v28 = 2 * v27 + 4;
      std::vector<unsigned char>::vector<unsigned char>(v43, v28);
      v29 = v43[0];
      *(_BYTE *)v43[0] = 1;
      *(_WORD *)(v29 + 2) = v27;
      for ( i = 0; i < *(_WORD *)(v29 + 2); ++i )
        *(_WORD *)(v29 + 2LL * i + 4) = *(_WORD *)(*(_QWORD *)(v25 + 16) + 2LL * i);
      v51 = v29;
      v52 = v28;
      v53 = -2147483136;
      *(&EnableParameters.FilterDescCount + 1) = 0;
      *(_QWORD *)&EnableParameters.Version = 2;
      memset(&EnableParameters.ControlFlags, 0, 24);
      v31 = (struct _EVENT_FILTER_DESCRIPTOR *)&v51;
      if ( !(_DWORD)v27 )
        v31 = 0;
      EnableParameters.EnableFilterDesc = v31;
      EnableParameters.FilterDescCount = v27 != 0;
      v32 = EnableTraceEx2(TraceHandle[0], (LPCGUID)v25, 1u, 4u, 0xFFFFFFFFFFFFFFFFuLL, 0, 0, &EnableParameters);
      if ( v32 )
      {
        LODWORD(MatchAnyKeyworda) = v32;
        AslLogCallPrintf(
          1,
          (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
          346,
          (unsigned int)"IdsEnableEtwExtension: EnableTraceEx2 failed %d",
          MatchAnyKeyworda);
        ++v24;
      }
      std::vector<ProcessInfo>::~vector<ProcessInfo>(v43);
      v25 += 40;
    }
    if ( v24 )
    {
      *(_DWORD *)(v38 + 272) = 5;
      AslLogCallPrintf(
        1,
        (unsigned int)"IdsEnableEtwExtension::StartEtwSession",
        359,
        (unsigned int)"IdsEnableEtwExtension: failed to enable %zu/%zu ETW providers",
        v24,
        0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)this + 5) - *((_QWORD *)this + 4)) >> 3));
    }
    else
    {
      *(_DWORD *)(v38 + 272) = 0;
    }
    LOBYTE(v20) = 1;
    std::wstring::_Tidy(lpFileName, v20, 0);
    LOBYTE(v33) = 1;
    std::wstring::_Tidy(lpPathName, v33, 0);
    tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(&v38);
    tip2::details::shared_data<1,0,0>::complete_without_lock(v42 + 8);
    operator delete[](Properties);
    tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(&v38);
    tip2::test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(v41);
    return 0;
  }
}

```

## disassembly

```asm
0x1800dd4f0  push    rbp
0x1800dd4f2  push    rbx
0x1800dd4f3  push    rsi
0x1800dd4f4  push    rdi
0x1800dd4f5  push    r12
0x1800dd4f7  push    r13
0x1800dd4f9  push    r14
0x1800dd4fb  push    r15
0x1800dd4fd  lea     rbp, [rsp-288h]
0x1800dd505  sub     rsp, 388h
0x1800dd50c  mov     rax, cs:__security_cookie
0x1800dd513  xor     rax, rsp
0x1800dd516  mov     [rbp+2C0h+var_50], rax
0x1800dd51d  mov     r14, rcx
0x1800dd520  xor     r12d, r12d
0x1800dd523  mov     [rsp+3C0h+Properties], r12
0x1800dd528  lea     rcx, [rsp+3C0h+var_360]; struct wil::details::IFailureCallback *
0x1800dd52d  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x1800dd532  nop
0x1800dd533  lea     rdx, [rbp+2C0h+var_328]
0x1800dd537  lea     rcx, [rsp+3C0h+var_380]
0x1800dd53c  call    ??0?$test_data_control@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@@tip2@@IEAA@AEBV?$com_ptr_t@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@@Z; tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(wil::com_ptr_t<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>,wil::err_returncode_policy> const &)
0x1800dd541  nop
0x1800dd542  lea     rax, [rsp+3C0h+var_380]
0x1800dd547  mov     [rbp+2C0h+var_308], rax
0x1800dd54b  lea     rax, [rsp+3C0h+var_360]
0x1800dd550  mov     [rbp+2C0h+var_300], rax
0x1800dd554  lea     rax, [rsp+3C0h+Properties]
0x1800dd559  mov     [rbp+2C0h+var_2F8], rax
0x1800dd55d  lea     r13d, [r12+1]
0x1800dd562  mov     [rbp+2C0h+var_2F0], r13b
0x1800dd566  lea     r15d, [r12+2]
0x1800dd56b  cmp     [r14+18h], r12b
0x1800dd56f  jz      short loc_1800DD593
0x1800dd571  mov     r15d, 102h
0x1800dd577  lea     r9, aIdsenableetwex_5; "IdsEnableEtwExtension: AlsoRealtime is "...
0x1800dd57e  lea     r8d, [r15-26h]
0x1800dd582  lea     rdx, aIdsenableetwex_16; "IdsEnableEtwExtension::StartEtwSession"
0x1800dd589  lea     ecx, [r12+3]
0x1800dd58e  call    AslLogCallPrintf
0x1800dd593  xor     edx, edx; Val
0x1800dd595  mov     r8d, 208h; Size
0x1800dd59b  lea     rcx, [rbp+2C0h+Buffer]; void *
0x1800dd59f  call    memset_0
0x1800dd5a4  mov     edx, 104h; uSize
0x1800dd5a9  lea     rcx, [rbp+2C0h+Buffer]; lpBuffer
0x1800dd5ad  call    cs:__imp_GetWindowsDirectoryW
0x1800dd5b3  lea     rdx, [rbp+2C0h+Buffer]
0x1800dd5b7  lea     rcx, [rbp+2C0h+lpPathName]
0x1800dd5bb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dd5c0  nop
0x1800dd5c1  lea     rdx, aAppcompatPca; "\\appcompat\\pca\\"
0x1800dd5c8  lea     rcx, [rbp+2C0h+lpPathName]
0x1800dd5cc  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800dd5d1  lea     r8, aPcaetwlogEtl; "PcaEtwLog.etl"
0x1800dd5d8  lea     rdx, [rbp+2C0h+lpPathName]
0x1800dd5dc  lea     rcx, [rbp+2C0h+lpFileName]
0x1800dd5e0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x1800dd5e5  nop
0x1800dd5e6  mov     eax, [rbp+2C0h+var_288]
0x1800dd5e9  lea     edi, ds:96h[rax*2]
0x1800dd5f0  mov     ecx, edi; unsigned __int64
0x1800dd5f2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800dd5f7  mov     [rsp+3C0h+Properties], rax
0x1800dd5fc  mov     r8d, edi; Size
0x1800dd5ff  xor     edx, edx; Val
0x1800dd601  mov     rcx, rax; void *
0x1800dd604  call    memset_0
0x1800dd609  mov     rsi, [rsp+3C0h+Properties]
0x1800dd60e  mov     [rsi], edi
0x1800dd610  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800dd617  movdqu  xmmword ptr [rsi+18h], xmm0
0x1800dd61c  mov     [rsi+28h], r13d
0x1800dd620  mov     dword ptr [rsi+2Ch], 20000h
0x1800dd627  mov     [rsi+40h], r15d
0x1800dd62b  mov     eax, [r14+14h]
0x1800dd62f  mov     [rsi+3Ch], eax
0x1800dd632  mov     r15d, 3
0x1800dd638  mov     [rsi+44h], r15d
0x1800dd63c  mov     dword ptr [rsi+74h], 78h ; 'x'
0x1800dd643  mov     dword ptr [rsi+70h], 94h
0x1800dd64a  mov     rcx, [rsp+3C0h+Properties]
0x1800dd64f  lea     rbx, [rcx+94h]
0x1800dd656  lea     r11d, [rdi-94h]
0x1800dd65d  shr     r11, 1
0x1800dd660  lea     edx, [rdi-78h]
0x1800dd663  shr     rdx, 1; unsigned __int64
0x1800dd666  add     rcx, 78h ; 'x'; unsigned __int16 *
0x1800dd66a  lea     r8, aPcaetwsession; "PcaEtwSession"
0x1800dd671  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dd676  mov     edi, eax
0x1800dd678  lea     r8, [rbp+2C0h+lpFileName]
0x1800dd67c  cmp     [rbp+2C0h+var_280], 8
0x1800dd681  cmovnb  r8, [rbp+2C0h+lpFileName]; unsigned __int16 *
0x1800dd686  mov     rdx, r11; unsigned __int64
0x1800dd689  mov     rcx, rbx; unsigned __int16 *
0x1800dd68c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800dd691  test    edi, edi
0x1800dd693  js      loc_1800DDB04
0x1800dd699  test    eax, eax
0x1800dd69b  js      loc_1800DDB04
0x1800dd6a1  mov     r9d, r13d; ControlCode
0x1800dd6a4  mov     r8, rsi; Properties
0x1800dd6a7  lea     rdx, aPcaetwsession; "PcaEtwSession"
0x1800dd6ae  xor     ecx, ecx; TraceHandle
0x1800dd6b0  call    cs:__imp_ControlTraceW
0x1800dd6b6  test    eax, eax
0x1800dd6b8  jz      short loc_1800DD6E1
0x1800dd6ba  cmp     eax, 1069h
0x1800dd6bf  jz      short loc_1800DD6E1
0x1800dd6c1  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], eax
0x1800dd6c5  lea     r9, aFailedToStopEx; "Failed to stop existing session %d"
0x1800dd6cc  mov     r8d, 111h
0x1800dd6d2  lea     rdx, aIdsenableetwex_16; "IdsEnableEtwExtension::StartEtwSession"
0x1800dd6d9  mov     ecx, r13d
0x1800dd6dc  call    AslLogCallPrintf
0x1800dd6e1  lea     rcx, [rbp+2C0h+lpPathName]
0x1800dd6e5  cmp     [rbp+2C0h+var_2A0], 8
0x1800dd6ea  cmovnb  rcx, [rbp+2C0h+lpPathName]; lpPathName
0x1800dd6ef  xor     edx, edx; lpSecurityAttributes
0x1800dd6f1  call    cs:__imp_CreateDirectoryW
0x1800dd6f7  test    eax, eax
0x1800dd6f9  jnz     loc_1800DD7A4
0x1800dd6ff  call    cs:__imp_GetLastError
0x1800dd705  cmp     eax, 0B7h
0x1800dd70a  jz      loc_1800DD7A4
0x1800dd710  lea     rbx, [rbp+2C0h+lpPathName]
0x1800dd714  cmp     [rbp+2C0h+var_2A0], 8
0x1800dd719  cmovnb  rbx, [rbp+2C0h+lpPathName]
0x1800dd71e  call    cs:__imp_GetLastError
0x1800dd724  mov     [rsp+3C0h+MatchAllKeyword], rbx
0x1800dd729  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], eax
0x1800dd72d  lea     r9, aFailedToCreate_29; "Failed to create folder %d, %ws"
0x1800dd734  mov     r8d, 116h
0x1800dd73a  lea     rdx, aIdsenableetwex_16; "IdsEnableEtwExtension::StartEtwSession"
0x1800dd741  mov     ecx, r13d
0x1800dd744  call    AslLogCallPrintf
0x1800dd749  mov     rax, [rsp+3C0h+var_380]
0x1800dd74e  mov     dword ptr [rax+110h], 7
0x1800dd758  xor     r8d, r8d
0x1800dd75b  mov     dl, r13b
0x1800dd75e  lea     rcx, [rbp+2C0h+lpFileName]
0x1800dd762  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd767  nop
0x1800dd768  xor     r8d, r8d
0x1800dd76b  mov     dl, r13b
0x1800dd76e  lea     rcx, [rbp+2C0h+lpPathName]
0x1800dd772  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd777  nop
0x1800dd778  lea     rcx, [rsp+3C0h+var_380]
0x1800dd77d  call    ?close@?$test_data_control@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(void)
0x1800dd782  mov     rcx, [rbp+2C0h+var_328]
0x1800dd786  add     rcx, 8
0x1800dd78a  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x1800dd78f  mov     rcx, [rsp+3C0h+Properties]
0x1800dd794  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800dd79a  mov     ebx, 0Ah
0x1800dd79f  jmp     loc_1800DD8FF
0x1800dd7a4  lea     rcx, [rbp+2C0h+lpFileName]
0x1800dd7a8  cmp     [rbp+2C0h+var_280], 8
0x1800dd7ad  cmovnb  rcx, [rbp+2C0h+lpFileName]; lpFileName
0x1800dd7b2  call    cs:__imp_DeleteFileW
0x1800dd7b8  test    eax, eax
0x1800dd7ba  jnz     short loc_1800DD7ED
0x1800dd7bc  call    cs:__imp_GetLastError
0x1800dd7c2  cmp     eax, 2
0x1800dd7c5  jz      short loc_1800DD7ED
0x1800dd7c7  call    cs:__imp_GetLastError
0x1800dd7cd  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], eax
0x1800dd7d1  lea     r9, aIdsenableetwex_12; "IdsEnableEtwExtension: Failed to delete"...
0x1800dd7d8  mov     r8d, 11Dh
0x1800dd7de  lea     rdx, aIdsenableetwex_16; "IdsEnableEtwExtension::StartEtwSession"
0x1800dd7e5  mov     ecx, r13d
0x1800dd7e8  call    AslLogCallPrintf
0x1800dd7ed  mov     rax, [r14+28h]
0x1800dd7f1  cmp     [r14+20h], rax
0x1800dd7f5  jnz     short loc_1800DD869
0x1800dd7f7  lea     r9, aIdsenableetwex_9; "IdsEnableEtwExtension: ETW provider lis"...
0x1800dd7fe  mov     r8d, 122h
0x1800dd804  lea     rdx, aIdsenableetwex_16; "IdsEnableEtwExtension::StartEtwSession"
0x1800dd80b  mov     ecx, r15d
0x1800dd80e  call    AslLogCallPrintf
0x1800dd813  mov     rax, [rsp+3C0h+var_380]
0x1800dd818  mov     [rax+110h], r12d
0x1800dd81f  xor     r8d, r8d
0x1800dd822  mov     dl, r13b
0x1800dd825  lea     rcx, [rbp+2C0h+lpFileName]
0x1800dd829  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd82e  nop
0x1800dd82f  xor     r8d, r8d
0x1800dd832  mov     dl, r13b
0x1800dd835  lea     rcx, [rbp+2C0h+lpPathName]
0x1800dd839  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd83e  nop
0x1800dd83f  lea     rcx, [rsp+3C0h+var_380]
0x1800dd844  call    ?close@?$test_data_control@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(void)
0x1800dd849  mov     rcx, [rbp+2C0h+var_328]
0x1800dd84d  add     rcx, 8
0x1800dd851  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x1800dd856  mov     rcx, [rsp+3C0h+Properties]
0x1800dd85b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800dd861  mov     ebx, r12d
0x1800dd864  jmp     loc_1800DD8FF
0x1800dd869  mov     [rsp+3C0h+TraceHandle], r12
0x1800dd86e  mov     r8, rsi; Properties
0x1800dd871  lea     rdx, aPcaetwsession; "PcaEtwSession"
0x1800dd878  lea     rcx, [rsp+3C0h+TraceHandle]; TraceHandle
0x1800dd87d  call    cs:__imp_StartTraceW
0x1800dd883  mov     ebx, eax
0x1800dd885  test    eax, eax
0x1800dd887  jz      loc_1800DD91B
0x1800dd88d  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], eax
0x1800dd891  lea     r9, aFailedToStartt; "Failed to StartTraceW %d"
0x1800dd898  mov     r8d, 12Bh
0x1800dd89e  lea     rdx, aIdsenableetwex_16; "IdsEnableEtwExtension::StartEtwSession"
0x1800dd8a5  mov     ecx, r13d
0x1800dd8a8  call    AslLogCallPrintf
0x1800dd8ad  mov     rcx, [rsp+3C0h+var_380]
0x1800dd8b2  mov     dword ptr [rcx+110h], 6
0x1800dd8bc  xor     r8d, r8d
0x1800dd8bf  mov     dl, r13b
0x1800dd8c2  lea     rcx, [rbp+2C0h+lpFileName]
0x1800dd8c6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd8cb  nop
0x1800dd8cc  xor     r8d, r8d
0x1800dd8cf  mov     dl, r13b
0x1800dd8d2  lea     rcx, [rbp+2C0h+lpPathName]
0x1800dd8d6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd8db  nop
0x1800dd8dc  lea     rcx, [rsp+3C0h+var_380]
0x1800dd8e1  call    ?close@?$test_data_control@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@@tip2@@QEAAXXZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::close(void)
0x1800dd8e6  mov     rcx, [rbp+2C0h+var_328]
0x1800dd8ea  add     rcx, 8
0x1800dd8ee  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x1800dd8f3  mov     rcx, [rsp+3C0h+Properties]
0x1800dd8f8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800dd8fe  nop
0x1800dd8ff  lea     rcx, [rsp+3C0h+var_380]
0x1800dd904  call    ??1?$test_data_control@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_data_control<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(void)
0x1800dd909  nop
0x1800dd90a  lea     rcx, [rsp+3C0h+var_360]
0x1800dd90f  call    ??1?$test_watcher@V?$merged_data@U_tip_IdsEnableEtwModelTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>::~test_watcher<tip2::details::merged_data<_tip_IdsEnableEtwModelTip,_tip_IdsEnableEtwModelTip>>(void)
0x1800dd914  mov     eax, ebx
0x1800dd916  jmp     loc_1800DDB91
0x1800dd91b  mov     r15, r12
0x1800dd91e  mov     rbx, [r14+20h]
0x1800dd922  mov     rdi, [r14+28h]
0x1800dd926  cmp     rbx, rdi
0x1800dd929  jz      loc_1800DDA47
0x1800dd92f  mov     rsi, [rbx+18h]
0x1800dd933  sub     rsi, [rbx+10h]
0x1800dd937  sar     rsi, 1
0x1800dd93a  mov     r13d, r12d
0x1800dd93d  test    esi, esi
0x1800dd93f  setnz   r13b
0x1800dd943  test    esi, esi
0x1800dd945  mov     r12d, 6
0x1800dd94b  jz      short loc_1800DD955
0x1800dd94d  lea     r12d, ds:4[rsi*2]
0x1800dd955  mov     edx, r12d
0x1800dd958  lea     rcx, [rbp+2C0h+var_320]
0x1800dd95c  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_K@Z; std::vector<uchar>::vector<uchar>(unsigned __int64)
0x1800dd961  nop
0x1800dd962  mov     r8, [rbp+2C0h+var_320]
0x1800dd966  mov     r10d, 1
0x1800dd96c  mov     [r8], r10b
0x1800dd96f  mov     [r8+2], si
0x1800dd974  xor     r9d, r9d
0x1800dd977  xor     eax, eax
0x1800dd979  cmp     ax, si
0x1800dd97c  jnb     short loc_1800DD99B
0x1800dd97e  movzx   edx, r9w
0x1800dd982  mov     rax, [rbx+10h]
0x1800dd986  movzx   ecx, word ptr [rax+rdx*2]
0x1800dd98a  mov     [r8+rdx*2+4], cx
0x1800dd990  add     r9w, r10w
0x1800dd994  cmp     r9w, [r8+2]
0x1800dd999  jb      short loc_1800DD97E
0x1800dd99b  mov     [rbp+2C0h+var_278], r8
0x1800dd99f  mov     [rbp+2C0h+var_270], r12d
0x1800dd9a3  mov     [rbp+2C0h+var_26C], 80000200h
0x1800dd9aa  xorps   xmm0, xmm0
0x1800dd9ad  movdqu  xmmword ptr [rbp+2C0h+var_2E8.SourceId.Data1], xmm0
0x1800dd9b2  xor     r12d, r12d
0x1800dd9b5  mov     dword ptr [rbp+2C0h+var_2E8+1Ch], r12d
0x1800dd9b9  mov     dword ptr [rbp+2C0h+var_2E8+2Ch], r12d
0x1800dd9bd  mov     qword ptr [rbp+2C0h+var_2E8.Version], 2
0x1800dd9c5  mov     [rbp+2C0h+var_2E8.ControlFlags], r12d
0x1800dd9c9  lea     rcx, [rbp+2C0h+var_278]
0x1800dd9cd  test    esi, esi
0x1800dd9cf  cmovz   rcx, r12
0x1800dd9d3  mov     [rbp+2C0h+var_2E8.EnableFilterDesc], rcx
0x1800dd9d7  mov     [rbp+2C0h+var_2E8.FilterDescCount], r13d
0x1800dd9db  lea     rax, [rbp+2C0h+var_2E8]
0x1800dd9df  mov     [rsp+3C0h+EnableParameters], rax; EnableParameters
0x1800dd9e4  mov     [rsp+3C0h+Timeout], r12d; Timeout
0x1800dd9e9  mov     [rsp+3C0h+MatchAllKeyword], r12; MatchAllKeyword
0x1800dd9ee  mov     [rsp+3C0h+MatchAnyKeyword], 0FFFFFFFFFFFFFFFFh; MatchAnyKeyword
0x1800dd9f7  mov     r9b, 4; Level
0x1800dd9fa  mov     r13, r10
  ... truncated ...
```
