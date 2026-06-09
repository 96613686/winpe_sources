# _anonymous_namespace_::TempCleanup::EnumProfiles

- ea: `0x1800230dc`
- end: `0x18002358e`
- name: `_anonymous_namespace_::TempCleanup::EnumProfiles`
- size: `1202`
- prototype: `LSTATUS __fastcall(wchar_t *wzStateRoot)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024138`

## callees

- `0x1800026d0`
- `0x1800186bc`
- `0x180018fb8`
- `0x180019178`
- `0x1800230dc`
- `0x180023594`
- `0x1800235c4`
- `0x18002363c`
- `0x180026540`
- `0x1800286c0`
- `0x1800286e4`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800231a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023565`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023565`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180023220`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180023220`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800232f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002343b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800232f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002343b`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18002347f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18002347f`
- `ext-ms-onecore-appmodel-tdlmigration-l1-1-0!CreateTdlMigrator` at `0x18002313d`
- `ext-ms-onecore-appmodel-tdlmigration-l1-1-0!CreateTdlMigrator` at `0x18002313d`

## string_xrefs

- `0x1800232bf`: `ProfileImagePath`
- `0x18002349f`: `Failed to get local app data path from PathCchRemoveFileSpec %ws`
- `0x18002352a`: `Failed to set all databases deleted`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::TempCleanup::EnumProfiles(wchar_t *wzStateRoot)
{
  DWORD v1; // edi
  bool v3; // si
  HRESULT v4; // eax
  LSTATUS v5; // eax
  const char *v6; // r8
  int v7; // ebx
  char v8; // r15
  char v9; // r14
  DWORD v10; // edx
  DWORD v11; // r12d
  LSTATUS v12; // eax
  const char *v13; // r8
  int v14; // ebx
  HRESULT v15; // eax
  LSTATUS ValueW; // eax
  const char *v17; // r8
  int v18; // ebx
  HRESULT v19; // eax
  HRESULT v20; // eax
  TileDataLayer::Migration::ITdlMigration *value; // rcx
  LSTATUS v22; // eax
  const char *v23; // r8
  int v24; // ebx
  HRESULT v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // eax
  LSTATUS result; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcchClass; // [rsp+30h] [rbp-D0h]
  wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration> > tdlMigrator; // [rsp+40h] [rbp-C0h] BYREF
  Common::AutoHandleRegKey hkProfileList; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int fullProfileValue; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int cbProfilePath; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int cchKeyName; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int fullProfileValueSize; // [rsp+5Ch] [rbp-A4h] BYREF
  wil::details::out_param_t<wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration> > > v37; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t wzKeyName[256]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t wzProfilePath[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t wzErrorPath[264]; // [rsp+490h] [rbp+390h] BYREF
  void *retaddr; // [rsp+6F8h] [rbp+5F8h]

  v1 = 0;
  hkProfileList.h = 0;
  v3 = 1;
  tdlMigrator.__ptr_.__value_ = 0;
  if ( IsCreateTdlMigratorPresent() )
  {
    v37.pRaw = 0;
    v37.wrapper = &tdlMigrator;
    v37.replace = 1;
    v4 = CreateTdlMigrator(&v37.pRaw);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        0xF4u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
        v4);
    wil::details::out_param_t<wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration>>>::~out_param_t<wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration>>>(&v37);
    if ( tdlMigrator.__ptr_.__value_ )
      v3 = tdlMigrator.__ptr_.__value_->AreAllDatabaseDeleted(tdlMigrator.__ptr_.__value_);
  }
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20019u,
         &hkProfileList.h);
  v7 = v5;
  if ( v5 )
  {
    wil::details::in1diag3::_Log_Win32(retaddr, 0xFDu, v6, v5);
    Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
      v7);
    goto LABEL_31;
  }
  v8 = 0;
  v9 = 0;
  do
  {
    v10 = v1;
    v11 = v1++;
    cchKeyName = 255;
    v12 = RegEnumKeyExW(hkProfileList.h, v10, wzKeyName, &cchKeyName, 0, 0, 0, 0);
    v14 = v12;
    if ( v12 )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, 0x109u, v13, v12);
      v8 = 1;
      if ( v14 != 259 )
      {
        LODWORD(phkResult) = v11;
        v15 = StringCchPrintfW(
                wzErrorPath,
                0x104u,
                L"%s\\%d",
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
                phkResult);
        if ( wil::details::in1diag3::Log_IfFailedMsg(
               retaddr,
               0x113u,
               "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
               v15,
               "i %u",
               v1) >= 0 )
          Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(wzErrorPath, v14);
      }
    }
    cbProfilePath = 520;
    ValueW = RegGetValueW(hkProfileList.h, wzKeyName, L"ProfileImagePath", 2u, 0, wzProfilePath, &cbProfilePath);
    v18 = ValueW;
    if ( ValueW )
    {
      wil::details::in1diag3::_Log_Win32(retaddr, 0x11Fu, v17, ValueW);
      v19 = StringCchPrintfW(
              wzErrorPath,
              0x104u,
              L"%s\\%s::%s",
              L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
              wzKeyName,
              L"ProfileImagePath");
      LODWORD(lpcchClass) = v1;
      if ( wil::details::in1diag3::Log_IfFailedMsg(
             retaddr,
             0x123u,
             "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
             v19,
             "StringCchPrintfW %ws i %u",
             wzKeyName,
             lpcchClass) >= 0 )
        Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(wzErrorPath, v18);
    }
    v20 = StringCchCatW(wzProfilePath, 0x104u, L"\\appdata\\local\\packages");
    if ( wil::details::in1diag3::Log_IfFailedMsg(
           retaddr,
           0x12Au,
           "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
           v20,
           "StringCchCatW %u",
           v1) < 0 )
      goto LABEL_25;
    anonymous_namespace_::TempCleanup::EnumStateRoot(wzStateRoot);
    value = tdlMigrator.__ptr_.__value_;
    if ( tdlMigrator.__ptr_.__value_ && !v3 )
    {
      fullProfileValue = 0;
      fullProfileValueSize = 4;
      v22 = RegGetValueW(hkProfileList.h, wzKeyName, L"FullProfile", 0x10u, 0, &fullProfileValue, &fullProfileValueSize);
      v24 = v22;
      if ( v22 )
      {
        wil::details::in1diag3::_Log_Win32(retaddr, 0x135u, v23, v22);
        Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(L"FullProfile", v24);
      }
      if ( fullProfileValue == 1 )
      {
        v25 = PathCchRemoveFileSpec(wzProfilePath, cbProfilePath);
        if ( wil::details::in1diag3::Log_IfFailedMsg(
               retaddr,
               0x13Du,
               "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
               v25,
               "Failed to get local app data path from PathCchRemoveFileSpec %ws",
               wzProfilePath) >= 0 )
        {
          v26 = tdlMigrator.__ptr_.__value_->DeleteTdlDatabaseIfAllDone(
                  tdlMigrator.__ptr_.__value_,
                  wzKeyName,
                  wzProfilePath);
          if ( v26 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              0x13Fu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
              v26);
            v9 = 1;
          }
        }
      }
LABEL_25:
      value = tdlMigrator.__ptr_.__value_;
    }
  }
  while ( !v8 );
  if ( value && !v3 && !v9 )
  {
    v27 = value->SetAllDatabasesDeleted(value);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      0x14Du,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
      v27,
      "Failed to set all databases deleted");
  }
LABEL_31:
  wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration>>::reset(
    &tdlMigrator,
    0);
  result = LODWORD(hkProfileList.h) - 1;
  if ( (unsigned __int64)hkProfileList.h - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    return RegCloseKey(hkProfileList.h);
  return result;
}

```

## disassembly

```asm
0x1800230dc  push    rbp
0x1800230de  push    rbx
0x1800230df  push    rsi
0x1800230e0  push    rdi
0x1800230e1  push    r12
0x1800230e3  push    r13
0x1800230e5  push    r14
0x1800230e7  push    r15
0x1800230e9  lea     rbp, [rsp-5B8h]
0x1800230f1  sub     rsp, 6B8h
0x1800230f8  mov     rax, cs:__security_cookie
0x1800230ff  xor     rax, rsp
0x180023102  mov     [rbp+5F0h+var_50], rax
0x180023109  xor     edi, edi
0x18002310b  mov     r13, this
0x18002310e  mov     [rsp+6F0h+hkProfileList.h], rdi
0x180023113  mov     sil, 1
0x180023116  mov     [rsp+6F0h+tdlMigrator.__ptr_.__value_], rdi
0x18002311b  call    IsCreateTdlMigratorPresent
0x180023120  test    al, al
0x180023122  jz      short loc_180023185
0x180023124  lea     rax, [rsp+6F0h+tdlMigrator]
0x180023129  mov     [rsp+6F0h+var_690.pRaw], rdi
0x18002312e  lea     this, [rsp+6F0h+var_690.pRaw]
0x180023133  mov     [rsp+6F0h+var_690.wrapper], rax
0x180023138  mov     [rsp+6F0h+var_690.replace], sil
0x18002313d  call    cs:__imp_CreateTdlMigrator
0x180023143  test    eax, eax
0x180023145  jns     short loc_180023162
0x180023147  mov     this, [rbp+5F8h]; callerReturnAddress
0x18002314e  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x180023155  mov     r9d, eax; hr
0x180023158  mov     edx, 0F4h; lineNumber
0x18002315d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023162  lea     this, [rsp+6F0h+var_690]; this
0x180023167  call    ??1?$out_param_t@V?$unique_ptr@UITdlMigration@Migration@TileDataLayer@@U?$default_delete@UITdlMigration@Migration@TileDataLayer@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration>>>::~out_param_t<wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration>>>(void)
0x18002316c  mov     this, [rsp+6F0h+tdlMigrator.__ptr_.__value_]
0x180023171  test    this, this
0x180023174  jz      short loc_180023185
0x180023176  mov     rax, [this]
0x180023179  mov     rax, [rax+60h]
0x18002317d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023182  mov     sil, al
0x180023185  lea     rax, [rsp+6F0h+hkProfileList]
0x18002318a  mov     r9d, 20019h; samDesired
0x180023190  xor     r8d, r8d; ulOptions
0x180023193  mov     [rsp+6F0h+phkResult], rax; phkResult
0x180023198  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002319f  mov     this, 0FFFFFFFF80000002h; hKey
0x1800231a6  call    cs:__imp_RegOpenKeyExW
0x1800231ac  mov     ebx, eax
0x1800231ae  test    eax, eax
0x1800231b0  jz      short loc_1800231D9
0x1800231b2  mov     this, [rbp+5F8h]; callerReturnAddress
0x1800231b9  mov     r9d, eax; callerReturnAddress
0x1800231bc  mov     edx, 0FDh; lineNumber
0x1800231c1  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800231c6  mov     edx, ebx; errorCode
0x1800231c8  lea     this, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800231cf  call    ?LogTempCleanupProfileError@Logging@StateABIHelpers@Storage@Windows@@SAJPEBGJ@Z; Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(ushort const *,long)
0x1800231d4  jmp     loc_18002354A
0x1800231d9  xor     r15b, r15b
0x1800231dc  xor     r14b, r14b
0x1800231df  mov     this, [rsp+6F0h+hkProfileList.h]; hKey
0x1800231e4  lea     r9, [rsp+6F0h+cchKeyName]; lpcchName
0x1800231e9  mov     [rsp+6F0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800231f2  lea     r8, [rbp+5F0h+wzKeyName]; lpName
0x1800231f6  mov     [rsp+6F0h+lpcchClass], 0; lpcchClass
0x1800231ff  mov     edx, edi; dwIndex
0x180023201  mov     [rsp+6F0h+lpClass], 0; lpClass
0x18002320a  mov     r12d, edi
0x18002320d  mov     [rsp+6F0h+phkResult], 0; lpReserved
0x180023216  inc     edi
0x180023218  mov     [rsp+6F0h+cchKeyName], 0FFh
0x180023220  call    cs:__imp_RegEnumKeyExW
0x180023226  mov     ebx, eax
0x180023228  test    eax, eax
0x18002322a  jz      loc_1800232B0
0x180023230  mov     this, [rbp+5F8h]; callerReturnAddress
0x180023237  mov     r9d, eax; callerReturnAddress
0x18002323a  mov     edx, 109h; lineNumber
0x18002323f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180023244  mov     r15b, 1
0x180023247  cmp     ebx, 103h
0x18002324d  jz      short loc_1800232B0
0x18002324f  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180023256  mov     dword ptr [rsp+6F0h+phkResult], r12d
0x18002325b  lea     r8, aSD; "%s\\%d"
0x180023262  mov     edx, 104h; cchDest
0x180023267  lea     this, [rbp+5F0h+wzErrorPath]; pszDest
0x18002326e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023273  mov     this, [rbp+5F8h]; callerReturnAddress
0x18002327a  lea     rdx, aIU; "i %u"
0x180023281  mov     dword ptr [rsp+6F0h+lpClass], edi
0x180023285  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002328c  mov     [rsp+6F0h+phkResult], rdx; formatString
0x180023291  mov     r9d, eax; hr
0x180023294  mov     edx, 113h; lineNumber
0x180023299  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002329e  test    eax, eax
0x1800232a0  js      short loc_1800232B0
0x1800232a2  mov     edx, ebx; errorCode
0x1800232a4  lea     this, [rbp+5F0h+wzErrorPath]; object
0x1800232ab  call    ?LogTempCleanupProfileError@Logging@StateABIHelpers@Storage@Windows@@SAJPEBGJ@Z; Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(ushort const *,long)
0x1800232b0  mov     this, [rsp+6F0h+hkProfileList.h]; hkey
0x1800232b5  lea     rax, [rsp+6F0h+cbProfilePath]
0x1800232ba  mov     [rsp+6F0h+lpcchClass], rax; pcbData
0x1800232bf  lea     r12, aProfileimagepa; "ProfileImagePath"
0x1800232c6  lea     rax, [rbp+5F0h+wzProfilePath]
0x1800232cd  mov     [rsp+6F0h+cbProfilePath], 208h
0x1800232d5  mov     [rsp+6F0h+lpClass], rax; pvData
0x1800232da  lea     rdx, [rbp+5F0h+wzKeyName]; lpSubKey
0x1800232de  mov     r9d, 2; dwFlags
0x1800232e4  mov     [rsp+6F0h+phkResult], 0; pdwType
0x1800232ed  mov     r8, r12; lpValue
0x1800232f0  call    cs:__imp_RegGetValueW
0x1800232f6  mov     ebx, eax
0x1800232f8  test    eax, eax
0x1800232fa  jz      loc_180023387
0x180023300  mov     this, [rbp+5F8h]; callerReturnAddress
0x180023307  mov     r9d, eax; callerReturnAddress
0x18002330a  mov     edx, 11Fh; lineNumber
0x18002330f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180023314  lea     rax, [rbp+5F0h+wzKeyName]
0x180023318  mov     [rsp+6F0h+lpClass], r12
0x18002331d  lea     r9, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180023324  mov     [rsp+6F0h+phkResult], rax
0x180023329  lea     r8, aSSS_0; "%s\\%s::%s"
0x180023330  mov     edx, 104h; cchDest
0x180023335  lea     this, [rbp+5F0h+wzErrorPath]; pszDest
0x18002333c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023341  mov     this, [rbp+5F8h]; callerReturnAddress
0x180023348  lea     rdx, [rbp+5F0h+wzKeyName]
0x18002334c  mov     dword ptr [rsp+6F0h+lpcchClass], edi
0x180023350  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x180023357  mov     [rsp+6F0h+lpClass], rdx
0x18002335c  mov     r9d, eax; hr
0x18002335f  lea     rdx, aStringcchprint_2; "StringCchPrintfW %ws i %u"
0x180023366  mov     [rsp+6F0h+phkResult], rdx; formatString
0x18002336b  mov     edx, 123h; lineNumber
0x180023370  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180023375  test    eax, eax
0x180023377  js      short loc_180023387
0x180023379  mov     edx, ebx; errorCode
0x18002337b  lea     this, [rbp+5F0h+wzErrorPath]; object
0x180023382  call    ?LogTempCleanupProfileError@Logging@StateABIHelpers@Storage@Windows@@SAJPEBGJ@Z; Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(ushort const *,long)
0x180023387  lea     r8, aAppdataLocalPa; "\\appdata\\local\\packages"
0x18002338e  mov     edx, 104h; cchDest
0x180023393  lea     this, [rbp+5F0h+wzProfilePath]; pszDest
0x18002339a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002339f  mov     this, [rbp+5F8h]; callerReturnAddress
0x1800233a6  lea     rdx, aStringcchcatwU; "StringCchCatW %u"
0x1800233ad  mov     dword ptr [rsp+6F0h+lpClass], edi
0x1800233b1  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800233b8  mov     [rsp+6F0h+phkResult], rdx; formatString
0x1800233bd  mov     r9d, eax; hr
0x1800233c0  mov     edx, 12Ah; lineNumber
0x1800233c5  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800233ca  test    eax, eax
0x1800233cc  js      loc_1800234FA
0x1800233d2  lea     rdx, [rbp+5F0h+wzProfilePath]
0x1800233d9  mov     this, r13; wzStateRoot
0x1800233dc  call    _anonymous_namespace___TempCleanup__EnumStateRoot
0x1800233e1  mov     this, [rsp+6F0h+tdlMigrator.__ptr_.__value_]
0x1800233e6  test    this, this
0x1800233e9  jz      loc_1800234FF
0x1800233ef  test    sil, sil
0x1800233f2  jnz     loc_1800234FF
0x1800233f8  mov     this, [rsp+6F0h+hkProfileList.h]; hkey
0x1800233fd  lea     rax, [rsp+6F0h+fullProfileValueSize]
0x180023402  mov     [rsp+6F0h+lpcchClass], rax; pcbData
0x180023407  lea     r8, aFullprofile; "FullProfile"
0x18002340e  lea     rax, [rsp+6F0h+fullProfileValue]
0x180023413  mov     [rsp+6F0h+fullProfileValue], 0
0x18002341b  mov     [rsp+6F0h+lpClass], rax; pvData
0x180023420  lea     rdx, [rbp+5F0h+wzKeyName]; lpSubKey
0x180023424  mov     r9d, 10h; dwFlags
0x18002342a  mov     [rsp+6F0h+phkResult], 0; pdwType
0x180023433  mov     [rsp+6F0h+fullProfileValueSize], 4
0x18002343b  call    cs:__imp_RegGetValueW
0x180023441  mov     ebx, eax
0x180023443  test    eax, eax
0x180023445  jz      short loc_180023469
0x180023447  mov     this, [rbp+5F8h]; callerReturnAddress
0x18002344e  mov     r9d, eax; callerReturnAddress
0x180023451  mov     edx, 135h; lineNumber
0x180023456  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002345b  mov     edx, ebx; errorCode
0x18002345d  lea     this, aFullprofile; "FullProfile"
0x180023464  call    ?LogTempCleanupProfileError@Logging@StateABIHelpers@Storage@Windows@@SAJPEBGJ@Z; Windows::Storage::StateABIHelpers::Logging::LogTempCleanupProfileError(ushort const *,long)
0x180023469  cmp     [rsp+6F0h+fullProfileValue], 1
0x18002346e  jnz     loc_1800234FA
0x180023474  mov     edx, [rsp+6F0h+cbProfilePath]; cchPath
0x180023478  lea     this, [rbp+5F0h+wzProfilePath]; pszPath
0x18002347f  call    cs:__imp_PathCchRemoveFileSpec
0x180023485  mov     this, [rbp+5F8h]; callerReturnAddress
0x18002348c  lea     rdx, [rbp+5F0h+wzProfilePath]
0x180023493  mov     [rsp+6F0h+lpClass], rdx
0x180023498  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002349f  lea     rdx, aFailedToGetLoc; "Failed to get local app data path from "...
0x1800234a6  mov     r9d, eax; hr
0x1800234a9  mov     [rsp+6F0h+phkResult], rdx; formatString
0x1800234ae  mov     edx, 13Dh; lineNumber
0x1800234b3  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800234b8  test    eax, eax
0x1800234ba  js      short loc_1800234FA
0x1800234bc  mov     this, [rsp+6F0h+tdlMigrator.__ptr_.__value_]
0x1800234c1  lea     r8, [rbp+5F0h+wzProfilePath]
0x1800234c8  lea     rdx, [rbp+5F0h+wzKeyName]
0x1800234cc  mov     rax, [this]
0x1800234cf  mov     rax, [rax+50h]
0x1800234d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234d8  test    eax, eax
0x1800234da  jns     short loc_1800234FA
0x1800234dc  mov     this, [rbp+5F8h]; callerReturnAddress
0x1800234e3  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800234ea  mov     r9d, eax; hr
0x1800234ed  mov     edx, 13Fh; lineNumber
0x1800234f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800234f7  mov     r14b, 1
0x1800234fa  mov     this, [rsp+6F0h+tdlMigrator.__ptr_.__value_]
0x1800234ff  test    r15b, r15b
0x180023502  jz      loc_1800231DF
0x180023508  test    this, this
0x18002350b  jz      short loc_18002354A
0x18002350d  test    sil, sil
0x180023510  jnz     short loc_18002354A
0x180023512  test    r14b, r14b
0x180023515  jnz     short loc_18002354A
0x180023517  mov     rax, [this]
0x18002351a  mov     rax, [rax+68h]
0x18002351e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023523  mov     this, [rbp+5F8h]; callerReturnAddress
0x18002352a  lea     rdx, aFailedToSetAll; "Failed to set all databases deleted"
0x180023531  mov     [rsp+6F0h+phkResult], rdx; formatString
0x180023536  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002353d  mov     edx, 14Dh; lineNumber
0x180023542  mov     r9d, eax; hr
0x180023545  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002354a  xor     edx, edx; __p
0x18002354c  lea     this, [rsp+6F0h+tdlMigrator]; this
0x180023551  call    ?reset@?$unique_ptr@UITdlMigration@Migration@TileDataLayer@@U?$default_delete@UITdlMigration@Migration@TileDataLayer@@@wistd@@@wistd@@QEAAXPEAUITdlMigration@Migration@TileDataLayer@@@Z; wistd::unique_ptr<TileDataLayer::Migration::ITdlMigration,wistd::default_delete<TileDataLayer::Migration::ITdlMigration>>::reset(TileDataLayer::Migration::ITdlMigration *)
0x180023556  mov     this, [rsp+6F0h+hkProfileList.h]; hKey
0x18002355b  lea     rax, [this-1]
0x18002355f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023563  ja      short loc_18002356B
0x180023565  call    cs:__imp_RegCloseKey
0x18002356b  mov     this, [rbp+5F0h+var_50]
0x180023572  xor     this, rsp; StackCookie
0x180023575  call    __security_check_cookie
0x18002357a  add     rsp, 6B8h
0x180023581  pop     r15
0x180023583  pop     r14
0x180023585  pop     r13
0x180023587  pop     r12
0x180023589  pop     rdi
0x18002358a  pop     rsi
0x18002358b  pop     rbx
0x18002358c  pop     rbp
0x18002358d  retn
```
