# ChangeUserAndSystemMuiLanguageInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort,Windows::Internal::SET_DISPLAY_LANGUAGE_OPTIONS)

- ea: `0x1800136c8`
- end: `0x180013a88`
- name: `?ChangeUserAndSystemMuiLanguageInternal@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@GW4SET_DISPLAY_LANGUAGE_OPTIONS@Internal@Windows@@@Z`
- size: `960`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800190bc`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x180008294`
- `0x180008870`
- `0x1800088b4`
- `0x180011428`
- `0x1800136c8`
- `0x18001617c`
- `0x180018bec`
- `0x180018c10`
- `0x18001b044`
- `0x18001d3e4`
- `0x18001d564`
- `0x18001ebcc`

## import_xrefs

- `ntdll!RtlpSetPreferredUILanguages` at `0x1800137c1`
- `ntdll!RtlpSetPreferredUILanguages` at `0x1800137fd`
- `ntdll!RtlpSetPreferredUILanguages` at `0x1800137c1`
- `ntdll!RtlpSetPreferredUILanguages` at `0x1800137fd`
- `ntdll!NtSetDefaultUILanguage` at `0x180013a21`
- `ntdll!NtSetDefaultUILanguage` at `0x180013a21`
- `ntdll!NtGetMUIRegistryInfo` at `0x180013a42`
- `ntdll!NtGetMUIRegistryInfo` at `0x180013a42`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001384a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001384a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013993`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800139e6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013993`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800139e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800138a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001393a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800138a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001393a`

## string_xrefs

- `0x180013755`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x1800138d6`: `onecoreuap\base\globalization\coreglobconfig\src\coreglobconfig.cpp`
- `0x18001387e`: `PreviousInstallLanguage`
- `0x180013974`: `PreviousInstallLanguage`
- `0x18001391b`: `InstallLanguage`
- `0x1800139bf`: `InstallLanguage`

## pseudocode

```c
int __fastcall ChangeUserAndSystemMuiLanguageInternal(__int64 a1, unsigned __int16 a2, char a3)
{
  unsigned int v4; // esi
  const unsigned __int16 *v5; // rax
  int v6; // ebx
  __int64 v7; // rdx
  int v9; // eax
  unsigned int v10; // r8d
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  __int64 v14; // rdx
  LSTATUS ValueW; // eax
  unsigned int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rdx
  LSTATUS v19; // eax
  NTSTATUS v20; // eax
  void *v21; // rdx
  unsigned int v22; // r8d
  int MUIRegistryInfo; // eax
  unsigned int v24; // r8d
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  size_t pcchLength; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t psz[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+68h] [rbp-98h]
  unsigned __int16 v34[88]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[176]; // [rsp+120h] [rbp+20h] BYREF
  _WORD pvData[88]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = a2;
  v28 = 0;
  memset_0(v34, 0, 0xAAu);
  pcchLength = 0;
  *(_QWORD *)psz = 0;
  v33 = 0;
  v5 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v6 = StringCchCopyW(v34, 0x55u, v5);
  if ( v6 < 0 )
  {
    v7 = 748;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
      (const char *)(unsigned int)v6,
      phkResult);
    return v6;
  }
  v6 = StringCchPrintfW(psz, 6u, L"%.4x", v4);
  if ( v6 < 0 )
  {
    v7 = 749;
    goto LABEL_3;
  }
  v6 = StringLengthWorkerW(psz, 6u, &pcchLength);
  if ( v6 < 0 )
  {
    v7 = 750;
    goto LABEL_3;
  }
  v9 = RtlpSetPreferredUILanguages(18568, v34, &v28);
  if ( v9 < 0 )
  {
    v11 = 758;
    return wil::details::in1diag3::Return_NtStatus(retaddr, (void *)v11, v10, (const char *)(unsigned int)v9, phkResult);
  }
  if ( (a3 & 2) == 0 )
  {
    v9 = RtlpSetPreferredUILanguages(10376, v34, &v28);
    if ( v9 < 0 )
    {
      v11 = 766;
      return wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v11,
               v10,
               (const char *)(unsigned int)v9,
               phkResult);
    }
  }
  if ( (a3 & 4) == 0 )
    goto LABEL_43;
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\NLS\\Language", 0, 0x2001Fu, &hkey);
  if ( v12 )
  {
    v14 = 778;
LABEL_40:
    v6 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v14, v13, (const char *)v12, phkResult);
    goto LABEL_41;
  }
  memset_0(pvData, 0, 0xAAu);
  pcbData = 170;
  ValueW = RegGetValueW(hkey, 0, L"PreviousInstallLanguage", 2u, 0, pvData, &pcbData);
  v6 = ValueW;
  if ( ValueW )
  {
    if ( ValueW != 2 )
    {
      if ( ValueW > 0 )
        v6 = (unsigned __int16)ValueW | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_41;
      v17 = 791;
      goto LABEL_24;
    }
  }
  else if ( pvData[0] )
  {
    v18 = 830;
    goto LABEL_37;
  }
  memset_0(Data, 0, 0xAAu);
  cbData = 170;
  v19 = RegGetValueW(hkey, 0, L"InstallLanguage", 2u, 0, Data, &cbData);
  v6 = v19;
  if ( v19 )
  {
    if ( v19 != 2 )
    {
      if ( v19 > 0 )
        v6 = (unsigned __int16)v19 | 0x80070000;
      if ( v6 >= 0 )
        goto LABEL_41;
      v17 = 808;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecoreuap\\base\\globalization\\coreglobconfig\\src\\coreglobconfig.cpp",
        (const char *)(unsigned int)v6,
        phkResulta);
LABEL_41:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return v6;
    }
  }
  else if ( *(_WORD *)Data )
  {
    v12 = RegSetValueExW(hkey, L"PreviousInstallLanguage", 0, 1u, Data, cbData);
    if ( v12 )
    {
      v14 = 824;
      goto LABEL_40;
    }
    goto LABEL_38;
  }
  v18 = 813;
LABEL_37:
  wil::details::in1diag3::Log_Hr(retaddr, (void *)v18, v16, (const char *)0x8000FFFFLL, phkResulta);
LABEL_38:
  v12 = RegSetValueExW(hkey, L"InstallLanguage", 0, 1u, (const BYTE *)psz, 2 * pcchLength + 2);
  if ( v12 )
  {
    v14 = 839;
    goto LABEL_40;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
LABEL_43:
  v20 = NtSetDefaultUILanguage(0);
  if ( v20 < 0 )
    wil::details::in1diag3::_Log_NtStatus(retaddr, v21, v22, (const char *)(unsigned int)v20, phkResult);
  MUIRegistryInfo = NtGetMUIRegistryInfo(10, 0, 0);
  if ( MUIRegistryInfo < 0 )
    wil::details::in1diag3::Return_NtStatus(
      retaddr,
      (void *)0x2BE,
      v24,
      (const char *)(unsigned int)MUIRegistryInfo,
      phkResult);
  return 0;
}

```

## disassembly

```asm
0x1800136c8  mov     [rsp-8+arg_10], rbx
0x1800136cd  push    rbp
0x1800136ce  push    rsi
0x1800136cf  push    rdi
0x1800136d0  push    r14
0x1800136d2  push    r15
0x1800136d4  lea     rbp, [rsp-190h]
0x1800136dc  sub     rsp, 290h
0x1800136e3  mov     rax, cs:__security_cookie
0x1800136ea  xor     rax, rsp
0x1800136ed  mov     [rbp+1B0h+var_30], rax
0x1800136f4  mov     edi, r8d
0x1800136f7  movzx   esi, dx
0x1800136fa  mov     rbx, rcx
0x1800136fd  mov     r15d, 0AAh
0x180013703  xor     r14d, r14d
0x180013706  lea     rcx, [rsp+2B0h+var_240]; void *
0x18001370b  mov     r8d, r15d; Size
0x18001370e  mov     [rsp+2B0h+var_268], r14d
0x180013713  xor     edx, edx; Val
0x180013715  call    memset_0
0x18001371a  xor     eax, eax
0x18001371c  mov     [rsp+2B0h+pcchLength], r14
0x180013721  mov     rcx, rbx
0x180013724  mov     qword ptr [rsp+2B0h+psz], rax
0x180013729  mov     [rsp+2B0h+var_248], eax
0x18001372d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180013732  mov     r8, rax; unsigned __int16 *
0x180013735  lea     rcx, [rsp+2B0h+var_240]; unsigned __int16 *
0x18001373a  lea     edx, [r14+55h]; unsigned __int64
0x18001373e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013743  mov     ebx, eax
0x180013745  test    eax, eax
0x180013747  jns     short loc_18001376B
0x180013749  mov     edx, 2ECh; void *
0x18001374e  mov     rcx, [rbp+1B8h]; this
0x180013755  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x18001375c  mov     r9d, ebx; char *
0x18001375f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013764  mov     eax, ebx
0x180013766  jmp     loc_180013A62
0x18001376b  mov     r9d, esi
0x18001376e  lea     r8, a4x; "%.4x"
0x180013775  mov     esi, 6
0x18001377a  lea     rcx, [rsp+2B0h+psz]; unsigned __int16 *
0x18001377f  mov     edx, esi; unsigned __int64
0x180013781  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180013786  mov     ebx, eax
0x180013788  test    eax, eax
0x18001378a  jns     short loc_180013793
0x18001378c  mov     edx, 2EDh
0x180013791  jmp     short loc_18001374E
0x180013793  lea     r8, [rsp+2B0h+pcchLength]; pcchLength
0x180013798  mov     rdx, rsi; cchMax
0x18001379b  lea     rcx, [rsp+2B0h+psz]; psz
0x1800137a0  call    StringLengthWorkerW
0x1800137a5  mov     ebx, eax
0x1800137a7  test    eax, eax
0x1800137a9  jns     short loc_1800137B2
0x1800137ab  mov     edx, 2EEh
0x1800137b0  jmp     short loc_18001374E
0x1800137b2  lea     r8, [rsp+2B0h+var_268]
0x1800137b7  mov     ecx, 4888h
0x1800137bc  lea     rdx, [rsp+2B0h+var_240]
0x1800137c1  call    cs:__imp_RtlpSetPreferredUILanguages
0x1800137c7  test    eax, eax
0x1800137c9  jns     short loc_1800137E4
0x1800137cb  mov     edx, 2F6h; void *
0x1800137d0  mov     rcx, [rbp+1B8h]; this
0x1800137d7  mov     r9d, eax; char *
0x1800137da  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800137df  jmp     loc_180013A62
0x1800137e4  mov     esi, 2
0x1800137e9  test    sil, dil
0x1800137ec  jnz     short loc_18001380E
0x1800137ee  lea     r8, [rsp+2B0h+var_268]
0x1800137f3  mov     ecx, 2888h
0x1800137f8  lea     rdx, [rsp+2B0h+var_240]
0x1800137fd  call    cs:__imp_RtlpSetPreferredUILanguages
0x180013803  test    eax, eax
0x180013805  jns     short loc_18001380E
0x180013807  mov     edx, 2FEh
0x18001380c  jmp     short loc_1800137D0
0x18001380e  test    dil, 4
0x180013812  jz      loc_180013A1F
0x180013818  xor     edx, edx
0x18001381a  mov     [rsp+2B0h+hkey], r14
0x18001381f  lea     rcx, [rsp+2B0h+hkey]
0x180013824  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180013829  lea     rax, [rsp+2B0h+hkey]
0x18001382e  mov     r9d, 2001Fh; samDesired
0x180013834  xor     r8d, r8d; ulOptions
0x180013837  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001383c  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\NLS"...
0x180013843  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001384a  call    cs:__imp_RegOpenKeyExW
0x180013850  test    eax, eax
0x180013852  jz      short loc_18001385E
0x180013854  mov     edx, 30Ah
0x180013859  jmp     loc_1800139F5
0x18001385e  mov     r8, r15; Size
0x180013861  lea     rcx, [rbp+1B0h+var_E0]; void *
0x180013868  xor     edx, edx; Val
0x18001386a  call    memset_0
0x18001386f  mov     rcx, [rsp+2B0h+hkey]; hkey
0x180013874  lea     rax, [rsp+2B0h+var_260]
0x180013879  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18001387e  lea     r8, Value; "PreviousInstallLanguage"
0x180013885  lea     rax, [rbp+1B0h+var_E0]
0x18001388c  mov     [rsp+2B0h+var_260], r15d
0x180013891  mov     [rsp+2B0h+pvData], rax; pvData
0x180013896  mov     r9d, esi; dwFlags
0x180013899  xor     edx, edx; lpSubKey
0x18001389b  mov     [rsp+2B0h+phkResult], r14; int
0x1800138a0  call    cs:__imp_RegGetValueW
0x1800138a6  mov     ebx, eax
0x1800138a8  mov     edi, 1
0x1800138ad  test    eax, eax
0x1800138af  jz      short loc_1800138EA
0x1800138b1  cmp     eax, esi
0x1800138b3  jz      short loc_1800138FE
0x1800138b5  test    eax, eax
0x1800138b7  jle     short loc_1800138C2
0x1800138b9  movzx   ebx, ax
0x1800138bc  or      ebx, 80070000h
0x1800138c2  test    ebx, ebx
0x1800138c4  jns     loc_180013A06
0x1800138ca  mov     edx, 317h; void *
0x1800138cf  mov     rcx, [rbp+1B8h]; this
0x1800138d6  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\globalization\\coregl"...
0x1800138dd  mov     r9d, ebx; char *
0x1800138e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800138e5  jmp     loc_180013A06
0x1800138ea  cmp     [rbp+1B0h+var_E0], r14w
0x1800138f2  jz      short loc_1800138FE
0x1800138f4  mov     edx, 33Eh
0x1800138f9  jmp     loc_1800139A9
0x1800138fe  mov     r8, r15; Size
0x180013901  lea     rcx, [rbp+1B0h+Data]; void *
0x180013905  xor     edx, edx; Val
0x180013907  call    memset_0
0x18001390c  mov     rcx, [rsp+2B0h+hkey]; hkey
0x180013911  lea     rax, [rsp+2B0h+cbData]
0x180013916  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18001391b  lea     r8, aInstalllanguag; "InstallLanguage"
0x180013922  lea     rax, [rbp+1B0h+Data]
0x180013926  mov     [rsp+2B0h+cbData], r15d
0x18001392b  mov     [rsp+2B0h+pvData], rax; pvData
0x180013930  mov     r9d, esi; dwFlags
0x180013933  xor     edx, edx; lpSubKey
0x180013935  mov     [rsp+2B0h+phkResult], r14; int
0x18001393a  call    cs:__imp_RegGetValueW
0x180013940  mov     ebx, eax
0x180013942  test    eax, eax
0x180013944  jz      short loc_180013969
0x180013946  cmp     eax, esi
0x180013948  jz      short loc_1800139A4
0x18001394a  test    eax, eax
0x18001394c  jle     short loc_180013957
0x18001394e  movzx   ebx, ax
0x180013951  or      ebx, 80070000h
0x180013957  test    ebx, ebx
0x180013959  jns     loc_180013A06
0x18001395f  mov     edx, 328h
0x180013964  jmp     loc_1800138CF
0x180013969  cmp     word ptr [rbp+1B0h+Data], r14w
0x18001396e  jz      short loc_1800139A4
0x180013970  mov     eax, [rsp+2B0h+cbData]
0x180013974  lea     rdx, Value; "PreviousInstallLanguage"
0x18001397b  mov     rcx, [rsp+2B0h+hkey]; hKey
0x180013980  mov     r9d, edi; dwType
0x180013983  mov     dword ptr [rsp+2B0h+pvData], eax; cbData
0x180013987  xor     r8d, r8d; Reserved
0x18001398a  lea     rax, [rbp+1B0h+Data]
0x18001398e  mov     [rsp+2B0h+phkResult], rax; lpData
0x180013993  call    cs:__imp_RegSetValueExW
0x180013999  test    eax, eax
0x18001399b  jz      short loc_1800139BB
0x18001399d  mov     edx, 338h
0x1800139a2  jmp     short loc_1800139F5
0x1800139a4  mov     edx, 32Dh; void *
0x1800139a9  mov     rcx, [rbp+1B8h]; this
0x1800139b0  mov     r9d, 8000FFFFh; char *
0x1800139b6  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800139bb  mov     eax, dword ptr [rsp+2B0h+pcchLength]
0x1800139bf  lea     rdx, aInstalllanguag; "InstallLanguage"
0x1800139c6  mov     rcx, [rsp+2B0h+hkey]; hKey
0x1800139cb  mov     r9d, edi; dwType
0x1800139ce  xor     r8d, r8d; Reserved
0x1800139d1  lea     eax, ds:2[rax*2]
0x1800139d8  mov     dword ptr [rsp+2B0h+pvData], eax; cbData
0x1800139dc  lea     rax, [rsp+2B0h+psz]
0x1800139e1  mov     [rsp+2B0h+phkResult], rax; int
0x1800139e6  call    cs:__imp_RegSetValueExW
0x1800139ec  test    eax, eax
0x1800139ee  jz      short loc_180013A15
0x1800139f0  mov     edx, 347h; void *
0x1800139f5  mov     rcx, [rbp+1B8h]; this
0x1800139fc  mov     r9d, eax; char *
0x1800139ff  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180013a04  mov     ebx, eax
0x180013a06  lea     rcx, [rsp+2B0h+hkey]
0x180013a0b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013a10  jmp     loc_180013764
0x180013a15  lea     rcx, [rsp+2B0h+hkey]
0x180013a1a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180013a1f  xor     ecx, ecx; LanguageId
0x180013a21  call    cs:__imp_NtSetDefaultUILanguage
0x180013a27  test    eax, eax
0x180013a29  jns     short loc_180013A3A
0x180013a2b  mov     rcx, [rbp+1B8h]; this
0x180013a32  mov     r9d, eax; char *
0x180013a35  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180013a3a  xor     edx, edx
0x180013a3c  xor     r8d, r8d
0x180013a3f  lea     ecx, [rdx+0Ah]
0x180013a42  call    cs:__imp_NtGetMUIRegistryInfo
0x180013a48  test    eax, eax
0x180013a4a  jns     short loc_180013A60
0x180013a4c  mov     rcx, [rbp+1B8h]; this
0x180013a53  mov     r9d, eax; char *
0x180013a56  mov     edx, 2BEh; void *
0x180013a5b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180013a60  xor     eax, eax
0x180013a62  mov     rcx, [rbp+1B0h+var_30]
0x180013a69  xor     rcx, rsp; StackCookie
0x180013a6c  call    __security_check_cookie
0x180013a71  mov     rbx, [rsp+2B0h+arg_10]
0x180013a79  add     rsp, 290h
0x180013a80  pop     r15
0x180013a82  pop     r14
0x180013a84  pop     rdi
0x180013a85  pop     rsi
0x180013a86  pop     rbp
0x180013a87  retn
```
