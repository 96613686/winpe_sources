# ArpApplication::GetArpApplication(ConfigSettings const &,HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong)

- ea: `0x180007824`
- end: `0x1800083f1`
- name: `?GetArpApplication@ArpApplication@@QEAAXAEBVConfigSettings@@QEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2K@Z`
- size: `3021`
- prototype: `__int64 __fastcall(Application *this, const struct ConfigSettings *, HKEY, __int64, __int64, REGSAM samDesired)`
- caller_count: `3`
- callee_count: `45`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007748`
- `0x18001405c`
- `0x180030c70`

## callees

- `0x180007824`
- `0x18000dfc4`
- `0x18000eb5c`
- `0x18000ecac`
- `0x1800118d0`
- `0x1800150ac`
- `0x180015f74`
- `0x18001716c`
- `0x1800175b0`
- `0x180017724`
- `0x180018450`
- `0x1800188f4`
- `0x180018a60`
- `0x1800197d4`
- `0x180019edc`
- `0x18001ccfc`
- `0x180022500`
- `0x1800260f4`
- `0x18002b55c`
- `0x18002bff4`
- `0x18002d210`
- `0x180030ff4`
- `0x180034908`
- `0x180034ff0`
- `0x18003c10c`
- `0x1800403ac`
- `0x1800404c4`
- `0x180041dbc`
- `0x180044c88`
- `0x1800461c4`
- `0x1800493b8`
- `0x18004f820`
- `0x180050030`
- `0x180052f28`
- `0x180053b1c`
- `0x180059920`
- `0x1800f92d0`
- `0x1800ff750`
- `0x1800ff7b4`
- `0x1800ff808`
- `0x1800ff89c`
- `0x1800ff8f0`
- `0x180100418`
- `0x180110aac`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180007ed2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180007ed2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000789a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000789a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008016`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180008016`
- `KERNEL32!FileTimeToSystemTime` at `0x18000803a`
- `KERNEL32!FileTimeToSystemTime` at `0x18000803a`
- `SHLWAPI!PathIsNetworkPathW` at `0x180008100`
- `SHLWAPI!PathIsNetworkPathW` at `0x180008100`

## string_xrefs

- `0x180007db0`: `UninstallString`
- `0x180007e7c`: `InstallDate`
- `0x1800083b0`: `base\appcompat\inventory\software\inv2\lib\arpapplication.cpp`
- `0x1800083df`: `base\appcompat\inventory\software\inv2\lib\arpapplication.cpp`
- `0x180007aef`: `Failed to compute ProgramId for: %ws, %ws, %ws, %d`
- `0x180007df9`: `QuietUninstallString`
- `0x18000830c`: `Ignoring install directory: %ws %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall ArpApplication::GetArpApplication(
        Application *this,
        const struct ConfigSettings *a2,
        HKEY a3,
        __int64 a4,
        __int64 a5,
        REGSAM samDesired)
{
  const WCHAR *v10; // rdx
  unsigned int v11; // eax
  __int64 RegValueString; // rax
  __int64 v13; // rax
  __int64 v15; // rax
  __int64 v16; // rcx
  int RegValueDword; // ebx
  LPCWSTR *v18; // rcx
  const struct ConfigSettings *v19; // rdx
  __int64 LongPath; // rax
  __int64 v21; // rax
  char *v22; // r14
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 *v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // ebx
  _QWORD *v31; // rcx
  unsigned int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  const WCHAR *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdi
  int v38; // ebx
  int v39; // eax
  struct File *i; // rbx
  char *v41; // rcx
  void *p_SystemTime; // rdx
  __int64 v43; // rax
  const char *v44; // r9
  void *v45; // rdx
  unsigned int v46; // r8d
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v50; // [rsp+68h] [rbp-98h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h]
  struct _FILETIME ftLastWriteTime; // [rsp+80h] [rbp-80h] BYREF
  __int64 v53; // [rsp+90h] [rbp-70h]
  _SYSTEMTIME SystemTime; // [rsp+98h] [rbp-68h] BYREF
  _BYTE Src[32]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v56[16]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v57; // [rsp+D8h] [rbp-28h]
  _QWORD v58[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v59; // [rsp+F8h] [rbp-8h]
  _BYTE v60[32]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v61[3]; // [rsp+128h] [rbp+28h] BYREF
  LPCWSTR v62[3]; // [rsp+148h] [rbp+48h] BYREF
  LPCWSTR pszPath[4]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v64[3]; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v65[4]; // [rsp+1A8h] [rbp+A8h] BYREF
  struct File *v66[5]; // [rsp+1C8h] [rbp+C8h] BYREF
  _BYTE v67[104]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v68; // [rsp+258h] [rbp+158h]
  char v69; // [rsp+516h] [rbp+416h]
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+478h]

  v53 = -2;
  hKey = 0;
  if ( *(_QWORD *)(a4 + 24) <= 7u )
    v10 = (const WCHAR *)a4;
  else
    v10 = *(const WCHAR **)a4;
  v11 = RegOpenKeyExW(a3, v10, 0, samDesired, &hKey);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x9B,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\arpapplication.cpp",
      (const char *)v11,
      phkResult);
  std::wstring::wstring(v58);
  std::wstring::wstring(v56, L"DisplayName");
  RegValueString = Utility::GetRegValueString(v60, a3, a4, v56);
  std::wstring::operator=(v58, RegValueString);
  std::wstring::~wstring(v60);
  std::wstring::~wstring(v56);
  if ( v59
    || (std::wstring::wstring(v56, L"QuietDisplayName"),
        v13 = Utility::GetRegValueString(v60, a3, a4, v56),
        std::wstring::operator=(v58, v13),
        std::wstring::~wstring(v60),
        std::wstring::~wstring(v56),
        v59) )
  {
    if ( !(unsigned __int8)Application::IsUpdate(v58) || *((_BYTE *)a2 + 51) )
    {
      std::wstring::wstring(v62);
      std::wstring::wstring(v56, L"Publisher");
      v15 = Utility::GetRegValueString(v60, a3, a4, v56);
      std::wstring::operator=(v62, v15);
      std::wstring::~wstring(v60);
      std::wstring::~wstring(v56);
      std::wstring::wstring(v61);
      ArpApplication::GetVersionInfoFromArp(v16, a3, a4, v61);
      std::wstring::wstring(v56, L"Language");
      RegValueDword = Utility::GetRegValueDword(a3, a4, v56, 0xFFFF);
      std::wstring::~wstring(v56);
      AslLogCallPrintf(
        3,
        (unsigned int)"ArpApplication::GetArpApplication",
        205,
        (unsigned int)"ArpApp >>>>>>>>>>> %ws, %ws, %ws, %d");
      Application::ComputeProgramId(
        (unsigned int)v64,
        (unsigned int)v58,
        (unsigned int)v62,
        (unsigned int)v61,
        RegValueDword);
      if ( !v64[2] )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"ArpApplication::GetArpApplication",
          215,
          (unsigned int)"Failed to compute ProgramId for: %ws, %ws, %ws, %d");
        std::wstring::wstring(v56, &byte_1801389F0);
        Application::SetName(this, v56);
        v18 = (LPCWSTR *)v56;
LABEL_12:
        std::wstring::~wstring(v18);
LABEL_13:
        std::wstring::~wstring(v64);
        std::wstring::~wstring(v61);
        std::wstring::~wstring(v62);
        goto LABEL_9;
      }
      if ( *((_BYTE *)a2 + 52) )
      {
        Application::SetName(this, v58);
        Application::SetPublisher(this, v62);
        Application::SetVersion(this, v61);
        *((_DWORD *)this + 116) = RegValueDword;
        std::wstring::operator=((char *)this + 56, v64);
        goto LABEL_13;
      }
      if ( !Application::ForceFullAppScan )
      {
        Application::GetApplicationFromCache(this);
        if ( Application::IsValid(this, v19) )
        {
          *((_BYTE *)this + 1000) = 1;
          goto LABEL_13;
        }
      }
      Application::SetName(this, v58);
      Application::SetPublisher(this, v62);
      Application::SetVersion(this, v61);
      *((_DWORD *)this + 116) = RegValueDword;
      std::wstring::operator=((char *)this + 56, v64);
      Application::AddUserSid(this, a5);
      std::wstring::wstring(pszPath);
      ArpApplication::GetInstallLocationFromArp(this, a3, a4, pszPath);
      LongPath = Utility::GetLongPath(v60, pszPath);
      std::wstring::operator=(pszPath, LongPath);
      std::wstring::~wstring(v60);
      Application::SetInstallLocation(this, pszPath);
      std::wstring::operator=((char *)this + 368, Application::ApplicationTypeApplication);
      if ( a3 == HKEY_LOCAL_MACHINE )
      {
        std::wstring::operator=((char *)this + 336, &Application::ApplicationSourceAddRemoveProgram);
        v21 = std::operator+<unsigned short>(v60, L"HKEY_LOCAL_MACHINE\\", a4);
        std::wstring::operator=((char *)this + 432, v21);
        std::wstring::~wstring(v60);
        v22 = (char *)this + 16;
      }
      else
      {
        if ( a3 != HKEY_USERS )
        {
          v44 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
          wil::details::in1diag3::Throw_Hr(retaddr, v45, v46, v44, phkResulta);
        }
        v22 = (char *)this + 16;
        v23 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 2) + 40LL))((char *)this + 16);
        v24 = std::wstring::find(v23, Application::SilverlightOutOfBrowserInstallPath);
        v25 = Application::ApplicationSourceSilverlight;
        if ( v24 == -1 )
          v25 = &Application::ApplicationSourceAddRemoveProgramPerUser;
        std::wstring::operator=((char *)this + 336, v25);
        v26 = std::operator+<unsigned short>(v60, L"HKEY_USERS\\", a4);
        std::wstring::operator=((char *)this + 432, v26);
        std::wstring::~wstring(v60);
        std::wstring::wstring(v56);
        std::wstring::wstring(Src, L"AndroidPackageName");
        v27 = Utility::GetRegValueString(v60, -2147483645, a4, Src);
        std::wstring::operator=(v56, v27);
        std::wstring::~wstring(v60);
        std::wstring::~wstring(Src);
        if ( v57 )
          goto LABEL_60;
        std::wstring::~wstring(v56);
      }
      std::wstring::wstring(v56);
      std::wstring::wstring(Src, L"UninstallString");
      v28 = Utility::GetRegValueString(v60, a3, a4, Src);
      std::wstring::operator=(v56, v28);
      std::wstring::~wstring(v60);
      std::wstring::~wstring(Src);
      if ( !v57 )
      {
        std::wstring::wstring(Src, L"QuietUninstallString");
        v29 = Utility::GetRegValueString(v60, a3, a4, Src);
        std::wstring::operator=(v56, v29);
        std::wstring::~wstring(v60);
        std::wstring::~wstring(Src);
      }
      Application::SetUninstallString(this, v56);
      std::wstring::wstring(Src, L"EstimatedSize");
      v30 = Utility::GetRegValueDword(a3, a4, Src, 0);
      std::wstring::~wstring(Src);
      *((_DWORD *)this + 117) = v30;
      std::wstring::wstring(v60, L"InstallDate");
      Utility::GetRegValueString(v65, a3, a4, v60);
      std::wstring::~wstring(v60);
      if ( v65[2] != 8 )
        goto LABEL_33;
      v31 = v65;
      if ( v65[3] > 7u )
        v31 = (_QWORD *)v65[0];
      if ( (unsigned int)_o__wtoi(v31) )
      {
        std::wstring::substr(v65, Src, 4, 2);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::substr(v65, v66, 6, 2);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::~wstring(v66);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::substr(v65, v66, 0, 4);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::~wstring(v66);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::operator=(v65, Src);
      }
      else
      {
LABEL_33:
        ftLastWriteTime = 0;
        v32 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
        if ( v32 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x162,
            (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\arpapplication.cpp",
            (const char *)v32,
            phkResulta);
        SystemTime = 0;
        if ( !FileTimeToSystemTime(&ftLastWriteTime, &SystemTime) )
          goto LABEL_37;
        phkResulta = SystemTime.wYear;
        v33 = Utility::FormatWstring(Src, L"%02d/%02d/%04d %02d:%02d:%02d", SystemTime.wMonth, SystemTime.wDay);
        std::wstring::operator=(v65, v33);
      }
      std::wstring::~wstring(Src);
LABEL_37:
      std::wstring::operator=((char *)this + 256, v65);
      *((_BYTE *)this + 700) = ArpApplication::GetIsArpSystemComponent(v34, a3, a4);
      if ( !*(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 96LL))(v22) + 16)
        && *(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 40LL))(v22) + 16) > 3u )
      {
        v35 = (const WCHAR *)pszPath;
        if ( pszPath[3] > (LPCWSTR)7 )
          v35 = pszPath[0];
        if ( !PathIsNetworkPathW(v35) )
        {
          if ( !*(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 40LL))(v22) + 16) )
            Application::SetInstallLocation(this, pszPath);
          v36 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 40LL))(v22);
          if ( (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(v36) )
          {
            v50 = 0;
            v51 = 0;
            std::wstring::wstring(Src, L".exe");
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v50, Src);
            std::wstring::~wstring(Src);
            std::wstring::wstring(Src, L".dll");
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v50, Src);
            std::wstring::~wstring(Src);
            std::wstring::wstring(Src, L".cpl");
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v50, Src);
            std::wstring::~wstring(Src);
            std::wstring::wstring(Src, L".sys");
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v50, Src);
            std::wstring::~wstring(Src);
            v37 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
            ftLastWriteTime = (struct _FILETIME)Src;
            v38 = std::vector<std::wstring>::vector<std::wstring>(Src, &v50);
            v39 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 40LL))(v22);
            File::SearchForPeFiles((unsigned int)v66, (_DWORD)a2, v39, v38, phkResulta, v37, 0);
            for ( i = v66[0]; ; i = (struct File *)((char *)i + 816) )
            {
              if ( i == v66[1] )
              {
                std::vector<File>::_Tidy(v66);
                std::vector<std::wstring>::_Tidy(&v50);
                goto LABEL_55;
              }
              File::File((File *)v67, i);
              if ( v69 )
              {
                v41 = (char *)this + 40;
                p_SystemTime = &SystemTime;
              }
              else
              {
                if ( !v68 )
                  goto LABEL_51;
                v41 = (char *)this + 24;
                p_SystemTime = &ftLastWriteTime;
              }
              std::_Tree<std::_Tset_traits<File,std::less<File>,std::allocator<File>,0>>::emplace<File &>(
                v41,
                p_SystemTime,
                v67);
LABEL_51:
              File::~File((File *)v67);
            }
          }
          AslLogCallPrintf(
            3,
            (unsigned int)"ArpApplication::GetArpApplication",
            419,
            (unsigned int)"Ignoring install directory: %ws %ws");
        }
      }
LABEL_55:
      v43 = Application::ComputeProgramInstanceId(this, Src);
      std::wstring::operator=((char *)this + 400, v43);
      std::wstring::~wstring(Src);
      if ( *((_BYTE *)a2 + 219) )
        (*(void (__fastcall **)(Application *, const struct ConfigSettings *))(*(_QWORD *)this + 96LL))(this, a2);
      if ( !*(_QWORD *)((*(__int64 (__fastcall **)(char *))(*(_QWORD *)v22 + 96LL))(v22) + 16) )
        Application::SaveApplicationToCache(this, a2);
      std::wstring::~wstring(v65);
LABEL_60:
      std::wstring::~wstring(v56);
      v18 = pszPath;
      goto LABEL_12;
    }
  }
LABEL_9:
  std::wstring::~wstring(v58);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180007824  push    rbp
0x180007826  push    rbx
0x180007827  push    rsi
0x180007828  push    rdi
0x180007829  push    r12
0x18000782b  push    r13
0x18000782d  push    r14
0x18000782f  push    r15
0x180007831  lea     rbp, [rsp-438h]
0x180007839  sub     rsp, 538h
0x180007840  mov     [rbp+470h+var_4E0], 0FFFFFFFFFFFFFFFEh
0x180007848  mov     rax, cs:__security_cookie
0x18000784f  xor     rax, rsp
0x180007852  mov     [rbp+470h+var_50], rax
0x180007859  mov     rdi, r9
0x18000785c  mov     r15, r8
0x18000785f  mov     r12, rdx
0x180007862  mov     rsi, rcx
0x180007865  mov     r14, [rbp+470h+arg_20]
0x18000786c  xor     r13d, r13d
0x18000786f  mov     [rsp+570h+hKey], r13
0x180007874  cmp     qword ptr [r9+18h], 7
0x180007879  jbe     short loc_180007880
0x18000787b  mov     rdx, [r9]
0x18000787e  jmp     short loc_180007883
0x180007880  mov     rdx, rdi; lpSubKey
0x180007883  lea     rax, [rsp+570h+hKey]
0x180007888  mov     [rsp+570h+phkResult], rax; unsigned int
0x18000788d  mov     r9d, [rbp+470h+samDesired]; samDesired
0x180007894  xor     r8d, r8d; ulOptions
0x180007897  mov     rcx, r15; hKey
0x18000789a  call    cs:__imp_RegOpenKeyExW
0x1800078a0  mov     rcx, [rbp+478h]; this
0x1800078a7  test    eax, eax
0x1800078a9  jnz     loc_1800083DC
0x1800078af  lea     rcx, [rbp+470h+var_488]
0x1800078b3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800078b8  nop
0x1800078b9  lea     rdx, aDisplayname_0; "DisplayName"
0x1800078c0  lea     rcx, [rbp+470h+var_4A8]
0x1800078c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800078c9  nop
0x1800078ca  lea     r9, [rbp+470h+var_4A8]
0x1800078ce  mov     r8, rdi
0x1800078d1  mov     rdx, r15
0x1800078d4  lea     rcx, [rbp+470h+var_468]
0x1800078d8  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x1800078dd  mov     rdx, rax
0x1800078e0  lea     rcx, [rbp+470h+var_488]
0x1800078e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800078e9  lea     rcx, [rbp+470h+var_468]
0x1800078ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800078f2  nop
0x1800078f3  lea     rcx, [rbp+470h+var_4A8]
0x1800078f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800078fc  cmp     [rbp+470h+var_478], r13
0x180007900  jnz     short loc_18000794B
0x180007902  lea     rdx, aQuietdisplayna; "QuietDisplayName"
0x180007909  lea     rcx, [rbp+470h+var_4A8]
0x18000790d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180007912  nop
0x180007913  lea     r9, [rbp+470h+var_4A8]
0x180007917  mov     r8, rdi
0x18000791a  mov     rdx, r15
0x18000791d  lea     rcx, [rbp+470h+var_468]
0x180007921  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x180007926  mov     rdx, rax
0x180007929  lea     rcx, [rbp+470h+var_488]
0x18000792d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180007932  lea     rcx, [rbp+470h+var_468]
0x180007936  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000793b  nop
0x18000793c  lea     rcx, [rbp+470h+var_4A8]
0x180007940  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007945  cmp     [rbp+470h+var_478], r13
0x180007949  jz      short loc_18000795F
0x18000794b  lea     rcx, [rbp+470h+var_488]
0x18000794f  call    ?IsUpdate@Application@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::IsUpdate(std::wstring const &)
0x180007954  test    al, al
0x180007956  jz      short loc_180007996
0x180007958  cmp     [r12+33h], r13b
0x18000795d  jnz     short loc_180007996
0x18000795f  lea     rcx, [rbp+470h+var_488]
0x180007963  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007968  nop
0x180007969  lea     rcx, [rsp+570h+hKey]
0x18000796e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180007973  mov     rcx, [rbp+470h+var_50]
0x18000797a  xor     rcx, rsp; StackCookie
0x18000797d  call    __security_check_cookie
0x180007982  add     rsp, 538h
0x180007989  pop     r15
0x18000798b  pop     r14
0x18000798d  pop     r13
0x18000798f  pop     r12
0x180007991  pop     rdi
0x180007992  pop     rsi
0x180007993  pop     rbx
0x180007994  pop     rbp
0x180007995  retn
0x180007996  lea     rcx, [rbp+470h+var_428]
0x18000799a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18000799f  nop
0x1800079a0  lea     rdx, aPublisher; "Publisher"
0x1800079a7  lea     rcx, [rbp+470h+var_4A8]
0x1800079ab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800079b0  nop
0x1800079b1  lea     r9, [rbp+470h+var_4A8]
0x1800079b5  mov     r8, rdi
0x1800079b8  mov     rdx, r15
0x1800079bb  lea     rcx, [rbp+470h+var_468]
0x1800079bf  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x1800079c4  mov     rdx, rax
0x1800079c7  lea     rcx, [rbp+470h+var_428]
0x1800079cb  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800079d0  lea     rcx, [rbp+470h+var_468]
0x1800079d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800079d9  nop
0x1800079da  lea     rcx, [rbp+470h+var_4A8]
0x1800079de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800079e3  lea     rcx, [rbp+470h+var_448]
0x1800079e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800079ec  nop
0x1800079ed  lea     r9, [rbp+470h+var_448]
0x1800079f1  mov     r8, rdi
0x1800079f4  mov     rdx, r15
0x1800079f7  call    ?GetVersionInfoFromArp@ArpApplication@@QEAAXQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; ArpApplication::GetVersionInfoFromArp(HKEY__ * const,std::wstring const &,std::wstring &)
0x1800079fc  lea     rdx, aLanguage; "Language"
0x180007a03  lea     rcx, [rbp+470h+var_4A8]
0x180007a07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180007a0c  nop
0x180007a0d  mov     r9d, 0FFFFh
0x180007a13  lea     r8, [rbp+470h+var_4A8]
0x180007a17  mov     rdx, rdi
0x180007a1a  mov     rcx, r15
0x180007a1d  call    ?GetRegValueDword@Utility@@SAKQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Utility::GetRegValueDword(HKEY__ * const,std::wstring const &,std::wstring const &,ulong)
0x180007a22  mov     ebx, eax
0x180007a24  lea     rcx, [rbp+470h+var_4A8]
0x180007a28  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007a2d  lea     r8, [rbp+470h+var_448]
0x180007a31  cmp     [rbp+470h+var_430], 7
0x180007a36  cmova   r8, [rbp+470h+var_448]
0x180007a3b  lea     rdx, [rbp+470h+var_428]
0x180007a3f  cmp     [rbp+470h+var_410], 7
0x180007a44  cmova   rdx, [rbp+470h+var_428]
0x180007a49  lea     rcx, [rbp+470h+var_488]
0x180007a4d  cmp     [rbp+470h+var_470], 7
0x180007a52  cmova   rcx, [rbp+470h+var_488]
0x180007a57  mov     dword ptr [rsp+570h+lpcValues], ebx
0x180007a5b  mov     [rsp+570h+lpcbMaxClassLen], r8
0x180007a60  mov     [rsp+570h+lpcbMaxSubKeyLen], rdx
0x180007a65  mov     [rsp+570h+phkResult], rcx
0x180007a6a  lea     r9, aArpappWsWsWsD; "ArpApp >>>>>>>>>>> %ws, %ws, %ws, %d"
0x180007a71  mov     r8d, 0CDh
0x180007a77  lea     rdx, aArpapplication_0; "ArpApplication::GetArpApplication"
0x180007a7e  mov     ecx, 3
0x180007a83  call    AslLogCallPrintf
0x180007a88  mov     dword ptr [rsp+570h+phkResult], ebx; int
0x180007a8c  lea     r9, [rbp+470h+var_448]
0x180007a90  lea     r8, [rbp+470h+var_428]
0x180007a94  lea     rdx, [rbp+470h+var_488]
0x180007a98  lea     rcx, [rbp+470h+var_3E8]
0x180007a9f  call    ?ComputeProgramId@Application@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@00K@Z; Application::ComputeProgramId(std::wstring const &,std::wstring const &,std::wstring const &,ulong)
0x180007aa4  nop
0x180007aa5  cmp     [rbp+470h+var_3D8], r13
0x180007aac  jnz     loc_180007B5A
0x180007ab2  lea     rdx, [rbp+470h+var_448]
0x180007ab6  cmp     [rbp+470h+var_430], 7
0x180007abb  cmova   rdx, [rbp+470h+var_448]
0x180007ac0  lea     rcx, [rbp+470h+var_428]
0x180007ac4  cmp     [rbp+470h+var_410], 7
0x180007ac9  cmova   rcx, [rbp+470h+var_428]
0x180007ace  lea     rax, [rbp+470h+var_488]
0x180007ad2  cmp     [rbp+470h+var_470], 7
0x180007ad7  cmova   rax, [rbp+470h+var_488]
0x180007adc  mov     dword ptr [rsp+570h+lpcValues], ebx
0x180007ae0  mov     [rsp+570h+lpcbMaxClassLen], rdx
0x180007ae5  mov     [rsp+570h+lpcbMaxSubKeyLen], rcx
0x180007aea  mov     [rsp+570h+phkResult], rax
0x180007aef  lea     r9, aFailedToComput; "Failed to compute ProgramId for: %ws, %"...
0x180007af6  mov     r8d, 0D7h
0x180007afc  lea     rdx, aArpapplication_0; "ArpApplication::GetArpApplication"
0x180007b03  mov     ecx, 1
0x180007b08  call    AslLogCallPrintf
0x180007b0d  lea     rdx, byte_1801389F0
0x180007b14  lea     rcx, [rbp+470h+var_4A8]
0x180007b18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180007b1d  nop
0x180007b1e  lea     rdx, [rbp+470h+var_4A8]
0x180007b22  mov     rcx, rsi
0x180007b25  call    ?SetName@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetName(std::wstring const &)
0x180007b2a  nop
0x180007b2b  lea     rcx, [rbp+470h+var_4A8]
0x180007b2f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007b34  nop
0x180007b35  lea     rcx, [rbp+470h+var_3E8]
0x180007b3c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007b41  nop
0x180007b42  lea     rcx, [rbp+470h+var_448]
0x180007b46  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007b4b  nop
0x180007b4c  lea     rcx, [rbp+470h+var_428]
0x180007b50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007b55  jmp     loc_18000795F
0x180007b5a  cmp     [r12+34h], r13b
0x180007b5f  jz      short loc_180007B9D
0x180007b61  lea     rdx, [rbp+470h+var_488]
0x180007b65  mov     rcx, rsi
0x180007b68  call    ?SetName@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetName(std::wstring const &)
0x180007b6d  lea     rdx, [rbp+470h+var_428]
0x180007b71  mov     rcx, rsi
0x180007b74  call    ?SetPublisher@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetPublisher(std::wstring const &)
0x180007b79  lea     rdx, [rbp+470h+var_448]
0x180007b7d  mov     rcx, rsi
0x180007b80  call    ?SetVersion@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetVersion(std::wstring const &)
0x180007b85  mov     [rsi+1D0h], ebx
0x180007b8b  lea     rcx, [rsi+38h]
0x180007b8f  lea     rdx, [rbp+470h+var_3E8]
0x180007b96  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180007b9b  jmp     short loc_180007B35
0x180007b9d  cmp     cs:?ForceFullAppScan@Application@@1_NA, r13b; bool Application::ForceFullAppScan
0x180007ba4  jnz     short loc_180007BD0
0x180007ba6  lea     r8, [rbp+470h+var_3E8]
0x180007bad  mov     rdx, r12
0x180007bb0  mov     rcx, rsi; struct IAmiInventoryItem *
0x180007bb3  call    ?GetApplicationFromCache@Application@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::GetApplicationFromCache(ConfigSettings const &,std::wstring const &)
0x180007bb8  mov     rcx, rsi; this
0x180007bbb  call    ?IsValid@Application@@QEAA_NAEBVConfigSettings@@@Z; Application::IsValid(ConfigSettings const &)
0x180007bc0  test    al, al
0x180007bc2  jz      short loc_180007BD0
0x180007bc4  mov     byte ptr [rsi+3E8h], 1
0x180007bcb  jmp     loc_180007B35
0x180007bd0  lea     rdx, [rbp+470h+var_488]
0x180007bd4  mov     rcx, rsi
0x180007bd7  call    ?SetName@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetName(std::wstring const &)
0x180007bdc  lea     rdx, [rbp+470h+var_428]
0x180007be0  mov     rcx, rsi
0x180007be3  call    ?SetPublisher@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetPublisher(std::wstring const &)
0x180007be8  lea     rdx, [rbp+470h+var_448]
0x180007bec  mov     rcx, rsi
0x180007bef  call    ?SetVersion@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetVersion(std::wstring const &)
0x180007bf4  mov     [rsi+1D0h], ebx
0x180007bfa  lea     rcx, [rsi+38h]
0x180007bfe  lea     rdx, [rbp+470h+var_3E8]
0x180007c05  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180007c0a  mov     rdx, r14
0x180007c0d  mov     rcx, rsi
0x180007c10  call    ?AddUserSid@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::AddUserSid(std::wstring const &)
0x180007c15  lea     rcx, [rbp+470h+pszPath]
0x180007c19  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180007c1e  nop
0x180007c1f  lea     r9, [rbp+470h+pszPath]
0x180007c23  mov     r8, rdi
0x180007c26  mov     rdx, r15
0x180007c29  mov     rcx, rsi
0x180007c2c  call    ?GetInstallLocationFromArp@ArpApplication@@QEAAXQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z; ArpApplication::GetInstallLocationFromArp(HKEY__ * const,std::wstring const &,std::wstring &)
0x180007c31  lea     rdx, [rbp+470h+pszPath]
0x180007c35  lea     rcx, [rbp+470h+var_468]
0x180007c39  call    ?GetLongPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetLongPath(std::wstring const &)
0x180007c3e  mov     rdx, rax
0x180007c41  lea     rcx, [rbp+470h+pszPath]
0x180007c45  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180007c4a  lea     rcx, [rbp+470h+var_468]
0x180007c4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007c53  lea     rdx, [rbp+470h+pszPath]
0x180007c57  mov     rcx, rsi
0x180007c5a  call    ?SetInstallLocation@Application@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::SetInstallLocation(std::wstring const &)
0x180007c5f  lea     rcx, [rsi+170h]
0x180007c66  lea     rdx, ?ApplicationTypeApplication@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationTypeApplication
0x180007c6d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180007c72  cmp     r15, 0FFFFFFFF80000002h
0x180007c79  jnz     short loc_180007CC4
0x180007c7b  lea     rcx, [rsi+150h]
0x180007c82  lea     rdx, ?ApplicationSourceAddRemoveProgram@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationSourceAddRemoveProgram
0x180007c89  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180007c8e  mov     r8, rdi
0x180007c91  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\"
0x180007c98  lea     rcx, [rbp+470h+var_468]
0x180007c9c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180007ca1  nop
0x180007ca2  lea     rcx, [rsi+1B0h]
0x180007ca9  mov     rdx, rax
0x180007cac  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180007cb1  nop
0x180007cb2  lea     rcx, [rbp+470h+var_468]
0x180007cb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180007cbb  lea     r14, [rsi+10h]
0x180007cbf  jmp     loc_180007DA6
0x180007cc4  mov     rbx, 0FFFFFFFF80000003h
0x180007ccb  cmp     r15, rbx
0x180007cce  jnz     loc_1800083C2
0x180007cd4  lea     r14, [rsi+10h]
0x180007cd8  mov     rax, [r14]
0x180007cdb  mov     rcx, r14
0x180007cde  mov     rax, [rax+28h]
0x180007ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce7  lea     rdx, ?SilverlightOutOfBrowserInstallPath@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::SilverlightOutOfBrowserInstallPath
0x180007cee  mov     rcx, rax
0x180007cf1  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV12@_K@Z; std::wstring::find(std::wstring const &,unsigned __int64)
0x180007cf6  lea     rcx, ?ApplicationSourceAddRemoveProgramPerUser@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ApplicationSourceAddRemoveProgramPerUser
  ... truncated ...
```
