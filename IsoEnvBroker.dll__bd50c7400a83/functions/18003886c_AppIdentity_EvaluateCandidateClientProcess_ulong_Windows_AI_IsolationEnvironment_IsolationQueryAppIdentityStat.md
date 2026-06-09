# AppIdentity::EvaluateCandidateClientProcess(ulong,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,std::shared_ptr<AppIdentity> &)

- ea: `0x18003886c`
- end: `0x180038f80`
- name: `?EvaluateCandidateClientProcess@AppIdentity@@CAJKAEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAppIdentity@@@std@@@Z`
- size: `1812`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x180038494`

## callees

- `0x180002520`
- `0x180002ee8`
- `0x1800030d0`
- `0x1800050cd`
- `0x180010148`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x180014c04`
- `0x18001f998`
- `0x1800366b4`
- `0x180036f34`
- `0x180038170`
- `0x180038334`
- `0x18003886c`
- `0x18003976c`
- `0x1800399a0`
- `0x180039cf8`
- `0x18004cf04`
- `0x18004d35c`
- `0x18004dce0`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180038a4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180038a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388f7`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180038940`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180038940`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800389a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038f4e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800388d7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800388d7`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800389e0`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800389e0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180038a1b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180038a1b`

## string_xrefs

- `0x18003891c`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180038956`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x180038f2f`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\appidentity.cpp`
- `0x18003890d`: `[QueryAppIdentity] Failed to open process %d.`
- `0x180038f1b`: `[QueryAppIdentity] Failed to find executable name from path for process %d.`
- `0x180038a05`: `[QueryAppIdentity] Process %d executable path: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall AppIdentity::EvaluateCandidateClientProcess(
        char *a1,
        enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *a2,
        _QWORD *a3)
{
  DWORD v4; // r15d
  char *v5; // rbx
  DWORD LastError; // eax
  unsigned int LastErrorMsg; // eax
  unsigned int v8; // edi
  const char *v9; // r9
  __int64 v10; // rdx
  WCHAR *FileNameW; // r12
  void ***v13; // rdi
  __int64 v14; // rax
  __int128 *v15; // r8
  unsigned __int64 v16; // r8
  __int64 v17; // rax
  int v18; // esi
  __int64 *v19; // rax
  volatile signed __int32 *v20; // rdi
  unsigned __int64 v21; // r8
  char v22; // di
  unsigned __int64 v23; // r8
  int DisplayNameFromVersionInfo; // edi
  __int64 v25; // r8
  unsigned __int64 v26; // rdx
  void **v27; // rsi
  __int64 v28; // rdi
  _DWORD *v29; // rdi
  unsigned __int64 v30; // r8
  volatile signed __int32 *v31; // rdi
  char *v32; // [rsp+20h] [rbp-E0h]
  char *v33; // [rsp+28h] [rbp-D8h]
  DWORD ExitCode; // [rsp+40h] [rbp-C0h] BYREF
  int v35; // [rsp+44h] [rbp-BCh]
  DWORD dwSize; // [rsp+48h] [rbp-B8h] BYREF
  int v37; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v38; // [rsp+58h] [rbp-A8h]
  char *v39; // [rsp+60h] [rbp-A0h]
  char v40[16]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h]
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int128 v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+98h] [rbp-68h]
  __int64 v45; // [rsp+A0h] [rbp-60h]
  __int128 v46; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v48; // [rsp+C0h] [rbp-40h]
  void *v49[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v50; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v51; // [rsp+E0h] [rbp-20h]
  __int64 v52[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h]
  __int64 v54; // [rsp+100h] [rbp+0h]
  __int128 v55; // [rsp+108h] [rbp+8h] BYREF
  __int64 v56; // [rsp+118h] [rbp+18h]
  __int64 v57; // [rsp+120h] [rbp+20h]
  __int128 v58; // [rsp+128h] [rbp+28h] BYREF
  __int64 v59; // [rsp+138h] [rbp+38h]
  __int64 v60; // [rsp+140h] [rbp+40h]
  _BYTE v61[8]; // [rsp+148h] [rbp+48h] BYREF
  __int128 v62; // [rsp+150h] [rbp+50h] BYREF
  __int64 v63; // [rsp+160h] [rbp+60h]
  __int64 v64; // [rsp+168h] [rbp+68h]
  char v65; // [rsp+170h] [rbp+70h]
  char *v66[5]; // [rsp+178h] [rbp+78h] BYREF
  WCHAR ExeName[264]; // [rsp+1A0h] [rbp+A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v38 = a3;
  v4 = (unsigned int)a1;
  v37 = (int)a1;
  v35 = 0;
  *(_DWORD *)a2 = 1;
  Log(4u, L"[QueryAppIdentity] Evaluating candidate client process %d", (unsigned int)a1);
  v5 = (char *)OpenProcess(0x400u, 0, v4);
  v39 = v5;
  if ( ((unsigned __int64)(v5 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    *(_DWORD *)a2 = 2;
    LastError = GetLastError();
    if ( LastError )
    {
      LODWORD(v33) = v4;
      LastErrorMsg = wil::details::in1diag3::Return_Win32Msg(
                       retaddr,
                       (void *)0x107,
                       (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
                       (const char *)LastError,
                       (unsigned int)"[QueryAppIdentity] Failed to open process %d.",
                       v33);
LABEL_4:
      v8 = LastErrorMsg;
LABEL_68:
      if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v5);
      return v8;
    }
  }
  ExitCode = 0;
  if ( !GetExitCodeProcess(v5, &ExitCode) )
  {
    v9 = "[QueryAppIdentity] Failed to get exit code for process %d.";
    v10 = 271;
LABEL_7:
    LODWORD(v32) = v4;
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v10,
                     (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
                     v9,
                     v32);
    goto LABEL_4;
  }
  if ( ExitCode == 259 )
  {
    dwSize = 260;
    memset_0(ExeName, 0, 0x208u);
    if ( !QueryFullProcessImageNameW(v5, 0, ExeName, &dwSize) )
    {
      v9 = "[QueryAppIdentity] Failed to get process image file name for process %d.";
      v10 = 289;
      goto LABEL_7;
    }
    Log(4u, L"[QueryAppIdentity] Process %d executable path: %s", v4, ExeName);
    FileNameW = PathFindFileNameW(ExeName);
    if ( !FileNameW || FileNameW == ExeName )
    {
      LODWORD(v33) = v4;
      v8 = -2147418113;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\appidentity.cpp",
        (const char *)0x8000FFFFLL,
        (int)"[QueryAppIdentity] Failed to find executable name from path for process %d.",
        v33);
      goto LABEL_68;
    }
    v13 = (void ***)&KnownInvalidClients;
    do
    {
      if ( !(unsigned int)_o__wcsicmp(FileNameW, *v13) )
      {
        Log(4u, L"[QueryAppIdentity] Process %s is a known invalid client.", FileNameW);
        Log(4u, L"[QueryAppIdentity] Process %d (%s) is a known invalid client.", v4, ExeName);
        goto LABEL_64;
      }
      ++v13;
    }
    while ( v13 != &`std::_Immortalize_memcpy_image<std::_Generic_error_category>'::`2'::_Static );
    v46 = 0;
    v47 = 0;
    v48 = 7;
    LOWORD(v46) = 0;
    v58 = 0;
    v59 = 0;
    v60 = 7;
    LOWORD(v58) = 0;
    v55 = 0;
    v56 = 0;
    v57 = 7;
    LOWORD(v55) = 0;
    *(_OWORD *)v52 = 0;
    v53 = 0;
    v54 = 7;
    LOWORD(v52[0]) = 0;
    if ( (unsigned __int8)AppIdentity::GetPackageInfoFromHandle(v5, (__int64)v52) )
    {
      v14 = std::wstring::wstring((__int64)v40, (__int64)&v46);
      if ( (unsigned __int8)IsSystemPackage(v14) )
      {
        v15 = &v46;
        if ( v48 > 7 )
          v15 = (__int128 *)v46;
        Log(4u, L"[QueryAppIdentity] Process is a known system packaged app %s. Skipping it.", v15);
      }
      else
      {
        Log(4u, L"[QueryAppIdentity] Process %d (%s) is a valid packaged client.", v4, ExeName);
        if ( v53 )
        {
          v17 = std::wstring::wstring((__int64)v66, (__int64)v52);
          v18 = 2;
        }
        else
        {
          *(_OWORD *)v40 = 0;
          v41 = 0;
          v42 = 0;
          v16 = -1;
          do
            ++v16;
          while ( FileNameW[v16] );
          std::wstring::_Construct<1,wchar_t const *>((char **)v40, FileNameW, v16);
          v17 = (__int64)v40;
          v18 = 1;
        }
        v35 = v18;
        v19 = (__int64 *)std::make_shared<AppIdentity,std::wstring &,std::wstring &,std::wstring &,std::wstring,wchar_t (&)[260],unsigned long &>(
                           (unsigned int)&v43,
                           (unsigned int)&v46,
                           (unsigned int)&v58,
                           (unsigned int)&v55,
                           v17,
                           (__int64)ExeName,
                           (__int64)&v37);
        std::shared_ptr<AppIdentity>::operator=(v38, v19);
        v20 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
        if ( *((_QWORD *)&v43 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
            if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
          }
        }
        if ( (v18 & 2) != 0 )
        {
          LOBYTE(v18) = v18 & 0xFD;
          std::wstring::~wstring(v66);
        }
        if ( (v18 & 1) != 0 )
          std::wstring::~wstring((char **)v40);
        *(_DWORD *)a2 = 0;
      }
    }
    else
    {
      Log(4u, L"[QueryAppIdentity] Process %d (%s) is not packaged. Checking the executable certificate.", v4, ExeName);
      v61[0] = 0;
      v62 = 0;
      v63 = 0;
      v64 = 7;
      LOWORD(v62) = 0;
      v65 = 0;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      v21 = -1;
      do
        ++v21;
      while ( ExeName[v21] );
      std::wstring::_Construct<1,wchar_t const *>((char **)&v43, ExeName, v21);
      if ( (int)CertificateInfo::VerifyFileWithCatalog(&v43, a2, v61) >= 0
        || (v22 = 1,
            (int)CertificateInfo::GetEmbeddedCertificateInfoFromFile((char *)&v43, a2, (struct CertificateInfo *)v61) >= 0) )
      {
        v22 = 0;
      }
      std::wstring::~wstring((char **)&v43);
      if ( !v22 )
      {
        *(_OWORD *)v49 = 0;
        v50 = 0;
        v51 = 7;
        LOWORD(v49[0]) = 0;
        *(_OWORD *)v40 = 0;
        v41 = 0;
        v42 = 0;
        v23 = -1;
        do
          ++v23;
        while ( ExeName[v23] );
        std::wstring::_Construct<1,wchar_t const *>((char **)v40, ExeName, v23);
        DisplayNameFromVersionInfo = CertificateInfo::GetDisplayNameFromVersionInfo(v40);
        std::wstring::~wstring((char **)v40);
        if ( DisplayNameFromVersionInfo < 0 )
        {
          Log(
            4u,
            L"[QueryAppIdentity] Failed to get display name from version info for process %d (%s). Will use executable name %s instead.",
            v4,
            FileNameW);
          v26 = -1;
          do
            ++v26;
          while ( FileNameW[v26] );
          if ( v26 > v51 )
          {
            ____Reallocate_for_V_lambda_1___1_____Assign__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV23_QEB_W_K_Z_PEB_W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign__W_01_AEAAAEAV01_QEB_W0_Z_PEB_W_Z(
              (char **)v49,
              v26,
              v25,
              FileNameW);
          }
          else
          {
            v27 = v49;
            if ( v51 > 7 )
              v27 = (void **)v49[0];
            v50 = v26;
            v28 = 2 * v26;
            memmove_0(v27, FileNameW, 2 * v26);
            *(_WORD *)((char *)v27 + v28) = 0;
          }
        }
        v29 = operator new(0xE0u);
        *(_QWORD *)&v43 = v29;
        *(_OWORD *)v29 = 0;
        v29[2] = 1;
        v29[3] = 1;
        *(_QWORD *)v29 = &std::_Ref_count_obj2<AppIdentity>::`vftable';
        *(_OWORD *)v40 = 0;
        v41 = 0;
        v42 = 0;
        v30 = -1;
        do
          ++v30;
        while ( ExeName[v30] );
        std::wstring::_Construct<1,wchar_t const *>((char **)v40, ExeName, v30);
        AppIdentity::AppIdentity((_DWORD)v29 + 16, (unsigned int)&v62, (unsigned int)v49, (unsigned int)v40, v4);
        std::wstring::~wstring((char **)v40);
        *(_QWORD *)&v43 = v29 + 4;
        *((_QWORD *)&v43 + 1) = v29;
        std::shared_ptr<AppIdentity>::operator=(v38, (__int64 *)&v43);
        v31 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
        if ( *((_QWORD *)&v43 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
            if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
          }
        }
        *(_DWORD *)a2 = 0;
        std::wstring::~wstring((char **)v49);
      }
      std::wstring::~wstring((char **)&v62);
    }
    std::wstring::~wstring((char **)v52);
    std::wstring::~wstring((char **)&v55);
    std::wstring::~wstring((char **)&v58);
    std::wstring::~wstring((char **)&v46);
LABEL_64:
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    return 0;
  }
  else
  {
    Log(3u, L"[QueryAppIdentity] Process %d has exited with code %d.", v4);
    *(_DWORD *)a2 = 2;
    if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v5);
    return 2147500036LL;
  }
}

```

## disassembly

```asm
0x18003886c  mov     [rsp-8+arg_18], rbx
0x180038871  push    rbp
0x180038872  push    rsi
0x180038873  push    rdi
0x180038874  push    r12
0x180038876  push    r13
0x180038878  push    r14
0x18003887a  push    r15
0x18003887c  lea     rbp, [rsp-2C0h]
0x180038884  sub     rsp, 3C0h
0x18003888b  mov     rax, cs:__security_cookie
0x180038892  xor     rax, rsp
0x180038895  mov     [rbp+2F0h+var_40], rax
0x18003889c  mov     [rsp+3F0h+var_398], r8
0x1800388a1  mov     r13, rdx
0x1800388a4  mov     r15d, ecx
0x1800388a7  mov     [rsp+3F0h+var_3A0], ecx
0x1800388ab  xor     esi, esi
0x1800388ad  mov     [rsp+3F0h+var_3AC], esi
0x1800388b1  mov     dword ptr [rdx], 1
0x1800388b7  mov     r8d, ecx
0x1800388ba  lea     rdx, aQueryappidenti_24; "[QueryAppIdentity] Evaluating candidate"...
0x1800388c1  lea     r14d, [rsi+4]
0x1800388c5  mov     ecx, r14d; unsigned __int8
0x1800388c8  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800388cd  mov     r8d, r15d; dwProcessId
0x1800388d0  xor     edx, edx; bInheritHandle
0x1800388d2  mov     ecx, 400h; dwDesiredAccess
0x1800388d7  call    cs:__imp_OpenProcess
0x1800388dd  mov     rbx, rax
0x1800388e0  mov     [rsp+3F0h+var_390], rax
0x1800388e5  inc     rax
0x1800388e8  lea     edi, [rsi+2]
0x1800388eb  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800388f1  jnz     short loc_180038934
0x1800388f3  mov     [r13+0], edi
0x1800388f7  call    cs:__imp_GetLastError
0x1800388fd  test    eax, eax
0x1800388ff  jz      short loc_180038934
0x180038901  mov     rcx, [rbp+2F8h]; this
0x180038908  mov     dword ptr [rsp+3F0h+var_3C8], r15d; char *
0x18003890d  lea     rdx, aQueryappidenti_0; "[QueryAppIdentity] Failed to open proce"...
0x180038914  mov     [rsp+3F0h+var_3D0], rdx; unsigned int
0x180038919  mov     r9d, eax; char *
0x18003891c  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180038923  mov     edx, 107h; void *
0x180038928  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18003892d  mov     edi, eax
0x18003892f  jmp     loc_180038F41
0x180038934  mov     [rsp+3F0h+ExitCode], esi
0x180038938  lea     rdx, [rsp+3F0h+ExitCode]; lpExitCode
0x18003893d  mov     rcx, rbx; hProcess
0x180038940  call    cs:__imp_GetExitCodeProcess
0x180038946  test    eax, eax
0x180038948  jnz     short loc_180038970
0x18003894a  lea     r9, aQueryappidenti_7; "[QueryAppIdentity] Failed to get exit c"...
0x180038951  mov     edx, 10Fh; void *
0x180038956  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003895d  mov     dword ptr [rsp+3F0h+var_3D0], r15d; char *
0x180038962  mov     rcx, [rbp+2F8h]; this
0x180038969  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18003896e  jmp     short loc_18003892D
0x180038970  mov     r9d, [rsp+3F0h+ExitCode]
0x180038975  cmp     r9d, 103h
0x18003897c  jz      short loc_1800389B3
0x18003897e  mov     r8d, r15d
0x180038981  lea     rdx, aQueryappidenti_29; "[QueryAppIdentity] Process %d has exite"...
0x180038988  mov     ecx, 3; unsigned __int8
0x18003898d  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180038992  mov     [r13+0], edi
0x180038996  lea     rax, [rbx-1]
0x18003899a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003899e  ja      short loc_1800389A9
0x1800389a0  mov     rcx, rbx; hObject
0x1800389a3  call    cs:__imp_CloseHandle
0x1800389a9  mov     eax, 80004004h
0x1800389ae  jmp     loc_180038F56
0x1800389b3  mov     [rsp+3F0h+dwSize], 104h
0x1800389bb  xor     edx, edx; Val
0x1800389bd  mov     r8d, 208h; Size
0x1800389c3  lea     rcx, [rbp+2F0h+ExeName]; void *
0x1800389ca  call    memset_0
0x1800389cf  lea     r9, [rsp+3F0h+dwSize]; lpdwSize
0x1800389d4  lea     r8, [rbp+2F0h+ExeName]; lpExeName
0x1800389db  xor     edx, edx; dwFlags
0x1800389dd  mov     rcx, rbx; hProcess
0x1800389e0  call    cs:__imp_QueryFullProcessImageNameW
0x1800389e6  test    eax, eax
0x1800389e8  jnz     short loc_1800389FB
0x1800389ea  lea     r9, aQueryappidenti_15; "[QueryAppIdentity] Failed to get proces"...
0x1800389f1  mov     edx, 121h
0x1800389f6  jmp     loc_180038956
0x1800389fb  lea     r9, [rbp+2F0h+ExeName]
0x180038a02  mov     r8d, r15d
0x180038a05  lea     rdx, aQueryappidenti_13; "[QueryAppIdentity] Process %d executabl"...
0x180038a0c  mov     ecx, r14d; unsigned __int8
0x180038a0f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180038a14  lea     rcx, [rbp+2F0h+ExeName]; pszPath
0x180038a1b  call    cs:__imp_PathFindFileNameW
0x180038a21  mov     r12, rax
0x180038a24  test    rax, rax
0x180038a27  jz      loc_180038F0F
0x180038a2d  lea     rax, [rbp+2F0h+ExeName]
0x180038a34  cmp     r12, rax
0x180038a37  jz      loc_180038F0F
0x180038a3d  lea     rdi, ?KnownInvalidClients@@3PAPEB_WA; wchar_t const * near * KnownInvalidClients
0x180038a44  mov     rdx, [rdi]
0x180038a47  mov     rcx, r12
0x180038a4a  call    cs:__imp__o__wcsicmp
0x180038a50  test    eax, eax
0x180038a52  jz      loc_180038ECC
0x180038a58  add     rdi, 8
0x180038a5c  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Generic_error_category@std@@@std@@YAAEBV_Generic_error_category@1@XZ@4V21@B; std::_Generic_error_category const `std::_Immortalize_memcpy_image<std::_Generic_error_category>(void)'::`2'::_Static
0x180038a63  cmp     rdi, rax
0x180038a66  jnz     short loc_180038A44
0x180038a68  xorps   xmm0, xmm0
0x180038a6b  movups  [rbp+2F0h+var_348], xmm0
0x180038a6f  mov     [rbp+2F0h+var_338], rsi
0x180038a73  mov     edi, 7
0x180038a78  mov     [rbp+2F0h+var_330], rdi
0x180038a7c  mov     word ptr [rbp+2F0h+var_348], si
0x180038a80  movups  [rbp+2F0h+var_2C8], xmm0
0x180038a84  mov     [rbp+2F0h+var_2B8], rsi
0x180038a88  mov     [rbp+2F0h+var_2B0], rdi
0x180038a8c  mov     word ptr [rbp+2F0h+var_2C8], si
0x180038a90  movups  [rbp+2F0h+var_2E8], xmm0
0x180038a94  mov     [rbp+2F0h+var_2D8], rsi
0x180038a98  mov     [rbp+2F0h+var_2D0], rdi
0x180038a9c  mov     word ptr [rbp+2F0h+var_2E8], si
0x180038aa0  movups  xmmword ptr [rbp+2F0h+var_308], xmm0
0x180038aa4  mov     [rbp+2F0h+var_2F8], rsi
0x180038aa8  mov     [rbp+2F0h+var_2F0], rdi
0x180038aac  mov     word ptr [rbp+2F0h+var_308], si
0x180038ab0  lea     rax, [rbp+2F0h+var_308]
0x180038ab4  mov     [rsp+3F0h+var_3D0], rax; __int64
0x180038ab9  lea     r9, [rbp+2F0h+var_2E8]
0x180038abd  lea     r8, [rbp+2F0h+var_2C8]
0x180038ac1  lea     rdx, [rbp+2F0h+var_348]
0x180038ac5  mov     rcx, rbx; hProcess
0x180038ac8  call    ?GetPackageInfoFromHandle@AppIdentity@@CA_NPEAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@111@Z; AppIdentity::GetPackageInfoFromHandle(void *,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x180038acd  test    al, al
0x180038acf  jz      loc_180038C53
0x180038ad5  lea     rdx, [rbp+2F0h+var_348]
0x180038ad9  lea     rcx, [rsp+3F0h+var_388]
0x180038ade  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038ae3  mov     rcx, rax
0x180038ae6  call    ?IsSystemPackage@@YA_NV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; IsSystemPackage(std::wstring)
0x180038aeb  mov     ecx, r14d; unsigned __int8
0x180038aee  test    al, al
0x180038af0  jz      short loc_180038B38
0x180038af2  lea     r8, [rbp+2F0h+var_348]
0x180038af6  cmp     [rbp+2F0h+var_330], rdi
0x180038afa  cmova   r8, qword ptr [rbp+2F0h+var_348]
0x180038aff  lea     rdx, aQueryappidenti_35; "[QueryAppIdentity] Process is a known s"...
0x180038b06  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180038b0b  nop
0x180038b0c  lea     rcx, [rbp+2F0h+var_308]
0x180038b10  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038b15  nop
0x180038b16  lea     rcx, [rbp+2F0h+var_2E8]
0x180038b1a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038b1f  nop
0x180038b20  lea     rcx, [rbp+2F0h+var_2C8]
0x180038b24  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038b29  nop
0x180038b2a  lea     rcx, [rbp+2F0h+var_348]
0x180038b2e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038b33  jmp     loc_180038EF8
0x180038b38  lea     r9, [rbp+2F0h+ExeName]
0x180038b3f  mov     r8d, r15d
0x180038b42  lea     rdx, aQueryappidenti_14; "[QueryAppIdentity] Process %d (%s) is a"...
0x180038b49  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180038b4e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180038b52  cmp     [rbp+2F0h+var_2F8], rsi
0x180038b56  jnz     short loc_180038B8F
0x180038b58  xorps   xmm0, xmm0
0x180038b5b  movups  xmmword ptr [rsp+3F0h+var_388], xmm0
0x180038b60  mov     [rsp+3F0h+var_378], rsi
0x180038b65  mov     [rbp+2F0h+var_370], rsi
0x180038b69  mov     r8, r14
0x180038b6c  inc     r8
0x180038b6f  cmp     [r12+r8*2], si
0x180038b74  jnz     short loc_180038B6C
0x180038b76  mov     rdx, r12
0x180038b79  lea     rcx, [rsp+3F0h+var_388]
0x180038b7e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180038b83  lea     rax, [rsp+3F0h+var_388]
0x180038b88  mov     esi, 1
0x180038b8d  jmp     short loc_180038BA2
0x180038b8f  lea     rdx, [rbp+2F0h+var_308]
0x180038b93  lea     rcx, [rbp+2F0h+var_278]
0x180038b97  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180038b9c  nop
0x180038b9d  mov     esi, 2
0x180038ba2  mov     [rsp+3F0h+var_3AC], esi
0x180038ba6  lea     rdx, [rsp+3F0h+var_3A0]
0x180038bab  mov     [rsp+3F0h+var_3C0], rdx
0x180038bb0  lea     rdx, [rbp+2F0h+ExeName]
0x180038bb7  mov     [rsp+3F0h+var_3C8], rdx
0x180038bbc  mov     [rsp+3F0h+var_3D0], rax
0x180038bc1  lea     r9, [rbp+2F0h+var_2E8]
0x180038bc5  lea     r8, [rbp+2F0h+var_2C8]
0x180038bc9  lea     rdx, [rbp+2F0h+var_348]
0x180038bcd  lea     rcx, [rbp+2F0h+var_368]
0x180038bd1  call    ??$make_shared@VAppIdentity@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@AEAV23@V23@AEAY0BAE@_WAEAK@std@@YA?AV?$shared_ptr@VAppIdentity@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@00$$QEAV20@AEAY0BAE@_WAEAK@Z; std::make_shared<AppIdentity,std::wstring &,std::wstring &,std::wstring &,std::wstring,wchar_t (&)[260],ulong &>(std::wstring &,std::wstring &,std::wstring &,std::wstring &&,wchar_t (&)[260],ulong &)
0x180038bd6  mov     rdx, rax
0x180038bd9  mov     rcx, [rsp+3F0h+var_398]
0x180038bde  call    ??4?$shared_ptr@VAppIdentity@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<AppIdentity>::operator=(std::shared_ptr<AppIdentity> &&)
0x180038be3  mov     rdi, qword ptr [rbp+2F0h+var_368+8]
0x180038be7  xor     r12d, r12d
0x180038bea  test    rdi, rdi
0x180038bed  jz      short loc_180038C27
0x180038bef  mov     eax, r14d
0x180038bf2  lock xadd [rdi+8], eax
0x180038bf7  add     eax, r14d
0x180038bfa  jnz     short loc_180038C27
0x180038bfc  mov     rax, [rdi]
0x180038bff  mov     rcx, rdi
0x180038c02  mov     rax, [rax]
0x180038c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c0a  mov     eax, r14d
0x180038c0d  lock xadd [rdi+0Ch], eax
0x180038c12  add     eax, r14d
0x180038c15  jnz     short loc_180038C27
0x180038c17  mov     rax, [rdi]
0x180038c1a  mov     rcx, rdi
0x180038c1d  mov     rax, [rax+8]
0x180038c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c26  nop
0x180038c27  test    sil, 2
0x180038c2b  jz      short loc_180038C3A
0x180038c2d  and     esi, 0FFFFFFFDh
0x180038c30  lea     rcx, [rbp+2F0h+var_278]
0x180038c34  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038c39  nop
0x180038c3a  test    sil, 1
0x180038c3e  jz      short loc_180038C4A
0x180038c40  lea     rcx, [rsp+3F0h+var_388]
0x180038c45  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038c4a  mov     [r13+0], r12d
0x180038c4e  jmp     loc_180038B0C
0x180038c53  lea     r9, [rbp+2F0h+ExeName]
0x180038c5a  mov     r8d, r15d
0x180038c5d  lea     rdx, aQueryappidenti_6; "[QueryAppIdentity] Process %d (%s) is n"...
0x180038c64  mov     ecx, r14d; unsigned __int8
0x180038c67  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180038c6c  mov     [rbp+2F0h+var_2A8], sil
0x180038c70  xorps   xmm0, xmm0
0x180038c73  movups  [rbp+2F0h+var_2A0], xmm0
0x180038c77  mov     [rbp+2F0h+var_290], rsi
0x180038c7b  mov     [rbp+2F0h+var_288], rdi
0x180038c7f  mov     word ptr [rbp+2F0h+var_2A0], si
0x180038c83  mov     [rbp+2F0h+var_280], sil
0x180038c87  movups  [rbp+2F0h+var_368], xmm0
0x180038c8b  mov     [rbp+2F0h+var_358], rsi
0x180038c8f  mov     [rbp+2F0h+var_350], rsi
0x180038c93  lea     rax, [rbp+2F0h+ExeName]
0x180038c9a  or      r14, 0FFFFFFFFFFFFFFFFh
0x180038c9e  mov     r8, r14
0x180038ca1  inc     r8
0x180038ca4  cmp     [rax+r8*2], si
0x180038ca9  jnz     short loc_180038CA1
0x180038cab  lea     rdx, [rbp+2F0h+ExeName]
0x180038cb2  lea     rcx, [rbp+2F0h+var_368]
0x180038cb6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180038cbb  nop
0x180038cbc  lea     r8, [rbp+2F0h+var_2A8]
0x180038cc0  mov     rdx, r13
0x180038cc3  lea     rcx, [rbp+2F0h+var_368]
0x180038cc7  call    ?VerifyFileWithCatalog@CertificateInfo@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV1@@Z; CertificateInfo::VerifyFileWithCatalog(std::wstring const &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,CertificateInfo &)
0x180038ccc  test    eax, eax
0x180038cce  jns     short loc_180038CE7
0x180038cd0  lea     r8, [rbp+2F0h+var_2A8]
0x180038cd4  mov     rdx, r13
0x180038cd7  lea     rcx, [rbp+2F0h+var_368]
0x180038cdb  call    ?GetEmbeddedCertificateInfoFromFile@CertificateInfo@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@AEAV1@@Z; CertificateInfo::GetEmbeddedCertificateInfoFromFile(std::wstring const &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &,CertificateInfo &)
0x180038ce0  test    eax, eax
0x180038ce2  mov     dil, 1
0x180038ce5  js      short loc_180038CEA
0x180038ce7  mov     dil, sil
0x180038cea  lea     rcx, [rbp+2F0h+var_368]
0x180038cee  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038cf3  test    dil, dil
0x180038cf6  jz      short loc_180038D06
0x180038cf8  lea     rcx, [rbp+2F0h+var_2A0]
0x180038cfc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038d01  jmp     loc_180038B0C
0x180038d06  xorps   xmm0, xmm0
0x180038d09  movups  xmmword ptr [rbp+2F0h+var_328], xmm0
0x180038d0d  mov     [rbp+2F0h+var_318], rsi
0x180038d11  mov     [rbp+2F0h+var_310], 7
0x180038d19  mov     word ptr [rbp+2F0h+var_328], si
0x180038d1d  movups  xmmword ptr [rsp+3F0h+var_388], xmm0
0x180038d22  mov     [rsp+3F0h+var_378], rsi
0x180038d27  mov     [rbp+2F0h+var_370], rsi
0x180038d2b  lea     rax, [rbp+2F0h+ExeName]
0x180038d32  mov     r8, r14
0x180038d35  inc     r8
0x180038d38  cmp     [rax+r8*2], si
0x180038d3d  jnz     short loc_180038D35
  ... truncated ...
```
