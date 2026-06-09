# SrSettings::CSrSettings::Init(ushort const *,bool,SrtUtil::ILogCallback *,bool,bool)

- ea: `0x18000b290`
- end: `0x18000b9a0`
- name: `?Init@CSrSettings@SrSettings@@UEAAJPEBG_NPEAUILogCallback@SrtUtil@@11@Z`
- size: `1808`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *this, const unsigned __int16 *, char, struct SrtUtil::ILogCallback *, bool, bool)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callees

- `0x180001d06`
- `0x18000b290`
- `0x18000e074`
- `0x18000ef08`
- `0x18000f418`
- `0x180010a0c`
- `0x180011840`
- `0x180011ac0`
- `0x180011b60`
- `0x180011c80`
- `0x180012d7c`
- `0x1800142d2`
- `0x180014310`
- `0x1800143d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000b38c`
- `msvcrt!_wcsicmp` at `0x18000b38c`
- `KERNEL32!GetLastError` at `0x18000b31e`
- `KERNEL32!GetLastError` at `0x18000b50a`
- `KERNEL32!GetLastError` at `0x18000b31e`
- `KERNEL32!GetLastError` at `0x18000b50a`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000b314`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000b314`
- `ReAgent!WinReGetConfig` at `0x18000b500`
- `ReAgent!WinReGetConfig` at `0x18000b500`

## string_xrefs

- `0x18000b2d7`: `CSrSettings already initialized`
- `0x18000b333`: `Failed to get current OS path. Error: 0x%08x`
- `0x18000b3d8`: `Failed to assign target OS path. Error: 0x%08x`
- `0x18000b95c`: `UseInWinRE mode requires target OS path`
- `0x18000b4af`: `UseInWinRE mode is enabled, treat as user mode as it's read only`
- `0x18000b51f`: `Failed to get WinRE config. Error: 0x%08x`
- `0x18000b574`: `Failed to assign WinRE installed location path. Error: 0x%08x`
- `0x18000b5a3`: `Failed to append backslash to WinRE installed location path. Error: 0x%08x`
- `0x18000b5c7`: `Failed to append setting file name to WinRE installed location path. Error: 0x%08x`
- `0x18000b626`: `No backup path, WinRE must be disabled, cannot use UseInWinRE mode`
- `0x18000b64a`: `Failed to assign backup settings file path to setting path. Error: 0x%08x`
- `0x18000b729`: `Failed to assign target OS path to setting path. Error: 0x%08x`
- `0x18000b6c7`: `\System32\LogFiles\Srt\SrSettings.TMP.ini`
- `0x18000b6df`: `Failed to append temporary setting file name to target OS path. Error: 0x%08x`
- `0x18000b6fb`: `Temporary settings file not found`
- `0x18000b735`: `\System32\Recovery\SrSettings.ini`
- `0x18000b751`: `Failed to append setting file name to target OS path. Error: 0x%08x`
- `0x18000b67f`: `Failed to assign target OS path to wifi setting file path. Error: 0x%08x`
- `0x18000b75d`: `\System32\Recovery\WifiSettings.ini`
- `0x18000b778`: `Failed to append wifi setting file name to target OS path. Error: 0x%08x`
- `0x18000b787`: `Settings file path: %s`
- `0x18000b7f0`: `Failed to assign target OS path to test config file path. Error: 0x%08x`
- `0x18000b7fc`: `\System32\Recovery\RecoverySimulation.ini`
- `0x18000b817`: `Failed to append test config file name to target OS path. Error: 0x%08x`
- `0x18000b827`: `Test config file: %s`
- `0x18000b855`: `Test config file not present`
- `0x18000b865`: `Test config file not found`
- `0x18000b8ab`: `Failed to create setting file with empty settings. Error: 0x%08x`
- `0x18000b8e3`: `Failed to create wifi setting file with empty settings. Error: 0x%08x`
- `0x18000b900`: `Failed to set ACL on wifi settings file. Error: 0x%08x`

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
  unsigned int v12; // edi
  __int64 v13; // rdi
  __int64 v14; // r8
  __int64 *v15; // rsi
  bool v16; // al
  __int64 v17; // r8
  __int64 v18; // r9
  const wchar_t *v19; // r15
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  bool v22; // bp
  bool v23; // zf
  const unsigned __int16 *v24; // rcx
  signed int v25; // eax
  _WORD *v26; // rdx
  __int64 v27; // rdx
  const unsigned __int16 **v28; // rdi
  const unsigned __int16 **v29; // r15
  char IsEnabled; // al
  __int64 v31; // rdx
  char *v32; // rcx
  _QWORD *v33; // r12
  int v34; // eax
  int v35; // eax
  _BYTE Src[3744]; // [rsp+30h] [rbp-10F8h] BYREF
  WCHAR Buffer[264]; // [rsp+ED0h] [rbp-258h] BYREF

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
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to get current OS path. Error: 0x%08x", v12);
    return v12;
  }
  *((_BYTE *)this + 3944) = a3;
  if ( a2 )
  {
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( a2[v14] );
    v15 = (__int64 *)((char *)this + 8);
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            (char *)this + 8,
                            a2) )
    {
      v16 = _wcsicmp(a2, Buffer) == 0;
      goto LABEL_19;
    }
LABEL_17:
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to assign target OS path. Error: 0x%08x", 2147942408LL);
    return v12;
  }
  if ( a3 )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"UseInWinRE mode requires target OS path");
    return 2147942487LL;
  }
  v13 = -1;
  v17 = -1;
  do
    ++v17;
  while ( Buffer[v17] );
  v15 = (__int64 *)((char *)this + 8);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 8,
                           Buffer) )
    goto LABEL_17;
  v16 = 1;
LABEL_19:
  *((_BYTE *)this + 3946) = v16;
  memset_0(Src, 0, sizeof(Src));
  memcpy_0((char *)this + 200, Src, 0xEA0u);
  v18 = *v15;
  *((_QWORD *)this + 25) = 3744;
  *((_QWORD *)this + 494) = a4;
  SrSettings::CSrSettings::Trace(this, 0, L"Target OS: %s", v18);
  v19 = L"true";
  v20 = L"true";
  if ( !*((_BYTE *)this + 3944) )
    v20 = L"false";
  SrSettings::CSrSettings::Trace(this, 0, L"UseInWinRE: %s", v20);
  v21 = L"true";
  if ( !*((_BYTE *)this + 3946) )
    v21 = L"false";
  SrSettings::CSrSettings::Trace(this, 0, L"Online OS: %s", v21);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetImpl'::`2'::impl) )
  {
    v22 = a6;
    goto LABEL_32;
  }
  v23 = a3 == 0;
  v22 = a6;
  if ( v23 )
    goto LABEL_27;
  v23 = !a6;
  if ( !a6 )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"UseInWinRE mode is enabled, treat as user mode as it's read only");
    v22 = 1;
LABEL_27:
    v23 = !v22;
  }
  if ( v23 )
    v19 = L"false";
  SrSettings::CSrSettings::Trace(this, 0, L"User mode: %s", v19);
LABEL_32:
  v24 = 0;
  if ( !*((_BYTE *)this + 3944) )
    v24 = a2;
  if ( !(unsigned int)WinReGetConfig(v24, (char *)this + 200) )
  {
    v25 = GetLastError();
    v12 = v25;
    if ( v25 > 0 )
      v12 = (unsigned __int16)v25 | 0x80070000;
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to get WinRE config. Error: 0x%08x", v12);
    return v12;
  }
  if ( *((_DWORD *)this + 52) )
  {
    v26 = (_WORD *)((char *)this + 832);
    if ( this != (SrSettings::CSrSettings *)-832LL )
    {
      if ( *v26 )
      {
        do
          ++v13;
        while ( v26[v13] );
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 (char *)this + 72,
                                 v26) )
        {
          v12 = -2147024888;
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to assign WinRE installed location path. Error: 0x%08x",
            2147942408LL);
          return v12;
        }
        if ( *(_WORD *)(*((_QWORD *)this + 10) - 2LL) != 92
          && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 (char *)this + 72,
                                 L"\\") )
        {
          v12 = -2147024888;
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to append backslash to WinRE installed location path. Error: 0x%08x",
            2147942408LL);
          return v12;
        }
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                                 (char *)this + 72,
                                 L"SrSettings.ini") )
        {
          v12 = -2147024888;
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to append setting file name to WinRE installed location path. Error: 0x%08x",
            2147942408LL);
          return v12;
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
    v27 = *((_QWORD *)this + 9);
    if ( v27 == *((_QWORD *)this + 10) )
    {
      SrSettings::CSrSettings::Trace(this, 2, L"No backup path, WinRE must be disabled, cannot use UseInWinRE mode");
      return 2147942450LL;
    }
    v28 = (const unsigned __int16 **)((char *)this + 40);
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             (char *)this + 40,
                             v27) )
    {
      v12 = -2147024888;
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to assign backup settings file path to setting path. Error: 0x%08x",
        2147942408LL);
      return v12;
    }
    goto LABEL_59;
  }
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl'::`2'::impl);
  v31 = *v15;
  v28 = (const unsigned __int16 **)((char *)this + 40);
  v32 = (char *)this + 40;
  if ( !IsEnabled )
    goto LABEL_68;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v32,
                           v31) )
  {
LABEL_69:
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to assign target OS path to setting path. Error: 0x%08x",
      2147942408LL);
    return v12;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           (char *)this + 40,
                           L"\\System32\\LogFiles\\Srt\\SrSettings.TMP.ini") )
  {
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to append temporary setting file name to target OS path. Error: 0x%08x",
      2147942408LL);
    return v12;
  }
  if ( !(unsigned int)FileExists(*v28) )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Temporary settings file not found");
    v32 = (char *)this + 40;
    v31 = *v15;
LABEL_68:
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             v32,
                             v31) )
      goto LABEL_69;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             (char *)this + 40,
                             L"\\System32\\Recovery\\SrSettings.ini") )
    {
      v12 = -2147024888;
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to append setting file name to target OS path. Error: 0x%08x",
        2147942408LL);
      return v12;
    }
  }
LABEL_59:
  v29 = (const unsigned __int16 **)((char *)this + 104);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 104,
                           *v15) )
  {
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to assign target OS path to wifi setting file path. Error: 0x%08x",
      2147942408LL);
    return v12;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           (char *)this + 104,
                           L"\\System32\\Recovery\\WifiSettings.ini") )
  {
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to append wifi setting file name to target OS path. Error: 0x%08x",
      2147942408LL);
    return v12;
  }
  SrSettings::CSrSettings::Trace(this, 0, L"Settings file path: %s", *v28);
  SrSettings::CSrSettings::Trace(this, 0, L"Backup setting file: %s", *((_QWORD *)this + 9));
  *((_BYTE *)this + 3947) = a5;
  if ( a5 )
    SrSettings::CSrSettings::Trace(this, 0, L"Test mode enabled");
  v33 = (_QWORD *)((char *)this + 136);
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 136,
                           *v15) )
  {
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to assign target OS path to test config file path. Error: 0x%08x",
      2147942408LL);
    return v12;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           (char *)this + 136,
                           L"\\System32\\Recovery\\RecoverySimulation.ini") )
  {
    v12 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to append test config file name to target OS path. Error: 0x%08x",
      2147942408LL);
    return v12;
  }
  SrSettings::CSrSettings::Trace(this, 0, L"Test config file: %s", *v33);
  if ( !(unsigned int)FileExists(*v33) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl'::`2'::impl) )
      SrSettings::CSrSettings::Trace(this, 0, L"Test config file not present");
    else
      SrSettings::CSrSettings::Trace(this, 1, L"Test config file not found");
  }
  v34 = FileExists(*v28);
  if ( v22 )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"Running in user mode, so skip wifi settings");
  }
  else
  {
    if ( !v34 )
    {
      v12 = SrSettings::CSrSettings::SetSetting(this, *v28, L"Settings", 0, 0);
      if ( (v12 & 0x80000000) != 0 )
      {
        SrSettings::CSrSettings::Trace(
          this,
          2,
          L"Failed to create setting file with empty settings. Error: 0x%08x",
          v12);
        return v12;
      }
    }
    if ( !(unsigned int)FileExists(*v29) )
    {
      v12 = SrSettings::CSrSettings::SetSetting(this, *v29, L"WiFiCredential", 0, 0);
      if ( (v12 & 0x80000000) != 0 )
      {
        SrSettings::CSrSettings::Trace(
          this,
          2,
          L"Failed to create wifi setting file with empty settings. Error: 0x%08x",
          v12);
        return v12;
      }
    }
    v12 = SrSettings::CSrSettings::SetACL(this, (WCHAR *)*v29);
    if ( (v12 & 0x80000000) != 0 )
    {
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to set ACL on wifi settings file. Error: 0x%08x", v12);
      return v12;
    }
  }
  *((_BYTE *)this + 3945) = 1;
  SrSettings::CSrSettings::Trace(this, 0, L"Setting up default values for settings");
  v35 = SrSettings::CSrSettings::SetupDefaultValues(this);
  if ( v35 < 0 )
    SrSettings::CSrSettings::Trace(
      this,
      1,
      L"Failed to setup default values for settings. Error: 0x%08x",
      (unsigned int)v35);
  return 0;
}

```

## disassembly

```asm
0x18000b290  mov     [rsp+arg_10], rbx
0x18000b295  push    rbp
0x18000b296  push    rsi
0x18000b297  push    rdi
0x18000b298  push    r12
0x18000b29a  push    r13
0x18000b29c  push    r14
0x18000b29e  push    r15
0x18000b2a0  mov     eax, 10F0h
0x18000b2a5  call    _alloca_probe
0x18000b2aa  sub     rsp, rax
0x18000b2ad  mov     rax, cs:__security_cookie
0x18000b2b4  xor     rax, rsp
0x18000b2b7  mov     [rsp+1128h+var_48], rax
0x18000b2bf  xor     r12d, r12d
0x18000b2c2  mov     r15, r9
0x18000b2c5  mov     bpl, r8b
0x18000b2c8  mov     r14, rdx
0x18000b2cb  mov     rbx, rcx
0x18000b2ce  cmp     [rcx+0F69h], r12b
0x18000b2d5  jz      short loc_18000B2F2
0x18000b2d7  lea     r8, aCsrsettingsAlr; "CSrSettings already initialized"
0x18000b2de  lea     edx, [r12+2]
0x18000b2e3  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b2e8  mov     eax, 80070055h
0x18000b2ed  jmp     loc_18000B975
0x18000b2f2  xor     edx, edx; Val
0x18000b2f4  lea     rcx, [rsp+1128h+Buffer]; void *
0x18000b2fc  mov     r8d, 208h; Size
0x18000b302  call    memset_0
0x18000b307  mov     edx, 104h; uSize
0x18000b30c  lea     rcx, [rsp+1128h+Buffer]; lpBuffer
0x18000b314  call    cs:__imp_GetWindowsDirectoryW
0x18000b31a  test    eax, eax
0x18000b31c  jnz     short loc_18000B351
0x18000b31e  call    cs:__imp_GetLastError
0x18000b324  mov     edi, eax
0x18000b326  test    eax, eax
0x18000b328  jle     short loc_18000B333
0x18000b32a  movzx   edi, ax
0x18000b32d  or      edi, 80070000h
0x18000b333  lea     r8, aFailedToGetCur; "Failed to get current OS path. Error: 0"...
0x18000b33a  mov     rcx, rbx
0x18000b33d  mov     r9d, edi
0x18000b340  mov     edx, 2
0x18000b345  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b34a  mov     eax, edi
0x18000b34c  jmp     loc_18000B975
0x18000b351  mov     [rbx+0F68h], bpl
0x18000b358  test    r14, r14
0x18000b35b  jz      short loc_18000B399
0x18000b35d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b361  mov     r8, rdi
0x18000b364  inc     r8
0x18000b367  cmp     [r14+r8*2], r12w
0x18000b36c  jnz     short loc_18000B364
0x18000b36e  lea     rsi, [rbx+8]
0x18000b372  mov     rdx, r14
0x18000b375  mov     rcx, rsi
0x18000b378  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b37d  test    al, al
0x18000b37f  jz      short loc_18000B3D3
0x18000b381  lea     rdx, [rsp+1128h+Buffer]; String2
0x18000b389  mov     rcx, r14; String1
0x18000b38c  call    cs:__imp__wcsicmp
0x18000b392  test    eax, eax
0x18000b394  setz    al
0x18000b397  jmp     short loc_18000B3E6
0x18000b399  test    bpl, bpl
0x18000b39c  jnz     loc_18000B95C
0x18000b3a2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b3a6  lea     rax, [rsp+1128h+Buffer]
0x18000b3ae  mov     r8, rdi
0x18000b3b1  inc     r8
0x18000b3b4  cmp     [rax+r8*2], r12w
0x18000b3b9  jnz     short loc_18000B3B1
0x18000b3bb  lea     rsi, [rbx+8]
0x18000b3bf  mov     rcx, rsi
0x18000b3c2  lea     rdx, [rsp+1128h+Buffer]
0x18000b3ca  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b3cf  test    al, al
0x18000b3d1  jnz     short loc_18000B3E4
0x18000b3d3  mov     edi, 80070008h
0x18000b3d8  lea     r8, aFailedToAssign_14; "Failed to assign target OS path. Error:"...
0x18000b3df  jmp     loc_18000B33A
0x18000b3e4  mov     al, 1
0x18000b3e6  mov     r13d, 0EA0h
0x18000b3ec  mov     [rbx+0F6Ah], al
0x18000b3f2  mov     r8d, r13d; Size
0x18000b3f5  lea     rcx, [rsp+1128h+Src]; void *
0x18000b3fa  xor     edx, edx; Val
0x18000b3fc  call    memset_0
0x18000b401  lea     r12, [rbx+0C8h]
0x18000b408  mov     r8d, r13d; Size
0x18000b40b  mov     rcx, r12; void *
0x18000b40e  lea     rdx, [rsp+1128h+Src]; Src
0x18000b413  call    memcpy_0
0x18000b418  mov     r9, [rsi]
0x18000b41b  lea     r8, aTargetOsS; "Target OS: %s"
0x18000b422  xor     edx, edx
0x18000b424  mov     [r12], r13
0x18000b428  mov     rcx, rbx
0x18000b42b  mov     [rbx+0F70h], r15
0x18000b432  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b437  lea     rax, aFalse; "false"
0x18000b43e  xor     r13d, r13d
0x18000b441  cmp     [rbx+0F68h], r13b
0x18000b448  lea     r15, aTrue; "true"
0x18000b44f  mov     r9, r15
0x18000b452  lea     r8, aUseinwinreS; "UseInWinRE: %s"
0x18000b459  cmovz   r9, rax
0x18000b45d  mov     rcx, rbx
0x18000b460  xor     edx, edx
0x18000b462  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b467  cmp     [rbx+0F6Ah], r13b
0x18000b46e  lea     rax, aFalse; "false"
0x18000b475  mov     r9, r15
0x18000b478  lea     r8, aOnlineOsS; "Online OS: %s"
0x18000b47f  cmovz   r9, rax
0x18000b483  mov     rcx, rbx
0x18000b486  xor     edx, edx
0x18000b488  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b48d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::GetImpl(void)'::`2'::impl
0x18000b494  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRInWinREFailWithNoIni>::__private_IsEnabled(void)
0x18000b499  test    al, al
0x18000b49b  jz      short loc_18000B4E7
0x18000b49d  test    bpl, bpl
0x18000b4a0  mov     bpl, [rsp+1128h+arg_28]
0x18000b4a8  jz      short loc_18000B4C3
0x18000b4aa  test    bpl, bpl
0x18000b4ad  jnz     short loc_18000B4C6
0x18000b4af  lea     r8, aUseinwinreMode_0; "UseInWinRE mode is enabled, treat as us"...
0x18000b4b6  xor     edx, edx
0x18000b4b8  mov     rcx, rbx
0x18000b4bb  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b4c0  mov     bpl, 1
0x18000b4c3  test    bpl, bpl
0x18000b4c6  lea     rax, aFalse; "false"
0x18000b4cd  mov     rcx, rbx
0x18000b4d0  cmovz   r15, rax
0x18000b4d4  lea     r8, aUserModeS; "User mode: %s"
0x18000b4db  mov     r9, r15
0x18000b4de  xor     edx, edx
0x18000b4e0  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b4e5  jmp     short loc_18000B4EF
0x18000b4e7  mov     bpl, [rsp+1128h+arg_28]
0x18000b4ef  cmp     [rbx+0F68h], r13b
0x18000b4f6  mov     rcx, r13
0x18000b4f9  mov     rdx, r12
0x18000b4fc  cmovz   rcx, r14
0x18000b500  call    cs:__imp_WinReGetConfig
0x18000b506  test    eax, eax
0x18000b508  jnz     short loc_18000B52B
0x18000b50a  call    cs:__imp_GetLastError
0x18000b510  mov     edi, eax
0x18000b512  test    eax, eax
0x18000b514  jle     short loc_18000B51F
0x18000b516  movzx   edi, ax
0x18000b519  or      edi, 80070000h
0x18000b51f  lea     r8, aFailedToGetWin; "Failed to get WinRE config. Error: 0x%0"...
0x18000b526  jmp     loc_18000B33A
0x18000b52b  cmp     [rbx+0D0h], r13d
0x18000b532  jz      loc_18000B5D3
0x18000b538  lea     rdx, [rbx+340h]
0x18000b53f  test    rdx, rdx
0x18000b542  jz      loc_18000B5D3
0x18000b548  cmp     r13w, [rdx]
0x18000b54c  jz      loc_18000B5D3
0x18000b552  inc     rdi
0x18000b555  cmp     [rdx+rdi*2], r13w
0x18000b55a  jnz     short loc_18000B552
0x18000b55c  lea     r14, [rbx+48h]
0x18000b560  mov     r8, rdi
0x18000b563  mov     rcx, r14
0x18000b566  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b56b  test    al, al
0x18000b56d  jnz     short loc_18000B580
0x18000b56f  mov     edi, 80070008h
0x18000b574  lea     r8, aFailedToAssign_7; "Failed to assign WinRE installed locati"...
0x18000b57b  jmp     loc_18000B33A
0x18000b580  mov     rax, [rbx+50h]
0x18000b584  cmp     word ptr [rax-2], 5Ch ; '\'
0x18000b589  jz      short loc_18000B5AF
0x18000b58b  lea     rdx, pszSrc; "\\"
0x18000b592  mov     rcx, r14
0x18000b595  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000b59a  test    al, al
0x18000b59c  jnz     short loc_18000B5AF
0x18000b59e  mov     edi, 80070008h
0x18000b5a3  lea     r8, aFailedToAppend_11; "Failed to append backslash to WinRE ins"...
0x18000b5aa  jmp     loc_18000B33A
0x18000b5af  lea     rdx, aSrsettingsIni; "SrSettings.ini"
0x18000b5b6  mov     rcx, r14
0x18000b5b9  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000b5be  test    al, al
0x18000b5c0  jnz     short loc_18000B5D3
0x18000b5c2  mov     edi, 80070008h
0x18000b5c7  lea     r8, aFailedToAppend_6; "Failed to append setting file name to W"...
0x18000b5ce  jmp     loc_18000B33A
0x18000b5d3  cmp     [rbx+0F68h], r13b
0x18000b5da  jz      loc_18000B697
0x18000b5e0  cmp     [rbx+0D0h], r13d
0x18000b5e7  jnz     short loc_18000B607
0x18000b5e9  lea     r8, aWinreIsNotAvai; "WinRE is not available, cannot use UseI"...
0x18000b5f0  mov     edx, 2
0x18000b5f5  mov     rcx, rbx
0x18000b5f8  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b5fd  mov     eax, 80070032h
0x18000b602  jmp     loc_18000B975
0x18000b607  lea     rcx, [rbx+340h]
0x18000b60e  test    rcx, rcx
0x18000b611  jz      short loc_18000B68B
0x18000b613  cmp     r13w, [rcx]
0x18000b617  jz      short loc_18000B68B
0x18000b619  mov     r8, [rbx+50h]
0x18000b61d  mov     rdx, [rbx+48h]
0x18000b621  cmp     rdx, r8
0x18000b624  jnz     short loc_18000B62F
0x18000b626  lea     r8, aNoBackupPathWi_0; "No backup path, WinRE must be disabled,"...
0x18000b62d  jmp     short loc_18000B5F0
0x18000b62f  sub     r8, rdx
0x18000b632  lea     rdi, [rbx+28h]
0x18000b636  sar     r8, 1
0x18000b639  mov     rcx, rdi
0x18000b63c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b641  test    al, al
0x18000b643  jnz     short loc_18000B656
0x18000b645  mov     edi, 80070008h
0x18000b64a  lea     r8, aFailedToAssign_4; "Failed to assign backup settings file p"...
0x18000b651  jmp     loc_18000B33A
0x18000b656  lea     r14, [rsi+8]
0x18000b65a  mov     r8, [r14]
0x18000b65d  lea     r15, [rbx+68h]
0x18000b661  sub     r8, [rsi]
0x18000b664  mov     rcx, r15
0x18000b667  mov     rdx, [rsi]
0x18000b66a  sar     r8, 1
0x18000b66d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b672  test    al, al
0x18000b674  jnz     loc_18000B75D
0x18000b67a  mov     edi, 80070008h
0x18000b67f  lea     r8, aFailedToAssign; "Failed to assign target OS path to wifi"...
0x18000b686  jmp     loc_18000B33A
0x18000b68b  lea     r8, aNoWinreLocatio; "No WinRE location, cannot use UseInWinR"...
0x18000b692  jmp     loc_18000B5F0
0x18000b697  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::GetImpl(void)'::`2'::impl
0x18000b69e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_RemoteManagement>::__private_IsEnabled(void)
0x18000b6a3  mov     rdx, [rsi]
0x18000b6a6  lea     r14, [rsi+8]
0x18000b6aa  mov     r8, [r14]
0x18000b6ad  lea     rdi, [rbx+28h]
0x18000b6b1  sub     r8, [rsi]
0x18000b6b4  mov     rcx, rdi
0x18000b6b7  sar     r8, 1
0x18000b6ba  test    al, al
0x18000b6bc  jz      short loc_18000B71B
0x18000b6be  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b6c3  test    al, al
0x18000b6c5  jz      short loc_18000B724
0x18000b6c7  lea     rdx, aSystem32Logfil; "\\System32\\LogFiles\\Srt\\SrSettings.T"...
0x18000b6ce  mov     rcx, rdi
0x18000b6d1  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000b6d6  test    al, al
0x18000b6d8  jnz     short loc_18000B6EB
0x18000b6da  mov     edi, 80070008h
0x18000b6df  lea     r8, aFailedToAppend_1; "Failed to append temporary setting file"...
0x18000b6e6  jmp     loc_18000B33A
0x18000b6eb  mov     rcx, [rdi]
0x18000b6ee  call    FileExists
0x18000b6f3  test    eax, eax
0x18000b6f5  jnz     loc_18000B65A
0x18000b6fb  lea     r8, aTemporarySetti; "Temporary settings file not found"
0x18000b702  xor     edx, edx
0x18000b704  mov     rcx, rbx
0x18000b707  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000b70c  mov     r8, [r14]
0x18000b70f  mov     rcx, rdi
0x18000b712  sub     r8, [rsi]
0x18000b715  mov     rdx, [rsi]
0x18000b718  sar     r8, 1
0x18000b71b  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000b720  test    al, al
0x18000b722  jnz     short loc_18000B735
0x18000b724  mov     edi, 80070008h
0x18000b729  lea     r8, aFailedToAssign_5; "Failed to assign target OS path to sett"...
0x18000b730  jmp     loc_18000B33A
0x18000b735  lea     rdx, aSystem32Recove_1; "\\System32\\Recovery\\SrSettings.ini"
0x18000b73c  mov     rcx, rdi
0x18000b73f  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000b744  test    al, al
0x18000b746  jnz     loc_18000B65A
0x18000b74c  mov     edi, 80070008h
0x18000b751  lea     r8, aFailedToAppend_9; "Failed to append setting file name to t"...
0x18000b758  jmp     loc_18000B33A
0x18000b75d  lea     rdx, aSystem32Recove; "\\System32\\Recovery\\WifiSettings.ini"
0x18000b764  mov     rcx, r15
0x18000b767  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000b76c  mov     rcx, rbx
0x18000b76f  test    al, al
0x18000b771  jnz     short loc_18000B784
  ... truncated ...
```
