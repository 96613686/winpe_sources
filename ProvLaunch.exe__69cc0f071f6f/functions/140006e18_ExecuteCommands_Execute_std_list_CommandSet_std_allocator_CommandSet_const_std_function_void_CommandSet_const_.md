# ExecuteCommands::Execute(std::list<CommandSet,std::allocator<CommandSet>> const &,std::function<void (CommandSet const &,Command const &)>,std::function<void (CommandSet const &,Command const &,ulong)>)

- ea: `0x140006e18`
- end: `0x140007b30`
- name: `?Execute@ExecuteCommands@@SAJAEBV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@V?$function@$$A6AXAEBUCommandSet@@AEBUCommand@@@Z@3@V?$function@$$A6AXAEBUCommandSet@@AEBUCommand@@K@Z@3@@Z`
- size: `3352`
- prototype: `__int64 __fastcall(_QWORD **, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000693c`

## callees

- `0x14000124c`
- `0x14000132c`
- `0x140001424`
- `0x140006b38`
- `0x140006e18`
- `0x140007b38`
- `0x140007bd8`
- `0x140008370`
- `0x1400088ac`
- `0x14000972c`
- `0x14000a33e`
- `0x14000a370`
- `0x14000b010`

## import_xrefs

- `msvcp110_win!?_Xbad_function_call@std@@YAXXZ` at `0x140006ef3`
- `msvcp110_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400075d8`
- `msvcp110_win!?_Xbad_function_call@std@@YAXXZ` at `0x140006ef3`
- `msvcp110_win!?_Xbad_function_call@std@@YAXXZ` at `0x1400075d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400077d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400079a6`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007a3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400077d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400079a6`
- `msvcrt!??3@YAXPEAX@Z` at `0x140007a3c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400073ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400073ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000732c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400074d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000732c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007402`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400074d2`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140007230`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140007230`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000748d`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000748d`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140006ec4`
- `api-ms-win-core-processthreads-l1-1-0!GetStartupInfoW` at `0x140006ec4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000797c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a26`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400077bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000797c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007a26`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x14000713d`
- `api-ms-win-shell-shdirectory-l1-1-0!__imp_SHCreateDirectoryExW` at `0x14000713d`

## string_xrefs

- `0x14000775c`: `SOFTWARE\Microsoft\Provisioning\Commands`

## pseudocode

```c
__int64 __fastcall ExecuteCommands::Execute(_QWORD **a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  _QWORD **v4; // r12
  _QWORD *v5; // r14
  _QWORD *v6; // rbx
  __int64 **v7; // r15
  __int64 *v8; // rsi
  __int64 v9; // rcx
  _QWORD *v10; // r13
  int v11; // r8d
  int v12; // r9d
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rdx
  _QWORD *v16; // rcx
  char *v17; // r8
  LPWSTR v18; // rcx
  LPWSTR v19; // rdx
  signed __int64 v20; // rbx
  signed __int64 v21; // rcx
  unsigned __int64 v22; // r9
  unsigned __int64 v23; // rdx
  signed __int64 v24; // rcx
  unsigned __int64 v25; // r9
  unsigned __int64 v26; // rdx
  const WCHAR *v27; // rbx
  int v28; // eax
  int v29; // r9d
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  LPWSTR v32; // rbx
  int v33; // r8d
  int v34; // r9d
  _QWORD *v35; // rcx
  LPWSTR v36; // rcx
  char *hProcess; // rbx
  int v38; // r8d
  int v39; // r9d
  _QWORD *v40; // rcx
  char *hThread; // rdi
  int v42; // r8d
  int v43; // r9d
  _QWORD *v44; // rcx
  int v45; // r8d
  int v46; // r9d
  int v47; // r8d
  int v48; // r9d
  _QWORD *v49; // rax
  _QWORD *v50; // rcx
  _QWORD *v51; // rax
  _QWORD *v52; // rcx
  __int64 v53; // rcx
  int v54; // r8d
  int v55; // r9d
  _QWORD *v56; // rax
  _QWORD *v57; // rcx
  _QWORD *v58; // rax
  const unsigned __int16 *v59; // rdx
  const unsigned __int16 *v60; // r8
  _QWORD *v61; // rax
  _QWORD *v62; // rcx
  int v63; // ecx
  _QWORD *v64; // rax
  __int64 v65; // rdi
  __int64 v66; // rcx
  __int64 v67; // rdi
  __int64 v68; // rcx
  __int64 v70; // rcx
  __int64 v71; // rbx
  __int64 v72; // rcx
  const WCHAR *lpCurrentDirectory; // [rsp+38h] [rbp-190h]
  _QWORD *v74; // [rsp+50h] [rbp-178h] BYREF
  DWORD ExitCode; // [rsp+58h] [rbp-170h] BYREF
  _QWORD *v76; // [rsp+60h] [rbp-168h] BYREF
  __int16 v77; // [rsp+68h] [rbp-160h] BYREF
  _QWORD *v78; // [rsp+70h] [rbp-158h] BYREF
  unsigned int v79; // [rsp+78h] [rbp-150h]
  DWORD v80; // [rsp+7Ch] [rbp-14Ch] BYREF
  LPWSTR lpCommandLine[2]; // [rsp+80h] [rbp-148h] BYREF
  WCHAR *v82; // [rsp+90h] [rbp-138h]
  __int64 v83; // [rsp+98h] [rbp-130h]
  HANDLE v84; // [rsp+A0h] [rbp-128h] BYREF
  DWORD v85; // [rsp+A8h] [rbp-120h] BYREF
  DWORD v86; // [rsp+ACh] [rbp-11Ch] BYREF
  DWORD LastError; // [rsp+B0h] [rbp-118h] BYREF
  int v88; // [rsp+B4h] [rbp-114h] BYREF
  __int64 v89; // [rsp+B8h] [rbp-110h]
  _QWORD v90[3]; // [rsp+C0h] [rbp-108h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+D8h] [rbp-F0h] BYREF
  HANDLE v92; // [rsp+F0h] [rbp-D8h]
  _STARTUPINFOW StartupInfo; // [rsp+100h] [rbp-C8h] BYREF
  __int64 v94; // [rsp+170h] [rbp-58h] BYREF
  __int16 v95[8]; // [rsp+178h] [rbp-50h] BYREF
  __int64 v96; // [rsp+188h] [rbp-40h]
  __int64 v97; // [rsp+190h] [rbp-38h]

  v89 = a3;
  v3 = a2;
  v83 = a2;
  v90[1] = a2;
  v90[2] = a3;
  v79 = 0;
  v4 = (_QWORD **)*a1;
  v5 = (_QWORD *)**a1;
LABEL_2:
  if ( v5 != v4 )
  {
    v6 = v5 + 2;
    v90[0] = v5 + 2;
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    memset_0(&StartupInfo.cb + 1, 0, 0x64u);
    StartupInfo.cb = 104;
    GetStartupInfoW(&StartupInfo);
    StartupInfo.dwFlags |= 1u;
    StartupInfo.wShowWindow = 0;
    v7 = (__int64 **)v5[3];
    v8 = *v7;
    while ( 1 )
    {
      if ( v8 == (__int64 *)v7 )
        goto LABEL_137;
      v9 = *(_QWORD *)(v3 + 24);
      if ( !v9 )
        std::_Xbad_function_call();
      v10 = v8 + 2;
      (*(void (__fastcall **)(__int64, _QWORD *, __int64 *))(*(_QWORD *)v9 + 16LL))(v9, v6, v8 + 2);
      if ( (unsigned int)dword_140010000 > 4
        && (qword_140010010 & 0x400000000000LL) != 0
        && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
      {
        if ( (unsigned __int64)v8[5] < 8 )
          v13 = v8 + 2;
        else
          v13 = (_QWORD *)*v10;
        v74 = v13;
        v14 = v6 + 3;
        if ( v6[6] >= 8u )
          v14 = (_QWORD *)*v14;
        v78 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          qword_140010018,
          (unsigned int)&byte_14000D4F7,
          v11,
          v12,
          (__int64)&v78,
          (__int64)&v74);
      }
      v15 = v8 + 6;
      if ( (unsigned __int64)v8[9] < 8 )
        v16 = v8 + 6;
      else
        v16 = (_QWORD *)*v15;
      v17 = (char *)v16 + 2 * v8[8];
      if ( (unsigned __int64)v8[9] >= 8 )
        v15 = (_QWORD *)*v15;
      *(_OWORD *)lpCommandLine = 0;
      v82 = 0;
      std::vector<unsigned short>::_Construct<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>(
        lpCommandLine,
        v15,
        v17);
      v77 = 0;
      v18 = lpCommandLine[1];
      v19 = lpCommandLine[0];
      if ( (LPWSTR)&v77 >= lpCommandLine[1] || lpCommandLine[0] > (LPWSTR)&v77 )
      {
        if ( lpCommandLine[1] == v82 && !(v82 - lpCommandLine[1]) )
        {
          v24 = lpCommandLine[1] - lpCommandLine[0];
          if ( v24 == 0x7FFFFFFFFFFFFFFFLL )
            std::vector<unsigned short>::_Xlen(0x7FFFFFFFFFFFFFFFLL, lpCommandLine[0]);
          v25 = v82 - lpCommandLine[0];
          v26 = 0;
          if ( 0x7FFFFFFFFFFFFFFFLL - (v25 >> 1) >= v25 )
            v26 = v25 + (v25 >> 1);
          if ( v26 < v24 + 1 )
            v26 = v24 + 1;
          std::vector<unsigned short>::_Reallocate(lpCommandLine, v26);
          v18 = lpCommandLine[1];
        }
        *v18 = 0;
      }
      else
      {
        v20 = (char *)&v77 - (char *)lpCommandLine[0];
        if ( lpCommandLine[1] == v82 && !(v82 - lpCommandLine[1]) )
        {
          v21 = lpCommandLine[1] - lpCommandLine[0];
          if ( v21 == 0x7FFFFFFFFFFFFFFFLL )
            std::vector<unsigned short>::_Xlen(0x7FFFFFFFFFFFFFFFLL, lpCommandLine[0]);
          v22 = v82 - lpCommandLine[0];
          v23 = 0;
          if ( 0x7FFFFFFFFFFFFFFFLL - (v22 >> 1) >= v22 )
            v23 = v22 + (v22 >> 1);
          if ( v23 < v21 + 1 )
            v23 = v21 + 1;
          std::vector<unsigned short>::_Reallocate(lpCommandLine, v23);
          v18 = lpCommandLine[1];
          v19 = lpCommandLine[0];
        }
        *v18 = v19[v20 >> 1];
      }
      lpCommandLine[1] = v18 + 1;
      v27 = (const WCHAR *)(v8 + 10);
      if ( (unsigned __int64)v8[13] >= 8 )
        v27 = *(const WCHAR **)v27;
      if ( !*v27 )
        goto LABEL_56;
      v28 = SHCreateDirectoryExW(0, v27, 0);
      if ( v28 )
      {
        if ( v28 != 80 && v28 != 183 )
          break;
      }
LABEL_57:
      lpCurrentDirectory = v27;
      v32 = lpCommandLine[0];
      if ( CreateProcessW(
             0,
             lpCommandLine[0],
             0,
             0,
             0,
             0x8000020u,
             0,
             lpCurrentDirectory,
             &StartupInfo,
             &ProcessInformation) )
      {
        hProcess = (char *)ProcessInformation.hProcess;
        if ( ProcessInformation.hProcess )
        {
          v84 = ProcessInformation.hProcess;
          hThread = (char *)ProcessInformation.hThread;
          v92 = ProcessInformation.hThread;
          LODWORD(v78) = WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF);
          if ( (_DWORD)v78 )
          {
            if ( (unsigned int)dword_140010000 > 2 )
            {
              a2 = 0x400000000000LL;
              if ( (qword_140010010 & 0x400000000000LL) != 0 && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
              {
                LastError = GetLastError();
                v88 = (int)v78;
                if ( (unsigned __int64)v8[5] >= 8 )
                  v10 = (_QWORD *)*v10;
                v76 = v10;
                v44 = v5 + 5;
                if ( v5[8] >= 8u )
                  v44 = (_QWORD *)*v44;
                v74 = v44;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  (_DWORD)v44,
                  (unsigned int)byte_14000D3D9,
                  v42,
                  v43,
                  (__int64)&v74,
                  (__int64)&v76,
                  (__int64)&v88,
                  (__int64)&LastError);
              }
            }
          }
          else
          {
            ExitCode = 0;
            if ( !GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode)
              && (unsigned int)dword_140010000 > 2
              && (qword_140010010 & 0x400000000000LL) != 0
              && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
            {
              v80 = GetLastError();
              if ( (unsigned __int64)v8[5] < 8 )
                v49 = v8 + 2;
              else
                v49 = (_QWORD *)*v10;
              v76 = v49;
              v50 = v5 + 5;
              if ( v5[8] >= 8u )
                v50 = (_QWORD *)*v50;
              v74 = v50;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (_DWORD)v50,
                (unsigned int)&byte_14000D2B7,
                v47,
                v48,
                (__int64)&v74,
                (__int64)&v76,
                (__int64)&v80);
            }
            if ( (unsigned int)dword_140010000 > 4
              && (qword_140010010 & 0x400000000000LL) != 0
              && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
            {
              LODWORD(v78) = ExitCode;
              if ( (unsigned __int64)v8[5] < 8 )
                v51 = v8 + 2;
              else
                v51 = (_QWORD *)*v10;
              v76 = v51;
              v52 = v5 + 5;
              if ( v5[8] >= 8u )
                v52 = (_QWORD *)*v52;
              v74 = v52;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (_DWORD)v52,
                (unsigned int)&dword_14000D274,
                v45,
                v46,
                (__int64)&v74,
                (__int64)&v76,
                (__int64)&v78);
            }
            LODWORD(v78) = ExitCode;
            v53 = *(_QWORD *)(v89 + 24);
            if ( !v53 )
              std::_Xbad_function_call();
            (*(void (__fastcall **)(__int64, _QWORD *, __int64 *, _QWORD **))(*(_QWORD *)v53 + 16LL))(
              v53,
              v5 + 2,
              v8 + 2,
              &v78);
            if ( ExitCode == *((_DWORD *)v8 + 30) || ExitCode == *((_DWORD *)v8 + 31) )
            {
              a2 = 0x400000000000LL;
              if ( (unsigned int)dword_140010000 > 4
                && (qword_140010010 & 0x400000000000LL) != 0
                && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
              {
                LODWORD(v78) = ExitCode;
                LODWORD(v74) = *((_DWORD *)v8 + 28);
                if ( (unsigned __int64)v8[5] < 8 )
                  v61 = v8 + 2;
                else
                  v61 = (_QWORD *)*v10;
                v76 = v61;
                v62 = v5 + 5;
                if ( v5[8] >= 8u )
                  v62 = (_QWORD *)*v62;
                v84 = v62;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                  (_DWORD)v62,
                  (unsigned int)byte_14000D315,
                  v54,
                  v55,
                  (__int64)&v84,
                  (__int64)&v76,
                  (__int64)&v74,
                  (__int64)&v78);
                a2 = 0x400000000000LL;
              }
              v63 = v79;
              if ( ExitCode == *((_DWORD *)v8 + 31) )
                v63 = -2147021886;
              v79 = v63;
              if ( *((_DWORD *)v8 + 28) )
              {
                if ( (unsigned int)dword_140010000 > 4
                  && (qword_140010010 & 0x400000000000LL) != 0
                  && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
                {
                  LODWORD(v74) = ExitCode;
                  v80 = *((_DWORD *)v8 + 28);
                  if ( (unsigned __int64)v8[5] >= 8 )
                    v10 = (_QWORD *)*v10;
                  v84 = v10;
                  v64 = (_QWORD *)(v90[0] + 24LL);
                  if ( *(_QWORD *)(v90[0] + 48LL) >= 8u )
                    v64 = (_QWORD *)*v64;
                  v90[0] = v64;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                    qword_140010018,
                    (unsigned int)&unk_14000D498,
                    v54,
                    v55,
                    (__int64)v90,
                    (__int64)&v84,
                    (__int64)&v80,
                    (__int64)&v74);
                }
                if ( (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  CloseHandle(hThread);
                if ( (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  CloseHandle(hProcess);
                if ( lpCommandLine[0] )
                  operator delete(lpCommandLine[0]);
                v65 = v83;
                v66 = *(_QWORD *)(v83 + 24);
                if ( v66 )
                {
                  LOBYTE(a2) = v66 != v83;
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 32LL))(v66, a2);
                  *(_QWORD *)(v65 + 24) = 0;
                }
                v67 = v89;
                v68 = *(_QWORD *)(v89 + 24);
                if ( v68 )
                {
                  LOBYTE(a2) = v68 != v89;
                  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v68 + 32LL))(v68, a2);
                  *(_QWORD *)(v67 + 24) = 0;
                }
                return 2147945410LL;
              }
            }
            else
            {
              a2 = 0x400000000000LL;
              if ( (unsigned int)dword_140010000 > 2
                && (qword_140010010 & 0x400000000000LL) != 0
                && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
              {
                LODWORD(v78) = ExitCode;
                if ( (unsigned __int64)v8[5] < 8 )
                  v56 = v8 + 2;
                else
                  v56 = (_QWORD *)*v10;
                v76 = v56;
                v57 = v5 + 5;
                if ( v5[8] >= 8u )
                  v57 = (_QWORD *)*v57;
                v74 = v57;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                  (_DWORD)v57,
                  (unsigned int)byte_14000D381,
                  v54,
                  v55,
                  (__int64)&v74,
                  (__int64)&v76,
                  (__int64)&v78);
                a2 = 0x400000000000LL;
              }
              if ( !*((_DWORD *)v8 + 29) )
              {
                if ( (unsigned int)dword_140010000 > 2
                  && (qword_140010010 & 0x400000000000LL) != 0
                  && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
                {
                  LODWORD(v78) = ExitCode;
                  if ( (unsigned __int64)v8[5] >= 8 )
                    v10 = (_QWORD *)*v10;
                  v76 = v10;
                  v58 = v5 + 5;
                  if ( v5[8] >= 8u )
                    v58 = (_QWORD *)*v58;
                  v74 = v58;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                    qword_140010018,
                    (unsigned int)&byte_14000D21F,
                    v54,
                    v55,
                    (__int64)&v74,
                    (__int64)&v76,
                    (__int64)&v78);
                }
                v94 = -2147483646;
                v97 = 7;
                v96 = 0;
                v95[0] = 0;
                std::wstring::assign(v95, L"SOFTWARE\\Microsoft\\Provisioning\\Commands");
                v60 = (const unsigned __int16 *)(v5 + 5);
                if ( v5[8] >= 8u )
                  v60 = *(const unsigned __int16 **)v60;
                RegistryConfig::DeleteCommandSet((RegistryConfig *)&v94, v59, v60);
                RegistryConfig::~RegistryConfig((RegistryConfig *)&v94);
                if ( (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  CloseHandle(hThread);
                if ( (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  CloseHandle(hProcess);
                if ( lpCommandLine[0] )
                  operator delete(lpCommandLine[0]);
                v3 = v83;
LABEL_137:
                v5 = (_QWORD *)*v5;
                goto LABEL_2;
              }
            }
          }
          if ( (unsigned __int64)(hThread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(hThread);
          if ( (unsigned __int64)(hProcess - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(hProcess);
        }
        else if ( (unsigned int)dword_140010000 > 2 )
        {
          a2 = 0x400000000000LL;
          if ( (qword_140010010 & 0x400000000000LL) != 0 && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
          {
            v86 = GetLastError();
            if ( (unsigned __int64)v8[5] >= 8 )
              v10 = (_QWORD *)*v10;
            v76 = v10;
            v40 = v5 + 5;
            if ( v5[8] >= 8u )
              v40 = (_QWORD *)*v40;
            v74 = v40;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (_DWORD)v40,
              (unsigned int)byte_14000D531,
              v38,
              v39,
              (__int64)&v74,
              (__int64)&v76,
              (__int64)&v86);
          }
        }
        v36 = lpCommandLine[0];
        if ( lpCommandLine[0] )
          goto LABEL_174;
      }
      else
      {
        if ( (unsigned int)dword_140010000 > 2 )
        {
          a2 = 0x400000000000LL;
          if ( (qword_140010010 & 0x400000000000LL) != 0 && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
          {
            v85 = GetLastError();
            if ( (unsigned __int64)v8[5] >= 8 )
              v10 = (_QWORD *)*v10;
            v76 = v10;
            v35 = v5 + 5;
            if ( v5[8] >= 8u )
              v35 = (_QWORD *)*v35;
            v74 = v35;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (_DWORD)v35,
              (unsigned int)&dword_14000D1CC,
              v33,
              v34,
              (__int64)&v74,
              (__int64)&v76,
              (__int64)&v85);
          }
        }
        if ( v32 )
        {
          v36 = v32;
LABEL_174:
          operator delete(v36);
        }
      }
      v8 = (__int64 *)*v8;
      v6 = v5 + 2;
      v3 = v83;
    }
    if ( (unsigned int)dword_140010000 > 2
      && (qword_140010010 & 0x400000000000LL) != 0
      && (qword_140010018 & 0x400000000000LL) == qword_140010018 )
    {
      LODWORD(v78) = v28;
      if ( (unsigned __int64)v8[5] < 8 )
        v30 = v8 + 2;
      else
        v30 = (_QWORD *)*v10;
      v74 = v30;
      v31 = v5 + 5;
      if ( v5[8] >= 8u )
        v31 = (_QWORD *)*v31;
      v76 = v31;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v31,
        (unsigned int)&dword_14000D43C,
        0,
        v29,
        (__int64)&v76,
        (__int64)&v74,
        (__int64)&v78);
    }
LABEL_56:
    v27 = 0;
    goto LABEL_57;
  }
  v70 = *(_QWORD *)(v3 + 24);
  if ( v70 )
  {
    LOBYTE(a2) = v70 != v3;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v70 + 32LL))(v70, a2);
    *(_QWORD *)(v3 + 24) = 0;
  }
  v71 = v89;
  v72 = *(_QWORD *)(v89 + 24);
  if ( v72 )
  {
    LOBYTE(a2) = v72 != v89;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 32LL))(v72, a2);
    *(_QWORD *)(v71 + 24) = 0;
  }
  return v79;
}

```

## disassembly

```asm
0x140006e18  mov     r11, rsp
0x140006e1b  mov     [r11+8], rbx
0x140006e1f  mov     [r11+20h], rsi
0x140006e23  push    rdi
0x140006e24  push    r12
0x140006e26  push    r13
0x140006e28  push    r14
0x140006e2a  push    r15
0x140006e2c  sub     rsp, 1A0h
0x140006e33  mov     rax, cs:__security_cookie
0x140006e3a  xor     rax, rsp
0x140006e3d  mov     [rsp+1C8h+var_30], rax
0x140006e45  mov     rbx, r8
0x140006e48  mov     [r11-110h], rbx
0x140006e4f  mov     r13, rdx
0x140006e52  mov     [r11-130h], rdx
0x140006e59  mov     [r11-100h], rdx
0x140006e60  mov     [r11-0F8h], rbx
0x140006e67  xor     edi, edi
0x140006e69  mov     [rsp+1C8h+var_150], edi
0x140006e6d  mov     r12, [rcx]
0x140006e70  mov     r14, [r12]
0x140006e74  cmp     r14, r12
0x140006e77  jz      loc_140007A56
0x140006e7d  lea     rbx, [r14+10h]
0x140006e81  mov     [rsp+1C8h+var_108], rbx
0x140006e89  xorps   xmm0, xmm0
0x140006e8c  xor     eax, eax
0x140006e8e  movups  xmmword ptr [rsp+1C8h+ProcessInformation.hProcess], xmm0
0x140006e96  mov     qword ptr [rsp+1C8h+ProcessInformation.dwProcessId], rax
0x140006e9e  xor     edx, edx; Val
0x140006ea0  lea     r8d, [rax+64h]; Size
0x140006ea4  lea     rcx, [rsp+1C8h+StartupInfo+4]; void *
0x140006eac  call    memset_0
0x140006eb1  mov     [rsp+1C8h+StartupInfo.cb], 68h ; 'h'
0x140006ebc  lea     rcx, [rsp+1C8h+StartupInfo]; lpStartupInfo
0x140006ec4  call    cs:__imp_GetStartupInfoW
0x140006eca  or      [rsp+1C8h+StartupInfo.dwFlags], 1
0x140006ed2  mov     [rsp+1C8h+StartupInfo.wShowWindow], di
0x140006eda  mov     r15, [rbx+8]
0x140006ede  mov     rsi, [r15]
0x140006ee1  cmp     rsi, r15
0x140006ee4  jz      loc_1400077E0
0x140006eea  mov     rcx, [r13+18h]
0x140006eee  test    rcx, rcx
0x140006ef1  jnz     short loc_140006EF9
0x140006ef3  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x140006ef9  lea     r13, [rsi+10h]
0x140006efd  mov     rax, [rcx]
0x140006f00  mov     r8, r13
0x140006f03  mov     rdx, rbx
0x140006f06  mov     rax, [rax+10h]
0x140006f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f0f  mov     eax, cs:dword_140010000
0x140006f15  cmp     eax, 4
0x140006f18  jbe     short loc_140006F8A
0x140006f1a  mov     rcx, cs:qword_140010018
0x140006f21  mov     rax, cs:qword_140010010
0x140006f28  mov     rdx, 400000000000h
0x140006f32  test    rdx, rax
0x140006f35  jz      short loc_140006F8A
0x140006f37  mov     rax, rcx
0x140006f3a  and     rax, rdx
0x140006f3d  cmp     rax, rcx
0x140006f40  jnz     short loc_140006F8A
0x140006f42  cmp     qword ptr [r13+18h], 8
0x140006f47  jb      short loc_140006F4F
0x140006f49  mov     rax, [r13+0]
0x140006f4d  jmp     short loc_140006F52
0x140006f4f  mov     rax, r13
0x140006f52  mov     [rsp+1C8h+var_178], rax
0x140006f57  lea     rax, [rbx+18h]
0x140006f5b  cmp     qword ptr [rbx+30h], 8
0x140006f60  jb      short loc_140006F65
0x140006f62  mov     rax, [rax]
0x140006f65  mov     [rsp+1C8h+var_158], rax
0x140006f6a  lea     rax, [rsp+1C8h+var_178]
0x140006f6f  mov     qword ptr [rsp+1C8h+dwCreationFlags], rax
0x140006f74  lea     rax, [rsp+1C8h+var_158]
0x140006f79  mov     qword ptr [rsp+1C8h+bInheritHandles], rax
0x140006f7e  lea     rdx, byte_14000D4F7
0x140006f85  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140006f8a  lea     rdx, [r13+20h]
0x140006f8e  cmp     qword ptr [r13+38h], 8
0x140006f93  jb      short loc_140006F9A
0x140006f95  mov     rcx, [rdx]
0x140006f98  jmp     short loc_140006F9D
0x140006f9a  mov     rcx, rdx
0x140006f9d  mov     rax, [rdx+10h]
0x140006fa1  lea     r8, [rcx+rax*2]
0x140006fa5  jb      short loc_140006FAA
0x140006fa7  mov     rdx, [rdx]
0x140006faa  xorps   xmm0, xmm0
0x140006fad  movdqu  xmmword ptr [rsp+1C8h+lpCommandLine], xmm0
0x140006fb6  mov     [rsp+1C8h+var_138], rdi
0x140006fbe  lea     rcx, [rsp+1C8h+lpCommandLine]
0x140006fc6  call    ??$_Construct@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@?$vector@GV?$allocator@G@std@@@std@@QEAAXV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0@Z; std::vector<ushort>::_Construct<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x140006fcb  nop
0x140006fcc  mov     [rsp+1C8h+var_160], di
0x140006fd1  lea     rax, [rsp+1C8h+var_160]
0x140006fd6  mov     rcx, [rsp+1C8h+lpCommandLine+8]
0x140006fde  mov     rdx, [rsp+1C8h+lpCommandLine]
0x140006fe6  cmp     rax, rcx
0x140006fe9  jnb     loc_140007094
0x140006fef  lea     rax, [rsp+1C8h+var_160]
0x140006ff4  cmp     rdx, rax
0x140006ff7  ja      loc_140007094
0x140006ffd  lea     rbx, [rsp+1C8h+var_160]
0x140007002  sub     rbx, rdx
0x140007005  mov     r9, [rsp+1C8h+var_138]
0x14000700d  cmp     rcx, r9
0x140007010  jnz     short loc_140007088
0x140007012  mov     rax, r9
0x140007015  sub     rax, rcx
0x140007018  sar     rax, 1
0x14000701b  cmp     rax, 1
0x14000701f  jnb     short loc_140007088
0x140007021  sub     rcx, rdx
0x140007024  sar     rcx, 1
0x140007027  mov     r10, 7FFFFFFFFFFFFFFFh
0x140007031  mov     rax, r10
0x140007034  sub     rax, rcx
0x140007037  cmp     rax, 1
0x14000703b  jb      loc_140007B23
0x140007041  lea     r8, [rcx+1]
0x140007045  sub     r9, rdx
0x140007048  sar     r9, 1
0x14000704b  mov     rax, r9
0x14000704e  shr     rax, 1
0x140007051  mov     rcx, r10
0x140007054  sub     rcx, rax
0x140007057  add     rax, r9
0x14000705a  mov     rdx, rdi
0x14000705d  cmp     rcx, r9
0x140007060  cmovnb  rdx, rax
0x140007064  cmp     rdx, r8
0x140007067  cmovb   rdx, r8
0x14000706b  lea     rcx, [rsp+1C8h+lpCommandLine]
0x140007073  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x140007078  mov     rcx, [rsp+1C8h+lpCommandLine+8]
0x140007080  mov     rdx, [rsp+1C8h+lpCommandLine]
0x140007088  sar     rbx, 1
0x14000708b  movzx   eax, word ptr [rdx+rbx*2]
0x14000708f  mov     [rcx], ax
0x140007092  jmp     short loc_140007112
0x140007094  mov     r9, [rsp+1C8h+var_138]
0x14000709c  cmp     rcx, r9
0x14000709f  jnz     short loc_14000710F
0x1400070a1  mov     rax, r9
0x1400070a4  sub     rax, rcx
0x1400070a7  sar     rax, 1
0x1400070aa  cmp     rax, 1
0x1400070ae  jnb     short loc_14000710F
0x1400070b0  sub     rcx, rdx
0x1400070b3  sar     rcx, 1
0x1400070b6  mov     r10, 7FFFFFFFFFFFFFFFh
0x1400070c0  mov     rax, r10
0x1400070c3  sub     rax, rcx
0x1400070c6  cmp     rax, 1
0x1400070ca  jb      loc_140007B29
0x1400070d0  lea     r8, [rcx+1]
0x1400070d4  sub     r9, rdx
0x1400070d7  sar     r9, 1
0x1400070da  mov     rax, r9
0x1400070dd  shr     rax, 1
0x1400070e0  mov     rcx, r10
0x1400070e3  sub     rcx, rax
0x1400070e6  add     rax, r9
0x1400070e9  mov     rdx, rdi
0x1400070ec  cmp     rcx, r9
0x1400070ef  cmovnb  rdx, rax
0x1400070f3  cmp     rdx, r8
0x1400070f6  cmovb   rdx, r8
0x1400070fa  lea     rcx, [rsp+1C8h+lpCommandLine]
0x140007102  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x140007107  mov     rcx, [rsp+1C8h+lpCommandLine+8]
0x14000710f  mov     [rcx], di
0x140007112  add     rcx, 2
0x140007116  mov     [rsp+1C8h+lpCommandLine+8], rcx
0x14000711e  lea     rbx, [r13+40h]
0x140007122  cmp     qword ptr [r13+58h], 8
0x140007127  jb      short loc_14000712C
0x140007129  mov     rbx, [rbx]
0x14000712c  cmp     di, [rbx]
0x14000712f  jz      loc_1400071EA
0x140007135  xor     r8d, r8d; psa
0x140007138  mov     rdx, rbx; pszPath
0x14000713b  xor     ecx, ecx; hwnd
0x14000713d  call    cs:__imp_SHCreateDirectoryExW
0x140007143  mov     ecx, eax
0x140007145  test    eax, eax
0x140007147  jz      loc_1400071ED
0x14000714d  cmp     eax, 50h ; 'P'
0x140007150  jz      loc_1400071ED
0x140007156  cmp     eax, 0B7h
0x14000715b  jz      loc_1400071ED
0x140007161  mov     eax, cs:dword_140010000
0x140007167  cmp     eax, 2
0x14000716a  jbe     short loc_1400071EA
0x14000716c  mov     rdx, cs:qword_140010018
0x140007173  mov     rax, cs:qword_140010010
0x14000717a  mov     r8, 400000000000h
0x140007184  test    r8, rax
0x140007187  jz      short loc_1400071EA
0x140007189  mov     rax, rdx
0x14000718c  and     rax, r8
0x14000718f  cmp     rax, rdx
0x140007192  jnz     short loc_1400071EA
0x140007194  mov     dword ptr [rsp+1C8h+var_158], ecx
0x140007198  cmp     qword ptr [r13+18h], 8
0x14000719d  jb      short loc_1400071A5
0x14000719f  mov     rax, [r13+0]
0x1400071a3  jmp     short loc_1400071A8
0x1400071a5  mov     rax, r13
0x1400071a8  mov     [rsp+1C8h+var_178], rax
0x1400071ad  lea     rcx, [r14+28h]
0x1400071b1  cmp     qword ptr [r14+40h], 8
0x1400071b6  jb      short loc_1400071BB
0x1400071b8  mov     rcx, [rcx]
0x1400071bb  mov     [rsp+1C8h+var_168], rcx
0x1400071c0  lea     rax, [rsp+1C8h+var_158]
0x1400071c5  mov     [rsp+1C8h+lpEnvironment], rax
0x1400071ca  lea     rax, [rsp+1C8h+var_178]
0x1400071cf  mov     qword ptr [rsp+1C8h+dwCreationFlags], rax
0x1400071d4  lea     rax, [rsp+1C8h+var_168]
0x1400071d9  mov     qword ptr [rsp+1C8h+bInheritHandles], rax
0x1400071de  lea     rdx, dword_14000D43C
0x1400071e5  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400071ea  mov     rbx, rdi
0x1400071ed  lea     rax, [rsp+1C8h+ProcessInformation]
0x1400071f5  mov     [rsp+1C8h+lpProcessInformation], rax; lpProcessInformation
0x1400071fa  lea     rax, [rsp+1C8h+StartupInfo]
0x140007202  mov     [rsp+1C8h+lpStartupInfo], rax; lpStartupInfo
0x140007207  mov     [rsp+1C8h+lpCurrentDirectory], rbx; lpCurrentDirectory
0x14000720c  mov     [rsp+1C8h+lpEnvironment], rdi; lpEnvironment
0x140007211  mov     [rsp+1C8h+dwCreationFlags], 8000020h; dwCreationFlags
0x140007219  mov     [rsp+1C8h+bInheritHandles], edi; bInheritHandles
0x14000721d  xor     r9d, r9d; lpThreadAttributes
0x140007220  xor     r8d, r8d; lpProcessAttributes
0x140007223  mov     rbx, [rsp+1C8h+lpCommandLine]
0x14000722b  mov     rdx, rbx; lpCommandLine
0x14000722e  xor     ecx, ecx; lpApplicationName
0x140007230  call    cs:__imp_CreateProcessW
0x140007236  test    eax, eax
0x140007238  jnz     loc_1400072E4
0x14000723e  mov     eax, cs:dword_140010000
0x140007244  cmp     eax, 2
0x140007247  jbe     loc_1400072D3
0x14000724d  mov     rcx, cs:qword_140010018
0x140007254  mov     rax, cs:qword_140010010
0x14000725b  mov     rdx, 400000000000h
0x140007265  test    rdx, rax
0x140007268  jz      short loc_1400072D3
0x14000726a  mov     rax, rcx
0x14000726d  and     rax, rdx
0x140007270  cmp     rax, rcx
0x140007273  jnz     short loc_1400072D3
0x140007275  call    cs:__imp_GetLastError
0x14000727b  mov     [rsp+1C8h+var_120], eax
0x140007282  cmp     qword ptr [r13+18h], 8
0x140007287  jb      short loc_14000728D
0x140007289  mov     r13, [r13+0]
0x14000728d  mov     [rsp+1C8h+var_168], r13
0x140007292  lea     rcx, [r14+28h]
0x140007296  cmp     qword ptr [r14+40h], 8
0x14000729b  jb      short loc_1400072A0
0x14000729d  mov     rcx, [rcx]
0x1400072a0  mov     [rsp+1C8h+var_178], rcx
0x1400072a5  lea     rax, [rsp+1C8h+var_120]
0x1400072ad  mov     [rsp+1C8h+lpEnvironment], rax
0x1400072b2  lea     rax, [rsp+1C8h+var_168]
0x1400072b7  mov     qword ptr [rsp+1C8h+dwCreationFlags], rax
0x1400072bc  lea     rax, [rsp+1C8h+var_178]
0x1400072c1  mov     qword ptr [rsp+1C8h+bInheritHandles], rax
0x1400072c6  lea     rdx, dword_14000D1CC
0x1400072cd  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1400072d2  nop
0x1400072d3  test    rbx, rbx
0x1400072d6  jz      loc_140007A42
0x1400072dc  mov     rcx, rbx
0x1400072df  jmp     loc_140007A3C
0x1400072e4  mov     rbx, [rsp+1C8h+ProcessInformation.hProcess]
0x1400072ec  test    rbx, rbx
0x1400072ef  jnz     loc_14000738F
0x1400072f5  mov     eax, cs:dword_140010000
0x1400072fb  cmp     eax, 2
0x1400072fe  jbe     loc_14000738A
0x140007304  mov     rcx, cs:qword_140010018
0x14000730b  mov     rax, cs:qword_140010010
0x140007312  mov     rdx, 400000000000h
0x14000731c  test    rdx, rax
0x14000731f  jz      short loc_14000738A
0x140007321  mov     rax, rcx
0x140007324  and     rax, rdx
0x140007327  cmp     rax, rcx
0x14000732a  jnz     short loc_14000738A
0x14000732c  call    cs:__imp_GetLastError
0x140007332  mov     [rsp+1C8h+var_11C], eax
0x140007339  cmp     qword ptr [r13+18h], 8
0x14000733e  jb      short loc_140007344
  ... truncated ...
```
