# SrSettings::CSrSettings::Init(ushort const *,bool,SrtUtil::ILogCallback *,bool,bool)

- ea: `0x180049360`
- end: `0x180049a5a`
- name: `?Init@CSrSettings@SrSettings@@UEAAJPEBG_NPEAUILogCallback@SrtUtil@@11@Z`
- size: `1786`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *this, const unsigned __int16 *, char, struct SrtUtil::ILogCallback *, bool, bool)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, installer_update`

## callees

- `0x180002786`
- `0x180006120`
- `0x18000efb0`
- `0x180049360`
- `0x18004a3bc`
- `0x18004aacc`
- `0x18004ad20`
- `0x18004afc8`
- `0x18004c0e8`
- `0x18004c4ec`
- `0x18004c564`
- `0x18004c5c8`
- `0x18004c6a0`
- `0x18004c6c8`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004944a`
- `msvcrt!_wcsicmp` at `0x18004944a`
- `KERNEL32!GetLastError` at `0x1800493ed`
- `KERNEL32!GetLastError` at `0x1800495b2`
- `KERNEL32!GetLastError` at `0x1800493ed`
- `KERNEL32!GetLastError` at `0x1800495b2`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800493e3`
- `KERNEL32!GetWindowsDirectoryW` at `0x1800493e3`

## string_xrefs

- `0x1800493a7`: `CSrSettings already initialized`
- `0x180049402`: `Failed to get current OS path. Error: 0x%08x`
- `0x180049493`: `Failed to assign target OS path. Error: 0x%08x`
- `0x180049a16`: `UseInWinRE mode requires target OS path`
- `0x18004955f`: `UseInWinRE mode is enabled, treat as user mode as it's read only`
- `0x1800495c7`: `Failed to get WinRE config. Error: 0x%08x`
- `0x18004960f`: `Failed to assign WinRE installed location path. Error: 0x%08x`
- `0x180049644`: `Failed to append backslash to WinRE installed location path. Error: 0x%08x`
- `0x18004966e`: `Failed to append setting file name to WinRE installed location path. Error: 0x%08x`
- `0x1800496cd`: `No backup path, WinRE must be disabled, cannot use UseInWinRE mode`
- `0x1800496f1`: `Failed to assign backup settings file path to setting path. Error: 0x%08x`
- `0x1800497d6`: `Failed to assign target OS path to setting path. Error: 0x%08x`
- `0x180049774`: `\System32\LogFiles\Srt\SrSettings.TMP.ini`
- `0x18004978c`: `Failed to append temporary setting file name to target OS path. Error: 0x%08x`
- `0x1800497a8`: `Temporary settings file not found`
- `0x1800497e8`: `\System32\Recovery\SrSettings.ini`
- `0x180049804`: `Failed to append setting file name to target OS path. Error: 0x%08x`
- `0x180049726`: `Failed to assign target OS path to wifi setting file path. Error: 0x%08x`
- `0x180049816`: `\System32\Recovery\WifiSettings.ini`
- `0x180049831`: `Failed to append wifi setting file name to target OS path. Error: 0x%08x`
- `0x180049840`: `Settings file path: %s`
- `0x1800498a9`: `Failed to assign target OS path to test config file path. Error: 0x%08x`
- `0x1800498bb`: `\System32\Recovery\RecoverySimulation.ini`
- `0x1800498d6`: `Failed to append test config file name to target OS path. Error: 0x%08x`
- `0x1800498e6`: `Test config file: %s`
- `0x180049914`: `Test config file not present`
- `0x180049924`: `Test config file not found`
- `0x180049965`: `Failed to create setting file with empty settings. Error: 0x%08x`
- `0x18004999d`: `Failed to create wifi setting file with empty settings. Error: 0x%08x`
- `0x1800499ba`: `Failed to set ACL on wifi settings file. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::Init(
        SrSettings::CSrSettings *this,
        const unsigned __int16 *a2,
        char a3,
        struct SrtUtil::ILogCallback *a4,
        bool a5,
        bool a6)
{
  signed int LastError; // eax
  signed int v12; // edi
  const wchar_t *v13; // r8
  __int64 *v14; // rsi
  bool v15; // al
  __int64 v16; // r8
  __int64 v17; // r9
  const wchar_t *v18; // r14
  const wchar_t *v19; // r9
  const wchar_t *v20; // r9
  bool v21; // bp
  bool v22; // zf
  const unsigned __int16 *v23; // rcx
  signed int v24; // eax
  _WORD *v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rdx
  _QWORD *v28; // rdi
  _QWORD *v29; // r14
  const unsigned __int16 **v30; // r15
  char IsEnabled; // al
  __int64 v32; // rdx
  char *v33; // rcx
  __int64 v34; // r8
  _QWORD *v35; // r12
  int v36; // eax
  int v37; // eax
  _BYTE Src[3744]; // [rsp+30h] [rbp-10F8h] BYREF
  wchar_t Buffer[264]; // [rsp+ED0h] [rbp-258h] BYREF

  if ( *((_BYTE *)this + 3945) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"CSrSettings already initialized");
    return 2147942485LL;
  }
  memset_0(Buffer, 0, 0x208u);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    v13 = L"Failed to get current OS path. Error: 0x%08x";
    goto LABEL_7;
  }
  *((_BYTE *)this + 3944) = a3;
  if ( a2 )
  {
    v14 = (__int64 *)((char *)this + 8);
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            (char *)this + 8,
                            a2) )
    {
      v15 = _wcsicmp(a2, Buffer) == 0;
      goto LABEL_18;
    }
LABEL_16:
    v12 = -2147024888;
    v13 = L"Failed to assign target OS path. Error: 0x%08x";
LABEL_7:
    SrSettings::CSrSettings::Trace(this, 2, v13, (unsigned int)v12);
    return (unsigned int)v12;
  }
  if ( a3 )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"UseInWinRE mode requires target OS path");
    return 2147942487LL;
  }
  v16 = -1;
  do
    ++v16;
  while ( Buffer[v16] );
  v14 = (__int64 *)((char *)this + 8);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 8,
                           Buffer,
                           v16) )
    goto LABEL_16;
  v15 = 1;
LABEL_18:
  *((_BYTE *)this + 3946) = v15;
  memset_0(Src, 0, sizeof(Src));
  memcpy_0((char *)this + 200, Src, 0xEA0u);
  v17 = *v14;
  *((_QWORD *)this + 25) = 3744;
  *((_QWORD *)this + 494) = a4;
  SrSettings::CSrSettings::Trace(this, 0, L"Target OS: %s", v17);
  v18 = L"true";
  v19 = L"true";
  if ( !*((_BYTE *)this + 3944) )
    v19 = L"false";
  SrSettings::CSrSettings::Trace(this, 0, L"UseInWinRE: %s", v19);
  v20 = L"true";
  if ( !*((_BYTE *)this + 3946) )
    v20 = L"false";
  SrSettings::CSrSettings::Trace(this, 0, L"Online OS: %s", v20);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetImpl'::`2'::impl) )
  {
    v21 = a6;
    goto LABEL_31;
  }
  v22 = a3 == 0;
  v21 = a6;
  if ( v22 )
    goto LABEL_26;
  v22 = !a6;
  if ( !a6 )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"UseInWinRE mode is enabled, treat as user mode as it's read only");
    v21 = 1;
LABEL_26:
    v22 = !v21;
  }
  if ( v22 )
    v18 = L"false";
  SrSettings::CSrSettings::Trace(this, 0, L"User mode: %s", v18);
LABEL_31:
  v23 = 0;
  if ( !*((_BYTE *)this + 3944) )
    v23 = a2;
  if ( !(unsigned int)WinReGetConfig(v23, (char *)this + 200) )
  {
    v24 = GetLastError();
    v12 = v24;
    if ( v24 > 0 )
      v12 = (unsigned __int16)v24 | 0x80070000;
    v13 = L"Failed to get WinRE config. Error: 0x%08x";
    goto LABEL_7;
  }
  if ( *((_DWORD *)this + 52) )
  {
    v25 = (_WORD *)((char *)this + 832);
    if ( this != (SrSettings::CSrSettings *)-832LL )
    {
      if ( *v25 )
      {
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 (char *)this + 72,
                                 v25) )
        {
          v12 = -2147024888;
          v13 = L"Failed to assign WinRE installed location path. Error: 0x%08x";
          goto LABEL_7;
        }
        if ( *(_WORD *)(*((_QWORD *)this + 10) - 2LL) != 92
          && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 (char *)this + 72,
                                 L"\\",
                                 1) )
        {
          v12 = -2147024888;
          v13 = L"Failed to append backslash to WinRE installed location path. Error: 0x%08x";
          goto LABEL_7;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 (char *)this + 72,
                                 L"SrSettings.ini",
                                 14) )
        {
          v12 = -2147024888;
          v13 = L"Failed to append setting file name to WinRE installed location path. Error: 0x%08x";
          goto LABEL_7;
        }
      }
    }
  }
  if ( *((_BYTE *)this + 3944) )
  {
    if ( !*((_DWORD *)this + 52) )
    {
      SrSettings::CSrSettings::Trace(this, 2, L"WinRE is not available, cannot use UseInWinRE mode");
      return 2147942450LL;
    }
    if ( this == (SrSettings::CSrSettings *)-832LL || !*((_WORD *)this + 416) )
    {
      SrSettings::CSrSettings::Trace(this, 2, L"No WinRE location, cannot use UseInWinRE mode");
      return 2147942450LL;
    }
    v26 = *((_QWORD *)this + 10);
    v27 = *((_QWORD *)this + 9);
    if ( v27 == v26 )
    {
      SrSettings::CSrSettings::Trace(this, 2, L"No backup path, WinRE must be disabled, cannot use UseInWinRE mode");
      return 2147942450LL;
    }
    v28 = (_QWORD *)((char *)this + 40);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             (char *)this + 40,
                             v27,
                             (v26 - v27) >> 1) )
    {
      v12 = -2147024888;
      v13 = L"Failed to assign backup settings file path to setting path. Error: 0x%08x";
      goto LABEL_7;
    }
    v29 = v14 + 1;
    goto LABEL_58;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl'::`2'::impl);
  v32 = *v14;
  v29 = v14 + 1;
  v28 = (_QWORD *)((char *)this + 40);
  v33 = (char *)this + 40;
  v34 = (v14[1] - *v14) >> 1;
  if ( !IsEnabled )
    goto LABEL_67;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v33,
                           v32,
                           v34) )
  {
LABEL_68:
    v12 = -2147024888;
    v13 = L"Failed to assign target OS path to setting path. Error: 0x%08x";
    goto LABEL_7;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           (char *)this + 40,
                           L"\\System32\\LogFiles\\Srt\\SrSettings.TMP.ini",
                           41) )
  {
    v12 = -2147024888;
    v13 = L"Failed to append temporary setting file name to target OS path. Error: 0x%08x";
    goto LABEL_7;
  }
  if ( !(unsigned int)FileExists(*v28) )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Temporary settings file not found");
    v33 = (char *)this + 40;
    v32 = *v14;
    v34 = (*v29 - *v14) >> 1;
LABEL_67:
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v33,
                             v32,
                             v34) )
      goto LABEL_68;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             (char *)this + 40,
                             L"\\System32\\Recovery\\SrSettings.ini",
                             33) )
    {
      v12 = -2147024888;
      v13 = L"Failed to append setting file name to target OS path. Error: 0x%08x";
      goto LABEL_7;
    }
  }
LABEL_58:
  v30 = (const unsigned __int16 **)((char *)this + 104);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 104,
                           *v14,
                           (*v29 - *v14) >> 1) )
  {
    v12 = -2147024888;
    v13 = L"Failed to assign target OS path to wifi setting file path. Error: 0x%08x";
    goto LABEL_7;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           (char *)this + 104,
                           L"\\System32\\Recovery\\WifiSettings.ini",
                           35) )
  {
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to append wifi setting file name to target OS path. Error: 0x%08x",
      2147942408LL);
    return (unsigned int)v12;
  }
  SrSettings::CSrSettings::Trace(this, 0, L"Settings file path: %s", *v28);
  SrSettings::CSrSettings::Trace(this, 0, L"Backup setting file: %s", *((_QWORD *)this + 9));
  *((_BYTE *)this + 3947) = a5;
  if ( a5 )
    SrSettings::CSrSettings::Trace(this, 0, L"Test mode enabled");
  v35 = (_QWORD *)((char *)this + 136);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 136,
                           *v14,
                           (*v29 - *v14) >> 1) )
  {
    v12 = -2147024888;
    v13 = L"Failed to assign target OS path to test config file path. Error: 0x%08x";
    goto LABEL_7;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           (char *)this + 136,
                           L"\\System32\\Recovery\\RecoverySimulation.ini",
                           41) )
  {
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to append test config file name to target OS path. Error: 0x%08x",
      2147942408LL);
    return (unsigned int)v12;
  }
  SrSettings::CSrSettings::Trace(this, 0, L"Test config file: %s", *v35);
  if ( !(unsigned int)FileExists(*v35) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl'::`2'::impl) )
      SrSettings::CSrSettings::Trace(this, 0, L"Test config file not present");
    else
      SrSettings::CSrSettings::Trace(this, 1, L"Test config file not found");
  }
  v36 = FileExists(*v28);
  if ( v21 )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Running in user mode, so skip wifi settings");
  }
  else
  {
    if ( !v36 )
    {
      v12 = SrSettings::CSrSettings::SetSetting(this, L"Settings", 0, 0);
      if ( v12 < 0 )
      {
        v13 = L"Failed to create setting file with empty settings. Error: 0x%08x";
        goto LABEL_7;
      }
    }
    if ( !(unsigned int)FileExists(*v30) )
    {
      v12 = SrSettings::CSrSettings::SetSetting(this, *v30, L"WiFiCredential", 0, 0);
      if ( v12 < 0 )
      {
        v13 = L"Failed to create wifi setting file with empty settings. Error: 0x%08x";
        goto LABEL_7;
      }
    }
    v12 = SrSettings::CSrSettings::SetACL(this, *v30);
    if ( v12 < 0 )
    {
      v13 = L"Failed to set ACL on wifi settings file. Error: 0x%08x";
      goto LABEL_7;
    }
  }
  *((_BYTE *)this + 3945) = 1;
  SrSettings::CSrSettings::Trace(this, 0, L"Setting up default values for settings");
  v37 = SrSettings::CSrSettings::SetupDefaultValues(this);
  if ( v37 < 0 )
    SrSettings::CSrSettings::Trace(
      this,
      1,
      L"Failed to setup default values for settings. Error: 0x%08x",
      (unsigned int)v37);
  return 0;
}

```

## disassembly

```asm
0x180049360  mov     [rsp+arg_10], rbx
0x180049365  push    rbp
0x180049366  push    rsi
0x180049367  push    rdi
0x180049368  push    r12
0x18004936a  push    r13
0x18004936c  push    r14
0x18004936e  push    r15
0x180049370  mov     eax, 10F0h
0x180049375  call    _alloca_probe
0x18004937a  sub     rsp, rax
0x18004937d  mov     rax, cs:__security_cookie
0x180049384  xor     rax, rsp
0x180049387  mov     [rsp+1128h+var_48], rax
0x18004938f  xor     r13d, r13d
0x180049392  mov     r14, r9
0x180049395  mov     bpl, r8b
0x180049398  mov     rdi, rdx
0x18004939b  mov     rbx, rcx
0x18004939e  cmp     [rcx+0F69h], r13b
0x1800493a5  jz      short loc_1800493C1
0x1800493a7  lea     r8, aCsrsettingsAlr; "CSrSettings already initialized"
0x1800493ae  lea     edx, [r13+2]
0x1800493b2  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800493b7  mov     eax, 80070055h
0x1800493bc  jmp     loc_180049A2F
0x1800493c1  xor     edx, edx; Val
0x1800493c3  lea     rcx, [rsp+1128h+Buffer]; void *
0x1800493cb  mov     r8d, 208h; Size
0x1800493d1  call    memset_0
0x1800493d6  mov     edx, 104h; uSize
0x1800493db  lea     rcx, [rsp+1128h+Buffer]; lpBuffer
0x1800493e3  call    cs:__imp_GetWindowsDirectoryW
0x1800493e9  test    eax, eax
0x1800493eb  jnz     short loc_180049420
0x1800493ed  call    cs:__imp_GetLastError
0x1800493f3  mov     edi, eax
0x1800493f5  test    eax, eax
0x1800493f7  jle     short loc_180049402
0x1800493f9  movzx   edi, ax
0x1800493fc  or      edi, 80070000h
0x180049402  lea     r8, aFailedToGetCur_0; "Failed to get current OS path. Error: 0"...
0x180049409  mov     rcx, rbx
0x18004940c  mov     r9d, edi
0x18004940f  mov     edx, 2
0x180049414  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180049419  mov     eax, edi
0x18004941b  jmp     loc_180049A2F
0x180049420  mov     [rbx+0F68h], bpl
0x180049427  test    rdi, rdi
0x18004942a  jz      short loc_180049457
0x18004942c  lea     rsi, [rbx+8]
0x180049430  mov     rdx, rdi
0x180049433  mov     rcx, rsi
0x180049436  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x18004943b  test    al, al
0x18004943d  jz      short loc_18004948E
0x18004943f  lea     rdx, [rsp+1128h+Buffer]; String2
0x180049447  mov     rcx, rdi; String1
0x18004944a  call    cs:__imp__wcsicmp
0x180049450  test    eax, eax
0x180049452  setz    al
0x180049455  jmp     short loc_1800494A1
0x180049457  test    bpl, bpl
0x18004945a  jnz     loc_180049A16
0x180049460  lea     rax, [rsp+1128h+Buffer]
0x180049468  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004946c  inc     r8
0x18004946f  cmp     [rax+r8*2], r13w
0x180049474  jnz     short loc_18004946C
0x180049476  lea     rsi, [rbx+8]
0x18004947a  mov     rcx, rsi
0x18004947d  lea     rdx, [rsp+1128h+Buffer]
0x180049485  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004948a  test    al, al
0x18004948c  jnz     short loc_18004949F
0x18004948e  mov     edi, 80070008h
0x180049493  lea     r8, aFailedToAssign_14; "Failed to assign target OS path. Error:"...
0x18004949a  jmp     loc_180049409
0x18004949f  mov     al, 1
0x1800494a1  mov     r12d, 0EA0h
0x1800494a7  mov     [rbx+0F6Ah], al
0x1800494ad  mov     r8d, r12d; Size
0x1800494b0  lea     rcx, [rsp+1128h+Src]; void *
0x1800494b5  xor     edx, edx; Val
0x1800494b7  call    memset_0
0x1800494bc  lea     r15, [rbx+0C8h]
0x1800494c3  mov     r8d, r12d; Size
0x1800494c6  mov     rcx, r15; void *
0x1800494c9  lea     rdx, [rsp+1128h+Src]; Src
0x1800494ce  call    memcpy_0
0x1800494d3  mov     r9, [rsi]
0x1800494d6  lea     r8, aTargetOsS; "Target OS: %s"
0x1800494dd  xor     edx, edx
0x1800494df  mov     [r15], r12
0x1800494e2  mov     rcx, rbx
0x1800494e5  mov     [rbx+0F70h], r14
0x1800494ec  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800494f1  cmp     [rbx+0F68h], r13b
0x1800494f8  lea     r14, aTrue; "true"
0x1800494ff  mov     r9, r14
0x180049502  lea     r12, aFalse; "false"
0x180049509  cmovz   r9, r12
0x18004950d  lea     r8, aUseinwinreS; "UseInWinRE: %s"
0x180049514  xor     edx, edx
0x180049516  mov     rcx, rbx
0x180049519  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004951e  cmp     [rbx+0F6Ah], r13b
0x180049525  lea     r8, aOnlineOsS; "Online OS: %s"
0x18004952c  mov     r9, r14
0x18004952f  mov     rcx, rbx
0x180049532  cmovz   r9, r12
0x180049536  xor     edx, edx
0x180049538  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004953d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetImpl(void)'::`2'::impl
0x180049544  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::__private_IsEnabled(void)
0x180049549  test    al, al
0x18004954b  jz      short loc_180049590
0x18004954d  test    bpl, bpl
0x180049550  mov     bpl, [rsp+1128h+arg_28]
0x180049558  jz      short loc_180049573
0x18004955a  test    bpl, bpl
0x18004955d  jnz     short loc_180049576
0x18004955f  lea     r8, aUseinwinreMode_0; "UseInWinRE mode is enabled, treat as us"...
0x180049566  xor     edx, edx
0x180049568  mov     rcx, rbx
0x18004956b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180049570  mov     bpl, 1
0x180049573  test    bpl, bpl
0x180049576  cmovz   r14, r12
0x18004957a  lea     r8, aUserModeS; "User mode: %s"
0x180049581  mov     r9, r14
0x180049584  xor     edx, edx
0x180049586  mov     rcx, rbx
0x180049589  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004958e  jmp     short loc_180049598
0x180049590  mov     bpl, [rsp+1128h+arg_28]
0x180049598  cmp     [rbx+0F68h], r13b
0x18004959f  mov     rcx, r13
0x1800495a2  mov     rdx, r15
0x1800495a5  cmovz   rcx, rdi
0x1800495a9  call    WinReGetConfig
0x1800495ae  test    eax, eax
0x1800495b0  jnz     short loc_1800495D3
0x1800495b2  call    cs:__imp_GetLastError
0x1800495b8  mov     edi, eax
0x1800495ba  test    eax, eax
0x1800495bc  jle     short loc_1800495C7
0x1800495be  movzx   edi, ax
0x1800495c1  or      edi, 80070000h
0x1800495c7  lea     r8, aFailedToGetWin_9; "Failed to get WinRE config. Error: 0x%0"...
0x1800495ce  jmp     loc_180049409
0x1800495d3  cmp     [rbx+0D0h], r13d
0x1800495da  jz      loc_18004967A
0x1800495e0  lea     rdx, [rbx+340h]
0x1800495e7  test    rdx, rdx
0x1800495ea  jz      loc_18004967A
0x1800495f0  cmp     r13w, [rdx]
0x1800495f4  jz      loc_18004967A
0x1800495fa  lea     rdi, [rbx+48h]
0x1800495fe  mov     rcx, rdi
0x180049601  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180049606  test    al, al
0x180049608  jnz     short loc_18004961B
0x18004960a  mov     edi, 80070008h
0x18004960f  lea     r8, aFailedToAssign_7; "Failed to assign WinRE installed locati"...
0x180049616  jmp     loc_180049409
0x18004961b  mov     rax, [rbx+50h]
0x18004961f  cmp     word ptr [rax-2], 5Ch ; '\'
0x180049624  jz      short loc_180049650
0x180049626  mov     r8d, 1
0x18004962c  lea     rdx, pszSrc; "\\"
0x180049633  mov     rcx, rdi
0x180049636  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18004963b  test    al, al
0x18004963d  jnz     short loc_180049650
0x18004963f  mov     edi, 80070008h
0x180049644  lea     r8, aFailedToAppend_20; "Failed to append backslash to WinRE ins"...
0x18004964b  jmp     loc_180049409
0x180049650  mov     r8d, 0Eh
0x180049656  lea     rdx, aSrsettingsIni; "SrSettings.ini"
0x18004965d  mov     rcx, rdi
0x180049660  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180049665  test    al, al
0x180049667  jnz     short loc_18004967A
0x180049669  mov     edi, 80070008h
0x18004966e  lea     r8, aFailedToAppend_11; "Failed to append setting file name to W"...
0x180049675  jmp     loc_180049409
0x18004967a  cmp     [rbx+0F68h], r13b
0x180049681  jz      loc_18004973E
0x180049687  cmp     [rbx+0D0h], r13d
0x18004968e  jnz     short loc_1800496AE
0x180049690  lea     r8, aWinreIsNotAvai_1; "WinRE is not available, cannot use UseI"...
0x180049697  mov     edx, 2
0x18004969c  mov     rcx, rbx
0x18004969f  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800496a4  mov     eax, 80070032h
0x1800496a9  jmp     loc_180049A2F
0x1800496ae  lea     rcx, [rbx+340h]
0x1800496b5  test    rcx, rcx
0x1800496b8  jz      short loc_180049732
0x1800496ba  cmp     r13w, [rcx]
0x1800496be  jz      short loc_180049732
0x1800496c0  mov     r8, [rbx+50h]
0x1800496c4  mov     rdx, [rbx+48h]
0x1800496c8  cmp     rdx, r8
0x1800496cb  jnz     short loc_1800496D6
0x1800496cd  lea     r8, aNoBackupPathWi_0; "No backup path, WinRE must be disabled,"...
0x1800496d4  jmp     short loc_180049697
0x1800496d6  sub     r8, rdx
0x1800496d9  lea     rdi, [rbx+28h]
0x1800496dd  sar     r8, 1
0x1800496e0  mov     rcx, rdi
0x1800496e3  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800496e8  test    al, al
0x1800496ea  jnz     short loc_1800496FD
0x1800496ec  mov     edi, 80070008h
0x1800496f1  lea     r8, aFailedToAssign_4; "Failed to assign backup settings file p"...
0x1800496f8  jmp     loc_180049409
0x1800496fd  lea     r14, [rsi+8]
0x180049701  mov     r8, [r14]
0x180049704  lea     r15, [rbx+68h]
0x180049708  sub     r8, [rsi]
0x18004970b  mov     rcx, r15
0x18004970e  mov     rdx, [rsi]
0x180049711  sar     r8, 1
0x180049714  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180049719  test    al, al
0x18004971b  jnz     loc_180049810
0x180049721  mov     edi, 80070008h
0x180049726  lea     r8, aFailedToAssign; "Failed to assign target OS path to wifi"...
0x18004972d  jmp     loc_180049409
0x180049732  lea     r8, aNoWinreLocatio; "No WinRE location, cannot use UseInWinR"...
0x180049739  jmp     loc_180049697
0x18004973e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl(void)'::`2'::impl
0x180049745  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(void)
0x18004974a  mov     rdx, [rsi]
0x18004974d  lea     r14, [rsi+8]
0x180049751  mov     r8, [r14]
0x180049754  lea     rdi, [rbx+28h]
0x180049758  sub     r8, [rsi]
0x18004975b  mov     rcx, rdi
0x18004975e  sar     r8, 1
0x180049761  test    al, al
0x180049763  jz      short loc_1800497C8
0x180049765  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004976a  test    al, al
0x18004976c  jz      short loc_1800497D1
0x18004976e  mov     r8d, 29h ; ')'
0x180049774  lea     rdx, aSystem32Logfil; "\\System32\\LogFiles\\Srt\\SrSettings.T"...
0x18004977b  mov     rcx, rdi
0x18004977e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180049783  test    al, al
0x180049785  jnz     short loc_180049798
0x180049787  mov     edi, 80070008h
0x18004978c  lea     r8, aFailedToAppend_1; "Failed to append temporary setting file"...
0x180049793  jmp     loc_180049409
0x180049798  mov     rcx, [rdi]
0x18004979b  call    FileExists
0x1800497a0  test    eax, eax
0x1800497a2  jnz     loc_180049701
0x1800497a8  lea     r8, aTemporarySetti; "Temporary settings file not found"
0x1800497af  xor     edx, edx
0x1800497b1  mov     rcx, rbx
0x1800497b4  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x1800497b9  mov     r8, [r14]
0x1800497bc  mov     rcx, rdi
0x1800497bf  sub     r8, [rsi]
0x1800497c2  mov     rdx, [rsi]
0x1800497c5  sar     r8, 1
0x1800497c8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800497cd  test    al, al
0x1800497cf  jnz     short loc_1800497E2
0x1800497d1  mov     edi, 80070008h
0x1800497d6  lea     r8, aFailedToAssign_5; "Failed to assign target OS path to sett"...
0x1800497dd  jmp     loc_180049409
0x1800497e2  mov     r8d, 21h ; '!'
0x1800497e8  lea     rdx, aSystem32Recove_4; "\\System32\\Recovery\\SrSettings.ini"
0x1800497ef  mov     rcx, rdi
0x1800497f2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1800497f7  test    al, al
0x1800497f9  jnz     loc_180049701
0x1800497ff  mov     edi, 80070008h
0x180049804  lea     r8, aFailedToAppend_17; "Failed to append setting file name to t"...
0x18004980b  jmp     loc_180049409
0x180049810  mov     r8d, 23h ; '#'
0x180049816  lea     rdx, aSystem32Recove; "\\System32\\Recovery\\WifiSettings.ini"
0x18004981d  mov     rcx, r15
0x180049820  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x180049825  mov     rcx, rbx
0x180049828  test    al, al
0x18004982a  jnz     short loc_18004983D
0x18004982c  mov     edi, 80070008h
0x180049831  lea     r8, aFailedToAppend_19; "Failed to append wifi setting file name"...
0x180049838  jmp     loc_18004940C
0x18004983d  mov     r9, [rdi]
0x180049840  lea     r8, aSettingsFilePa; "Settings file path: %s"
0x180049847  xor     edx, edx
0x180049849  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004984e  mov     r9, [rbx+48h]
  ... truncated ...
```
