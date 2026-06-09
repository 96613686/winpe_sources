# CellularUxBackupRestoreHandler::RestoreWifiFailover(Windows::Data::NetworkUX::Cellular::_bond_enumerators::WifiFailoverValue::WifiFailoverValue)

- ea: `0x1800f3904`
- end: `0x1800f3a7f`
- name: `?RestoreWifiFailover@CellularUxBackupRestoreHandler@@AEAAXW4WifiFailoverValue@2_bond_enumerators@Cellular@NetworkUX@Data@Windows@@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f3320`

## callees

- `0x18000c6e0`
- `0x1800156b0`
- `0x18001cf84`
- `0x18001d0a8`
- `0x18001d5fc`
- `0x18001daf4`
- `0x18002498c`
- `0x180031774`
- `0x1800bf3dc`
- `0x1800f3904`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x1800f3979`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800f3979`
- `ADVAPI32!RegSetValueExW` at `0x1800f3a34`
- `ADVAPI32!RegSetValueExW` at `0x1800f3a34`
- `ADVAPI32!RegCreateKeyExW` at `0x1800f39ef`
- `ADVAPI32!RegCreateKeyExW` at `0x1800f39ef`

## pseudocode

```c
__int64 __fastcall CellularUxBackupRestoreHandler::RestoreWifiFailover(__int64 a1, int a2)
{
  int v2; // ecx
  __int64 v3; // rax
  __int64 v4; // rax
  const WCHAR *v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-19h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-19h]
  BYTE Data[8]; // [rsp+50h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+1Fh] BYREF
  _BYTE v13[32]; // [rsp+60h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  v2 = 2;
  if ( a2 != 2 )
    v2 = 0;
  *(_DWORD *)Data = v2;
  std::wstring::wstring(v13);
  std::wstring::resize(v13, 256);
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  if ( (int)RtlGetPersistedStateLocation(
              L"WcmSvcRoot",
              0,
              L"SOFTWARE\\Microsoft\\WcmSvc\\CellularFailover",
              0,
              v3,
              512,
              0) < 0 )
  {
    v4 = std::_WChar_traits<unsigned short>::length(L"SOFTWARE\\Microsoft\\WcmSvc\\CellularFailover");
    std::wstring::_Assign<unsigned short>(v13, L"SOFTWARE\\Microsoft\\WcmSvc\\CellularFailover", v4);
  }
  hKey = 0;
  v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x178,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\cellularuxbackuprestorehandler.cpp",
      (const char *)v6,
      dwOptions);
  v7 = RegSetValueExW(hKey, L"AllowFailover", 0, 4u, Data, 4u);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x179,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\cellularuxbackuprestorehandler.cpp",
      (const char *)v7,
      dwOptionsa);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return std::wstring::_Tidy_deallocate(v13);
}

```

## disassembly

```asm
0x1800f3904  push    rbp
0x1800f3906  lea     rbp, [rsp-57h]
0x1800f390b  sub     rsp, 90h
0x1800f3912  mov     rax, cs:__security_cookie
0x1800f3919  xor     rax, rsp
0x1800f391c  mov     [rbp+57h+var_10], rax
0x1800f3920  mov     ecx, 2
0x1800f3925  xor     eax, eax
0x1800f3927  cmp     edx, ecx
0x1800f3929  cmovnz  ecx, eax
0x1800f392c  mov     dword ptr [rbp+57h+Data], ecx
0x1800f392f  lea     rcx, [rbp+57h+var_30]
0x1800f3933  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800f3938  nop
0x1800f3939  mov     edx, 100h
0x1800f393e  lea     rcx, [rbp+57h+var_30]
0x1800f3942  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800f3947  lea     rcx, [rbp+57h+var_30]
0x1800f394b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f3950  mov     [rsp+90h+lpSecurityAttributes], 0
0x1800f3959  mov     [rsp+90h+samDesired], 200h
0x1800f3961  mov     qword ptr [rsp+90h+dwOptions], rax
0x1800f3966  xor     r9d, r9d
0x1800f3969  lea     r8, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\WcmSvc\\CellularFa"...
0x1800f3970  xor     edx, edx
0x1800f3972  lea     rcx, aWcmsvcroot; "WcmSvcRoot"
0x1800f3979  call    cs:__imp_RtlGetPersistedStateLocation
0x1800f397f  test    eax, eax
0x1800f3981  jns     short loc_1800F39A3
0x1800f3983  lea     rcx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\WcmSvc\\CellularFa"...
0x1800f398a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800f398f  mov     r8, rax
0x1800f3992  lea     rdx, aSoftwareMicros_11; "SOFTWARE\\Microsoft\\WcmSvc\\CellularFa"...
0x1800f3999  lea     rcx, [rbp+57h+var_30]
0x1800f399d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800f39a2  nop
0x1800f39a3  mov     [rbp+57h+hKey], 0
0x1800f39ab  lea     rcx, [rbp+57h+var_30]
0x1800f39af  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800f39b4  mov     rdx, rax; lpSubKey
0x1800f39b7  mov     [rsp+90h+lpdwDisposition], 0; lpdwDisposition
0x1800f39c0  lea     rax, [rbp+57h+hKey]
0x1800f39c4  mov     [rsp+90h+phkResult], rax; phkResult
0x1800f39c9  mov     [rsp+90h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800f39d2  mov     [rsp+90h+samDesired], 20006h; samDesired
0x1800f39da  mov     [rsp+90h+dwOptions], 0; unsigned int
0x1800f39e2  xor     r9d, r9d; lpClass
0x1800f39e5  xor     r8d, r8d; Reserved
0x1800f39e8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f39ef  call    cs:__imp_RegCreateKeyExW
0x1800f39f5  mov     rcx, [rbp+5Fh]; this
0x1800f39f9  test    eax, eax
0x1800f39fb  jz      short loc_1800F3A12
0x1800f39fd  mov     r9d, eax; char *
0x1800f3a00  lea     r8, aPcshellShellCl_37; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f3a07  mov     edx, 178h; void *
0x1800f3a0c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800f3a12  mov     r9d, 4; dwType
0x1800f3a18  mov     [rsp+90h+samDesired], r9d; cbData
0x1800f3a1d  lea     rax, [rbp+57h+Data]
0x1800f3a21  mov     qword ptr [rsp+90h+dwOptions], rax; unsigned int
0x1800f3a26  xor     r8d, r8d; Reserved
0x1800f3a29  lea     rdx, aAllowfailover; "AllowFailover"
0x1800f3a30  mov     rcx, [rbp+57h+hKey]; hKey
0x1800f3a34  call    cs:__imp_RegSetValueExW
0x1800f3a3a  mov     rcx, [rbp+5Fh]; this
0x1800f3a3e  test    eax, eax
0x1800f3a40  jz      short loc_1800F3A57
0x1800f3a42  mov     r9d, eax; char *
0x1800f3a45  lea     r8, aPcshellShellCl_37; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800f3a4c  mov     edx, 179h; void *
0x1800f3a51  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800f3a57  lea     rcx, [rbp+57h+hKey]
0x1800f3a5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800f3a60  nop
0x1800f3a61  lea     rcx, [rbp+57h+var_30]
0x1800f3a65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800f3a6a  mov     rcx, [rbp+57h+var_10]
0x1800f3a6e  xor     rcx, rsp; StackCookie
0x1800f3a71  call    __security_check_cookie
0x1800f3a76  add     rsp, 90h
0x1800f3a7d  pop     rbp
0x1800f3a7e  retn
```
