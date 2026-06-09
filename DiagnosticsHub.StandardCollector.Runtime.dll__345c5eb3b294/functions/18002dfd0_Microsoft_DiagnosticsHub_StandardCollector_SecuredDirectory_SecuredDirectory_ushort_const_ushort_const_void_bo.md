# Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::SecuredDirectory(ushort const *,ushort const *,void *,bool)

- ea: `0x18002dfd0`
- end: `0x18002e980`
- name: `??0SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@AEAA@PEBG0PEAX_N@Z`
- size: `2480`
- prototype: `Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *__fastcall(Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *this, const unsigned __int16 *, const unsigned __int16 *, void *, bool)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18002d9a4`

## callees

- `0x1800023c0`
- `0x1800023c4`
- `0x180002604`
- `0x18000288c`
- `0x18000a17c`
- `0x18002d698`
- `0x18002de3c`
- `0x18002dfd0`
- `0x18002f17c`
- `0x18002f2a0`
- `0x18002f63c`
- `0x18002f7d0`
- `0x18002fa20`
- `0x18002fb2c`
- `0x18002fc38`
- `0x18003070c`
- `0x180031284`
- `0x18003153c`
- `0x1800315c8`
- `0x1800316c4`
- `0x18003d864`
- `0x180049b50`
- `0x18004ad58`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e1a3`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e1e7`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e38a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e3ce`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e1a3`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e1e7`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e38a`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18002e3ce`
- `KERNEL32!SetLastError` at `0x18002e58e`
- `KERNEL32!SetLastError` at `0x18002e58e`
- `KERNEL32!GetCurrentProcess` at `0x18002e08a`
- `KERNEL32!GetCurrentProcess` at `0x18002e093`
- `KERNEL32!GetCurrentProcess` at `0x18002e08a`
- `KERNEL32!GetCurrentProcess` at `0x18002e093`
- `KERNEL32!DuplicateHandle` at `0x18002e0bd`
- `KERNEL32!DuplicateHandle` at `0x18002e0bd`
- `KERNEL32!CreateFileW` at `0x18002e181`
- `KERNEL32!CreateFileW` at `0x18002e368`
- `KERNEL32!CreateFileW` at `0x18002e478`
- `KERNEL32!CreateFileW` at `0x18002e181`
- `KERNEL32!CreateFileW` at `0x18002e368`
- `KERNEL32!CreateFileW` at `0x18002e478`
- `KERNEL32!InitializeCriticalSection` at `0x18002e083`
- `KERNEL32!InitializeCriticalSection` at `0x18002e083`
- `KERNEL32!GetLastError` at `0x18002e0ef`
- `KERNEL32!GetLastError` at `0x18002e641`
- `KERNEL32!GetLastError` at `0x18002e66c`
- `KERNEL32!GetLastError` at `0x18002e6a1`
- `KERNEL32!GetLastError` at `0x18002e6cb`
- `KERNEL32!GetLastError` at `0x18002e70f`
- `KERNEL32!GetLastError` at `0x18002e739`
- `KERNEL32!GetLastError` at `0x18002e763`
- `KERNEL32!GetLastError` at `0x18002e78d`
- `KERNEL32!GetLastError` at `0x18002e7eb`
- `KERNEL32!GetLastError` at `0x18002e815`
- `KERNEL32!GetLastError` at `0x18002e83f`
- `KERNEL32!GetLastError` at `0x18002e869`
- `KERNEL32!GetLastError` at `0x18002e8d2`
- `KERNEL32!GetLastError` at `0x18002e92c`
- `KERNEL32!GetLastError` at `0x18002e956`
- `KERNEL32!GetLastError` at `0x18002e0ef`
- `KERNEL32!GetLastError` at `0x18002e641`
- `KERNEL32!GetLastError` at `0x18002e66c`
- `KERNEL32!GetLastError` at `0x18002e6a1`
- `KERNEL32!GetLastError` at `0x18002e6cb`
- `KERNEL32!GetLastError` at `0x18002e70f`
- `KERNEL32!GetLastError` at `0x18002e739`
- `KERNEL32!GetLastError` at `0x18002e763`
- `KERNEL32!GetLastError` at `0x18002e78d`
- `KERNEL32!GetLastError` at `0x18002e7eb`
- `KERNEL32!GetLastError` at `0x18002e815`
- `KERNEL32!GetLastError` at `0x18002e83f`
- `KERNEL32!GetLastError` at `0x18002e869`
- `KERNEL32!GetLastError` at `0x18002e8d2`
- `KERNEL32!GetLastError` at `0x18002e92c`
- `KERNEL32!GetLastError` at `0x18002e956`
- `ADVAPI32!GetTokenInformation` at `0x18002e0e9`
- `ADVAPI32!GetTokenInformation` at `0x18002e12f`
- `ADVAPI32!GetTokenInformation` at `0x18002e0e9`
- `ADVAPI32!GetTokenInformation` at `0x18002e12f`
- `ADVAPI32!SetSecurityInfo` at `0x18002e584`
- `ADVAPI32!SetSecurityInfo` at `0x18002e584`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002e238`
- `api-ms-win-crt-string-l1-1-0!wcsncmp` at `0x18002e238`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002e614`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002e614`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002e101`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18002e101`

## string_xrefs

- `0x18002e90a`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\SecuredDirectory.cpp`
- `0x18002e903`: `Failed to create lock file in secure file directory '%s': %#08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *__fastcall Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::SecuredDirectory(
        Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4,
        bool a5)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  HANDLE *v10; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v12; // rax
  const struct _SID **v13; // rbx
  const unsigned __int16 *v14; // r8
  __int64 v15; // rax
  HANDLE FileW; // rax
  DWORD FinalPathNameByHandleW; // eax
  DWORD v18; // eax
  int v19; // eax
  const wchar_t *v20; // rdx
  unsigned __int8 v21; // r9
  bool v22; // r8
  void *v23; // rax
  HANDLE v24; // rax
  DWORD v25; // eax
  struct ATL::IAtlStringMgr *v26; // rax
  LPCWSTR v27; // rdi
  HANDLE v28; // rax
  unsigned __int8 v29; // r9
  bool v30; // si
  unsigned __int8 v31; // r9
  unsigned __int8 v32; // r9
  void *v33; // rsi
  ACL *PACL; // rax
  DWORD v35; // esi
  signed int v37; // eax
  unsigned int v38; // ecx
  signed int v39; // eax
  unsigned int v40; // ecx
  signed int LastError; // eax
  unsigned int v42; // ecx
  signed int v43; // eax
  unsigned int v44; // ecx
  signed int v45; // eax
  unsigned int v46; // ecx
  signed int v47; // eax
  unsigned int v48; // ecx
  signed int v49; // eax
  unsigned int v50; // ecx
  signed int v51; // eax
  unsigned int v52; // ecx
  signed int v53; // eax
  unsigned int v54; // ecx
  signed int v55; // eax
  unsigned int v56; // ecx
  signed int v57; // eax
  unsigned int v58; // ecx
  signed int v59; // eax
  unsigned int v60; // ecx
  signed int v61; // eax
  unsigned int v62; // ebx
  __int64 v63; // rax
  signed int v64; // eax
  unsigned int v65; // ecx
  signed int v66; // eax
  unsigned int v67; // ecx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-E0h]
  int pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpszFilePath[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v71; // [rsp+58h] [rbp-A8h]
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR String1[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v74; // [rsp+78h] [rbp-88h]
  Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *v75; // [rsp+80h] [rbp-80h]
  const struct _SID **v76; // [rsp+88h] [rbp-78h]
  _BYTE v77[128]; // [rsp+90h] [rbp-70h] BYREF
  DWORD ReturnLength; // [rsp+110h] [rbp+10h] BYREF
  struct _SECURITY_DESCRIPTOR *v79[2]; // [rsp+118h] [rbp+18h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+128h] [rbp+28h] BYREF
  void **v81; // [rsp+140h] [rbp+40h] BYREF
  void *v82; // [rsp+148h] [rbp+48h]
  _QWORD v83[3]; // [rsp+150h] [rbp+50h] BYREF
  __int128 v84; // [rsp+168h] [rbp+68h]
  __int64 v85; // [rsp+178h] [rbp+78h]
  __int64 v86; // [rsp+180h] [rbp+80h]
  _QWORD v87[3]; // [rsp+188h] [rbp+88h] BYREF
  __int128 v88; // [rsp+1A0h] [rbp+A0h]
  __int64 v89; // [rsp+1B0h] [rbp+B0h]
  __int64 v90; // [rsp+1B8h] [rbp+B8h]

  v75 = this;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  *(_QWORD *)this = (*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance) + 24;
  *((_BYTE *)this + 8) = 1;
  *((_BYTE *)this + 9) = a5;
  v10 = (HANDLE *)((char *)this + 16);
  *((_QWORD *)this + 2) = 0;
  ATL::CSid::CSid((Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)((char *)this + 24));
  *((_QWORD *)this + 18) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *(_OWORD *)((char *)this + 168) = 0;
  *(_OWORD *)((char *)this + 184) = 0;
  *((_QWORD *)this + 25) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  CurrentProcess = GetCurrentProcess();
  v12 = GetCurrentProcess();
  if ( !DuplicateHandle(v12, a4, CurrentProcess, (LPHANDLE)this + 2, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v42 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v42 = LastError;
    pExceptionObject = v42;
    throw (long *)&pExceptionObject;
  }
  ReturnLength = 0;
  GetTokenInformation(*v10, TokenUser, 0, 0, &ReturnLength);
  if ( GetLastError() != 122 )
  {
    v43 = GetLastError();
    v44 = (unsigned __int16)v43 | 0x80070000;
    if ( v43 <= 0 )
      v44 = v43;
    pExceptionObject = v44;
    throw (long *)&pExceptionObject;
  }
  v13 = (const struct _SID **)malloc(ReturnLength);
  v76 = v13;
  if ( !v13 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !GetTokenInformation(*v10, TokenUser, v13, ReturnLength, &ReturnLength) )
  {
    v45 = GetLastError();
    v46 = (unsigned __int16)v45 | 0x80070000;
    if ( v45 <= 0 )
      v46 = v45;
    pExceptionObject = v46;
    throw (long *)&pExceptionObject;
  }
  v15 = ATL::CSid::CSid((ATL::CSid *)v77, *v13, v14);
  ATL::CSid::operator=((char *)this + 24, v15);
  ATL::CSid::~CSid((ATL::CSid *)v77);
  FileW = CreateFileW(a2, 1u, 3u, 0, 3u, 0x2000000u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    v47 = GetLastError();
    v48 = (unsigned __int16)v47 | 0x80070000;
    if ( v47 <= 0 )
      v48 = v47;
    pExceptionObject = v48;
    throw (long *)&pExceptionObject;
  }
  *((_QWORD *)this + 19) = FileW;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
  if ( !FinalPathNameByHandleW )
  {
    v49 = GetLastError();
    v50 = (unsigned __int16)v49 | 0x80070000;
    if ( v49 <= 0 )
      v50 = v49;
    pExceptionObject = v50;
    throw (long *)&pExceptionObject;
  }
  *(_OWORD *)lpszFilePath = 0;
  v71 = 0;
  std::vector<unsigned short>::vector<unsigned short>(lpszFilePath, FinalPathNameByHandleW);
  v18 = GetFinalPathNameByHandleW(*((HANDLE *)this + 19), lpszFilePath[0], lpszFilePath[1] - lpszFilePath[0], 0);
  if ( !v18 )
  {
    v51 = GetLastError();
    v52 = (unsigned __int16)v51 | 0x80070000;
    if ( v51 <= 0 )
      v52 = v51;
    pExceptionObject = v52;
    throw (long *)&pExceptionObject;
  }
  if ( (unsigned __int64)v18 + 1 > lpszFilePath[1] - lpszFilePath[0] )
  {
    pExceptionObject = -2147418113;
    throw (long *)&pExceptionObject;
  }
  _mm_lfence();
  if ( (unsigned int)Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifyUserHasWriteAccess(
                       *v10,
                       lpszFilePath[0]) )
  {
    pExceptionObject = -2147024891;
    throw (long *)&pExceptionObject;
  }
  v19 = wcsncmp(lpszFilePath[0], L"\\\\?\\", 4u);
  v20 = L"\\\\?\\%s\\%s\\";
  if ( !v19 )
    v20 = L"%s\\%s\\";
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    this,
    v20,
    lpszFilePath[0],
    a3);
  v87[1] = 0;
  v87[2] = 0x200000000LL;
  v87[0] = &ATL::CDacl::`vftable';
  v88 = 0;
  v89 = 0;
  v90 = 0;
  if ( !ATL::CDacl::AddAllowedAce((ATL::CDacl *)v87, (const struct ATL::CSid *)&qword_180077070, 0x10000000u, v21) )
  {
    v53 = GetLastError();
    v54 = (unsigned __int16)v53 | 0x80070000;
    if ( v53 <= 0 )
      v54 = v53;
    pExceptionObject = v54;
    throw (long *)&pExceptionObject;
  }
  v79[0] = (struct _SECURITY_DESCRIPTOR *)&ATL::CSecurityDesc::`vftable';
  v79[1] = 0;
  ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)v79, (const struct ATL::CDacl *)v87, v22);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  v81 = &ATL::CSecurityDesc::`vftable';
  v23 = 0;
  v82 = 0;
  if ( v79[1] )
  {
    ATL::CSecurityDesc::Init((ATL::CSecurityDesc *)&v81, v79[1]);
    v23 = v82;
  }
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = v23;
  SecurityAttributes.bInheritHandle = 0;
  v24 = CreateFileW(*(LPCWSTR *)this, 0xC0050001, 1u, &SecurityAttributes, 1u, 0x3200010u, 0);
  if ( v24 == (HANDLE)-1LL )
  {
    v55 = GetLastError();
    v56 = (unsigned __int16)v55 | 0x80070000;
    if ( v55 <= 0 )
      v56 = v55;
    pExceptionObject = v56;
    throw (long *)&pExceptionObject;
  }
  *((_QWORD *)this + 20) = v24;
  v25 = GetFinalPathNameByHandleW(v24, 0, 0, 0);
  if ( !v25 )
  {
    v57 = GetLastError();
    v58 = (unsigned __int16)v57 | 0x80070000;
    if ( v57 <= 0 )
      v58 = v57;
    pExceptionObject = v58;
    throw (long *)&pExceptionObject;
  }
  *(_OWORD *)String1 = 0;
  v74 = 0;
  std::vector<unsigned short>::vector<unsigned short>(String1, v25);
  if ( !GetFinalPathNameByHandleW(*((HANDLE *)this + 20), String1[0], String1[1] - String1[0], 0) )
  {
    v59 = GetLastError();
    v60 = (unsigned __int16)v59 | 0x80070000;
    if ( v59 <= 0 )
      v60 = v59;
    pExceptionObject = v60;
    throw (long *)&pExceptionObject;
  }
  if ( lpszFilePath[1] - lpszFilePath[0] >= (unsigned __int64)(String1[1] - String1[0]) )
  {
    pExceptionObject = -2147024891;
    throw (long *)&pExceptionObject;
  }
  _mm_lfence();
  if ( (unsigned int)anonymous_namespace_::ValidateSamePath_0(String1[0], *(wchar_t **)this) )
  {
    pExceptionObject = -2147024891;
    throw (long *)&pExceptionObject;
  }
  v26 = ATL::CAtlStringMgr::GetInstance();
  if ( !v26 )
    ATL::AtlThrowImpl(-2147467259);
  lpFileName = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)v26 + 24LL))(v26) + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &lpFileName,
    L"%slock",
    *(_QWORD *)this);
  v27 = lpFileName;
  v28 = CreateFileW(lpFileName, 0xC0000000, 0, 0, 1u, 0x4000002u, 0);
  if ( v28 == (HANDLE)-1LL )
  {
    v61 = GetLastError();
    v62 = (unsigned __int16)v61 | 0x80070000;
    if ( v61 <= 0 )
      v62 = v61;
    v63 = ATL::CSimpleStringT<unsigned short,0>::operator unsigned short const *(this);
    dwDesiredAccess[0] = v62;
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\SecuredDirectory.cpp",
      L"Failed to create lock file in secure file directory '%s': %#08x",
      v63,
      *(_QWORD *)dwDesiredAccess);
    pExceptionObject = v62;
    throw (long *)&pExceptionObject;
  }
  *((_QWORD *)this + 18) = v28;
  v83[1] = 0;
  v83[2] = 0x200000000LL;
  v83[0] = &ATL::CDacl::`vftable';
  v84 = 0;
  v85 = 0;
  v86 = 0;
  dwDesiredAccess[0] = 544;
  ATL::CSid::CSid(
    (ATL::CSid *)v77,
    (const struct _SID_IDENTIFIER_AUTHORITY *)&ATL::Sids::SecurityNTAuthority,
    2u,
    32,
    *(_QWORD *)dwDesiredAccess);
  v30 = ATL::CDacl::AddAllowedAce((ATL::CDacl *)v83, (const struct ATL::CSid *)v77, 0x10000000u, v29);
  ATL::CSid::~CSid((ATL::CSid *)v77);
  if ( !v30 )
  {
    v64 = GetLastError();
    v65 = (unsigned __int16)v64 | 0x80070000;
    if ( v64 <= 0 )
      v65 = v64;
    pExceptionObject = v65;
    throw (long *)&pExceptionObject;
  }
  if ( !ATL::CDacl::AddAllowedAce((ATL::CDacl *)v83, (const struct ATL::CSid *)&qword_180077070, 0x10000000u, v31) )
  {
    v66 = GetLastError();
    v67 = (unsigned __int16)v66 | 0x80070000;
    if ( v66 <= 0 )
      v67 = v66;
    pExceptionObject = v67;
    throw (long *)&pExceptionObject;
  }
  if ( !ATL::CDacl::AddAllowedAce(
          (ATL::CDacl *)v83,
          (Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory *)((char *)this + 24),
          0x120089u,
          v32) )
  {
    v37 = GetLastError();
    v38 = (unsigned __int16)v37 | 0x80070000;
    if ( v37 <= 0 )
      v38 = v37;
    pExceptionObject = v38;
    throw (long *)&pExceptionObject;
  }
  v33 = (void *)*((_QWORD *)this + 20);
  if ( !v33
    || (PACL = (ACL *)ATL::CAcl::GetPACL((ATL::CAcl *)v83),
        v35 = SetSecurityInfo(v33, SE_FILE_OBJECT, 0x80000004, 0, 0, PACL, 0),
        SetLastError(v35),
        v35) )
  {
    v39 = GetLastError();
    v40 = (unsigned __int16)v39 | 0x80070000;
    if ( v39 <= 0 )
      v40 = v39;
    pExceptionObject = v40;
    throw (long *)&pExceptionObject;
  }
  ATL::CDacl::~CDacl((ATL::CDacl *)v83);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v27 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v27 - 3) + 8LL))(*((_QWORD *)v27 - 3));
  }
  std::vector<unsigned short>::~vector<unsigned short>(String1);
  v81 = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)&v81);
  v79[0] = (struct _SECURITY_DESCRIPTOR *)&ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v79);
  ATL::CDacl::~CDacl((ATL::CDacl *)v87);
  std::vector<unsigned short>::~vector<unsigned short>(lpszFilePath);
  free(v13);
  return this;
}

```

## disassembly

```asm
0x18002dfd0  push    rbp
0x18002dfd2  push    rbx
0x18002dfd3  push    rsi
0x18002dfd4  push    rdi
0x18002dfd5  push    r12
0x18002dfd7  push    r13
0x18002dfd9  push    r14
0x18002dfdb  push    r15
0x18002dfdd  lea     rbp, [rsp-0D8h]
0x18002dfe5  sub     rsp, 1D8h
0x18002dfec  mov     rax, cs:__security_cookie
0x18002dff3  xor     rax, rsp
0x18002dff6  mov     [rbp+110h+var_50], rax
0x18002dffd  mov     r12, r9
0x18002e000  mov     rsi, r8
0x18002e003  mov     r15, rdx
0x18002e006  mov     r14, rcx
0x18002e009  mov     [rbp+110h+var_190], rcx
0x18002e00d  xor     ebx, ebx
0x18002e00f  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002e014  mov     rcx, rax
0x18002e017  test    rax, rax
0x18002e01a  jz      loc_18002E696
0x18002e020  mov     rax, [rax]
0x18002e023  mov     rax, [rax+18h]
0x18002e027  call    cs:__guard_dispatch_icall_fptr
0x18002e02d  add     rax, 18h
0x18002e031  mov     [r14], rax
0x18002e034  mov     byte ptr [r14+8], 1
0x18002e039  mov     al, [rbp+110h+arg_20]
0x18002e03f  mov     [r14+9], al
0x18002e043  lea     rdi, [r14+10h]
0x18002e047  mov     [rdi], rbx
0x18002e04a  lea     r13, [r14+18h]
0x18002e04e  mov     rcx, r13; this
0x18002e051  call    ??0CSid@ATL@@QEAA@XZ; ATL::CSid::CSid(void)
0x18002e056  nop
0x18002e057  mov     [r14+90h], rbx
0x18002e05e  mov     [r14+98h], rbx
0x18002e065  mov     [r14+0A0h], rbx
0x18002e06c  lea     rcx, [r14+0A8h]; lpCriticalSection
0x18002e073  xorps   xmm0, xmm0
0x18002e076  xor     eax, eax
0x18002e078  movups  xmmword ptr [rcx], xmm0
0x18002e07b  movups  xmmword ptr [rcx+10h], xmm0
0x18002e07f  mov     [rcx+20h], rax
0x18002e083  call    cs:__imp_InitializeCriticalSection
0x18002e089  nop
0x18002e08a  call    cs:__imp_GetCurrentProcess
0x18002e090  mov     rbx, rax
0x18002e093  call    cs:__imp_GetCurrentProcess
0x18002e099  mov     [rsp+210h+dwOptions], 2; dwOptions
0x18002e0a1  mov     [rsp+210h+bInheritHandle], 0; bInheritHandle
0x18002e0a9  mov     [rsp+210h+dwDesiredAccess], 0; dwDesiredAccess
0x18002e0b1  mov     r9, rdi; lpTargetHandle
0x18002e0b4  mov     r8, rbx; hTargetProcessHandle
0x18002e0b7  mov     rdx, r12; hSourceHandle
0x18002e0ba  mov     rcx, rax; hSourceProcessHandle
0x18002e0bd  call    cs:__imp_DuplicateHandle
0x18002e0c3  xor     r12d, r12d
0x18002e0c6  test    eax, eax
0x18002e0c8  jz      loc_18002E6A1
0x18002e0ce  mov     [rbp+110h+ReturnLength], r12d
0x18002e0d2  lea     rax, [rbp+110h+ReturnLength]
0x18002e0d6  mov     qword ptr [rsp+210h+dwDesiredAccess], rax; ReturnLength
0x18002e0db  xor     r9d, r9d; TokenInformationLength
0x18002e0de  xor     r8d, r8d; TokenInformation
0x18002e0e1  lea     edx, [r12+1]; TokenInformationClass
0x18002e0e6  mov     rcx, [rdi]; TokenHandle
0x18002e0e9  call    cs:__imp_GetTokenInformation
0x18002e0ef  call    cs:__imp_GetLastError
0x18002e0f5  cmp     eax, 7Ah ; 'z'
0x18002e0f8  jnz     loc_18002E6CB
0x18002e0fe  mov     ecx, [rbp+110h+ReturnLength]; Size
0x18002e101  call    cs:__imp_malloc
0x18002e107  mov     rbx, rax
0x18002e10a  mov     [rbp+110h+var_188], rax
0x18002e10e  test    rax, rax
0x18002e111  jz      loc_18002E6F5
0x18002e117  lea     rax, [rbp+110h+ReturnLength]
0x18002e11b  mov     qword ptr [rsp+210h+dwDesiredAccess], rax; ReturnLength
0x18002e120  mov     r9d, [rbp+110h+ReturnLength]; TokenInformationLength
0x18002e124  mov     r8, rbx; TokenInformation
0x18002e127  lea     edx, [r12+1]; TokenInformationClass
0x18002e12c  mov     rcx, [rdi]; TokenHandle
0x18002e12f  call    cs:__imp_GetTokenInformation
0x18002e135  test    eax, eax
0x18002e137  jz      loc_18002E70F
0x18002e13d  mov     rdx, [rbx]; struct _SID *
0x18002e140  lea     rcx, [rbp+110h+var_180]; this
0x18002e144  call    ??0CSid@ATL@@QEAA@PEBU_SID@@PEBG@Z; ATL::CSid::CSid(_SID const *,ushort const *)
0x18002e149  nop
0x18002e14a  mov     rdx, rax
0x18002e14d  mov     rcx, r13
0x18002e150  call    ??4CSid@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSid::operator=(ATL::CSid const &)
0x18002e155  nop
0x18002e156  lea     rcx, [rbp+110h+var_180]; this
0x18002e15a  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x18002e15f  mov     qword ptr [rsp+210h+dwOptions], r12; hTemplateFile
0x18002e164  mov     [rsp+210h+bInheritHandle], 2000000h; dwFlagsAndAttributes
0x18002e16c  lea     r8d, [r12+3]; dwShareMode
0x18002e171  mov     [rsp+210h+dwDesiredAccess], r8d; dwCreationDisposition
0x18002e176  xor     r9d, r9d; lpSecurityAttributes
0x18002e179  lea     edx, [r12+1]; dwDesiredAccess
0x18002e17e  mov     rcx, r15; lpFileName
0x18002e181  call    cs:__imp_CreateFileW
0x18002e187  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e18b  jz      loc_18002E739
0x18002e191  mov     [r14+98h], rax
0x18002e198  xor     r9d, r9d; dwFlags
0x18002e19b  xor     r8d, r8d; cchFilePath
0x18002e19e  xor     edx, edx; lpszFilePath
0x18002e1a0  mov     rcx, rax; hFile
0x18002e1a3  call    cs:__imp_GetFinalPathNameByHandleW
0x18002e1a9  mov     edx, eax
0x18002e1ab  test    eax, eax
0x18002e1ad  jz      loc_18002E763
0x18002e1b3  xorps   xmm0, xmm0
0x18002e1b6  xor     eax, eax
0x18002e1b8  movups  xmmword ptr [rsp+210h+lpszFilePath], xmm0
0x18002e1bd  mov     [rsp+210h+var_1B8], rax
0x18002e1c2  lea     rcx, [rsp+210h+lpszFilePath]
0x18002e1c7  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18002e1cc  nop
0x18002e1cd  mov     rdx, [rsp+210h+lpszFilePath]; lpszFilePath
0x18002e1d2  mov     r8, [rsp+210h+lpszFilePath+8]
0x18002e1d7  sub     r8, rdx
0x18002e1da  sar     r8, 1; cchFilePath
0x18002e1dd  xor     r9d, r9d; dwFlags
0x18002e1e0  mov     rcx, [r14+98h]; hFile
0x18002e1e7  call    cs:__imp_GetFinalPathNameByHandleW
0x18002e1ed  mov     eax, eax
0x18002e1ef  test    rax, rax
0x18002e1f2  jz      loc_18002E78D
0x18002e1f8  mov     rdx, [rsp+210h+lpszFilePath]; pObjectName
0x18002e1fd  mov     rcx, [rsp+210h+lpszFilePath+8]
0x18002e202  sub     rcx, rdx
0x18002e205  sar     rcx, 1
0x18002e208  inc     rax
0x18002e20b  cmp     rax, rcx
0x18002e20e  ja      loc_18002E7B7
0x18002e214  lfence
0x18002e217  mov     rcx, [rdi]; ClientToken
0x18002e21a  call    ?VerifyUserHasWriteAccess@SecuredDirectory@StandardCollector@DiagnosticsHub@Microsoft@@SAJPEAXPEBG@Z; Microsoft::DiagnosticsHub::StandardCollector::SecuredDirectory::VerifyUserHasWriteAccess(void *,ushort const *)
0x18002e21f  test    eax, eax
0x18002e221  jnz     loc_18002E7D1
0x18002e227  lea     r8d, [r12+4]; MaxCount
0x18002e22c  lea     rdx, asc_180056FA0; "\\\\?\\"
0x18002e233  mov     rcx, [rsp+210h+lpszFilePath]; String1
0x18002e238  call    cs:__imp_wcsncmp
0x18002e23e  mov     r9, rsi
0x18002e241  mov     r8, [rsp+210h+lpszFilePath]
0x18002e246  mov     rcx, r14
0x18002e249  test    eax, eax
0x18002e24b  lea     rdx, aSS_0; "\\\\?\\%s\\%s\\"
0x18002e252  jnz     short loc_18002E25B
0x18002e254  lea     rdx, aSS; "%s\\%s\\"
0x18002e25b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18002e260  xorps   xmm0, xmm0
0x18002e263  xor     eax, eax
0x18002e265  movups  [rbp+110h+var_88], xmm0
0x18002e26c  movups  [rbp+110h+var_78], xmm0
0x18002e273  movups  [rbp+110h+var_68], xmm0
0x18002e27a  mov     [rbp+110h+var_58], rax
0x18002e281  mov     qword ptr [rbp+110h+var_88+8], r12
0x18002e288  mov     byte ptr [rbp+110h+var_78], r12b
0x18002e28f  mov     dword ptr [rbp+110h+var_78+4], 2
0x18002e299  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x18002e2a0  mov     qword ptr [rbp+110h+var_88], rax
0x18002e2a7  movdqu  [rbp+110h+var_78+8], xmm0
0x18002e2af  mov     qword ptr [rbp+110h+var_68+8], r12
0x18002e2b6  mov     dword ptr [rbp+110h+var_58], r12d
0x18002e2bd  mov     esi, 10000000h
0x18002e2c2  mov     r8d, esi; unsigned int
0x18002e2c5  lea     rdx, qword_180077070; struct ATL::CSid *
0x18002e2cc  lea     rcx, [rbp+110h+var_88]; this
0x18002e2d3  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x18002e2d8  test    al, al
0x18002e2da  jz      loc_18002E7EB
0x18002e2e0  xorps   xmm0, xmm0
0x18002e2e3  movups  xmmword ptr [rbp+110h+var_F8], xmm0
0x18002e2e7  lea     rdi, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x18002e2ee  mov     [rbp+110h+var_F8], rdi
0x18002e2f2  mov     [rbp+110h+var_F8+8], r12
0x18002e2f6  lea     rdx, [rbp+110h+var_88]; struct ATL::CDacl *
0x18002e2fd  lea     rcx, [rbp+110h+var_F8]; this
0x18002e301  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x18002e306  xorps   xmm0, xmm0
0x18002e309  movups  xmmword ptr [rbp+110h+SecurityAttributes.nLength], xmm0
0x18002e30d  movups  xmmword ptr [rbp+110h+SecurityAttributes.bInheritHandle], xmm0
0x18002e311  mov     [rbp+110h+var_D0], rdi
0x18002e315  mov     rax, r12
0x18002e318  mov     [rbp+110h+var_C8], rax
0x18002e31c  mov     rdx, [rbp+110h+var_F8+8]; struct _SECURITY_DESCRIPTOR *
0x18002e320  test    rdx, rdx
0x18002e323  jz      short loc_18002E332
0x18002e325  lea     rcx, [rbp+110h+var_D0]; this
0x18002e329  call    ?Init@CSecurityDesc@ATL@@IEAAXAEBU_SECURITY_DESCRIPTOR@@@Z; ATL::CSecurityDesc::Init(_SECURITY_DESCRIPTOR const &)
0x18002e32e  mov     rax, [rbp+110h+var_C8]
0x18002e332  mov     [rbp+110h+SecurityAttributes.nLength], 18h
0x18002e339  mov     [rbp+110h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002e33d  mov     [rbp+110h+SecurityAttributes.bInheritHandle], r12d
0x18002e341  mov     qword ptr [rsp+210h+dwOptions], r12; hTemplateFile
0x18002e346  mov     [rsp+210h+bInheritHandle], 3200010h; dwFlagsAndAttributes
0x18002e34e  mov     r15d, 1
0x18002e354  mov     [rsp+210h+dwDesiredAccess], r15d; dwCreationDisposition
0x18002e359  lea     r9, [rbp+110h+SecurityAttributes]; lpSecurityAttributes
0x18002e35d  mov     r8d, r15d; dwShareMode
0x18002e360  mov     edx, 0C0050001h; dwDesiredAccess
0x18002e365  mov     rcx, [r14]; lpFileName
0x18002e368  call    cs:__imp_CreateFileW
0x18002e36e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e372  jz      loc_18002E815
0x18002e378  mov     [r14+0A0h], rax
0x18002e37f  xor     r9d, r9d; dwFlags
0x18002e382  xor     r8d, r8d; cchFilePath
0x18002e385  xor     edx, edx; lpszFilePath
0x18002e387  mov     rcx, rax; hFile
0x18002e38a  call    cs:__imp_GetFinalPathNameByHandleW
0x18002e390  mov     edx, eax
0x18002e392  test    eax, eax
0x18002e394  jz      loc_18002E83F
0x18002e39a  xorps   xmm0, xmm0
0x18002e39d  xor     eax, eax
0x18002e39f  movups  xmmword ptr [rsp+210h+String1], xmm0
0x18002e3a4  mov     [rsp+210h+var_198], rax
0x18002e3a9  lea     rcx, [rsp+210h+String1]
0x18002e3ae  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18002e3b3  nop
0x18002e3b4  mov     rdx, [rsp+210h+String1]; lpszFilePath
0x18002e3b9  mov     r8, [rsp+210h+String1+8]
0x18002e3be  sub     r8, rdx
0x18002e3c1  sar     r8, 1; cchFilePath
0x18002e3c4  xor     r9d, r9d; dwFlags
0x18002e3c7  mov     rcx, [r14+0A0h]; hFile
0x18002e3ce  call    cs:__imp_GetFinalPathNameByHandleW
0x18002e3d4  test    eax, eax
0x18002e3d6  jz      loc_18002E869
0x18002e3dc  mov     r8, [rsp+210h+String1]
0x18002e3e1  mov     rcx, [rsp+210h+String1+8]
0x18002e3e6  sub     rcx, r8
0x18002e3e9  sar     rcx, 1
0x18002e3ec  mov     rax, [rsp+210h+lpszFilePath+8]
0x18002e3f1  sub     rax, [rsp+210h+lpszFilePath]
0x18002e3f6  sar     rax, 1
0x18002e3f9  cmp     rax, rcx
0x18002e3fc  jnb     loc_18002E893
0x18002e402  lfence
0x18002e405  mov     rdx, [r14]; wchar_t *
0x18002e408  mov     rcx, r8; String1
0x18002e40b  call    _anonymous_namespace___ValidateSamePath_0
0x18002e410  test    eax, eax
0x18002e412  jnz     loc_18002E8AD
0x18002e418  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x18002e41d  mov     rcx, rax
0x18002e420  test    rax, rax
0x18002e423  jz      loc_18002E8C7
0x18002e429  mov     rax, [rax]
0x18002e42c  mov     rax, [rax+18h]
0x18002e430  call    cs:__guard_dispatch_icall_fptr
0x18002e436  add     rax, 18h
0x18002e43a  mov     [rsp+210h+lpFileName], rax
0x18002e43f  mov     r8, [r14]
0x18002e442  lea     rdx, aSlock; "%slock"
0x18002e449  lea     rcx, [rsp+210h+lpFileName]
0x18002e44e  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18002e453  mov     qword ptr [rsp+210h+dwOptions], r12; hTemplateFile
0x18002e458  mov     [rsp+210h+bInheritHandle], 4000002h; dwFlagsAndAttributes
0x18002e460  mov     [rsp+210h+dwDesiredAccess], r15d; dwCreationDisposition
0x18002e465  xor     r9d, r9d; lpSecurityAttributes
0x18002e468  xor     r8d, r8d; dwShareMode
0x18002e46b  mov     edx, 0C0000000h; dwDesiredAccess
0x18002e470  mov     rdi, [rsp+210h+lpFileName]
0x18002e475  mov     rcx, rdi; lpFileName
0x18002e478  call    cs:__imp_CreateFileW
0x18002e47e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e482  jz      loc_18002E8D2
0x18002e488  mov     [r14+90h], rax
0x18002e48f  xorps   xmm0, xmm0
0x18002e492  xor     eax, eax
0x18002e494  movups  [rbp+110h+var_C0], xmm0
0x18002e498  movups  [rbp+110h+var_B0], xmm0
0x18002e49c  movups  [rbp+110h+var_A0], xmm0
0x18002e4a0  mov     [rbp+110h+var_90], rax
0x18002e4a7  mov     qword ptr [rbp+110h+var_C0+8], r12
0x18002e4ab  mov     byte ptr [rbp+110h+var_B0], r12b
0x18002e4af  lea     ecx, [rax+2]
0x18002e4b2  mov     dword ptr [rbp+110h+var_B0+4], ecx
0x18002e4b5  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x18002e4bc  mov     qword ptr [rbp+110h+var_C0], rax
0x18002e4c0  movdqu  [rbp+110h+var_B0+8], xmm0
0x18002e4c5  mov     qword ptr [rbp+110h+var_A0+8], r12
0x18002e4c9  mov     dword ptr [rbp+110h+var_90], r12d
0x18002e4d0  mov     [rsp+210h+dwDesiredAccess], 220h
0x18002e4d8  lea     r9d, [r15+1Fh]
0x18002e4dc  mov     r8d, ecx; unsigned __int8
0x18002e4df  lea     rdx, ?SecurityNTAuthority@Sids@ATL@@3U_SID_IDENTIFIER_AUTHORITY@@B; struct _SID_IDENTIFIER_AUTHORITY *
0x18002e4e6  lea     rcx, [rbp+110h+var_180]; this
0x18002e4ea  call    ??0CSid@ATL@@QEAA@AEBU_SID_IDENTIFIER_AUTHORITY@@EZZ; ATL::CSid::CSid(_SID_IDENTIFIER_AUTHORITY const &,uchar,...)
0x18002e4ef  nop
  ... truncated ...
```
