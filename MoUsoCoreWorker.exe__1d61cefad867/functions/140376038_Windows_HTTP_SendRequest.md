# Windows::HTTP::SendRequest

- ea: `0x140376038`
- end: `0x140376a6f`
- name: `Windows::HTTP::SendRequest`
- size: `2615`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x1403770a0`
- `0x140377210`

## callees

- `0x14003fd58`
- `0x140040184`
- `0x140040308`
- `0x140045404`
- `0x140057a20`
- `0x140075a18`
- `0x1400a3d80`
- `0x14012d864`
- `0x140375e08`
- `0x140376038`
- `0x140379070`
- `0x14037b4b0`
- `0x140380b50`

## import_xrefs

- `WINHTTP!WinHttpAddRequestHeaders` at `0x14037668f`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x14037668f`
- `WINHTTP!WinHttpCloseHandle` at `0x1403760f3`
- `WINHTTP!WinHttpCloseHandle` at `0x14037614b`
- `WINHTTP!WinHttpCloseHandle` at `0x14037647f`
- `WINHTTP!WinHttpCloseHandle` at `0x1403764dc`
- `WINHTTP!WinHttpCloseHandle` at `0x140376530`
- `WINHTTP!WinHttpCloseHandle` at `0x1403765a5`
- `WINHTTP!WinHttpCloseHandle` at `0x1403765b4`
- `WINHTTP!WinHttpCloseHandle` at `0x14037660a`
- `WINHTTP!WinHttpCloseHandle` at `0x1403766cf`
- `WINHTTP!WinHttpCloseHandle` at `0x1403766de`
- `WINHTTP!WinHttpCloseHandle` at `0x140376734`
- `WINHTTP!WinHttpCloseHandle` at `0x1403767ac`
- `WINHTTP!WinHttpCloseHandle` at `0x1403767bb`
- `WINHTTP!WinHttpCloseHandle` at `0x140376811`
- `WINHTTP!WinHttpCloseHandle` at `0x140376859`
- `WINHTTP!WinHttpCloseHandle` at `0x14037686c`
- `WINHTTP!WinHttpCloseHandle` at `0x14037687f`
- `WINHTTP!WinHttpCloseHandle` at `0x1403760f3`
- `WINHTTP!WinHttpCloseHandle` at `0x14037614b`
- `WINHTTP!WinHttpCloseHandle` at `0x14037647f`
- `WINHTTP!WinHttpCloseHandle` at `0x1403764dc`
- `WINHTTP!WinHttpCloseHandle` at `0x140376530`
- `WINHTTP!WinHttpCloseHandle` at `0x1403765a5`
- `WINHTTP!WinHttpCloseHandle` at `0x1403765b4`
- `WINHTTP!WinHttpCloseHandle` at `0x14037660a`
- `WINHTTP!WinHttpCloseHandle` at `0x1403766cf`
- `WINHTTP!WinHttpCloseHandle` at `0x1403766de`
- `WINHTTP!WinHttpCloseHandle` at `0x140376734`
- `WINHTTP!WinHttpCloseHandle` at `0x1403767ac`
- `WINHTTP!WinHttpCloseHandle` at `0x1403767bb`
- `WINHTTP!WinHttpCloseHandle` at `0x140376811`
- `WINHTTP!WinHttpCloseHandle` at `0x140376859`
- `WINHTTP!WinHttpCloseHandle` at `0x14037686c`
- `WINHTTP!WinHttpCloseHandle` at `0x14037687f`
- `WINHTTP!WinHttpOpenRequest` at `0x140376565`
- `WINHTTP!WinHttpOpenRequest` at `0x140376565`
- `WINHTTP!WinHttpSendRequest` at `0x14037678e`
- `WINHTTP!WinHttpSendRequest` at `0x14037678e`
- `WINHTTP!WinHttpOpen` at `0x1403760a7`
- `WINHTTP!WinHttpOpen` at `0x1403760a7`
- `WINHTTP!WinHttpConnect` at `0x14037649c`
- `WINHTTP!WinHttpConnect` at `0x14037649c`
- `WINHTTP!WinHttpSetTimeouts` at `0x14037640a`
- `WINHTTP!WinHttpSetTimeouts` at `0x14037640a`
- `WINHTTP!WinHttpSetOption` at `0x14037611e`
- `WINHTTP!WinHttpSetOption` at `0x14037611e`

## string_xrefs

- `0x1403768fe`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140376918`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x140376932`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x14037694c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`
- `0x1403760d9`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x140376130`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x14037641f`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x1403764c2`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x14037658b`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`
- `0x1403766a5`: `C:\__w\1\s\src\orchestrator\system\windows\common\HTTP.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::HTTP::SendRequest(
        LPCWSTR *a1,
        LPCWSTR *a2,
        LPCWSTR *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7)
{
  int v7; // r13d
  LPCWSTR *v8; // r12
  void *v9; // rax
  const char *v10; // r9
  void *v11; // rbx
  bool v12; // si
  unsigned int v13; // ebx
  __int64 result; // rax
  const char *v16; // r9
  unsigned int v17; // edi
  _QWORD *System; // rax
  volatile signed __int32 *v19; // rdi
  unsigned int (__fastcall *v20)(__int64, const wchar_t **, int *); // rdi
  wchar_t *traits_2_unsigned_short; // rax
  const char *v22; // r9
  __int64 v23; // r11
  __int64 v24; // rax
  __int64 v25; // r14
  unsigned int (__fastcall *v26)(__int64, const wchar_t **, int *); // rdi
  wchar_t *v27; // rax
  const char *v28; // r9
  __int64 v29; // r11
  __int64 v30; // rax
  __int64 v31; // rsi
  unsigned int (__fastcall *v32)(__int64, const wchar_t **, int *); // rdi
  __int16 *v33; // rax
  const char *v34; // r9
  __int64 v35; // r11
  __int64 v36; // rax
  __int64 v37; // rdi
  unsigned int (__fastcall *v38)(__int64, const wchar_t **, int *); // r12
  wchar_t *v39; // rax
  const char *v40; // r9
  __int64 v41; // r11
  __int64 v42; // rax
  __int64 v43; // rcx
  const char *v44; // r9
  unsigned int v45; // esi
  const char *v46; // r9
  volatile signed __int32 *v47; // rdi
  void *v48; // rax
  const char *v49; // r9
  void *v50; // rdi
  bool v51; // r12
  unsigned int v52; // esi
  volatile signed __int32 *v53; // rdi
  LPCWSTR *v54; // rsi
  const char *v55; // r9
  bool v56; // r13
  unsigned int v57; // esi
  volatile signed __int32 *v58; // rdi
  LPCWSTR *v59; // rax
  LPCWSTR *v60; // r14
  const WCHAR *p_lpszHeaders; // rdx
  __int64 v62; // rdx
  const char *v63; // r9
  unsigned int LastError; // r14d
  __int64 v65; // rdx
  volatile signed __int32 *v66; // rdi
  __int64 v67; // rax
  wil::details *v68; // rcx
  unsigned int LastErrorFailHr; // r14d
  volatile signed __int32 *v70; // rdi
  volatile signed __int32 *v71; // rbx
  bool v72; // [rsp+40h] [rbp-148h]
  int v73; // [rsp+44h] [rbp-144h] BYREF
  int v74; // [rsp+48h] [rbp-140h]
  const wchar_t *v75; // [rsp+50h] [rbp-138h] BYREF
  __int64 v76; // [rsp+58h] [rbp-130h]
  int v77; // [rsp+60h] [rbp-128h]
  LPCWSTR *v78; // [rsp+68h] [rbp-120h]
  LPCWSTR *v79; // [rsp+70h] [rbp-118h]
  LPCWSTR *v80; // [rsp+78h] [rbp-110h]
  __int64 v81; // [rsp+80h] [rbp-108h]
  __int64 v82; // [rsp+88h] [rbp-100h]
  __int128 pExceptionObject; // [rsp+90h] [rbp-F8h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-E8h]
  __int128 v85; // [rsp+A8h] [rbp-E0h] BYREF
  __int64 v86; // [rsp+B8h] [rbp-D0h]
  __int128 v87; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 v88; // [rsp+D0h] [rbp-B8h]
  __int128 v89; // [rsp+D8h] [rbp-B0h] BYREF
  __int64 v90; // [rsp+E8h] [rbp-A0h]
  __int128 v91; // [rsp+F0h] [rbp-98h] BYREF
  __int64 v92; // [rsp+100h] [rbp-88h]
  void *v93; // [rsp+108h] [rbp-80h]
  __int128 v94; // [rsp+110h] [rbp-78h] BYREF
  int Buffer; // [rsp+120h] [rbp-68h] BYREF
  LPCWSTR lpszHeaders; // [rsp+128h] [rbp-60h] BYREF
  HINTERNET v97; // [rsp+130h] [rbp-58h]
  HINTERNET hInternet; // [rsp+138h] [rbp-50h]
  unsigned __int64 v99; // [rsp+140h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v81 = a4;
  v78 = a3;
  v80 = a2;
  v8 = a1;
  v79 = a1;
  v82 = a6;
  v77 = 0;
  v9 = WinHttpOpen(L"Devices", 4u, 0, 0, 0);
  v11 = v9;
  v93 = v9;
  v12 = v9 != 0;
  v72 = v9 != 0;
  LOBYTE(v7) = v9 != 0;
  v74 = v7;
  if ( v9 )
  {
    Buffer = 2048;
    if ( WinHttpSetOption(v9, 0x54u, &Buffer, 4u) )
    {
      v94 = 0;
      try
      {
        System = (_QWORD *)SystemInterface::Service::GetSystem(&lpszHeaders);
        (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*System + 40LL))(*System, &v94);
        v19 = (volatile signed __int32 *)v97;
        if ( v97 )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v97 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
            if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
        if ( a7 )
        {
          v20 = *(unsigned int (__fastcall **)(__int64, const wchar_t **, int *))(*(_QWORD *)v94 + 56LL);
          v73 = 2;
          traits_2_unsigned_short = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                                 L"HTTPResolveTimeoutInSeconds",
                                                 L"{}: {}",
                                                 0);
          if ( traits_2_unsigned_short == L"{}: {}"
            || (v24 = traits_2_unsigned_short - L"HTTPResolveTimeoutInSeconds", v24 == -1) )
          {
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v22);
          }
          v75 = L"HTTPResolveTimeoutInSeconds";
          v76 = v24;
          v25 = 1000LL * v20(v23, &v75, &v73);
          v26 = *(unsigned int (__fastcall **)(__int64, const wchar_t **, int *))(*(_QWORD *)v94 + 56LL);
          v73 = 2;
          v27 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                             L"HTTPConnectTimeoutInSeconds",
                             L"GET",
                             0);
          if ( v27 == L"GET" || (v30 = v27 - L"HTTPConnectTimeoutInSeconds", v30 == -1) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v28);
          v75 = L"HTTPConnectTimeoutInSeconds";
          v76 = v30;
          v31 = 1000LL * v26(v29, &v75, &v73);
          v32 = *(unsigned int (__fastcall **)(__int64, const wchar_t **, int *))(*(_QWORD *)v94 + 56LL);
          v73 = 8;
          v33 = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                             L"HTTPSendTimeoutInSeconds",
                             word_140487E12,
                             0);
          if ( v33 == word_140487E12 || (v36 = ((char *)v33 - (char *)L"HTTPSendTimeoutInSeconds") >> 1, v36 == -1) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v34);
          v75 = L"HTTPSendTimeoutInSeconds";
          v76 = v36;
          v37 = 1000LL * v32(v35, &v75, &v73);
          v38 = *(unsigned int (__fastcall **)(__int64, const wchar_t **, int *))(*(_QWORD *)v94 + 56LL);
          v73 = 8;
          v39 = (wchar_t *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                             L"HTTPReceiveTimeoutInSeconds",
                             L"POST",
                             0);
          if ( v39 == L"POST" || (v42 = v39 - L"HTTPReceiveTimeoutInSeconds", v42 == -1) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0xC9,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
              v40);
          v75 = L"HTTPReceiveTimeoutInSeconds";
          v76 = v42;
          v43 = 1000LL * v38(v41, &v75, &v73);
          v8 = v79;
        }
        else
        {
          v43 = 60000;
          v25 = 60000;
          v31 = 60000;
          v37 = 60000;
        }
        if ( (int)v43 != v43 )
        {
          pExceptionObject = 0;
          v84 = 0;
          Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&pExceptionObject);
          throw (gsl::narrowing_error *)&pExceptionObject;
        }
        if ( (int)v37 != v37 )
        {
          v85 = 0;
          v86 = 0;
          Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&v85);
          throw (gsl::narrowing_error *)&v85;
        }
        if ( (int)v31 != v31 )
        {
          v87 = 0;
          v88 = 0;
          Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&v87);
          throw (gsl::narrowing_error *)&v87;
        }
        if ( (int)v25 != v25 )
        {
          v89 = 0;
          v90 = 0;
          Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&v89);
          throw (gsl::narrowing_error *)&v89;
        }
        if ( WinHttpSetTimeouts(v11, v25, v31, v37, v43) )
        {
          v48 = WinHttpConnect(v11, *v8, 0x1BBu, 0);
          v50 = v48;
          v79 = (LPCWSTR *)v48;
          v51 = v48 != 0;
          if ( v48 )
          {
            v54 = (LPCWSTR *)WinHttpOpenRequest(v48, *v78, *v80, 0, 0, 0, 0x800000u);
            v80 = v54;
            v56 = v54 != 0;
            if ( v54 )
            {
              v59 = *(LPCWSTR **)(a5 + 8);
              v78 = v59;
              v60 = (LPCWSTR *)*v59;
              while ( v60 != v59 )
              {
                v75 = L"{}: {}";
                v76 = 6;
                std::format<std::wstring const &,std::wstring const &>(&lpszHeaders);
                v77 |= 7u;
                p_lpszHeaders = (const WCHAR *)&lpszHeaders;
                if ( v99 > 7 )
                  p_lpszHeaders = lpszHeaders;
                if ( !WinHttpAddRequestHeaders(v54, p_lpszHeaders, 0xFFFFFFFF, 0x20000000u) )
                {
                  LastError = wil::details::in1diag3::Return_GetLastError(
                                retaddr,
                                (void *)0xDD,
                                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
                                v63);
                  std::wstring::~wstring(&lpszHeaders, v65);
                  WinHttpCloseHandle(v54);
                  if ( v51 )
                    WinHttpCloseHandle(v50);
                  v66 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
                  if ( *((_QWORD *)&v94 + 1) )
                  {
                    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                    {
                      (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
                      if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
                        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
                    }
                  }
                  if ( v72 )
                    WinHttpCloseHandle(v11);
                  result = LastError;
                  goto LABEL_113;
                }
                std::wstring::~wstring(&lpszHeaders, v62);
                v60 = (LPCWSTR *)*v60;
                v59 = v78;
              }
              v67 = *(unsigned int *)(v81 + 8);
              if ( v67 != *(_QWORD *)(v81 + 8) )
              {
                v91 = 0;
                v92 = 0;
                Concurrency::task_canceled::task_canceled((Concurrency::task_canceled *)&v91);
                throw (gsl::narrowing_error *)&v91;
              }
              if ( WinHttpSendRequest(v54, 0, 0xFFFFFFFF, *(LPVOID *)v81, v67, v67, 0) )
              {
                lpszHeaders = (LPCWSTR)v11;
                v97 = v50;
                hInternet = v54;
                Windows::HTTP::_anonymous_namespace_::Connection::operator_(v82, &lpszHeaders);
                if ( hInternet )
                  WinHttpCloseHandle(hInternet);
                if ( v97 )
                  WinHttpCloseHandle(v97);
                if ( lpszHeaders )
                  WinHttpCloseHandle((HINTERNET)lpszHeaders);
                v71 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
                if ( *((_QWORD *)&v94 + 1) )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v71)(v71);
                    if ( _InterlockedExchangeAdd(v71 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v71 + 8LL))(v71);
                  }
                }
                result = 0;
              }
              else
              {
                LastErrorFailHr = wil::details::GetLastErrorFailHr(v68);
                WinHttpCloseHandle(v54);
                if ( v51 )
                  WinHttpCloseHandle(v50);
                v70 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
                if ( *((_QWORD *)&v94 + 1) )
                {
                  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                  {
                    (**(void (__fastcall ***)(volatile signed __int32 *))v70)(v70);
                    if ( _InterlockedExchangeAdd(v70 + 3, 0xFFFFFFFF) == 1 )
                      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v70 + 8LL))(v70);
                  }
                }
                if ( v72 )
                  WinHttpCloseHandle(v11);
                result = LastErrorFailHr;
              }
            }
            else
            {
              v57 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xD9,
                      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
                      v55);
              if ( v56 )
                WinHttpCloseHandle(0);
              if ( v51 )
                WinHttpCloseHandle(v50);
              v58 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
              if ( *((_QWORD *)&v94 + 1) )
              {
                if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
                {
                  (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
                  if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
                    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
                }
              }
              if ( (_BYTE)v74 )
                WinHttpCloseHandle(v11);
              result = v57;
            }
          }
          else
          {
            v52 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xD6,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
                    v49);
            if ( v51 )
              WinHttpCloseHandle(0);
            v53 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
            if ( *((_QWORD *)&v94 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
                if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
              }
            }
            if ( (_BYTE)v7 )
              WinHttpCloseHandle(v11);
            result = v52;
          }
        }
        else
        {
          v45 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xD3,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
                  v44);
          v47 = (volatile signed __int32 *)*((_QWORD *)&v94 + 1);
          if ( *((_QWORD *)&v94 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v94 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
              if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
            }
          }
          if ( (_BYTE)v7 )
            WinHttpCloseHandle(v11);
          result = v45;
        }
      }
      catch ( ... )
      {
        result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0xE6,
                                 (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
                                 v46);
      }
LABEL_113:
      ;
    }
    else
    {
      v17 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xC7,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
              v16);
      if ( v12 )
        WinHttpCloseHandle(v11);
      return v17;
    }
  }
  else
  {
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xC4,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\HTTP.cpp",
            v10);
    if ( v12 )
      WinHttpCloseHandle(0);
    return v13;
  }
  return result;
}

```

## disassembly

```asm
0x140376038  push    rbx
0x14037603a  push    rsi
0x14037603b  push    rdi
0x14037603c  push    r12
0x14037603e  push    r13
0x140376040  push    r14
0x140376042  push    r15
0x140376044  sub     rsp, 150h
0x14037604b  mov     rax, cs:__security_cookie
0x140376052  xor     rax, rsp
0x140376055  mov     [rsp+188h+var_40], rax
0x14037605d  mov     [rsp+188h+var_108], r9
0x140376065  mov     [rsp+188h+var_120], r8
0x14037606a  mov     [rsp+188h+var_110], rdx
0x14037606f  mov     r12, rcx
0x140376072  mov     [rsp+188h+var_118], rcx
0x140376077  mov     rax, [rsp+188h+arg_28]
0x14037607f  mov     [rsp+188h+var_100], rax
0x140376087  xor     r14d, r14d
0x14037608a  mov     [rsp+188h+var_128], r14d
0x14037608f  mov     [rsp+188h+dwFlags], r14d; dwFlags
0x140376094  xor     r9d, r9d; pszProxyBypassW
0x140376097  xor     r8d, r8d; pszProxyW
0x14037609a  lea     edi, [r14+4]
0x14037609e  mov     edx, edi; dwAccessType
0x1403760a0  lea     rcx, pszAgentW; "Devices"
0x1403760a7  call    cs:__imp_WinHttpOpen
0x1403760ad  mov     rbx, rax
0x1403760b0  mov     [rsp+188h+var_80], rax
0x1403760b8  test    rax, rax
0x1403760bb  setnz   sil
0x1403760bf  mov     [rsp+188h+var_148], sil
0x1403760c4  mov     r13b, sil
0x1403760c7  mov     [rsp+188h+var_140], r13d
0x1403760cc  test    rax, rax
0x1403760cf  jnz     short loc_140376100
0x1403760d1  mov     rcx, [rsp+188h]; this
0x1403760d9  lea     r8, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403760e0  mov     edx, 0C4h; void *
0x1403760e5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1403760ea  mov     ebx, eax
0x1403760ec  test    sil, sil
0x1403760ef  jz      short loc_1403760F9
0x1403760f1  xor     ecx, ecx; hInternet
0x1403760f3  call    cs:__imp_WinHttpCloseHandle
0x1403760f9  mov     eax, ebx
0x1403760fb  jmp     loc_1403768D3
0x140376100  mov     [rsp+188h+Buffer], 800h
0x14037610b  mov     r9d, edi; dwBufferLength
0x14037610e  lea     r8, [rsp+188h+Buffer]; lpBuffer
0x140376116  mov     edx, 54h ; 'T'; dwOption
0x14037611b  mov     rcx, rbx; hInternet
0x14037611e  call    cs:__imp_WinHttpSetOption
0x140376124  test    eax, eax
0x140376126  jnz     short loc_140376158
0x140376128  mov     rcx, [rsp+188h]; this
0x140376130  lea     r8, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140376137  mov     edx, 0C7h; void *
0x14037613c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140376141  mov     edi, eax
0x140376143  test    sil, sil
0x140376146  jz      short loc_140376151
0x140376148  mov     rcx, rbx; hInternet
0x14037614b  call    cs:__imp_WinHttpCloseHandle
0x140376151  mov     eax, edi
0x140376153  jmp     loc_1403768D3
0x140376158  xorps   xmm0, xmm0
0x14037615b  movups  [rsp+188h+var_78], xmm0
0x140376163  lea     rcx, [rsp+188h+lpszHeaders]
0x14037616b  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x140376170  nop
0x140376171  mov     rcx, [rax]
0x140376174  mov     rax, [rcx]
0x140376177  lea     rdx, [rsp+188h+var_78]
0x14037617f  mov     rax, [rax+28h]
0x140376183  call    _guard_dispatch_icall
0x140376188  nop
0x140376189  mov     rdi, [rsp+188h+var_58]
0x140376191  or      r15, 0FFFFFFFFFFFFFFFFh
0x140376195  test    rdi, rdi
0x140376198  jz      short loc_1403761D1
0x14037619a  mov     eax, r15d
0x14037619d  lock xadd [rdi+8], eax
0x1403761a2  add     eax, r15d
0x1403761a5  jnz     short loc_1403761D1
0x1403761a7  mov     rax, [rdi]
0x1403761aa  mov     rcx, rdi
0x1403761ad  mov     rax, [rax]
0x1403761b0  call    _guard_dispatch_icall
0x1403761b5  mov     eax, r15d
0x1403761b8  lock xadd [rdi+0Ch], eax
0x1403761bd  add     eax, r15d
0x1403761c0  jnz     short loc_1403761D1
0x1403761c2  mov     rax, [rdi]
0x1403761c5  mov     rcx, rdi
0x1403761c8  mov     rax, [rax+8]
0x1403761cc  call    _guard_dispatch_icall
0x1403761d1  cmp     [rsp+188h+arg_30], r14b
0x1403761d9  jz      loc_1403763BE
0x1403761df  mov     r11, qword ptr [rsp+188h+var_78]
0x1403761e7  mov     rax, [r11]
0x1403761ea  mov     rdi, [rax+38h]
0x1403761ee  mov     r12d, 2
0x1403761f4  mov     [rsp+188h+var_144], r12d
0x1403761f9  xor     r8d, r8d
0x1403761fc  lea     rsi, asc_140487DD0; "{}: {}"
0x140376203  mov     rdx, rsi
0x140376206  lea     r14, aHttpresolvetim; "HTTPResolveTimeoutInSeconds"
0x14037620d  mov     rcx, r14
0x140376210  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140376215  cmp     rax, rsi
0x140376218  jz      loc_140376944
0x14037621e  sub     rax, r14
0x140376221  sar     rax, 1
0x140376224  cmp     rax, r15
0x140376227  jz      loc_140376944
0x14037622d  mov     [rsp+188h+var_138], r14
0x140376232  mov     [rsp+188h+var_130], rax
0x140376237  lea     r8, [rsp+188h+var_144]
0x14037623c  lea     rdx, [rsp+188h+var_138]
0x140376241  mov     rcx, r11
0x140376244  mov     rax, rdi
0x140376247  call    _guard_dispatch_icall
0x14037624c  mov     eax, eax
0x14037624e  imul    r14, rax, 3E8h
0x140376255  mov     r11, qword ptr [rsp+188h+var_78]
0x14037625d  mov     rax, [r11]
0x140376260  mov     rdi, [rax+38h]
0x140376264  mov     [rsp+188h+var_144], r12d
0x140376269  xor     r8d, r8d
0x14037626c  lea     rsi, aGet; "GET"
0x140376273  mov     rdx, rsi
0x140376276  lea     r12, aHttpconnecttim; "HTTPConnectTimeoutInSeconds"
0x14037627d  mov     rcx, r12
0x140376280  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140376285  cmp     rax, rsi
0x140376288  jz      loc_14037692A
0x14037628e  sub     rax, r12
0x140376291  sar     rax, 1
0x140376294  cmp     rax, r15
0x140376297  jz      loc_14037692A
0x14037629d  mov     [rsp+188h+var_138], r12
0x1403762a2  mov     [rsp+188h+var_130], rax
0x1403762a7  lea     r8, [rsp+188h+var_144]
0x1403762ac  lea     rdx, [rsp+188h+var_138]
0x1403762b1  mov     rcx, r11
0x1403762b4  mov     rax, rdi
0x1403762b7  call    _guard_dispatch_icall
0x1403762bc  mov     eax, eax
0x1403762be  imul    rsi, rax, 3E8h
0x1403762c5  mov     r11, qword ptr [rsp+188h+var_78]
0x1403762cd  mov     rax, [r11]
0x1403762d0  mov     rdi, [rax+38h]
0x1403762d4  mov     [rsp+188h+var_144], 8
0x1403762dc  xor     r8d, r8d
0x1403762df  lea     r12, word_140487E12
0x1403762e6  mov     rdx, r12
0x1403762e9  lea     rcx, aHttpsendtimeou; "HTTPSendTimeoutInSeconds"
0x1403762f0  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x1403762f5  cmp     rax, r12
0x1403762f8  jz      loc_140376910
0x1403762fe  lea     rcx, aHttpsendtimeou; "HTTPSendTimeoutInSeconds"
0x140376305  sub     rax, rcx
0x140376308  sar     rax, 1
0x14037630b  cmp     rax, r15
0x14037630e  jz      loc_140376910
0x140376314  mov     [rsp+188h+var_138], rcx
0x140376319  mov     [rsp+188h+var_130], rax
0x14037631e  lea     r8, [rsp+188h+var_144]
0x140376323  lea     rdx, [rsp+188h+var_138]
0x140376328  mov     rcx, r11
0x14037632b  mov     rax, rdi
0x14037632e  call    _guard_dispatch_icall
0x140376333  mov     eax, eax
0x140376335  imul    rdi, rax, 3E8h
0x14037633c  mov     r11, qword ptr [rsp+188h+var_78]
0x140376344  mov     rax, [r11]
0x140376347  mov     r12, [rax+38h]
0x14037634b  mov     [rsp+188h+var_144], 8
0x140376353  xor     r8d, r8d
0x140376356  lea     rdx, aPost; "POST"
0x14037635d  lea     rcx, aHttpreceivetim; "HTTPReceiveTimeoutInSeconds"
0x140376364  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x140376369  lea     rcx, aPost; "POST"
0x140376370  cmp     rax, rcx
0x140376373  jz      loc_1403768F6
0x140376379  lea     rcx, aHttpreceivetim; "HTTPReceiveTimeoutInSeconds"
0x140376380  sub     rax, rcx
0x140376383  sar     rax, 1
0x140376386  cmp     rax, r15
0x140376389  jz      loc_1403768F6
0x14037638f  mov     [rsp+188h+var_138], rcx
0x140376394  mov     [rsp+188h+var_130], rax
0x140376399  lea     r8, [rsp+188h+var_144]
0x14037639e  lea     rdx, [rsp+188h+var_138]
0x1403763a3  mov     rcx, r11
0x1403763a6  mov     rax, r12
0x1403763a9  call    _guard_dispatch_icall
0x1403763ae  mov     eax, eax
0x1403763b0  imul    rcx, rax, 3E8h
0x1403763b7  mov     r12, [rsp+188h+var_118]
0x1403763bc  jmp     short loc_1403763CA
0x1403763be  mov     ecx, 0EA60h
0x1403763c3  mov     r14d, ecx
0x1403763c6  mov     esi, ecx
0x1403763c8  mov     edi, ecx
0x1403763ca  movsxd  rax, ecx
0x1403763cd  cmp     rax, rcx
0x1403763d0  jnz     loc_14037695E
0x1403763d6  movsxd  rax, edi
0x1403763d9  cmp     rax, rdi
0x1403763dc  jnz     loc_140376994
0x1403763e2  movsxd  rax, esi
0x1403763e5  cmp     rax, rsi
0x1403763e8  jnz     loc_1403769CA
0x1403763ee  movsxd  rax, r14d
0x1403763f1  cmp     rax, r14
0x1403763f4  jnz     loc_140376A00
0x1403763fa  mov     [rsp+188h+dwFlags], ecx; nReceiveTimeout
0x1403763fe  mov     r9d, edi; nSendTimeout
0x140376401  mov     r8d, esi; nConnectTimeout
0x140376404  mov     edx, r14d; nResolveTimeout
0x140376407  mov     rcx, rbx; hInternet
0x14037640a  call    cs:__imp_WinHttpSetTimeouts
0x140376410  xor     r14d, r14d
0x140376413  test    eax, eax
0x140376415  jnz     short loc_14037648C
0x140376417  mov     rcx, [rsp+188h]; this
0x14037641f  lea     r8, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140376426  mov     edx, 0D3h; void *
0x14037642b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140376430  mov     esi, eax
0x140376432  mov     rdi, qword ptr [rsp+188h+var_78+8]
0x14037643a  test    rdi, rdi
0x14037643d  jz      short loc_140376477
0x14037643f  mov     ecx, r15d
0x140376442  lock xadd [rdi+8], ecx
0x140376447  add     ecx, r15d
0x14037644a  jnz     short loc_140376477
0x14037644c  mov     rcx, [rdi]
0x14037644f  mov     rax, [rcx]
0x140376452  mov     rcx, rdi
0x140376455  call    _guard_dispatch_icall
0x14037645a  mov     eax, r15d
0x14037645d  lock xadd [rdi+0Ch], eax
0x140376462  add     eax, r15d
0x140376465  jnz     short loc_140376477
0x140376467  mov     rax, [rdi]
0x14037646a  mov     rcx, rdi
0x14037646d  mov     rax, [rax+8]
0x140376471  call    _guard_dispatch_icall
0x140376476  nop
0x140376477  test    r13b, r13b
0x14037647a  jz      short loc_140376485
0x14037647c  mov     rcx, rbx; hInternet
0x14037647f  call    cs:__imp_WinHttpCloseHandle
0x140376485  mov     eax, esi
0x140376487  jmp     loc_1403768D3
0x14037648c  mov     r8d, 1BBh; nServerPort
0x140376492  xor     r9d, r9d; dwReserved
0x140376495  mov     rdx, [r12]; pswzServerName
0x140376499  mov     rcx, rbx; hSession
0x14037649c  call    cs:__imp_WinHttpConnect
0x1403764a2  mov     rdi, rax
0x1403764a5  mov     [rsp+188h+var_118], rax
0x1403764aa  test    rax, rax
0x1403764ad  setnz   r12b
0x1403764b1  test    rax, rax
0x1403764b4  jnz     loc_14037653D
0x1403764ba  mov     rcx, [rsp+188h]; this
0x1403764c2  lea     r8, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403764c9  mov     edx, 0D6h; void *
0x1403764ce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1403764d3  mov     esi, eax
0x1403764d5  test    r12b, r12b
0x1403764d8  jz      short loc_1403764E3
0x1403764da  xor     ecx, ecx; hInternet
0x1403764dc  call    cs:__imp_WinHttpCloseHandle
0x1403764e2  nop
0x1403764e3  mov     rdi, qword ptr [rsp+188h+var_78+8]
0x1403764eb  test    rdi, rdi
0x1403764ee  jz      short loc_140376528
0x1403764f0  mov     eax, r15d
0x1403764f3  lock xadd [rdi+8], eax
0x1403764f8  add     eax, r15d
0x1403764fb  jnz     short loc_140376528
0x1403764fd  mov     rax, [rdi]
0x140376500  mov     rcx, rdi
0x140376503  mov     rax, [rax]
0x140376506  call    _guard_dispatch_icall
0x14037650b  mov     eax, r15d
0x14037650e  lock xadd [rdi+0Ch], eax
0x140376513  add     eax, r15d
0x140376516  jnz     short loc_140376528
0x140376518  mov     rax, [rdi]
0x14037651b  mov     rcx, rdi
0x14037651e  mov     rax, [rax+8]
0x140376522  call    _guard_dispatch_icall
0x140376527  nop
0x140376528  test    r13b, r13b
  ... truncated ...
```
