# OSIntegration::DEH::Internal::EventLogHelper::RemoveEventLogChanges(void)

- ea: `0x18006deb8`
- end: `0x18006e47b`
- name: `?RemoveEventLogChanges@EventLogHelper@Internal@DEH@OSIntegration@@AEAAJXZ`
- size: `1475`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::EventLogHelper *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ed250`

## callees

- `0x180009dc0`
- `0x18000a138`
- `0x18000a398`
- `0x180012fc8`
- `0x180018f88`
- `0x18001adb4`
- `0x1800225fc`
- `0x180050e60`
- `0x180069eb4`
- `0x18006cac4`
- `0x18006deb8`
- `0x180081974`
- `0x180084f38`
- `0x180087e3c`
- `0x1800af1bc`
- `0x1800ec490`
- `0x1800ec550`
- `0x1800ecd60`
- `0x1800ecf3c`
- `0x1800ed674`
- `0x180184c80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e194`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e194`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006e25c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006e25c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006e184`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006e3c5`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006e184`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18006e3c5`

## string_xrefs

- `0x18006e20f`: `SYSTEM\CurrentControlSet\Services\EventLog\Application\`
- `0x18006e00a`: `Uninstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OSIntegration::DEH::Internal::EventLogHelper::RemoveEventLogChanges(
        OSIntegration::DEH::Internal::EventLogHelper *this)
{
  __int64 v2; // rdx
  int EventFilesNotInDirectories; // edi
  __int64 v4; // rdx
  const struct std::nothrow_t *v5; // rdx
  int v7; // eax
  __int64 v8; // rdx
  unsigned __int64 v9; // rsi
  __int64 v10; // r14
  struct PACKAGE_VERSION *v11; // r8
  const struct std::nothrow_t *v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdx
  const struct std::nothrow_t *v18; // rdx
  WCHAR *v19; // rcx
  bool *v20; // r8
  __int64 v21; // rdx
  DWORD LastError; // eax
  const struct std::nothrow_t *v23; // rdx
  unsigned int v24; // ebx
  const struct std::nothrow_t *v25; // rdx
  int v26; // eax
  unsigned __int16 *v27; // rcx
  const struct std::nothrow_t *v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  const unsigned __int16 *v31; // rdx
  const unsigned __int16 *v32; // r8
  WCHAR *v33; // rdi
  int v34; // eax
  unsigned int v35; // esi
  const struct std::nothrow_t *v36; // rdx
  const struct std::nothrow_t *v37; // rdx
  const struct std::nothrow_t *v38; // rdx
  int v39; // eax
  const struct std::nothrow_t *v40; // rdx
  __int64 v41; // [rsp+20h] [rbp-79h]
  _QWORD v42[2]; // [rsp+40h] [rbp-59h] BYREF
  LPCWSTR lpPathName[2]; // [rsp+50h] [rbp-49h] BYREF
  int v44; // [rsp+60h] [rbp-39h]
  LPCWSTR lpSubKey[2]; // [rsp+68h] [rbp-31h] BYREF
  int v46; // [rsp+78h] [rbp-21h]
  _QWORD v47[2]; // [rsp+80h] [rbp-19h] BYREF
  unsigned __int64 v48; // [rsp+90h] [rbp-9h]
  char v49; // [rsp+98h] [rbp-1h]
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp+7h] BYREF
  int v51; // [rsp+B0h] [rbp+17h]
  unsigned __int16 *v52[2]; // [rsp+B8h] [rbp+1Fh] BYREF
  int v53; // [rsp+C8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  __int64 v55; // [rsp+100h] [rbp+67h] BYREF

  v2 = *((_QWORD *)this + 3);
  if ( !*(_BYTE *)(v2 + 403) || !*((_DWORD *)this + 22) )
    return 0;
  *(_OWORD *)lpPathName = 0;
  v44 = 0;
  EventFilesNotInDirectories = Common::PathHelpers::CombinePaths(
                                 *((const unsigned __int16 **)this + 9),
                                 *(const unsigned __int16 **)(v2 + 248),
                                 (struct Common::StringBuffer *)lpPathName);
  if ( EventFilesNotInDirectories < 0 )
  {
    v4 = 552;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)EventFilesNotInDirectories,
      v41);
LABEL_6:
    if ( lpPathName[1] )
      operator delete((void *)lpPathName[1], v5);
    return (unsigned int)EventFilesNotInDirectories;
  }
  EventFilesNotInDirectories = Common::PathHelpers::AddTrailingSlashIfNecessary((struct Common::StringBuffer *)lpPathName);
  if ( EventFilesNotInDirectories < 0 )
  {
    v4 = 553;
    goto LABEL_5;
  }
  v42[0] = 0;
  v42[1] = 0;
  v7 = Common::ImpersonationContext::Impersonate((Common::ImpersonationContext *)v42, 0);
  EventFilesNotInDirectories = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)v7,
      v41);
LABEL_13:
    if ( LODWORD(v42[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
    goto LABEL_6;
  }
  v47[0] = 0;
  v47[1] = 0;
  v48 = 0;
  v49 = 1;
  EventFilesNotInDirectories = OSIntegration::DEH::Internal::CopyFilenameArray((char *)this + 112, v47);
  if ( EventFilesNotInDirectories < 0 )
  {
    v8 = 560;
    goto LABEL_17;
  }
  EventFilesNotInDirectories = OSIntegration::DEH::Internal::EventLogHelper::FindEventFilesNotInDirectories(this, v47);
  if ( EventFilesNotInDirectories < 0 )
  {
    v8 = 561;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)EventFilesNotInDirectories,
      v41);
LABEL_18:
    Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v47);
    goto LABEL_13;
  }
  v55 = 0;
  v9 = 0;
  v10 = v47[0];
  while ( v9 < v48 )
  {
    *(_OWORD *)lpSubKey = 0;
    v46 = 0;
    EventFilesNotInDirectories = Common::PathHelpers::CombinePaths(
                                   lpPathName[1],
                                   *(const unsigned __int16 **)(*(_QWORD *)(v10 + 8 * v9) + 8LL),
                                   (struct Common::StringBuffer *)lpSubKey);
    if ( EventFilesNotInDirectories < 0 )
    {
      v17 = 568;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
        (const char *)(unsigned int)EventFilesNotInDirectories,
        v41);
      v19 = (WCHAR *)lpSubKey[1];
LABEL_35:
      if ( v19 )
        operator delete(v19, v18);
      goto LABEL_18;
    }
    if ( OSIntegration::DEH::Internal::GetPackageVersionFromHardLink(lpSubKey[1], (const unsigned __int16 *)&v55, v11)
      && *(_QWORD *)(*((_QWORD *)this + 3) + 464LL) == v55 )
    {
      v13 = AppXDeleteHardlinkSafely(lpSubKey[1]);
      EventFilesNotInDirectories = v13;
      if ( (byte_180245601 & 1) != 0 )
        McTemplateU0dzzz_EventWriteTransfer(
          lpSubKey[1],
          v14,
          v13,
          *(_QWORD *)(*((_QWORD *)this + 3) + 224LL),
          (__int64)lpSubKey[1],
          (__int64)L"Uninstall");
      v16 = *((_QWORD *)this + 3);
      v41 = *(_QWORD *)(v16 + 224);
      details::appxLog<long,unsigned short *,unsigned short *,unsigned short const *>(
        v16,
        v14,
        v15,
        (unsigned int)EventFilesNotInDirectories);
      if ( EventFilesNotInDirectories < 0 )
      {
        v17 = 586;
        goto LABEL_34;
      }
    }
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v12);
    ++v9;
  }
  *(_OWORD *)lpFileName = 0;
  v51 = 0;
  EventFilesNotInDirectories = Common::PathHelpers::CombinePaths(
                                 lpPathName[1],
                                 L"*.*",
                                 (struct Common::StringBuffer *)lpFileName);
  if ( EventFilesNotInDirectories < 0 )
  {
    v21 = 593;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)EventFilesNotInDirectories,
      v41);
LABEL_40:
    v19 = (WCHAR *)lpFileName[1];
    goto LABEL_35;
  }
  LOBYTE(v55) = 0;
  EventFilesNotInDirectories = OSIntegration::DEH::Internal::IsDirectoryEmpty(
                                 lpFileName[1],
                                 (const unsigned __int16 *)&v55,
                                 v20);
  if ( EventFilesNotInDirectories < 0 )
  {
    v21 = 595;
    goto LABEL_39;
  }
  if ( (_BYTE)v55 )
  {
    if ( !RemoveDirectoryW(lpPathName[1]) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x258,
                (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
                (const char *)LastError,
                v41);
        if ( lpFileName[1] )
          operator delete((void *)lpFileName[1], v23);
        Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v47);
        if ( LODWORD(v42[0]) )
          Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
        if ( lpPathName[1] )
          operator delete((void *)lpPathName[1], v25);
        return v24;
      }
    }
    *(_OWORD *)lpSubKey = 0;
    v46 = 0;
    v26 = Common::PathHelpers::CombinePaths(
            L"SYSTEM\\CurrentControlSet\\Services\\EventLog\\Application\\",
            *((const unsigned __int16 **)this + 12),
            (struct Common::StringBuffer *)lpSubKey);
    EventFilesNotInDirectories = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25C,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
        (const char *)(unsigned int)v26,
        v41);
      v27 = (unsigned __int16 *)lpSubKey[1];
      goto LABEL_55;
    }
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey[1]);
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v28);
  }
  *(_OWORD *)v52 = 0;
  v53 = 0;
  EventFilesNotInDirectories = Common::PathHelpers::CombinePaths(
                                 *((const unsigned __int16 **)this + 9),
                                 *(const unsigned __int16 **)(*((_QWORD *)this + 3) + 224LL),
                                 (struct Common::StringBuffer *)v52);
  if ( EventFilesNotInDirectories < 0 )
  {
    v29 = 610;
LABEL_61:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)EventFilesNotInDirectories,
      v41);
LABEL_62:
    v27 = v52[1];
LABEL_55:
    if ( v27 )
      operator delete(v27, v18);
    goto LABEL_40;
  }
  EventFilesNotInDirectories = Common::PathHelpers::AddTrailingSlashIfNecessary((struct Common::StringBuffer *)v52);
  if ( EventFilesNotInDirectories < 0 )
  {
    v29 = 611;
    goto LABEL_61;
  }
  *(_OWORD *)lpSubKey = 0;
  v46 = 0;
  EventFilesNotInDirectories = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)lpSubKey, v52[1]);
  if ( EventFilesNotInDirectories < 0 )
  {
    v30 = 613;
    goto LABEL_67;
  }
  EventFilesNotInDirectories = Common::PathHelpers::AppendPathSegment((struct Common::StringBuffer *)v52, L"*");
  if ( EventFilesNotInDirectories < 0 )
  {
    v30 = 614;
LABEL_67:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
      (const char *)(unsigned int)EventFilesNotInDirectories,
      v41);
    if ( lpSubKey[1] )
      operator delete((void *)lpSubKey[1], v18);
    goto LABEL_62;
  }
  v33 = (WCHAR *)lpSubKey[1];
  v34 = Common::Deployment::DeleteFiles((Common::Deployment *)lpSubKey[1], v31, v32);
  v35 = v34;
  if ( v34 >= 0 )
  {
    if ( !RemoveDirectoryW(v33) )
    {
      v39 = ReliableCleanup::CleanupManager::AddToPurgeList(*(_QWORD *)(*((_QWORD *)this + 3) + 224LL), 1, v33);
      if ( v39 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x26D,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
          (const char *)(unsigned int)v39,
          v41);
    }
    if ( v33 )
      operator delete(v33, v38);
    if ( v52[1] )
      operator delete(v52[1], v38);
    if ( lpFileName[1] )
      operator delete((void *)lpFileName[1], v38);
    Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v47);
    if ( LODWORD(v42[0]) )
      Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
    if ( lpPathName[1] )
      operator delete((void *)lpPathName[1], v40);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x268,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\eventlog\\eventloghelper.cpp",
    (const char *)(unsigned int)v34,
    v41);
  if ( v33 )
    operator delete(v33, v36);
  if ( v52[1] )
    operator delete(v52[1], v36);
  if ( lpFileName[1] )
    operator delete((void *)lpFileName[1], v36);
  Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(v47);
  if ( LODWORD(v42[0]) )
    Common::ImpersonationContext::Revert((Common::ImpersonationContext *)v42);
  if ( lpPathName[1] )
    operator delete((void *)lpPathName[1], v37);
  return v35;
}

```

## disassembly

```asm
0x18006deb8  mov     [rsp-8+arg_8], rbx
0x18006debd  mov     [rsp-8+arg_10], rsi
0x18006dec2  push    rbp
0x18006dec3  push    rdi
0x18006dec4  push    r12
0x18006dec6  push    r14
0x18006dec8  push    r15
0x18006deca  lea     rbp, [rsp-37h]
0x18006decf  sub     rsp, 0D0h
0x18006ded6  mov     rbx, rcx
0x18006ded9  mov     rdx, [rcx+18h]
0x18006dedd  xor     r15d, r15d
0x18006dee0  cmp     [rdx+193h], r15b
0x18006dee7  jz      loc_18006E45C
0x18006deed  cmp     [rcx+58h], r15d
0x18006def1  jbe     loc_18006E45C
0x18006def7  xorps   xmm0, xmm0
0x18006defa  movups  xmmword ptr [rbp+57h+lpPathName], xmm0
0x18006defe  mov     [rbp+57h+var_90], r15d
0x18006df02  lea     r8, [rbp+57h+lpPathName]; this
0x18006df06  mov     rdx, [rdx+0F8h]; Src
0x18006df0d  mov     rcx, [rcx+48h]; unsigned __int16 *
0x18006df11  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18006df16  mov     edi, eax
0x18006df18  test    eax, eax
0x18006df1a  jns     short loc_18006DF4A
0x18006df1c  mov     edx, 228h; void *
0x18006df21  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006df28  mov     r9d, edi; char *
0x18006df2b  mov     rcx, [rbp+5Fh]; this
0x18006df2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006df34  nop
0x18006df35  mov     rcx, [rbp+57h+lpPathName+8]; void *
0x18006df39  test    rcx, rcx
0x18006df3c  jz      short loc_18006DF43
0x18006df3e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006df43  mov     eax, edi
0x18006df45  jmp     loc_18006E45E
0x18006df4a  lea     rcx, [rbp+57h+lpPathName]; struct Common::StringBuffer *
0x18006df4e  call    ?AddTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBuffer@2@@Z; Common::PathHelpers::AddTrailingSlashIfNecessary(Common::StringBuffer *)
0x18006df53  mov     edi, eax
0x18006df55  test    eax, eax
0x18006df57  jns     short loc_18006DF60
0x18006df59  mov     edx, 229h
0x18006df5e  jmp     short loc_18006DF21
0x18006df60  mov     [rbp+57h+var_B0], r15
0x18006df64  mov     [rbp+57h+var_A8], r15
0x18006df68  xor     edx, edx; void *
0x18006df6a  lea     rcx, [rbp+57h+var_B0]; this
0x18006df6e  call    ?Impersonate@ImpersonationContext@Common@@QEAAJPEAX@Z; Common::ImpersonationContext::Impersonate(void *)
0x18006df73  mov     edi, eax
0x18006df75  test    eax, eax
0x18006df77  jns     short loc_18006DFA3
0x18006df79  mov     rcx, [rbp+5Fh]; this
0x18006df7d  mov     r9d, eax; char *
0x18006df80  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006df87  mov     edx, 22Dh; void *
0x18006df8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006df91  nop
0x18006df92  cmp     dword ptr [rbp+57h+var_B0], r15d
0x18006df96  jz      short loc_18006DF35
0x18006df98  lea     rcx, [rbp+57h+var_B0]; this
0x18006df9c  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18006dfa1  jmp     short loc_18006DF35
0x18006dfa3  mov     [rbp+57h+var_70], r15
0x18006dfa7  mov     [rbp+57h+var_68], r15
0x18006dfab  mov     [rbp+57h+var_60], r15
0x18006dfaf  mov     [rbp+57h+var_58], 1
0x18006dfb3  lea     rcx, [rbx+70h]
0x18006dfb7  lea     rdx, [rbp+57h+var_70]
0x18006dfbb  call    ?CopyFilenameArray@Internal@DEH@OSIntegration@@YAJAEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@0@Z; OSIntegration::DEH::Internal::CopyFilenameArray(Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &,Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &)
0x18006dfc0  mov     edi, eax
0x18006dfc2  test    eax, eax
0x18006dfc4  jns     short loc_18006DFEA
0x18006dfc6  mov     edx, 230h; void *
0x18006dfcb  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006dfd2  mov     r9d, edi; char *
0x18006dfd5  mov     rcx, [rbp+5Fh]; this
0x18006dfd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006dfde  nop
0x18006dfdf  lea     rcx, [rbp+57h+var_70]
0x18006dfe3  call    ??1?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@QEAA@XZ; Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(void)
0x18006dfe8  jmp     short loc_18006DF92
0x18006dfea  lea     rdx, [rbp+57h+var_70]
0x18006dfee  mov     rcx, rbx
0x18006dff1  call    ?FindEventFilesNotInDirectories@EventLogHelper@Internal@DEH@OSIntegration@@AEAAJAEAV?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@@Z; OSIntegration::DEH::Internal::EventLogHelper::FindEventFilesNotInDirectories(Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>> &)
0x18006dff6  mov     edi, eax
0x18006dff8  test    eax, eax
0x18006dffa  jns     short loc_18006E003
0x18006dffc  mov     edx, 231h
0x18006e001  jmp     short loc_18006DFCB
0x18006e003  mov     [rbp+57h+arg_0], r15
0x18006e007  mov     rsi, r15
0x18006e00a  lea     r12, aUninstall; "Uninstall"
0x18006e011  mov     r14, [rbp+57h+var_70]
0x18006e015  xorps   xmm0, xmm0
0x18006e018  cmp     rsi, [rbp+57h+var_60]
0x18006e01c  jnb     loc_18006E117
0x18006e022  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18006e026  mov     [rbp+57h+var_78], r15d
0x18006e02a  mov     rdx, [r14+rsi*8]
0x18006e02e  lea     r8, [rbp+57h+lpSubKey]; this
0x18006e032  mov     rdx, [rdx+8]; Src
0x18006e036  mov     rcx, [rbp+57h+lpPathName+8]; unsigned __int16 *
0x18006e03a  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18006e03f  mov     edi, eax
0x18006e041  test    eax, eax
0x18006e043  js      loc_18006E0E7
0x18006e049  lea     rdx, [rbp+57h+arg_0]; unsigned __int16 *
0x18006e04d  mov     rcx, [rbp+57h+lpSubKey+8]; lpFileName
0x18006e051  call    ?GetPackageVersionFromHardLink@Internal@DEH@OSIntegration@@YA_NPEBGAEAUPACKAGE_VERSION@@@Z; OSIntegration::DEH::Internal::GetPackageVersionFromHardLink(ushort const *,PACKAGE_VERSION &)
0x18006e056  test    al, al
0x18006e058  jz      short loc_18006E0CA
0x18006e05a  mov     rcx, [rbx+18h]
0x18006e05e  mov     rax, [rbp+57h+arg_0]
0x18006e062  cmp     [rcx+1D0h], rax
0x18006e069  jnz     short loc_18006E0CA
0x18006e06b  mov     rcx, [rbp+57h+lpSubKey+8]; lpExistingFileName
0x18006e06f  call    ?AppXDeleteHardlinkSafely@@YAJPEBG@Z; AppXDeleteHardlinkSafely(ushort const *)
0x18006e074  mov     edi, eax
0x18006e076  test    cs:byte_180245601, 1
0x18006e07d  jz      short loc_18006E0A0
0x18006e07f  mov     r9, [rbx+18h]
0x18006e083  mov     [rsp+0F0h+var_C8], r12
0x18006e088  mov     rcx, [rbp+57h+lpSubKey+8]
0x18006e08c  mov     [rsp+0F0h+var_D0], rcx
0x18006e091  mov     r9, [r9+0E0h]
0x18006e098  mov     r8d, eax
0x18006e09b  call    McTemplateU0dzzz_EventWriteTransfer
0x18006e0a0  mov     rcx, [rbx+18h]
0x18006e0a4  mov     [rsp+0F0h+var_C0], r12
0x18006e0a9  mov     rax, [rbp+57h+lpSubKey+8]
0x18006e0ad  mov     [rsp+0F0h+var_C8], rax
0x18006e0b2  mov     rax, [rcx+0E0h]
0x18006e0b9  mov     [rsp+0F0h+var_D0], rax
0x18006e0be  mov     r9d, edi
0x18006e0c1  call    ??$appxLog@JPEAGPEAGPEBG@details@@YAXJAEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@JPEAG2PEBG@Z; details::appxLog<long,ushort *,ushort *,ushort const *>(long,_GUID const &,_EVENT_DESCRIPTOR const &,long,ushort *,ushort *,ushort const *)
0x18006e0c6  test    edi, edi
0x18006e0c8  js      short loc_18006E0E0
0x18006e0ca  mov     rcx, [rbp+57h+lpSubKey+8]; void *
0x18006e0ce  test    rcx, rcx
0x18006e0d1  jz      short loc_18006E0D8
0x18006e0d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e0d8  inc     rsi
0x18006e0db  jmp     loc_18006E015
0x18006e0e0  mov     edx, 24Ah
0x18006e0e5  jmp     short loc_18006E0EC
0x18006e0e7  mov     edx, 238h; void *
0x18006e0ec  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006e0f3  mov     r9d, edi; char *
0x18006e0f6  mov     rcx, [rbp+5Fh]; this
0x18006e0fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e0ff  nop
0x18006e100  mov     rcx, [rbp+57h+lpSubKey+8]; void *
0x18006e104  test    rcx, rcx
0x18006e107  jz      loc_18006DFDF
0x18006e10d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e112  jmp     loc_18006DFDF
0x18006e117  movups  xmmword ptr [rbp+57h+lpFileName], xmm0
0x18006e11b  mov     [rbp+57h+var_40], r15d
0x18006e11f  lea     r8, [rbp+57h+lpFileName]; this
0x18006e123  lea     rdx, asc_1801DEE88; "*.*"
0x18006e12a  mov     rcx, [rbp+57h+lpPathName+8]; unsigned __int16 *
0x18006e12e  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18006e133  mov     edi, eax
0x18006e135  test    eax, eax
0x18006e137  jns     short loc_18006E158
0x18006e139  mov     edx, 251h; void *
0x18006e13e  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006e145  mov     r9d, edi; char *
0x18006e148  mov     rcx, [rbp+5Fh]; this
0x18006e14c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e151  nop
0x18006e152  mov     rcx, [rbp+57h+lpFileName+8]
0x18006e156  jmp     short loc_18006E104
0x18006e158  mov     byte ptr [rbp+57h+arg_0], r15b
0x18006e15c  lea     rdx, [rbp+57h+arg_0]; unsigned __int16 *
0x18006e160  mov     rcx, [rbp+57h+lpFileName+8]; lpFileName
0x18006e164  call    ?IsDirectoryEmpty@Internal@DEH@OSIntegration@@YAJPEBGAEA_N@Z; OSIntegration::DEH::Internal::IsDirectoryEmpty(ushort const *,bool &)
0x18006e169  mov     edi, eax
0x18006e16b  test    eax, eax
0x18006e16d  jns     short loc_18006E176
0x18006e16f  mov     edx, 253h
0x18006e174  jmp     short loc_18006E13E
0x18006e176  cmp     byte ptr [rbp+57h+arg_0], r15b
0x18006e17a  jz      loc_18006E277
0x18006e180  mov     rcx, [rbp+57h+lpPathName+8]; lpPathName
0x18006e184  call    cs:__imp_RemoveDirectoryW
0x18006e18b  nop     dword ptr [rax+rax+00h]
0x18006e190  test    eax, eax
0x18006e192  jnz     short loc_18006E1FC
0x18006e194  call    cs:__imp_GetLastError
0x18006e19b  nop     dword ptr [rax+rax+00h]
0x18006e1a0  test    eax, eax
0x18006e1a2  jz      short loc_18006E1FC
0x18006e1a4  mov     rcx, [rbp+5Fh]; this
0x18006e1a8  mov     r9d, eax; char *
0x18006e1ab  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006e1b2  mov     edx, 258h; void *
0x18006e1b7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006e1bc  mov     ebx, eax
0x18006e1be  mov     rcx, [rbp+57h+lpFileName+8]; void *
0x18006e1c2  test    rcx, rcx
0x18006e1c5  jz      short loc_18006E1CD
0x18006e1c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e1cc  nop
0x18006e1cd  lea     rcx, [rbp+57h+var_70]
0x18006e1d1  call    ??1?$Array@VStringBuffer@Common@@V?$ContainerOperations@VStringBuffer@Common@@V12@@2@VNoKey@2@V?$ContainerOperations@VNoKey@Common@@VStringBuffer@2@@2@V?$ArrayOperations@VStringBuffer@Common@@VNoKey@2@@2@@Common@@QEAA@XZ; Common::Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>::~Array<Common::StringBuffer,Common::ContainerOperations<Common::StringBuffer,Common::StringBuffer>,Common::NoKey,Common::ContainerOperations<Common::NoKey,Common::StringBuffer>,Common::ArrayOperations<Common::StringBuffer,Common::NoKey>>(void)
0x18006e1d6  nop
0x18006e1d7  cmp     dword ptr [rbp+57h+var_B0], r15d
0x18006e1db  jz      short loc_18006E1E7
0x18006e1dd  lea     rcx, [rbp+57h+var_B0]; this
0x18006e1e1  call    ?Revert@ImpersonationContext@Common@@QEAAXXZ; Common::ImpersonationContext::Revert(void)
0x18006e1e6  nop
0x18006e1e7  mov     rcx, [rbp+57h+lpPathName+8]; void *
0x18006e1eb  test    rcx, rcx
0x18006e1ee  jz      short loc_18006E1F5
0x18006e1f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e1f5  mov     eax, ebx
0x18006e1f7  jmp     loc_18006E45E
0x18006e1fc  xorps   xmm0, xmm0
0x18006e1ff  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18006e203  mov     [rbp+57h+var_78], r15d
0x18006e207  lea     r8, [rbp+57h+lpSubKey]; this
0x18006e20b  mov     rdx, [rbx+60h]; Src
0x18006e20f  lea     rcx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x18006e216  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18006e21b  mov     edi, eax
0x18006e21d  test    eax, eax
0x18006e21f  jns     short loc_18006E251
0x18006e221  mov     rcx, [rbp+5Fh]; this
0x18006e225  mov     r9d, eax; char *
0x18006e228  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006e22f  mov     edx, 25Ch; void *
0x18006e234  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e239  nop
0x18006e23a  mov     rcx, [rbp+57h+lpSubKey+8]; void *
0x18006e23e  test    rcx, rcx
0x18006e241  jz      loc_18006E152
0x18006e247  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e24c  jmp     loc_18006E152
0x18006e251  mov     rdx, [rbp+57h+lpSubKey+8]; lpSubKey
0x18006e255  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e25c  call    cs:__imp_RegDeleteTreeW
0x18006e263  nop     dword ptr [rax+rax+00h]
0x18006e268  nop
0x18006e269  mov     rcx, [rbp+57h+lpSubKey+8]; void *
0x18006e26d  test    rcx, rcx
0x18006e270  jz      short loc_18006E277
0x18006e272  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e277  xorps   xmm0, xmm0
0x18006e27a  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18006e27e  mov     [rbp+57h+var_28], r15d
0x18006e282  mov     rdx, [rbx+18h]
0x18006e286  lea     r8, [rbp+57h+var_38]; this
0x18006e28a  mov     rdx, [rdx+0E0h]; Src
0x18006e291  mov     rcx, [rbx+48h]; unsigned __int16 *
0x18006e295  call    ?CombinePaths@PathHelpers@Common@@SAJPEBG0PEAVStringBuffer@2@@Z; Common::PathHelpers::CombinePaths(ushort const *,ushort const *,Common::StringBuffer *)
0x18006e29a  mov     edi, eax
0x18006e29c  test    eax, eax
0x18006e29e  jns     short loc_18006E2C2
0x18006e2a0  mov     edx, 262h; void *
0x18006e2a5  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006e2ac  mov     r9d, edi; char *
0x18006e2af  mov     rcx, [rbp+5Fh]; this
0x18006e2b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e2b8  nop
0x18006e2b9  mov     rcx, [rbp+57h+var_38+8]
0x18006e2bd  jmp     loc_18006E23E
0x18006e2c2  lea     rcx, [rbp+57h+var_38]; struct Common::StringBuffer *
0x18006e2c6  call    ?AddTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBuffer@2@@Z; Common::PathHelpers::AddTrailingSlashIfNecessary(Common::StringBuffer *)
0x18006e2cb  mov     edi, eax
0x18006e2cd  test    eax, eax
0x18006e2cf  jns     short loc_18006E2D8
0x18006e2d1  mov     edx, 263h
0x18006e2d6  jmp     short loc_18006E2A5
0x18006e2d8  xorps   xmm0, xmm0
0x18006e2db  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18006e2df  mov     [rbp+57h+var_78], r15d
0x18006e2e3  mov     rdx, [rbp+57h+var_38+8]; unsigned __int16 *
0x18006e2e7  lea     rcx, [rbp+57h+lpSubKey]; this
0x18006e2eb  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18006e2f0  mov     edi, eax
0x18006e2f2  test    eax, eax
0x18006e2f4  jns     short loc_18006E31F
0x18006e2f6  mov     edx, 265h; void *
0x18006e2fb  lea     r8, aOnecoreAdminAp_74; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18006e302  mov     r9d, edi; char *
0x18006e305  mov     rcx, [rbp+5Fh]; this
0x18006e309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006e30e  nop
0x18006e30f  mov     rcx, [rbp+57h+lpSubKey+8]; void *
0x18006e313  test    rcx, rcx
0x18006e316  jz      short loc_18006E2B9
0x18006e318  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006e31d  jmp     short loc_18006E2B9
0x18006e31f  lea     rdx, asc_1801CAC10; "*"
0x18006e326  lea     rcx, [rbp+57h+var_38]; struct Common::StringBuffer *
0x18006e32a  call    ?AppendPathSegment@PathHelpers@Common@@SAJPEAVStringBuffer@2@PEBG@Z; Common::PathHelpers::AppendPathSegment(Common::StringBuffer *,ushort const *)
0x18006e32f  mov     edi, eax
  ... truncated ...
```
