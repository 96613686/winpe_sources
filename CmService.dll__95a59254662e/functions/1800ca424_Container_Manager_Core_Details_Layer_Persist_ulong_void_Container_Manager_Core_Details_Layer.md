# Container::Manager::Core::Details::Layer::Persist(ulong,void *,Container::Manager::Core::Details::Layer *)

- ea: `0x1800ca424`
- end: `0x1800cb3e8`
- name: `?Persist@Layer@Details@Core@Manager@Container@@QEAAJKPEAXPEAV12345@@Z`
- size: `4036`
- prototype: `__int64 __fastcall(struct _GUID *this, unsigned int, void *, struct Container::Manager::Core::Details::Layer *)`
- caller_count: `2`
- callee_count: `29`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180044f34`
- `0x18006a0a8`

## callees

- `0x180004fc4`
- `0x180005704`
- `0x1800067cc`
- `0x180008bf0`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x180016774`
- `0x18002c390`
- `0x18002dc0c`
- `0x18002fae4`
- `0x18002fc34`
- `0x18002fd88`
- `0x1800300a8`
- `0x180030200`
- `0x180031c14`
- `0x180080034`
- `0x180080264`
- `0x1800c6c38`
- `0x1800ca424`
- `0x1800cc4ec`
- `0x1800cc648`
- `0x1800cc8e8`
- `0x1800cd24c`
- `0x180108354`
- `0x18018307c`
- `0x180197608`
- `0x180198658`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x1800cb063`
- `ntdll!RtlDoesFileExists_U` at `0x1800cb063`
- `ntdll!RtlAcquirePrivilege` at `0x1800ca4e0`
- `ntdll!RtlAcquirePrivilege` at `0x1800ca4e0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cb26b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cb26b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb2b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb387`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb2b4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cb387`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cb277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cb277`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800caf86`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1800caf86`

## string_xrefs

- `0x1800ca4f7`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`
- `0x1800cadc4`: `Program Files (x86)\Microsoft\EdgeUpdate`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::Layer::Persist(
        struct _GUID *this,
        unsigned int a2,
        void *a3,
        struct Container::Manager::Core::Details::Layer *a4)
{
  int ResourcePath; // eax
  int LastError; // ebx
  void *v9; // rcx
  NTSTATUS v11; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  WCHAR *v16; // rax
  __m128i si128; // xmm6
  int v18; // eax
  bool *v19; // r8
  WCHAR *v20; // rcx
  WCHAR *v21; // rax
  Csl *v22; // rbx
  int IsWcifsReparsePoint; // eax
  unsigned int v24; // r15d
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  struct Path *v28; // rdx
  int SystemDrivePath; // eax
  void *v30; // rbx
  void *v31; // rbx
  WCHAR *v32; // rcx
  WCHAR *v33; // rax
  int v34; // edi
  __int64 v35; // rdx
  void *v36; // rbx
  __int16 *v37; // rcx
  __int16 *v38; // rax
  void *v39; // rbx
  __int64 v40; // rdx
  struct _SECURITY_ATTRIBUTES *v41; // r8
  int DirectoryRecursive; // eax
  __int64 v43; // rdx
  struct _SECURITY_ATTRIBUTES *v44; // r8
  int v45; // eax
  WCHAR *v46; // rcx
  WCHAR *v47; // rax
  int v48; // eax
  int v49; // eax
  const char *v50; // r9
  const wchar_t **v51; // rbx
  const wchar_t **v52; // rdi
  __int64 v53; // rcx
  unsigned __int64 v54; // r12
  const struct Path *v55; // rax
  const struct Path *v56; // r15
  unsigned int v57; // r9d
  int v58; // eax
  const struct std::nothrow_t *v59; // rdx
  unsigned int v60; // r12d
  int v61; // eax
  const struct std::nothrow_t *v62; // rdx
  __int64 v63; // rdx
  int OsVersionInfoString; // eax
  __int64 v65; // rdx
  int v66; // eax
  PVOID ReturnedState; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v68; // [rsp+30h] [rbp-D8h] BYREF
  void *v69; // [rsp+38h] [rbp-D0h] BYREF
  char *v70; // [rsp+40h] [rbp-C8h]
  __int16 v71; // [rsp+48h] [rbp-C0h] BYREF
  void *v72[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int16 v73; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v74[4]; // [rsp+70h] [rbp-98h] BYREF
  const wchar_t *v75; // [rsp+90h] [rbp-78h]
  __int64 v76; // [rsp+98h] [rbp-70h]
  _QWORD v77[2]; // [rsp+A0h] [rbp-68h] BYREF
  _WORD v78[8]; // [rsp+B0h] [rbp-58h] BYREF
  PCWSTR FileName[2]; // [rsp+C0h] [rbp-48h] BYREF
  _WORD v80[8]; // [rsp+D0h] [rbp-38h] BYREF
  void *v81[2]; // [rsp+E0h] [rbp-28h] BYREF
  _WORD v82[8]; // [rsp+F0h] [rbp-18h] BYREF
  void *v83; // [rsp+100h] [rbp-8h] BYREF
  char *v84; // [rsp+108h] [rbp+0h]
  _WORD v85[8]; // [rsp+110h] [rbp+8h] BYREF
  Csl *v86[2]; // [rsp+120h] [rbp+18h] BYREF
  __int64 v87; // [rsp+130h] [rbp+28h]
  ULONG Privilege[2]; // [rsp+138h] [rbp+30h] BYREF
  __int64 v89; // [rsp+140h] [rbp+38h]
  void *v90[2]; // [rsp+148h] [rbp+40h] BYREF
  _WORD v91[8]; // [rsp+158h] [rbp+50h] BYREF
  void *v92[2]; // [rsp+168h] [rbp+60h] BYREF
  _WORD v93[8]; // [rsp+178h] [rbp+70h] BYREF
  LPCWSTR lpExistingFileName[2]; // [rsp+188h] [rbp+80h] BYREF
  _WORD v95[8]; // [rsp+198h] [rbp+90h] BYREF
  void *v96[2]; // [rsp+1A8h] [rbp+A0h] BYREF
  _WORD v97[8]; // [rsp+1B8h] [rbp+B0h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+1C8h] [rbp+C0h] BYREF
  _WORD v99[8]; // [rsp+1D8h] [rbp+D0h] BYREF
  void *v100[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  __int16 v101; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v102; // [rsp+1FAh] [rbp+F2h]
  int v103; // [rsp+202h] [rbp+FAh]
  __int16 v104; // [rsp+206h] [rbp+FEh]
  __m128i v105; // [rsp+208h] [rbp+100h] BYREF
  __int64 v106; // [rsp+218h] [rbp+110h]
  void *v107[2]; // [rsp+220h] [rbp+118h] BYREF
  __int128 v108; // [rsp+230h] [rbp+128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A0h] [rbp+198h]

  v69 = &v71;
  v71 = 0;
  v70 = (char *)&v71;
  ResourcePath = Container::Manager::Core::Details::Layer::GetResourcePath(this, 0, &v69);
  LastError = ResourcePath;
  if ( ResourcePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x993,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)ResourcePath,
      (int)ReturnedState);
    goto LABEL_3;
  }
  ReturnedState = 0;
  Privilege[0] = 17;
  Privilege[1] = 18;
  v11 = RtlAcquirePrivilege(Privilege, 2u, 0, &ReturnedState);
  if ( v11 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x52,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
                  (const char *)(unsigned int)v11,
                  (int)ReturnedState);
    if ( LastError < 0 )
    {
      v12 = 2457;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)LastError,
        (int)ReturnedState);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
LABEL_3:
      v9 = v69;
      if ( v69 == &v71 )
        return (unsigned int)LastError;
LABEL_4:
      operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)LastError;
    }
  }
  LastError = Container::Manager::Core::Details::Layer::UnmountFileSystemIfNeeded((Container::Manager::Core::Details::Layer *)this);
  if ( LastError < 0 )
  {
    v12 = 2462;
    goto LABEL_9;
  }
  v13 = *(_DWORD *)&this[3].Data2;
  if ( v13 != 5 && v13 )
  {
    if ( (this[14].Data2 & 4) != 0 )
    {
      v95[0] = 0;
      lpExistingFileName[0] = v95;
      lpExistingFileName[1] = v95;
      v48 = Container::Manager::Core::Details::Layer::GetResourcePath(a4, 4, lpExistingFileName);
      LastError = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA03,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v48,
          (int)ReturnedState);
        v20 = (WCHAR *)lpExistingFileName[0];
        v21 = v95;
        goto LABEL_23;
      }
      v99[0] = 0;
      lpNewFileName[0] = v99;
      lpNewFileName[1] = v99;
      v49 = Container::Manager::Core::Details::Layer::GetResourcePath(this, 4, lpNewFileName);
      LastError = v49;
      if ( v49 >= 0 )
      {
        if ( CopyFileW(lpExistingFileName[0], lpNewFileName[0], 1) )
        {
          if ( lpNewFileName[0] != v99 )
            operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
          v46 = (WCHAR *)lpExistingFileName[0];
          v47 = v95;
LABEL_128:
          if ( v46 != v47 )
            operator delete(v46, (const struct std::nothrow_t *)&std::nothrow);
          goto LABEL_130;
        }
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xA0C,
                      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
                      v50);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA08,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v49,
          (int)ReturnedState);
      }
      if ( lpNewFileName[0] != v99 )
        operator delete((void *)lpNewFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      v20 = (WCHAR *)lpExistingFileName[0];
      v21 = v95;
LABEL_23:
      if ( v20 != v21 )
        operator delete(v20, (const struct std::nothrow_t *)&std::nothrow);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      v9 = v69;
      if ( v69 == &v71 )
        return (unsigned int)LastError;
      goto LABEL_4;
    }
LABEL_130:
    v51 = *(const wchar_t ***)this[12].Data4;
    v52 = *(const wchar_t ***)&this[13].Data1;
    while ( v51 != v52 )
    {
      FileName[0] = v80;
      FileName[1] = v80;
      v80[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               FileName,
                               v69,
                               (v70 - (_BYTE *)v69) >> 1) )
      {
        v63 = 2589;
        goto LABEL_153;
      }
      v53 = (char *)v51[1] - (char *)*v51;
      v75 = *v51;
      v76 = v53 >> 1;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)FileName) )
      {
        v63 = 2590;
        goto LABEL_153;
      }
      if ( RtlDoesFileExists_U(FileName[0]) )
      {
        v54 = 2 * (v51[1] - *v51) + 52;
        v55 = (const struct Path *)operator new[](v54, (const struct std::nothrow_t *)&std::nothrow);
        v56 = v55;
        if ( !v55 )
        {
          v63 = 2601;
LABEL_153:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v63,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
            (const char *)0x8007000ELL,
            (int)ReturnedState);
          v15 = (WCHAR *)FileName[0];
          v16 = v80;
          goto LABEL_154;
        }
        memset_0(v55, 0, v54);
        v58 = Csl::DeleteReparsePoint((Csl *)FileName, v56, (unsigned __int8 *)(unsigned int)v54, v57);
        v60 = v58;
        if ( v58 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA2D,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
            (const char *)(unsigned int)v58,
            (int)ReturnedState);
          operator delete(v56, v62);
          if ( FileName[0] != v80 )
            operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
          Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
          if ( v69 != &v71 )
            operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
          return v60;
        }
        operator delete(v56, v59);
      }
      if ( *(_QWORD *)this[3].Data4 != *(_QWORD *)&GUID_NULL.Data1
        || *(_QWORD *)&this[4].Data1 != *(_QWORD *)GUID_NULL.Data4 )
      {
        v61 = Container::Manager::Storage::CreateOrSetDirectoryReparsePoint(&v69, v51, this[3].Data4, 0);
        v24 = v61;
        if ( v61 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA41,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
            (const char *)(unsigned int)v61,
            (int)ReturnedState);
          v32 = (WCHAR *)FileName[0];
          v33 = v80;
          goto LABEL_67;
        }
      }
      if ( FileName[0] != v80 )
        operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
      v51 += 4;
    }
    v82[0] = 0;
    v81[0] = v82;
    v81[1] = v82;
    OsVersionInfoString = Csl::GetOsVersionInfoString(v81);
    LastError = OsVersionInfoString;
    if ( OsVersionInfoString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)OsVersionInfoString,
        (int)ReturnedState);
      v20 = (WCHAR *)v81[0];
      v21 = v82;
      goto LABEL_23;
    }
    AcquireSRWLockExclusive((PSRWLOCK)&this[17]);
    *(_DWORD *)this[17].Data4 = GetCurrentThreadId();
    if ( this[7].Data1 == 1 )
    {
      v34 = Container::Manager::Core::Details::Layer::SetStateLocked(this, 2, a3);
      if ( v34 >= 0 )
      {
        v34 = Container::Manager::Core::Details::LayerStore::SetOSVersion(*(_QWORD *)&this[16].Data1, this, v81, a3);
        if ( v34 >= 0 )
        {
          utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
            &this[5],
            v81);
          v66 = Container::Manager::Core::Details::LayerStore::SetSequenceNumber(
                  *(Container::Manager::Core::Details::LayerStore **)&this[16].Data1,
                  this,
                  a2,
                  a3);
          v34 = v66;
          if ( v66 >= 0 )
          {
            *(_DWORD *)&this[7].Data2 = a2;
            *(_DWORD *)this[17].Data4 = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)&this[17]);
            if ( v81[0] != v82 )
              operator delete(v81[0], (const struct std::nothrow_t *)&std::nothrow);
            Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
            if ( v69 != &v71 )
              operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
            return 0;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA5E,
            (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
            (const char *)(unsigned int)v66,
            (int)ReturnedState);
          *(_DWORD *)this[17].Data4 = 0;
          goto LABEL_164;
        }
        v65 = 2651;
      }
      else
      {
        v65 = 2648;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v65,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
        (const char *)(unsigned int)v34,
        (int)ReturnedState);
    }
    else
    {
      v34 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xA55,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
              (const char *)0x139F,
              (unsigned int)ReturnedState);
    }
    *(_DWORD *)this[17].Data4 = 0;
LABEL_164:
    ReleaseSRWLockExclusive((PSRWLOCK)&this[17]);
    v37 = (__int16 *)v81[0];
    v38 = v82;
LABEL_79:
    if ( v37 != v38 )
      operator delete(v37, (const struct std::nothrow_t *)&std::nothrow);
    Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
    if ( v69 != &v71 )
      operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v34;
  }
  if ( this[12].Data1 != 1 )
    goto LABEL_130;
  if ( (this[14].Data2 & 4) == 0 )
  {
LABEL_92:
    if ( (this[14].Data2 & 8) != 0 )
    {
      v77[0] = v78;
      v77[1] = v78;
      v78[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v77,
                               v69,
                               (v70 - (_BYTE *)v69) >> 1) )
      {
        v40 = 2542;
LABEL_95:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)0x8007000ELL,
          (int)ReturnedState);
LABEL_96:
        v15 = (WCHAR *)v77[0];
        v16 = v78;
        goto LABEL_154;
      }
      v76 = 34;
      v75 = L"Program Files (x86)\\Microsoft\\Edge";
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v77) )
      {
        v40 = 2543;
        goto LABEL_95;
      }
      DirectoryRecursive = Csl::CreateDirectoryRecursive((Csl *)v77, 0, v41);
      LastError = DirectoryRecursive;
      if ( DirectoryRecursive < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9F1,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)DirectoryRecursive,
          (int)ReturnedState);
LABEL_101:
        v20 = (WCHAR *)v77[0];
        v21 = v78;
        goto LABEL_23;
      }
      v92[0] = v93;
      v92[1] = v93;
      v93[0] = 0;
      if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                               v92,
                               v69,
                               (v70 - (_BYTE *)v69) >> 1) )
      {
        v43 = 2548;
        goto LABEL_104;
      }
      v76 = 40;
      v75 = L"Program Files (x86)\\Microsoft\\EdgeUpdate";
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v92) )
      {
        v43 = 2549;
LABEL_104:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)0x8007000ELL,
          (int)ReturnedState);
        if ( v92[0] != v93 )
          operator delete(v92[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_96;
      }
      v45 = Csl::CreateDirectoryRecursive((Csl *)v92, 0, v44);
      LastError = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9F7,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v45,
          (int)ReturnedState);
        if ( v92[0] != v93 )
          operator delete(v92[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_101;
      }
      if ( v92[0] != v93 )
        operator delete(v92[0], (const struct std::nothrow_t *)&std::nothrow);
      v46 = (WCHAR *)v77[0];
      v47 = v78;
      goto LABEL_128;
    }
    goto LABEL_130;
  }
  v72[0] = &v73;
  v72[1] = &v73;
  v73 = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v72,
                           v69,
                           (v70 - (_BYTE *)v69) >> 1) )
  {
    v14 = 2488;
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)0x8007000ELL,
      (int)ReturnedState);
    v15 = (WCHAR *)v72[0];
    v16 = (WCHAR *)&v73;
    goto LABEL_154;
  }
  v89 = 21;
  *(_QWORD *)Privilege = L"Windows\\Microsoft.NET";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v72) )
  {
    v14 = 2489;
    goto LABEL_18;
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v87 = -1;
  *(__m128i *)v86 = si128;
  v18 = Csl::EnumerateDirectory(v72, 13, v86, L"*");
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9C3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
      (const char *)(unsigned int)v18,
      (int)ReturnedState);
    utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(v86);
    v20 = (WCHAR *)v72[0];
    v21 = (WCHAR *)&v73;
    goto LABEL_23;
  }
  v22 = v86[0];
  *(__m128i *)&v74[1] = si128;
  v74[3] = -1;
  while ( 1 )
  {
    if ( v22 == v86[1] )
    {
      v97[0] = 0;
      v96[0] = v97;
      v96[1] = v97;
      v34 = Container::Manager::Core::Details::Layer::GetResourcePath(this, 4, v96);
      if ( v34 < 0 )
      {
        v35 = 2531;
LABEL_74:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v35,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)v34,
          (int)ReturnedState);
        if ( v96[0] != v97 )
          operator delete(v96[0], (const struct std::nothrow_t *)&std::nothrow);
        v36 = (void *)v74[1];
        if ( v74[1] != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<Container::Manager::Core::Details::BindMapping>>(
            v74[2] - v74[1],
            v74[1],
            (v74[2] - v74[1]) / 88LL);
          operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
        }
        utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(v86);
        v37 = (__int16 *)v72[0];
        v38 = &v73;
        goto LABEL_79;
      }
      v34 = Container::Manager::Core::Details::BindingStore::BatchBindMappingsToFile(&v74[1], v96);
      if ( v34 < 0 )
      {
        v35 = 2534;
        goto LABEL_74;
      }
      if ( v96[0] != v97 )
        operator delete(v96[0], (const struct std::nothrow_t *)&std::nothrow);
      v39 = (void *)v74[1];
      if ( v74[1] != -1 )
      {
        utl::_RangeDestroyApc<utl::allocator<Container::Manager::Core::Details::BindMapping>>(
          v74[2] - v74[1],
          v74[1],
          (v74[2] - v74[1]) / 88LL);
        operator delete(v39, (const struct std::nothrow_t *)&std::nothrow);
      }
      utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(v86);
      if ( v72[0] != &v73 )
        operator delete(v72[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_92;
    }
    LOBYTE(v68) = 0;
    IsWcifsReparsePoint = Csl::IsWcifsReparsePoint(v22, (const struct Path *)&v68, v19);
    v24 = IsWcifsReparsePoint;
    if ( IsWcifsReparsePoint < 0 )
      break;
    if ( (_BYTE)v68 )
    {
      v25 = *(_QWORD *)v22;
      v85[0] = 0;
      v26 = v25 + 2 * (((v70 - (_BYTE *)v69) >> 1) + 1);
      *(_QWORD *)Privilege = v26;
      v83 = v85;
      v84 = (char *)v85;
      v27 = -1;
      do
        ++v27;
      while ( *(_WORD *)(v26 + 2 * v27) );
      v89 = v27;
      if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)&v83) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)0x8007000ELL,
          (int)ReturnedState);
        goto LABEL_52;
      }
      v91[0] = 0;
      v90[0] = v91;
      v90[1] = v91;
      SystemDrivePath = Csl::GetSystemDrivePath((Csl *)v90, v28);
      v24 = SystemDrivePath;
      if ( SystemDrivePath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9D4,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)(unsigned int)SystemDrivePath,
          (int)ReturnedState);
        if ( v90[0] != v91 )
          operator delete(v90[0], (const struct std::nothrow_t *)&std::nothrow);
        if ( v83 != v85 )
          operator delete(v83, (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_64;
      }
      v75 = (const wchar_t *)v83;
      v76 = (v84 - (_BYTE *)v83) >> 1;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v90) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9D5,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)0x8007000ELL,
          (int)ReturnedState);
LABEL_50:
        if ( v90[0] != v91 )
          operator delete(v90[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_52:
        if ( v83 != v85 )
          operator delete(v83, (const struct std::nothrow_t *)&std::nothrow);
        v30 = (void *)v74[1];
        if ( v74[1] != -1 )
        {
          utl::_RangeDestroyApc<utl::allocator<Container::Manager::Core::Details::BindMapping>>(
            v74[2] - v74[1],
            v74[1],
            (v74[2] - v74[1]) / 88LL);
          operator delete(v30, (const struct std::nothrow_t *)&std::nothrow);
        }
        utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(v86);
        v15 = (WCHAR *)v72[0];
        v16 = (WCHAR *)&v73;
LABEL_154:
        if ( v15 != v16 )
          operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
        Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
        if ( v69 != &v71 )
          operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
        return 2147942414LL;
      }
      v102 = 0;
      v103 = 0;
      v100[0] = &v101;
      v104 = 0;
      v100[1] = &v101;
      v101 = 0;
      v107[0] = &v108;
      v108 = 0;
      v107[1] = &v108;
      v105 = si128;
      v106 = -1;
      LOWORD(v108) = 0;
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        v107,
        v90);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
        v100,
        &v83);
      if ( !(unsigned __int8)utl::vector<Container::Manager::Core::Details::BindMapping,utl::allocator<Container::Manager::Core::Details::BindMapping>>::emplace_back<Container::Manager::Core::Details::BindMapping,0>(
                               &v74[1],
                               v100) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9DB,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
          (const char *)0x8007000ELL,
          (int)ReturnedState);
        if ( v107[0] != &v108 )
          operator delete(v107[0], (const struct std::nothrow_t *)&std::nothrow);
        utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v105);
        if ( v100[0] != &v101 )
          operator delete(v100[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_50;
      }
      if ( v107[0] != &v108 )
        operator delete(v107[0], (const struct std::nothrow_t *)&std::nothrow);
      utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v105);
      if ( v100[0] != &v101 )
        operator delete(v100[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v90[0] != v91 )
        operator delete(v90[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v83 != v85 )
        operator delete(v83, (const struct std::nothrow_t *)&std::nothrow);
    }
    v22 = (Csl *)((char *)v22 + 32);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9CA,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\layermanager.cpp",
    (const char *)(unsigned int)IsWcifsReparsePoint,
    (int)ReturnedState);
LABEL_64:
  v31 = (void *)v74[1];
  if ( v74[1] != -1 )
  {
    utl::_RangeDestroyApc<utl::allocator<Container::Manager::Core::Details::BindMapping>>(
      v74[2] - v74[1],
      v74[1],
      (v74[2] - v74[1]) / 88LL);
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  }
  utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(v86);
  v32 = (WCHAR *)v72[0];
  v33 = (WCHAR *)&v73;
LABEL_67:
  if ( v32 != v33 )
    operator delete(v32, (const struct std::nothrow_t *)&std::nothrow);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  if ( v69 != &v71 )
    operator delete(v69, (const struct std::nothrow_t *)&std::nothrow);
  return v24;
}

```

## disassembly

```asm
0x1800ca424  mov     rax, rsp
0x1800ca427  mov     [rax+10h], edx
0x1800ca42a  push    rbp
0x1800ca42b  push    rbx
0x1800ca42c  push    rsi
0x1800ca42d  push    rdi
0x1800ca42e  push    r12
0x1800ca430  push    r13
0x1800ca432  push    r14
0x1800ca434  push    r15
0x1800ca436  lea     rbp, [rax-198h]
0x1800ca43d  sub     rsp, 258h
0x1800ca444  movaps  xmmword ptr [rax-58h], xmm6
0x1800ca448  mov     r13, r8
0x1800ca44b  lea     rax, [rsp+290h+var_250]
0x1800ca450  xor     r12d, r12d
0x1800ca453  mov     [rsp+290h+var_260], rax
0x1800ca458  lea     r8, [rsp+290h+var_260]
0x1800ca45d  lea     rax, [rsp+290h+var_250]
0x1800ca462  mov     [rsp+290h+var_250], r12w
0x1800ca468  xor     edx, edx
0x1800ca46a  mov     [rsp+290h+var_258], rax
0x1800ca46f  mov     r15, r9
0x1800ca472  mov     r14, rcx
0x1800ca475  call    ?GetResourcePath@Layer@Details@Core@Manager@Container@@QEBAJW4LayerResource@2345@AEAVPath@Csl@@@Z; Container::Manager::Core::Details::Layer::GetResourcePath(Container::Manager::Core::Details::LayerResource,Csl::Path &)
0x1800ca47a  mov     ebx, eax
0x1800ca47c  test    eax, eax
0x1800ca47e  jns     short loc_1800CA4BD
0x1800ca480  mov     rcx, [rbp+198h]; this
0x1800ca487  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ca48e  mov     r9d, eax; char *
0x1800ca491  mov     edx, 993h; void *
0x1800ca496  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca49b  mov     rcx, [rsp+290h+var_260]; void *
0x1800ca4a0  lea     rax, [rsp+290h+var_250]
0x1800ca4a5  cmp     rcx, rax
0x1800ca4a8  jz      short loc_1800CA4B6
0x1800ca4aa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800ca4b1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca4b6  mov     eax, ebx
0x1800ca4b8  jmp     loc_1800CB3CB
0x1800ca4bd  xor     r8d, r8d; Flags
0x1800ca4c0  mov     [rsp+290h+ReturnedState], r12; int
0x1800ca4c5  lea     r9, [rsp+290h+ReturnedState]; ReturnedState
0x1800ca4ca  mov     [rbp+190h+Privilege], 11h
0x1800ca4d1  lea     rcx, [rbp+190h+Privilege]; Privilege
0x1800ca4d5  mov     [rbp+190h+Privilege+4], 12h
0x1800ca4dc  lea     edx, [r8+2]; NumPriv
0x1800ca4e0  call    cs:__imp_RtlAcquirePrivilege
0x1800ca4e7  nop     dword ptr [rax+rax+00h]
0x1800ca4ec  test    eax, eax
0x1800ca4ee  jns     short loc_1800CA53B
0x1800ca4f0  mov     rcx, [rbp+198h]; this
0x1800ca4f7  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800ca4fe  mov     r9d, eax; char *
0x1800ca501  mov     edx, 52h ; 'R'; void *
0x1800ca506  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800ca50b  mov     ebx, eax
0x1800ca50d  test    eax, eax
0x1800ca50f  jns     short loc_1800CA53B
0x1800ca511  mov     edx, 999h; void *
0x1800ca516  mov     rcx, [rbp+198h]; this
0x1800ca51d  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ca524  mov     r9d, ebx; char *
0x1800ca527  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca52c  lea     rcx, [rsp+290h+ReturnedState]; this
0x1800ca531  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1800ca536  jmp     loc_1800CA49B
0x1800ca53b  mov     rcx, r14; this
0x1800ca53e  call    ?UnmountFileSystemIfNeeded@Layer@Details@Core@Manager@Container@@AEAAJXZ; Container::Manager::Core::Details::Layer::UnmountFileSystemIfNeeded(void)
0x1800ca543  mov     ebx, eax
0x1800ca545  test    eax, eax
0x1800ca547  jns     short loc_1800CA550
0x1800ca549  mov     edx, 99Eh
0x1800ca54e  jmp     short loc_1800CA516
0x1800ca550  mov     eax, [r14+34h]
0x1800ca554  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800ca55b  cmp     eax, 5
0x1800ca55e  jz      short loc_1800CA568
0x1800ca560  test    eax, eax
0x1800ca562  jnz     loc_1800CAE6C
0x1800ca568  cmp     dword ptr [r14+0C0h], 1
0x1800ca570  jnz     loc_1800CAE5B
0x1800ca576  mov     edi, 4
0x1800ca57b  test    [r14+0E4h], dil
0x1800ca582  jz      loc_1800CAC87
0x1800ca588  mov     rdx, [rsp+290h+var_260]
0x1800ca58d  lea     rax, [rsp+290h+var_230]
0x1800ca592  mov     r8, [rsp+290h+var_258]
0x1800ca597  lea     rcx, [rsp+290h+var_240]
0x1800ca59c  mov     [rsp+290h+var_240], rax
0x1800ca5a1  sub     r8, rdx
0x1800ca5a4  lea     rax, [rsp+290h+var_230]
0x1800ca5a9  sar     r8, 1
0x1800ca5ac  mov     qword ptr [rsp+290h+var_238], rax
0x1800ca5b1  mov     [rsp+290h+var_230], r12w
0x1800ca5b7  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800ca5bc  test    al, al
0x1800ca5be  jnz     short loc_1800CA5F4
0x1800ca5c0  mov     edx, 9B8h; void *
0x1800ca5c5  mov     rcx, [rbp+198h]; this
0x1800ca5cc  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ca5d3  mov     r9d, 8007000Eh; char *
0x1800ca5d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca5de  mov     rcx, [rsp+290h+var_240]
0x1800ca5e3  lea     rax, [rsp+290h+var_230]
0x1800ca5e8  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800ca5ef  jmp     loc_1800CB1DD
0x1800ca5f4  lea     rax, aWindowsMicroso; "Windows\\Microsoft.NET"
0x1800ca5fb  mov     [rbp+190h+var_158], 15h
0x1800ca603  lea     rdx, [rbp+190h+Privilege]
0x1800ca607  mov     qword ptr [rbp+190h+Privilege], rax
0x1800ca60b  lea     rcx, [rsp+290h+var_240]; this
0x1800ca610  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800ca615  test    al, al
0x1800ca617  jnz     short loc_1800CA620
0x1800ca619  mov     edx, 9B9h
0x1800ca61e  jmp     short loc_1800CA5C5
0x1800ca620  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800ca628  lea     r9, asc_1801D1840; "*"
0x1800ca62f  lea     r8, [rbp+190h+var_178]
0x1800ca633  mov     [rbp+190h+var_168], 0FFFFFFFFFFFFFFFFh
0x1800ca63b  mov     edx, 0Dh
0x1800ca640  lea     rcx, [rsp+290h+var_240]
0x1800ca645  movdqu  xmmword ptr [rbp+190h+var_178], xmm6
0x1800ca64a  call    ?EnumerateDirectory@Csl@@YAJAEBVPath@1@W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectory(Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x1800ca64f  mov     ebx, eax
0x1800ca651  test    eax, eax
0x1800ca653  jns     short loc_1800CA6BC
0x1800ca655  mov     rcx, [rbp+198h]; this
0x1800ca65c  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ca663  mov     r9d, eax; char *
0x1800ca666  mov     edx, 9C3h; void *
0x1800ca66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca670  lea     rcx, [rbp+190h+var_178]
0x1800ca674  call    ?_Uninit@?$vector@UOverlayDirectory@Details@Core@Manager@Container@@V?$allocator@UOverlayDirectory@Details@Core@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(void)
0x1800ca679  mov     rcx, [rsp+290h+var_240]; void *
0x1800ca67e  lea     rax, [rsp+290h+var_230]
0x1800ca683  lea     rsi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1800ca68a  cmp     rcx, rax
0x1800ca68d  jz      short loc_1800CA697
0x1800ca68f  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca692  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca697  lea     rcx, [rsp+290h+ReturnedState]; this
0x1800ca69c  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1800ca6a1  mov     rcx, [rsp+290h+var_260]
0x1800ca6a6  lea     rax, [rsp+290h+var_250]
0x1800ca6ab  cmp     rcx, rax
0x1800ca6ae  jz      loc_1800CA4B6
0x1800ca6b4  mov     rdx, rsi
0x1800ca6b7  jmp     loc_1800CA4B1
0x1800ca6bc  mov     rbx, [rbp+190h+var_178]
0x1800ca6c0  movdqu  xmmword ptr [rsp+290h+var_228+8], xmm6
0x1800ca6c6  mov     [rbp+190h+var_210], 0FFFFFFFFFFFFFFFFh
0x1800ca6ce  cmp     rbx, [rbp+190h+var_178+8]
0x1800ca6d2  jz      loc_1800CAAEC
0x1800ca6d8  lea     rdx, [rsp+290h+var_268]; struct Path *
0x1800ca6dd  mov     byte ptr [rsp+290h+var_268], r12b
0x1800ca6e2  mov     rcx, rbx; this
0x1800ca6e5  call    ?IsWcifsReparsePoint@Csl@@YAJAEBVPath@1@AEA_N@Z; Csl::IsWcifsReparsePoint(Csl::Path const &,bool &)
0x1800ca6ea  mov     r15d, eax
0x1800ca6ed  test    eax, eax
0x1800ca6ef  js      loc_1800CAA47
0x1800ca6f5  cmp     byte ptr [rsp+290h+var_268], r12b
0x1800ca6fa  jz      loc_1800CA8CE
0x1800ca700  mov     rax, [rbx]
0x1800ca703  mov     rdx, [rsp+290h+var_258]
0x1800ca708  sub     rdx, [rsp+290h+var_260]
0x1800ca70d  sar     rdx, 1
0x1800ca710  inc     rdx
0x1800ca713  mov     [rbp+190h+var_188], r12w
0x1800ca718  lea     rdx, [rax+rdx*2]
0x1800ca71c  lea     rax, [rbp+190h+var_188]
0x1800ca720  mov     qword ptr [rbp+190h+Privilege], rdx
0x1800ca724  mov     [rbp+190h+var_198], rax
0x1800ca728  lea     rax, [rbp+190h+var_188]
0x1800ca72c  mov     [rbp+190h+var_190], rax
0x1800ca730  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ca734  inc     rax
0x1800ca737  cmp     [rdx+rax*2], r12w
0x1800ca73c  jnz     short loc_1800CA734
0x1800ca73e  lea     rdx, [rbp+190h+Privilege]
0x1800ca742  mov     [rbp+190h+var_158], rax
0x1800ca746  lea     rcx, [rbp+190h+var_198]; this
0x1800ca74a  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800ca74f  test    al, al
0x1800ca751  jz      loc_1800CAA24
0x1800ca757  lea     rax, [rbp+190h+var_140]
0x1800ca75b  mov     [rbp+190h+var_140], r12w
0x1800ca760  mov     [rbp+190h+var_150], rax
0x1800ca764  lea     rcx, [rbp+190h+var_150]; this
0x1800ca768  lea     rax, [rbp+190h+var_140]
0x1800ca76c  mov     [rbp+190h+var_148], rax
0x1800ca770  call    ?GetSystemDrivePath@Csl@@YAJAEAVPath@1@@Z; Csl::GetSystemDrivePath(Csl::Path &)
0x1800ca775  mov     r15d, eax
0x1800ca778  test    eax, eax
0x1800ca77a  js      loc_1800CA9DD
0x1800ca780  mov     rax, [rbp+190h+var_198]
0x1800ca784  lea     rdx, [rbp+190h+var_208]
0x1800ca788  mov     rcx, [rbp+190h+var_190]
0x1800ca78c  sub     rcx, rax
0x1800ca78f  mov     [rbp+190h+var_208], rax
0x1800ca793  sar     rcx, 1
0x1800ca796  mov     [rbp+190h+var_200], rcx
0x1800ca79a  lea     rcx, [rbp+190h+var_150]; this
0x1800ca79e  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800ca7a3  test    al, al
0x1800ca7a5  jz      loc_1800CA9BA
0x1800ca7ab  xorps   xmm0, xmm0
0x1800ca7ae  mov     [rbp+190h+var_9E], r12
0x1800ca7b5  movups  xmmword ptr [rbp+190h+var_78], xmm0
0x1800ca7bc  lea     rax, [rbp+190h+var_A0]
0x1800ca7c3  mov     [rbp+190h+var_96], r12d
0x1800ca7ca  mov     [rbp+190h+var_B0], rax
0x1800ca7d1  lea     rdx, [rbp+190h+var_150]
0x1800ca7d5  lea     rax, [rbp+190h+var_A0]
0x1800ca7dc  mov     [rbp+190h+var_92], r12w
0x1800ca7e4  mov     [rbp+190h+var_A8], rax
0x1800ca7eb  lea     rcx, [rbp+190h+var_78]
0x1800ca7f2  lea     rax, [rbp+190h+var_68]
0x1800ca7f9  mov     [rbp+190h+var_A0], r12w
0x1800ca801  mov     [rbp+190h+var_78], rax
0x1800ca808  lea     rax, [rbp+190h+var_68]
0x1800ca80f  movups  [rbp+190h+var_68], xmm0
0x1800ca816  mov     [rbp+190h+var_78+8], rax
0x1800ca81d  movdqa  [rbp+190h+var_90], xmm6
0x1800ca825  mov     [rbp+190h+var_80], 0FFFFFFFFFFFFFFFFh
0x1800ca830  mov     word ptr [rbp+190h+var_68], r12w
0x1800ca838  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800ca83d  lea     rdx, [rbp+190h+var_198]
0x1800ca841  lea     rcx, [rbp+190h+var_B0]
0x1800ca848  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1800ca84d  lea     rdx, [rbp+190h+var_B0]
0x1800ca854  lea     rcx, [rsp+290h+var_228+8]
0x1800ca859  call    ??$emplace_back@UBindMapping@Details@Core@Manager@Container@@$0A@@?$vector@UBindMapping@Details@Core@Manager@Container@@V?$allocator@UBindMapping@Details@Core@Manager@Container@@@utl@@@utl@@QEAA_N$$QEAUBindMapping@Details@Core@Manager@Container@@@Z; utl::vector<Container::Manager::Core::Details::BindMapping,utl::allocator<Container::Manager::Core::Details::BindMapping>>::emplace_back<Container::Manager::Core::Details::BindMapping,0>(Container::Manager::Core::Details::BindMapping &&)
0x1800ca85e  test    al, al
0x1800ca860  jz      short loc_1800CA8D7
0x1800ca862  mov     rcx, [rbp+190h+var_78]; void *
0x1800ca869  lea     rax, [rbp+190h+var_68]
0x1800ca870  cmp     rcx, rax
0x1800ca873  jz      short loc_1800CA87D
0x1800ca875  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca878  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca87d  lea     rcx, [rbp+190h+var_90]
0x1800ca884  call    ?_Uninit@?$vector@UOverlayDirectory@Details@Core@Manager@Container@@V?$allocator@UOverlayDirectory@Details@Core@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(void)
0x1800ca889  mov     rcx, [rbp+190h+var_B0]; void *
0x1800ca890  lea     rax, [rbp+190h+var_A0]
0x1800ca897  cmp     rcx, rax
0x1800ca89a  jz      short loc_1800CA8A4
0x1800ca89c  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca89f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca8a4  mov     rcx, [rbp+190h+var_150]; void *
0x1800ca8a8  lea     rax, [rbp+190h+var_140]
0x1800ca8ac  cmp     rcx, rax
0x1800ca8af  jz      short loc_1800CA8B9
0x1800ca8b1  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca8b4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca8b9  mov     rcx, [rbp+190h+var_198]; void *
0x1800ca8bd  lea     rax, [rbp+190h+var_188]
0x1800ca8c1  cmp     rcx, rax
0x1800ca8c4  jz      short loc_1800CA8CE
0x1800ca8c6  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca8c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca8ce  add     rbx, 20h ; ' '
0x1800ca8d2  jmp     loc_1800CA6CE
0x1800ca8d7  mov     rcx, [rbp+198h]; this
0x1800ca8de  lea     r8, aOnecoreBaseGen_46; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800ca8e5  mov     r9d, 8007000Eh; char *
0x1800ca8eb  mov     edx, 9DBh; void *
0x1800ca8f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca8f5  mov     rcx, [rbp+190h+var_78]; void *
0x1800ca8fc  lea     rax, [rbp+190h+var_68]
0x1800ca903  cmp     rcx, rax
0x1800ca906  jz      short loc_1800CA910
0x1800ca908  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca90b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca910  lea     rcx, [rbp+190h+var_90]
0x1800ca917  call    ?_Uninit@?$vector@UOverlayDirectory@Details@Core@Manager@Container@@V?$allocator@UOverlayDirectory@Details@Core@Manager@Container@@@utl@@@utl@@AEAAXXZ; utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(void)
0x1800ca91c  mov     rcx, [rbp+190h+var_B0]; void *
0x1800ca923  lea     rax, [rbp+190h+var_A0]
0x1800ca92a  cmp     rcx, rax
0x1800ca92d  jz      short loc_1800CA937
0x1800ca92f  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca932  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca937  mov     rcx, [rbp+190h+var_150]; void *
0x1800ca93b  lea     rax, [rbp+190h+var_140]
0x1800ca93f  cmp     rcx, rax
0x1800ca942  jz      short loc_1800CA94C
0x1800ca944  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca947  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca94c  mov     rcx, [rbp+190h+var_198]; void *
0x1800ca950  lea     rax, [rbp+190h+var_188]
0x1800ca954  cmp     rcx, rax
0x1800ca957  jz      short loc_1800CA961
0x1800ca959  mov     rdx, rsi; struct std::nothrow_t *
0x1800ca95c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca961  mov     rbx, qword ptr [rsp+290h+var_228+8]
0x1800ca966  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800ca96a  jz      short loc_1800CA9A2
0x1800ca96c  mov     rcx, qword ptr [rsp+290h+var_228+10h]
  ... truncated ...
```
