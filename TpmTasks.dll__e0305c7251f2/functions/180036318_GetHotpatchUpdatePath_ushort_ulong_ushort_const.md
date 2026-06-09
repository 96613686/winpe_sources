# GetHotpatchUpdatePath(ushort *,ulong,ushort const *)

- ea: `0x180036318`
- end: `0x18003664e`
- name: `?GetHotpatchUpdatePath@@YAJPEAGKPEBG@Z`
- size: `822`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180037050`

## callees

- `0x1800078b0`
- `0x1800085d4`
- `0x18000e48c`
- `0x18001bd50`
- `0x18001bddc`
- `0x18001be20`
- `0x180024780`
- `0x180036318`
- `0x18003a068`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003647b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003657d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003647b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003657d`
- `api-ms-win-crt-private-l1-1-0!_o__wgetenv` at `0x18003644b`
- `api-ms-win-crt-private-l1-1-0!_o__wgetenv` at `0x18003644b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800365cb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800365cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800363f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800363f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036386`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036386`

## string_xrefs

- `0x1800363a7`: `GetHotpatchUpdatePath: Registry key not found, returning empty path`
- `0x1800363c3`: `GetHotpatchUpdatePath: RegOpenKeyEx failed with hr=0x%08x`
- `0x1800363eb`: `HotpatchDirectory`
- `0x18003640d`: `GetHotpatchUpdatePath: HotpatchDirectory registry value not found, returning empty path`
- `0x18003641a`: `GetHotpatchUpdatePath: RegQueryValueEx for HotpatchDirectory failed with hr=0x%08x`
- `0x180036426`: `GetHotpatchUpdatePath: HotpatchDirectory raw value: %s`
- `0x18003645f`: `GetHotpatchUpdatePath: SystemRoot environment variable is NULL`
- `0x1800364db`: `GetHotpatchUpdatePath: SystemRoot=%s`
- `0x180036512`: `GetHotpatchUpdatePath: Failed to build WinSXS path (buffer too small)`
- `0x180036489`: `GetHotpatchUpdatePath: Path starts with SYSTEMROOT_PREFIX, expanding`
- `0x1800364cf`: `GetHotpatchUpdatePath: Failed to expand SYSTEMROOT_PREFIX path (buffer too small)`
- `0x180036539`: `GetHotpatchUpdatePath: Failed to copy expanded path (buffer too small)`
- `0x180036545`: `GetHotpatchUpdatePath: Expanded path: %s`
- `0x180036553`: `GetHotpatchUpdatePath: Path does not start with SYSTEMROOT_PREFIX`
- `0x18003658f`: `GetHotpatchUpdatePath: Path '%s' does not start with trusted WinSXS prefix '%s', rejecting`
- `0x180036606`: `GetHotpatchUpdatePath: Failed to append filename '%s' to path (buffer too small)`
- `0x1800365dd`: `Hotpatch update file for %ls not found`
- `0x1800365f5`: `Hotpatch update path: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
__int64 __fastcall GetHotpatchUpdatePath(unsigned __int16 *a1, __int64 a2, const unsigned __int16 *a3)
{
  HKEY *phkResult; // rax
  LSTATUS v6; // eax
  signed int v7; // ebx
  LSTATUS v8; // eax
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v15[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v16[264]; // [rsp+250h] [rbp+150h] BYREF

  hKey = 0;
  cbData = 520;
  phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\SecureBoot\\Servicing\\Hotpatch",
         0,
         0x20019u,
         phkResult);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 == -2147024894 )
  {
    SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: Registry key not found, returning empty path");
LABEL_5:
    v7 = 0;
LABEL_6:
    *a1 = 0;
    goto LABEL_39;
  }
  if ( v7 < 0 )
  {
    SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: RegOpenKeyEx failed with hr=0x%08x", (unsigned int)v7);
    goto LABEL_39;
  }
  v8 = RegQueryValueExW(hKey, L"HotpatchDirectory", 0, 0, (LPBYTE)a1, &cbData);
  v7 = v8;
  if ( v8 > 0 )
    v7 = (unsigned __int16)v8 | 0x80070000;
  if ( v7 == -2147024894 )
  {
    SBServicingLogMessage(L"GetHotpatchUpdatePath: HotpatchDirectory registry value not found, returning empty path");
    goto LABEL_5;
  }
  if ( v7 < 0 )
  {
    SBServicingLogMessage(
      L"GetHotpatchUpdatePath: RegQueryValueEx for HotpatchDirectory failed with hr=0x%08x",
      (unsigned int)v7);
    goto LABEL_39;
  }
  SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: HotpatchDirectory raw value: %s", a1);
  memset_0(v15, 0, 0x208u);
  v9 = _o__wgetenv(L"SystemRoot");
  v10 = v9;
  if ( v9 )
  {
    SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: SystemRoot=%s", v9);
    if ( StringCchPrintfW(v15, 0x104u, L"%s%s", v10, L"\\WinSXS\\") < 0 )
    {
      SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: Failed to build WinSXS path (buffer too small)");
      goto LABEL_38;
    }
  }
  else
  {
    SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: SystemRoot environment variable is NULL");
  }
  if ( (unsigned int)_o__wcsnicmp(a1, L"\\systemroot", 11) )
  {
    SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: Path does not start with SYSTEMROOT_PREFIX");
  }
  else
  {
    SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: Path starts with SYSTEMROOT_PREFIX, expanding");
    memset_0(v16, 0, 0x208u);
    if ( StringCchPrintfW(v16, 0x104u, L"%s%s", v10, a1 + 11) < 0 )
    {
      SBServicingLogMessage(L"GetHotpatchUpdatePath: Failed to expand SYSTEMROOT_PREFIX path (buffer too small)");
LABEL_38:
      v7 = -2147024774;
      goto LABEL_39;
    }
    if ( StringCchCopyW(a1, 0x104u, v16) < 0 )
    {
      SBServicingLogMessage(L"GetHotpatchUpdatePath: Failed to copy expanded path (buffer too small)");
      goto LABEL_38;
    }
    SBServicingLogMessage((wchar_t *)L"GetHotpatchUpdatePath: Expanded path: %s", a1);
  }
  v11 = -1;
  do
    ++v11;
  while ( v15[v11] );
  if ( (unsigned int)_o__wcsnicmp(a1, v15, (unsigned int)v11) )
  {
    SBServicingLogMessage(
      (wchar_t *)L"GetHotpatchUpdatePath: Path '%s' does not start with trusted WinSXS prefix '%s', rejecting",
      a1,
      v15);
    goto LABEL_6;
  }
  if ( StringCchCatW(a1, 0x104u, L"\\") < 0 || StringCchCatW(a1, 0x104u, a3) < 0 )
  {
    SBServicingLogMessage(
      (wchar_t *)L"GetHotpatchUpdatePath: Failed to append filename '%s' to path (buffer too small)",
      a3);
    goto LABEL_38;
  }
  if ( GetFileAttributesW(a1) == -1 )
  {
    *a1 = 0;
    SBServicingLogMessage((wchar_t *)L"Hotpatch update file for %ls not found", a3);
    SetUpdateTriggerRegistryHotPatch(0);
  }
  else
  {
    SBServicingLogMessage((wchar_t *)L"Hotpatch update path: %s", a1);
  }
LABEL_39:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180036318  mov     [rsp-8+arg_8], rbx
0x18003631d  mov     [rsp-8+arg_18], rsi
0x180036322  push    rbp
0x180036323  push    rdi
0x180036324  push    r12
0x180036326  push    r14
0x180036328  push    r15
0x18003632a  lea     rbp, [rsp-370h]
0x180036332  sub     rsp, 470h
0x180036339  mov     rax, cs:__security_cookie
0x180036340  xor     rax, rsp
0x180036343  mov     [rbp+390h+var_30], rax
0x18003634a  mov     r14, r8
0x18003634d  mov     rdi, rcx
0x180036350  xor     r15d, r15d
0x180036353  mov     [rsp+490h+hKey], r15
0x180036358  mov     [rsp+490h+cbData], 208h
0x180036360  lea     rcx, [rsp+490h+hKey]
0x180036365  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18003636a  mov     [rsp+490h+phkResult], rax; phkResult
0x18003636f  mov     r9d, 20019h; samDesired
0x180036375  xor     r8d, r8d; ulOptions
0x180036378  lea     rdx, aSystemCurrentc_15; "SYSTEM\\CurrentControlSet\\Control\\Sec"...
0x18003637f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036386  call    cs:__imp_RegOpenKeyExW
0x18003638c  mov     ebx, eax
0x18003638e  mov     r12d, 80070000h
0x180036394  test    eax, eax
0x180036396  jle     short loc_18003639E
0x180036398  movzx   ebx, ax
0x18003639b  or      ebx, r12d
0x18003639e  mov     esi, 80070002h
0x1800363a3  cmp     ebx, esi
0x1800363a5  jnz     short loc_1800363BF
0x1800363a7  lea     rcx, aGethotpatchupd; "GetHotpatchUpdatePath: Registry key not"...
0x1800363ae  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800363b3  mov     ebx, r15d
0x1800363b6  mov     [rdi], r15w
0x1800363ba  jmp     loc_180036617
0x1800363bf  test    ebx, ebx
0x1800363c1  jns     short loc_1800363D6
0x1800363c3  lea     rcx, aGethotpatchupd_0; "GetHotpatchUpdatePath: RegOpenKeyEx fai"...
0x1800363ca  mov     edx, ebx
0x1800363cc  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800363d1  jmp     loc_180036617
0x1800363d6  lea     rax, [rsp+490h+cbData]
0x1800363db  mov     [rsp+490h+lpcbData], rax; lpcbData
0x1800363e0  mov     [rsp+490h+phkResult], rdi; lpData
0x1800363e5  xor     r9d, r9d; lpType
0x1800363e8  xor     r8d, r8d; lpReserved
0x1800363eb  lea     rdx, aHotpatchdirect; "HotpatchDirectory"
0x1800363f2  mov     rcx, [rsp+490h+hKey]; hKey
0x1800363f7  call    cs:__imp_RegQueryValueExW
0x1800363fd  mov     ebx, eax
0x1800363ff  test    eax, eax
0x180036401  jle     short loc_180036409
0x180036403  movzx   ebx, ax
0x180036406  or      ebx, r12d
0x180036409  cmp     ebx, esi
0x18003640b  jnz     short loc_180036416
0x18003640d  lea     rcx, aGethotpatchupd_2; "GetHotpatchUpdatePath: HotpatchDirector"...
0x180036414  jmp     short loc_1800363AE
0x180036416  test    ebx, ebx
0x180036418  jns     short loc_180036423
0x18003641a  lea     rcx, aGethotpatchupd_10; "GetHotpatchUpdatePath: RegQueryValueEx "...
0x180036421  jmp     short loc_1800363CA
0x180036423  mov     rdx, rdi
0x180036426  lea     rcx, aGethotpatchupd_8; "GetHotpatchUpdatePath: HotpatchDirector"...
0x18003642d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180036432  xor     edx, edx; Val
0x180036434  mov     r8d, 208h; Size
0x18003643a  lea     rcx, [rsp+490h+var_450]; void *
0x18003643f  call    memset_0
0x180036444  lea     rcx, aSystemroot; "SystemRoot"
0x18003644b  call    cs:__imp__o__wgetenv
0x180036451  mov     rsi, rax
0x180036454  mov     r12d, 104h
0x18003645a  test    rax, rax
0x18003645d  jnz     short loc_1800364D8
0x18003645f  lea     rcx, aGethotpatchupd_6; "GetHotpatchUpdatePath: SystemRoot envir"...
0x180036466  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003646b  mov     r8d, 0Bh
0x180036471  lea     rdx, aSystemroot_0; "\\systemroot"
0x180036478  mov     rcx, rdi
0x18003647b  call    cs:__imp__o__wcsnicmp
0x180036481  test    eax, eax
0x180036483  jnz     loc_180036553
0x180036489  lea     rcx, aGethotpatchupd_7; "GetHotpatchUpdatePath: Path starts with"...
0x180036490  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180036495  xor     edx, edx; Val
0x180036497  mov     r8d, 208h; Size
0x18003649d  lea     rcx, [rbp+390h+var_240]; void *
0x1800364a4  call    memset_0
0x1800364a9  lea     rax, [rdi+16h]
0x1800364ad  mov     [rsp+490h+phkResult], rax
0x1800364b2  mov     r9, rsi
0x1800364b5  lea     r8, aSS_0; "%s%s"
0x1800364bc  mov     rdx, r12; unsigned __int64
0x1800364bf  lea     rcx, [rbp+390h+var_240]; unsigned __int16 *
0x1800364c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800364cb  test    eax, eax
0x1800364cd  jns     short loc_180036523
0x1800364cf  lea     rcx, aGethotpatchupd_4; "GetHotpatchUpdatePath: Failed to expand"...
0x1800364d6  jmp     short loc_180036519
0x1800364d8  mov     rdx, rsi
0x1800364db  lea     rcx, aGethotpatchupd_13; "GetHotpatchUpdatePath: SystemRoot=%s"
0x1800364e2  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800364e7  lea     rax, aWinsxs; "\\WinSXS\\"
0x1800364ee  mov     [rsp+490h+phkResult], rax
0x1800364f3  mov     r9, rsi
0x1800364f6  lea     r8, aSS_0; "%s%s"
0x1800364fd  mov     rdx, r12; unsigned __int64
0x180036500  lea     rcx, [rsp+490h+var_450]; unsigned __int16 *
0x180036505  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003650a  test    eax, eax
0x18003650c  jns     loc_18003646B
0x180036512  lea     rcx, aGethotpatchupd_12; "GetHotpatchUpdatePath: Failed to build "...
0x180036519  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003651e  jmp     loc_180036612
0x180036523  lea     r8, [rbp+390h+var_240]; unsigned __int16 *
0x18003652a  mov     rdx, r12; unsigned __int64
0x18003652d  mov     rcx, rdi; unsigned __int16 *
0x180036530  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180036535  test    eax, eax
0x180036537  jns     short loc_180036542
0x180036539  lea     rcx, aGethotpatchupd_5; "GetHotpatchUpdatePath: Failed to copy e"...
0x180036540  jmp     short loc_180036519
0x180036542  mov     rdx, rdi
0x180036545  lea     rcx, aGethotpatchupd_3; "GetHotpatchUpdatePath: Expanded path: %"...
0x18003654c  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180036551  jmp     short loc_18003655F
0x180036553  lea     rcx, aGethotpatchupd_1; "GetHotpatchUpdatePath: Path does not st"...
0x18003655a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003655f  lea     rcx, [rsp+490h+var_450]
0x180036564  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036568  inc     rax
0x18003656b  cmp     [rcx+rax*2], r15w
0x180036570  jnz     short loc_180036568
0x180036572  mov     r8d, eax
0x180036575  lea     rdx, [rsp+490h+var_450]
0x18003657a  mov     rcx, rdi
0x18003657d  call    cs:__imp__o__wcsnicmp
0x180036583  test    eax, eax
0x180036585  jz      short loc_1800365A0
0x180036587  lea     r8, [rsp+490h+var_450]
0x18003658c  mov     rdx, rdi
0x18003658f  lea     rcx, aGethotpatchupd_11; "GetHotpatchUpdatePath: Path '%s' does n"...
0x180036596  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003659b  jmp     loc_1800363B6
0x1800365a0  lea     r8, asc_180066EF0; "\\"
0x1800365a7  mov     rdx, r12; unsigned __int64
0x1800365aa  mov     rcx, rdi; unsigned __int16 *
0x1800365ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800365b2  test    eax, eax
0x1800365b4  js      short loc_180036603
0x1800365b6  mov     r8, r14; unsigned __int16 *
0x1800365b9  mov     rdx, r12; unsigned __int64
0x1800365bc  mov     rcx, rdi; unsigned __int16 *
0x1800365bf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800365c4  test    eax, eax
0x1800365c6  js      short loc_180036603
0x1800365c8  mov     rcx, rdi; lpFileName
0x1800365cb  call    cs:__imp_GetFileAttributesW
0x1800365d1  cmp     eax, 0FFFFFFFFh
0x1800365d4  jnz     short loc_1800365F2
0x1800365d6  mov     [rdi], r15w
0x1800365da  mov     rdx, r14
0x1800365dd  lea     rcx, aHotpatchUpdate_0; "Hotpatch update file for %ls not found"
0x1800365e4  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800365e9  xor     ecx, ecx; unsigned int
0x1800365eb  call    ?SetUpdateTriggerRegistryHotPatch@@YAJK@Z; SetUpdateTriggerRegistryHotPatch(ulong)
0x1800365f0  jmp     short loc_180036617
0x1800365f2  mov     rdx, rdi
0x1800365f5  lea     rcx, aHotpatchUpdate; "Hotpatch update path: %s"
0x1800365fc  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180036601  jmp     short loc_180036617
0x180036603  mov     rdx, r14
0x180036606  lea     rcx, aGethotpatchupd_9; "GetHotpatchUpdatePath: Failed to append"...
0x18003660d  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180036612  mov     ebx, 8007007Ah
0x180036617  lea     rcx, [rsp+490h+hKey]
0x18003661c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180036621  mov     eax, ebx
0x180036623  mov     rcx, [rbp+390h+var_30]
0x18003662a  xor     rcx, rsp; StackCookie
0x18003662d  call    __security_check_cookie
0x180036632  lea     r11, [rsp+490h+var_20]
0x18003663a  mov     rbx, [r11+38h]
0x18003663e  mov     rsi, [r11+48h]
0x180036642  mov     rsp, r11
0x180036645  pop     r15
0x180036647  pop     r14
0x180036649  pop     r12
0x18003664b  pop     rdi
0x18003664c  pop     rbp
0x18003664d  retn
```
